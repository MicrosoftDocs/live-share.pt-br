---
title: Associação manual - Visual Studio Live Share | Microsoft Docs
description: Compartilhar informações sobre como ingressar em uma sessão de colaboração manualmente no Visual Studio Live.
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
ms.openlocfilehash: 8ec4bac1c169c17de5e5ec8d26352cc13d62683b
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640062"
---
# <a name="join-a-session-manually"></a>Ingressar em uma sessão manualmente

Além de abrir um link em um navegador para ingressar em uma sessão de colaboração, você pode unir manualmente colando o link em uma ferramenta já está em execução. Isso pode ser útil se você quiser usar uma ferramenta diferente, que é geralmente feito ou se você estiver tendo problemas com a introdução de links de convite para trabalhar por algum motivo.

As instruções exatas variam entre [Visual Studio](#join-from-visual-studio) e [Visual Studio Code](#join-from-visual-studio-code), então, escolher a ferramenta que você pretende usar para obter mais informações.

## <a name="join-from-visual-studio-code"></a>Junte-se do Visual Studio Code

### <a name="1-sign-in"></a>1. Entrar

>**Observação:** Se você quiser ingressar em uma sessão de colaboração como um convidado de somente leitura, você poderá ignorar a entrar. Você será têm acesso para exibir e navegar em todo o código que é compartilhado, mas não conseguir fazer edições.

![Notificação do sistema solicitando a entrada com um navegador da Web](../media/vscode-sign-in-toast.png)

Para colaborar, é preciso entrar no Visual Studio Live Share para que todos saibam quem é você. **Clique em** sobre o status de "Live Share" barra item ou pressione **Ctrl + Shift + P / Cmd + Shift + P** e selecione o "compartilhamento ao vivo: Entrar com Navegador".

![Botão Entrar do VS Code](../media/vscode-sign-in-button.png)

Seu navegador será iniciado enquanto uma notificação será exibida a inicialização, solicitando que você entrar. Conclua o processo de entrada no navegador e, em seguida, feche-o quando terminar.

Se você estiver encontrando problemas com o VS Code não pegar um entrar com êxito, clique no link "Problemas" na tela de sucesso no navegador e siga as instruções. Fazer check-out [solução de problemas](../troubleshooting.md#sign-in) para obter mais dicas.

### <a name="2-use-the-join-command"></a>2. Use o comando de junção

Abra o Live Share viewlet na barra de atividade do VS Code e selecione "junção sessão de colaboração..." ícone ou entrada.

![Ícone do viewlet Ingressar](../media/vscode-join-viewlet.png)

>**Observação:** Se você estiver unindo como um convidado de somente leitura, em seguida, será solicitado a inserir um nome de exibição para ajudar a identificá-lo na sessão de participantes.

### <a name="3-paste-the-invite-link"></a>3. Cole o link de convite

Cole a URL de convite foram enviadas e pressionar 'Enter' para confirmar.

É só isso! Em breve, você deverá estar conectado à sessão de colaboração.

## <a name="join-from-visual-studio"></a>Junte-se do Visual Studio

### <a name="1-sign-in"></a>1. Entrar

Uma vez instalado, inicie o Visual Studio e entre, se você ainda não tiver. Se você precisa usar uma entrada diferente para o Visual Studio que sua [conta de personalização](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), acesse **ferramentas &gt; opções &gt; Live Share &gt; conta de usuário**.

![VS entrar](../media/vs-sign-in-button.png)

Ainda está com problemas? Ver [solução de problemas](../troubleshooting.md#sign-in).

### <a name="2-use-the-join-command"></a>2. Use o comando de junção

Basta ir para **arquivo > Junte-se a sessão de colaboração**.

![Menu de ingresso do VS](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. Cole o link de convite

Cole a URL de convite foram enviadas e pressionar 'Enter' para confirmar.

É só isso! Em breve, você deverá estar conectado à sessão de colaboração.

## <a name="see-also"></a>Consulte também

Guias de Início Rápido

- [Início Rápido: Compartilhar seu primeiro projeto](../quickstart/share.md)
- [Início Rápido: Ingressar em sua primeira sessão](../quickstart/join.md)

Instruções

- [Como colaborar usando o Visual Studio Code](../use/vscode.md)
- [Como colaborar usando o Visual Studio](../use/vs.md)
- [Como Fornecer comentários](../support.md)

Referência

- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)
- [Detalhes de instalação do Linux](linux.md)
- [Suporte de idioma e plataforma](platform-support.md)
- [Suporte de extensão](extensions.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
