---
title: Suporte a extensões e ecossistema - Visual Studio Live Share | Microsoft Docs
description: Uma visão geral do suporte de extensão para o Visual Studio Live share.
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
ms.openlocfilehash: 57be1ffd58be1a752974d58407adecd0d51fe9f0
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640231"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="extensions-and-ecosystem-support"></a>Ecossistema de suporte e extensões

Uma das principais metas do Visual Studio Live Share é permitir que os desenvolvedores colaborem uns com os outros, com a comodidade de sua favorito, e [ **altamente personalizada** ](https://marketplace.visualstudio.com/) ferramentas. Dessa forma, as interações de ad hoc podem ocorrer com frequência, permanecendo visualmente familiar e ergonômicos, independentemente o que você está ajudando com. Para fazer isso, é essencial que os participantes dentro de uma sessão de colaboração são capazes de continuar a usar qualquer extensão que dão suporte a suas [fluxos de trabalho e preferências pessoais](#user-specific-extensions) (por exemplo, temas de cores/ícones, associações de teclas, editor aperfeiçoadores de produtividade).

Além disso, para tornar o ato de ingressar em uma sessão de colaboração como instantâneas possível, mas permanecendo altamente produtivo, o objetivo do Visual Studio Live Share é habilitar convidados automaticamente aproveitar as ferramentas específicas do projeto que compartilhou seu host. Dessa forma, você pode simplesmente clicar em um link, inicie a ferramenta de escolha e começar a colaborar, sem nenhuma configuração adicional. Para fazer isso, é essencial que extensões, que o núcleo de energia [editar, compilar e depurar o fluxo de trabalho](#project-specific-extensions), são transparentemente "remoto" do host para o convidado, de modo que coisas como preenchimento automático, ir para definição e a depuração " simplesmente funcionem".

Este documento aborda atual conhecido de estado para o ecossistema de extensão grande, bem como um "scorecard" para as metas mencionadas anteriormente. Se você encontrar uma extensão que não atendem a esse critério e é essencial para seu fluxo de trabalho pessoal, em seguida, [Fale conosco!](https://github.com/MicrosoftDocs/live-share/issues/new)

## <a name="user-specific-extensions"></a>Extensões específicas do usuário

Extensões que oferecem suporte a personalizações específicas de usuário **devem** funcionam para o host, e **deve** funcionam para todos os convidados. Se uma extensão não funciona corretamente para o host, que seria uma regressão e provavelmente é um bug no Visual Studio Live Share (por favor [registre um problema](https://github.com/MicrosoftDocs/live-share/issues/new) se você vir um!). Se uma extensão não se comportar conforme o esperado para um convidado, podem exigir [alterações na extensão do próprio](#known-issues), e trabalharemos com o ecossistema de endereço/melhorar esses cenários.

### <a name="visual-studio-code"></a>Visual Studio Code

| Categoria | Exemplos | Suporte para convidado? | Colaboração? |
|-|-|-|-|
| Temas de cores | [Um Pro escuro](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme), [colorizador de saída](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer), [Rainbow cadeia de caracteres](https://marketplace.visualstudio.com/items?itemName=wk-j.vscode-rainbow-string), [coloridos regiões](https://github.com/jmihelcic/colored-regions), [recuado bloco Realce](https://marketplace.visualstudio.com/items?itemName=byi8220.indented-block-highlighting), [ Realce de tarefas pendentes](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight), [colorizador par de colchetes](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) | ✅ | *N/A* |
| Conjuntos de ícones | [ícones de vscode](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons), [ícones clássicos do Visual Studio](https://marketplace.visualstudio.com/items?itemName=jez9999.vsclassic-icon-theme) | ✅ | *N/A* |
| Associações de teclas | [VIM](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim), [IntelliJ IDEA Keybindings](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings), [Emacs amigável de mapa de teclas](https://marketplace.visualstudio.com/items?itemName=lfs.vscode-emacs-friendly) | ✅ | *N/A* |
| Trechos de código | [Trechos de código angular v5](https://marketplace.visualstudio.com/items?itemName=johnpapa.Angular2), [trechos de código HTML](https://marketplace.visualstudio.com/items?itemName=abusaidm.html-snippets), [SVG ícones](https://marketplace.visualstudio.com/items?itemName=idleberg.svg-icons), [cabeçalho de arquivo](https://marketplace.visualstudio.com/items?itemName=mikey.vscode-fileheader) | ✅ | *N/A* <sup>1</sup> |
| Organização | [Sincronização de configurações](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync), [gerente de projeto](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager), [Timeit](https://marketplace.visualstudio.com/items?itemName=smulyono.timeit), [pontos de verificação](https://marketplace.visualstudio.com/items?itemName=micnil.vscode-checkpoints), [TODO analisador](https://marketplace.visualstudio.com/items?itemName=minhthai.vscode-todo-parser), [Favoritos ](https://marketplace.visualstudio.com/items?itemName=kdcro101.favorites) (❌) [indicadores](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) (❌) | ✅ <sup>2</sup> | *N/A* <sup>3</sup> |
| Produtividade | [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens), [renomear automaticamente marca](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag), [da estrutura de tópicos de código](https://github.com/patrys/vscode-code-outline), [realce de cor](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight), [incrementar seleção](https://marketplace.visualstudio.com/items?itemName=albymor.increment-selection), [ Bracketeer](https://marketplace.visualstudio.com/items?itemName=pustelto.bracketeer), [visualização da imagem](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview), [auxiliar JSON](https://marketplace.visualstudio.com/items?itemName=zhoufeng.json-helper) (em foco), [seletor de cores](https://marketplace.visualstudio.com/items?itemName=anseki.vscode-color), [copiar palavra no Cursor](https://marketplace.visualstudio.com/items?itemName=alefragnani.copy-word), [CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics) (CodeLens) [Git coautores](https://github.com/rjimenezda/vscode-coauthor), [JavaScript auxiliares](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster) (CodeActions) [Log de Console Turbo](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log), [ Membro de ir para próximo/anterior](https://marketplace.visualstudio.com/items?itemName=mishkinf.goto-next-previous-member), [rolagem automática](https://github.com/PejmanNik/vscode-autoScroll?files=1), [NPM importação versão](https://marketplace.visualstudio.com/items?itemName=axetroy.vscode-npm-import-package-version) (❌) [importar custo](https://github.com/wix/import-cost) (❌) | ✅ <sup>2</sup> | ❌ <sup>3</sup> |
| REPLs | [Cliente REST](https://marketplace.visualstudio.com/items?itemName=humao.rest-client), [código executor](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner), [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode), [R](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) | ✅ <sup>4</sup> | ❌ <sup>3</sup>  |
| Gerenciadores de recursos | [MSSQL](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql), [ftp simples](https://marketplace.visualstudio.com/items?itemName=humy2833.ftp-simple), [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions), [Docker](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker), [Brew serviços](https://marketplace.visualstudio.com/items?itemName=beauallison.brew-services) | ✅ <sup>5</sup> | ❌ <sup>3</sup>  |

<sup>1</sup> *, a menos que um usuário já estava familiarizado com um trecho de código, eles não esperaria que ele esteja disponível e, portanto, torná-los compartilhado sem necessariamente sentido.*

<sup>2</sup> *essas categorias de extensão são tão diferentes, que é impossível dizer que todos eles funcionam. No entanto, em teoria, eles devem, e vamos rastrear a chave aqueles que não.*

<sup>3</sup> *essas categorias de extensão podem se beneficiar com experiências de colaboração e, portanto, precisamos de comentários do usuário final para saber que!*

<sup>4</sup> *eles requerem que o convidado tem as ferramentas de tempo de execução instaladas (por exemplo, Node. js) e trabalhar com a execução de código localmente.*

<sup>5</sup> *esses funcionam ao se conectar a um servidor de algum tipo e pode trabalhar com qualquer um dos servidores centralizados, os servidores que o convidado compartilhado.*

### <a name="visual-studio"></a>Visual Studio

Em breve.

## <a name="project-specific-extensions"></a>Extensões específicas do projeto

Extensões de host instalado, que suportam o núcleo de edição, criação e depuração de um aplicativo e são específicos para um linguagem/plataforma/biblioteca/SDK, devem ser automaticamente disponíveis para os convidados, sem a necessidade de instalar nada. Dessa forma, a hosts podem configurar seu ambiente para dar suporte a desenvolvimento produtivo de um projeto e permitir que os seus convidados instantaneamente uni-las, sem os pré-requisitos adicionais. Como não são extensões específicas do projeto subjetiva ou pessoal de qualquer forma, eles podem ser determinística, compartilhados do host-para-convidado, sem afetar do qualquer pessoa ambiente familiar.

Além disso, para dar suporte a extensões específicas do projeto que instalou um convidado, mas o host não, o ideal é que elas poderiam fornecer uma experiência degradada, ainda funcional (por exemplo, o intellisense de arquivo único de obtenção, sendo capaz de formatar um documento).

| Categoria | Exemplos | Compartilhado? | Suporte para convidado? |
|-------|----------|--------|-----|
| Gramáticas / realce de sintaxe | [Shell de peixes](https://marketplace.visualstudio.com/items?itemName=TeddyDD.fish), [Nginx](https://marketplace.visualstudio.com/items?itemName=shanoor.vscode-nginx), [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur), [DotEnv](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv), [ES6 cadeia de caracteres HTML](https://marketplace.visualstudio.com/items?itemName=hjb2012.vscode-es6-string-html), [Todo +](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-todo-plus), [Rainbow CSV](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv) | ❌ | ✅ |
| Serviços de linguagem | [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml), [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [ARM](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools) | ✅ <sup>1</sup>| ✅ <sup>2</sup> |
| Esquemas JSON | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions) | ✅ | ✅ |
| Linters | [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint), [Markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint), [código verificador ortográfico](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker), [PHPCS](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs) | ✅ | ✅ <sup>2</sup>  |
| Formatadores | [Mais bonito](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode), [Beautify](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify) | ✅ | ✅ <sup>2</sup> |
| Depuradores | [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python), [depurador para Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) | ✅ <sup>3</sup> | ❌ <sup>4</sup> |
| Executores de teste | [Executor de teste do Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-test), [barra lateral do MOCA](https://marketplace.visualstudio.com/items?itemName=maty.vscode-mocha-sidebar), [Postman executor](https://marketplace.visualstudio.com/items?itemName=eridem.vscode-postman), [Jest executor](https://marketplace.visualstudio.com/items?itemName=firsttris.vscode-jest-runner), [Neptune](https://marketplace.visualstudio.com/items?itemName=LambdaFactory.neptune) | ❌ <sup>5</sup> | ✅ <sup>2</sup> |
| Visualizadores de arquivo personalizado | [Visualização SVG](https://marketplace.visualstudio.com/items?itemName=cssho.vscode-svgviewer), [GraphViz](https://marketplace.visualstudio.com/items?itemName=joaompinto.vscode-graphviz), [tamanho da imagem de Markdown](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-image-size) | ❌ |  ✅ |
| Geradores de arquivo/projeto | [O Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions), [gerador de projeto do C/C++](https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-project-generator) | ❌ | ❌<sup>6</sup> |
| Provedores de controle do código-fonte | [SVN](https://marketplace.visualstudio.com/items?itemName=johnstoncode.svn-scm), [Hg](https://marketplace.visualstudio.com/items?itemName=mrcrowl.hg) | ❌ | ❌ |

<sup>1</sup> *atualmente, apenas C# e JavaScript/TypeScript com mais suporte em breve.*

<sup>2</sup> *só seriam compatíveis com o documento ativo atual, já que os convidados não têm acesso de arquivo local.*

<sup>3</sup> *o núcleo de experiência de depuração é compartilhado, no entanto, todos os servidores iniciados automaticamente não são encaminhados.*

<sup>4</sup> *convidados não tem uma cópia local do aplicativo e, portanto, o aplicativo em execução e todas as sessões de depuração necessário iniciar na máquina do host.*

<sup>5</sup> *a saída de uma execução de teste exige que todos os terminais resultantes, painéis de saída e erros também foram compartilhados com convidados.*

<sup>6</sup> *quase todos eles usaria o Node. js `fs` módulo diretamente para criar arquivos que não funcionaria.*

### <a name="visual-studio"></a>Visual Studio

Em breve.

## <a name="known-issues"></a>Problemas Conhecidos

Estes são problemas conhecidos no momento de extensão, que podem impedir que ele funcionar para convidados dentro do contexto de uma sessão de colaboração (juntamente com suas soluções alternativas) e, portanto, podem afetar seu fluxo de trabalho:

### <a name="visual-studio-code"></a>Visual Studio Code

| Problema | Motivo | Solução alternativa |
|-|-|-|
| Usando o Node. js `fs` módulo detectar/leitura de arquivos (por exemplo, um arquivo de configuração) ou enumerar os diretórios (e você não é um serviço de linguagem). | Os convidados não têm acesso de arquivo local. | 1. Reduzir gradualmente a experiência do usuário *(se possível).*<br /><br />2. Use o `openTextDocument` e `findFiles` APIs para ler e enumerar arquivos de espaço de trabalho. |
| Usando o Node. js `fs` módulo para criar ou gravar arquivos | *Mesmo que acima* | *N/d* você pode usar o `openTextDocument(Uri)` API para criar um `untitled` arquivo, mas você não salvá-lo diretamente para o sistema de arquivos em um caminho específico. |
| Dependendo de uma ferramenta ou biblioteca agrupado por projeto | *Mesmo que acima* | 1. Uma versão de fallback da dependência com a extensão do pacote<br><br> 2. Dar suporte à instalação global desbloquear convidados se ele optarem por instalá-lo explicitamente.<br><br> 3. Remoto estado/ação se possível, como o host teria as dependências à direita disponíveis. |
| Usando o Node. js `fs` módulo para criar um diretório | *Mesmo que acima* | *N/A* |
| Restringindo a funcionalidade para documentos que usam o `file` esquema. | Arquivos em uso do lado do convidado a `vsls` esquema. | Adicionar suporte para `vsls` documentos ([exemplo](https://github.com/CoenraadS/BracketPair/pull/73)) |
| Usando o `Uri.file` método de e/ou `Uri.fsPath` / `TextDocument.fileName` membros para serializar/análise de URIs | *Mesmo que acima* | Use `Uri.parse` e `Url.toString()` em vez disso, que mantêm e respeitar os esquemas de arquivo ([exemplo](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| Usando o `workspace.openTextDocument` método com um caminho de arquivo em vez de um `Uri` | *Mesmo que acima* | Fornecer um `Uri` instância em vez de uma cadeia de caracteres de caminho de arquivo bruto ([exemplo](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| Usando o `workspace.rootPath` propriedade para detectar a presença de um espaço de trabalho | O `workspace.rootPath` chamadas de propriedade `Uri.fsPath` na primeira `workspaceFolder` no `workspace`, que tem o mesmo problema mencionado acima | Use o `workspace.workspaceFolders` propriedade para detectar a presença de um espaço de trabalho em vez disso e, se necessário, examinar cada `workspaceFolder`do `Uri.scheme` para determinar se ele é local ou não |
| Não especificando um esquema de documento ao registrar os serviços de linguagem (via uma `LanguageClient`, ou o `languages.register*` métodos) | Convidados recebem os resultados do serviço de linguagem de suas extensões de locais e o host e, portanto, se ambos os participantes têm a mesma extensão de serviço de linguagem instalada, os convidados verá entradas duplicadas para certas ações (por exemplo, preenchimento automático, código ações) | Restringir os serviços de linguagem apenas `file` e `untitled` esquemas ([exemplo](https://github.com/vuejs/vetur/pull/756/files)) |
| Não marcar um documento `Uri.scheme` antes de preencher um `DiagnosticCollection` para ele | *Mesmo que acima* | Gerar apenas `Diagnostics` para `documents` cuja `Uri.scheme`  ===  `file` ([exemplo](https://github.com/Huachao/vscode-restclient/pull/196)) |
| Não verificando o esquema de espaço de trabalho ao retornar `Tasks` de um personalizado `TaskProvider`  | Convidados exibem todas as tarefas remotas e locais e portanto, seriam exibida duplicatas se ambos os participantes tinham a mesma extensão instalada  | Retornar apenas `Tasks` para `WorkspaceFolder`s cujo `Uri.scheme`  ===  `file` ([exemplo](https://github.com/Microsoft/vscode-eslint/blob/0fdb7c74b093cae9dc08355e7235582a254f24c2/client/src/tasks.ts#L42)) |

### <a name="visual-studio"></a>Visual Studio

Em breve.

<!--

## Extensibility API

In addition to the core goals outlined in the beginning of this document, Live Share also wants to enable extension authors to enhance the default sharing experience in the following ways:

1. Contributing to the core collaborative feature set, based on behavior that only the extension would know about. In these scenarios, the host could have an extension installed, and potentially allow guests to benefit from it without also needing to have it installed

2. Enhancing their own experiences to be collaborative (e.g. syncing bookmarks between participants), by synchronizing any custom state and UI interactions. In these scenarios, only participants that had the custom extension installed would be able to take advantage of the added collaboratively.

This will require some form of API/SDK, which extensions can use to determine if/when the end-user is within a Live Share session, and if so, light up additional capabilities. The following represents a high-level overview of some of the extension points we've identified, and look forward to getting further feedback on:

| Shared Resource | Extensibility Point(s) |
|------------------|---------------------|
| User status | 1. Retrieving the list of participants within the current Live Share session (e.g. the [Git Co-Authors](https://marketplace.visualstudio.com/items?itemName=drrouman.git-coauthors) extension could use that to populate the host's commit message with)<br /><br /> 2. Updating a participant's location (outside of just editors), as well as allowing other participant's to jump to/pin to them as they move into custom extension UI (e.g. a participant is navigating a MongoDB database using the [Azure Cosmos DB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) extension). |
| Workspace | *N/A* - Live Share can transparently share all files, edits, cursors and highlights, without requiring an extension to do anything extra if it modified the file system and/or cursor/highlight position. |
| Language Services | *N/A* - Long-term, Live Share can transparently remote all language services (e.g. go to definition, document formatting, CodeLens) to the guest, including those that are contributed via extensions (e.g. [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)) |
| Debugging Sessions | *N/A* - Live Share can transparently remote all debugging sessions, including those that are enabled by custom extensions (e.g. [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)) |
| Servers | 1. Sharing a server that an extension was responsible for starting, and then optionally specifying whether a browser should be launched on the guest's machine as well (e.g. a debug adapter that launched a web server).  |
| Custom | 1. Synchronizing arbitrary state and/or user interactions (e.g. the [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) extension syncing CRUD operations across participants, the [Maven for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-maven) extension exposing the project-wide view to guests) |

-->

## <a name="see-also"></a>Consulte também

- [Suporte de idioma e plataforma](platform-support.md)
- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
