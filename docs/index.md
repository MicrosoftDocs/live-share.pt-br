---
title: Visão geral – Visual Studio Live Share | Microsoft Docs
description: Uma visão geral do Visual Studio Live Share e suas funcionalidades.
ms.custom: ''
ms.date: 04/26/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5f67086e9040a477e082cbd3ef27a1789c6406c5
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58853580"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>O que é o Visual Studio Live Share?

Bem-vindo ao Visual Studio Live Share! O Live Share permite que você edite e depure de forma colaborativa com outras pessoas em tempo real, sejam quais forem as linguagens de programação usadas ou os tipos de aplicativo criados. Ele permite que você compartilhe seu projeto atual de forma instantânea e segura e, em seguida, conforme necessário, compartilhe sessões de depuração, instâncias de terminal, aplicativos Web do localhost, chamadas de voz e muito mais!

Além disso, ao contrário da programação em par tradicional, o Visual Studio Live Share permite que os desenvolvedores trabalhem em conjunto, mantendo suas preferências pessoais de editor (por exemplo, tema, associações de teclas), além de terem seu próprio cursor. Isso permite que você faça uma transição tranquila entre a capacidade de seguir uns aos outros e de explorar ideias/tarefas por conta própria. Na prática, essa capacidade de trabalhar em conjunto _e_ de forma independente fornece uma experiência de colaboração que é potencialmente mais natural para muitos casos de uso comuns.

Pronto para começar? Neste artigo, explicaremos alguns conceitos e como instalar as extensões necessárias. Caso esteja procurando uma versão resumida, confira os Inícios Rápidos [Compartilhar](quickstart/share.md) e [Ingressar](quickstart/join.md).

> [!TIP]
> Você sabia que pode *ingressar em sua própria sessão de colaboração*? Isso permite que você experimente o Live Share por conta própria ou crie uma instância do Visual Studio ou do VS Code e conecte-a remotamente. Você pode até mesmo usar a mesma identidade em ambas as instâncias. Confira!

## <a name="install-visual-studio-live-share"></a>Instalar o Visual Studio Live Share

Antes de começar, você precisa confirmar se tem uma versão do Visual Studio ou do Visual Studio Code instalada que atenda aos requisitos principais do Live Share.

