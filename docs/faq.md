---
title: Perguntas Frequentes - compartilhamento ao vivo do Visual Studio | Microsoft Docs
description: Perguntas frequentes sobre o Visual Studio Live Share.
ms.custom: ''
ms.date: 05/05/2018
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
ms.openlocfilehash: 7e9151d513127fa46c3936b359afd0127e4a5fca
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255235"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>Perguntas frequentes

## <a name="what-is-live-share"></a>O que é o compartilhamento ao vivo?
Compartilhamento ao vivo permite aos desenvolvedores compartilhar uma base de código e seu contexto para que você obtenha uma colaboração instantânea e bidirecional, diretamente de suas ferramentas existentes (Visual Studio 2017 ou Visual Studio Code). Com o Live Share, seu colega de equipe pode ler, navegar, editar e depurar o projeto que você compartilhou com eles, diretamente e com segurança.

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>Quais são os requisitos de ferramentas para usar o Live Share?
O [principais recursos](#what-are-the-core-capabilities-of-live-share) do Live Share têm suporte total nas seguintes ferramentas:

* [Visual Studio 2017 (15.6 +)](https://visualstudio.microsoft.com/vs/)
* [Visual Studio Code](https://code.visualstudio.com/)

Durante a visualização, Live Share irá iterar rapidamente para responder aos comentários do usuário, que podem exigir a tirar proveito dos recursos dentro do Visual Studio e Visual Studio Code que só são estar disponíveis em suas versões de visualização/insider respectivo. Indicaremos quais recursos exigem versões mais recentes do VS ou VS Code na documentação. Por exemplo, o suporte de desfazer/refazer local requer o Visual Studio 2017 15.7 +.

## <a name="what-are-the-core-capabilities-of-live-share"></a>Quais são os principais recursos do Live Share?
Compartilhamento ao vivo permite que você compartilhe sua base de código com os membros da equipe por meio de uma conexão segura. Com o Live Share, você é capaz de forma colaborativa editar vários arquivos em um espaço de trabalho e mais importante é que depurar seu aplicativo com seus colegas de equipe. Durante a edição conjunta suas edições imediatamente são vistas por seus colegas de equipe. Durante a depuração conjunta você está compartilhando a mesma sessão de depuração do seu aplicativo. Isso significa que você e seus colegas de equipe podem controlar a execução do programa com pontos de interrupção e etapas, mas você pode inspecionar independentemente variáveis, inspeções, locais e REPLs (por exemplo, a janela imediata no Visual Studio).

Compartilhamento ao vivo tem uma ampla variedade de casos de uso, como: investigando um bug, juntas, mostrando um problema que não a reprodução na máquina de outra pessoa, resolvendo design emite, par de programação, realizando uma entrevista de codificação, aconselhamento outros membros em uma equipe ou executar revisão de código ad hoc.

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>Usando o Live Share, é meu código armazenado em um servidor da Microsoft?
Não, o código compartilhado reside somente no computador do desenvolvedor que iniciou o compartilhamento. Ele não é armazenado ou carregado para a nuvem de forma alguma. Em vez disso, Live Share simplesmente estabelece uma conexão segura entre você e seus colegas de equipe (que é criptografada ponta a ponta) e não inspecionar ou coletar todos os dados sobre o código que é compartilhado.

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>Esse modelo baseado em remoto funciona em qualquer lugar? É ponto a ponto?
Único requisito ao vivo do compartilhamento é que a pessoa de compartilhamento e seu colega de equipe tenham acesso à internet. Comunicação segura entre os membros da equipe durante uma sessão de colaboração é facilitada por uma retransmissão do Azure. Seu espaço de trabalho (ou seja, arquivos de origem) não é armazenado na nuvem. Nenhuma conexão peer-to-peer especial é necessária, embora um pode ser usado para reduzir a latência. Ver [alterando o modo de conexão](https://aka.ms/vsls-docs/connection-mode) em nossos documentos para obter mais detalhes.

## <a name="what-is-shared-during-a-live-share-session"></a>O que é compartilhado durante uma sessão do Live Share?
Compartilhamento ao vivo não transfere todas as entradas de teclado e mouse. Ele se comunica somente os dados necessários para cada atividade de colaboração para máquinas dos seus colegas de equipe. Por exemplo, quando você compartilha seu espaço de trabalho, sua estrutura de pasta é compartilhada. Ao editar um arquivo de forma colaborativa, o conteúdo do arquivo que é compartilhado. Quando você estiver depurando em colaboração, ações de depuração (por exemplo, passo a passo) e o estado (por exemplo, pilha de chamadas e variáveis locais) são compartilhados.

## <a name="when-will-live-share-be-released"></a>Quando o Live Share será lançado?
Compartilhamento ao vivo está disponível agora em visualização pública! Pretendemos trabalham em conjunto os desenvolvedores testando os bits de visualização, a fim de coletar comentários e certifique-se de que podemos fornecer a melhor experiência possível, antes de abrir o serviço de forma mais ampla.

## <a name="how-much-will-it-cost"></a>Quanto custará?
Estamos empenhados em uma camada gratuita substancial do Visual Studio Live Share que os desenvolvedores usem de forma contínua. Avaliaremos a introdução das camadas pagas com recursos avançados como podemos entender melhor as necessidades da comunidade.

## <a name="how-is-my-code-shared-with-other-teammates"></a>Como meu código é compartilhado com outras colegas de equipe?
Ao usar o Live Share, você está fazendo o código que você está trabalhando em disponível, de modo que seus colegas de equipe podem acessá-lo por meio de um serviço de nuvem segura que comandos remotos do seu editor. Seus colegas de equipe podem abrir e editar os arquivos sem a necessidade de armazená-los na nuvem ou permanentemente armazená-los no computador do seu colega de equipe.

Compartilhamento ao vivo permite o acesso instantâneo aos recursos, como a árvore de projeto, a navegação de código e a pesquisa. Ele também permite que seus colegas de equipe para se beneficiar de aprimoramentos do editor como o IntelliSense.

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>O que acontece se um usuário fica offline ou interrompe o compartilhamento?
O modelo de remoto exige que o desenvolvedor de compartilhamento por meio do Live Share e seu colega de equipe deve estar online para ser conectado. Se seu colega de equipe tenta usar o Live Share quando estiver offline, eles poderão ingressar na sessão até que você esteja online novamente. Além disso, depois de parar de colaboração (por exemplo, você feche seu editor, entra no modo offline ou interromper o compartilhamento), além disso, em seguida, ações ou acesso a arquivos por seus colegas de equipe imediatamente estão desabilitados.

## <a name="what-about-screen-sharing"></a>E quanto ao compartilhamento de tela?
Compartilhamento ao vivo permite que você compartilhe o código do projeto e seu contexto. Isso significa que seu colega de equipe pode ir diretamente para sua base de código e trabalhem facilmente com você, usando sua ferramenta familiar. Seu editor ou outros aplicativos não são compartilhados ou visível por seu colega de equipe, e você não precisa alterar seu estilo de trabalho ou usar um aplicativo baseado na web.

Compartilhamento ao vivo não substitui o compartilhamento de tela em que você talvez queira mostrar um item de menu ou discutir aspectos visuais de seu aplicativo ou seu editor. Em vez disso, você tem a opção de usar o Live Share juntamente com os bate-papo, voz, vídeo e compartilhamento de tela.

## <a name="what-about-other-collaboration-tools"></a>E outras ferramentas de colaboração?
Compartilhamento ao vivo pode ser usado com tecnologias de email, mensagens instantâneas ou chat. Observamos que muitas colaborativas interações entre os desenvolvedores começar nessas ferramentas. No entanto, quando a discussão é sobre código, eles geralmente chegarem a um ponto em que ele é simplesmente muito difícil de explicar um problema com o texto, trechos de código ou arquivos únicos - mais contexto é necessária.

Compartilhamento ao vivo pode ser usado para muitas coisas, como: que buscam obter ajuda sobre um problema, resolver um bug, o par de programação, realizando uma entrevista de codificação ou executar um ad-hoc examinar antes de uma confirmação de código ou uma solicitação de pull.

## <a name="what-about-other-web-editors"></a>E quanto a outros editores da web?
Com editores baseados na web, ambos os colegas de equipe precisam usar o mesmo aplicativo web para obter os benefícios de colaboração, que podem não ser o seu editor de primário e diária. Muitos editores baseados na web pressupõem que você esteja criando e implantando em uma máquina Virtual geralmente hospedada em um ambiente de nuvem.

Embora isso possa ser desejável para muitos cenários, os desenvolvedores geralmente querem colaborar em aplicativos que não são hospedados em uma VM ou na nuvem.  Com o Live Share, você e seu colega de equipe podem usar os recursos do ecossistema da ferramenta, além dos mesmos recursos disponíveis nos editores baseados na web.

Compartilhamento ao vivo vai um passo além e permite que você compartilhe uma sessão de depuração.  Isso torna especialmente útil em Inscrever-se outras pessoas para ajudá-lo a rastrear problemas que ocorrem apenas em seu computador sem alterar seu fluxo de trabalho de desenvolvimento ou precisar alterar o design do aplicativo.

## <a name="which-languages-and-platforms-will-be-supported-in-the-preview"></a>Quais linguagens e plataformas terão suporte na versão prévia?
No entanto, nossa meta é dar suporte a paisagem diversa de linguagens e plataformas, para garantir que podemos pode permite farta colaboração, independentemente do tipo de aplicativo que está sendo desenvolvido. Consulte a [linguagem e suporte de plataforma](reference/platform-support.md) para obter detalhes sobre o que funciona atualmente. Isso é apenas o começo, e esperamos melhorar essa imagem para mover para frente com base nos comentários.

## <a name="how-many-developers-can-join-a-collaboration-session"></a>Como muitos desenvolvedores podem ingressar em uma sessão de colaboração?
Atualmente, damos suporte a cinco convidados simultâneos, além do desenvolvedor que está compartilhando ("hospedagem") seu projeto. Portanto, uma sessão de colaboração pode ter um total de seis desenvolvedores na qualquer momento. Dito isso, essa é uma área estamos procurando comentários, portanto, se você tiver um caso de uso que requer um limite mais alto, por favor [Fale conosco](https://github.com/MicrosoftDocs/live-share/issues/229)!

## <a name="what-is-the-roadmap"></a>Qual é o roteiro?
Você pode exibir o conjunto de problemas conhecidos e itens de roteiro [aqui](https://aka.ms/vsls-issues). Se você quiser ver somente solicitações de recurso em vez de todos os problemas, consulte [aqui](https://aka.ms/vsls-feature-requests). Recomendamos que você votar itens existentes, solicitações de novos recursos de arquivo e fazer relatórios de bugs para nos ajudar a forma a direção do produto mais adiante.

## <a name="see-also"></a>Consulte também

- [Suporte de idioma e plataforma](platform-support.md)
- [Requisitos de conectividade do Live Share](reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](reference/security.md)
- [Todos os bugs importantes, solicitações de recursos e limitações](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

Está tendo problemas? Confira [Solução de problemas](troubleshooting.md) ou [envie comentários](support.md).
