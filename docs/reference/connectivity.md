---
title: Conectividade | Microsoft Docs
description: Informações sobre conectividade e modos de conexão para Visual Studio Live Share.
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
ms.openlocfilehash: e1a2567b18e7dbd30d86e49a22950d300fb0a95b
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870520"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Requisitos de conectividade do Live Share

Este artigo resume os requisitos de conectividade para Visual Studio Live Share, opções de conectividade disponíveis e soluções alternativas conhecidas, quando aplicável.

## <a name="sign-in"></a>Entrar

Você pode entrar Live Share usando qualquer [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) conta corporativa ou de estudante com suporte, um [conta Microsoft](https://account.microsoft.com/account)ou um [perfil do GitHub](https://github.com/). Normalmente, as URLs de entrada para elas estão abertas na maioria das organizações, considerando o número de produtos públicos destinados que os usam, mas se não estiverem, entre em contato com seu administrador de rede sobre como abrir `login.microsoftonline.com` e/ou `github.com` além dos domínios [listados abaixo](#requirements-for-connection-modes).

> [!NOTE]
> Contas do AD local (ADFS) e contas corporativas do GitHub local não têm suporte no momento [(vote 👍 )](https://github.com/MicrosoftDocs/live-share/issues/341).

## <a name="connection-modes"></a>Modos de conexão

Para garantir o desempenho ideal, por padrão Visual Studio Live Share detecta automaticamente se um computador host da sessão de colaboração e o computador convidado podem se comunicar diretamente por meio de uma rede e somente retransmissões por meio da nuvem se não houver nenhuma rota entre eles. Esse modo "automático" misto é flexível e até mesmo permite que alguns convidados retransmitam por meio da nuvem enquanto outros se conectam diretamente à mesma sessão.

As conexões diretas são autenticadas por meio de um mecanismo baseado em nuvem para garantir a segurança, mas exigem que uma porta entre 5990 e 5999 seja aberta para habilitar a conectividade. Como resultado, ao compartilhar pela primeira vez, o firewall da área de trabalho pode solicitar que você abra uma porta. Aceitar isso é opcional, pois ignorar isso fará com que Live Share sempre use a retransmissão quando estiver no modo auto.

Todas as conexões em Visual Studio Live Share são criptografadas por SSH ou SSL e autenticadas em relação a um serviço central para garantir que apenas aquelas na sessão de colaboração possam obter acesso ao seu conteúdo. Além disso, a retransmissão de nuvem do Live Share não mantém nenhum tráfego roteado através dele e não "espiona" o tráfego de forma alguma.

## <a name="changing-the-connection-mode"></a>Alterando o modo de conexão

Se você preferir desabilitar conexões diretas ou retransmitidas ou simplesmente solucionar problemas de conectividade, poderá forçar outros modos de conexão.

| Modo | Comportamento do host | Comportamento do convidado |
|------|----------------|----------------------|
| Auto | A sessão de colaboração do host aceita conexões diretas seguras e autenticadas ou conexões de nuvem retransmitidas. | Tenta usar uma conexão direta e volta a retransmitir pela nuvem se isso falhar. |
| Direto | A sessão de colaboração do host só aceita conexões diretas autenticadas e seguras. | Tenta usar uma conexão direta e para quando ela não puder se conectar. |
| Retransmissão | A sessão de colaboração do host não permite conexões diretas. Nenhuma porta está aberta no computador do host. | Sempre se conecta por meio da nuvem. |

Para alterar o modo:

**VS**

1. Vá para ferramentas > opções > Live Share.
2. Selecione o modo no menu suspenso "modo de conexão".
3. Reinicie o VS.

**VS Code:**

1. Edite settings.jsem (> preferências de arquivo > configurações).
2. Defina `"liveshare.connectionMode"` como `"auto"` , `"direct"` ou `"relay"` dependendo de sua preferência.
3. Reinicie VS Code.

## <a name="requirements-for-connection-modes"></a>Requisitos para modos de conexão

O modo de conexão em que você está determinará as portas e URLs específicas que precisam estar disponíveis para que Live Share funcionem.

| Modo | Requisito de acesso de cliente | Solução de problemas |
|------|--------------|-----------------|
| Qualquer | Acesso de saída para `*.liveshare.vsengsaas.visualstudio.com:443` | Verifique se o firewall de rede corporativo ou pessoal permite que você se conecte a este domínio. Insira https://insiders.liveshare.vsengsaas.visualstudio.com em um navegador e verifique se você Lande o home page Visual Studio Live share. Você também pode estar executando [problemas de proxy](#proxies) que precisam ser resolvidos.|
| Qualquer (VS Code) | Acesso de saída para `download.microsoft.com:443` | Verifique se o firewall de rede corporativo ou pessoal permite que você se conecte a este domínio. Você também pode estar executando [problemas de proxy](#proxies) que precisam ser resolvidos. |
| Auto | Comutadores automáticos. Consulte modos diretos e de retransmissão. | Alterne para o modo direto ou de retransmissão para solucionar problemas. |
| Direto | Hosts: uma porta no intervalo de 5990 a 5999 precisa ser aberta para aceitar conexões de rede local de entrada.<br /><br />Convidados: uma rota de rede e acesso de saída para o host nessa mesma porta. | Verifique se o "vsls-Agent" não está bloqueado pelo seu software de firewall de desktop para esse intervalo de porta e se você pode executar o ping um do outro. Embora o Windows e outros softwares de desktop devam solicitar a primeira vez que o agente é iniciado, vimos instâncias em que as políticas de grupo impedem que isso aconteça e você precisará [adicionar manualmente a entrada](#manually-adding-a-firewall-entry). Você também pode estar executando [problemas de proxy](#proxies) que precisam ser resolvidos. |
| Retransmissão | Acesso de saída para `*.servicebus.windows.net:443` . | Verifique se o firewall de rede corporativo ou pessoal permite que você se conecte a este domínio. Você também pode estar executando [problemas de proxy](#proxies) que precisam ser resolvidos.|

## <a name="manually-adding-a-firewall-entry"></a>Adicionando manualmente uma entrada de firewall

Conforme descrito acima, o modo direto requer que o firewall pessoal permita que o **vsls** aceite conexões no intervalo de portas 5990-5999. Se você quiser usar o modo direto, mas tiver encontrado que o firewall não tem a entrada vsls-Agent, você poderá adicioná-lo manualmente. A maneira como você faz isso varia por software de firewall, mas você pode encontrar informações sobre como **[Configurar o Firewall do Windows aqui](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)**.

Se você não vir uma entrada para o vsls-Agent, poderá encontrar o executável do agente em um dos seguintes locais.

### <a name="vs-code-agent-location"></a>Local do agente de VS Code

**Versão** substituta do número de versão da extensão em um dos caminhos abaixo:

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Local do agente do Visual Studio

O local do Visual Studio é mais dinâmico, mas você pode seguir estas etapas para encontrar o executável:

1. Navegue até o local de instalação do Visual Studio. Normalmente, é `C:\Program Files (x86)\Microsoft Visual Studio\EDITION` aí que a **edição** é Comunidade, empresa, etc.

2. Execute uma pesquisa para `vsls-agent.exe` o em na subpasta **IDE\Extensions** .

Infelizmente, talvez seja necessário fazer essa etapa **sempre que você atualizar Visual Studio Live share.**

## <a name="proxies"></a>Proxies

Visual Studio Live Share atualmente tem algumas limitações sobre o uso de proxy. Embora as configurações de proxy automáticas funcionem no Windows, ao usar o macOS ou Linux (e com determinadas configurações de proxy no Windows), as variáveis de ambiente **http_proxy** e **HTTPS_PROXY** precisarão ser definidas *globalmente*.

Se o proxy não os definir automaticamente para você, você poderá definir manualmente as variáveis no seguinte formato:

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

Se você tiver um proxy de autenticação, poderá adicionar o usuário e a senha da seguinte maneira:

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

Se essas configurações não resolverem o problema para você, informe [-nos](https://github.com/MicrosoftDocs/live-share/issues/86) sobre as especificidades de sua configuração de proxy para que possamos dar uma olhada no aprimoramento do suporte.

## <a name="see-also"></a>Confira também

- [Como colaborar usando o Visual Studio Code](../use/vscode.md)
- [Como colaborar usando o Visual Studio](../use/vs.md)
- [Funcionalidades de segurança do Live Share](security.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
