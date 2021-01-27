---
title: Blocos de anotações-Visual Studio Live Share | Microsoft Docs
description: Informações detalhadas sobre como usar Live Share para colaboração de notebook
ms.date: 01/26/2021
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: simoncal
ms.workload:
- liveshare
ms.openlocfilehash: 2c934e9d2b9f366b7e3c99e59c0a0a06d9ea5cd2
ms.sourcegitcommit: 48c7e4f4f28ef6087a45b268557cc411f96d4c8b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98901825"
---
# <a name="-notebooks"></a>📓 Notebooks

Os notebooks se tornaram uma parte importante do fluxo de trabalho de muitos desenvolvedores e de cientista de dados. Com Visual Studio Code oferecendo um editor de blocos de anotações nativo e avançado, estamos empolgados em habilitar uma experiência de colaboração em tempo real, que permitirá que equipes e salas de aula usem blocos de anotações e Live Share juntos.

A experiência do Live Share notebook está atualmente em versão prévia e, portanto, tem algumas [requisições](#pre-requisites) e [problemas conhecidos](#known-issues) que você deve conhecer. Vamos iterar rapidamente nesta versão de visualização inicial e, portanto, não hesite em [nos enviar perguntas/comentários](http://github.com/microsoftdocs/live-share)) enquanto estiver avaliando 👍<br />

<img width="800px" src="https://user-images.githubusercontent.com/116461/105928037-0d07a680-5ffa-11eb-8447-23bdb77fee9e.png" title="Colaboração do notebook" />

## <a name="pre-requisites"></a>Pré-requisitos

Antes de começar a experimentar os notebooks colaborativos, você precisa instalar os seguintes pré-requisitos como parte desta versão de visualização:

| Pré-requisito | Host-necessário? | Convidado-obrigatório? |
|-|-|-|
| Pessoas do Visual Studio | ✅ | ✅ |
| Live Share v 1.0.3541 + | ✅ | ✅ |
| As extensões de notebook necessárias (por exemplo, Jupyter) | ✅ | _N/A_ (Live share cuida disso!) |

## <a name="getting-started"></a>Introdução

Depois que você e seus participantes tiverem os pré-requisitos apropriados, você poderá começar a usar o Live Share e os blocos de anotações usando as seguintes etapas:

1. Abrir um bloco de anotações no Visual Studio Code
1. Iniciar uma sessão de Live Share
1. Depois que seus convidados ingressarem, você poderá começar a coeditar células e ver os cursores e os realces de texto uns dos outros
1. Divirta-se colaborando com os notebooks! 🎉 

## <a name="known-issues"></a>Problemas conhecidos

A lista a seguir representa o conjunto de problemas conhecidos com a experiência atual do Live Share notebook, juntamente com suas respectivas soluções alternativas: 

| Problema | Solução alternativa | 
|-|-|
| O "modo de acompanhamento" não rastreia a rolagem em um bloco de anotações | Estamos trabalhando no suporte apropriado a "seguir" para notebooks, mas enquanto isso, você precisará rolar manualmente para a célula de notebook à direita que você deseja coeditar com seus participantes. |
| Adicionar/excluir/mover células não é sincronizado entre os participantes | Salve o documento do bloco de anotações e faça com que todos o abram novamente. No futuro, sincronizaremos totalmente as operações em nível de bloco de anotações em tempo real. |
| Os editores de notebook não respeitam sessões de Live Share somente leitura | Embora os convidados possam editar células do bloco de anotações, eles não poderão realmente salvá-las no disco e, portanto, sua segurança será mantida em uma sessão somente leitura. |
