---
title: Início Rápido sobre como compartilhar – Visual Studio Live Share | Microsoft Docs
description: Um passo a passo resumido sobre como compartilhar seu primeiro projeto usando uma sessão de colaboração do Visual Studio Live Share.
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
ms.openlocfilehash: 339fb176eed78ece2117ba645a84fafe4f4247f4
ms.sourcegitcommit: cab8df5c29f9d91e702ef514def53944ee7701ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/01/2019
ms.locfileid: "64987209"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>Início Rápido: Compartilhar seu primeiro projeto

Bem-vindo ao Visual Studio Live Share! O Live Share permite que você edite e depure de forma colaborativa com outras pessoas em tempo real, sejam quais forem as linguagens de programação usadas ou os tipos de aplicativo criados. Ele permite que você compartilhe seu projeto atual de forma instantânea e segura e, em seguida, conforme necessário, compartilhe sessões de depuração, instâncias de terminal, aplicativos Web do localhost, chamadas de voz e muito mais!

Pronto para começar?  A colaboração em equipe será tão rápida e natural que será difícil não participar. Por esse motivo, o Visual Studio Live Share simplifica o início, para que você possa começar a compartilhar seu trabalho e suas ideias facilmente.

> [!TIP]
> Você sabia que pode *ingressar em sua própria sessão de colaboração*? Isso permite que você experimente o Live Share por conta própria ou crie uma instância do Visual Studio ou do VS Code e conecte-a remotamente. Você pode até mesmo usar a mesma identidade em ambas as instâncias. Confira!

Basta seguir estas etapas para iniciar o compartilhamento.

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
        4. <strong>Linux</strong>: Se precisar <a href="../reference/linux.md#install-linux-prerequisites">instalar bibliotecas</a>, clique em Instalar, insira a senha e reinicie o VS Code quando terminar.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="../media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. Instale o <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
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

## <a name="2-sign-in"></a>2. Entrar

Após instalar a extensão do Live Share, reiniciar e aguardar as dependências terminarem a instalação (VS Code), entre para que os outros participantes conheçam você. Clique no item da barra de status "Live Share" (VS Code)/no botão "Entrar" (VS) para começar.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

No **VS Code**, seu navegador será iniciado e uma notificação será exibida, solicitando que você entre. Conclua o processo de entrada no navegador e, em seguida, feche-o quando terminar.

![Notificação do sistema solicitando a entrada com um navegador da Web](../media/vscode-sign-in-toast.png)

