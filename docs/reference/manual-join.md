---
title: Junção manual-Visual Studio Live Share | Microsoft Docs
description: Informações sobre como unir uma sessão de colaboração manualmente no compartilhamento ao vivo do Visual Studio.
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
ms.openlocfilehash: 0d46cb53a28bfac1c088371ff5eecdb6af0c8420
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019786"
---
# <a name="join-a-session-manually"></a>Ingressar uma sessão manualmente

Além de abrir um link em um navegador para ingressar em uma sessão de colaboração, você pode ingressar manualmente colando o link em uma ferramenta já em execução. Isso pode ser útil se você quiser usar uma ferramenta diferente da que normalmente faz ou se estiver tendo problemas para que os links de convite funcionem por algum motivo.

As instruções exatas variam entre o [Visual Studio](#join-from-visual-studio) e o [Visual Studio Code](#join-from-visual-studio-code), portanto, escolha a ferramenta que você pretende usar para obter mais informações.

## <a name="join-from-visual-studio-code"></a>Ingressar de Visual Studio Code

### <a name="1-sign-in"></a>1. entrar

>**Observação:** Se você quiser ingressar em uma sessão de colaboração como um guesasdsat somente leitura, poderá ignorar a entrada. Você terá acesso para exibir e navegar pelo código compartilhado, mas não poderá fazer edições.

![Notificação do sistema solicitando a entrada com um navegador da Web](../media/vscode-sign-in-toast.png)

Para colaborar, é preciso entrar no Visual Studio Live Share para que todos saibam quem é você. **Clique** no item da barra de status "Live share" ou pressione **Ctrl + Shift + p/Cmd + Shift + p** e selecione o comando "Live share: entrar com o navegador".

![Botão Entrar do VS Code](../media/vscode-sign-in-button.png)

Seu navegador será iniciado enquanto uma notificação será exibida, solicitando que você entre. Conclua o processo de entrada no navegador e, em seguida, feche-o quando terminar.

Se você estiver tendo problemas com VS Code não selecionando uma entrada bem-sucedida, clique no link "tendo problemas" na tela de êxito no navegador e siga as instruções. Confira [solução de problemas](../troubleshooting.md#sign-in) para obter mais dicas.

### <a name="2-use-the-join-command"></a>2. usar o comando de junção

Abra o Live Share Viewlet na barra de atividade do VS Code e selecione "ingressar na sessão de colaboração..." ícone ou entrada.

![Ícone do viewlet Ingressar](../media/vscode-join-viewlet.png)

>**Observação:** Se você estiver ingressando como convidado somente leitura, será solicitado a inserir um nome de exibição para ajudar os participantes a identificá-lo na sessão.

### <a name="3-paste-the-invite-link"></a>3. colar o link de convite

Cole a URL do convite enviada e pressione ' Enter ' para confirmar.

É só isso! Em breve, você deverá estar conectado à sessão de colaboração.

## <a name="join-from-visual-studio"></a>Ingressar do Visual Studio

### <a name="1-sign-in"></a>1. entrar

Depois de instalado, inicie o Visual Studio e entre se você ainda não tiver feito isso. Se você precisar usar uma entrada diferente para o Visual Studio que sua conta de [personalização](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), vá para **ferramentas &gt; opções &gt; Live share &gt; conta de usuário**.

![Entrada do VS](../media/vs-sign-in-button.png)

Ainda está com problemas? Consulte [solução de problemas](../troubleshooting.md#sign-in).

### <a name="2-use-the-join-command"></a>2. usar o comando de junção

Basta ir para o **arquivo > ingressar na sessão de colaboração**.

![Menu de ingresso do VS](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. colar o link de convite

Cole a URL do convite enviada e pressione ' Enter ' para confirmar.

É só isso! Em breve, você deverá estar conectado à sessão de colaboração.

## <a name="see-also"></a>Consulte também

Guias de Início Rápido

- [Início rápido: compartilhar seu primeiro projeto](../quickstart/share.md)
- [Início rápido: ingressar na sua primeira sessão](../quickstart/join.md)

Instruções

- [Como colaborar usando o Visual Studio Code](../use/vscode.md)
- [Como colaborar usando o Visual Studio](../use/vs.md)
- [Como: fornecer comentários](../support.md)

Referência

- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)
- [Detalhes de instalação do Linux](linux.md)
- [Suporte de idioma e plataforma](platform-support.md)
- [Suporte de extensão](extensions.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
