---
title: Colaborar usando o Visual Studio Code – Visual Studio Live Share | Microsoft Docs
description: Um conjunto de instruções de colaboração para Visual Studio Code e Live Share.
ms.custom: ''
ms.date: 09/16/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: 810c60754c0be4f11511fb1ccbb0bb612de42e5d
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019804"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>Como fazer: entrevistas técnicas usando Live Share

Antes de começar a usar o Live Share para entrevistas técnicas, você deve concluir uma etapa integral: **baixar Visual Studio Code e o pacote de extensão Live share de seu Marketplace** seguindo [estas etapas.](../use/vscode.md)

Live Share fornece a capacidade de hospedar sessões reutilizáveis! Tudo isso significa que você pode agendar uma sessão de Live Share com antecedência para suas entrevistas técnicas e não se preocupe com a expiração do link.

> [!TIP] 
>Um link de sessão reutilizável é persistente e dura 30 dias a partir da data de criação ou da data do último uso. Ao gerar um link de sessão reutilizável para sua entrevista, verifique se a entrevista está dentro de 30 dias a partir da data da criação do link. Se o link expirar, basta criar uma nova sessão reutilizável. (Há uma maneira de garantir que o link nunca expire, mas isso é muito mais fácil para entrevistas!)

### <a name="what-to-do-as-an-interviewer"></a>**O que fazer como um intervisor?**

Como um intervisor, você atuará como o host da sessão de Live Share. Se você não estiver familiarizado com Live Share, sugerimos que consulte a seção [compartilhar um projeto](../use/vscode.md) do nosso guia de instruções.

Agora, para criar uma sessão de Live Share para sua entrevista técnica, você criará uma "sessão reutilizável" especial em vez da sessão de colaboração normal. Isso permitirá que você tenha uma sessão de Live Share que possa ser agendada antecipadamente e, em seguida, usada a qualquer momento.

Para criar uma sessão reutilizável, faça o seguinte:

1. Vá para o `Command Palette` usando `Ctrl+Shift+P`
1. Digite "Sha ao vivo..." e clique no comando ' **_Live share: criar link de sessão reutilizável_** '.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Isso criará uma sessão reutilizável e um link para ela será copiado para a área de transferência. Você verá um pop-up de notificação no canto inferior direito do seu editor.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Sua sessão reutilizável foi criada! Compartilhe o link com sua sessão e use-o toda vez para acessar a sessão!

Quando você tiver esse link, basta compartilhá-lo com o intervisor por email ou sua escolha de mecanismo de agendamento. Tudo o que eles precisam fazer é clicar nesse link no momento da entrevista e eles estarão em uma sessão de Live Share. 

### <a name="what-to-do-as-the-interviewee"></a>**O que fazer como a interexibição?**

Se você estiver esperando fazer uma entrevista técnica usando Live Share, você está com sorte! Queremos ter certeza de que você está familiarizado com os recursos básicos de Live Share para se sentir confortável durante sua entrevista.

1. Antes da entrevista, Reserve algum tempo e veja o [Guia de instruções](../use/vscode.md) para entender como Live share funciona.

1. Talvez você queira instalar o Visual Studio Code antecipadamente para que não esteja aguardando a conclusão da instalação depois de iniciar sua entrevista

1. Se você não tiver tempo, não há preocupações. Tudo o que você precisa ter uma entrevista completa é o link para uma sessão Live Share que o seu entrevistador envia ao programar a entrevista. Apenas clicar no link o guiará automaticamente por todas as etapas necessárias.

1. No momento da entrevista, basta clicar no link e seguir as etapas que ele conduz. Se você estiver no início ou o seu entrevistador está atrasado para a entrevista, não se preocupe! Você estará apenas no ' lobby ' aguardando a junção do seu intervisor. Nenhuma outra etapa é necessária e, depois que o seu intervisor se juntar, a sessão será iniciada automaticamente.

>[!NOTE]
>Se você descobrir que a sessão foi desconectada antes ou depois da junção do intervisor, não se preocupe. Basta sair dessa sessão se (ela ainda não estiver fechada) e clicar novamente no mesmo link!

Agora você está pronto para usar Live Share para sua entrevista! 
