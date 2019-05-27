---
title: Perfil de usuário – compartilhamento ao vivo do Visual Studio | Microsoft Docs
description: Uma visão geral de como exibir e remover seu perfil de usuário do Visual Studio Live Share.
ms.custom: ''
ms.date: 05/222/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 1d3b4977745e33ba0ee1b599ea4257c4a49d970d
ms.sourcegitcommit: bfa1020882095fcc7d31cd71cf1f2e601e3bea06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "66224695"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>Perfil do usuário

Quando você autentica com o Visual Studio Live Share, ele cria um perfil de usuário para você, que permite que qualquer participantes colabora para ver quem é você (por exemplo, seu endereço de email, o avatar). Em um determinado momento, você pode exibir as informações de perfil que Live Share armazenados em seu nome, navegando até uma das páginas a seguir (dependendo do provedor de identidade que você usou):

- [Conta da Microsoft / Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

A página de pedir que você entrar para verificar sua identidade e, em seguida, exibir a saída JSON bruta para o seu perfil do usuário.

<img width="500px" src="media/user-profile.png" />

Se o Visual Studio Live Share atualmente não tem um perfil armazenado para a identidade que você conectado, em seguida, ele permitirá que você sabe que também.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>Remover seu perfil

Se você quiser remover seu perfil do usuário, você pode clicar no link intitulado `Click here to get your data removed from our systems` sobre o [página de perfil do usuário](#user-profile). Como alternativa, você pode visitar uma das seguintes páginas diretamente (dependendo do provedor de identidade que você usou):

- [Conta da Microsoft / Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/deleteme)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/deleteme)

Caso contrário, o Visual Studio Live Share excluirá automaticamente seu perfil de 30 dias após seu último entrar com êxito. Nesse contexto, um "entrar com êxito" refere-se ao seguinte (dependendo da ferramenta que você está usando):

| Editor/IDE | Seu perfil do usuário será excluído 30 dias após a última vez que você... |
|-|-|
| Visual Studio | Inicie uma nova instância do IDE. Para dar suporte a logon único, o Visual Studio Live Share atualiza sua sessão de autenticação, sempre que você abrir uma nova instância do Visual Studio. |
| Visual Studio Code | Concluir o fluxo de trabalho de autenticação baseada em navegador (por exemplo, clicando na `Sign In` botão ou executando o `Live Share: Sign in with browser` comando). Visual Studio Live Share irão se lembrar de sua sessão de autenticação no cliente, para impedir que você precise entrar toda vez que você compartilha. No entanto, essa sessão expira após 30 dias e nunca automaticamente é atualizada, até você explícita entrar por meio do navegador novamente. |

## <a name="see-also"></a>Consulte também

- [Suporte de idioma e plataforma](reference/platform-support.md)
- [Requisitos de conectividade do Live Share](reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](reference/security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](troubleshooting.md) ou [envie comentários](support.md).
