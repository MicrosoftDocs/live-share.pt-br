---
title: Perfil do usuário | Microsoft Docs
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
ms.openlocfilehash: c1c0363074c0737ae3aedb68952f3147e58cddb9
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870801"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>Perfil do Usuário

Quando você se autentica com o Visual Studio Live Share, ele cria um perfil de usuário para você, que simplesmente permite aos participantes que colaboram para ver quem você está (por exemplo, seu endereço de email, Avatar). A qualquer momento, você pode exibir as informações de perfil que Live Share armazenadas em seu nome, navegando para uma das seguintes páginas (dependendo do provedor de identidade usado):

- [Conta da Microsoft/Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

Essa página solicitará que você entre (para verificar sua identidade) e, em seguida, exibirá a saída JSON bruta para seu perfil de usuário.

<img width="500px" src="media/user-profile.png" />

Se Visual Studio Live Share atualmente não tiver um perfil armazenado para a identidade com a qual você fez logon, ele também permitirá que você saiba isso.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>Removendo seu perfil

Se desejar remover seu perfil de usuário, você poderá clicar no `Delete your account` botão na [página perfil do usuário](#user-profile). Caso contrário, Visual Studio Live Share excluirá automaticamente o seu perfil 30 dias desde a última entrada bem-sucedida. Nesse contexto, uma "entrada bem-sucedida" refere-se ao seguinte (dependendo da ferramenta que você está usando):

| IDE/Editor | Seu perfil de usuário será excluído 30 dias após a última vez que você... |
|-|-|
| Visual Studio | Inicie uma nova instância do IDE. Para dar suporte ao logon único, o Visual Studio Live Share atualiza sua sessão de autenticação toda vez que você abre uma nova instância do Visual Studio. |
| Visual Studio Code | Conclua o fluxo de trabalho de autenticação baseada em navegador (por exemplo, clicando no `Sign In` botão ou executando o `Live Share: Sign in with browser` comando). Visual Studio Live Share se lembrará da sessão de autenticação no cliente, para impedir que você entre sempre que compartilhar. No entanto, essa sessão expira após 30 dias e nunca é atualizada automaticamente, até você explicitamente entrar no navegador. |

## <a name="see-also"></a>Confira também

- [Suporte de idioma e plataforma](reference/platform-support.md)
- [Requisitos de conectividade do Live Share](reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](reference/security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](troubleshooting.md) ou [envie comentários](support.md).
