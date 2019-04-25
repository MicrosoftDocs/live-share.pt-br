---
title: Colaborar usando o Visual Studio Code – Visual Studio Live Share | Microsoft Docs
description: Um conjunto de instruções de colaboração para Visual Studio Code e Live Share.
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: ed96ba572a58b8d3bfda7b634f1052a1b4e73051
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58853632"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>Como: colaborar usando o Visual Studio Code

Pronto para receber colaboração com o Live Share no VS Code?  Nesse caso, você está no lugar certo! Neste artigo, vamos explicar como usar alguns dos recursos específicos da extensão Visual Studio Live Share para Visual Studio Code.

Observe que todas as atividades de colaboração descritas aqui envolvem um único **host da sessão de colaboração** e um ou mais **convidados**. O host é a pessoa que iniciou a sessão de colaboração, e qualquer pessoa que ingressa na sessão é um convidado.

*Procurando uma versão resumida? É só conferir os guias de início rápido [compartilhar](../quickstart/share.md) ou [ingressar](../quickstart/join.md).*

> [!TIP]
> Você sabia que pode *ingressar em sua própria sessão de colaboração*? Isso permite que você experimente o Live Share por conta própria ou crie uma instância do Visual Studio ou do VS Code e conecte-a remotamente. Você pode até mesmo usar a mesma identidade em ambas as instâncias. Confira!

## <a name="installation"></a>Instalação

Antes de começar, será preciso confirmar se você tem uma versão do Visual Studio Code instalada que atenda aos requisitos principais do Live Share. Você precisará do **Visual Studio Code (1.22.0 ou superior)** em execução em:

- **Windows**: 7, 8.1 ou 10

- **macOS**: apenas Sierra (10.12) e superiores.
    - _El Capitan (10.11) e inferiores não são aceitos atualmente devido aos [requisitos do .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872315)._