> **Usuários do Linux:** talvez você seja solicitado a inserir um código do usuário se estiver usando uma versão mais antiga do Live Share (v0.3.295 ou anteriores). Atualize para a versão mais recente da extensão ou clique no link "Está com problemas?" depois de entrar para ver o código. Confira [aqui para mais detalhes](../use/vscode.md#sign-in-using-a-user-code).

No **Visual Studio**, o Live Share usa automaticamente sua [conta de personalização](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Como resultado, você pode simplesmente entrar como você faria normalmente. No entanto, se você preferir usar um logon diferente da sua conta de personalização do Visual Studio, acesse **Ferramentas &gt; Opções &gt; Live Share &gt; Conta de usuário** e selecione credenciais diferentes.

Confira [Solução de problemas](../troubleshooting.md#sign-in) se ainda tiver problemas.

## <a name="3-open-a-folder-project-or-solution"></a>3. Abra uma pasta, um projeto ou uma solução

Use o fluxo de trabalho normal para abrir uma pasta, um projeto ou uma solução que você queira compartilhar no Visual Studio ou no Visual Studio Code.

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [Opcional] Atualize os arquivos ocultos ou excluídos

Por padrão, o Live Share **oculta** quaisquer arquivos/pastas referenciados nos arquivos .gitignore em suas pastas compartilhadas de convidados. **Ocultar** um arquivo impede que ele apareça na árvore de arquivos do convidado. **Excluir** um arquivo aplica uma regra mais rigorosa que impede o Live Share de abri-lo para o convidado em situações como "Ir para Definição" ou se você intervir no arquivo durante a depuração ou ao ser "seguido". Se você quiser ocultar/excluir arquivos diferentes, um arquivo **.vsls.json** poderá ser adicionado ao seu projeto com essas configurações. Confira [Controlar o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para saber mais detalhes.

## <a name="5-start-a-collaboration-session"></a>5. Inicie uma sessão de colaboração

Em seguida, basta clicar em "Live Share" na ferramenta e um link de convite será copiado automaticamente para sua área de transferência.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> Talvez o software de firewall do computador exija que o agente do Live Share tenha permissão para abrir uma porta no primeiro compartilhamento. Aceitar isso é totalmente opcional, mas habilita um "modo direto" seguro para melhorar o desempenho quando a pessoa com que você está trabalhando estiver na mesma rede que você. Confira [Alterar o modo de conexão](../reference/connectivity.md#changing-the-connection-mode) para saber mais detalhes.

## <a name="6-optional-enable-read-only-mode"></a>6. [Opcional] Habilite o modo somente leitura

Após iniciar a sessão de colaboração, configure a sessão como somente leitura para impedir que os convidados façam edições no código compartilhado.

Após o compartilhamento, você receberá uma notificação de que o link de convite foi copiado para a área de transferência. Em seguida, você poderá selecionar a opção para definir a sessão como somente leitura.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-read-only-toast.png" width="100%" alt="Visual Studio Code read-only option" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-read-only-notification.png" width="100%" alt="Visual Studio read-only option"/>
    </td>
</tr>
</table>

No **VS Code**, você também pode iniciar uma sessão somente leitura na guia de viewlet do Live Share.

![Notificação do sistema solicitando a entrada com um navegador da Web](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7. Envie o link de convite para alguém

Envie o link por email, pelo Slack, pelo Skype etc. para as pessoas que você quer convidar. Abrir o link em um navegador permite que elas ingressem na sessão de colaboração que está compartilhando o conteúdo da pasta, do projeto ou da solução que você abriu. Observe que, considerando o nível de acesso que as sessões do Live Share podem conceder aos convidados, **você só deve compartilhar com pessoas em que confia** e considerar as implicações do que você está compartilhando.

> **Dica de segurança:** quer entender as implicações de segurança de alguns recursos do Live Share? Confira o artigo sobre [segurança](../reference/security.md).

Se o convidado tiver dúvidas, o artigo [Início Rápido: Ingressar na primeira sessão](join.md) oferece algumas informações sobre como começar a trabalhar como convidado.

## <a name="8-optional-approve-the-guest"></a>8. [Opcional] Aprove o convidado

Por padrão, os convidados ingressam automaticamente na sessão de colaboração e você recebe uma notificação quando eles estiverem prontos para trabalhar com você.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

Em vez disso, você pode optar por exigir uma "aprovação" explícita para todos que solicitarem ingresso. Se essa configuração estiver ativada, uma notificação solicitará que você aprove o convidado quando este tentar ingressar em sua sessão.

Confira [Exigir aprovação do convidado](../reference/security.md#requiring-guest-approval) para saber mais detalhes sobre como ativar esse recurso.

## <a name="9-collaborate"></a>9. Colabore!

É só isso! Algumas coisas para experimentar quando um convidado ingressar:

1. Navegue pelos diferentes arquivos do projeto de maneira independente e faça algumas edições
1. Siga o convidado e observe como ele navega, faz edições e acessa diferentes arquivos
1. Inicie uma sessão de codepuração com o convidado
1. Compartilhe um servidor para conferir algo como um aplicativo Web em execução no computador
1. Compartilhe um terminal e execute alguns comandos

Confira a documentação de extensão do [Visual Studio Code](../use/vscode.md) e do [Visual Studio](../use/vs.md) para saber como realizar essas ações e muito mais.

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).

## <a name="next-steps"></a>Próximas etapas

Confira estes outros artigos para saber mais.

- [Início Rápido: Ingressar na sua primeira sessão de colaboração](join.md)
- [Como colaborar usando o Visual Studio Code](../use/vscode.md)
- [Como colaborar usando o Visual Studio](../use/vs.md)

Referência

- [Requisitos de conectividade do Live Share](../reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](../reference/security.md)
- [Suporte de idioma e plataforma](../reference/platform-support.md)
- [Suporte de extensão](../reference/extensions.md)
