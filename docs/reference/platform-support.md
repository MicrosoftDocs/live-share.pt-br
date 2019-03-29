---
title: Suporte de plataforma e linguagem - Visual Studio Live Share | Microsoft Docs
description: Uma visão geral do suporte de plataforma e linguagem para Visual Studio Live share.
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
ms.openlocfilehash: 91e80df324a0b2f49fdf37a5270cf7b86fca5c7c
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640218"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>Suporte de linguagem e plataforma

Recursos do Visual Studio Live Share destinam-se para funcionar em uma paisagem diversa de linguagens e plataformas de aplicativos. No entanto, dado o número absoluto de variações, algumas plataformas e linguagens são mais completas do que outros. Este documento aborda atual conhecido de estado de um número de linguagens populares e plataformas para os recursos com suporte no momento.

Consulte um idioma ou plataforma que você precisa? Deseja adicioná-lo, que você não vir? [Vote aqui.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

Todos os idiomas / plataformas têm o mesmo intellisense de arquivo (quando a respectiva extensão está instalada), bem como colorização e co-autor de suporte de edição. As listas abaixo aborda avançados recursos atualmente sem suporte completo, universal:

### <a name="languages"></a>Linguagens

| Idioma | Serviços de linguagem compartilhada | Depuração de compartilhado |
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
| DART | ✅ | ✅ |
| Docker | ✅ | *N/A* |
| Elixir | ✅ | ✅ |
| Elm | ✅ |  *N/A* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *N/A* <sup>4</sup> |
| Fluxo | ✅ |  *N/A* <sup>4</sup> |
| Fortran | ✅ | *N/A* |
| Ir | ✅ | ✅ |
| Gradle | ✅ | *N/A* <sup>4</sup> |
| GraphQL | ✅ | *N/A* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *N/A* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript / TypeScript | ✅ | ✅ <sup>3</sup> |
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
| [Razão/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *N/A* <sup>4</sup> |
| reStructuredText | ✅ | *N/A* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *N/A* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *N/A* |
| Scala | ✅ | *N/A* <sup>4</sup> |
| Solidez | ✅ | *N/A* <sup>4</sup> |
| SQL / T-SQL | *N/A* | *N/A* <sup>4</sup> |
| [Caneta](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *N/A* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *N/A* <sup>4</sup> |
| Swift | ✅ | *N/A* <sup>4</sup> |
| Terraform | ✅ | *N/A* <sup>4</sup> |
| XML | ✅ | *N/A* <sup>4</sup> |
| YAML | ✅ | *N/A* <sup>4</sup> |

<sup>1</sup> suporte de nenhum CSHTML em C# extensão.<br />
<sup>2</sup> JavaScript incorporado em HTML é suportado ao fazer a depuração do cliente.<br />
<sup>3</sup> JavaScript / TypeScript depuração para o nó ou navegador.<br />
<sup>4</sup> a extensão do respectiva para VS Code atualmente não dá suporte a depuração. Assim que ele faz, analisaremos a adição de suporte à depuração junto a ele. <br />

### <a name="platforms"></a>Plataformas

| Tipo de aplicativo/plataforma | Depuração de compartilhado | Compartilhamento de aplicativo |
|-------------------|--------------|-------------|
| Arduino | ✅ | *N/A* |
| Serviço de Aplicativo do Azure | ✅ | *N/A* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| O Azure Functions (local e remoto) | ✅ | ✅ <sup>1</sup> |
| Blockchain (Ethereum) | ✅ | ✅ <sup>1</sup> |
| Console / CLI | ✅ | ✅ <sup>4</sup> |
| Bancos de dados | <sup>5</sup> | ✅ <sup>1</sup> |
| Área de trabalho (Electron/nativo) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| Jogos (Unity) | ✅ | <sup>9</sup> |
| Jogos (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *N/A* | ✅ <sup>6</sup> |
| Mobile (Cordova) | ✅ | ✅ <sup>1,7</sup> |
| Mobile (nativo) | ✅ | <sup>9</sup> |
| Mobile (React Native) | ✅ | ✅ <sup>1,8</sup> |
| Aplicativo Web / API (Back-end) | ✅ | ✅ <sup>1</sup> |
| Aplicativo Web (front-end) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Extensões de código do VS | | <sup>9</sup> |

<sup>1</sup> via [servidor de local de compartilhamento](../use/vscode.md#share-a-server).<br />
<sup>2</sup> depuração Ocorre do host navegador em vez de convidado.<br />
<sup>3</sup> compartilhando o back-end.<br />
<sup>4</sup> têm suporte por meio de terminais compartilhados.<br />
<sup>5</sup> depuração de procedimentos armazenado do banco de dados não é suportada atualmente <br />
<sup>6</sup> por meio do "preview". No entanto, imagens não aparecem devido a problema conhecido. [Voto (👍) aqui.](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> aplicativos Cordova podem ser compartilhados por meio da plataforma "navegador"<br />
<sup>8</sup> react Native aplicativos podem ser compartilhados por meio de Expo e [servidores compartilhados](../use/vscode.md#share-a-server).<br />
<sup>9</sup> live Share atualmente não dá suporte a compartilhamento windows/telas. [Voto (👍) aqui.](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

Embora a maioria das linguagens tenha algum suporte ao Intellisense de arquivo único, há algumas limitações descritas abaixo. Todas as linguagens/plataformas suporte à edição de conjunto. O restante da lista aborda recursos avançados atualmente sem suporte completo, universal:

### <a name="languages"></a>Linguagens

| Idioma | Serviços de arquivo único idioma | Serviços de linguagem em todo o projeto | Depuração de co |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅  <sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *N/A* | <sup>2</sup> |
| CSS | ✅ | *N/A* | *N/A* |
| JavaScript / TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *N/A* | *N/A* |
| PowerShell | ✅ | *N/A* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *N/A* | <sup>4</sup> |
| SQL / T-SQL | ✅ | *N/A* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *N/A* | ✅ |

<sup>1</sup> lacuna: ASPX, CSHTML e VBHTML têm um conhecido problemas em torno inserido C#suporte /VB dado de lógica C#/VB arquivos não são resolvidos devido ao intellisense completo não está sendo implementado. [Voto (👍) aqui no CSHTML/VBHTML.](https://github.com/MicrosoftDocs/live-share/issues/59) [Voto (👍) aqui no ASPX.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> JavaScript incorporado em HTML é suportado ao fazer a depuração do cliente.<br />
<sup>3</sup> JavaScript / TypeScript depuração para o nó ou navegador.<br />
<sup>4</sup> que a depuração XAML em si seja tecnicamente n/d, a depuração de lógica tem suporte.<br />
<sup>5</sup> lacuna: Erros de serviço de linguagem de R no lado do convidado em join e após cada nova linha. Sem suporte. [Voto (👍) aqui.](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>Plataformas

| Tipo de aplicativo/plataforma | Codepuração | Compartilhamento de aplicativo |
|-------------------|--------------|-------------|
| Aplicativo Web / API (Back-End) | ✅ | ✅ <sup>1</sup> |
| Aplicativo Web (front-end) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Verificação de | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Espaços de desenvolvimento do Azure](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Bancos de dados | <sup>4</sup> | ✅ <sup>5</sup> |
| Console / CLI | ✅ | ✅ <sup>6</sup> |
| Área de trabalho (WinForms) | ✅ | |
| Área de trabalho (WPF) | ✅ | |
| Plataforma Universal do Windows | ✅ |  |
| Extensões do VS | ✅ |  |

<sup>1</sup> via [servidor de local de compartilhamento](../use/vs.md#share-a-server). Aplicativos Web do ASP.NET também pode usar [compartilhamento de aplicativo na web automática](../use/vs.md#automatic-web-app-sharing).<br />
<sup>2</sup> depuração Ocorre do host navegador em vez de convidado.<br />
<sup>3</sup> compartilhando o back-end.<br />
<sup>4</sup> depuração de procedimentos armazenado do banco de dados não é suportada atualmente <br />
<sup>5</sup> via [servidor de local de compartilhamento](../use/vs.md#share-a-server). <br />
<sup>6</sup> parcialmente com suporte via terminais compartilhados.<br />
<sup>?</sup> Ainda não foram validados.

## <a name="see-also"></a>Consulte também

- [Suporte de extensão](extensions.md)
- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
