---
title: Ingressar em início rápido – Visual Studio Live Share | Microsoft Docs
description: Uma explicação resumida a estiver ingressando em sua primeira sessão de colaboração do Visual Studio Live Share.
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
ms.openlocfilehash: d4280484aaa3fd4ac204588bf4aefc4e3ac51871
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255253"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>Início Rápido: Junte-se a primeira sessão de colaboração

> **Observação: Atualmente, o Visual Studio Live Share está em versão prévia. A experiência do usuário e as funcionalidades não são definitivas.**

Bem-vindo ao Visual Studio Live Share! O Live Share permite que você edite e depure de forma colaborativa com outras pessoas em tempo real, sejam quais forem as linguagens de programação usadas ou os tipos de aplicativo criados. Ele permite que você instantaneamente e segura ingressar projeto atual de um colega de equipe, o e, em seguida, conforme necessário, insira na depuração de sessões, exibir e editar instâncias de terminal, consulte aplicativos de web do localhost, chamadas de voz de junção e muito mais!

Pronto para começar? Colaboração em equipe deve ser rápido e natural, que se torna mais difícil para não fazê-lo! Por esse motivo, o Visual Studio Live Share torna simples para começar a usar, para que você possa começar perfeitamente a compartilhar seu trabalho e ideias.

> [!TIP]
> Você sabia que pode *ingressar em sua própria sessão de colaboração*? Isso permite que você experimente o Live Share por conta própria ou crie uma instância do Visual Studio ou do VS Code e conecte-a remotamente. Você pode até mesmo usar a mesma identidade em ambas as instâncias. Confira!

Basta seguir estas etapas para ingressar em uma sessão de colaboração.

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
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
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

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [junção de opcional] como um convidado somente-leitura no VS Code

No VS Code, depois de instalar a extensão de compartilhamento ao vivo, reiniciar e aguardando as dependências para concluir a instalação, você pode entrar e ingressar em uma sessão de colaboração como um convidado de somente leitura.

> [!NOTE]
> Se você quiser fazer edições no código que você está ingressando, você precisará [entrar](../quickstart/join.md#3-Sign-in).

Abra (ou abre novamente) no link de convite em um navegador, e você receberá uma notificação de que deseja que o navegador iniciar o VS Code. Permita que ele inicie e começará a se conectar à sessão de colaboração.

Quando inicia o VS Code, você obterá uma notificação pedindo para entrar. Selecione "Continuar como convidado somente leitura" para ingressar na sessão.

![Junte-se como sessão como uma notificação do sistema do convidado de somente leitura](../media/vscode-read-only-guest.png)

Você será solicitado a inserir um nome de exibição para ajudar a identificá-lo na sessão de participantes.

![Nome do convidado de somente leitura](../media/vscode-read-only-guest-name.png)

Depois disso, você vai ser Unido para a sessão como somente leitura. Você poderá exibir e navegar em torno do código, depuração de colegas e servidores de modo compartilhado e terminais (somente leitura).

> [!NOTE]
> Se você quiser mais tarde, obtenha acesso de leitura/gravação para o código, você pode entrar. Clique em seu nome de exibição no status, barra e selecione a opção "entrar".
![Entrada convidado somente-leitura](../media/vscode-read-only-guest-signin.png) isso iniciará o navegador e você pode escolher uma conta da Microsoft ou GitHub para entrar.

## <a name="3-sign-in"></a>3. Entrar

Depois de instalar a extensão de compartilhamento ao vivo, reiniciar e aguardando as dependências concluir a instalação (VS Code), você desejará entrar para permitir que outros participantes Saiba quem é você. Se você ignorar essa etapa, você será solicitado a entrar durante o processo de junção ou poderão ingressar na sessão como um convidado de somente leitura. Clique no item de barra de status (VS Code) "compartilhamento" / "entrar" botão (VS) para começar a usar.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item" />
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

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. Abrir/re-open o convite do link em um navegador

Agora, basta abrir (ou abrir novamente) no link de convite em um navegador.

> **Observação**: Se você ainda não tiver instalado a extensão de compartilhamento ao vivo, você verá com links para o marketplace de extensão. Instalar a extensão e reinicie sua ferramenta e tente novamente.

Você deve ser notificado que o navegador deseja iniciar uma ferramenta de Live Share habilitado. Se você permitir que ele inicie a ferramenta selecionada, você estará conectado à sessão de colaboração, depois que ele for iniciado.

![Página de junção](../media/join-page.png)

Se o host estiver offline, você será notificado no momento em vez disso. Você pode, em seguida, entre em contato com o host e peça-lhe para compartilhar novamente.

> **Dica de solução de problemas:** Ao usar o VS Code, certifique-se de que você já **iniciado a ferramenta de pelo menos uma vez** depois de instalar a extensão e aguardaram para as dependências concluir a instalação (consulte a barra de status) antes de abertura/re-opening a página de convite. Ainda está com problemas? Ver [unir manualmente](../reference/manual-join.md) para obter detalhes.

## <a name="5-collaborate"></a>5. Colabore!

É só isso! Em alguns instantes, você estará conectado à sessão de colaboração de seu colega. Por padrão, o host automático-aceita as pessoas que unem, mas se o host estiver configurado para [exigir aprovação do convidado](../reference/security.md#requiring-guest-approval) você irá ver a barra de status / unir menção de caixa de diálogo que Live Share está aguardando o host para aprovar sua solicitação para ingressar.

> **Dica de segurança:** Como um convidado a ingressar em uma sessão de colaboração, é importante entender que os hosts podem restringir o acesso a determinados arquivos ou recursos. Deseja entender as implicações de segurança de alguns dos recursos e configurações de compartilhamento ao vivo? Confira a [segurança](../reference/security.md) artigo.

Aqui estão algumas coisas para experimentar:

1. Mover-se o projeto de forma independente e fazer algumas modificações
2. Check-out de trabalho intellisense para JavaScript, TypeScript, e/ou C# código
3. Editar algo junto com o host
4. Siga o host e mover-se com eles como navegar e fazer edições em arquivos diferentes
5. Iniciar uma sessão de depuração junto com o host
6. Solicitar que o host para compartilhar um servidor, para que você pode fazer check-out de algo como um aplicativo web em execução no seu computador
7. Solicitar que o host para compartilhar um terminal e executar alguns comandos

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).

## <a name="next-steps"></a>Próximas etapas

Confira estes artigos adicionais para obter mais informações.

- [Início Rápido: Compartilhar seu primeiro projeto](share.md)
- [Como: Colaborar usando o Visual Studio Code](../use/vscode.md)
- [Como: Colaborar usando o Visual Studio](../use/vs.md)

Referência

- [Requisitos de conectividade do Live Share](../reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](../reference/security.md)
- [Suporte de idioma e plataforma](../reference/platform-support.md)
- [Suporte de extensão](../reference/extensions.md)