- **Visual Studio Code 1.22.0 ou posterior** – Windows 7, 8.1 ou 10, macOS *(somente Serra 10.12 e posterior)* e Linux de 64 bits *(Ubuntu Desktop de 64 bits 16.04 ou posterior, Fedora 27 ou posterior, recomendado – [ver detalhes](use/vscode.md#installation))*.
- **Visual Studio 2019** (qualquer edição) – Windows 7, 8.1 ou 10.
- **Visual Studio 2017 15.6 ou posterior** (qualquer edição) – Windows 7, 8.1 ou 10.

Depois disso, o download e a instalação da extensão do Visual Studio Live Share são muito simples:

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0 ou posterior)</strong><br />
        1. Instale o <a href="https://code.visualstudio.com/">Visual Studio Code</a> para Windows (7, 8.1 ou 10), macOS <b>(Sierra ou posterior)</b> e Linux de 64 bits <b>(<a href="use/vscode.md#installation">detalhes</a>)</b><br />
        2. Baixe e instale a extensão Visual Studio Live Share do marketplace. <br />
        3. Recarregue e aguarde até que as dependências sejam baixadas e instaladas (veja a barra de status).<br />
        4. <strong>Linux</strong>: Se precisar <a href="reference/linux.md#install-linux-prerequisites">instalar bibliotecas</a>, clique em Instalar, insira a senha e reinicie o VS Code quando terminar.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. Instale o <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
        2. Instale uma <a href="reference/platform-support.md">carga de trabalho compatível</a>. (por exemplo, ASP.NET, .NET Core, C++ e/ou Node.js)<br />
        3. O Visual Studio Live Share é instalado por padrão com essas cargas de trabalho. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 ou posterior</strong><br />
        1. Instale a última versão do <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6 ou posterior) no Windows (7, 8.1 ou 10).<br/>
        2. Instale uma <a href="reference/platform-support.md">carga de trabalho compatível</a>. (por exemplo, ASP.NET, .NET Core, C++ e/ou Node.js)<br />
        3. Baixe e instale a extensão Visual Studio Live Share do marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Ao baixar e usar o Visual Studio Live Share, você concorda com os [termos de licença](https://aka.ms/vsls-license) e a [política de privacidade](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Confira [Solução de problemas](troubleshooting.md) caso tenha problemas.

E isso é tudo! Agora você deverá ver uma barra de status de entrada no canto inferior esquerdo do VS Code e um botão de compartilhamento na parte superior direita do Visual Studio. Confira o restante da documentação para saber o que fazer em seguida.

## <a name="concepts-and-features"></a>Conceitos e funcionalidades

Assim como acontece com qualquer produto, o Visual Studio Live Share fornece um conjunto de funcionalidades avançadas criadas com base em alguns conceitos principais. Esta seção fornece alguns conceitos e um breve tour das funcionalidades.

### <a name="collaboration-sessions"></a>Sessões de colaboração

Todas as atividades de colaboração do Visual Studio Live Share envolvem um único **host da sessão de colaboração** e um ou mais **convidados**. O host é a pessoa que iniciou a sessão de colaboração, e qualquer pessoa que ingressa na sessão é um convidado.

Os hosts da sessão de colaboração podem usar todas as suas ferramentas e todos os seus serviços, mas os convidados só recebem acesso aos itens específicos que o host compartilhou com eles. Isso inclui código, execução de servidores, sessões de depuração, terminais, entre outros. Atualmente, todo o conteúdo compartilhado é mantido no computador do host e não é sincronizado na nuvem ou no computador do convidado, o que permite o _acesso instantâneo_ e uma _maior segurança_. A vantagem é que a solução inteira fica disponível no momento em que um convidado ingressa na sessão e, no momento em que um host encerra uma sessão de colaboração, o conteúdo não fica mais disponível. Além disso, os arquivos temporários criados pelo IDE/editor para melhorar o desempenho para o convidado são limpos automaticamente quando a sessão é encerrada.

#### <a name="sharing"></a>Compartilhamento

Ao fazer o "compartilhamento" como um host, você inicia uma sessão de colaboração que compartilha o conteúdo de um projeto, uma solução ou uma pasta. Os convidados obtêm acesso a esse conteúdo usando o link do convite que você envia para eles. Embora "compartilhamento" seja a abreviação de "compartilhamento de um projeto", ele também possibilita o compartilhamento de outras funcionalidades, como depuração.

**Saiba mais:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-project) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-project)

#### <a name="joining"></a>Ingressando

Clicando em um link do convite enviado a você por um host, você pode "ingressar" em uma sessão de colaboração como convidado e acessar qualquer conteúdo ou as funcionalidades que o host tiver optado por compartilhar com você. O link da Web fornece uma maneira rápida de entrar em uma sessão de colaboração, caso você já tenha a extensão instalada, e de configurar informações, caso não tenha feito isso.

**Saiba mais:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#join-a-collaboration-session) [![VS](media/vs-icon-15x15.png)](use/vs.md#join-a-collaboration-session)

### <a name="features"></a>Recursos

#### <a name="co-editing"></a>Coedição

Quando você abre o mesmo arquivo como outro colaborador, você consegue instantaneamente "editar de forma colaborativa" ou "coeditar" o conteúdo do arquivo. Você pode ver as edições de cada colaborador, seus cursores e seleções, entre outros. Melhor ainda, você não é obrigado a editar o mesmo arquivo em todos os momentos, podendo, assim, colaborar oportunamente e agir de forma independente conforme achar melhor.

> [!NOTE]
> A coedição tem algumas limitações. Confira [Suporte de plataforma](reference/platform-support.md) para obter o estado das funcionalidades por linguagem.

**Saiba mais:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-editing) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-editing)

#### <a name="following-and-focusing"></a>Seguindo e focando a atenção

Às vezes, você precisa explicar um problema ou um design que abrange vários arquivos ou locais no código. Nessas situações, pode ser útil seguir temporariamente um colega enquanto ele percorre o projeto ao coeditá-lo. Por esse motivo, ao ingressar em uma sessão de colaboração, você, como convidado, "segue" automaticamente o local de edição do host. Os hosts e os convidados podem seguir e deixar de seguir uns aos outros com um simples clique do mouse. Além disso, talvez você deseje solicitar a todos os participantes que sigam você. O Live Share permite solicitar a todos que "foquem a atenção" em você com uma notificação que facilita para eles o seguirem de volta.

**Saiba mais:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#following) [![VS](media/vs-icon-15x15.png)](use/vs.md#following)

#### <a name="co-debugging"></a>Codepuração

