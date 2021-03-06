---
title: Presença | Microsoft Docs
description: Informações sobre o serviço de presença de contatos para Visual Studio Live Share.
ms.custom: ''
ms.date: 10/08/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: b13acd28ac7a13d90633bfdb6427a87c1c47609a
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870745"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="contacts-in-live-share"></a>Contatos em Live Share 

Você esteve usando Live Share e observou que o envio de links por meio de um aplicativo externo (como bate-papo ou email) pode ficar realmente mais velho? Sabemos que, se quisermos incentivar a colaboração, precisa haver a menor quantidade possível de fricção para você adorar. É por isso que Live Share agora tem **contatos** com **status** .

>Os contatos serão habilitados automaticamente para todas as versões do **Live share v 1.0.950** em diante.

Os contatos aparecerão na janela de Live Share como um painel separado, como mostrado na imagem abaixo: 

![Contacts](../media/vscode-contacts-intro.png)

<em> Mostrando o painel de contatos na janela de Live Share</em>
## <a name="who-shows-up-in-my-contacts"></a>Quem aparece em meus contatos?

O painel contatos é exibido para exibir dois tipos de contatos que dão suporte a fluxos de trabalho naturais dos desenvolvedores enquanto trabalham.
### <a name="1-recent-contacts"></a>1. contatos recentes  
 Esses são os desenvolvedores com os quais você colaborau anteriormente usando Live Share. Na prática, a maioria dos desenvolvedores costuma colaborar com as mesmas pessoas e, portanto, a lista recente permite um meio mais reproduzível de trabalhar com sua equipe/sala de aula/etc.
### <a name="2-suggested-contacts"></a>2. contatos sugeridos
Esses são os desenvolvedores que contribuíram para seu projeto aberto no momento nos últimos 30 dias. Na prática, esses são os colegas com os quais você provavelmente deseja colaborar e, portanto, nós os sugerimos para tornar mais fácil começar.

## <a name="direct-user-invitations"></a>Convites de usuário diretos 
Todos os seus contatos podem ser convidados diretamente para uma sessão de Live Share de dentro de seu editor. Eles receberão uma notificação do sistema que lhes dá a opção de ingressar na sessão ou não. Isso elimina a necessidade de trocar totalmente as URLs de sessão.
![DirectInvitationVSCode ](https://user-images.githubusercontent.com/51928518/66443914-e59c5d00-e9f5-11e9-957a-b1a92949d660.gif)
 <em>um host de Live share (à esquerda) convidando diretamente um par (direito) em uma sessão</em>

## <a name="how-does-status-for-contacts-work"></a>Como o status dos contatos funciona?
Depois que os desenvolvedores entrarem com Live Share, **seu status de disponibilidade será publicado em seus colegas.** Como resultado, você pode ver que alguém em sua equipe está online e, em seguida, começar a colaborar com eles imediatamente, usando o convite direto, como visto acima.
Seu status pode ser definido diretamente de dentro do editor para que você possa sinalizar a disponibilidade para sua equipe, sem a necessidade de alternar o contexto. Os contatos do Live Share têm 4 status no momento:

**1. disponível:** seu status padrão será `Available` se você tiver a extensão de Live share e estiver usando o editor ativamente, enquanto não estiver em uma sessão.

**2. não incomodar:** seu status é definido como `Do not disturb` se você estiver atualmente em uma sessão ativa do Live share e todas as notificações de convite forem suprimidas.

**3. ausentes:** após 5 minutos de inatividade, seu status será alternado automaticamente para `Away` .

**4. offline:** você estará offline quando estiver ausente por um longo período de tempo ou se optar por [recusar o status de compartilhamento](##ManagingPresence)


## <a name="managing-contacts-and-sharing-status"></a>Gerenciando contatos e status<a name="ManagingPresence"> </a> de compartilhamento

Se você quiser recusar esse recurso, poderá fazê-lo de duas maneiras.
1. Você pode desabilitar a configuração de status escolhendo `offline` . Depois de desabilitado, você ainda poderá ver o status de outro e convidá-los, mas seu status não será publicado e outros não poderão convidá-lo diretamente.
Você pode optar por estar offline clicando no círculo de status que abrirá o seguinte menu suspenso:

![dropdownstatus ](../media/vscode-presence-opt-out.png)
 <em> mostrando a lista suspensa dos Estados de presença</em>

2. Você pode abrir `user settings` e ir para *extensões > Visual Studio Live Share > Live share: presença* e desabilitar o serviço de presença. Depois de desabilitado, você ainda poderá ver o status de outro e convidá-los, mas seu status não será publicado e outros não poderão convidá-lo diretamente.

![presencesettings](../media/vscode-presence-setting.png)

## <a name="faqs"></a>Perguntas frequentes 

###### <a name="1-will-i-be-automatically-opting-into-sharing-status-when-i-use-live-share-v10950-and-above"></a>1. vou optar automaticamente por compartilhar o status ao usar Live Share v 1.0.950 e superior?

Na primeira vez que você vir contatos, você será notificado com um sistema de notificação e uma opção para recusar o compartilhamento do seu status. Depois disso, você será compartilhado automaticamente seu status com seus contatos, a menos que você opte por recusar, como mostrado acima.

###### <a name="2-can-i-add-my-own-contacts"></a>2. posso adicionar meus próprios contatos?

Atualmente, nosso serviço de contatos detecta automaticamente os colaboradores com quem você compartilha código com frequência ou trabalha no lado e não fornece a opção de adicionar seus próprios contatos. 


>A possibilidade de adicionar contatos manualmente será útil? Ajude-nos a priorizar isso abrindo uma solicitação de recurso do GitHub [aqui.](https://github.com/MicrosoftDocs/live-share/issues/new?template=feature_request.md)
 

 