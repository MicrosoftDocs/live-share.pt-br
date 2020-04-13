---
title: Início Rápido sobre como ingressar – Visual Studio Live Share | Microsoft Docs
description: Um passo a passo resumido sobre como ingressar na sua primeira sessão de colaboração do Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 7b8b3d9b566231f4b4205b559232ef1752fd9441
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "79508566"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->


# <a name="quickstart-join-your-first-collaboration-session"></a>Quickstart: Participe da sua primeira sessão de colaboração

Bem-vindo ao Visual Studio Live Share! O Live Share permite que você edite e depure de forma colaborativa com outras pessoas em tempo real, sejam quais forem as linguagens de programação usadas ou os tipos de aplicativo criados. Ele permite que você ingresse em um projeto atual de um colega de equipe de forma instantânea e segura e, em seguida, conforme necessário, entre em sessões de depuração, exiba e edite instâncias de terminal, veja aplicativos Web do localhost, participe de chamadas de voz e muito mais.

Pronto para começar? A colaboração em equipe será tão rápida e natural que será difícil não participar. Por esse motivo, o Visual Studio Live Share simplifica o início, para que você possa começar a compartilhar seu trabalho e suas ideias facilmente.

> [!TIP]
> Você sabia que pode *ingressar em sua própria sessão de colaboração*? Isso permite que você experimente o Live Share por conta própria ou crie uma instância do Visual Studio ou do VS Code e conecte-a remotamente. Você pode até mesmo usar a mesma identidade em ambas as instâncias. Confira!

Basta seguir estas etapas para ingressar em uma sessão de colaboração.

## <a name="1-install-the-extension"></a>1. Instale a extensão

