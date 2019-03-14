---
title: Casos de uso comuns - compartilhamento ao vivo do Visual Studio | Microsoft Docs
description: Uma visão geral dos casos de uso que os desenvolvedores normalmente estão utilizando o Visual Studio Live Share para.
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 2ef982a00a06cb312cd0270ba65abd308518d99e
ms.sourcegitcommit: c20a6ddef4f184678a2d6cf1a2493d42ea3a4356
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2019
ms.locfileid: "57725695"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="common-use-cases"></a>Casos de uso comuns

O objetivo principal do Visual Studio Live Share é permitir que os desenvolvedores colaborem uns com os outros mais facilmente, sem introduzir qualquer opinião sobre quando e como fazê-lo (por exemplo, qual ferramenta de comunicação usar, a metodologia de software "certo" ou o fluxo de trabalho do SCM). Dessa forma, suas ferramentas podem dar suporte a interações que ocorrem **naturalmente**e como **frequentemente*conforme necessário, mas de uma maneira que **cumprimentos*como já você preferir trabalhar.

Este destaques do documento alguns casos que já está sendo usado para Visual Studio Live Share e descreve quão bem suportamos-los e maneiras planejamos para otimizá-los ainda mais (com base no feedback!) de uso. Se você estiver usando o Live Share para algo que já não é abordado abaixo, ou você acha que podemos fazer melhor para dar suporte a um caso de uso específico, por favor [Fale conosco](https://github.com/MicrosoftDocs/live-share/issues/new).

- [Assistência rápida](#quick-assistance)
    - [Horário de expediente](#office-hours)
- [Programação de par](#pair-programming)
    - [Programação MOB](#mob-programming)
    - [Competições de codificação / Hack-A-Thons](#coding-competitions--hack-a-thons)
    - [Projetos do grupo de escola](#school-group-projects)
    - [Desenvolvedor de Streaming](#developer-streaming)
    - [Criação de protótipos / concepção do projeto](#prototyping--project-inception)
- [Treinamento interativo](#interactive-education)
    - [Par aconselhamento / integração](#peer-mentoring--onboarding)
    - [Falas de equipe](#team-brown-bags)
    - [Palestras em sala de aula](#classroom-lectures)
- [Revisões de código](#code-reviews)
- [Entrevistas técnicas](#technical-interviews)

## <a name="quick-assistance"></a>Assistência rápida

Quando você tiver um problema (por exemplo, tentando resolver um bug, configurar seu ambiente), você pode usar o Visual Studio Live Share instantaneamente buscar assistência de outra máquina. Em muitos casos, não é imediatamente claro que a pessoa fornecendo ajuda precisará de contexto e, portanto, ajuda Live Share, tornando simples para fornecer acesso a todo o projeto e if/como necessário incrementalmente compartilhar mais (por exemplo, um servidor local, somente leitura Terminal). Não há necessidade de enviar trechos de código e/ou mensagens de erro back bidirecional!

Além disso, uma vez que o Live Share permite que você compartilhe sua sessão de depuração ativa, sem exigir "convidados" instalar qualquer um dos SDKs plataformas necessário (por exemplo, Node. js, Go, .NET Core) ou as ferramentas de extensões, ele pode ajudar você obter resolução mais rápida e evitar a "não situações de reprodução no meu computador". Compartilhamento ao vivo permite que você compartilhar o estado de depuração com outras pessoas, para qualquer idioma ou tempo de execução do ambiente de programação (por exemplo, Kubernetes, aplicativo React Native) e independentemente que você precisa de Ajuda, você pode compartilhá-lo!

### <a name="office-hours"></a>Horário de expediente

Muitas empresas e instituições educacionais (por exemplo, escolas, cursos de treinamento online) dão suporte para os clientes/funcionários/alunos em determinados previamente vezes e, em geral, em uma frequência recorrente (por exemplo, toda sexta-feira de 3-5 PM). Dessa forma, o "expediente" é simplesmente uma forma agendada de "assistência rápida," em vez de ser inteiramente ad-hoc. Compartilhamento ao vivo facilita obter ajuda com rapidez, desde que a "especialista" Ajuda fornecendo imediatamente pode ingressar em uma sessão de colaboração e responder às suas perguntas, sem a necessidade de configuração do seu computador em todos os.

## <a name="pair-programming"></a>Programação de par

Um dos mais comumente usado cenários para Visual Studio Live Share é "programação de par": dois ou mais desenvolvedores, trabalhando juntos em uma tarefa compartilhada, com o objetivo de compartilhamento de dados de Conhecimento, aumentar a coesão da equipe e, potencialmente, a qualidade do produto. A exata aparência e funcionalidade de programação de par pode diferir significativamente entre equipes e situações, dependendo do seguinte (entre outros):

1. O escopo de "tarefas" que está sendo colaboraram em (por exemplo, um bug, uma história de usuário)

1. A duração esperada da sessão de colaboração (por exemplo, dois minutos, uma hora, em tempo integral, uma vez por semana, TBD)

1. O número de pessoas envolvidas (por exemplo, duas, toda a equipe)

1. A função de cada participante (por exemplo, "driver", observador/revisor, especialista no assunto)

1. A proximidade de participantes (por exemplo, colocalizado na mesma compilação, em todo o mundo)

Compartilhamento ao vivo foi projetado para ser independente de todas as preocupações mencionado anteriormente e, em vez disso, se esforça para dar suporte à programação de par que está completamente "oportunista" e fornecido para sua situação. Dito isso, ao contrário de dois desenvolvedores compartilhando um único teclado e tela, Live Share permite que um formulário de programação de par que permite aos desenvolvedores trabalhar em uma meta compartilhada, sem remover seus autonomia individual ou preferências de ambiente. Você pode trabalhar de forma independente ou em conjunto, permitindo que cada participante trazer suas próprias o processo pensado para a colaboração.

Para dar suporte à programação de par e permitem que cada "convidado" executar ações exigidas normalmente, temos trabalho em nosso roteiro para continuar aumentando o contexto e os recursos que são compartilhados em uma sessão do Live Share: tarefas ([40 #](https://github.com/MicrosoftDocs/live-share/issues/40)), saída de compilação ([#48](https://github.com/MicrosoftDocs/live-share/issues/48)), depuração controlada por convidado ([#32](https://github.com/MicrosoftDocs/live-share/issues/32)) e muito mais. Queremos sabe que uma dessas experiências são importantes para você!

Para dividir esse caso de uso ainda mais, os itens a seguir representam os formulários de par de programação que observamos as pessoas que usam o compartilhamento ao vivo para:

### <a name="mob-programming"></a>Programação MOB

[MOB programação](https://en.wikipedia.org/wiki/Mob_programming) (ou swarm programação) é, essencialmente, o par de programação, mas com mais de duas pessoas. Portanto, todos os benefícios do Live Share para programação de par se aplicam igualmente bem. Além disso, algumas equipes fazer "swarming" em uma base conforme necessário (por exemplo, a equipe rallying em torno de uma simulação de incêndio) em vez de em tempo integral.

Atualmente, o Live Share dá suporte a até cinco convidados dentro de uma sessão, que pode ou não pode acomodar o tamanho da sua equipe. No entanto, isso é algo que podemos planejar o aumento (para vários casos de uso) e à procura de feedback ([voto 👍 aqui](https://github.com/MicrosoftDocs/live-share/issues/229))

### <a name="coding-competitions--hack-a-thons"></a>Competições de codificação / Hack-A-Thons

Codificação competições e hack um thons são variações de curto prazo com eficiência, a única tarefa de programação mob. Os membros da equipe e sua função atual, também são potencialmente dinâmicos. Como esse caso de uso normalmente também é sensível ao tempo, a capacidade de colaborar em tempo real sem a necessidade de adotar uma ferramenta completamente nova e a capacidade de trabalhar em conjunto, sem ficar limitado a uma única tela ou o teclado, pode ir uma maneira de log em crescente velocidade.

Uma vez que os participantes nesse ambiente podem não ser sempre totalmente "confiáveis", ouvimos as solicitações para permitir removendo (e de bloqueio) um convidado de uma sessão a qualquer momento, o que é algo que planejamos habilitar ([398 #](https://github.com/MicrosoftDocs/live-share/issues/398)) e dá suporte a o objetivo de fornecer "hosts" com controle completo sobre seu ambiente.

### <a name="school-group-projects"></a>Projetos do grupo de escola

Grupo de projetos acaba ficando muito parecido com a questão de programação, em que vários alunos estão trabalhando juntas e pode transição perfeitamente entre concentrando-se em uma única tarefa ou trabalhando em tarefas separadas simultaneamente. Em vez de simplesmente contar com controle de versão para colaborar de forma assíncrona, eles podem usar o Live Share para trabalharem juntos em tempo real, que pode ajudar os benefícios sociais e educacionais de trabalhar em um grupo.

### <a name="developer-streaming"></a>Desenvolvedor de Streaming

Desenvolvedor de streaming (via Twitch ou Mixer) tornou-se um novo formulário atraente de educação. Enquanto o Live Share não se destina a substituir suas plataformas de difusão (embora já ouvimos a solicitação!), ela fornece um meio para o host de par de programa com um ou mais convidados e, em seguida, transmitir essa interação. Dessa forma, os visualizadores potencialmente Saiba mais, vendo a interação natural e o processo pensado de dois ou mais desenvolvedores, que até mesmo poderia estar trabalhando em sistemas de operacionais totalmente separados e IDEs!

### <a name="prototyping--project-inception"></a>Criação de protótipos / concepção do projeto

Quando uma equipe está iniciando um novo projeto/microsserviço ou um novo recurso de criação de protótipos/picos, muitas vezes pode ser útil colaborar em conjunto para tornar o progresso da rápida e explorar novas ideias. Uma vez que a base de código recentemente ao pode não ser confirmados para um repositório compartilhado, Live Share permite que todos participem do processo iterativo, independentemente se eles forem da mesma filial ou não.

## <a name="interactive-education"></a>Treinamento interativo

Em termos gerais, o Live Share buscas ajudar os desenvolvedores a compartilhar conhecimento entre a sua equipe. Educação é um caso de uso fundamentais para Live Share e ele dá suporte a isso especialmente bem permitindo que cada participante interagir com a base de código que está sendo colaboraram em, em vez de simplesmente assistindo a uma tela. Cada um aprende de maneiras diferentes de sutileza e, portanto, fornecendo independência para "aluno", eles são capazes de tirar vantagem da instrução de dado, sem precisar sacrificar a capacidade de explorar suas próprias ideias ao longo do caminho.

### <a name="peer-mentoring--onboarding"></a>Par aconselhamento / integração

Ao introduzir um desenvolvedor para uma nova base de código, recursos de área, tecnologia, etc. você pode usar o Live Share para orientá-los por meio do projeto (usando `Follow Mode`), de modo que eles podem seguir junto com você, mas dentro de seu próprio IDE pessoal. Uma vez que o Live Share permite "convidados" navegar independentemente do projeto (por exemplo, a abertura de um arquivo, a execução de um `Peek Definition`), eles podem seguir permitir, mas também executar explorações rápidas conforme necessário (por exemplo, "Hmm, o que faz essa função?").

### <a name="team-brown-bags"></a>Falas de equipe

Recipientes de equipe marrom são efetivamente como aconselhamento de mesmo nível, mas apresentado para toda a equipe e muito mais voltada para comunicar dados de conhecimento geralmente útil, potencialmente, em vez de ambientação dar suporte a e/ou ajudando com uma tarefa específica.

### <a name="classroom-lectures"></a>Palestras em sala de aula

Quando o instrutor está ensinando uma lição, eles podem usar o Live Share para compartilhar seu projeto com os alunos, em vez de simplesmente apresentando sua tela. Isso permite que a classe inteira acompanhar o professor, sendo capaz de interagir com o projeto por conta própria. Além disso, o professor pode pedir aos alunos individuais para auxiliar na solução de uma parte específica da lição (por exemplo "Qual método devemos chamar aqui?"), que pode ajudar a nos aspectos sociais da classe, sem exigir que os alunos a movimentar-se para a frente da sala ou até mesmo estar fisicamente presente na mesma sala (por exemplo, os cursos online).

Para auxiliar nas configurações de sala de aula, o Live Share permite o compartilhamento no modo somente leitura. Os instrutores podem usar modo somente leitura para que eles possam compartilhar seus projetos com os alunos sem precisar se preocupar sobre edições acidentais ou desnecessárias que estão sendo feitas.

Além disso, o Live Share tem suporte experimental para habilitar o ingresso em uma sessão de colaboração de convidados até 30. Dessa forma, os instrutores podem ter sua classe inteira ingressar em uma sessão e exibir o código juntos.

Para habilitar esse recurso experimental:

- **VS Code:** Adicione "liveshare.features":"experimental" para o Settings.
- **VS:** Conjunto de ferramentas > Opções > Live Share > recursos para "Experimental"

Para otimizar totalmente Live Share para esse cenário, é preciso aumentar ainda mais o limite atual de convidado ([#229](https://github.com/MicrosoftDocs/live-share/issues/229)) e simplificar a forma que as sessões são iniciadas ([#422](https://github.com/MicrosoftDocs/live-share/issues/422)).

## <a name="code-reviews"></a>Revisões de código

Solicitações de pull são uma maneira eficiente para colaborar com outras pessoas, mas geralmente representam a conclusão de uma tarefa (excluindo as solicitações de pull "WIP") e o desejo de mesclados-o no. Muitas vezes, os comentários que são fornecidos em uma solicitação pull poderiam facilmente ter sido fornecido anteriormente e, portanto, há potencialmente valor para as equipes buscar o conselho de seus colegas, em vez de esperar até que eles "Concluir" para solicitar uma tarefa fácil e continuamente.

Como o Live Share permite que você compartilhe instantaneamente seu projeto com outras pessoas, ele pode ser usado para habilitar "informal" / ad-hoc revisões de código, onde, em vez de pedir ajuda, você está simplesmente procurando entrada para garantir que sua direção e/ou abordagem alinha-se com outras pessoas. Isso pode ajudar subsequentes PRs concluídos mais rapidamente e definitivamente ajuda a se socializar conhecimento entre a equipe.

Além disso, como Live Share permite que você compartilhe um diretório arbitrário, você pode usá-lo para executar revisões de código, mesmo se você atualmente não estiver usando o controle de versão (embora você deve!), ou se sua equipe não usar solicitações pull (ex.: Para fazer desenvolvimento com base em tronco).

Compartilhamento ao vivo atualmente não compartilha comparações de controle do código-fonte, que é uma parte crítica do contexto de quando usá-lo para revisões de código. Isso está em nosso roteiro e quaisquer comentários na prioridade são muito bem-vindos ([voto 👍 aqui](https://github.com/MicrosoftDocs/live-share/issues/36)).

## <a name="technical-interviews"></a>Entrevistas técnicas

Ao entrevistar candidatos para uma posição de desenvolvedor, muitas vezes pode ser útil ir além do quadro de comunicações discussões e, em vez disso, observe-os para solucionar um problema de codificação de um IDE real (especialmente se sua organização/equipe "padronizou" uma ferramenta que Você gostaria para vê-los a usar). Isso não só oferece a vantagem de trabalhar de forma que é potencialmente mais natural/confortável (a maioria dos desenvolvedores não código em quadros de comunicações!), mas também fornece comentários imediata/assistência durante o trabalho (por exemplo, erros, intellisense de compilação). Muitas vezes, é mais importante entender o processo de pensamento de um candidato, em vez de sua capacidade de memorizar a sintaxe exata e/ou nomes de API. Dessa forma, o Live Share fornece uma experiência que é similar ao fazer um par de programação de sessão, mas permite que o participante de estar em seu próprio ambiente (incluindo configurações do sistema operacional, como acessibilidade) e funciona igualmente bem para entrevistas locais ou remotas.

Além disso, o desenvolvimento no mundo real é mais do que simplesmente escrever código. Como o Live Share também suporta compartilhado de depuração, tarefas e terminais, ele permite que os entrevistadores observar os candidatos ao diagnosticar um problema e forneça as ferramentas apropriadas necessárias para resolvê-lo (por exemplo, etapa depurar, executar testes). Uma vez que todo o contexto é remota na máquina do host, candidatos podem ir rapidamente para o ambiente"entrevista" sem a necessidade de configuração do seu computador (além da instalação Live Share). As equipes poderiam, em seguida, mantenha um repositório de compartilhado entrevistando aplicativos (ou use sua base de código do produto real), que pode ser clonado e compartilhado com candidatos, simplesmente enviando a URL de sessão antes de cada entrevista.

## <a name="see-also"></a>Consulte também

- [Suporte de idioma e plataforma](platform-support.md)
- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)
- [Todos os bugs importantes, solicitações de recursos e limitações](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
