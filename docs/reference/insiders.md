---
title: Pessoas-Visual Studio Live Share | Microsoft Docs
description: Uma descrição do canal ' Insiders ' no Visual Studio Live Share.
ms.custom: ''
ms.date: 04/02/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 04bfb314ebae711566a8bab8b0ada8f2fbd2e940
ms.sourcegitcommit: 6b46e300d76eda661ab34c67a3b909d5c162cd9a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2019
ms.locfileid: "70062291"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Participante do Programa Windows Insider

A equipe de Visual Studio Live Share se trata de iteração rápida, experimentando novas ideias e ouvindo nossos clientes! As pessoas de fora oferecem aos nossos usuários a oportunidade de experimentar todos os nossos novos recursos primeiro e fornecer seus valiosos comentários! Saiba como [se tornar um](#BecomeanInsider) Insider abaixo e ajude-nos a moldar o futuro da colaboração do desenvolvedor. 

## <a name="new-to-insiders"></a>✨ Novos para insideres ✨


### <a name="reusable-sessions-vs-code"></a>**Sessões reutilizáveis (VS Code)**

Agora Live Share pode hospedar sessões reutilizáveis! As sessões reutilizáveis oferecem a capacidade de reutilizar uma sessão de Live Share para vários cenários. Isso significa que você pode agendar uma sessão de Live Share com antecedência para suas entrevistas técnicas, sessão de Mob semanal, usar a mesma sessão ao mentor de um amigo e muito mais!

Para criar uma sessão reutilizável, faça o seguinte:
1. Vá para o `Command Palette` usando`Ctrl+Shift+P`
1. Digite "Sha ao vivo..." e clique no botão **'_Live share: Crie o comando de link_** de sessão reutilizável.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Isso criará uma sessão reutilizável e um link para ela será copiado para a área de transferência. Você verá um pop-up de notificação no canto inferior direito do seu editor.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Sua sessão reutilizável foi criada! Compartilhe o link com sua sessão e use-o toda vez para acessar a sessão!

> [!TIP] 
>Um link de sessão reutilizável é persistente e dura 30 dias a partir da data de criação ou da data do último uso. Isso significa que se você continuar usando sua sessão pelo menos uma vez a cada 30 dias, não precisará se preocupar com ela expirar. Basta salvar o link em um local seguro onde você possa acessá-lo facilmente!
 

### <a name="direct-user-invitations"></a>**Convites de usuário diretos**

Atualmente, o Visual Studio e o Visual Studio Code fornecem `Contacts` um painel, que habilita duas funções principais:

1. Exibindo uma lista `Suggested Contacts`de, que são os desenvolvedores que contribuíram para seu projeto aberto no momento nos últimos 30 dias. Na prática, esses são os colegas com os quais você provavelmente deseja colaborar e, portanto, nós os sugerimos para tornar mais fácil começar.

2. Fornecendo a lista de `Recent Contacts`, que são os desenvolvedores com os quais você colaborau anteriormente usando Live share. Na prática, a maioria dos desenvolvedores costuma colaborar com as mesmas pessoas e, portanto, a lista recente permite um meio mais reproduzível de trabalhar com sua equipe/sala de aula/etc.

No entanto `Contacts` , a lista atualmente só permite que você convide contatos recentes/sugeridos por email, o que aprendemos não é tão eficiente quanto poderia ser. Se você instalar a atualização de Live share mais recente e `Insiders` habilitar (conforme descrito acima), agora será possível **convidar os desenvolvedores para uma sessão de colaboração diretamente do IDE**! Observe que, se você estiver usando Visual Studio Code, precisará instalar a [compilação](https://code.visualstudio.com/insiders/) dos insiders para que esse recurso funcione.

![Invitatiosn direto](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Um host Live Share (à esquerda) convidando diretamente um par (direito) em uma sessão</em>

Depois que os desenvolvedores entrarem com Live Share, seu status de disponibilidade será publicado em seus colegas. Como resultado, você pode ver que alguém em sua equipe está online e, em seguida, começar a colaborar com eles imediatamente. Eles receberão uma notificação do sistema que lhes dá a opção de ingressar na sessão ou não. Isso elimina a necessidade de trocar totalmente as URLs de sessão.

Após 5 minutos de inatividade, seu status será alternado automaticamente `Away`para e, quando você estiver dentro de uma sessão de Live share, seu status será `Do not disturb` alternado automaticamente para (que suprresses notificações do sistema de convite). Depois que você se tornar ativo novamente e/ou deixar uma sessão de Live Share, seu status será automaticamente `Available`revertido para. Com esse comportamento, você não precisa realmente gerenciar seu status de Live Share. Ele é simplesmente para habilitar convites diretos e se comunicar com seus colegas se você estiver disponível para colaboração ou não. No entanto, você sempre pode definir manualmente seu status, se preferir.

Se você quiser recusar esse recurso, basta desabilitar a `Presence` configuração dentro das configurações de Live share no Visual Studio e Visual Studio Code. Depois de desabilitado, você ainda poderá ver o status de outro e convidá-los, mas seu status não será publicado e outros não poderão convidá-lo diretamente.

 

## Torne-se <a name="BecomeanInsider"></a> um insider

Por padrão, depois de instalar a extensão de Visual Studio Live share, você está `Stable` usando o conjunto de recursos, que inclui todos os recursos prontos para produção (por exemplo, coedição, depuração compartilhada, terminais). No entanto, se você quiser obter acesso antecipado ao recurso no qual estamos trabalhando, você pode aceitar o `Insiders` conjunto de recursos alterando a seguinte configuração em seu IDE:

* Visual Studio

    ![conjunto de recursos-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![recurso-Set-vscode](../media/feature-set-vscode.png)

As seções a seguir descrevem o conjunto de recursos que estão atualmente dentro `Insiders` do conjunto de recursos e, portanto, estão prontas para avaliação quando você altera a configuração mencionada anteriormente:



## <a name="see-also"></a>Consulte também

- [Suporte de idioma e plataforma](platform-support.md)
- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