Quando você estiver depurando bugs ou problemas de codificação difíceis, poderá ser muito útil ter um parceiro para unir forças. Como host, o Live Share permite "a depuração colaborativa" ou a "codepuração" automaticamente pelo compartilhamento da sessão de depuração com todos os convidados. Cada um dos participantes obtém funcionalidades de coedição, juntamente com a capacidade de investigar de forma independente, conforme vocês analisam o problema juntos.

> [!NOTE]
> Confira [Suporte de plataforma](reference/platform-support.md) para obter o estado das funcionalidades de depuração por linguagem ou plataforma.

**Saiba mais:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-debugging) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>Compartilhar o servidor/compartilhar a porta

Durante a codepuração, pode ser muito útil obter acesso a diferentes partes do aplicativo que está sendo fornecido pelo host para a sessão de depuração. Talvez você deseje acessar o aplicativo em um navegador, acessar um banco de dados local ou um ponto de extremidade REST por meio de suas ferramentas. O Live Share permite que você "compartilhe um servidor", que mapeia uma porta local no computador do host para exatamente a mesma porta no computador de cada convidado. Como convidado, você pode então interagir com o aplicativo exatamente como se ele estivesse sendo executado localmente em seu computador (por exemplo, o host e o convidado podem acessar um aplicativo Web em execução em http://localhost:3000).

**Saiba mais:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-server) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-server)

#### <a name="share-terminals"></a>Compartilhar terminais

O desenvolvimento moderno faz uso frequente de uma ampla gama de ferramentas de linha de comando. Felizmente, o Live Share permite que você, como host, opcionalmente, "compartilhe um terminal" com os convidados. O terminal compartilhado pode ser somente leitura ou totalmente colaborativo, de modo que você e seus convidados possam executar comandos e ver os resultados. Como o host, você está sempre no controle e pode decidir se outros colaboradores podem executar comandos por conta própria ou apenas ver a saída do comando. Na verdade, qualquer coisa que você desejar manter para si mesmo, poderá executar em um terminal não compartilhado.

**Saiba mais:** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-terminal) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-terminal)

#### <a name="access-controls"></a>Controles de acesso

O Visual Studio Live Share fornece aos participantes diversas maneiras excelentes de colaboração. No entanto, com o número de opções e a flexibilidade oferecida aos convidados para interação com os hosts, o ideal é aprovar explicitamente os convidados que ingressam na sessão ou bloquear o acesso a determinados arquivos ou pastas. O Live Share tem várias configurações que podem ajudá-lo, incluindo somente leitura e solicitação da aceitação de convidados.

**Saiba mais:** [![VS Code](media/vscode-icon-15x15.png)](reference/security.md) [![VS](media/vs-icon-15x15.png)](reference/security.md)

#### <a name="flexible-connection-modes"></a>Modos de conexão flexíveis

Para garantir um desempenho ideal, o Visual Studio Live Share dá suporte a dois "modos de conexão" principais: "direto" e "retransmissão". No modo direto, os convidados se conectam diretamente ao host sem passar pela Web. O modo de retransmissão permite que os convidados localizados em uma rede completamente diferente se conectem ao host por meio de uma retransmissão da Internet. Em todos os casos, as conexões são criptografadas em SSH ou SSL para garantir que somente os colaboradores obtenham acesso ao que está acontecendo durante a transmissão. Por padrão, o Live Share está no modo "automático", que tenta primeiro estabelecer uma conexão direta e, em seguida, faz failover para a retransmissão. Porém, se você preferir, poderá bloqueá-lo em um único modo.

**Saiba mais:** [![VS Code](media/vscode-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode) [![VS](media/vs-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode)

## <a name="see-also"></a>Consulte também

Guias de Início Rápido

- [Compartilhar seu primeiro projeto](quickstart/share.md)
- [Ingressar em sua primeira sessão](quickstart/join.md)

Instruções

- [colaborar usando o Visual Studio Code](use/vscode.md)
- [colaborar usando o Visual Studio](use/vs.md)

Referência

- [Requisitos de conectividade do Live Share](reference/connectivity.md)
- [Recursos de segurança do Live Share](reference/security.md)
- [Suporte de idioma e plataforma](reference/platform-support.md)
- [Suporte de extensão](reference/extensions.md)
- [Notas sobre a versão](https://aka.ms/vsls-releases)

Está tendo problemas? Confira [Solução de problemas](troubleshooting.md) ou [envie comentários](support.md).
