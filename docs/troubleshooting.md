---
title: Solução de problemas | Microsoft Docs
description: Dicas e truques de solução de problemas para Visual Studio Live Share.
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
ms.openlocfilehash: 692e129252ac92c159660842b62a45fe4f7db864
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870844"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Solução de problemas Visual Studio Live Share

Este artigo aborda dicas de solução de problemas, soluções alternativas e respostas para problemas e perguntas comuns. Talvez você também queira dar uma olhada nas [perguntas frequentes](faq.md). 

## <a name="installation--tool-requirements"></a>Instalação/requisitos de ferramenta

Veja a seguir as dicas de solução de problemas relacionadas à instalação do Visual Studio Live Share.

| Ferramenta | Problema | Resolução/solução alternativa |
|------|---------|------------|
|VS Code <strong>(MacOS)</strong>| É exibido um aviso informando que o <strong> MacOS não é mais suportado pelo .NET Core <strong>| Esse aviso aparece devido a uma atualização recente [feita pelo .NET Core](https://docs.microsoft.com/en-us/dotnet/core/install/dependencies?tabs=netcore31&pivots=os-macos) que não dá mais suporte a nenhuma versão inferior à <strong>alta Sierra (10.13 +).</strong> Para habilitar a extensão de Live Share, atualize seu sistema operacional.
| VS | O instalador de extensão <strong>não pode encontrar uma versão do Visual Studio</strong> para usar ao tentar instalar a extensão de Visual Studio Live share. | Visual Studio Live Share requer o **Visual Studio 2017 versão 15,6** ou superior para hosts e convidados. Instale a atualização estável mais recente [do Visual Studio 2017](https://visualstudio.com/vs/) e tente novamente. |
| Código VS | Um erro "**dependências não puderam ser instaladas**" parece que a extensão while está **concluindo a instalação** na primeira inicialização ou você obtém erros sobre **arquivos ausentes ou já presentes**. | Verifique se você está em uma **boa conexão de rede**. Se você estiver, poderá estar executando um problema de **proxy ou firewall** . Consulte [solução de problemas de conectividade](#connectivity). <br /><br />|
| Código VS | Instalar a extensão de Visual Studio Live Share do Marketplace a <strong>instala na versão estável/Insider do vs Code</strong> em vez da versão desejada. | Inicie VS Code os inexistentes ou inversos dependendo de sua preferência, clique na guia "extensões", pesquise por "Visual Studio Live Share" e instale a partir daí. |
| VS Code (**Linux**) | A extensão de Live Share não é ativada e **nenhum item de barra de status aparece** depois da instalação da extensão no **Linux**. | O Visual Studio Live Share depende do .NET Core 2,0, que tem vários pré-requisitos do Linux que podem não ser atendidos em determinadas distribuições do Linux por padrão. Consulte [aqui para obter detalhes](reference/linux.md#install-linux-prerequisites) sobre o que deve ser instalado. |

## <a name="sign-in"></a>Entrar

Veja a seguir as dicas de solução de problemas de conexão.

| Ferramenta | Problema | Resolução/solução alternativa |
|------|---------|------------|
| VS | Você precisa entrar Visual Studio Live Share com uma <strong>identidade diferente</strong> da usada para entrar no Visual Studio. | Vá para ferramentas > opções > Live Share > conta de usuário para selecionar uma conta alternativa. |
| Código VS | Enquanto uma janela do navegador é exibida durante a entrada e o processo <strong>parece ter sucesso na página da Web</strong>, a barra de status <strong>ainda diz "entrar"</strong> depois de fechar o navegador. | Depois de entrar, clique em "tendo problemas?" e siga as instruções para inserir um código de usuário temporário na ferramenta.<br /><br />Também adoramos ver o que pode estar acontecendo, portanto, [registre um bug](https://aka.ms/vsls-problem). |
| Tudo | Você está recebendo um <strong>erro de tempo limite ou de conexão</strong>. | Consulte [solução de problemas de conectividade](#connectivity). |
| Tudo | Ao entrar usando um **endereço de email corporativo ou de estudante** com suporte da Microsoft, você verá uma mensagem dizendo **"precisar de aprovação de administrador"**. | Seu princípio do Azure AD é configurado para exigir "consentimento do administrador" para novos aplicativos que acessam o conteúdo do diretório. Veja [aqui](reference/security.md) para obter mais detalhes. |
| VS Code (**MacOS**) | Ao entrar, você verá um erro informando que **SecKeychainAddGenericPassword () falhou**. | Isso é quase sempre devido a um problema comum com o macOS, onde as alterações de senha não são refletidas no conjunto de chaves de logon. Tente entrar em "acesso ao conjunto de chaves", bloquear o conjunto de chaves de logon e, em seguida, desbloqueá-lo novamente. Isso pode ser suficiente para resolver o problema, mas se você não conseguir desbloqueá-lo com sua senha atual, experimente o anterior. Se isso funcionar, altere a senha do conjunto de chaves de logon para sua senha atual. Confira [aqui](https://support.apple.com/en-us/HT201609) para obter detalhes. |
| VS Code (**Linux**) | Ao inserir o código do usuário depois de entrar por meio do navegador, você verá um erro informando **secret_password_store_sync () falhou com o código de erro XX**. | Isso normalmente ocorre devido a `gnome-keyring` e/ou `libsecret-1-0` /  `libsecret` não ser instalado. Você pode validar o gnome-keyring configurado corretamente instalando `seahorse` e usando o aplicativo "senhas e chaves" no seu ambiente de área de trabalho. Leia mais sobre os [pré-requisitos do Linux aqui](reference/linux.md#install-linux-prerequisites). |
| VS Code (**Linux**) | Você será <strong>solicitado a inserir um código de usuário</strong> com Live share v 0.3.295 ou abaixo, mas nenhum navegador aparecerá para permitir que você obtenha um. | Estamos trabalhando para eliminar o requisito de código do usuário no Linux. No tempo médio, uma janela do navegador deve aparecer para que você use para entrar. Caso contrário, a janela do navegador poderá estar oculta em VS Code. Consulte a próxima dica, se esse não for o caso.  |
| Código VS | Depois de clicar em "entrar" (ou usando o comando "Live Share: entrar"), <strong>nenhuma janela do navegador é exibida para permitir que você insira suas credenciais</strong>. | 1. [entre aqui](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2. depois de entrar, clique em "tendo problemas?"<br /> 3. siga as instruções para inserir um código de usuário temporário na ferramenta. |
| Tudo | Você gostaria de <strong>ingressar</strong> em uma sessão de colaboração </strong> , mas <strong>não deseja receber atualizações de email</strong>. | Entrar na extensão de Live Share no VS/VS Code <strong>não</strong> lhe aceita receber atualizações de email.<br /><br />Live Share exige que os convidados entrem como uma medida de segurança para que o host tenha visibilidade da identidade dos que ingressaram. [Vote nesse recurso](https://github.com/MicrosoftDocs/live-share/issues/3) se você quiser a opção de permitir que usuários anônimos ingressem (por exemplo, usuários sem nome definido pelo usuário ou um nome). |

## <a name="share-and-join"></a>Compartilhar e ingressar

Veja a seguir as dicas de solução de problemas de conexão.

| Ferramenta | Problema | Resolução/solução alternativa |
|------|----------------|------------|
| Tudo | <strong>Compartilhamento/junção:</strong> Você está recebendo um tempo limite ou um erro para não conseguir se conectar. | Consulte [solução de problemas de conectividade](#connectivity). |
| Código VS | <strong>Ingressar:</strong> Você <strong>não foi solicitado/capaz de iniciar o vs Code</strong> depois de abrir a página de junção em um navegador. |  Dicas: <ul><li>Verifique se você <i>iniciou o vs Code pelo menos uma vez e aguardou a conclusão da instalação na barra de status.</i></li><li>Se isso não funcionar, tente executar o comando "Live Share: iniciador Setup".</li><li>**Usuários do Linux**: se solicitado a inserir sua senha de administrador (sudo) ao executar o comando acima, faça isso.</li><li>Por fim, consulte [unindo manualmente](reference/manual-join.md) como uma solução alternativa.</li></ul> Se você acertar esse problema, adoraríamos ver o que pode estar acontecendo, portanto, [registre um bug](https://aka.ms/vsls-new-issue). |
| VS | <strong>Ingressar:</strong> Você <strong>não foi solicitado/capaz de iniciar o vs </strong> depois de abrir a página de junção em um navegador. |  Confira [ingressar manualmente](reference/manual-join.md).<br /><br /> Também adoramos ver seus logs, portanto, [registre um bug](https://aka.ms/vsls-problem) usando o Visual Studio "relatar um problema..." recurso. |
| Tudo | <strong>Ingressar:</strong> Você prefere <strong>colar o link de junção diretamente no Visual Studio/vs Code</strong> em vez de clicar no link da Web. | Confira [ingressar manualmente](reference/manual-join.md). |
| Tudo | <strong>Ingressar:</strong> Você vê uma mensagem dizendo "**o proprietário do espaço de trabalho parece estar offline**" ao ingressar por meio do navegador. | Possíveis soluções alternativas:<br /><ul><li>Tente [ingressar manualmente](reference/manual-join.md). Vimos problemas com junções entre regiões (por exemplo, leste e oeste dos EUA) devido a problemas de serviço que não afetam junções manuais.</li><li>Live Share pode não conseguir rotear diretamente para o host ao ser executado no modo de conexão "auto". Experimente o [modo de retransmissão](reference/connectivity.md).</li></ul>Consulte [solução de problemas de conectividade](#connectivity) para obter mais possibilidades |
| Código VS | <strong>Ingressar:</strong> Você ingressou por meio do navegador <strong>antes de entrar</strong>, não foi solicitado a entrar </strong> e a junção nunca foi concluída. |  Esse é um [bug conhecido](https://github.com/MicrosoftDocs/live-share/issues/167). Clique no item da barra de status de entrada para entrar e depois ingressar novamente. |

## <a name="connectivity"></a>Conectividade

As informações abaixo podem ajudá-lo a solucionar problemas se você estiver tendo problemas relacionados à conectividade ou tempos limite ao entrar, compartilhar ou ingressar.

Conforme descrito nos [requisitos de conectividade para Live share](reference/connectivity.md) artigo, diferentes modos de conexão têm diferentes requisitos para funcionar, portanto, há alguns problemas potenciais diferentes em andamento.

| Ferramenta | Problema | Causas prováveis |
|------|------|----------------|
| Tudo | Você está usando um <strong>proxy</strong> e está vendo vários problemas de conectividade | As configurações de proxy podem ser complicadas.  Tente definir as variáveis de ambiente **http_proxy** e **HTTPS_PROXY** **globalmente** e reinicie a ferramenta. Consulte [configurações de proxy](reference/connectivity.md#proxies) para obter mais detalhes. Provavelmente, há algumas configurações às quais ainda não damos suporte. portanto, [informe-nos](https://github.com/MicrosoftDocs/live-share/issues/86) se isso não funciona para você. |
| Código VS | Depois de instalar a extensão e iniciar VS Code pela primeira vez, você receberá um <strong>erro quando "Concluindo a instalação" aparecer na barra de status</strong>. |  Você não pode acessar a Internet ou o acesso a download.visualstudio.microsoft.com e/ou download.microsoft.com na porta 443 está bloqueado por seu firewall pessoal ou corporativo. Consulte [aqui](https://github.com/MicrosoftDocs/live-share/issues/58) para obter informações sobre por que Live share precisa baixar algo neste ponto. |
| Tudo | <strong>Não é possível entrar no Visual Studio Live share</strong> | Você não pode acessar a Internet ou o acesso a *. liveshare.vsengsaas.visualstudio.com na porta 80/443 está bloqueado por seu firewall pessoal ou corporativo. Insira https://insiders.liveshare.vsengsaas.visualstudio.com em um navegador e verifique se você Lande o home page Visual Studio Live share. |
| Tudo | Você está no <strong>modo auto</strong> (o padrão), é capaz de entrar, mas veja um <strong>erro de tempo limite ou de conexão</strong> ao compartilhar ou ingressar. | Tanto os modos diretos quanto de retransmissão estão falhando ao se conectar ou há um bug com o modo auto. Se você conseguir se conectar depois [de alternar para o modo direto ou de retransmissão](reference/connectivity.md#changing-the-connection-mode), [gere um bug](https://aka.ms/vsls-problem). |
| Tudo | Você está no <strong>modo direto</strong>, é capaz de entrar, mas veja um <strong>erro de tempo limite ou de conexão</strong> ao compartilhar ou ingressar. | O convidado e o host não podem se conectar diretamente. Experimente o [modo automático ou de retransmissão](reference/connectivity.md#changing-the-connection-mode) para ver se o problema desaparece. Talvez seja necessário [permitir manualmente Live share por meio de seu firewall pessoal](reference/connectivity.md#manually-adding-a-firewall-entry) ou simplesmente usar o modo de retransmissão. |
| Tudo | Você está no <strong>modo de retransmissão</strong>, é capaz de entrar, mas é notificado de um <strong>erro de tempo limite ou de conexão</strong> ao compartilhar ou ingressar. | O acesso a *. servicebus.windows.net na porta 80/443 está bloqueado é bloqueado por seu firewall pessoal ou corporativo. Experimente o [modo direto](reference/connectivity.md#changing-the-connection-mode). |

Consulte o artigo [requisitos de conectividade para Live share](reference/connectivity.md) para obter mais informações sobre os requisitos de conectividade.

## <a name="see-also"></a>Confira também

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
