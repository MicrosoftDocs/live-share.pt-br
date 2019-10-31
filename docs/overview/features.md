---
title: Visão geral – Visual Studio Live Share | Microsoft Docs
description: Uma visão geral do Visual Studio Live Share e suas funcionalidades.
ms.custom: ''
ms.date: 10/30/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 8091a7ba5cf1f57f192ecea18da4473c8fdd99f7
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73179865"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->
# <a name="live-share-features-and-concepts"></a>Recursos e conceitos do Live Share 

Live Share é criado usando a arquitetura revolucionária e conceitos que se manifestam como recursos avançados para nossos usuários. Abaixo, você encontrará todos os recursos de distinção de Live Share e o que o tornará um líder no espaço de colaboração. 

### <a name="collaboration-sessions"></a>Sessões de colaboração

Todas as atividades de colaboração do Visual Studio Live Share envolvem um único **host da sessão de colaboração** e um ou mais **convidados**. O host é a pessoa que iniciou a sessão de colaboração, e qualquer pessoa que ingressa na sessão é um convidado.

Os hosts da sessão de colaboração podem usar todas as suas ferramentas e todos os seus serviços, mas os convidados só recebem acesso aos itens específicos que o host compartilhou com eles. Isso inclui código, execução de servidores, sessões de depuração, terminais, entre outros. Atualmente, todo o conteúdo compartilhado é mantido no computador do host e não é sincronizado na nuvem ou no computador do convidado, o que permite o _acesso instantâneo_ e uma _maior segurança_. A vantagem é que a solução inteira fica disponível no momento em que um convidado ingressa na sessão e, no momento em que um host encerra uma sessão de colaboração, o conteúdo não fica mais disponível. Além disso, os arquivos temporários criados pelo IDE/editor para melhorar o desempenho para o convidado são limpos automaticamente quando a sessão é encerrada.

#### <a name="sharing"></a>Compartilhamento

Ao fazer o "compartilhamento" como um host, você inicia uma sessão de colaboração que compartilha o conteúdo de um projeto, uma solução ou uma pasta. Os convidados obtêm acesso a esse conteúdo usando o link do convite que você envia para eles. Embora "compartilhamento" seja a abreviação de "compartilhamento de um projeto", ele também possibilita o compartilhamento de outras funcionalidades, como depuração.

**Saiba mais:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-project) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-project)

#### <a name="joining"></a>Ingressando

Clicando em um link do convite enviado a você por um host, você pode "ingressar" em uma sessão de colaboração como convidado e acessar qualquer conteúdo ou as funcionalidades que o host tiver optado por compartilhar com você. O link da Web fornece uma maneira rápida de entrar em uma sessão de colaboração, caso você já tenha a extensão instalada, e de configurar informações, caso não tenha feito isso.

**Saiba mais:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#join-a-collaboration-session) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#join-a-collaboration-session)

### <a name="features"></a>Recursos

#### <a name="co-editing"></a>Coedição

Quando você abre o mesmo arquivo como outro colaborador, você consegue instantaneamente "editar de forma colaborativa" ou "coeditar" o conteúdo do arquivo. Você pode ver as edições de cada colaborador, seus cursores e seleções, entre outros. Melhor ainda, você não é obrigado a editar o mesmo arquivo em todos os momentos, podendo, assim, colaborar oportunamente e agir de forma independente conforme achar melhor.

> [!NOTE]
> A coedição tem algumas limitações. Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades por linguagem.

**Saiba mais:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-editing) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-editing)

#### <a name="following-and-focusing"></a>Seguindo e focando a atenção

Às vezes, você precisa explicar um problema ou um design que abrange vários arquivos ou locais no código. Nessas situações, pode ser útil seguir temporariamente um colega enquanto ele percorre o projeto ao coeditá-lo. Por esse motivo, ao ingressar em uma sessão de colaboração, você, como convidado, "segue" automaticamente o local de edição do host. Os hosts e os convidados podem seguir e deixar de seguir uns aos outros com um simples clique do mouse. Além disso, talvez você deseje solicitar a todos os participantes que sigam você. O Live Share permite solicitar a todos que "foquem a atenção" em você com uma notificação que facilita para eles o seguirem de volta.

