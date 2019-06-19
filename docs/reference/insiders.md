---
title: Insiders - compartilhamento ao vivo do Visual Studio | Microsoft Docs
description: Uma descrição do canal 'Insiders' dentro do Visual Studio Live Share.
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
ms.openlocfilehash: a79effc25c09851301bb2231511a8a9d8a9f549b
ms.sourcegitcommit: 6e84bf17eedd616417f474551344c2161700c4d3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67192718"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Participante do Programa Windows Insider

A equipe do Visual Studio Live Share tenta iterar rapidamente na ordem aos comentários dos usuários de endereço, e como parte disso, oferecemos dois recursos separados "canais" que permitem que você decida como rapidamente receberá novos recursos. Por padrão, depois de instalar a extensão do Visual Studio Live Share, você está usando o `Stable` conjunto, que inclui todos os recursos prontos para produção (por exemplo, co editando, compartilhado de depuração, terminais) de recursos. No entanto, se você quisesse obter acesso antecipado ao recurso que estamos trabalhando, você pode participar de `Insiders` conjunto de recursos, alterando a configuração a seguir no seu IDE:

* Visual Studio

    ![feature-set-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![feature-set-vscode](../media/feature-set-vscode.png)

As seções a seguir descrevem o conjunto de recursos que estão dentro de `Insiders` conjunto de recursos e, portanto, está pronto para avaliar o depois que você alterar a configuração mencionada anteriormente:

## <a name="direct-user-invitations"></a>Convites direta do usuário

Atualmente, o Visual Studio e Visual Studio Code fornecem um `Contacts` painel, que permite duas funções principais:

1. Exibindo uma lista de `Suggested Contacts`, que são os desenvolvedores que contribuíram para o projeto aberto no momento nos últimos 30 dias. Na prática, as pessoas que você provavelmente deseja colaborar e, portanto, sugerimos-los para torná-lo mais fácil começar.

2. Fornecer a lista de `Recent Contacts`, que são os desenvolvedores anteriormente, você tiver colaborado com usando o Live Share. Na prática, a maioria dos desenvolvedores frequentemente colabore com as mesmas pessoas e, portanto, a lista recente possibilita um meio mais reproduzível de trabalhar com sua equipe/sala de aula, etc.

No entanto, o `Contacts` lista atualmente só permite que você convidar contatos recentes/sugeridos por email, que aprendemos não não tão eficiente quanto poderia ser. Se você instalar a atualização mais recente do Live Share e ativar `Insiders` (conforme descrito acima), você agora poderá **convidar desenvolvedores em uma sessão de colaboração diretamente do IDE**! Observe que, se você estiver usando o Visual Studio Code, você precisará instalar o [Build Insiders](https://code.visualstudio.com/insiders/) para que esse recurso funcione.

![Invitatiosn direta](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Um host do Live Share (à esquerda) diretamente, convidando um par (à direita) em uma sessão</em>

Depois que os desenvolvedores entrar com o Live Share, seu status de disponibilidade serão publicadas para seus colegas. Como resultado, você pode ver que alguém de sua equipe está online e, em seguida, imediatamente começar a colaborar com eles. Eles receberá uma notificação do sistema que lhes dá a opção de ingressar na sessão ou não. Isso remove a necessidade de URLs de sessão do exchange totalmente.

Após 5 minutos de inatividade, seu status alternará automaticamente para `Away`, e quando você estiver dentro de uma sessão do Live Share, seu status alternará automaticamente para `Do not disturb` (quais suprresses convite notificações do sistema). Depois que você se torne ativa novamente e/ou deixe uma sessão do Live Share, seu status alternará automaticamente para `Available`. Com esse comportamento, você não precisa gerenciar, na verdade, o status do Live Share. Ele está aí simplesmente para habilitar os convites diretos e se comunicar com seus colegas que se encontram disponíveis para colaboração ou não. No entanto, você pode definir seu status sempre manualmente se preferir.

Se você deseja recusar esse recurso, você pode simplesmente desabilitar o `Presence` definindo configurações de compartilhamento ao vivo no Visual Studio e Visual Studio Code. Quando desabilitado, você ainda poderá ver o status dos outros e convidá-los, mas seu status não será publicado e outros não diretamente convidá-lo.

## <a name="see-also"></a>Consulte também

- [Suporte de idioma e plataforma](platform-support.md)
- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
