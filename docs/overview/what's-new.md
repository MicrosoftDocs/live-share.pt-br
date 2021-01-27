---
title: Visão geral | Microsoft Docs
description: Novos recursos e versões do Live Share
ms.custom: ''
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
ms.workload:
- liveshare
ms.openlocfilehash: 70adacfbb8d5e3b4ca9a7b2652c7c455a977f2f7
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870468"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

## <a name="integrated-chat"></a>Chat integrado 
O Live Share agora tem um bate-papo integrado para [Visual Studio Code](..\use\vscode.md) e [Live share Web.](..\quickstart\browser-join) Isso significa que você pode bater papo com seus colegas de dentro de seu IDE.

>[!TIP]
>Live Share forneceu anteriormente uma extensão complementar. Isso significava que os usuários com essa extensão poderiam usar o chat dentro de Live Share. Essa extensão agora foi depreciada e todos os usuários de Live Share no VS Code e no cliente Web terão um serviço de chat.

### <a name="common-questions"></a>Perguntas comuns

##### <a name="why-am-i-seeing-this-error-message"></a>Por que estou vendo essa mensagem de erro?

Se você tiver desabilitado atualizações automáticas para suas extensões (incluindo Live Share e a Live Share extensão de chat complementar), verá as seguintes mensagens de erro.

1. Como o host ou convidado, se você tiver a extensão de chat Live Share Companion instalada, se você vir:

>Atualize a `Live Share Chat` extensão complementar. A versão instalada não é mais compatível.

Esta mensagem de erro requer que você atualize o bate-papo do Live Share Companion para usar a nova experiência de chat integrada.
Visite o Marketplace e pesquise por *chat* e atualize para a versão mais recente. 

2. Como convidado, se você tiver as versões mais recentes das extensões de Live Share e se você vir:

>O host desta sessão de colaboração está atualmente desconectado do chat ou está usando uma versão do _Live share_ que não oferece suporte a esse recurso. [Saiba mais] 

O host de sua sessão de Live Share está usando o Visual Studio ou outras plataformas para hospedar uma sessão, que não oferece suporte a Live Share chat integrado ainda. Eles também podem estar vendo a mensagem de erro 1. listados acima.

3. Como um host ou convidado, se você vir essa mensagem de erro: 

> A pessoa que você está tentando contatar não está disponível no momento ou usando uma versão do _Live share_ que não oferece suporte a esse recurso. [Saiba mais] 

>O serviço de chat está desconectado no momento. Tente novamente em breve.

O host de sua sessão de Live Share está usando o Visual Studio ou outras plataformas para hospedar uma sessão, que não oferece suporte a Live Share chat integrado ainda. Eles também podem estar indisponíveis no momento. Eles também podem estar vendo a mensagem de erro 1. listados acima.


**Para usar o chat integrado, você precisa ter atualizações automáticas para suas extensões de Live Share no.** 