**Saiba mais:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#following) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#following)

#### <a name="co-debugging"></a>Codepuração

Quando você estiver depurando bugs ou problemas de codificação difíceis, poderá ser muito útil ter um parceiro para unir forças. Como host, o Live Share permite "a depuração colaborativa" ou a "codepuração" automaticamente pelo compartilhamento da sessão de depuração com todos os convidados. Cada um dos participantes obtém funcionalidades de coedição, juntamente com a capacidade de investigar de forma independente, conforme vocês analisam o problema juntos.

> [!NOTE]
> Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades de depuração por linguagem ou plataforma.

**Saiba mais:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-debugging) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>Compartilhar o servidor/compartilhar a porta

Durante a codepuração, pode ser muito útil obter acesso a diferentes partes do aplicativo que está sendo fornecido pelo host para a sessão de depuração. Talvez você deseje acessar o aplicativo em um navegador, acessar um banco de dados local ou um ponto de extremidade REST por meio de suas ferramentas. O Live Share permite que você "compartilhe um servidor", que mapeia uma porta local no computador do host para exatamente a mesma porta no computador de cada convidado. Como convidado, você pode então interagir com o aplicativo exatamente como se ele estivesse sendo executado localmente em seu computador (por exemplo, o host e o convidado podem acessar um aplicativo Web em execução em http://localhost:3000).

**Saiba mais:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-server) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-server)

#### <a name="share-terminals"></a>Compartilhar terminais

O desenvolvimento moderno faz uso frequente de uma ampla gama de ferramentas de linha de comando. Felizmente, o Live Share permite que você, como host, opcionalmente, "compartilhe um terminal" com os convidados. O terminal compartilhado pode ser somente leitura ou totalmente colaborativo, de modo que você e seus convidados possam executar comandos e ver os resultados. Como o host, você está sempre no controle e pode decidir se outros colaboradores podem executar comandos por conta própria ou apenas ver a saída do comando. Na verdade, qualquer coisa que você desejar manter para si mesmo, poderá executar em um terminal não compartilhado.

**Saiba mais:** [![vs Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-terminal) [![vs](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-terminal)

#### <a name="access-controls"></a>Controles de acesso

O Visual Studio Live Share fornece aos participantes diversas maneiras excelentes de colaboração. No entanto, com o número de opções e a flexibilidade oferecida aos convidados para interação com os hosts, o ideal é aprovar explicitamente os convidados que ingressam na sessão ou bloquear o acesso a determinados arquivos ou pastas. O Live Share tem várias configurações que podem ajudá-lo, incluindo somente leitura e solicitação da aceitação de convidados.

**Saiba mais:** [![vs Code](../media/vscode-icon-15x15.png)](../reference/security.md) [![vs](../media/vs-icon-15x15.png)](../reference/security.md)

#### <a name="flexible-connection-modes"></a>Modos de conexão flexíveis

Para garantir um desempenho ideal, o Visual Studio Live Share dá suporte a dois "modos de conexão" principais: "direto" e "retransmissão". No modo direto, os convidados se conectam diretamente ao host sem passar pela Web. O modo de retransmissão permite que os convidados localizados em uma rede completamente diferente se conectem ao host por meio de uma retransmissão da Internet. Em todos os casos, as conexões são criptografadas em SSH ou SSL para garantir que somente os colaboradores obtenham acesso ao que está acontecendo durante a transmissão. Por padrão, o Live Share está no modo "automático", que tenta primeiro estabelecer uma conexão direta e, em seguida, faz failover para a retransmissão. Porém, se você preferir, poderá bloqueá-lo em um único modo.

**Saiba mais:** [![vs Code](../media/vscode-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode) [![vs](../media/vs-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode)
