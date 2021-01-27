---
title: PERGUNTAS FREQUENTES | Microsoft Docs
description: Perguntas frequentes sobre Visual Studio Live Share.
ms.custom: ''
ms.date: 05/05/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 3da327261766ea0aea7ed167059c864100d25da0
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870482"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>Perguntas frequentes

## <a name="what-is-live-share"></a>O que é Live Share?
O Live Share permite que você edite e depure de forma colaborativa com outras pessoas em tempo real, sejam quais forem as linguagens de programação usadas ou os tipos de aplicativo criados. Ele permite que você compartilhe instantaneamente (e com segurança) seu projeto atual e, em seguida, conforme necessário, compartilhe sessões de depuração, instâncias de terminal, aplicativos Web de localhost e muito mais! Os desenvolvedores que ingressam em suas sessões recebem todo o contexto do editor do seu ambiente (por exemplo, serviços de linguagem, depuração), o que garante que eles possam começar a colaborar de forma produtiva imediatamente, sem a necessidade de clonar qualquer repositórios ou instalar SDKs.

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>Quais são os requisitos de ferramentas para usar o Live Share?
Os [principais recursos](#what-are-the-core-capabilities-of-live-share) do Live share são totalmente suportados nas seguintes ferramentas:

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [Visual Studio 2017 (15.6 +)](https://visualstudio.microsoft.com/vs/older-downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)

Iteramos rapidamente para responder aos comentários do usuário. Isso exige que possamos aproveitar os recursos do Visual Studio e Visual Studio Code que estão disponíveis apenas em suas respectivas versões Preview/Insider. Indicaremos quais recursos exigem versões mais recentes do VS ou VS Code na documentação. Por exemplo, o suporte local para desfazer/refazer requer o Visual Studio 2017 15.7 +.

## <a name="what-are-the-core-capabilities-of-live-share"></a>Quais são os principais recursos do Live Share?
Live Share permite que você compartilhe sua base de código com os membros da equipe por meio de uma conexão segura. Com o Live Share, você pode editar vários arquivos de forma colaborativa em um espaço de trabalho e, mais importante, depurar seu aplicativo com seus colegas de equipe. Durante a coedição, suas edições são vistas imediatamente por seus colegas de equipe. Durante a codepuração, você está compartilhando a mesma sessão de depuração do seu aplicativo. Isso significa que você e seus colegas de equipe podem controlar a execução do programa com pontos de interrupção e etapas, mas você pode inspecionar de forma independente variáveis, inspeções, locais e REPLs (por exemplo, a janela imediata no Visual Studio).

Live Share tem uma ampla variedade de casos de uso, como: investigar um bug juntos, mostrando um problema que não será reproduzido na máquina de outra pessoa, resolvendo problemas de design, emparelhar a programação, conduzir uma entrevista de codificação, orientar outros membros de uma equipe ou executar revisões de código ad hoc.

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>Usando Live Share, meu código é armazenado em um servidor Microsoft?
Não, o código compartilhado reside exclusivamente no computador do desenvolvedor que iniciou o compartilhamento. Ele não é armazenado nem carregado na nuvem de forma alguma. Em vez disso, Live Share simplesmente estabelece uma conexão segura entre você e seus colegas de equipe (que é criptografado de ponta a ponta) e não inspeciona nem coleta nenhum dado no código compartilhado.

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>Esse modelo baseado em remoto funciona em qualquer lugar? Ele é ponto a ponto?
O único requisito de Live Share é que o compartilhamento de pessoas e sua equipe tenham acesso à Internet. A comunicação segura entre os membros da equipe durante uma sessão de colaboração é facilitada por uma retransmissão do Azure. Seu espaço de trabalho (ou seja, arquivos de origem) não é armazenado na nuvem. Nenhuma conexão ponto a ponto especial é necessária, embora uma delas possa ser usada para reduzir a latência. Consulte [alterando o modo de conexão](https://aka.ms/vsls-docs/connection-mode) em nossos documentos para obter detalhes adicionais.

## <a name="what-is-shared-during-a-live-share-session"></a>O que é compartilhado durante uma sessão de Live Share?
Live Share não transfere todas as entradas de teclado e mouse. Ele só comunica os dados necessários para cada atividade de colaboração nos computadores dos seus colegas. Por exemplo, quando você compartilha seu espaço de trabalho, sua estrutura de pastas é compartilhada. Quando você edita um arquivo de forma colaborativa, o conteúdo desse arquivo é compartilhado. Quando você está depurando a depuração colaborativa, ações de depuração (por exemplo, depuração) e estado (por exemplo, pilha de chamadas e locais) são compartilhadas.

## <a name="when-will-live-share-be-released"></a>Quando Live Share será lançado?
Live Share agora está disponível para o público geral! Você pode começar a usar o [Live share](https://aka.ms/vsls-start) hoje mesmo.

## <a name="how-much-will-it-cost"></a>Quanto isso custará?
Estamos comprometidos com uma camada gratuita de Visual Studio Live Share para que os desenvolvedores usem em uma base contínua. Avaliaremos a introdução de camadas pagas com recursos avançados, já que entendemos melhor as necessidades da Comunidade.

## <a name="how-is-my-code-shared-with-other-teammates"></a>Como meu código é compartilhado com outros colegas de equipe?
Ao usar o Live Share, você está disponibilizando o código que está trabalhando, de modo que seus colegas de equipe possam acessá-lo por meio de um serviço de nuvem seguro que Remotae os comandos do seu editor. Seus colegas de equipe podem abrir e editar os arquivos sem precisar armazená-los na nuvem ou armazená-los permanentemente no computador de sua equipe.

Live Share permite o acesso instantâneo a recursos como a árvore do projeto, a navegação de código e a pesquisa. Ele também permite que seus colegas de equipe se beneficiem de aprimoramentos do editor, como o IntelliSense.

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>O que acontece se um usuário ficar offline ou parar de compartilhar?
O modelo remoto requer que o compartilhamento do desenvolvedor via Live Share e seu colega de equipe estejam online para serem conectados. Se seu colega de equipe tentar usar Live Share quando você estiver offline, ele não poderá ingressar na sessão até que você esteja online novamente. Além disso, quando a colaboração for interrompida (por exemplo, você fechar o editor, ficar offline ou parar de compartilhar), outras ações ou o acesso ao arquivo por seus colegas serão imediatamente desabilitados.

## <a name="what-about-screen-sharing"></a>E o compartilhamento de tela?
Live Share permite que você compartilhe o código do projeto e seu contexto. Isso significa que sua equipe de trabalho pode facilmente acessar sua base de código e trabalhar com você, usando sua ferramenta familiar. Seu editor ou outros aplicativos não são compartilhados ou exibíveis por sua equipe e você não precisa alterar seu conjunto de trabalho nem usar um aplicativo baseado na Web.

Live Share não substitui o compartilhamento de tela onde você talvez queira mostrar um item de menu ou discutir aspectos visuais de seu aplicativo ou seu editor. Em vez disso, você tem a opção de usar Live Share junto com o bate-papo, voz, vídeo e compartilhamento de tela.

## <a name="what-about-other-collaboration-tools"></a>E quanto a outras ferramentas de colaboração?
Live Share pode ser usado com chat, mensagens instantâneas ou tecnologias de email. Observamos que muitas interações colaborativas entre os desenvolvedores começam nessas ferramentas. No entanto, quando a discussão se trata de código, elas costumam chegar a um ponto em que é simplesmente muito difícil explicar um problema com texto, trechos de código ou arquivos únicos-mais contexto é necessário.

Live Share pode ser usado para muitas coisas, como: procurar ajuda em um problema, resolver um bug, programar a programação, conduzir uma entrevista de codificação ou executar uma revisão ad hoc antes de uma confirmação de código ou uma solicitação de pull.

## <a name="what-about-other-web-editors"></a>E quanto a outros editores da Web?
Com os editores baseados na Web, ambos os colegas de equipe precisam usar o mesmo aplicativo Web para obter benefícios colaborativos, o que pode não ser o editor principal, dia a dia. Muitos editores baseados na Web pressupõem que você esteja criando e implantando em uma máquina virtual geralmente hospedada em um ambiente de nuvem.

Embora isso possa ser desejável para muitos cenários, os desenvolvedores geralmente desejam colaborar em aplicativos que não são hospedados em uma VM ou na nuvem.  Com o Live Share, você e seu colega de equipe podem usar os recursos do ecossistema das ferramentas, além dos mesmos recursos disponíveis em editores baseados na Web.

Live Share vai um passo além e permite que você compartilhe uma sessão de depuração.  Isso o torna especialmente útil na inscrição de outras pessoas para ajudá-lo a rastrear problemas que ocorrem apenas em seu computador sem alterar o fluxo de trabalho de desenvolvimento ou precisar alterar o design do aplicativo.

## <a name="which-languages-and-platforms-will-be-supported"></a>Quais idiomas e plataformas terão suporte?
Nosso objetivo é dar suporte ao Panorama variado de linguagens e plataformas, para garantir que possamos habilitar a colaboração avançada, independentemente do tipo de aplicativo que está sendo desenvolvido. Consulte o artigo [suporte a idiomas e plataformas](reference/platform-support.md) para obter detalhes sobre o que funciona hoje.

## <a name="how-many-developers-can-join-a-collaboration-session"></a>Quantos desenvolvedores podem ingressar em uma sessão de colaboração?
Atualmente, damos suporte a 30 convidados simultâneos, além do desenvolvedor que está compartilhando ("hospedando") seu projeto. 

## <a name="what-is-the-roadmap"></a>O que é o roteiro?
Você pode exibir o conjunto de problemas conhecidos e itens de roteiro [aqui](https://aka.ms/vsls-issues). Se você quiser ver apenas as solicitações de recursos em vez de todos os problemas, consulte [aqui](https://aka.ms/vsls-feature-requests). Incentivamos você a votar itens existentes, arquivos de novas solicitações de recursos e relatórios de bugs de log, para nos ajudar a moldar a direção do produto avançando.

## <a name="see-also"></a>Confira também

- [Suporte de idioma e plataforma](platform-support.md)
- [Requisitos de conectividade do Live Share](reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](reference/security.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](troubleshooting.md) ou [envie comentários](support.md).
