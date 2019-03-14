---
title: Colabore usando o Visual Studio Code – Visual Studio Live Share | Microsoft Docs
description: Um conjunto de instruções de colaboração para Visual Studio Code e Live Share.
ms.custom: ''
ms.date: 04/27/2018
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
ms.openlocfilehash: 9285fef38fea9bb164892775521ed2a28fe9ef1b
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255227"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>Como: Colaborar usando o Visual Studio Code

Pronto para obter colaborando com Live Share no VS Code?  Nesse caso, você está no lugar certo! Neste artigo, vamos percorrer você como usar alguns dos recursos específicos na extensão do Visual Studio Live Share para Visual Studio Code.

Observe que todas as atividades de colaboração descritas aqui envolvem uma única **host de sessão de colaboração** e um ou mais **convidados**. O host é a pessoa que iniciou a sessão de colaboração, e qualquer pessoa que ingressa na sessão é um convidado.

*Procurando um resumo resumido? Confira a [compartilhar](../quickstart/share.md) ou [junção](../quickstart/join.md) guias de início rápido em vez disso.*

> [!TIP]
> Você sabia que pode *ingressar em sua própria sessão de colaboração*? Isso permite que você experimente o Live Share por conta própria ou crie uma instância do Visual Studio ou do VS Code e conecte-a remotamente. Você pode até usar a mesma identidade em ambas as instâncias. Confira!

## <a name="installation"></a>Instalação

Antes de começar, você precisará ter certeza de que você tem uma versão do Visual Studio Code instalado que atende aos requisitos de núcleo do Live Share. Você precisará **Visual Studio Code (1.22.0 ou superior)** em execução em:

- **Windows**: 7, 8.1 ou 10

- **macOS**: Sierra (10.12) e superiores apenas.
    - _El Capitan (10.11) e a seguir não têm suporte atualmente devido ao [requisitos do .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872315)._

