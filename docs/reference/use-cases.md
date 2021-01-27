---
title: Casos de uso comuns | Microsoft Docs
description: Uma visão geral dos casos de uso para os quais os desenvolvedores costumam aproveitar Visual Studio Live Share.
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: deda1f483b4c4d9c7f9cf2928dde8c6cf5eea769
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870900"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="common-use-cases"></a>Casos de uso comuns

O objetivo principal do Visual Studio Live Share é permitir que os desenvolvedores colaborem entre si com mais facilidade, sem apresentar qualquer opinião sobre quando e como fazer isso (por exemplo, qual ferramenta de comunicação usar, a metodologia de software "correta" ou o fluxo de trabalho do SCM). Dessa forma, suas ferramentas podem dar suporte a interações que ocorrem **naturalmente** e **com a frequência** necessária, mas de forma a **complementar** como você já prefere trabalhar.

Este documento realça alguns casos de uso que Visual Studio Live Share já está sendo usado para o e descreve como oferecemos suporte a eles, e como planejamos otimizá-los mais detalhadamente (com base nos comentários!). Se você estiver usando Live Share para algo que ainda não esteja coberto abaixo, ou se você considerar que podemos fazer melhor para dar suporte a um caso de uso específico, informe [-nos](https://github.com/MicrosoftDocs/live-share/issues/new).

- [Assistência rápida](#quick-assistance)
    - [Horário comercial](#office-hours)
- [Programação de pares](#pair-programming)
    - [Programação de Mob](#mob-programming)
    - [Competições de codificação/hack-A-thons](#coding-competitions--hack-a-thons)
    - [Projetos de grupo escolar](#school-group-projects)
    - [Streaming do desenvolvedor](#developer-streaming)
    - [Criação de protótipos/projeto](#prototyping--project-inception)
- [Educação interativa](#interactive-education)
    - [Aconselhamento/integração de pares](#peer-mentoring--onboarding)
    - [Bolsas de Brown da equipe](#team-brown-bags)
    - [Palestras em sala de aula](#classroom-lectures)
- [Revisões de código](#code-reviews)
- [Entrevistas técnicas](#technical-interviews)
- [Trabalhando remotamente](#working-remotely)

## <a name="quick-assistance"></a>Assistência rápida

Ao encontrar um problema (por exemplo, tentar resolver um bug, configurar seu ambiente), você pode usar Visual Studio Live Share para buscar instantaneamente assistência de outro ponto. Em muitos casos, não é preciso limpar imediatamente o contexto que a pessoa que fornece ajuda precisará e, portanto, Live Share ajuda simplificando o fornecimento de acesso a todo o seu projeto e se/conforme necessário, compartilhar incrementalmente mais (por exemplo, um servidor local, terminal somente leitura). Não é necessário enviar trechos de código e/ou mensagens de erro de volta e para trás!

Além disso, como Live Share permite que você compartilhe sua sessão de depuração ativa, sem a necessidade de "convidados" instalar qualquer um dos SDKs de plataformas necessários (por exemplo, Node.js, go, .NET Core) ou extensões de ferramentas, ele pode ajudá-lo a obter a resolução mais rapidamente e evitar situações "não reproduzidas em meu computador". Live Share permite compartilhar o estado de depuração com outras pessoas, para qualquer linguagem de programação ou ambiente de tempo de execução (por exemplo, kubernetes, reagir ao aplicativo nativo) e, portanto, independentemente do que você precisa de ajuda, você pode compartilhar!

### <a name="office-hours"></a>Horário de expediente

Muitas empresas e instituições educacionais (por exemplo, escolas, cursos de treinamento online) oferecem suporte a seus clientes/funcionários/alunos em momentos predeterminados e, geralmente, em uma frequência recorrente (por exemplo, toda sexta-feira da 3-5 PM). Dessa forma, "horário do escritório" é simplesmente uma forma agendada de "assistência rápida", em vez de ser totalmente ad hoc. Live Share facilita a obtenção de ajuda rapidamente, já que o "especialista" que fornece ajuda pode entrar imediatamente em uma sessão de colaboração e responder às suas perguntas, sem a necessidade de configurar seu computador.

## <a name="pair-programming"></a>Programação de pares

Um dos cenários mais usados para Visual Studio Live Share é "programação de pares": dois ou mais desenvolvedores, trabalhando juntos em uma tarefa compartilhada, com o objetivo de compartilhar conhecimento, aumentar a coesão da equipe e, potencialmente, a qualidade do produto. A aparência exata da programação de pares pode diferir significativamente entre equipes e situações, dependendo do seguinte (entre outras):

1. O escopo da "tarefa" que está sendo colaborável (por exemplo, um bug, uma história de usuário)

1. A duração esperada da sessão de colaboração (por exemplo, dois minutos, uma hora, tempo integral, uma vez por semana, TBD)

1. O número de pessoas envolvidas (por exemplo, duas, a equipe inteira)

1. A função de cada participante (por exemplo, "driver", observador/revisor, especialista no assunto)

1. A proximidade dos participantes (por exemplo, colocalizado na mesma construção, em todo o mundo)

A Live Share foi projetada para ser independente de todas as preocupações mencionadas anteriormente e, em vez disso, procura oferecer suporte à programação de pares que é completamente "oportunista" e atendeu à sua situação. Dito isso, ao contrário de dois desenvolvedores que compartilham um único teclado e uma tela, Live Share permite uma forma de programação de pares que permite que os desenvolvedores trabalhem em uma meta compartilhada, sem remover suas preferências individuais de autonomia ou ambiente. Você pode trabalhar de forma independente ou em conjunto, permitindo que cada participante traga seu próprio processo de pensamento para a colaboração.

Para interromper esse caso de uso ainda mais, os itens a seguir representam formas de programação de par que observamos pessoas usando Live Share para:

### <a name="mob-programming"></a>Programação de Mob

A [programação Mob](https://en.wikipedia.org/wiki/Mob_programming) (ou a programação Swarm) é basicamente a programação de pares, mas com mais de duas pessoas. Portanto, todos os benefícios de Live Share para a programação de par também se aplicam igualmente. Além disso, algumas equipes fazem "swarming" de acordo com a necessidade (por exemplo, a equipe rallying em uma análise de incêndio) em oposição ao tempo integral.

Atualmente, Live Share dá suporte a até 30 convidados em uma sessão.
> [!TIP]
> Para habilitar 30 convidados em uma sessão:
> - **Vs Code:** adicionar "LiveShare. increasedGuestLimit": "true" para settings.jsem
> - **Vs:** Definir ferramentas > opções > Live Share > maior limite de convidado para "verdadeiro" 

### <a name="coding-competitions--hack-a-thons"></a>Competições de codificação/hack-A-thons

As competições de codificação e os hack-a-thons são efetivamente as variações de tarefa única e de curto prazo da programação de Mob. Os membros da equipe e sua função atual também são potencialmente dinâmicos. Como esse caso de uso normalmente também é sensível ao tempo, a capacidade de colaborar em tempo real sem a necessidade de adotar uma ferramenta totalmente nova, e a capacidade de trabalhar juntas, sem ser restrita a uma única tela ou ao teclado, pode passar por um log para aumentar a velocidade.

Como os participantes nesse ambiente talvez nem sempre sejam totalmente "confiáveis", você pode remover (e bloquear) um convidado de uma sessão a qualquer momento. Isso fornece "hosts" com controle total sobre seu ambiente.

### <a name="school-group-projects"></a>Projetos de grupo escolar

Os projetos de grupo acabam olhando muito como a programação Mob, em que vários alunos estão trabalhando juntos e podem fazer a transição diretamente entre o foco em uma única tarefa ou trabalhar em tarefas separadas simultaneamente. Em vez de simplesmente depender do controle de versão para colaborar de forma assíncrona, eles podem usar Live Share para trabalhar em conjunto em tempo real, o que pode ajudar os benefícios sociais e educacionais de trabalhar em um grupo.

### <a name="developer-streaming"></a>Streaming do desenvolvedor

O streaming do desenvolvedor (via Twitch ou mixer) se tornou uma nova forma atraente de educação. Embora Live Share não se destinar a substituir suas plataformas de difusão (embora tenhamos ouvido a solicitação!), ele fornece um meio para o host emparelhar o programa com um ou mais convidados e, em seguida, transmitir essa interação. Dessa forma, os visualizadores podem potencialmente aprender mais vendo a interação natural e o processo de pensamento de dois ou mais desenvolvedores, que poderiam até mesmo trabalhar juntos em sistemas operacionais e IDEs totalmente separados!

### <a name="prototyping--project-inception"></a>Criação de protótipos/projeto

Quando uma equipe está iniciando um novo projeto/microserviço, ou criando um protótipo/travadondo um novo recurso, muitas vezes pode ser útil colaborar para tornar o progresso rápido e explorar novas ideias. Como a base de código de forma mais recente talvez ainda não esteja confirmada em um repositório compartilhado, Live Share permite que todos participem do processo iterativo, independentemente de estarem no mesmo escritório ou não.

## <a name="interactive-education"></a>Educação interativa

Em termos gerais, Live Share busca ajudar os desenvolvedores a compartilhar conhecimento entre suas equipes. A educação é um caso de uso fundamental para Live Share e dá suporte a isso particularmente bem, permitindo que cada participante interaja com a base de código de colaboração, em vez de simplesmente assistir a uma tela. Todos aprendem de maneiras diferentes e, portanto, ao fornecer independência a um "aluno", eles podem aproveitar a instrução que está sendo fornecida, sem a necessidade de sacrificar sua capacidade de explorar suas próprias ideias ao longo do caminho.

### <a name="peer-mentoring--onboarding"></a>Aconselhamento/integração de pares

Ao introduzir um desenvolvedor para uma nova base de código, área de recursos, tecnologia, etc., você pode usar Live Share para orientá-los no projeto (usando `Follow Mode` ), de modo que eles possam acompanhar você, mas de dentro de seu próprio IDE pessoal. Como Live Share permite que "convidados" naveguem de forma independente o projeto (por exemplo, abrindo um arquivo, executando um `Peek Definition` ), eles podem seguir a permissão, mas também executar explorações rápidas, conforme necessário (por exemplo, "Hmm, o que essa função faz?").

### <a name="team-brown-bags"></a>Bolsas de Brown da equipe

Os pacotes Brown da equipe são efetivamente como o Orientador de pares, mas são apresentados a uma equipe inteira e, potencialmente, mais concentrados na social do conhecimento geralmente útil, em oposição ao suporte à integração e/ou à ajuda com uma tarefa específica.

### <a name="classroom-lectures"></a>Palestras em sala de aula

Quando os instrutores estão ensinando uma lição, eles podem usar Live Share para compartilhar seus projetos com alunos, em vez de simplesmente apresentar a tela. Isso permite que toda a classe acompanhe com o professor, enquanto pode interagir com o projeto por conta própria. Além disso, o professor pode pedir aos alunos individuais para auxiliar na resolução de uma parte específica da lição (por exemplo, "qual método devemos chamar aqui?"), que pode ajudar nos aspectos sociais da classe, sem exigir que os alunos percorram a frente da sala ou até mesmo estejam fisicamente presentes na mesma sala (por exemplo, cursos online).

Para auxiliar nas configurações da sala de aula, Live Share habilita o compartilhamento no modo somente leitura. Os instrutores podem usar o modo somente leitura para permitir que eles compartilhem seus projetos com alunos sem precisar se preocupar com edições desnecessárias ou acidentais sendo feitas.

Além disso, Live Share tem suporte para habilitar até 30 convidados ingressando em uma sessão de colaboração. Dessa forma, os instrutores podem ter sua classe inteira unida em uma sessão e exibir código juntos.

Para habilitar esse recurso:

- **Vs Code:** Adicione "LiveShare. increasedGuestLimit": "true" para settings.js.
- **Vs:** Definir ferramentas > opções > Live Share > maior limite de convidado para "verdadeiro"

Para otimizar totalmente Live Share para esse cenário, precisamos simplificar a maneira como as sessões são iniciadas ([#422](https://github.com/MicrosoftDocs/live-share/issues/422)).

## <a name="code-reviews"></a>Revisões de código

PRs são uma maneira eficiente de colaborar com outras pessoas, mas normalmente representam a conclusão de uma tarefa (excluindo "WIP" PRs) e o desejo de mesclá-las. Muitas vezes, os comentários fornecidos em uma PR poderiam ser facilmente fornecidos anteriormente e, portanto, há um valor potencialmente para que as equipes busquem conselhos de seus colegas de forma fácil e contínua, em vez de esperar até que eles "concluam" uma tarefa a perguntar.

Como Live Share permite que você compartilhe instantaneamente seu projeto com outras pessoas, ele pode ser usado para habilitar revisões de código "informais"/ad-hoc, em que, em vez de pedir ajuda, você está simplesmente procurando entrada para garantir que sua direção e/ou abordagem se alinhe com outras pessoas. Isso pode potencialmente ajudar a PRs subsequentes a concluir e, definitivamente, ajuda a proteger o conhecimento em toda a equipe.

Além disso, como Live Share permite que você compartilhe um diretório arbitrário, você pode usá-lo para executar revisões de código, mesmo que você não esteja usando o controle de versão no momento (embora você deva!) ou se sua equipe não usar PRs (por exemplo, Você faz o desenvolvimento baseado em troncos).

No momento, o Live Share não compartilha diferenças de controle do código-fonte, o que é uma parte crítica do contexto ao usá-lo para revisões de código. Isso está em nosso roteiro, e todos os comentários sobre a prioridade são muito apreciados ([vote 👍 aqui](https://github.com/MicrosoftDocs/live-share/issues/36)).

## <a name="technical-interviews"></a>Entrevistas técnicas

Ao diexibir os candidatos para uma posição de desenvolvedor, muitas vezes pode ser útil ir além das discussões do quadro de comunicações e, em vez disso, observar que resolvem um problema de codificação de dentro de um IDE real (especialmente se a sua equipe/organização tiver "padronizado" em uma ferramenta que você gostaria de vê-los usar). Isso não só oferece a eles o benefício de trabalhar de forma potencialmente mais natural/confortável (a maioria dos desenvolvedores não codificam em quadros de comunicações!), mas também fornece comentários/assistência imediatas enquanto trabalha (por exemplo, erros de compilação, IntelliSense). Muitas vezes, é mais importante entender o processo de pensamento de um candidato, em oposição à sua capacidade de memorizar a sintaxe exata e/ou nomes de API. Dessa forma, Live Share fornece uma experiência semelhante a fazer uma sessão de programação de par, mas permite que o participante esteja em seu próprio ambiente (incluindo as configurações do sistema operacional, como acessibilidade) e também funcionaria igualmente para entrevistas locais ou remotas. Ingressar em uma sessão da Web permite que o candidato use o ambiente de desenvolvimento e a base de código da equipe sem baixar nada. 

Além disso, o desenvolvimento do mundo real é mais do que simplesmente escrever código. Como o Live Share também dá suporte à depuração, às tarefas e aos terminais compartilhados, ele permite aos covisores observar os candidatos ao diagnosticar um problema e fornecer a eles as ferramentas apropriadas necessárias para solucioná-lo (por exemplo, depuração de etapa, executar testes). Como todo o contexto é remoto no computador do host, os candidatos podem rapidamente ir para a "ambiente de entrevista" sem a necessidade de configurar seu computador (além de instalar Live Share). As equipes poderiam manter um repositório de aplicativos de interexibição compartilhados (ou usar sua base de código de produto real), que poderiam ser clonados e compartilhados com candidatos, simplesmente enviando-os à URL da sessão antes de cada entrevista.

## <a name="working-remotely"></a>Trabalhando remotamente

Trabalhe em casa sem precisar manter o ferramentas da sua máquina de desenvolvimento doméstico em sincronia com o seu trabalho. Termine rapidamente essa linha de código de casa sem precisar enviar por push do trabalho, clonar o repositório em casa e encontrar a linha exata em que você estava trabalhando. Conecte-se de um laptop leve ao seu computador de trabalho pesado.

## <a name="see-also"></a>Confira também

- [Suporte de idioma e plataforma](../reference/platform-support.md)
- [Requisitos de conectividade do Live Share](../reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](../reference/security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
