---
title: Compartilhar o guia de início rápido - Visual Studio Live Share | Microsoft Docs
description: Uma explicação resumida sobre compartilhando seu primeiro projeto usando uma sessão de colaboração do Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 3596b25dc0d08962d7813f52549dbe6fef4f00a0
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255198"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>Início Rápido: Compartilhar seu primeiro projeto

> **Observação: Atualmente, o Visual Studio Live Share está em versão prévia. A experiência do usuário e as funcionalidades não são definitivas.**

Bem-vindo ao Visual Studio Live Share! O Live Share permite que você edite e depure de forma colaborativa com outras pessoas em tempo real, sejam quais forem as linguagens de programação usadas ou os tipos de aplicativo criados. Ele permite que você compartilhe seu projeto atual de forma instantânea e segura e, em seguida, conforme necessário, compartilhe sessões de depuração, instâncias de terminal, aplicativos Web do localhost, chamadas de voz e muito mais!

Pronto para começar?  Colaboração em equipe deve ser rápido e natural, que se torna mais difícil para não fazê-lo! Por esse motivo, o Visual Studio Live Share torna simples para começar a usar, para que você possa começar perfeitamente a compartilhar seu trabalho e ideias.

> [!TIP]
> Você sabia que pode *ingressar em sua própria sessão de colaboração*? Isso permite que você experimente o Live Share por conta própria ou crie uma instância do Visual Studio ou do VS Code e conecte-a remotamente. Você pode até usar a mesma identidade em ambas as instâncias. Confira!

Basta seguir estas etapas para iniciar o compartilhamento.

## <a name="1-install-the-extension"></a>1. Instalar a extensão

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
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide.svg" width="128px" alt="Visual Studio logo" /></td>
    <td style="border:none;">
        <strong>Visual Studio 2017 15.6 ou posterior</strong><br />
        1. Instale a última versão do <a href="https://visualstudio.microsoft.com/vs/">Visual Studio 2017</a> (15.6 ou posterior) no Windows (7, 8.1 ou 10).<br/>
        2. Instale uma <a href="../reference/platform-support.md">carga de trabalho compatível</a>. (por exemplo, ASP.NET, .NET Core, C++ e/ou Node.js)<br />
        3. Baixe e instale a extensão do Visual Studio Live Share por meio do marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button"></a><br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-preview.svg" width="128px" alt="Visual Studio Preview logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. Instale a última versão prévia do <a href="https://aka.ms/vs-preview">Visual Studio 2019</a>.<br/>
        2. Instale uma <a href="../reference/platform-support.md">carga de trabalho compatível</a>. (por exemplo, ASP.NET, .NET Core, C++ e/ou Node.js)<br />
        3. O Visual Studio Live Share é instalado por padrão com essas cargas de trabalho. <br />
    </td>
</tr>
</table>