- **Linux**: Ubuntu Desktop 16.04+ de 64 bits, Fedora Workstation 27+, CentOS 7

    - O Live Share exige vários [pré-requisitos de Linux](#linux-install-steps) que talvez você tenha que instalar.
    - _O Linux de 32 bits não é aceito devido aos [requisitos do .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872314)._
    - ARM também não é aceito no momento.
    - Confira o artigo com [detalhes de instalação do Linux](../reference/linux.md) para saber como usar o downstream e outras distribuições.

Depois disso, o download e a instalação da extensão do Visual Studio Live Share são muito simples:

1. Instale o <a href="https://code.visualstudio.com/">Visual Studio Code</a>
2. [Baixe](https://aka.ms/vsls-dl/vscode) e instale a extensão Visual Studio Live Share do marketplace.
3. Recarregue o Visual Studio Code
4. Aguarde que as dependências sejam baixadas e instaladas (veja a barra de status).<br/>
    ![Concluindo a instalação](../media/vscode-finishing-install.png)
5. **Linux**: se você receber uma notificação sobre como instalar bibliotecas ausentes:
    1. Clique em "Instalar" na notificação.
    2. Informe a sua senha de administrador (sudo) quando solicitado.
    3. Reinicie o VS Code quando terminar.

Ao baixar e usar o Visual Studio Live Share, você concorda com os [termos de licença](https://aka.ms/vsls-license) e a [política de privacidade](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Confira [Solução de problemas](../troubleshooting.md) caso tenha problemas.

[![Baixar](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Etapas de instalação do Linux

Linux é um ambiente altamente variável e, com o grande número de ambientes de desktop e distribuições, pode ser complicado trabalhar. Se você tiver versões compatíveis do **Ubuntu Desktop** (16.04+) ou **Fedora Workstation** (27+), **CentOS 7** e usar apenas **distribuições oficiais do VS Code**, você achará o processo simples. No entanto, se estiver usando uma configuração não padrão ou distribuição downstream, pode ser que você passe por alguns contratempos. Confira [Detalhes de instalação do Linux](../reference/linux.md) para obter mais informações.

#### <a name="install-linux-prerequisites"></a>Instalar pré-requisitos do Linux

Algumas distribuições do Linux têm bibliotecas que o Live Share precisa para funcionar. Por padrão, o Live Share tenta detectar e instalar os pré-requisitos do Linux para você. Uma notificação será exibida quando o Live Share encontrar um problema que tenha sido originado pela ausência das bibliotecas, solicitando a você permissão para instalá-las.

![Notificação do sistema mostrando a mensagem que os pré-requisitos do Linux estão ausentes](../media/vscode-linux-prereq-missing.png)

Quando você clicar em "Instalar", será exibida uma janela de terminal em que será preciso inserir a sua senha de administrador (sudo) para continuar. Supondo que a conclusão tenha sido bem-sucedida, com o reinício do Visual Studio Code, tudo deverá estar pronto! Talvez você também queira conferir as **[dicas por distribuição](../reference/linux.md#tips-by-distribution)** para ver outras dicas e soluções alternativas, caso haja alguma.

Caso seja exibida uma mensagem indicando que o script não dá suporte à sua distribuição, confira **[dicas para distribuição suportada pela comunidade](../reference/linux.md#tips-for-community-supported-distros)** para obter informações compartilhadas conosco pela comunidade.

Se **preferir que o VS Code não execute o comando em seu nome**, você também poderá optar por executar novamente a última versão desse script a qualquer momento manualmente executando o seguinte comando em uma janela do Terminal:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Integração do navegador do Linux

Geralmente, o Visual Studio Live Share **não exige etapas de instalação adicionais** para permitir a integração do navegador no Linux.

Embora incomum, em determinadas distribuições, você **pode ser notificado de que a sua senha de administrador (sudo) é obrigatória** para conclusão do processo de instalação. Uma janela do terminal será exibida informando a você onde o inicializador do navegador será instalado. Basta digitar a senha quando solicitado e pressionar enter assim que a instalação for concluída para fechar janela do terminal.

Você pode ler **[aqui](../reference/linux.md#linux-browser-integration)** mais sobre a necessidade disso e onde o Live Share coloca os arquivos. Observe que mesmo que não seja possível fazer a integração do navegador funcionar, você poderá **[ingressar nas sessões de colaboração manualmente](../use/vscode.md#join-manually)**.

## <a name="sign-in"></a>Entrar

Para colaborar, é preciso entrar no Visual Studio Live Share para que todos saibam quem é você. Trata-se apenas de uma medida de segurança e **não** inscreve você para receber marketing nem em outras atividades de pesquisa. Você pode entrar usando uma conta pessoal da Microsoft (por exemplo, @outlook.com), a AAD (conta corporativa ou de estudante) da Microsoft ou uma conta do GitHub. Entrar é fácil.

**Clique** no item da barra de status "Live Share" ou pressione **Ctrl+Shift+P / Cmd+Shift+P** e selecione o comando "Live Share: Entrar com Navegador".

![Botão Entrar do VS Code](../media/vscode-sign-in-button.png)

Uma notificação será exibida solicitando que você entre usando o navegador da Web. Clicar em "Iniciar entrada" abrirá o navegador para que você possa concluir o processo de conexão. Basta fechar o navegador quando terminar.

![Notificação do sistema solicitando a entrada com um navegador da Web](../media/vscode-sign-in-toast.png)

> **Usuários do Linux:** talvez você seja solicitado a inserir um código do usuário se estiver usando uma versão mais antiga do Live Share (v0.3.295 ou anteriores). Atualize para a versão mais recente da extensão ou clique no link "Está com problemas?" depois de entrar para ver o código. Veja [abaixo mais detalhes](#sign-in-using-a-user-code).

Se o Visual Studio Code não estiver capturando sua entrada após a conclusão do processo de conexão no navegador, confira [entrar usando um código de usuário](#sign-in-using-a-user-code). Caso contrário, verifique [solução de problemas](../troubleshooting.md#sign-in) para obter mais dicas.

### <a name="sign-in-using-a-user-code"></a>Entrar usando um código de usuário

Se o VS Code não estiver aceitando uma entrada concluída, você poderá inserir um "código de usuário" no lugar.

1. Pressione **Ctrl+Shift+P / Cmd+Shift+P** e execute o comando "Live Share: Entrar com código de usuário".

2. Um navegador deverá aparecer para que você possa concluir o processo de conexão.

    > [!NOTE]
    > Se um navegador não aparecer automaticamente, abra [este local](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) em um navegador e se conecte.

3. Quando terminar, clique em "Está com problemas? Clique aqui para obter instruções sobre código de usuário" para ver o código de usuário.

    ![Imagem do código de usuário no navegador](../media/vscode-user-code-browser.png)

4. Copie o código de usuário.

5. Por fim, cole o código de usuário no campo de entrada que apareceu quando você executou o comando e pressione enter para concluir o processo de conexão.

    ![Imagem do campo de entrada do código de usuário](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>Usando o viewlet do Live Share

Após a instalação do Visual Studio Live Share, uma guia personalizada será adicionada à barra de atividade do VS Code. Nessa guia, você pode acessar todas as funções para colaboração no Live Share. Além disso, quando você compartilha uma sessão de colaboração, ou ingressa em uma, uma exibição aparece na guia Explorer para que também seja possível acessar todas essas funções.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

Com essas exibições, você pode ver o local do participante no código compartilhado, clicar em um participante para segui-lo, focar os participantes, acessar servidores compartilhados e terminais, e muito mais.

## <a name="using-the-scoped-command-menu"></a>Usando o menu de comando no escopo

Além disso, todas as funções do Visual Studio Live Share estão disponíveis na "Paleta de Comandos" do Visual Studio Code, que pode ser acessada pressionando Ctrl+Shift+P/Cmd+Shift+P ou F1. Você pode encontrar uma lista completa de comandos digitando "live share".

Como essa lista pode ficar longa, pode ser mais fácil aproveitar um menu de comandos no escopo disponível na barra de status. Clicar no ícone entrar/estado de sessão na barra de status exibirá imediatamente uma lista contextualizada de comandos que estão disponíveis para você usar.

![Ícone do estado de sessão do VS Code](../media/vscode-share-state.png)

## <a name="share-a-project"></a>Compartilhar um projeto

Depois de baixar e instalar o Visual Studio Live Share, siga estas etapas para iniciar uma sessão de colaboração e convidar um colega para trabalhar com você.

1. **Entrar**

    Depois de instalar a extensão Live Share, recarregar e aguardar o término da instalação das dependências, convém entrar para permitir que outros colaboradores saibam quem é você. Confira o tópico [Entrar](#sign-in) para obter mais detalhes.

2. **Abrir uma pasta**

    Use o fluxo de trabalho normal para abrir uma pasta, um projeto ou uma solução que queira compartilhar com os seus convidados.

3. **[Opcional] Atualizar arquivos ocultos ou excluídos**

    Por padrão, o Live Share **oculta** dos convidados quaisquer arquivos/pastas referenciados nos arquivos .gitignore em suas pastas compartilhadas. **Ocultar** um arquivo impede que ele apareça na árvore de arquivos do convidado. **Excluir** um arquivo aplica uma regra mais rigorosa que impedirá o Live Share de abri-lo para o convidado em situações como "Ir para Definição" ou se você intervir no arquivo durante a depuração ou ao ser "seguido". Se você quiser ocultar/excluir arquivos diferentes, um arquivo **.vsls.json** poderá ser adicionado ao seu projeto com essas configurações. Confira o tópico sobre como [controlar a visibilidade e o acesso a arquivos](../reference/security.md#controlling-file-access-and-visibility) para saber mais detalhes.

4. **Iniciar uma sessão de colaboração**

    Agora, basta **clicar** no item da barra de status "Live Share" ou pressionar **Ctrl+Shift+P/Cmd+Shift+P** e selecionar "Live Share: Iniciar uma sessão de colaboração (Compartilhar)".

    ![Botão Compartilhar](../media/vscode-share-button.png)

    > [!NOTE]
    > Talvez o software de firewall do computador exija que o agente do Live Share tenha permissão para abrir uma porta no primeiro compartilhamento. Aceitar isso é totalmente opcional, mas habilita um "modo direto" seguro para melhorar o desempenho quando a pessoa com que você está trabalhando estiver na mesma rede que você. Confira o tópico sobre como [alterar o modo de conexão](../reference/connectivity.md#changing-the-connection-mode) para saber mais detalhes.

    Um link de convite será copiado automaticamente para a área de transferência. Quando aberto em um navegador, esse link permite que outras pessoas ingressem em uma nova sessão de colaboração que compartilha o conteúdo dessas pastas com elas.

    Você também verá a transição do item da barra de status "Live Share" para representar o estado de sessão. Confira as informações do [estado de sessão](#session-states) abaixo para ver sua aparência.

    Observe que, se precisar obter o link de convite novamente depois de ter iniciado o compartilhamento, você o acessa novamente clicando no ícone da barra de status do estado de sessão e seleciona "Convidar Outras Pessoas (Copiar Link)".

5. **[Opcional] Habilitar o modo somente leitura**

    Após iniciar a sessão de colaboração, configure a sessão como somente leitura para impedir que os convidados façam edições no código compartilhado.

    Após o compartilhamento, você receberá uma notificação de que o link de convite foi copiado para a área de transferência. Em seguida, você poderá selecionar a opção para definir a sessão como somente leitura.

    ![Modo somente leitura do VS Code](../media/vscode-read-only-toast.png)

6. **Enviar o link para alguém**

    Envie o link por email, pelo Slack, pelo Skype etc. para as pessoas que você quer convidar. Observe que, considerando o nível de acesso que as sessões do Live Share podem conceder aos convidados, **você só deve compartilhar com pessoas em que confia** e considerar as implicações do que você está compartilhando.

    > **Dica de segurança:** quer entender as implicações de segurança de alguns recursos do Live Share? Confira o artigo sobre [segurança](../reference/security.md).

    Se o convidado tiver dúvidas, o artigo "[Início Rápido: Ingressar na primeira sessão](../quickstart/join.md)" oferece mais algumas informações sobre como começar a trabalhar como convidado.

7. **[Opcional] Aprovar o convidado**

    Por padrão, os convidados ingressarão automaticamente na sessão de colaboração e você receberá uma notificação quando eles estiverem prontos para trabalhar com você. Embora essa notificação dê a opção de removê-los da sessão, você também pode optar por exigir uma "aprovação" explícita para os que estão ingressando.

    Para habilitar esse recurso, basta adicionar o seguinte a settings.json:

         "liveshare.guestApprovalRequired": true

    Quando essa configuração for ativada, uma notificação solicitará que você aprove o convidado para que ele possa ingressar na sessão.

    ![Solicitação de aprovação para ingressar do Visual Studio Code](../media/vscode-join-approval.png)

    Confira o tópico [convites e acesso para ingressar](../reference/security.md#invitations-and-join-access) a fim de obter detalhes adicionais sobre considerações de segurança de convite.

E pronto!

### <a name="stop-the-collaboration-session"></a>Interromper a sessão de colaboração

Como um host, você pode interromper completamente e encerrar a sessão de colaboração a qualquer momento, bastando para isso abrir a exibição Live Share no Explorer ou, na guia personalizada Live Share, selecionar o ícone "Interromper a sessão de colaboração".

![Interromper a sessão de colaboração](../media/vscode-end-collaboration-viewlet.png)

Todos os convidados serão notificados de que a sessão foi encerrada.  Depois que a sessão for encerrada, os convidados não poderão mais acessar o conteúdo e todos os arquivos temporários serão apagados automaticamente.

Está tendo problemas com o compartilhamento? Verifique a [solução de problemas](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Ingressar em uma sessão de colaboração

Depois de baixar e instalar o Visual Studio Live Share, os convidados só precisam executar algumas etapas para ingressar em uma sessão de colaboração hospedada. Há duas maneiras de ingresso: [por navegador](#join-via-the-browser) e [manualmente](#join-manually).

> **Dica de segurança:** como um convidado que ingressa em uma sessão de colaboração, é importante entender que os hosts podem restringir seu acesso a determinados arquivos ou recursos. Quer entender as implicações de segurança de alguns recursos e configurações do Live Share? Confira o artigo sobre [segurança](../reference/security.md).

### <a name="join-via-the-browser"></a>Ingressar pelo navegador

A maneira mais fácil de ingressar em uma sessão de colaboração é simplesmente abrir o link de convite em um navegador da Web. Veja a seguir o que esperar ao seguir esse fluxo.

1. **Entrar**

    Depois de instalar a extensão Live Share, recarregar e aguardar o término da instalação das dependências, convém entrar para permitir que outros colaboradores saibam quem é você. Confira o tópico [Entrar](#sign-in) para obter mais detalhes.

2. **Clicar no link de convite/abrir o convite no navegador**

    Agora, basta abrir (ou reabrir) o link de convite em um navegador.

    > **Observação**: se a extensão Live Share ainda não tiver sido instalada, você verá links para o marketplace da extensão. Instale a extensão, reinicie a ferramenta e tente novamente.

    Você receberá uma notificação de que o navegador quer iniciar uma ferramenta habilitada para o Live Share. Ao permitir a inicialização da ferramenta selecionada, você será conectado à sessão de colaboração quando ela começar.

    ![Página Ingressar](../media/join-page.png)

    Se o host estiver offline, você receberá uma notificação. Você pode entrar em contato com o host e solicitar o compartilhamento novamente.

    > [!NOTE]
    > Certifique-se de que você já **iniciou a ferramenta pelo menos uma vez** após a instalação da extensão Visual Studio Live Share e de que permitiu que a instalação finalizasse antes de abrir/reabrir a página de convite. Ainda está com problemas? Confira [ingressar manualmente](#join-manually).

3. **Colaborar**

    É só isso! Em poucos instantes você será conectado e poderá iniciar a colaboração.

    Você verá a transição do botão "Live Share" para transmitir um "Estado de Sessão". Confira as informações do [estado de sessão](#session-states) abaixo para ver sua aparência.

    Você será automaticamente levado para o arquivo que o host está editando no momento assim que o ingresso for concluído.

### <a name="join-manually"></a>Ingressar manualmente

Também é possível ingressar manualmente sem usar um navegador da Web, o que pode ser útil nas situações em que a ferramenta que você quer usar já estiver em execução, se quiser usar uma ferramenta diferente do que usa normalmente ou se estiver tendo problemas em fazer os links de convite funcionarem por algum motivo. O processo é fácil:

1. **Entrar**

    Depois de instalar a extensão Live Share, recarregar e aguardar o término da instalação das dependências, convém entrar para permitir que outros colaboradores saibam quem é você. Confira o tópico [Entrar](#sign-in) para obter mais detalhes.

2. **Usar o comando de ingresso**

    Abra a guia personalizada Live Share na barra de atividade do VS Code e selecione o ícone ou a entrada "Ingressar na sessão de colaboração...".

    ![Ícone do viewlet Ingressar](../media/vscode-join-viewlet.png)

3. **Colar o link do convite**

    Cole a URL do convite que você recebeu e pressione enter para confirmar.

4. **Colabore!**

    É só isso! Em breve, você deverá estar conectado à sessão de colaboração.

    Você verá a transição do botão "Live Share" para transmitir um "Estado de Sessão". Confira as informações do [estado de sessão](#session-states) abaixo para ver sua aparência.

    Você será automaticamente levado para o arquivo que o host está editando no momento assim que o ingresso for concluído.

### <a name="leave-the-collaboration-session"></a>Sair da sessão de colaboração

Como um convidado, você pode deixar a sessão de colaboração sem encerrá-la para outras pessoas simplesmente fechando a janela do VS Code. Se preferir manter a janela aberta, é possível abrir a exibição Explorer do Live Share ou a guia personalizada Live Share e selecionar o ícone "Sair da sessão de colaboração".

![Ícone Sair da sessão](../media/vscode-leave-session-viewlet.png)

Todos os arquivos temporários são automaticamente apagados, de modo que não é preciso fazer mais nada.

Está tendo problemas para ingressar? Verifique a [solução de problemas](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Coedição

Depois que um convidado tiver ingressado em uma sessão de colaboração, todos os colaboradores poderão ver imediatamente as edições e seleções uns dos outros em tempo real. Tudo o que você precisa fazer é escolher um arquivo no explorador de arquivos e começar a editar. Hosts e convidados verão as edições à medida que você as cria e poderão contribuir com elas, facilitando a iteração e a rapidez das soluções.

> [!NOTE]
> Ingressar em uma sessão de colaboração somente leitura impede convidados de fazer edições nos arquivos. Um host pode [habilitar o modo somente leitura quando compartilha](#share-a-project). Como um convidado, você pode saber se ingressou em uma sessão somente leitura observando seu [estado de sessão](#session-states).

![Captura de tela mostrando a coedição](../media/vscode-coedit.png)

> [!NOTE]
> A coedição tem limitações para determinados idiomas. Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades por linguagem.

Além de cursores e edições, as seleções feitas também ficam visíveis para todos os participantes no mesmo arquivo. Isso facilita destacar onde podem ocorrer problemas ou transmitir ideias.

![Captura de tela mostrando o realce](../media/vscode-highlight.png)

Melhor ainda, você e outros participantes podem navegar para qualquer arquivo no projeto compartilhado. Você pode fazer edições em conjunto ou separadamente, o que significa que é possível alternar entre investigação, fazer pequenos ajustes e edição totalmente colaborativa.

As edições resultantes são mantidas no computador do host no salvamento, de modo que não há necessidade de sincronizar, efetuar push nem de enviar arquivos depois de fazer a edição. As edições "estão lá".

> **Dica de segurança:** uma vez que todos os participantes podem navegar e editar arquivos independentemente, como um host, talvez você queira restringir os arquivos que os convidados podem acessar no seu projeto por um arquivo .vsls.json. Como um convidado, também é importante entender que você talvez não veja determinados arquivos como consequência dessas configurações. Confira o tópico sobre como [controlar a visibilidade e o acesso a arquivos](../reference/security.md#controlling-file-access-and-visibility) para saber mais detalhes.

### <a name="changing-participant-flag-behaviors"></a>Alterando os comportamentos do sinalizador do participante

Por padrão, o Visual Studio Live Share exibe automaticamente um "sinalizador" ao lado do cursor em foco de um participante, ou quando ele edita, realça ou move o respectivo cursor. Em alguns casos, talvez você prefira alterar esse comportamento.

Basta **editar settings.json** (Arquivo > Preferências > Configurações), adicionar uma das seguintes linhas e reinicializar o VS Code:

| Configuração | Comportamento |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | O sinalizador só fica visível quando você focaliza o cursor. |
| ``"liveshare.nameTagVisibility":"Activity"`` | Esse é o padrão. O sinalizador fica visível na focalização ou se o participante editar, realçar ou mover o próprio cursor. |
| ``"liveshare.nameTagVisibility":"Always"`` | O sinalizador está sempre visível. |

## <a name="following"></a>Seguindo

Às vezes, você precisa explicar um problema ou um design que abrange vários arquivos ou locais no código. Nessas situações, pode ser útil seguir temporariamente um colega enquanto ele percorre o projeto. Por esse motivo, ao ingressar em uma sessão de colaboração, você automaticamente "seguirá" o host. Ao seguir alguém, seu editor permanecerá em sincronização com o arquivo aberto e a posição de rolagem do momento.

> [!NOTE]
> Por padrão, o Live Share também compartilha arquivos abertos externos à pasta compartilhada. Se quiser desabilitar esse recurso, atualize o Live Share de `liveshare.shareExternalFiles` para `false` em settings.json.

Para começar a seguir um participante (como um host ou convidado), clique em seu nome na lista de participantes na guia personalizada ou na exibição Explorer Live Share. O círculo ao lado do nome será preenchido para indicar que você o está seguindo.

![VS Code decorrente do viewlet](../media/vscode-follow-multiple-viewlet.png)

Como alternativa, você pode clicar no ícone de fixar no canto superior direito do grupo de editores ou pressionar **Ctrl+Alt+F/Cmd+Alt+F**.

![Pino do VS Code](../media/vscode-pin.png)

> [!NOTE]
> Se mais de uma pessoa estiver na sessão de colaboração, será solicitado que você selecione o participante que quer seguir.
>
>![Captura de tela mostrando a lista de colaboradores](../media/vscode-list-collaborators.png)

Uma vez que o ato de seguir alguém está associado a um grupo de editores, você pode usar o modo divisão (ou layout de grade) para ter um grupo que está seguindo um participante e um grupo que não está. Isso permite que você siga passivamente alguém enquanto também trabalha em algo de maneira independente. Com um grupo de editores selecionado, é possível selecionar um participante na lista para que esse grupo o siga.

![Pino do VS Code no modo divisão](../media/vscode-follow-split.png)

Para que fique fácil sair do "modo seguir" e começar a editar por conta própria, você vai parar de seguir automaticamente na ocorrência de uma destas situações:

1. Você começa a editar o arquivo ativo no momento
1. Você abre outro arquivo
1. Você fecha o arquivo ativo no momento

Além disso, é possível parar explicitamente de seguir alguém clicando no ícone de fixar novamente ou pressionando **Ctrl+Alt+F/Cmd+Alt+F**.

## <a name="listing-participants"></a>Listando participantes

Uma maneira rápida de verificar quem está na sessão de colaboração é examinar a lista de participantes na guia personalizada ou na exibição Explorer Live Share. As exibições mostrarão todos os participantes da sessão.

![Captura de tela mostrando o ícone de barra de status do usuário](../media/vscode-explorer-view.png)

Para seguir o participante no grupo de editores ativo, basta clicar nele nessa lista.

Como alternativa, você pode pressionar **Ctrl+Shift+P/Cmd+Shift+P** e selecionar o comando "Live Share: Listar Participantes" ou **clicar** no item da barra de status que mostra o número de participantes da sessão.

![Captura de tela mostrando o ícone de barra de status do usuário](../media/vscode-user-status.png)

Uma lista de todos os participantes da sessão será exibida. Diferentemente de clicar no ícone de fixar, essa lista será exibida mesmo se houver apenas uma pessoa na sessão com você para que sempre seja possível ver rapidamente onde a outra pessoa está localizada. Por motivos de conveniência, como o ícone de fixar, você pode selecionar um dos participantes na lista para segui-lo. Pressione escape caso queira sair.

## <a name="focusing"></a>Focando

Ocasionalmente, talvez seja conveniente que todas as pessoas em uma sessão de colaboração vejam algo que você esteja fazendo. O Live Share permite solicitar a todos que "foquem" a atenção em você com uma notificação que facilita para eles o seguirem de volta.

Abra a guia personalizada Live Share na barra de atividade do VS Code ou a exibição Explorer do Live Share e selecione o ícone "Focar participantes".

![Ícone do viewlet Focar](../media/vscode-focus-viewlet.png)

Após a execução do comando, todos na sessão de colaboração receberão a notificação que você solicitou a atenção deles.

![Notificação do sistema para Focar](../media/vscode-focus-toast.png)

Eles poderão apenas clicar em "Seguir" diretamente na notificação quando estiverem prontos para focarem em você.

## <a name="co-debugging"></a>Codepuração

O recurso de depuração colaborativa do Visual Studio Live Share é uma maneira exclusiva e avançada de depurar um problema. Além de proporcionar uma experiência colaborativa para a solução de problemas, ele também oferece a você e aos outros participantes a capacidade de investigar problemas que possam ser específicos do ambiente, fornecendo uma sessão de depuração compartilhada no computador do host.

> **Dica de segurança:** uma vez que todos os participantes podem navegar e editar arquivos independentemente, como um host, talvez você queira restringir os arquivos que os convidados podem acessar no seu projeto por um arquivo .vsls.json. Você também deve estar ciente de que o acesso ao Console/REPL significa que os participantes podem executar comandos em seu computador, de modo que você só deve codepurar com as pessoas em quem confia. Como um convidado, também é importante entender que talvez você não possa seguir o depurador, uma vez que ele intervém em determinados arquivos que são restringidos como resultado dessas configurações. Confira o tópico sobre como [controlar a visibilidade e o acesso a arquivos](../reference/security.md#controlling-file-access-and-visibility) para saber mais detalhes.

A utilização é simples.

1. Certifique-se de que o host e todos os convidados tenham a extensão de depuração apropriada instalada. (Tecnicamente isso nem sempre é necessário, mas é recomendável.)

2. Como host, se ainda não estiver configurado para o projeto, você deverá [configurar launch.json](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) para depurar o aplicativo do VS Code, como faria normalmente. Nenhuma configuração especial é necessária.

3. Em seguida, o host pode começar a depurar usando o botão na guia de depuração, como de costume.

    ![Botão de depuração do VS Code](../media/vscode-debug-button.png)

    > [!TIP]
    > Você também pode participar de sessões de depuração do Visual Studio no VS Code, e vice-versa! Confira as [instruções do Visual Studio](vs.md#co-debugging) em codepuração para obter mais informações.

Depois que o depurador for conectado no lado do host, todos os convidados também serão automaticamente conectados. Enquanto houver uma "sessão" de depuração em execução no computador do host, todos os participantes serão conectados a ela e terão a sua própria exibição.

![Depurador anexado do VS Code](../media/vscode-debugger.png)

Qualquer pessoa pode passar pelo processo de depuração, que permite alternância perfeita entre colaboradores sem ter que negociar o controle.

> [!NOTE]
> Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades de depuração por linguagem ou plataforma.

Cada colaborador pode investigar variáveis diferentes, pular para arquivos diferentes na pilha de chamadas, inspecionar variáveis e, até mesmo, adicionar ou remover pontos de interrupção. Os recursos de coedição permitem que cada orador participante rastreie onde as outras pessoas estão localizadas para fornecer a capacidade exclusiva de alternar diretamente entre investigar simultaneamente diferentes aspectos do problema e depurar de maneira colaborativa.

> [!NOTE]
> Enquanto estiver em uma sessão de colaboração somente leitura, um convidado não poderá passar pelo processo de depuração. No entanto, ele pode adicionar ou remover pontos de interrupção e inspecionar variáveis.

![Animação de depuração simultânea](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>Alterar quando o VS Code ingressa em sessões de depuração

Por padrão, como um convidado, você vai ser automaticamente anexado às sessões de depuração quando elas forem compartilhadas pelo host. No entanto, em alguns casos, você pode achar esse comportamento incômodo. Felizmente, você pode alterá-lo da seguinte maneira:

Basta **editar settings.json** (Arquivo > Preferências > Configurações), adicionar uma das seguintes linhas e reinicializar o VS Code:

| Configuração | Comportamento |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | O padrão. Como um convidado, você ingressará automaticamente em qualquer sessão de depuração compartilhada iniciada pelo host. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | Como um convidado, será perguntado se você deseja ingressar em uma sessão de depuração compartilhada quando ela for iniciada pelo host. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | Como convidado, você precisará ingressar manualmente em qualquer sessão de depuração. Confira [desanexando e reanexando](#detaching-and-reattaching). |

### <a name="detaching-and-reattaching"></a>Desanexando e reanexando

Como um convidado, você pode querer interromper a depuração temporariamente. Felizmente, você pode simplesmente clicar no ícone "parar" na barra de ferramentas de depuração para desanexar o depurador sem afetar o anfitrião ou outros convidados.

![Botão de parada do depurador do VS Code](../media/vscode-debug-stop.png)

Se você tiver atualizado as configurações para que não seja mais possível anexar automaticamente ou se simplesmente quiser reanexar posteriormente, faça isso pressionando **Ctrl+Shift+P/Cmd+Shift+P** ou **clicando** no item da barra de status do estado de sessão e selecionando "Anexar a uma Sessão de Depuração Compartilhada".

![Anexar depurador do VS Code](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>Compartilhando o aplicativo em execução em um navegador

O Visual Studio Code não tem o conceito de uma "porta de aplicativo Web" conhecida como o Visual Studio para tipos de projeto, como ASP.NET. No entanto, se estiver ingressando em uma sessão de colaboração de um host do Visual Studio, você poderá ver automaticamente o seu navegador padrão aparecer quando a depuração começar, isto é, será automaticamente conectado aos aplicativos em execução do host. Confira os [recursos do Visual Studio](vs.md#automatic-web-app-sharing) para obter mais detalhes.

Como um host, você pode conseguir algo semelhante ao compartilhar manualmente o aplicativo ou outros pontos de extremidade, como serviços RESTful, usando o recurso "Compartilhar Servidor Local". Os convidados do Visual Studio e VS Code podem abrir um navegador na mesma porta do localhost para ver o aplicativo em execução.  Confira [compartilhar um servidor](#share-a-server) para obter mais detalhes.

## <a name="share-a-server"></a>Compartilhar um servidor

De tempos em tempos, como um host da sessão de colaboração, você pode achar conveniente compartilhar um aplicativo Web, ou outros servidores ou serviços em execução no local com convidados. Isso pode variar de outros pontos de extremidade RESTful a bancos de dados e outros servidores. O Visual Studio Live Share permite que você especifique um número de porta local, se desejar, dê um nome a ele e, em seguida, o compartilhe com todos os convidados.

Os convidados poderão então acessar o servidor compartilhado por você nessa porta dos respectivos computadores locais nessa mesma porta. Por exemplo, se você compartilhou um servidor Web **em execução na porta 3000**, o convidado poderá acessar esse mesmo servidor Web em execução nos **próprios computadores** em http://localhost:3000! Isso é feito por meio de um túnel SSH ou SSL seguro entre o host e os convidados e autenticado por meio do serviço, de modo que você possa ter certeza de que apenas as pessoas na sessão de colaboração tenham acesso.

> **Dica de segurança:** como um host, você deve ser muito seletivo com as portas que compartilha com convidados e seguir com as porta de aplicativo (em vez de compartilhar uma porta do sistema). Para convidados, as portas compartilhadas se comportarão exatamente como fariam se o servidor/serviço estivesse em execução em seu próprio computador. Isso é muito útil, mas se a porta errada for compartilhada, isso também poderá ser um risco.

Por motivos de segurança, somente servidores em execução em portas que você especifica são disponibilizadas para outros convidados. Felizmente, é fácil adicioná-los como o **host** da sessão de colaboração. Veja como:

1. Abra a guia personalizada Live Share na barra de atividade do VS Code ou a exibição Explorer do Live Share e selecione a entrada "Compartilhar servidor..." ou clique no ícone.

    ![Servidor do local de compartilhamento do VS Code](../media/vscode-share-local-server-viewlet.png)<br />

1. Insira o número da porta em que o servidor está em execução e, se desejar, dê um nome a ele.

    ![Captura de tela da solicitação do número da porta](../media/vscode-enter-port.png)<br />

É só isso! O servidor na porta especificada agora será mapeado para o localhost de cada convidado na mesma porta (a menos que a porta já esteja ocupada)!

Se a porta já estiver em uso no computador do convidado, outra será selecionada automaticamente. Felizmente, como convidado, você pode ver uma lista de portas atualmente compartilhadas (por nome, se especificado) na guia personalizada ou na exibição Explorer do Live Share na barra de atividade do VS Code, e observar abaixo da lista de servidores compartilhados. Selecionar uma entrada abre esse servidor no navegador. Você também pode clicar com o botão direito do mouse e selecionar a opção de copiar o link para o servidor na área de transferência.

![Acessar servidor local do VS Code](../media/vscode-access-shared-server-viewlet.png)<br />

Observe que, por motivos de segurança, os *convidados não podem* controlar quais portas no computador do host são compartilhadas.

Para **interromper** o compartilhamento de um servidor local como o host, passe o mouse sobre a entrada do servidor na lista de servidores compartilhados da guia personalizada ou da exibição Explorer do Live Share e clique no ícone "Descompartilhar servidor".

![Parar compartilhamento de servidor no VS Code](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>Compartilhar um terminal

O desenvolvimento moderno faz uso frequente de uma ampla gama de ferramentas de linha de comando. Felizmente, o Live Share permite que você, como host, se desejar, "compartilhe um terminal" com os convidados. O terminal compartilhado pode ser somente leitura ou totalmente colaborativo, de modo que você e os convidados possam executar comandos e ver os resultados. Você pode dar aos convidados visibilidade da saída do terminal ou permitir que eles ganhem experiência e executem testes, compilações ou, até mesmo, façam triagem de problemas específicos de ambiente que acontecem somente em seu computador.

No entanto, os terminais **não** são compartilhados por padrão, pois eles dão aos convidados no mínimo acesso somente leitura à saída dos comandos que você executa (se não a capacidade de executar comandos por conta própria). Dessa maneira, é possível executar comandos livremente nos terminais locais sem riscos e compartilhar somente quando realmente for preciso. Além disso, somente hosts podem iniciar terminais compartilhados para impedir os convidados de iniciar um e fazer algo que você não está esperando nem observando.

Como host, você pode compartilhar um terminal abrindo a guia personalizada Live Share na barra de atividade do VS Code ou a exibição Explorer do Live Share e selecionando a entrada "Compartilhar servidor...", ou clicando no ícone.

![Compartilhar terminal do VS Code](../media/vscode-share-terminal-viewlet.png)<br />

Neste ponto, você pode selecionar um terminal somente leitura ou leitura/gravação no menu. Quando o terminal for leitura/gravação, todos poderão digitar no terminal, incluindo o host, o que facilita a intervenção caso um convidado faça algo indesejável. No entanto, para que seja seguro, você deve **dar somente acesso de leitura/gravação aos convidados quando tiver ciência de que eles realmente precisam** e continuar com os terminais somente leitura para cenários em que deseja que o convidado veja apenas a saída dos comandos que você executa.

> [!NOTE]
> Se a sessão de colaboração estiver no modo somente leitura, somente os terminais somente leitura poderão ser compartilhados pelo host.

![Seleção de somente leitura ou leitura/gravação](../media/vscode-share-terminal-ro-rw.png)<br />

Uma vez selecionado o tipo de terminal compartilhado que você quer iniciar, um novo terminal compartilhado aparecerá na guia de terminais do VS Code.

![Terminal compartilhado em execução](../media/vscode-share-terminal-up.png)<br />

Se vários terminais forem compartilhados, ou seu foco estiver em uma guia diferente, você poderá colocar o foco em um terminal específico selecionando a entrada na lista de terminais compartilhados.

![Colocar foco no terminal compartilhado](../media/vscode-shared-terminal-focus.png)<br />

Para encerrar a sessão de terminal, basta digitar sair (exit), fechar a janela do terminal ou clicar no ícone "Descompartilhar terminal" na exibição Explorer ou na guia personalizada Live Share e todos serão desconectados.

## <a name="session-states"></a>Estados de sessão

Depois de iniciar ou ingressar em uma sessão de colaboração e ter acesso ao conteúdo compartilhado, os itens da barra de status do Visual Studio Live Share atualizam sua aparência para refletir o estado da sessão de colaboração ativa.

Estes são os estados que você normalmente verá:

| Estado | Barra de Status | Descrição |
|-------|--------------------|-------------|
| Inativo | ![Status do VS Code: inativo](../media/vscode-status-share.png) | Nenhuma sessão de colaboração ativa e nada está compartilhado. |
| Host: Compartilhamento em Andamento | ![Status do VS Code: compartilhar em andamento](../media/vscode-status-sharing.png)| Uma sessão de colaboração está iniciando e o compartilhamento do conteúdo começará em breve. |
| Host: Compartilhamento | ![Status do VS Code: compartilhamento ativo ](../media/vscode-status-active.png)| Uma sessão de colaboração está ativa e o conteúdo está compartilhado. |
| Host: Compartilhamento Somente Leitura | ![Status do VS Code: compartilhamento somente leitura](../media/vscode-status-sharing-read-only.png)| Compartilhando uma sessão de colaboração somente leitura. |
| Convidado: Ingressando na Sessão | ![Status do VS Code: ingressando](../media/vscode-status-joining.png)| Ingressando em uma sessão de colaboração existente. |
| Convidado: Ingressou | ![Status do VS Code: ingressou](../media/vscode-status-active.png) | Ingressou e conectou-se a uma sessão de colaboração ativa e está recebendo conteúdo compartilhado. |
| Convidado: Ingressou Somente Leitura | ![Status do VS Code: ingressou somente leitura](../media/vscode-status-joined-read-only.png) | Ingressou e conectou-se a uma sessão de colaboração somente leitura. |

## <a name="guest-limitations"></a>Limitações do convidado

Embora, no momento, existam algumas falhas com as quais os usuários vão se deparar enquanto estiverem usando os recursos descritos acima, os hosts da sessão de colaboração mantêm a funcionalidade completa de sua ferramenta de escolha. Para obter mais informações, consulte o seguinte:

- [Suporte de idioma e plataforma](../reference/platform-support.md)
- [Suporte de extensão](../reference/extensions.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)
- [Solução de problemas](../troubleshooting.md)

## <a name="next-steps"></a>Próximas etapas

Confira estes outros artigos para saber mais.

- [Início Rápido: Compartilhar seu primeiro projeto](../quickstart/share.md)
- [Início Rápido: Ingressar em sua primeira sessão](../quickstart/share.md)
- [Como colaborar usando o Visual Studio](vs.md)
- [Requisitos de conectividade do Live Share](../reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](../reference/security.md)
- [Detalhes de Instalação do Linux](../reference/linux.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
