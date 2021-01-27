---
title: Suporte a plataformas e idiomas | Microsoft Docs
description: Uma visão geral do suporte de plataforma e idioma para o Visual Studio Live share.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: f3dbe1c81a9f91b6452185f4089b5d5100582275
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870533"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>Suporte de idioma e plataforma

Os recursos de Visual Studio Live Share destinam-se a trabalhar em um cenário diversificado de linguagens e plataformas de aplicativos. No entanto, considerando o número enorme de variações, algumas plataformas e linguagens são mais completas do que outras. Este documento aborda o estado atual conhecido de várias linguagens e plataformas populares para recursos com suporte no momento.

Vê uma linguagem ou plataforma de que precisa? Deseja adicionar um que você não vê? [Vote aqui.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

Todas as linguagens/plataformas têm o mesmo arquivo IntelliSense (quando a respectiva extensão está instalada), bem como o suporte à colorização e à coedição. As listas a seguir abrangem recursos avançados atualmente sem suporte completo e universal:

### <a name="languages"></a>Idiomas

| Idioma | Serviços de linguagem compartilhada | Depuração compartilhada |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *N/A* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *N/A* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *N/A* <sup>4</sup> |
| [Crystal](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *N/A* <sup>4</sup> |
| CSHTML | *N/A* <sup>1</sup> | ✅ |
| CSS | *N/A* | *N/A* |
| Dart | ✅ | ✅ |
| Docker | ✅ | *N/A* |
| Elixir | ✅ | ✅ |
| Elm | ✅ |  *N/A* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *N/A* <sup>4</sup> |
| Fluxo | ✅ |  *N/A* <sup>4</sup> |
| Fortran | ✅ | *N/A* |
| Go | ✅ | ✅ |
| Gradle | ✅ | *N/A* <sup>4</sup> |
|  GraphQL | ✅ | *N/A* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *N/A* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript/TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *N/A* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *N/A* | *N/A* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *N/A* |
| MATLAB |  ✅ | *N/A* <sup>4</sup> |
| Objective-C | ✅ | *N/A* <sup>4</sup> |
| Pascal | ✅ | *N/A* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *N/A* | ✅ |
| Python |  ✅ | ✅ |
| PureScript | ✅ | *N/A* <sup>4</sup> |
| R |  ✅ | *N/A* <sup>4</sup> |
| [Motivo/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *N/A* <sup>4</sup> |
| reStructuredText | ✅ | *N/A* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *N/A* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *N/A* |
| Scala | ✅ | *N/A* <sup>4</sup> |
| Solidity | ✅ | *N/A* <sup>4</sup> |
| SQL/T-SQL | *N/A* | *N/A* <sup>4</sup> |
| [Caneta digitalizadora](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *N/A* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *N/A* <sup>4</sup> |
| Swift | ✅ | *N/A* <sup>4</sup> |
| Terraform | ✅ | *N/A* <sup>4</sup> |
| XML | ✅ | *N/A* <sup>4</sup> |
| YAML | ✅ | *N/A* <sup>4</sup> |

<sup>1</sup> nenhum suporte a cshtml na extensão C#.<br />
<sup>2</sup> o JavaScript inserido em HTML tem suporte ao fazer a depuração do cliente.<br />
<sup>3</sup> depuração de JavaScript/TypeScript para o nó ou navegador.<br />
<sup>4</sup> a respectiva extensão para vs Code atualmente não dá suporte à depuração. Assim que for, investigaremos a adição de suporte de codepuração a ele. <br />

### <a name="platforms"></a>Plataformas

| Tipo de aplicativo/plataforma | Depuração compartilhada | Compartilhamento de aplicativos |
|-------------------|--------------|-------------|
| Arduino | ✅ | *N/A* |
| Serviço de Aplicativo do Azure | ✅ | *N/A* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure Functions (local e remoto) | ✅ | ✅ <sup>1</sup> |
| Blockchain (Ethereum) | ✅ | ✅ <sup>1</sup> |
| Console/CLI | ✅ | ✅ <sup>4</sup> |
| Bancos de dados | <sup>5</sup> | ✅ <sup>1</sup> |
| Área de trabalho (irnativo) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| Jogos (Unity) | ✅ | <sup>9</sup> |
| Jogos (não reais) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *N/A* | ✅<sup>6</sup> |
| Mobile (Cordova) | ✅ | ✅<sup>1, 7</sup> |
| Móvel (nativo) | ✅ | <sup>9</sup> |
| Móvel (reagir nativo) | ✅ | ✅<sup>1, 8</sup> |
| Aplicativo Web/API (back-end) | ✅ | ✅ <sup>1</sup> |
| Aplicativo Web (front-end) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Extensões de VS Code | | <sup>9</sup> |

<sup>1</sup> via [compartilhamento de servidor local](../use/vscode.md#share-a-server).<br />
<sup>2</sup> a depuração ocorre em relação ao navegador do host, e não ao convidado.<br />
<sup>3</sup> ao compartilhar o back-end.<br />
<sup>4</sup> com suporte por meio de terminais compartilhados.<br />
<sup>5</sup> não há suporte para os procedimentos armazenados de banco de dados de depuração no momento <br />
<sup>6</sup> por meio de "visualização". No entanto, as imagens não aparecem devido a um problema conhecido. [Vote ( 👍 ) aqui.](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> aplicativos Cordova podem ser compartilhados por meio da plataforma "navegador"<br />
<sup>8</sup> os aplicativos de reagir nativos podem ser compartilhados por meio de servidores exposição e [compartilhados](../use/vscode.md#share-a-server).<br />
<sup>9</sup> Live share atualmente não dá suporte ao compartilhamento de janelas/telas. [Vote ( 👍 ) aqui.](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

Embora a maioria das linguagens tenha um único suporte a IntelliSense de arquivo, há algumas limitações descritas abaixo. Todas as linguagens/plataformas dão suporte à coedição. O restante da lista cobre recursos avançados, atualmente sem suporte completo e universal:

### <a name="languages"></a>Idiomas

| Idioma | Serviços de linguagem de arquivo único | Serviços de linguagem em todo o projeto | Co-Debugging |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅  <sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *N/A* | <sup>2</sup> |
| CSS | ✅ | *N/A* | *N/A* |
| JavaScript/TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *N/A* | *N/A* |
| PowerShell | ✅ | *N/A* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *N/A* | <sup>4</sup> |
| SQL/T-SQL | ✅ | *N/A* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *N/A* | ✅ |

<sup>1</sup> Gap: cshtml, vbhtml e aspx têm um problema conhecido em relação ao suporte do c#/vb. o código por trás do c#/VB arquivos não são resolvidos porque o IntelliSense completo não está sendo implementado. [Vote ( 👍 ) aqui em cshtml/vbhtml.](https://github.com/MicrosoftDocs/live-share/issues/59) [Vote ( 👍 ) aqui no aspx.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> o JavaScript inserido em HTML tem suporte ao fazer a depuração do cliente.<br />
<sup>3</sup> depuração de JavaScript/TypeScript para o nó ou navegador.<br />
<sup>4</sup> embora a depuração do próprio XAML seja tecnicamente N/A, há suporte para a depuração do code-behind.<br />
<sup>5</sup> Gap: erros do serviço de linguagem R no lado do convidado em junção e após cada nova linha. Não há suporte. [Vote ( 👍 ) aqui.](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>Plataformas

| Tipo de aplicativo/plataforma | Codepuração | Compartilhamento de aplicativo |
|-------------------|--------------|-------------|
| Aplicativo Web/API (back-end) | ✅ | ✅ <sup>1</sup> |
| Aplicativo Web (front-end) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Funções do Azure | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure Dev Spaces](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Bancos de dados | <sup>4</sup> | ✅ <sup>5</sup> |
| Console/CLI | ✅ | ✅<sup>6</sup> |
| Área de trabalho (WinForms) | ✅ | |
| Desktop (WPF) | ✅ | |
| Plataforma Universal do Windows | ✅ |  |
| Extensões do VS | ✅ |  |

<sup>1</sup> via [compartilhamento de servidor local](../use/vs.md#share-a-server). Os aplicativos Web do ASP.NET também podem usar o [compartilhamento automático de aplicativos Web](../use/vs.md#automatic-web-app-sharing).<br />
<sup>2</sup> a depuração ocorre em relação ao navegador do host, e não ao convidado.<br />
<sup>3</sup> ao compartilhar o back-end.<br />
<sup>4</sup> não há suporte para os procedimentos armazenados de banco de dados de depuração no momento <br />
<sup>5</sup> por meio [do servidor local de compartilhamento](../use/vs.md#share-a-server). <br />
<sup>6</sup> com suporte parcial por meio de terminais compartilhados.<br />
<sup>?</sup> Ainda não validado.

## <a name="see-also"></a>Confira também

- [Suporte de extensão](extensions.md)
- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
