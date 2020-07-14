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
ms.openlocfilehash: ff5dff3e6a88dba8e0d6f49c5bdcf52d1163ef1a
ms.sourcegitcommit: 6b1c502ba1763527aa69bad2e0c919d60a47153d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86300259"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>Como fazer: entrevistas técnicas usando Live Share

Usando Live Share para entrevistas, permite que o entrevistador e o candidato tenham uma sessão de entrevista rápida e confiável, com um IDE ou editor de fidelidade total. Este tutorial se concentrará no uso de ["sessões planejadas"](../reference/insiders.md) e [Live share Web Join](../quickstart/browser-join.md) para a experiência de entrevistas. 

## <a name="setup-for-interviewer-vs-code"></a>Configuração do intervisor (VS Code)

Instale [Visual Studio Code](../use/vscode.md) e baixe o [pacote de extensão Live share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack) do Marketplace. O pacote de extensão fornecerá o nosso suporte de áudio para entrevistas.

>[!TIP]
>Para ter a melhor experiência de visualização usando Live Share no VS Code, certifique-se de ativar o sinalizador de recursos de Live Share de entrada. *Preferências: UserSettings > Extensions > Visual Studio Live Share conjunto de recursos >: pessoas*

>[!NOTE]
> Live Share o chat é criado com a extensão de Live Share no VS Code.

## <a name="scheduling-an-interview"></a>Agendando uma entrevista 

**Live share no vs Code** fornece a capacidade de criar sessões de Live share com antecedência. Você pode usar as seguintes etapas para criar uma sessão com antecedência:

### <a name="option-a-insider"></a>Opção A (insider)
1. Vá para o `Planned Sessions` no Viewlet e crie uma nova sessão. Agora, isso criou uma sessão de Live Share com antecedência para você, que estará disponível no Viewlet para você no momento da entrevista. 

![sessão planejada-CreateLink](../media/planned-session-creation-vscode.PNG)


2. Copie o link de Viewlet e envie-o para o candidato. O link que você envia para o candidato pode ser usado por eles no momento da entrevista para ingressar na sessão.

![COPYLINK-sessão planejada](../media/planned-session-copylink-vscode.PNG)


### <a name="option-b-not-an-insider"></a>Opção B (não é um insider)

1. Vá para o `Command Palette` usando`Ctrl+Shift+P`
1. Digite "Sha ao vivo..." e clique no comando '_Live share: criar link de sessão reutilizável_'.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Isso criará uma sessão reutilizável e um link para ela será copiado para a área de transferência. Você verá um pop-up de notificação no canto inferior direito do seu editor.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. envie o link.

Quando você tiver esse link, basta compartilhá-lo com o intervisor por email ou sua escolha de mecanismo de agendamento. Tudo o que eles precisam fazer é clicar nesse link no momento da entrevista e eles estarão em uma sessão de Live Share. 
> [!TIP] 
>Um link de sessão reutilizável é persistente e dura 30 dias a partir da data de criação ou da data do último uso. Ao gerar um link de sessão reutilizável para sua entrevista, verifique se a entrevista está dentro de 30 dias a partir da data da criação do link. Se o link expirar, basta criar uma nova sessão reutilizável. (Há uma maneira de garantir que o link nunca expire, mas isso é muito mais fácil para entrevistas!)

**Observação:** Atualmente, Live Share no Visual Studio não tem a capacidade de criar sessões com antecedência. Para as entrevistas que você realiza usando Live Share no Visual Studio, você pode seguir nosso guia sobre como iniciar uma sessão de Live Share instantânea [aqui](../quickstart/share.md)



## <a name="setup-for-candidate"></a>Configuração para candidato
Embora um candidato sempre possa instalar o Visual Studio ou Visual Studio Code para ingressar na entrevista, ele não precisa fazer isso. **Live Share as sessões de entrevista podem ser unidas por candidatos sem nenhuma configuração anterior.** Eles podem clicar no link entrevista no momento da sessão e **ingressar no navegador**. Saiba mais [aqui.](../quickstart/browser-join.md)


<!--
### **What to do as an Interviewer?**

As an interviewer you will act as the host of the Live Share session. If you are not familiar with Live Share, we suggest you refer to the [share a project](../use/vscode.md) section of our how-to guide
### **What to do as the Interviewee?**

If you are expecting to do a Technical Interview using Live Share, you are in luck! We want to make sure you are familiar with the basic Live Share features so you feel comfortable during your interview.

1. Before the interview, take some time and look over the [How-to guide](../use/vscode.md) so you understand how Live Share works.

1. You may want to install Visual Studio Code beforehand so that you are not waiting for the installation to complete once you start your interview

1. If you don't have the time, no worries. All you need to have a full interview is the link to a Live Share session your interviewer sends you while scheduling the interview. Just clicking on the link will automatically take you through all the steps needed.

1. At the time of the interview, just click on the link and follow the steps it takes you through. If you are early or your interviewer is late to the interview, don't worry! You will just be in the 'lobby' waiting for your interviewer to join. No other steps are required, and once your interviewer joins the session will automatically start.

>[!NOTE]
>If you find that the session has disconnected before or after the interviewer joined, don't worry. Just exit out of that session if (it isn't already closed) and re-click on the same link!

You are now all set to go with using Live Share for your interview! 
-->
