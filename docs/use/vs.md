---
title: Colaborar usando o Visual Studio - Visual Studio Live Share | Microsoft Docs
description: Um conjunto de instruções de colaboração para o Visual Studio e o Live Share.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 995c9e16d24328bb2680deb99cd7e7d421af945c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255272"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio"></a>Como: Colaborar usando o Visual Studio

Pronto para obter colaborando com Live Share no Visual Studio? Nesse caso, você está no lugar certo! Neste artigo vamos percorrer você como usar alguns dos recursos específicos na extensão do Visual Studio Live Share para Visual Studio.

Observe que todas as atividades de colaboração em descrito aqui envolvem uma única **host de sessão de colaboração** e um ou mais **convidados**. O host é a pessoa que iniciou a sessão de colaboração, e qualquer pessoa que ingressa na sessão é um convidado.

*Procurando um resumo resumido? Confira a [compartilhar](../quickstart/share.md) ou [junção](../quickstart/join.md) guias de início rápido em vez disso.*

> [!TIP]
> Você sabia que pode *ingressar em sua própria sessão de colaboração*? Isso permite que você experimente o Live Share por conta própria ou crie uma instância do Visual Studio ou do VS Code e conecte-a remotamente. Você pode até mesmo usar a mesma identidade em ambas as instâncias. Confira!

## <a name="installation"></a>Instalação

Antes de começar, você precisará instalar **Visual Studio 2017 15.6 ou posterior** no Windows 7, 8.1 ou 10. *No entanto, o Visual Studio 15.7 + é recomendável como isso habilita o suporte de desfazer/refazer local.*

Obtendo vai é simple:

