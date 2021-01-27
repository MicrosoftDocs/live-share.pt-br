---
title: Insideres | Microsoft Docs
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
ms.openlocfilehash: a58bf30ad1c6f4c4cecedb1a07ca0482a67f5ec7
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870715"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Participante do Programa Windows Insider

A equipe de Visual Studio Live Share se trata de iteração rápida, experimentando novas ideias e ouvindo nossos clientes! As pessoas de fora oferecem aos nossos usuários a oportunidade de experimentar todos os nossos novos recursos primeiro e fornecer seus valiosos comentários! Saiba como [se tornar um insider](#BecomeanInsider) abaixo e ajude-nos a moldar o futuro da colaboração do desenvolvedor. 

## <a name="new-to-insiders"></a>✨ Novos para insideres ✨

### <a name="planned-sessions-vs-code"></a>**Sessões planejadas (VS Code)**
As sessões reutilizáveis agora têm um lugar no Live Share Viewlet. As sessões planejadas permitem que você como o host de uma sessão de Live Share para criar um link de sessão de Live Share com antecedência. 


![imagem planejada-CreateLink-vscode ](../media/planned-session-creation-vscode.png)
 *mostrando a criação de uma nova sessão planejada a partir do Viewlet*

Isso permite que você compartilhe esse link como parte de suas reuniões agendadas regularmente com suas equipes, suas entrevistas ou suas sessões de emparelhamento.
Assim que uma sessão for tão planejada antecipadamente, você poderá acessá-la do Live Share Viewlet diretamente. 

![imagem planejada-vscode ](../media/planned-session-copylink-vscode.png) * mostrando "sessões planejadas" no Live share Viewlet

>[!TIP]
>Ative as pessoas para Live Share em VS Code para usar ' sessões de >planejadas '. Saiba como se tornar um insider abaixo. 

"Sessões planejadas" no Visual Studio é atualmente apenas um recurso interno. Verifique novamente se há atualizações quando avança para o estágio Insider. 


# <a name="pushed-to-public"></a>Enviado por push para público 

Os recursos do Insider a seguir foram enviados por push para o público.

### <a name="reusable-sessions-vs-code"></a>**Sessões reutilizáveis (VS Code)**

Agora Live Share pode hospedar sessões reutilizáveis! As sessões reutilizáveis oferecem a capacidade de reutilizar uma sessão de Live Share para vários cenários. Isso significa que você pode agendar uma sessão de Live Share com antecedência para suas entrevistas técnicas, sessão de Mob semanal, usar a mesma sessão ao mentor de um amigo e muito mais!

Para criar uma sessão reutilizável, faça o seguinte:
1. Vá para o `Command Palette` usando `Ctrl+Shift+P`
1. Digite "Sha ao vivo..." e clique no comando '**_Live share: criar link de sessão reutilizável_**'.

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Isso criará uma sessão reutilizável e um link para ela será copiado para a área de transferência. Você verá um pop-up de notificação no canto inferior direito do seu editor.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Sua sessão reutilizável foi criada! Compartilhe o link com sua sessão e use-o toda vez para acessar a sessão!

> [!TIP] 
>Um link de sessão reutilizável é persistente e dura 30 dias a partir da data de criação ou da data do último uso. Isso significa que se você continuar usando sua sessão pelo menos uma vez a cada 30 dias, não precisará se preocupar com ela expirar. Basta salvar o link em um local seguro onde você possa acessá-lo facilmente!
 


## <a name="become-an-insider"></a>Torne-se <a name="BecomeanInsider"></a> um insider

Por padrão, depois de instalar a extensão de Visual Studio Live Share, você está usando o `Stable` conjunto de recursos, que inclui todos os recursos prontos para produção (por exemplo, coedição, depuração compartilhada, terminais). No entanto, se você quiser obter acesso antecipado ao recurso no qual estamos trabalhando, você pode aceitar o conjunto de `Insiders` recursos alterando a seguinte configuração em seu IDE:

* Visual Studio

    ![conjunto de recursos-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![recurso-Set-vscode](../media/feature-set-vscode.png)

As seções a seguir descrevem o conjunto de recursos que estão atualmente dentro do `Insiders` conjunto de recursos e, portanto, estão prontas para avaliação quando você altera a configuração mencionada anteriormente:



## <a name="see-also"></a>Confira também

- [Suporte de idioma e plataforma](platform-support.md)
- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