É fácil instalar a extensão. Basta seguir estas etapas:

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0 ou posterior)</strong><br />
        1. Instale o <a href="https://code.visualstudio.com/">Visual Studio Code</a> para Windows (7, 8.1 ou 10), macOS <b>(Serra ou posterior)</b> e Linux de 64 bits <b>(<a href="../use/vscode.md#installation">detalhes</a>)</b><br />
        2. Baixe e instale a extensão do Visual Studio Live Share por meio do marketplace. <br />
        3. Recarregue-a e aguarde até as dependências serem baixadas e instaladas (veja a barra de status).<br />
        4. <strong>Linux</strong>: Se solicitado a <a href="../reference/linux.md#install-linux-prerequisites">instalar bibliotecas,</a>clique em instalar, digite senha, reinicie o código VS quando estiver pronto.<br />
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019</strong><br />
        1.Instale <a href="https://visualstudio.microsoft.com/downloads/">o Visual Studio 2019</a>.<br/>
        2. Instale uma <a href="../reference/platform-support.md">carga de trabalho compatível</a>. (por exemplo, ASP.NET, .NET Core, C++, Python e/ou Node.js)<br />
        3. O Visual Studio Live Share é instalado por padrão com essas cargas de trabalho. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 ou posterior</strong><br />
        1. Instale a última versão do <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6 ou posterior) no Windows (7, 8.1 ou 10).<br/>
        2. Instale uma <a href="../reference/platform-support.md">carga de trabalho compatível</a>. (por exemplo, ASP.NET, .NET Core, C++ e/ou Node.js)<br />
        3. Baixe e instale a extensão do Visual Studio Live Share por meio do marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Ao baixar e usar o Visual Studio Live Share, você concorda com os [termos de licença](https://aka.ms/vsls-license) e a [política de privacidade](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Confira [Solução de problemas](../troubleshooting.md) caso tenha problemas.

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [Opcional] Ingresse como um convidado somente leitura no VS Code

No VS Code, após instalar a extensão do Live Share, reiniciar e aguardar as dependências finalizarem a instalação, é possível ingressar em uma sessão de colaboração como convidado somente leitura.

> [!NOTE]
> Se quiser editar o código em que está ingressando, será preciso entrar.

Abra (ou reabra) o link de convite em um navegador para receber uma notificação de que o navegador quer iniciar o VS Code. Permita a inicialização e o navegador começará a se conectar com a sessão de colaboração.

Quando o VS Code for inicializado, você receberá uma notificação do sistema solicitando a entrada. Selecione "Continuar como convidado somente leitura" para ingressar na sessão.

![Notificação do sistema "Ingressar na sessão como convidado somente leitura"](../media/vscode-read-only-guest.png)

Você será solicitado a inserir um nome de exibição para ajudar os participantes a identificá-lo na sessão.

![Nome do convidado somente leitura](../media/vscode-read-only-guest-name.png)

Depois disso, você será ingressado na sessão como somente leitura. Você poderá ver e navegar pelo código, fazer codepuração e exibir os servidores compartilhados e terminais (somente leitura).

> [!NOTE]
> Se você quiser ter acesso de leitura/gravação ao código posteriormente, faça logon. Clique no seu nome de exibição na barra de status e selecione a opção "Entrar".
![Entrada de convidado somente leitura](../media/vscode-read-only-guest-signin.png) Isso iniciará o navegador e você poderá escolher uma conta Microsoft ou GitHub para entrar.

## <a name="3-sign-in"></a>3. Faça login

Após instalar a extensão do Live Share, reiniciar e aguardar as dependências terminarem a instalação (VS Code), entre para que os outros participantes conheçam você. Se você ignorar essa etapa, será solicitado a entrar durante o processo de ingresso ou poderá ingressar na sessão como convidado somente leitura. Clique no item da barra de status "Live Share" (VS Code) ou no botão "Entrar" (VS) para começar.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button-new.png" width="100%" alt="Visual Studio Code sign in status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

No **VS Code**, seu navegador será iniciado e uma notificação será exibida, solicitando que você entre. Conclua o processo de entrada no navegador e, em seguida, feche-o quando terminar.

![Notificação do sistema solicitando a entrada com um navegador da Web](../media/vscode-sign-in-toast.png)

> **Usuários de Linux:** Você pode ser solicitado a inserir um código de usuário se estiver usando uma versão mais antiga do Live Share (v0.3.295 ou abaixo). Atualize para a versão mais recente da extensão ou clique no link "Está com problemas?" depois de entrar para ver o código. Veja [aqui para mais detalhes](../use/vscode.md#sign-in-using-a-user-code).

No **Visual Studio**, o Live Share usa automaticamente sua [conta de personalização](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Como resultado, você pode simplesmente entrar como você faria normalmente. No entanto, se você preferir usar um logon diferente da sua conta de personalização do Visual Studio, acesse **Ferramentas &gt; Opções &gt; Live Share &gt; Conta de usuário** e selecione credenciais diferentes.

Confira [Solução de problemas](../troubleshooting.md#sign-in) se ainda tiver problemas.

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. Abra/reabra o link de convite em um navegador

Agora, basta abrir (ou reabrir) o link de convite em um navegador.

> **Nota**: Se você ainda não instalou a extensão Live Share, você será apresentado com links para o mercado de extensão. Instale a extensão, reinicie a ferramenta e tente novamente.

Você receberá uma notificação de que o navegador quer iniciar uma ferramenta habilitada para o Live Share. Ao permitir a inicialização da ferramenta selecionada, você será conectado à sessão de colaboração quando ela começar.

![Página Ingressar](../media/join-page.png)

Se o host estiver offline, você receberá uma notificação. Você pode entrar em contato com o host e solicitar o compartilhamento novamente.

> **Solução de problemas Dica:** Ao usar o CÓDIGO VS, certifique-se de que **você iniciou a ferramenta pelo menos uma vez** depois de instalar a extensão e esperou que as dependências terminassem a instalação (veja a barra de status) antes de abrir/reabrir a página de convite. Ainda está com problemas? Confira [Ingressar manualmente](../reference/manual-join.md) para saber mais detalhes.

## <a name="5-collaborate"></a>5. Colabore!

É isso! Em alguns instantes, você será conectado à sessão de colaboração do seu colega. Por padrão, o host aceita automaticamente as pessoas que ingressam. No entanto, se o host estiver configurado para [exigir aprovação do convidado](../reference/security.md#requiring-guest-approval), você verá a barra de status/menção da caixa de diálogo de ingresso de que o Live Share está aguardando o host aprovar sua solicitação de ingresso.

> **Dica de segurança:** Como convidado participando de uma sessão de colaboração, é importante entender que os hosts podem restringir seu acesso a determinados arquivos ou recursos. Quer entender as implicações de segurança de alguns recursos e configurações do Live Share? Confira o artigo sobre [segurança](../reference/security.md).

Algumas coisas para experimentar:

1. Navegue pelo projeto de maneira independente e faça algumas edições
2. Confira como trabalhar com o IntelliSense para JavaScript, TypeScript e/ou código C#
3. Edite algo junto com o host
4. Siga o host e navegue com ele conforme ele navega e faz edições em arquivos diferentes
5. Inicie uma sessão de codepuração com o host
6. Solicite ao host que compartilhe um servidor para você conferir algo como um aplicativo Web em execução no computador
7. Solicite ao host que compartilhe um terminal e execute alguns comandos

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).

## <a name="next-steps"></a>Próximas etapas

Confira estes outros artigos para saber mais.

- [Quickstart: Compartilhe seu primeiro projeto](share.md)
- [Como fazer: Colabore usando o Visual Studio Code](../use/vscode.md)
- [Como fazer: Colabore usando o Visual Studio](../use/vs.md)

Referência

- [Requisitos de conectividade do Live Share](../reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](../reference/security.md)
- [Suporte de idioma e plataforma](../reference/platform-support.md)
- [Suporte de extensão](../reference/extensions.md)
