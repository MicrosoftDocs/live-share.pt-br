---
title: Unindo-se do navegador-Visual Studio Live Share | Microsoft Docs
description: Introdução ao ingresso no navegador aos
ms.date: 03/18/2020
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: fishah
ms.author: fishah
manager: joncart
ms.workload:
- liveshare
ms.openlocfilehash: 741292a3df8b86a8f7a9484875b352ebe6e8ec10
ms.sourcegitcommit: 382f069abbd81ed258d497a974b30379be36b4f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79510621"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="preview-joining-a-live-share-session-from-the-browser"></a>✨ [Visualização] ✨ ingressando uma sessão de Live Share do navegador

Todas as Live Share sessões de colaboração agora têm a capacidade de ser unida ao navegador. Isso significa que um convidado para sua sessão não precisa mais instalar VS Code ou o Visual Studio para ingressar na sua sessão. Isso é especialmente útil para todas essas instâncias quando você deseja que alguém entre em sua sessão rapidamente ou para alunos que geralmente não têm os clientes de desktop instalados.

> [!TIP]
> Consulte a seção de perguntas frequentes abaixo para obter as perguntas mais comuns sobre como ingressar no navegador.

# <a name="how-to-join-a-live-share-session-from-the-browser"></a>Como ingressar em uma sessão de Live Share do navegador 

### <a name="1-host-starts-session"></a>1. host: inicia a sessão 
Para começar, o host deve ir para o Visual Studio ou VS Code para iniciar uma sessão de colaboração. Quando o host compartilha uma pasta ou projeto.

![Animação da sessão inicial](https://user-images.githubusercontent.com/51928518/76938928-b814e300-68b4-11ea-923e-cefabd4688c6.gif)

### <a name="2-guest-uses-shared-link-to-join-from-browser"></a>2. Guest: usa link compartilhado para ingressar do navegador 
Live Share irá gerar um link de junção que pode ser compartilhado com o convidado. O convidado agora pode usar este link para ser navegado para uma página da Web, que agora oferece a eles uma opção para continuar com o navegador.

![Animação de ingressar em uma sessão](https://user-images.githubusercontent.com/51928518/76941137-b8af7880-68b8-11ea-8228-41fdf4afd3ef.gif)

### <a name="3-guest-enjoys-full-fidelity-collaboration-experience-from-browser"></a>3. convidado: gosta da experiência de colaboração de fidelidade total do navegador 
Depois que o convidado ingressar na sessão, ele poderá ser executado da mesma forma que faria se estivesse colaborando com os clientes de desktop.

![Animação de fidelidade total](https://user-images.githubusercontent.com/51928518/76942009-40e24d80-68ba-11ea-885c-6eb1069ed550.gif)
# <a name="frequently-asked-questions"></a>Perguntas frequentes 

##### <a name="1-is-there-an-environment-running-in-the-background-that-is-hosting-my-session-in-the-browser"></a>1. há um ambiente em execução em segundo plano, que está hospedando minha sessão no navegador?
Quando você ingressa em uma sessão de Live Share do navegador, não há nenhum novo ambiente girado. É um serviço sem servidor. 
##### <a name="2-do-i-have-to-pay-for-the-service-of-joining-from-the-browser"></a>2. é necessário pagar pelo serviço de ingresso no navegador?
Ingressar do navegador é gratuito, assim como todas as Live Share.

##### <a name="3-how-is-this-different-from-visual-studio-online"></a>3. como isso é diferente do Visual Studio online?
Ao ingressar no navegador, você só acessa o cliente do VS Code no navegador durante a sessão. Quando a sessão terminar, todos os arquivos e pastas junto com os recursos do editor serão fechados. Para usar um editor no navegador, apoiado com seu próprio ambiente para editar seus próprios arquivos, você deve usar o [Visual Studio online.](aka.ms/vso)

##### <a name="4-does-this-work-for-all-browsers"></a>4. isso funciona para todos os navegadores?
Sim. Isso funciona em todos os navegadores. 
##### <a name="5-is-there-a-vs-client-that-i-can-use-in-the-browser"></a>5. há um cliente do VS que eu posso usar no navegador?
Ainda não temos isso disponível. 

# <a name="feedback-and-issues"></a>Comentários e problemas 
Esse é um recurso de visualização e esperamos obter comentários do usuário para melhorar a experiência. Preencha todos os comentários ou problemas que você vê em nosso repositório GitHub [aqui.](https://github.com/MicrosoftDocs/live-share/issues/new?template=bug_report.md)