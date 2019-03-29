---
title: Solução de problemas - compartilhamento ao vivo do Visual Studio | Microsoft Docs
description: Solução de problemas de dicas e truques para Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: troubleshooting
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5fc611714d148a9ba1d5a6848e0399af753d1a37
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640205"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Solução de problemas de compartilhamento ao vivo do Visual Studio

Este artigo aborda as dicas de solução de problemas, soluções alternativas e respostas para perguntas e problemas comuns. Talvez você queira dar uma olhada a [perguntas frequentes sobre](faq.md). 

## <a name="installation--tool-requirements"></a>Instalação / ferramenta requisitos

A seguir é de solução de problemas relacionadas à instalação do Visual Studio Live Share de dicas.

| Ferramenta | Problema | Resolução / solução alternativa |
|------|---------|------------|
| VS | O instalador de extensão <strong>não é possível localizar uma versão do Visual Studio</strong> usar durante a tentativa de instalar a extensão do Visual Studio Live Share. | Requer o Visual Studio Live Share **Visual Studio 2017 versão 15.6** ou superior para hosts e convidados. Instalar o estável mais recente [atualização do Visual Studio 2017](https://visualstudio.com/vs/) e tente novamente.|
| VS Code | Aparecerá um erro ao tentar usar o Visual Studio Live Share com o VS Code no macOS <strong>El Capitan ou abaixo</strong>. | Suporte do Visual Studio Live Share sistema operacional é dependente no .NET Core que atualmente [dá suporte apenas a macOS Sierra e superior.]((https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).) |
| VS Code | Um "**não foi possível instalar as dependências**" erro aparece quando é de extensão **Concluindo a instalação** na primeira inicialização, ou você receber erros **ausente ou arquivosjáestápresente**. | Verifique se você estiver usando um **conexão de rede em boas condições**. Se você estiver, você poderia estar executando em um **proxy ou firewall** problema. Ver [solução de problemas de conectividade](#connectivity). <br /><br />|
| VS Code | Instalar a extensão do Visual Studio Live Share do marketplace <strong>instala-o na versão stable/insiders do VS Code</strong> em vez da versão desejada. | Iniciar estável do VS Code ou insiders dependendo de sua preferência, clique na guia "extensões", pesquise por "Visual Studio Live Share" e instalar a partir daí. |
| VS Code (**Linux**) | A extensão de compartilhamento ao vivo não ativa e **nenhum item de barra de status aparecer** depois de instalar a extensão em **Linux**. | Visual Studio Live Share depende do .NET Core 2.0 que tem uma série de pré-requisitos de Linux que não podem ser atendidos em determinadas distribuições do Linux por padrão. Ver [aqui para obter detalhes](reference/linux.md#install-linux-prerequisites) sobre o que deve ser instalado. |

## <a name="sign-in"></a>Entrar

A seguir é dicas de solução de problemas de entrada.

| Ferramenta | Problema | Resolução / solução alternativa |
|------|---------|------------|
| VS | Você precisa entrar no Visual Studio Live Share com um <strong>identidade diferente</strong> que você usa para entrar no Visual Studio. | Vá para Ferramentas > Opções > Live Share > conta de usuário para selecionar uma conta alternativa. |
| VS Code | Embora uma navegador janela é exibida durante a entrada e o processo <strong>parece ter êxito na página da web</strong>, a barra de status <strong>ainda diz, "Entrar"</strong> depois de fechar o navegador. | Depois de entrar, clique em "Problemas?" e siga as instruções para inserir um código de usuário temporárias na ferramenta.<br /><br />Também Gostaríamos muito ver o que pode estar ocorrendo, isso por favor [registrar um bug](https://aka.ms/vsls-problem). |
| Todos | Você está obtendo uma <strong>erro de tempo limite ou conexão</strong>. | Ver [solução de problemas de conectividade](#connectivity). |
| Todos | Quando entrar usando um Microsoft feito **ou de estudante endereço de email** você verá uma mensagem dizendo **"Precisa de aprovação de administrador"**. | Sua filosofia do AD do Azure está configurado para exigir "consentimento do administrador" para novos aplicativos que acessam o conteúdo do diretório. Ver [aqui](reference/security.md) para obter mais detalhes. |
| VS Code (**macOS**) | Quando a assinatura se você vir um erro informando **SecKeychainAddGenericPassword() falhado**. | Isso é quase sempre devido a um problema comum com macOS em que as alterações de senha não são refletidas no conjunto de chaves de logon. Tente entrar em um "Conjunto de chaves de acesso", bloqueando o conjunto de chaves de logon e, em seguida, desbloqueá-lo novamente. Isso pode ser suficiente para resolver o problema, mas se não for possível desbloqueá-lo com sua senha atual, tente usar seu anterior. Se isso funcionar, altere a senha de logon do conjunto de chaves para sua senha atual. Ver [aqui](https://support.apple.com/en-us/HT201609) para obter detalhes. |
| VS Code (**Linux**) | Ao inserir no código de usuário depois de entrar por meio do navegador, você verá um erro informando **secret_password_store_sync() falhou com o código de erro XX**. | Isso normalmente é devido à `gnome-keyring` e/ou `libsecret-1-0` /  `libsecret` não está sendo instalado. Você pode validar o token de autenticação gnome está configurado corretamente, instalando `seahorse` e, em seguida, usar o aplicativo de "Senhas e chaves" no seu ambiente de área de trabalho. Leia mais sobre [pré-requisitos de Linux aqui](reference/linux.md#install-linux-prerequisites). |
| VS Code (**Linux**) | Você está <strong>solicitado a inserir um código de usuário</strong> com Live Share v0.3.295 ou abaixo, mas nenhum navegador é exibida permitir que você obtenha uma. | Estamos trabalhando para eliminar a necessidade de código do usuário no Linux. Durante o tempo médio, deve aparecer uma janela do navegador para que você possa usar para entrar. Caso contrário, a janela do navegador pode estar oculto sob o VS Code. Consulte a próxima dica se isso não for o caso.  |
| VS Code | Depois de clicar em "Entrar" (ou usando o "compartilhamento ao vivo: Entrar no"comando), <strong>nenhuma janela do navegador é exibida permitir que você insira suas credenciais</strong>. | 1. [Inscrever-se aqui](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2. Depois de entrar, clique em "Problemas?"<br /> 3. Siga as instruções para inserir um código de usuário temporárias na ferramenta. |
| Todos | Você gostaria <strong>junção</strong> uma sessão de colaboração</strong> mas <strong>ainda não tiver / não deseja receber atualizações por email</strong>. | Entrar para a extensão de compartilhamento ao vivo no código VS/VS faz <strong>não</strong> aceitar você receber atualizações por email.<br /><br />Compartilhamento ao vivo requer convidados entrar como medida de segurança para que o host tem visibilidade para a identidade do que aquelas que se associaram. [Votar esse recurso](https://github.com/MicrosoftDocs/live-share/issues/3) se você deseja que a opção para permitir que usuários anônimos ingressar (por exemplo, os usuários sem nome / nome definido pelo usuário). |

## <a name="share-and-join"></a>Compartilhamento e junção

A seguir é dicas de solução de problemas de entrada.

| Ferramenta | Problema | Resolução / solução alternativa |
|------|----------------|------------|
| Todos | <strong>Share/Join:</strong> Você está recebendo um erro informando que não é capaz de se conectar ou o tempo limite. | Ver [solução de problemas de conectividade](#connectivity). |
| VS Code | <strong>Junte-se:</strong> Você estava <strong>não solicitadas / capaz de iniciar o VS Code</strong> após abrir a página de junção em um navegador. |  Dicas: <ul><li>Certifique-se de que você já <i>iniciado do VS Code pelo menos uma vez e aguardaram para a instalação ser concluída na barra de status.</i></li><li>Se isso não funcionar, tente executar o "compartilhamento ao vivo: Comando de instalação do iniciador".</li><li>**Os usuários do Linux**: Se for solicitado a inserir sua senha de administrador (sudo) ao executar o comando acima, faça isso.</li><li>Por fim, veja [unindo manualmente](reference/manual-join.md) como uma solução alternativa.</li></ul> Se você atingir esse problema, adoraríamos saber o que pode estar acontecendo, isso por favor [registrar um bug](https://aka.ms/vsls-new-issue). |
| VS | <strong>Junte-se:</strong> Você estava <strong>não solicitadas / capaz de iniciar o VS</strong>  após abrir a página de junção em um navegador. |  Confira [ingressar manualmente](reference/manual-join.md).<br /><br /> Também Gostaríamos muito ver os logs, portanto, por favor [registrar um bug](https://aka.ms/vsls-problem) usando "Relatório de problema..." do Visual Studio recurso. |
| Todos | <strong>Junte-se:</strong> Você prefere <strong>cole o link de associação diretamente no Visual Studio / VS Code</strong> em vez de clicar no link da web. | Confira [ingressar manualmente](reference/manual-join.md). |
| Todos | <strong>Junte-se:</strong> Você verá uma mensagem dizendo que "**o proprietário do espaço de trabalho parece estar offline**," ao serem unidas por meio do navegador. | Possíveis soluções alternativas:<br /><ul><li>Tente [unindo manualmente](reference/manual-join.md). Temos visto problemas com entre regiões (por exemplo, Leste e Oeste dos EUA) junções devido a problemas de serviço que não afetam junções manuais.</li><li>Compartilhamento ao vivo pode ser não foi possível rotear diretamente ao host durante a execução no modo de conexão "auto". Tente [modo de retransmissão](reference/connectivity.md).</li></ul>Ver [solução de problemas de conectividade](#connectivity) mais possibilidades |
| VS Code | <strong>Junte-se:</strong> Unidas por meio do navegador <strong>antes de entrar no</strong>, não foi solicitado a entrar no</strong>e a associação não foi concluída. |  Esse é um [bug conhecido](https://github.com/MicrosoftDocs/live-share/issues/167). Clique no item da barra de status para entrar e, em seguida, ingressar novamente de entrada. |

## <a name="connectivity"></a>Conectividade

As informações a seguir podem ajudá-lo a solucionar problemas se você estiver tendo problemas relacionados à conectividade ou tempos limite ao entrar, compartilhamento ou ingressar em.

Conforme descrito na [requisitos de conectividade para Live Share](reference/connectivity.md) artigo, modos de conexão diferentes têm requisitos diferentes para funcionar, portanto, há alguns problemas possíveis diferentes acontecendo.

| Ferramenta | Problema | Causa provável |
|------|------|----------------|
| Todos | Você está usando um <strong>proxy</strong> e está vendo uma série de problemas de conectividade | As configurações de proxy podem ser complicadas.  Tente definir a **HTTP_PROXY** e **HTTPS_PROXY** variáveis de ambiente **globalmente** e, em seguida, reiniciar sua ferramenta. Ver [as configurações de proxy](reference/connectivity.md#proxies) para obter mais detalhes. Provavelmente, há algumas configurações que não ainda há suporte, portanto [Fale conosco](https://github.com/MicrosoftDocs/live-share/issues/86) se isso não funcionar para você. |
| VS Code | Depois de instalar a extensão e iniciar o código do VS pela primeira vez que você obtenha uma <strong>um erro quando "Concluindo a instalação" aparece na barra de status</strong>. |  Você não pode acessar a internet ou acesso a download.visualstudio.microsoft.com e/ou download.microsoft.com na porta 443 é bloqueado pelo firewall pessoal ou corporativo. Ver [aqui](https://github.com/MicrosoftDocs/live-share/issues/58) para obter informações sobre por que o Live Share precisa baixar algo no momento. |
| Todos | Você está <strong>não é possível entrar no Visual Studio Live Share</strong> | Você não pode acessar a internet ou acesso a *. liveshare.vsengsaas.visualstudio.com na porta 80/443 é bloqueado pelo firewall pessoal ou corporativo. Insira https://insiders.liveshare.vsengsaas.visualstudio.com em um navegador e verifique se você pousar em home page do Visual Studio Live Share. |
| Todos | Você está no <strong>modo auto</strong> (o padrão), são capazes de entrar, mas consulte um <strong>erro de tempo limite ou conexão</strong> quando o compartilhamento ou ingressar em. | Em ambos direcionam e retransmitam os modos de falha para se conectar ou que há um bug com o modo auto. Se você puder se conectar após [modo de retransmissão ou alternar para direcionar](reference/connectivity.md#changing-the-connection-mode), por favor [gere um bug](https://aka.ms/vsls-problem). |
| Todos | Você está no <strong>modo direto</strong>, são capazes de entrar, mas consulte um <strong>erro de tempo limite ou conexão</strong> quando o compartilhamento ou ingressar em. | O convidado e o host não podem se conectar diretamente. Tente [modo auto ou retransmissão](reference/connectivity.md#changing-the-connection-mode) para ver se o problema desapareça. Talvez você precise [permitir manualmente o Live Share através do firewall pessoal](reference/connectivity.md#manually-adding-a-firewall-entry) ou simplesmente usar o modo de retransmissão. |
| Todos | Estão em <strong>modo de retransmissão</strong>, são capazes de entrar, mas são notificados sobre uma <strong>erro de tempo limite ou conexão</strong> quando o compartilhamento ou unindo. | Acesso a *. servicebus.windows.net na porta 80/443 é bloqueado é bloqueado pelo firewall pessoal ou corporativo. Tente [modo direto](reference/connectivity.md#changing-the-connection-mode). |

Consulte a [requisitos de conectividade para Live Share](reference/connectivity.md) artigo, para obter mais informações sobre requisitos de conectividade.

## <a name="see-also"></a>Consulte também

Guias de Início Rápido

- [Compartilhar seu primeiro projeto](quickstart/share.md)
- [Ingressar em sua primeira sessão](quickstart/join.md)

Instruções

- [Colaborar usando o Visual Studio Code](use/vscode.md)
- [Colaborar usando o Visual Studio](use/vs.md)

Referência

- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)
- [Requisitos de conectividade do Live Share](reference/connectivity.md)
- [Detalhes de instalação do Linux](reference/linux.md)
- [Suporte de idioma e plataforma](reference/platform-support.md)
- [Suporte de extensão](reference/extensions.md)

Ainda está tendo problemas? Você pode [fornecer comentários](support.md).