- **Linux**: área de trabalho 64-bit Ubuntu 16.04 +, estação de trabalho Fedora 27 +, CentOS 7

    - Compartilhamento ao vivo requer um número de [pré-requisitos do Linux](#linux-install-steps) você pode ser solicitado a instalar.
    - _Não há suporte para Linux de 32 bits devido à [requisitos do .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872314)._
    - ARM também não é suportado atualmente.
    - Consulte a [Linux instalar detalhes](../reference/linux.md) artigo para obter detalhes sobre como usar as distribuições de downstream e outras.

Depois disso, o download e a instalação da extensão do Visual Studio Live Share são muito simples:

1. Instalar <a href="https://code.visualstudio.com/">Visual Studio Code</a>
2. [Baixar](https://aka.ms/vsls-dl/vscode) e instalar a extensão do Visual Studio Live Share do marketplace.
3. Recarregue o Visual Studio Code
4. Aguarde até que as dependências baixar e instalar (consulte barra de status).<br/>
    ![Concluindo a instalação](../media/vscode-finishing-install.png)
5. **Linux**: Se você receber uma notificação sobre como instalar bibliotecas ausentes:
    1. Clique em "Instalar" na notificação.
    2. Insira sua senha de administrador (sudo) quando solicitado.
    3. Reinicie o VS Code quando terminar.

Ao baixar e usar o Visual Studio Live Share, você concorda com os [termos de licença](https://aka.ms/vsls-license) e a [política de privacidade](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Confira [Solução de problemas](../troubleshooting.md) caso tenha problemas.

[![Download](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Etapas de instalação do Linux

Linux é um ambiente altamente variável e com o enorme número de distribuições e ambientes de desktop pode ser complicado para começar a trabalhar. Se você continuar com as versões com suporte do **área de trabalho do Ubuntu** (16.04 +) ou **estação de trabalho do Fedora** (27 +), **CentOS 7** e usar apenas **distribuições oficiais do VS Código**, você deve encontrar o processo simples. No entanto, se você estiver usando uma configuração não padrão ou a distribuição de downstream, você pode ou não podem ser executadas em algumas dificuldades. Ver [detalhes da instalação Linux](../reference/linux.md) para obter mais informações.

#### <a name="install-linux-prerequisites"></a>Instale os pré-requisitos do Linux

Algumas distribuições do Linux não têm bibliotecas que Live Share precisa para funcionar. Por padrão, Live Share tenta detectar e instalar os pré-requisitos do Linux para você. Você verá uma notificação quando o Live Share encontra um problema que pode ser originado de bibliotecas ausentes solicitando sua permissão para instalá-los.

![Notificação do sistema mostrando a mensagem que pré-requisitos do Linux estão ausentes](../media/vscode-linux-prereq-missing.png)

Quando você clica em "Instalar", aparecerá uma janela de terminal em que você precisará inserir sua senha de administrador (sudo) para continuar. Supondo que ele for concluído com êxito, reinicie o Visual Studio Code, você deve estar pronto! Talvez você queira fazer check-out **[dicas de distribuição](../reference/linux.md#tips-by-distribution)** para outras dicas e soluções alternativas, se existir alguma.

Se você vir uma mensagem indicando que o script não dá suporte a sua distribuição, consulte **[dicas para distribuições de suporte da comunidade](../reference/linux.md#tips-for-community-supported-distros)** para obter informações a comunidade tiver compartilhado conosco.

Se você **prefere não ter o VS Code, execute o comando para você**, você também pode para executar novamente a versão mais recente deste script a qualquer momento manualmente, executando o seguinte comando em uma janela de Terminal:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Integração de navegador do Linux

Live do Visual Studio normalmente compartilham **não exige etapas adicionais de instalação** para habilitar a integração de navegador no Linux.

Embora incomum, determinadas distribuições você **pode ser notificado de que sua senha de administrador (sudo) é necessária** para concluir o processo de instalação. Uma janela do terminal será exibida informando a você onde o iniciador do navegador será instalado. Basta digitar a senha quando solicitado e pressione enter após a conclusão da instalação para fechar a janela do terminal.

Você pode ler mais sobre por que isso é necessário e onde Live compartilham coloca arquivos  **[aqui](../reference/linux.md#linux-browser-integration)**. Observe, mesmo se não for possível obter o trabalho de integração de navegador, você ainda pode  **[sessões de colaboração de junção manualmente](../use/vscode.md#join-manually)**.

## <a name="sign-in"></a>Entrar

Para colaborar, você precisará entrar no Visual Studio Live Share, portanto, todo mundo sabe quem é você. Isso é puramente uma medida de segurança e faz **não** consentir qualquer marketing ou outras atividades de pesquisa. Você pode entrar usando uma conta pessoal da Microsoft (por exemplo, @outlook.com), trabalho com suporte da Microsoft ou conta de Estudante (AAD) ou uma conta do GitHub. É fácil entrar.

**Clique em** sobre o status de "Compartilhamento" barra item ou pressione **Ctrl + Shift + P / Cmd + Shift + P** e selecione o "compartilhamento ao vivo: Comando entrar com navegador".

![No botão entrar de código do VS](../media/vscode-sign-in-button.png)

Uma notificação será exibida solicitando que você entrar usando seu navegador da web. Clicar em "Iniciar entrar" abrirá um navegador para que você possa usar para concluir o processo de logon. Basta feche o navegador quando terminar.

![Notificação do sistema pedindo para entrar usando um navegador da web](../media/vscode-sign-in-toast.png)

> **Usuários do Linux:** Você será solicitado a inserir um código de usuário, se você estiver usando uma versão mais antiga do Live Share (v0.3.295 ou abaixo). Atualizar para a versão mais recente da extensão ou clique no "tendo problemas?" Vincular depois de entrar para ver o código. Ver [abaixo para obter detalhes](#sign-in-using-a-user-code).

Se o Visual Studio Code não estiver capturando sua entrada depois de concluir o processo de logon no navegador, consulte [entrar usando um código de usuário](#sign-in-using-a-user-code). Caso contrário, fazer check-out [solução de problemas](../troubleshooting.md#sign-in) para obter mais dicas.

### <a name="sign-in-using-a-user-code"></a>Conecte-se usando um código de usuário

Se você estiver executando em problemas com o VS Code não pegar uma entrada concluída, você pode inserir um código de usuário"" em vez disso.

1. Pressione **Ctrl + Shift + P / Cmd + Shift + P** e execute o "compartilhamento ao vivo: Comando entrar com o código do usuário".

2. Um navegador deve aparecer para que você usa para concluir o processo de logon.

    > [!NOTE]
    > Se um navegador não aparecer automaticamente, abra [nesse local](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) em um navegador e de entrada.

3. Quando terminar, clique em "problemas? Clique aqui para obter instruções de código do usuário"para ver o código do usuário.

    ![Imagem do código do usuário no navegador](../media/vscode-user-code-browser.png)

4. Copie o código do usuário.

5. Por fim, cole o código de usuário no campo de entrada que apareceu quando você executou o comando e pressione enter para concluir o processo de logon.

    ![Imagem do campo de entrada de código do usuário](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>Usando o Live Share viewlet

Depois de instalar o Visual Studio Live Share, uma guia personalizada será adicionada à barra de atividade do VS Code. Nessa guia, você pode acessar todas as funções do Live Share para colaborar. Além disso, quando você compartilha ou ingressar em uma sessão de colaboração, um modo de exibição também aparecerão na guia Explorer para acessar todas essas funções.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

Com esses modos de exibição, você pode ver o local do participante no código compartilhado, clique em um participante para segui-las, concentre-se os participantes, acessar servidores compartilhados terminais e muito mais.

## <a name="using-the-scoped-command-menu"></a>Usando o menu de comando no escopo

Além disso, todas as funções do Visual Studio Live Share estão disponíveis no Visual Studio Code "Paleta" que pode ser acessada pressionando Ctrl + Shift + P / Cmd + Shift + P ou F1. Você pode encontrar uma lista completa de comandos, digitando "compartilhamento ao vivo".

Uma vez que essa lista pode se tornar longa, talvez seja mais fácil tirar proveito de um menu de comando de escopo disponível na barra de status. Clicar na entrada / ícone de estado de sessão na barra de status abrirá imediatamente uma contextualizadas lista de comandos que estão disponíveis para uso.

![Ícone de estado de sessão de código do VS](../media/vscode-share-state.png)

## <a name="share-a-project"></a>Compartilhar um projeto

Depois de baixar e instalar o Visual Studio Live Share, siga estas etapas para iniciar uma sessão de colaboração e convidar um colega para trabalhar com você.

1. **Entrar**

    Depois de instalar a extensão de compartilhamento ao vivo, recarregar e aguardando as dependências concluir a instalação, você desejará entrar para permitir que outros colaboradores Saiba quem é você. Ver [entrar](#sign-in) para obter mais detalhes.

2. **Abrir uma pasta**

    Use o fluxo de trabalho normal para abrir uma pasta, projeto ou solução que você gostaria de compartilhar com seus convidados.

3. **[Opcional] Atualizar arquivos ocultos ou excluídos**

    Por padrão, o Live Share **oculta** quaisquer arquivos/pastas referenciadas nos arquivos. gitignore em suas pastas compartilhadas de convidados. **Ocultando** um arquivo impede que ele apareça na árvore de arquivos do convidado. **Excluindo** um arquivo aplica uma regra mais rígida que impedirão o Live Share de abri-lo para o convidado em situações como ir para uma definição ou se você depurar o arquivo durante a depuração ou sendo "seguido". Se você quiser ocultar/excluir arquivos diferentes, uma **. vsls.json** arquivo pode ser adicionado ao seu projeto com essas configurações. Ver [controlando o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para obter detalhes.

4. **Iniciar uma sessão de colaboração**

    Agora, simplesmente **clique em** barra item ou uma ocorrência de status de "Compartilhamento" **Ctrl + Shift + P / Cmd + Shift + P** e selecione "compartilhamento ao vivo: Iniciar uma sessão de colaboração (compartilhamento) ".

    ![Botão compartilhar](../media/vscode-share-button.png)

    > [!NOTE]
    > Você poderá ser solicitado por seu software de firewall da área de trabalho para permitir que o agente Live Share abrir uma porta na primeira vez que você compartilha. Aceitar isso é totalmente opcional, mas permite que um seguro "modo direto" para melhorar o desempenho quando a pessoa que você está trabalhando com está na mesma rede que você esteja. Ver [alterando o modo de conexão](../reference/connectivity.md#changing-the-connection-mode) para obter detalhes.

    Um link de convite será copiado automaticamente para a área de transferência. Quando aberto em um navegador, esse link permite que outras pessoas ingressar em uma nova sessão de colaboração que compartilha o conteúdo dessas pastas com eles.

    Você também verá a transição de item de barra de status "Share" para representar o estado de sessão. Ver [estado de sessão](#session-states) informações abaixo para ver como fica isso.

    Observe que, se você precisa obter o link de convite novamente depois de começar o compartilhamento, você acessá-lo novamente clicando no ícone de barra de status de estado de sessão e selecionar "Convidar outras pessoas (Copiar Link)".

5. **[Opcional] Habilitar o modo somente leitura**

    Depois de iniciar sua sessão de colaboração, você pode definir a sessão a ser somente leitura para impedir que os convidados façam edições no código que está sendo compartilhado.

    Após o compartilhamento, você receberá uma notificação de que o link de convite foi copiado para a área de transferência. Em seguida, você pode selecionar a opção de fazer a sessão somente leitura.

    ![Modo de somente leitura do código VS](../media/vscode-read-only-toast.png)

6. **Enviar a alguém o link**

    Enviar link por email, Slack, Skype, etc., para aqueles que deseja convidar. Observe que, considerando o nível de acesso Live Share sessões podem fornecer aos convidados, **você só deve compartilhar com pessoas confiáveis** e considere as implicações do que você está compartilhando.

    > **Dica de segurança:** Deseja entender as implicações de segurança de alguns dos recursos do Live Share? Confira a [segurança](../reference/security.md) artigo.

    Se o convidado é convidado tiver perguntas, o "[guia de início rápido: Junte-se a primeira sessão](../quickstart/join.md)"artigo fornece algumas informações sobre colocar em execução como convidado.

7. **[Opcional] Aprovar o convidado**

    Por padrão, os convidados ingressarão automaticamente sua sessão de colaboração e você será notificado quando eles estiverem prontos para trabalhar com você. Enquanto essa notificação oferece a opção para removê-los da sessão, você também pode optar em vez disso, exigem uma "aprovação" explícita para qualquer pessoa unindo.

    Para habilitar esse recurso, simplesmente adicione o seguinte ao Settings:

         "liveshare.guestApprovalRequired": true

    Depois que essa configuração ativada, uma notificação solicitará que você aprovar o convidado para que possam participar.

    ![Solicitação de aprovação do Visual Studio Code junção](../media/vscode-join-approval.png)

    Ver [convites e acesso ao ingresso](../reference/security.md#invitations-and-join-access) para obter detalhes adicionais sobre as considerações de segurança do convite.

Isso é tudo!!

### <a name="stop-the-collaboration-session"></a>Parar a sessão de colaboração

Como um host, você pode interromper o compartilhamento completamente e encerrar a sessão de colaboração a qualquer hora abrindo o modo de exibição do Live Share no Explorer ou na guia personalizada Live Share e selecionando o ícone "Parar a sessão de colaboração".

![Parar a sessão de colaboração](../media/vscode-end-collaboration-viewlet.png)

Todos os convidados serão notificados de que a sessão foi encerrada.  Depois que a sessão foi encerrada, os convidados não poderá acessar o conteúdo e todos os arquivos temporários são limpos automaticamente.

Está tendo problemas com o compartilhamento? Fazer check-out [solução de problemas](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Ingressar em uma sessão de colaboração

Depois de baixar e instalar o Visual Studio Live Share, convidados só precisará executar algumas etapas para ingressar em uma sessão de colaboração hospedada. Há duas maneiras para unir: [por meio do navegador](#join-via-the-browser) e [manualmente](#join-manually).

> **Dica de segurança:** Como um convidado a ingressar em uma sessão de colaboração, é importante entender que os hosts podem restringir o acesso a determinados arquivos ou recursos. Deseja entender as implicações de segurança de alguns dos recursos e configurações de compartilhamento ao vivo? Confira a [segurança](../reference/security.md) artigo.

### <a name="join-via-the-browser"></a>Junte-se por meio do navegador

A maneira mais fácil para ingressar em uma sessão de colaboração é simplesmente abrir o link de convite em um navegador da web. Aqui está o que você pode esperar quando você segue esse fluxo.

1. **Entrar**

    Depois de instalar a extensão de compartilhamento ao vivo, recarregar e aguardando as dependências concluir a instalação, você desejará entrar para permitir que outros colaboradores Saiba quem é você. Ver [entrar](#sign-in) para obter mais detalhes.

2. **Clique no link de convite / abrir o convite em seu navegador**

    Agora, basta abrir (ou abrir novamente) no link de convite em um navegador.

    > **Observação**: Se você ainda não tiver instalado a extensão de compartilhamento ao vivo, você verá com links para o marketplace de extensão. Instalar a extensão e reinicie sua ferramenta e tente novamente.

    Você deve ser notificado que o navegador deseja iniciar uma ferramenta de Live Share habilitado. Se você permitir que ele inicie a ferramenta selecionada, você estará conectado à sessão de colaboração, depois que ele for iniciado.

    ![Página de junção](../media/join-page.png)

    Se o host estiver offline, você será notificado no momento em vez disso. Você pode, em seguida, entre em contato com o host e peça-lhe para compartilhar novamente.

    > [!NOTE]
    > Certifique-se de que você já **iniciado a ferramenta de pelo menos uma vez** depois de instalar a extensão do Visual Studio Live Share e permitido a instalação seja concluída antes de abertura/re-opening a página de convite. Ainda está com problemas? Ver [unir manualmente](#join-manually).

3. **Colaborar**

    É só isso! Em alguns instantes você estará conectado e você pode começar a colaborar.

    Você verá a transição do botão "Share" para transmitir um "estado de sessão". Ver [estado de sessão](#session-states) informações abaixo para ver como fica isso.

    Você será automaticamente levado para o arquivo de que host estiver atualmente editando depois que a junção for concluída.

### <a name="join-manually"></a>Unir manualmente

Você pode unir manualmente sem usar um navegador da web que pode ser útil em situações em que a ferramenta que você deseja usar já está em execução, você deseja usar outra ferramenta que faria normalmente, ou se você estiver tendo problemas com a introdução convidar links trabalhar por algum motivo. O processo é fácil:

1. **Entrar**

    Depois de instalar a extensão de compartilhamento ao vivo, recarregar e aguardando as dependências concluir a instalação, você desejará entrar para permitir que outros colaboradores Saiba quem é você. Ver [entrar](#sign-in) para obter mais detalhes.

2. **Use o comando de junção**

    Abra a guia personalizada do Live Share na barra de atividade do VS Code e selecione "junção sessão de colaboração..." ícone ou entrada.

    ![Ícone de viewlet de junção](../media/vscode-join-viewlet.png)

3. **Cole o link de convite**

    Cole a URL do convite, você foi enviado e pressione enter para confirmar.

4. **Colabore!**

    É só isso! Você deve estar conectado à sessão de colaboração momentaneamente.

    Você verá a transição do botão "Share" para transmitir um "estado de sessão". Ver [estado de sessão](#session-states) informações abaixo para ver como fica isso.

    Você será automaticamente levado para o arquivo de que host estiver atualmente editando depois que a junção for concluída.

### <a name="leave-the-collaboration-session"></a>Deixe a sessão de colaboração

Como um convidado, você pode deixar a sessão de colaboração sem encerrá-la para outras pessoas simplesmente fechando a janela do VS Code. Se você preferir manter a janela aberta, você pode abrir a exibição do Gerenciador de compartilhamento ao vivo ou a guia personalizada do Live Share e selecione o ícone de "Sair da sessão de colaboração".

![Ícone de folhas de sessão](../media/vscode-leave-session-viewlet.png)

Todos os arquivos temporários são automaticamente limpas para que nenhuma ação adicional é necessária.

Está tendo problemas com unindo? Fazer check-out [solução de problemas](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Coedição

Depois que um convidado ingressou em uma sessão de colaboração, todos os colaboradores imediatamente será capazes de ver as edições e as seleções em tempo real de uns dos outros. Tudo o que você precisa fazer é pegar um arquivo no Gerenciador de arquivos e começar a editar. Hosts e convidados verá edições como torná-los e contribuir com a mesmos, tornando fácil iterar e prego rapidamente para reduzir as soluções.

> [!NOTE]
> Ingressar em uma sessão de colaboração de somente leitura impede que convidados sejam capazes de fazer edições em arquivos. Um host pode [habilitar o modo somente leitura quando eles compartilham](#share-a-project). Como um convidado, você pode informar se você se associou a uma sessão somente leitura, observando sua [estado de sessão](#session-states).

![Captura de tela mostrando conjunta de edição](../media/vscode-coedit.png)

> [!NOTE]
> Editar co tem limitações para determinados idiomas. Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades por linguagem.

Além de cursores e edições, as seleções feitas também são visíveis para todos os participantes no mesmo arquivo. Isso torna mais fácil realçar onde os problemas podem existir ou transmitir ideias.

![Captura de tela mostrando o realce](../media/vscode-highlight.png)

Melhor ainda, você e outros participantes podem navegar para qualquer arquivo no projeto compartilhado. Você pode editar juntos ou de forma independente que significa que você pode alternar diretamente entre a investigação, fazer pequenos ajustes e completa de colaboração por edição.

As edições resultantes são persistidas na máquina do host em Salvar existe há necessidade de sincronizar, enviar por push ou enviar arquivos ao redor quando você terminar edição. As edições são "apenas there".

> **Dica de segurança:** Dada a todos os participantes podem independentemente navegar e editar arquivos, como um host, você talvez queira restringir quais arquivos convidados são capazes de acessar em seu projeto por meio de um. vsls.json arquivo. Como um convidado, também é importante perceber que você não poderá ver a certos arquivos como resultado dessas configurações. Ver [controlando o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para obter detalhes.

### <a name="changing-participant-flag-behaviors"></a>Alterando os comportamentos do sinalizador de participante

Por padrão, o Visual Studio Live Share exibe automaticamente um sinalizador de"" ao lado do cursor de um participante em foco, ou quando eles editar, realce, ou move seu cursor. Em alguns casos, você talvez prefira alterar esse comportamento.

Simplesmente **Editar Settings** (arquivo > Preferências > Configurações), adicione uma das linhas a seguir e, em seguida, reinicie o VS Code:

| Configuração | Comportamento |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | O sinalizador só fica visível quando você focaliza o cursor. |
| ``"liveshare.nameTagVisibility":"Activity"`` | Esse é o padrão. O sinalizador é visível ao focalizar ou se o participante edita, destaca ou move o cursor. |
| ``"liveshare.nameTagVisibility":"Always"`` | O sinalizador está sempre visível. |

## <a name="following"></a>A seguir

Às vezes, você precisa explicar um problema ou um design que abrange vários arquivos ou locais no código. Nessas situações, pode ser útil seguir temporariamente um colega quando eles passam ao longo do projeto. Por esse motivo, quando você ingressa em uma sessão de colaboração você será automaticamente "seguir" host. Ao seguir alguém, seu editor permanecerão em sincronizado com sua posição de rolagem e de arquivo aberta no momento.

> [!NOTE]
> Por padrão, o Live Share compartilhamentos aberto arquivos externos à pasta compartilhada. Se você quiser desabilitar esse recurso, atualize `liveshare.shareExternalFiles` Live Share para `false` em Settings.

Para começar a seguir um participante (como um host ou convidado), clique em seu nome na lista dos participantes na exibição do Explorador de compartilhamento ao vivo ou guia personalizada. O círculo ao lado do nome preencherá para indicar que você está seguindo-los.

![Siga do VS Code da viewlet](../media/vscode-follow-multiple-viewlet.png)

Como alternativa, você pode clicar no ícone de pino no canto superior direito do grupo de editor ou pressione **Ctrl + Alt + F / Cmd + Alt + F**.

![Pin de código do VS](../media/vscode-pin.png)

> [!NOTE]
> Se mais de uma outra pessoa está em sessão de colaboração, você será solicitado para selecionar o participante que devem ser seguidas.
>
>![Captura de tela mostrando a lista de colaboradores](../media/vscode-list-collaborators.png)

Uma vez que a seguir está vinculada a um grupo de editor, você pode usar o modo divisão (ou layout de grade!) para ter um grupo que está seguindo um participante e um grupo que não é. Isso permite que você passivamente siga alguém enquanto também trabalha em algo independentemente. Com um grupo do editor selecionado, você pode selecionar um participante de ter esse grupo segui-las na lista de participantes.

![Pin de código VS no modo de exibição de divisão](../media/vscode-follow-split.png)

Para tornar mais fácil do "modo de acompanhamento" e começar a editá-lo por conta própria, você irá parar automaticamente a seguir se qualquer uma dessas ocorrem:

1. Começar a editar o arquivo de ativo no momento
1. Abrir um arquivo diferente
1. Fechar o arquivo ativo no momento

Além disso, você pode interromper explicitamente as seguir alguém clicando no ícone de pino novamente ou atingindo **Ctrl + Alt + F / Cmd + Alt + F**.

## <a name="listing-participants"></a>Listagem de participantes

Uma maneira rápida de verificar quem está na sessão de colaboração é examinar a lista de participantes na exibição do Explorador de compartilhamento ao vivo ou guia personalizada. Os modos de exibição mostrará todos os participantes em sua sessão.

![Ícone de barra de status de usuário do captura de tela mostrando](../media/vscode-explorer-view.png)

Clicar em qualquer participante nessa lista serão segui-los em seu grupo de editor ativo.

Como alternativa, você pode atingir **Ctrl + Shift + P / Cmd + Shift + P** e selecione o "compartilhamento ao vivo: Comando list participantes"ou **clique** sobre o item da barra de status que mostra o número de participantes em sua sessão.

![Ícone de barra de status de usuário do captura de tela mostrando](../media/vscode-user-status.png)

Em seguida, será exibida uma lista de todos os participantes da sessão. Ao contrário de clicar no ícone de pino, essa lista é exibida mesmo se houver apenas uma outra pessoa na sessão com você para que você pode ver sempre rapidamente em que outra pessoa está localizada. Para fins de conveniência, como o ícone de pino, em seguida, você pode escolher um dos participantes da lista a segui-los. Pressione escape sair, em vez disso.

## <a name="focusing"></a>Concentrando-se

Ocasionalmente, talvez você queira todos em uma sessão de colaboração para vêm e dar uma olhada em algo que está fazendo. Compartilhamento ao vivo permite solicitar que todos "concentram" você com uma notificação que torna mais fácil para que elas sigam você de volta.

Abra a guia personalizada do Live Share na barra de atividade de código do VS ou a exibição do Gerenciador de compartilhamento ao vivo e selecione o ícone "Se concentrar participantes".

![Ícone de viewlet de foco](../media/vscode-focus-viewlet.png)

Depois de executar o comando, todos na sessão de colaboração, em seguida, receberá uma notificação que você solicitou a sua atenção.

![Notificação do sistema de foco](../media/vscode-focus-toast.png)

Pode, em seguida, basta clicar em "Follow" à direita da notificação de quando eles estiverem prontos para colocar o foco em você.

## <a name="co-debugging"></a>Codepuração

O recurso de depuração colaborativo do Visual Studio Live Share é uma maneira exclusiva e poderosa para depurar um problema. Além de permitir uma experiência de colaboração solucionar problemas, também você e outros participantes em sua sessão, a capacidade de investigar os problemas que podem ser específicos do ambiente, fornecendo uma sessão de depuração compartilhada no computador do host.

> **Dica de segurança:** Dada a todos os participantes podem independentemente navegar e editar arquivos, como um host, você talvez queira restringir quais arquivos convidados são capazes de acessar em seu projeto por meio de um. vsls.json arquivo. Você também deve estar ciente de que o acesso de Console/REPL significa que os participantes podem executar comandos em seu computador para que você só deve depurar junto com aqueles que você confia. Como um convidado, também é importante perceber a que não ser capaz de acompanhar o depurador conforme ele entra em determinados arquivos restritos de arquivos como resultado dessas configurações. Ver [controlando o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para obter detalhes.

Usá-la simples.

1. Certifique-se de que o host e todos os convidados têm a extensão de depuração apropriada instalada. (Tecnicamente isso nem sempre é necessário, mas geralmente é uma boa ideia.)

2. Como o host, se ainda não estiver configurado para o projeto, você deve [configurar Launch](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) para depurar o aplicativo do VS Code, como você faria normalmente. Nenhuma configuração especial é necessária.

3. Em seguida, o host pode iniciar a depuração usando o botão na guia depuração como de costume.

    ![Botão de depuração de código do VS](../media/vscode-debug-button.png)

    > [!TIP]
    > Você também pode participar em sessões do VS Code e vice-versa de depuração do Visual Studio! Confira a [instruções do Visual Studio](vs.md#co-debugging) no conjunto de depuração para obter mais informações.

Depois que o depurador é anexado no lado do host, todos os convidados serão anexados automaticamente. Embora haja uma "sessão de depuração" em execução na máquina do host, todos os participantes são conectados a ele e tem sua própria exibição.

![Depurador do VS Code anexado](../media/vscode-debugger.png)

Qualquer pessoa pode percorrer o processo de depuração que permite a alternância perfeita entre colaboradores sem precisar negociar o controle.

> [!NOTE]
> Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades de depuração por linguagem ou plataforma.

Cada colaborador pode investigar variáveis diferentes, ir para arquivos diferentes na pilha de chamadas, inspecionar variáveis e até mesmo adicionar ou remover pontos de interrupção. Recursos de edição de conjunto, em seguida, permitir que cada participante oradores controlar onde os outros estão localizados para fornecer a capacidade única de alternar diretamente entre investigando simultaneamente a diferentes aspectos do problema e depuração de modo colaborativo.

> [!NOTE]
> Enquanto estiver em uma sessão de colaboração de somente leitura, um convidado não será capaz de percorrer o processo de depuração. Eles podem, no entanto, ainda adicionar ou remover pontos de interrupção e inspecionar variáveis.

![Animação de depuração simultânea](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>Alterar quando as sessões de depuração de junções de VS Code

Por padrão, como um convidado, você vai ser automaticamente anexados aos quando elas são compartilhadas pelo host de sessões de depuração. No entanto, em alguns casos, você pode encontrar esse comportamento interrupções. Felizmente, você pode alterá-lo da seguinte maneira:

Simplesmente **Editar Settings** (arquivo > Preferências > Configurações), adicione uma das linhas a seguir e, em seguida, reinicie o VS Code:

| Configuração | Comportamento |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | O padrão. Como um convidado, você automaticamente se Junte a qualquer sessão de depuração compartilhado, o host é iniciado. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | Como um convidado, você será solicitado se deseja ingressar em uma sessão de depuração compartilhada quando ele for iniciado pelo host. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | Como um convidado, você precisará unir manualmente todas as sessões de depuração. Ver [desanexar e anexar novamente](#detaching-and-reattaching). |

### <a name="detaching-and-reattaching"></a>Desanexar e anexar novamente

Como um convidado, você poderá interromper a depuração temporariamente. Felizmente, você pode simplesmente clicar no ícone "parar" na barra de ferramentas de depuração para desanexar o depurador sem afetar o host ou outros convidados.

![Botão de parada de depurador de código do VS](../media/vscode-debug-stop.png)

Se você tiver atualizado as configurações para que você não precisa mais a anexação automática ou se você simplesmente deseja anexar novamente mais tarde, você pode fazer isso pressionando **Ctrl + Shift + P / Cmd + Shift + P** ou **clicando em** sobre o item de barra de status de estado de sessão e selecionando "Anexar para uma depuração de sessão compartilhada".

![Anexar o depurador VS Code](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>Compartilhamento de aplicativo em execução em um navegador

Visual Studio Code não tem o conceito de um conhecido "web application porta" como o Visual Studio para tipos de projeto, como o ASP.NET. No entanto, se você estiver unindo uma sessão de colaboração de um host do Visual Studio, você pode automaticamente ver seu navegador padrão quando a depuração começa, que é automaticamente conectada para execução de aplicativos do host. Ver [recursos do Visual Studio](vs.md#automatic-web-app-sharing) para obter mais detalhes.

Como um host, você pode obter algo semelhante ao compartilhar manualmente o aplicativo ou outros pontos de extremidade, como os serviços RESTful usando o recurso de "Servidor de Local de compartilhamento". Convidados do Visual Studio e o VS Code, em seguida, podem abrir um navegador na mesma porta do localhost para ver o aplicativo em execução.  Ver [compartilhar um servidor](#share-a-server) para obter mais detalhes.

## <a name="share-a-server"></a>Compartilhar um servidor

De tempos em tempos, como um host de sessão de colaboração, você pode achar que você deseja compartilhar um aplicativo web ou outro executado localmente servidores ou serviços com convidados. Isso pode variar de outros pontos de extremidade RESTful para bancos de dados e outros servidores. Visual Studio Live Share permite que você especifique um número de porta local, opcionalmente, atribua um nome e, em seguida, compartilhá-lo com todos os convidados.

Os convidados, em seguida, serão possível acessar o servidor que você compartilhou nessa porta de seu próprio computador local na mesma porta exata. Por exemplo, se você compartilhou um servidor web **em execução na porta 3000**, o convidado pode acessar esse mesmo servidor web em execução em seus **própria máquina** em http://localhost:3000! Isso é feito por meio de um encapsulamento seguro de SSH ou SSL entre o host e convidados e autenticado por meio do serviço, portanto, você pode ter certeza de que somente aqueles na sessão de colaboração tem acesso.

> **Dica de segurança:** Como um host, você deve estar muito seletiva com as portas que você compartilha com convidados e continuar com o aplicativo portas (em vez de compartilhar uma porta de sistema). Para convidados, portas compartilhadas se comportará exatamente como fariam se o serviço do servidor/estava em execução no seu próprio computador. Isso é muito útil, mas se a porta errada for compartilhada também pode ser arriscado.

Para fins de segurança, em execução nas portas que você especificar somente os servidores estão disponíveis para outras convidadas. Felizmente, é fácil adicioná-lo como a sessão de colaboração **host**. Veja como:

1. Abra a guia personalizada do Live Share na barra de atividade de código do VS ou a exibição do Gerenciador de compartilhamento ao vivo e selecione o "servidor de compartilhamento..." entrada ou clique no ícone.

    ![Servidor do local de compartilhamento de código do VS](../media/vscode-share-local-server-viewlet.png)<br />

1. Insira o número de porta que o servidor está em execução no e, opcionalmente, um nome.

    ![Captura de tela do prompt de número de porta](../media/vscode-enter-port.png)<br />

É só isso! O servidor na porta especificada será mapeado para localhost do cada convidado na mesma porta (a menos que essa porta já estava ocupada)!

Se a porta já está em uso no computador do convidado, o outro é selecionado automaticamente. Felizmente, como um convidado, você pode ver uma lista de portas atualmente compartilhadas (por nome, se especificado) na exibição do Explorador de compartilhamento ao vivo ou uma guia personalizada na barra de atividade do VS Code e aparência sob a lista de servidores compartilhados. Selecionando uma entrada é aberto nesse servidor em seu navegador. Você pode também clique com botão direito e selecione a opção para copiar o link para o servidor para a área de transferência.

![Servidor do local de acesso do código VS](../media/vscode-access-shared-server-viewlet.png)<br />

Observe que *convidados não podem* controlar quais portas na máquina do host são compartilhadas por motivos de segurança.

Para **parar** compartilhamento de um servidor local como o host, passe o mouse sobre a entrada do servidor na lista de servidores compartilhados na exibição do Explorador de compartilhamento ao vivo ou guia personalizada e clique no ícone "Remover o compartilhamento de servidor".

![Pare o código VS compartilhamento de servidor](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>Compartilhar um terminal

O desenvolvimento moderno faz uso frequente de uma ampla gama de ferramentas de linha de comando. Felizmente, Live Share permite que você, como um host, opcionalmente, "um terminal de compartilhar" com convidados. Terminal compartilhado pode ser somente leitura ou totalmente colaborativo para que você e os convidados possam executar comandos e ver os resultados. Você pode dar a visibilidade de convidados a saída do terminal ou deixá-los a obter práticos e execução de testes, compilações ou problemas específicos do ambiente de triagem, mesmo que acontecem somente em seu computador.

No entanto, são os terminais **não** compartilhadas por padrão, pois eles oferecem convidados acesso somente leitura pelo menos a saída do comando executado (se não a capacidade de executar comandos em si). Dessa forma, você pode executar comandos em terminais locais sem risco livremente e compartilhar somente quando necessário, na verdade, fazer isso. Além disso, somente hosts podem começar a terminais compartilhados para impedir que os convidados da inicialização de um e fazendo algo não estiver esperando ou assistindo.

Como um host, você pode compartilhar um terminal abrindo a guia personalizada Live Share na barra de atividade do VS Code ou na exibição de Live compartilhar Explorer e selecionando o "compartilhamento de servidor..." entrada ou clicando no ícone.

![Terminal de compartilhamento de código do VS](../media/vscode-share-terminal-viewlet.png)<br />

Neste ponto, você pode selecionar somente leitura ou leitura/gravação terminal no menu. Quando o terminal é leitura/gravação, todas as pessoas podem digitar no terminal, incluindo o que torna mais fácil interfira, se um convidado está fazendo algo que você não gosta do host. No entanto, para ser seguro, você deve **conceda acesso de leitura/gravação para os convidados somente quando você sabe que eles realmente precisam** e permanecer fiel a terminais de somente leitura para cenários em que você deseja apenas convidado para ver a saída de qualquer comando executado.

> [!NOTE]
> Se a sessão de colaboração está no modo somente leitura, terminais de somente leitura podem ser compartilhadas pelo host.

![Somente leitura ou leitura/gravação seleção](../media/vscode-share-terminal-ro-rw.png)<br />

Depois de selecionar o tipo de terminal compartilhado que você deseja iniciar, um novo terminal compartilhado será exibido na guia de terminais do VS Code.

![Execução de terminal compartilhada](../media/vscode-share-terminal-up.png)<br />

Se vários terminais compartilhados, ou seu foco estiver em uma guia diferente, você pode colocar o foco para um terminal específico, selecionando a entrada na lista de terminais compartilhados.

![Terminal compartilhado focalizar](../media/vscode-shared-terminal-focus.png)<br />

Para encerrar a sessão de terminal, simplesmente digite exit, feche a janela do terminal ou clique no ícone de "Remover o compartilhamento de terminal" na exibição do Explorer de compartilhamento ao vivo ou guia personalizada e todos serão desconectados.

## <a name="session-states"></a>Estados de sessão

Depois de você ter iniciado ou associado a sessão de colaboração e ter acesso ao conteúdo compartilhado, os itens de barra de status do Visual Studio Live Share atualizar sua aparência para refletir o estado da sessão de colaboração do Active Directory.

Estes são os estados que você normalmente verá:

| Estado | Barra de Status | Descrição |
|-------|--------------------|-------------|
| Inativo | ![Status do código VS: inativa](../media/vscode-status-share.png) | Nenhuma sessão de colaboração do Active Directory e nada é compartilhado. |
| Host: Compartilhamento em andamento | ![Status do código VS: compartilhar em andamento](../media/vscode-status-sharing.png)| Começa uma sessão de colaboração e compartilhamento de conteúdo será iniciado em breve. |
| Host: Compartilhamento | ![Status do código VS: compartilhamento o Active Directory ](../media/vscode-status-active.png)| Uma sessão de colaboração está ativa e o conteúdo é compartilhado. |
| Host: Compartilhamento somente leitura | ![Status do código VS: compartilhamento somente leitura](../media/vscode-status-sharing-read-only.png)| Compartilhando uma sessão de colaboração de somente leitura. |
| Convidado: Ingressar na sessão | ![Status do código VS: unindo](../media/vscode-status-joining.png)| Ingressar em uma sessão de colaboração existente. |
| Convidado: Ingressou | ![Status do código VS: unida](../media/vscode-status-active.png) | Associado e conectado a uma sessão de colaboração do Active Directory e o recebimento de conteúdo compartilhado. |
| Convidado: Unida de somente leitura | ![Status do código VS: unida de somente leitura](../media/vscode-status-joined-read-only.png) | Associado e conectado a uma sessão de colaboração ativa de somente leitura. |

## <a name="guest-limitations"></a>Limitações do convidado

Enquanto atualmente, há algumas limitações que os convidados serão encontrados ao usar os recursos descritos acima, hosts de sessão de colaboração retêm toda a funcionalidade de sua ferramenta escolhida. Para obter mais informações, consulte o seguinte:

- [Suporte de idioma e plataforma](../reference/platform-support.md)
- [Suporte de extensão](../reference/extensions.md)
- [Todos os bugs importantes, solicitações de recursos e limitações](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)
- [Solução de problemas](../troubleshooting.md)

## <a name="next-steps"></a>Próximas etapas

Confira estes artigos adicionais para obter mais informações.

- [Início Rápido: Compartilhar seu primeiro projeto](../quickstart/share.md)
- [Início Rápido: Junte-se a primeira sessão](../quickstart/share.md)
- [Como: Colaborar usando o Visual Studio](vs.md)
- [Requisitos de conectividade do Live Share](../reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](../reference/security.md)
- [Detalhes de instalação do Linux](../reference/linux.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