1. Instale qualquer edição do [Visual Studio 2017](https://visualstudio.microsoft.com/vs/) 15.6 +.
2. Instale um [suporte para a carga de trabalho](../reference/platform-support.md). (por exemplo, ASP.NET, .NET Core, C++ e/ou Node.js)
3. [Baixar](https://aka.ms/vsls-dl/vs) e instalar a extensão do Visual Studio Live Share do marketplace.

Ao baixar e usar o Visual Studio Live Share, você concorda com os [termos de licença](https://aka.ms/vsls-license) e a [política de privacidade](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Confira [Solução de problemas](../troubleshooting.md) caso tenha problemas.

[![Download](../media/download.png)](https://aka.ms/vsls-dl/vs)

## <a name="sign-in"></a>Entrar

Para colaborar, você precisará entrar no Visual Studio Live Share para que todo mundo sabe quem é você. Isso é puramente uma medida de segurança e faz **não** consentir qualquer marketing ou outras atividades de pesquisa. Você pode entrar usando uma conta pessoal da Microsoft (por exemplo, @outlook.com), trabalho com suporte da Microsoft ou conta de Estudante (AAD) ou uma conta do GitHub. É fácil entrar.

Por padrão o Visual Studio usa o seu [conta de personalização](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) portanto, se você já estiver conectado ao Visual Studio, você poderá ignorar esta etapa. Caso contrário, entrar como você faria normalmente.

![No botão entrar do VS](../media/vs-sign-in-button.png)

Se você deseja usar um outro logon em que o Visual Studio [conta de personalização](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), acesse **ferramentas &gt; opções &gt; Live Share &gt; conta de usuário** alternar credenciais.

![Opções de ferramentas do VS Live compartilhamento](../media/vs-tools-options.png)

Selecionando **conta externa** permite que você selecione uma conta que não tem suportada pelo recurso de personalização do Visual Studio como o GitHub. Um navegador será exibido automaticamente na primeira vez que você usa um recurso de Live Share, portanto, você pode concluir de entrada.

Se você tiver problemas, fazer check-out [solução de problemas](../troubleshooting.md#sign-in) para obter mais dicas.

## <a name="share-a-project"></a>Compartilhar um projeto

Depois de baixar e instalar o Visual Studio Live Share, siga estas etapas para iniciar uma sessão de colaboração e convidar um colega para trabalhar com você.

1. **Entrar**

    Depois de instalar a extensão de compartilhamento ao vivo, você desejará entrar para permitir que outros colaboradores Saiba quem é você. Por padrão o Visual Studio usa sua conta de personalização, portanto, você poderá ignorar esta etapa inteiramente.

    Ver [entrar](#sign-in) para obter mais detalhes.

2. **Abra uma solução, projeto ou pasta**

    Use o fluxo de trabalho normal para abrir uma pasta, projeto ou solução que você gostaria de compartilhar com seus convidados.

3. **[Opcional] Atualizar arquivos ocultos ou excluídos**

    Por padrão, o Live Share **oculta** quaisquer arquivos/pastas referenciadas nos arquivos. gitignore em seu projeto de convidados. **Ocultando** um arquivo impede que ele apareça na árvore de arquivos ao mesmo tempo **excluindo** interrompe sejam transmitidas, mesmo durante as operações, como depuração. Se você quiser ocultar/excluir arquivos diferentes, uma **. vsls.json** arquivo pode ser adicionado ao seu projeto com essas configurações. Ver [controlando o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para obter detalhes.

4. **Iniciar uma sessão de colaboração**

    Agora, basta clicar no botão de "Compartilhamento" no canto superior direito.

    ![Botão de compartilhamento do VS](../media/vs-share-button.png)

    > [!NOTE]
    > Você poderá ser solicitado por seu software de firewall da área de trabalho para permitir que o agente Live Share abrir uma porta na primeira vez que você compartilha. Aceitar isso é totalmente opcional, mas permite que um seguro "modo direto" para melhorar o desempenho quando a pessoa que você está trabalhando com está na mesma rede que você esteja. Ver [alterando o modo de conexão](../reference/connectivity.md#changing-the-connection-mode) para obter detalhes.

    Um link de convite será copiado automaticamente para a área de transferência. Quando aberto em um navegador, esse link permite que outras pessoas ingressar em uma nova sessão de colaboração que compartilha o conteúdo dessas pastas com eles.

    Você também verá a transição do botão "Share" para transmitir um "estado de sessão". Ver [estado de sessão](#session-states) informações abaixo sobre o que isso se parece.

    Observe que, se você precisar obter o link de convite novamente depois de começar o compartilhamento, você pode acessá-la clicando no compartilhamento / botão e selecionando "Copiar Link" de estado de sessão.

5. **[Opcional] Habilitar o modo somente leitura**

    Depois de iniciar sua sessão de colaboração, você pode definir a sessão a ser somente leitura para impedir que os convidados façam edições no código que está sendo compartilhado.

    Após o compartilhamento, você receberá uma notificação de que o link de convite foi copiado para a área de transferência. Em seguida, você pode selecionar a opção de fazer a sessão somente leitura.

    ![Modo somente leitura do VS](../media/vs-read-only-notification.png)

6. **Enviar a alguém o link**

    Enviar link por email, Slack, Skype, etc., para aqueles que deseja convidar. Observe que, considerando o nível de acesso Live Share sessões podem fornecer aos convidados, **você só deve compartilhar com pessoas confiáveis** e considere as implicações do que você está compartilhando.

    > **Dica de segurança:** Deseja entender as implicações de segurança de alguns dos recursos do Live Share? Confira a [segurança](../reference/security.md) artigo.

    Se o convidado é convidado tiver perguntas, o "[guia de início rápido: Junte-se a primeira sessão](../quickstart/join.md)"artigo fornece algumas informações sobre colocar em execução como convidado.

7. **[Opcional] Aprovar o convidado**

    Por padrão, os convidados ingressarão automaticamente sua sessão de colaboração e você será notificado quando eles já pronto para trabalhar com você. Enquanto essa notificação oferece a opção para removê-los da sessão, você também pode optar em vez disso, exigem uma "aprovação" explícita para qualquer pessoa unindo.

    Basta alterar **Ferramentas > Opções > Live Share > exigir aprovação do convidado** como True para habilitar o recurso. Depois que essa configuração ativada, uma notificação solicitará que você aprovar o convidado para que possam participar.

    ![Solicitação de aprovação de junção do Visual Studio](../media/vs-join-approval.png)

    Ver [convites e acesso ao ingresso](../reference/security.md#invitations-and-join-access) para obter detalhes adicionais sobre as considerações de segurança do convite.

Isso é tudo!!

### <a name="ending-the-collaboration-session"></a>Encerrando a sessão de colaboração

Como um host, você pode interromper o compartilhamento completamente e encerrar a sessão de colaboração clicando o compartilhamento / botão (no canto superior direito) e selecionando "encerrar sessão de colaboração" de estado de sessão.

![Interromper o compartilhamento](../media/vs-stop-sharing.png)

Todos os convidados serão notificados de que a sessão foi encerrada. Depois que a sessão foi encerrada, os convidados não poderá acessar o conteúdo e todos os arquivos temporários são limpos automaticamente.

Está tendo problemas com o compartilhamento? Fazer check-out [solução de problemas](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Ingressar em uma sessão de colaboração

Depois de baixar e instalar o Visual Studio Live Share, convidados só precisará executar algumas etapas para ingressar em uma sessão de colaboração hospedada. Há duas maneiras para unir: [por meio do navegador](#join-via-the-browser) e [manualmente](#join-manually).

> **Dica de segurança:** Como um convidado a ingressar em uma sessão de colaboração, é importante entender que os hosts podem restringir o acesso a determinados arquivos ou recursos. Deseja entender as implicações de segurança de alguns dos recursos e configurações de compartilhamento ao vivo? Confira a [segurança](../reference/security.md) artigo.

### <a name="join-via-the-browser"></a>Junte-se por meio do navegador

A maneira mais fácil para ingressar em uma sessão de colaboração é simplesmente abrir o link de convite em um navegador da web. Aqui está o que você pode esperar quando você segue esse fluxo.

1. **Entrar**

    Depois de instalar a extensão de compartilhamento ao vivo, você desejará entrar para permitir que outros colaboradores Saiba quem é você. Por padrão o Visual Studio usa sua conta de personalização, portanto, você poderá ignorar esta etapa inteiramente.

    Ver [entrar](#sign-in) para obter mais detalhes.

2. **Clique no link de convite / abrir o convite em seu navegador**

    Agora, basta abrir (ou abrir novamente) no link de convite em um navegador.

    > **Observação**: Se você ainda não tiver instalado a extensão de compartilhamento ao vivo, você verá com links para o marketplace de extensão. Instalar a extensão e reinicie sua ferramenta e tente novamente.

    Você deve ser notificado que o navegador deseja iniciar uma ferramenta de Live Share habilitado. Se você permitir que ele inicie a ferramenta selecionada, você estará conectado à sessão de colaboração, depois que ele for iniciado.

    ![Página de junção](../media/join-page.png)

    Se o host estiver offline, você será notificado no momento em vez disso. Você pode, em seguida, entre em contato com o host e peça-lhe para compartilhar novamente.

    > [!NOTE]
    > Ainda está com problemas? Ver [unir manualmente](#join-manually).

3. **Colaborar**

    Isso é tudo!! Em alguns instantes você estará conectado e você pode começar a colaborar.

    Você verá a transição do botão "Share" para transmitir um "estado de sessão". Ver [estado de sessão](#session-states) informações abaixo para ver como fica isso.

    Você será automaticamente levado para o arquivo de que host estiver atualmente editando depois que a junção for concluída.

### <a name="join-manually"></a>Unir manualmente

Você pode unir manualmente sem usar um navegador da web que pode ser útil em situações em que a ferramenta que você deseja usar já está em execução, você deseja usar outra ferramenta que faria normalmente, ou se você estiver tendo problemas com a introdução convidar links trabalhar por algum motivo. O processo é fácil:

1. **Entrar**

    Depois de instalar a extensão de compartilhamento ao vivo, você desejará entrar para permitir que outros colaboradores Saiba quem é você. Por padrão o Visual Studio usa sua conta de personalização, portanto, você poderá ignorar esta etapa inteiramente.

    Ver [entrar](#sign-in) para obter mais detalhes.

2. **Use o comando de junção**

    Basta ir para **arquivo > Junte-se a sessão de colaboração**

    ![Menu de junção do VS](../media/vs-join.png)

3. **Cole o link de convite**

    Cole a URL de convite que foram enviadas e confirme.

4. **Colabore!**

    É só isso! Você deve estar conectado à sessão de colaboração momentaneamente.

    Você verá a transição do botão "Share" para transmitir um "estado de sessão". Ver [estado de sessão](#session-states) informações abaixo para ver como fica isso.

    Você será automaticamente levado para onde o host estiver atualmente editando após a conclusão da junção.

### <a name="leave-the-collaboration-session"></a>Deixe a sessão de colaboração

Como um convidado, você pode deixar a sessão de colaboração sem encerrá-la para outras pessoas, basta fechar a ferramenta ou clicando o compartilhamento / botão e selecionando "Deixe a sessão de colaboração" de estado de sessão.

![Menu de junção do VS](../media/vs-leave-session.png)

Todos os arquivos temporários são automaticamente limpas para que nenhuma ação adicional é necessária.

Está tendo problemas com unindo? Fazer check-out [solução de problemas](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Coedição

Depois que um convidado ingressou em uma sessão de colaboração, todos os colaboradores imediatamente será capazes de ver uns dos outros edições e as seleções em tempo real. Tudo o que você precisa fazer é pegar um arquivo no Gerenciador de arquivos e começar a editar. Hosts e convidados verá edições como torná-los e contribuir com a mesmos, tornando fácil iterar e prego rapidamente para reduzir as soluções.

> [!NOTE]
> Ingressar em uma sessão de colaboração de somente leitura impede que convidados sejam capazes de fazer edições em arquivos. Um host pode [habilitar o modo somente leitura quando eles compartilham](#share-a-project). Como um convidado, você pode informar se você se associou a uma sessão somente leitura, observando sua [estado de sessão](#session-states).

![Captura de tela mostrando conjunta de edição](../media/vs-coedit.png)

> [!NOTE]
> Parceria entre a edição tem algumas limitações para determinados idiomas. Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades por linguagem.

Além de cursores e edições, as seleções feitas também são visíveis para todos os participantes no mesmo arquivo. Isso torna mais fácil realçar onde os problemas podem existir ou transmitir ideias.

![Captura de tela mostrando o realce](../media/vs-highlight.png)

Melhor ainda, você e outros participantes podem navegar para qualquer arquivo no projeto compartilhado. Você pode editar juntos ou de forma independente que significa que você pode alternar diretamente entre a investigação, fazer pequenos ajustes e completa de colaboração por edição.

> [!NOTE]
> Por padrão o Live Share compartilhamentos aberta arquivos externos à solução compartilhada. Se você quiser desabilitar esse recurso, atualize o compartilhamento de arquivos externos em ferramentas &gt; opções &gt; Live Share como False.

As edições resultantes são persistidas na máquina do host em Salvar existe há necessidade de sincronizar, enviar por push ou enviar arquivos ao redor quando você terminar edição. As edições são "apenas there".

> **Dica de segurança:** Dada a todos os participantes podem independentemente navegar e editar arquivos, como um host, você talvez queira restringir quais arquivos convidados são capazes de acessar em seu projeto por meio de um. vsls.json arquivo. Como um convidado, também é importante perceber que você não poderá ver a certos arquivos como resultado dessas configurações. Ver [controlando o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para obter detalhes.

### <a name="changing-participant-flag-behaviors"></a>Alterando os comportamentos do sinalizador de participante

Por padrão, o Visual Studio Live Share exibe automaticamente um sinalizador de"" ao lado do cursor de um participante em foco, ou quando eles editar, realce, ou move seu cursor. Em alguns casos, você talvez prefira alterar esse comportamento. Para fazer isso:

1. Vá para **Ferramentas > Opções > Live compartilhamento**
2. Alterar o **sinalizador de visibilidade** opção para um dos seguintes:

| Opção | Comportamento |
|--------|----------|
| OnHoverOnly | O sinalizador só fica visível quando você focaliza o cursor. |
| OnHoverOrActivity | Esse é o padrão. O sinalizador é visível ao focalizar ou se o participante edita, destaca ou move o cursor. |
| Sempre | O sinalizador está sempre visível.

## <a name="following"></a>A seguir

Sempre que você está em uma sessão de colaboração, você poderá pode ver as iniciais de cada participante na parte superior direita do editor ao lado do botão de entrada. Passar o mouse sobre as iniciais mostra informações completas do participante.

![Captura de tela mostrando usuário](../media/vs-person.png)

Às vezes, você talvez precise explicar um problema ou design que abrange vários arquivos ou locais no código. Nessas situações, ele pode útil seguir temporariamente um colega quando eles passam ao longo do projeto. Por esse motivo, como um convidado quando você ingressa em uma sessão de colaboração você será automaticamente "seguir" host. Ao seguir um participante, seu editor permanecerão em sincronizado com seu arquivo aberto no momento, o cursor e a posição de rolagem.

> [!NOTE]
> Por padrão o Live Share compartilhamentos aberta arquivos externos à solução compartilhada. Se você quiser desabilitar esse recurso, atualize o compartilhamento de arquivos externos em ferramentas &gt; opções &gt; Live Share como False.

Para tornar mais fácil do "modo de acompanhamento" e começar a editá-lo por conta própria, você irá parar a seguir se qualquer uma das seguintes acontece:

1. Editar, mova o cursor ou faça uma seleção
2. Selecione outro arquivo

Você também pode interromper a seguir a qualquer momento clicando as iniciais da pessoa que você está seguindo no canto superior direito. O círculo iniciais do participante que indica que você está seguindo-los, em seguida, desaparecerá.

![Participante Visual do Studio sendo seguido](../media/vs-pinned.png) ![Participante do Studio Visual não sendo seguido](../media/vs-pin-hover.png)

Você pode clicar em qualquer iniciais nesse mesmo local a seguir qualquer host ou convidado na sessão de colaboração. Observe que, se você apenas deseja saltar de alguém local em vez de segui-las, simplesmente clique duas vezes em suas iniciais.

## <a name="focusing"></a>Concentrando-se

Ocasionalmente, talvez você queira todos em uma sessão de colaboração para vêm e dar uma olhada em algo que está fazendo. Compartilhamento ao vivo permite solicitar que todos "concentram" você com uma notificação que torna mais fácil para que elas sigam você de volta.

Basta clicar no estado de sessão / compartilhar botão no canto superior direito e selecione "Foco participantes".

![Opção de menu de foco](../media/vs-focus.png)

Todas as pessoas a sessão de colaboração, em seguida, receberá uma notificação de que você solicitou a sua atenção

![Notificação do sistema de foco](../media/vs-focus-toast.png)

Pode, em seguida, basta clicar em "Follow" à direita da notificação de quando eles estiverem prontos para colocar o foco em você.

## <a name="co-debugging"></a>Codepuração

O recurso de depuração colaborativo do Visual Studio Live Share é uma maneira exclusiva e poderosa para depurar um problema. Além de permitir uma experiência de colaboração solucionar problemas, também você e outros participantes em sua sessão, a capacidade de investigar os problemas que podem ser específicos do ambiente, fornecendo uma sessão de depuração compartilhada no computador do host.

> **Dica de segurança:** Dada a todos os participantes podem independentemente navegar e editar arquivos, como um host, você talvez queira restringir quais arquivos convidados são capazes de acessar em seu projeto por meio de um. vsls.json arquivo. Você também deve estar ciente de que o acesso de Console/REPL significa que os participantes podem executar comandos em seu computador para que você só deve depurar junto com aqueles que você confia. Como um convidado, também é importante perceber a que não ser capaz de acompanhar o depurador conforme ele avança em determinados arquivos restritos de arquivos como resultado dessas configurações. Ver [controlando o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para obter detalhes.

Usá-la simples. O host de sessão de colaboração simplesmente precisa iniciar a depuração por meio de meios comuns no Visual Studio.

![Botão de depuração do VS](../media/vs-debug-button.png)

Depois que o depurador é anexado no lado do host, todos os convidados são automaticamente anexados também. Embora haja uma "sessão de depuração" em execução na máquina do host, todos os participantes são conectados a ele e tem sua própria exibição.

> [!TIP]
> Se você quiser alterar quando e como co depuração ocorre, você pode alterar os comportamentos padrão por meio das configurações no **Ferramentas > Opções > Live Share**.

![Depurador VS anexado](../media/vs-debugger.png)

Qualquer pessoa pode percorrer o processo de depuração que permite a alternância perfeita entre colaboradores sem precisar negociar o controle.

> [!NOTE]
> Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades de depuração por linguagem ou plataforma.

Cada colaborador pode investigar variáveis diferentes, ir para arquivos diferentes na pilha de chamadas, inspecionar variáveis e até mesmo adicionar ou remover pontos de interrupção. Recursos de edição de conjunto, em seguida, permitir que cada participante oradores controlar onde os outros estão localizados para fornecer a capacidade única de alternar diretamente entre investigando simultaneamente a diferentes aspectos do problema e depuração de modo colaborativo.

> [!NOTE]
> Enquanto estiver em uma sessão de colaboração de somente leitura, um convidado não será capaz de percorrer o processo de depuração. Eles podem, no entanto, ainda adicionar ou remover pontos de interrupção e inspecionar variáveis.

> [!TIP]
> Você também pode participar do Visual Studio e vice-versa de sessões de depuração do VS Code! Confira a [instruções do Visual Studio](vscode.md#co-debugging) no conjunto de depuração para obter mais informações.

### <a name="automatic-web-app-sharing"></a>Compartilhamento de aplicativo na web automática

Melhor ainda, para projetos de aplicativo Web ASP.NET, por padrão se o projeto do host está configurado para iniciar automaticamente um navegador da web para se conectar ao aplicativo web em execução durante a depuração, Live Share automaticamente fará o mesmo no computador de cada convidado! Isso é feito de maneira segura e o aplicativo remoto da web só está disponível para os convidados durante a sessão de depuração por padrão.

Ver [compartilhar um servidor](#share-a-server) para obter informações sobre como compartilhar o acesso ao servidor para outros tipos de projeto e/ou para a duração da sessão.

> [!TIP]
> Se não, como o comportamento de compartilhamento de navegador automatizado e quiser alterá-lo, você pode atualizar as configurações no **Ferramentas > Opções > Live Share**.

![Animação de depuração simultânea](../media/co-debug.gif)

### <a name="change-when-visual-studio-joins-debugging-sessions"></a>Alterar quando as sessões de depuração de junções de Visual Studio

Por padrão, como um convidado, você vai ser automaticamente anexados aos quando elas são compartilhadas pelo host de sessões de depuração. No entanto, em alguns casos você pode encontrar esse comportamento interrupções. Felizmente, você pode alterá-lo da seguinte maneira:

1. Vá para **Ferramentas > Opções > Live compartilhamento**
2. Alterar o **opção de sessão de depuração de junção** para um dos seguintes:

| Opção | Comportamento |
|--------|----------|
| Automático | O padrão. Como um convidado, você automaticamente se Junte a qualquer sessão de depuração compartilhado, o host é iniciado. |
| Solicitado | Como um convidado, você será solicitado se deseja ingressar em uma sessão de depuração compartilhada quando ele for iniciado pelo host. |
| Manual | Como um convidado, você precisará unir manualmente todas as sessões de depuração. Ver [desanexar e anexar novamente](#detaching-and-reattaching).|

### <a name="detaching-and-reattaching"></a>Desanexar e anexar novamente

Como um convidado, você poderá interromper a depuração temporariamente. Felizmente, você pode simplesmente clicar no ícone "parar" na barra de ferramentas de depuração para desanexar o depurador sem afetar o host ou outros convidados.

Se você tiver atualizado as configurações para que você não precisa mais a anexação automática ou se simplesmente desejar anexar novamente mais tarde, você pode simplesmente selecionar a execução desejada, sessão de depuração do "Selecione inicialização Item..." lista suspensa...

![Botão de depuração do VS](../media/vs-select-reattach.png)

... e, em seguida, clique nele para anexar.

![Botão de depuração do VS](../media/vs-reattach.png)

## <a name="share-a-server"></a>Compartilhar um servidor

De hora com a hora, como um host de sessão de colaboração você pode achar que você deseja compartilhar servidores locais adicionais ou serviços com os convidados. Isso pode variar de outros pontos de extremidade RESTful para outros servidores ou bancos de dados. Visual Studio Live Share permite que você especifique um número de porta local, opcionalmente, atribua um nome e, em seguida, compartilhá-lo com todos os convidados.

Os convidados, em seguida, serão possível acessar o servidor que você compartilhou nessa porta de seu próprio computador local na mesma porta exata. Por exemplo, se você compartilhou um servidor web **em execução na porta 3000**, o convidado pode acessar esse mesmo servidor web em execução em seus **própria máquina** em http://localhost:3000! Isso é feito por meio de um encapsulamento seguro de SSH ou SSL entre o host e convidados e autenticado por meio do serviço, portanto, você pode ter certeza de que somente aqueles na sessão de colaboração tem acesso.

> **Dica de segurança:** Como um host, você deve estar muito seletiva com as portas que você compartilha com convidados e continuar com o aplicativo portas (em vez de compartilhar uma porta de sistema). Para convidados, portas compartilhadas se comportará exatamente como fariam se o serviço do servidor/estava em execução no seu próprio computador. Isso é muito útil, mas se a porta errada for compartilhada também pode ser arriscado.

Para fins de segurança, em execução nas portas que você especificar somente os servidores estão disponíveis para outras convidadas. Felizmente, fácil adicioná-lo como a sessão de colaboração **host**. Veja como:

1. Clique no compartilhamento / estado de sessão do botão no canto superior direito e selecione "Gerenciar servidores compartilhados locais"

    ![Gerenciar servidores locais compartilhados](../media/vs-share-local-servers.png)

2. Na caixa de diálogo que aparece, clique em "Adicionar" e insira o número de porta que o servidor estiver executando em localmente, insira um nome, pressione enter, em seguida, Okey.

    ![Gerenciar servidores locais compartilhados](../media/vs-manage-local-shared-servers.png)

É só isso! O servidor na porta especificada será mapeado para localhost do cada convidado na mesma porta (a menos que essa porta já estava ocupada)!

Se a porta já está em uso no computador de um convidado, o outro é selecionado automaticamente. Felizmente, como um convidado, você pode ver uma lista de atualmente compartilhado portas (por nome, se especificado) clicando o compartilhamento / estado de sessão do botão no canto superior direito e selecionando "modo de exibição Shared servidores locais."

![Viw compartilhado servidores locais](../media/vs-view-shared-servers.png)

Observe que *convidados não podem* controlar quais portas na máquina do host são compartilhadas por motivos de segurança.

Para **parar** compartilhamento de um servidor local, o host precisa apenas clique no compartilhamento / estado de sessão do botão no canto superior direito canto como acima, selecione "Gerenciar compartilhado servidores locais", selecione a porta apropriada e clique em "Remover".

## <a name="share-a-terminal"></a>Compartilhar um terminal

O desenvolvimento moderno faz uso frequente de uma ampla gama de ferramentas de linha de comando. Felizmente, Live Share permite que você, como um host, opcionalmente, "um terminal de compartilhar" com convidados. Terminal compartilhado pode ser somente leitura ou totalmente colaborativo para que você e os convidados possam executar comandos e ver os resultados. Você pode dar a visibilidade de convidados a saída do terminal ou deixá-los a ter em mãos e executar testes, compilações ou até mesmo triagem ambiente problemas específicos que acontecem somente em seu computador.

No entanto, são os terminais **não** compartilhadas por padrão, pois eles oferecem convidados acesso somente leitura pelo menos a saída do comando executado (se não a capacidade de executar comandos em si). Dessa forma, você pode executar comandos em terminais locais sem risco livremente e compartilhar somente quando necessário, na verdade, fazer isso. Além disso, somente hosts podem começar a terminais compartilhados para impedir que os convidados da inicialização de um e fazendo algo não estiver esperando ou assistindo.

Como um host, você pode compartilhar um terminal, clicando no estado de sessão / compartilhar botão no canto superior direito e selecionando um dos itens de menu "Compartilhar Terminal".

![Menu de terminal](../media/vs-terminal-menu.png)

Neste ponto, você pode selecionar somente leitura ou leitura/gravação terminal no menu. Quando o terminal é leitura/gravação, todas as pessoas podem digitar no terminal, incluindo o que torna mais fácil interfira, se um convidado está fazendo algo que você não gosta do host. No entanto, para ser seguro, você deve **conceda acesso de leitura/gravação para os convidados somente quando você sabe que eles realmente precisam** e permanecer fiel a terminais de somente leitura para cenários em que você deseja apenas convidado para ver a saída de qualquer comando executado.

> [!NOTE]
> Se a sessão de colaboração está no modo somente leitura, terminais de somente leitura podem ser compartilhadas pelo host.

Depois de selecionar o tipo de terminal compartilhado que você deseja iniciar, um novo terminal compartilhado será exibida para todos os participantes com as permissões corretas. Enquanto o Visual Studio Code tem um suporte interno de terminal Visual Studio não tem um pronto para uso. Portanto, por padrão, nova janela que contém o terminal será exibida. No entanto, se o [partilhar partilhar Terminal extensão](https://marketplace.visualstudio.com/items?itemName=DanielGriffen.WhackWhackTerminal), Live Share criará um terminal integrado em vez disso. Visual Studio lhe dará um link para instalá-lo na primeira vez que você inicia ou ingressar em um terminal compartilhado.

![Notificação do sistema de instalação de terminal](../media/vs-terminal-install.png)

Para encerrar a sessão de terminal, simplesmente digite exit ou feche a janela do terminal e todos serão desconectados.

## <a name="session-states"></a>Estados de sessão

Depois de você ter iniciado ou associado a sessão de colaboração e ter acesso ao conteúdo compartilhado, o botão "Compartilhar" no canto superior direito atualiza sua aparência para refletir o estado da sessão de colaboração do Active Directory.

Estes são os estados que você normalmente verá:

| Estado | Botão | Descrição |
|-------|--------|-------------|
| Inativo | ![Status do VS: inativa](../media/vs-status-share.png) | Nenhuma sessão de colaboração do Active Directory e nada é compartilhado. |
| Host: Compartilhamento em andamento | ![Status do VS: compartilhar em andamento](../media/vs-status-sharing.png) | Começa uma sessão de colaboração e compartilhamento de conteúdo será iniciado em breve. |
| Host: Compartilhamento | ![Status do VS: compartilhamento o Active Directory ](../media/vs-status-active.png) | Uma sessão de colaboração está ativa e o conteúdo é compartilhado. |
| Host: Compartilhamento somente leitura | ![Status do VS: compartilhamento somente leitura](../media/vs-status-sharing-read-only.png)| Compartilhando uma sessão de colaboração de somente leitura. |
| Convidado: Ingressar na sessão | ![Status do código VS: unindo](../media/vs-status-joining.png) | Ingressar em uma sessão de colaboração existente. |
| Convidado: Ingressou | ![Status do VS: unida](../media/vs-status-joined.png) | Associado e conectado a uma sessão de colaboração do Active Directory e o recebimento de conteúdo compartilhado. |
| Convidado: Unida de somente leitura | ![Status do VS: unida de somente leitura](../media/vs-status-joined-read-only.png) | Associado e conectado a uma sessão de colaboração ativa de somente leitura. |

## <a name="guest-limitations"></a>Limitações do convidado

Enquanto atualmente, há algumas limitações que os convidados serão encontrados ao usar os recursos descritos acima, hosts de sessão de colaboração retêm toda a funcionalidade de sua ferramenta escolhida. Para obter mais informações, consulte o seguinte:

- [Suporte de idioma e plataforma](../reference/platform-support.md)
- [Suporte de extensão](../reference/extensions.md)
- [Todos os bugs importantes, solicitações de recursos e limitações](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

## <a name="next-steps"></a>Próximas etapas

Confira estes artigos adicionais para obter mais informações.

- [Início Rápido: Compartilhar seu primeiro projeto](../quickstart/share.md)
- [Início Rápido: Junte-se a primeira sessão](../quickstart/join.md)
- [Como: Colaborar usando o Visual Studio Code](vscode.md)
- [Requisitos de conectividade do Live Share](../reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](../reference/security.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