Ao baixar e usar o Visual Studio Live Share, você concorda com os [termos de licença](https://aka.ms/vsls-license) e a [política de privacidade](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Confira [Solução de problemas](../troubleshooting.md) caso tenha problemas.

## <a name="2-sign-in"></a>2. Entrar

Depois de instalar a extensão de compartilhamento ao vivo, reiniciar e aguardando as dependências concluir a instalação (VS Code), você desejará entrar para permitir que outros participantes Saiba quem é você. Basta clicar o item de barra de status (VS Code) "Live Share" / "Entrar" botão (VS) para começar a usar.

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

Na **VS Code**, seu navegador será iniciado enquanto uma notificação será exibida a inicialização, solicitando que você entrar. Concluir o processo em seu navegador de entrada e, em seguida, simplesmente fechar o navegador quando terminar.

![Notificação do sistema pedindo para entrar usando um navegador da web](../media/vscode-sign-in-toast.png)

> **Usuários do Linux:** Você será solicitado a inserir um código de usuário, se você estiver usando uma versão mais antiga do Live Share (v0.3.295 ou abaixo). Atualizar para a versão mais recente da extensão ou clique no "tendo problemas?" Vincular depois de entrar para ver o código. Ver [aqui para obter detalhes](../use/vscode.md#sign-in-using-a-user-code).

Na **Visual Studio**, Live Share usa automaticamente seu [conta de personalização](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Como resultado, você pode simplesmente entrar como você faria normalmente. No entanto, se você preferir usar um logon-in diferente de sua conta de personalização do Visual Studio, acesse **ferramentas &gt; opções &gt; Live Share &gt; conta de usuário** e selecione credenciais diferentes.

Ver [solução de problemas](../troubleshooting.md#sign-in) se você ainda estiver tendo problemas.

## <a name="3-open-a-folder-project-or-solution"></a>3. Abra uma pasta, projeto ou solução

Use o fluxo de trabalho normal para abrir uma pasta, projeto ou solução que você gostaria de compartilhar no Visual Studio ou Visual Studio Code.

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [atualização opcional] oculto ou arquivos excluídos

Por padrão, o Live Share **oculta** quaisquer arquivos/pastas referenciadas nos arquivos. gitignore em suas pastas compartilhadas de convidados. **Ocultando** um arquivo impede que ele apareça na árvore de arquivos do convidado. **Excluindo** um arquivo se aplica a uma regra mais rígida que impede que o Live Share abri-lo para o convidado em situações como ir para definição ou se você segue o arquivo durante a depuração ou sendo "seguido". Se você quiser ocultar/excluir arquivos diferentes, uma **. vsls.json** arquivo pode ser adicionado ao seu projeto com essas configurações. Ver [controlando o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para obter detalhes.

## <a name="5-start-a-collaboration-session"></a>5. Iniciar uma sessão de colaboração

Em seguida, basta clicar em "Live Share" dentro de sua ferramenta e um link de convite é copiado automaticamente na área de transferência.

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
> Você poderá ser solicitado por seu software de firewall da área de trabalho para permitir que o agente Live Share abrir uma porta na primeira vez que você compartilha. Aceitar isso é totalmente opcional, mas permite que um seguro "modo direto" para melhorar o desempenho quando a pessoa que você está trabalhando com está na mesma rede que você esteja. Ver [alterar o modo de conexão](../reference/connectivity.md#changing-the-connection-mode) para obter detalhes.

## <a name="6-optional-enable-read-only-mode"></a>6. [opcional] habilitar o modo de somente leitura

Depois de iniciar sua sessão de colaboração, você pode definir a sessão a ser somente leitura para impedir que os convidados façam edições no código que está sendo compartilhado.

Após o compartilhamento, você receberá uma notificação de que o link de convite foi copiado para a área de transferência. Em seguida, você pode selecionar a opção de fazer a sessão somente leitura.

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

Na **VS Code**, você também pode iniciar uma sessão somente leitura a partir da guia de viewlet Live Share.

![Notificação do sistema pedindo para entrar usando um navegador da web](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7. Enviar a alguém o link de convite

Enviar link por email, Slack, Skype, etc., para aqueles que deseja convidar. Abrindo o link em um navegador permite que eles ingressar na sessão de colaboração que está compartilhando o conteúdo da pasta, projeto ou solução que você abriu. Observe que, considerando o nível de acesso Live Share sessões podem fornecer aos convidados, **você só deve compartilhar com pessoas confiáveis** e considere as implicações do que você está compartilhando.

> **Dica de segurança:** Deseja entender as implicações de segurança de alguns dos recursos do Live Share? Confira a [segurança](../reference/security.md) artigo.

Se o convidado é convidado tiver perguntas, o [guia de início rápido: Junte-se a primeira sessão](join.md) artigo fornece algumas informações sobre colocar em execução como convidado.

## <a name="8-optional-approve-the-guest"></a>8. [opcional] aprovar o convidado

Por padrão, os convidados automaticamente ingressarem em sua sessão de colaboração e você será notificado quando eles estiverem prontos para trabalhar com você.

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

Você pode optar por exigir uma "aprovação" explícita para ingressar em vez disso, qualquer pessoa que. Se você tiver essa configuração ativada, uma notificação solicita que você aprovar o convidado quando tentarem ingressar em sua sessão.

Ver [exigir aprovação do convidado](../reference/security.md#requiring-guest-approval) para obter detalhes sobre como ativar esse recurso.

## <a name="9-collaborate"></a>9. Colabore!

É só isso! Aqui estão algumas coisas para experimentar depois que um convidado ingressou:

1. Mova para diferentes arquivos no projeto independentemente e fazer algumas modificações
1. Siga o convidado e observe como Role, fazer edições e navegar para diferentes arquivos
1. Iniciar uma sessão de depuração junto com eles
1. Compartilhar um servidor para que você pode fazer check-out de algo como um aplicativo web em execução no seu computador
1. Compartilhar um terminal e execute alguns comandos

Confira a [Visual Studio Code](../use/vscode.md) e [Visual Studio](../use/vs.md) docs de extensão para obter informações sobre como realizar essas ações e muito mais.

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).

## <a name="next-steps"></a>Próximas etapas

Confira estes artigos adicionais para obter mais informações.

- [Início Rápido: Junte-se a primeira sessão de colaboração](join.md)
- [Como: Colaborar usando o Visual Studio Code](../use/vscode.md)
- [Como: Colaborar usando o Visual Studio](../use/vs.md)

Referência

- [Requisitos de conectividade do Live Share](../reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](../reference/security.md)
- [Suporte de idioma e plataforma](../reference/platform-support.md)
- [Suporte de extensão](../reference/extensions.md)
