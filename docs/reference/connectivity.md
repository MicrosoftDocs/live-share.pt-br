---
title: Conectividade - compartilhamento ao vivo do Visual Studio | Microsoft Docs
description: Informações sobre modos de conectividade e conexão para o Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c685df798fc10b449c3e73db678e3b5d34e73ef0
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640075"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Requisitos de conectividade para o compartilhamento ao vivo

Este artigo resume os requisitos de conectividade para o Visual Studio Live Share, opções de conectividade disponíveis e soluções alternativas conhecidas quando aplicável.

## <a name="sign-in"></a>Entrar

Você pode entrar no Live Share usando qualquer [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) suporte conta corporativa ou estudante, um [conta da Microsoft](https://account.microsoft.com/account), ou uma [perfil do GitHub](https://github.com/). Normalmente entrar URLs para os mesmos estão abertos na maioria das organizações, dado o número de produtos voltado para o públicos que usá-los, mas se não, entre em contato com o administrador da rede sobre abrindo `login.microsoftonline.com` e/ou `github.com` além os domínios [listados abaixo](#requirements-for-connection-modes).

> [!NOTE]
> Local contas do AD (ADFS) e contas do GitHub Enterprise local não têm suporte no momento [(votar 👍)](https://github.com/MicrosoftDocs/live-share/issues/341).

## <a name="connection-modes"></a>Modos de Conexão

Para garantir o melhor desempenho, por padrão, o Visual Studio Live Share detecta automaticamente se uma máquina de host de sessão de colaboração e a máquina convidada podem se comunicar diretamente em uma rede e retransmite apenas por meio da nuvem, se não houver nenhuma rota entre elas. Esse modo misto "auto" é flexível e permite até mesmo alguns convidados para retransmissão por meio da nuvem enquanto outros se conectar diretamente para a mesma sessão.

As conexões diretas são autenticadas por meio de um mecanismo baseado em nuvem para garantir a segurança, mas exige uma porta entre 5990 e 5999 ser aberta para habilitar a conectividade. Como resultado, quando o compartilhamento de seu firewall da área de trabalho pela primeira vez pode solicitar que você abre uma porta. Aceitar opcional como ignorá-la simplesmente fará com que Live Share sempre usar a retransmissão quando no modo auto.

Todas as conexões no Visual Studio Live Share são SSH ou SSL criptografadas e autenticadas em relação a um serviço central para garantir que somente aqueles na sessão de colaboração podem acessar seu conteúdo. Além disso, a retransmissão de nuvem do Live Share não persiste qualquer tráfego roteado por ele e não "rastrear" o tráfego de qualquer forma.

## <a name="changing-the-connection-mode"></a>Alterando o modo de conexão

Se você prefere desabilitar conexões diretas ou retransmissão ou simplesmente estiver solucionando problemas de conectividade, você pode forçar a outros modos de conexão.

| Modo | Comportamento de host | Comportamento de convidado |
|------|----------------|----------------------|
| Automático | Sessão de colaboração do host aceita conexões diretas segura e autenticadas ou conexões de retransmissão na nuvem. | Tenta usar uma conexão direta e voltará para a retransmissão por meio da nuvem no caso de falha. |
| Direto | Sessão de colaboração do host aceita apenas conexões diretas, seguras e autenticadas. | Tenta usar uma conexão direta e interromperá se ele não pode se conectar. |
| Retransmissão | Sessão de colaboração do host não permite conexões diretas. Nenhuma porta é aberta no computador do host. | Sempre se conecta por meio da nuvem. |

Para alterar o modo:

**VS:**

1. Vá para Ferramentas > Opções > Live Share.
2. Selecione o modo na lista suspensa "Modo de Conexão".
3. Reinicie o VS.

**VS Code:**

1. Editar Settings (arquivo > Preferências > Configurações).
2. Definir `"liveshare.connectionMode"` à `"auto"`, `"direct"`, ou `"relay"` dependendo de sua preferência.
3. Reinicie o VS Code.

## <a name="requirements-for-connection-modes"></a>Requisitos para modos de conexão

O modo de conexão em que estão ditará a portas específicas e as URLs que precisam estar disponíveis para o Live Share a função.

| Modo | Requisito de acesso do cliente | Solução de problemas |
|------|--------------|-----------------|
| Qualquer | Acesso de saída para `*.liveshare.vsengsaas.visualstudio.com:443` | Verifique se sua empresa ou firewall pessoal de rede permite que você se conectar a esse domínio. Insira https://insiders.liveshare.vsengsaas.visualstudio.com em um navegador e verifique se você pousar em home page do Visual Studio Live Share. Você também pode estar executando no [problemas de proxy](#proxies) que precisam ser resolvidos.|
| Qualquer (VS Code) | Acesso de saída para `download.microsoft.com:443` | Verifique se sua empresa ou firewall pessoal de rede permite que você se conectar a esse domínio. Você também pode estar executando no [problemas de proxy](#proxies) que precisam ser resolvidos. |
| Automático | Autocomutadores. Consulte direto e modos de retransmissão. | Alterne para direcionar ou modo para solucionar problemas de retransmissão. |
| Direto | Hosts: Uma porta no intervalo 5990 5999 precisa ser aberto para aceitar conexões de entrada de rede local.<br /><br />Convidados: Uma rota de rede e acesso de saída para o host na mesma porta. | Verifique se "vsls-agent" não está bloqueada por seu software de firewall da área de trabalho para esse intervalo de porta e você pode executar ping uma da outra. Embora o Windows e outros softwares de desktop solicitará que você na primeira vez em que o agente é iniciado, temos visto instâncias onde as diretivas de grupo evitar que isso aconteça, e você precisará [adicione manualmente a entrada](#manually-adding-a-firewall-entry). Você também pode estar executando no [problemas de proxy](#proxies) que precisam ser resolvidos. |
| Retransmissão | Acesso de saída para `*.servicebus.windows.net:443`. | Verifique se sua empresa ou firewall pessoal de rede permite que você se conectar a esse domínio. Você também pode estar executando no [problemas de proxy](#proxies) que precisam ser resolvidos.|

## <a name="manually-adding-a-firewall-entry"></a>Adicionar manualmente uma entrada de firewall

Conforme descrito acima, o modo direto exige que permite que seu firewall pessoal **vsls agente** para aceitar conexões na porta de intervalo 5990 5999. Se você quiser usar o modo direto, mas descobriram que seu firewall não tem agente vsls entrada, você pode adicioná-lo manualmente. Como fazer isso varia de acordo com o software de firewall, mas você pode encontrar informações sobre  **[Configurando o Firewall do Windows](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)**.

Se você não vir uma entrada para o agente vsls, você pode localizar o agente executável em um dos seguintes locais.

### <a name="vs-code-agent-location"></a>Local do agente de código VS

SUBSTITUTE **versão** para o número de versão de extensão em um dos caminhos abaixo:

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Local do agente do Visual Studio

O local do Visual Studio é mais dinâmico, mas você pode seguir estas etapas para localizar o executável:

1. Navegue até o local de instalação do Visual Studio. Isso é normalmente `C:\Program Files (x86)\Microsoft Visual Studio\EDITION` onde **EDITION** é Community, Enterprise, etc

2. Executar uma pesquisa para `vsls-agent.exe` no sob o **IDE\Extensions** subpasta.

Infelizmente, você talvez precise realizar esta etapa **sempre que você atualize o Visual Studio Live Share.**

## <a name="proxies"></a>Proxies

Atualmente, o Visual Studio Live Share tem algumas limitações em torno do uso de proxy. Embora as configurações de proxy automático devem funcionar no Windows, ao usar o macOS ou Linux (e, com certas configurações de proxy no Windows) a **HTTP_PROXY** e **HTTPS_PROXY** variáveis de ambiente serão necessário ser definida *globalmente*.

Se seu proxy não será definido automaticamente para você, você pode definir manualmente as variáveis no seguinte formato:

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

Se você tiver um proxy de autenticação, você pode adicionar o usuário e a senha da seguinte maneira:

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

Se essas configurações não resolverem o problema para você, [Fale conosco](https://github.com/MicrosoftDocs/live-share/issues/86) as especificidades de seu proxy para podermos dar uma olhada em como melhorar o suporte de instalação.

## <a name="see-also"></a>Consulte também

- [Como colaborar usando o Visual Studio Code](../use/vscode.md)
- [Como colaborar usando o Visual Studio](../use/vs.md)
- [Funcionalidades de segurança do Live Share](security.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
