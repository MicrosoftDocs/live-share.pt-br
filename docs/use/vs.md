---
title: Colaborar usando o Visual Studio – Visual Studio Live Share | Microsoft Docs
description: Um conjunto de instruções de colaboração para Visual Studio e Live Share.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 2f7be9b3c81aeca63eb9965085b42b777cc4a6d7
ms.sourcegitcommit: a48488302bc56abdedf7130ec22b4e21ac16a4ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84337239"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio"></a>Como colaborar usando o Visual Studio

Pronto para receber colaboração com o Live Share no Visual Studio? Nesse caso, você está no lugar certo! Neste artigo, vamos explicar como usar alguns dos recursos específicos da extensão Visual Studio Live Share para Visual Studio.

Todas as atividades de colaboração descritas aqui envolvem um único **host da sessão de colaboração** e um ou mais **convidados**. O host é a pessoa que iniciou a sessão de colaboração, e qualquer pessoa que ingressa na sessão é um convidado.

*Procurando um resumo de resumida? Confira os guias de início rápido [compartilhar](../quickstart/share.md) ou [ingressar](../quickstart/join.md) em seu lugar.*

> [!TIP]
> Você sabia que pode *ingressar em sua própria sessão de colaboração*? Isso permite que você experimente o Live Share por conta própria ou crie uma instância do Visual Studio ou do VS Code e conecte-a remotamente. Você pode até mesmo usar a mesma identidade em ambas as instâncias. Confira!

## <a name="installation"></a>Instalação

Antes de começar, será preciso instalar o **Visual Studio 2019** ou o **Visual Studio 2017 15.6 ou posterior** no Windows 7, 8.1 ou 10. *No entanto, é recomendável o Visual Studio 15.7 ou posterior, já que ele oferece suporte local às ações desfazer/refazer.*

Começar é simples:

Para o Visual Studio 2019
1. Instale qualquer edição do [Visual Studio 2019](https://visualstudio.microsoft.com/vs/).
2.  Instale uma [carga de trabalho compatível](../reference/platform-support.md). (por exemplo, ASP.NET, .NET Core, C++, Python e/ou Node.js)
3. O Visual Studio Live Share é instalado por padrão com essas cargas de trabalho.

Para o Visual Studio 2017
1. Instale qualquer edição do [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/) 15.6+.
2.  Instale uma [carga de trabalho compatível](../reference/platform-support.md). (por exemplo, ASP.NET, .NET Core, C++ e/ou Node.js)
3. [Baixe](https://aka.ms/vsls-dl/vs) e instale a extensão de Visual Studio Live share do Marketplace.

Ao baixar e usar o Visual Studio Live Share, você concorda com os [termos de licença](https://aka.ms/vsls-license) e a [política de privacidade](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Confira [Solução de problemas](../troubleshooting.md) caso tenha problemas.

[![Baixar](../media/download.png)](https://aka.ms/vsls-dl/vs)

## <a name="sign-in"></a>Entrar

Para colaborar, é preciso entrar no Visual Studio Live Share para que todos saibam quem é você. Trata-se apenas de uma medida de segurança e **não** inscreve você para receber marketing nem em outras atividades de pesquisa. Você pode entrar usando uma conta pessoal da Microsoft (por exemplo, @outlook.com), a AAD (conta corporativa ou de estudante) da Microsoft ou uma conta do GitHub. Entrar é fácil.

Por padrão, o Visual Studio usa a sua [conta de personalização](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), assim, se você já estiver conectado no Visual Studio, pode pular essa etapa. Caso contrário, entre como de costume.

![Botão de entrada do VS](../media/vs-sign-in-button.png)


Se quiser usar uma credencial diferente da sua [conta de personalização](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) do Visual Studio, acesse **Ferramentas&gt; Opções &gt; Live Share &gt; Conta de usuário** para mudar as credenciais.

![Ferramentas Opções Live Share do VS](../media/vs-tools-options-new.png)

Selecionar **Conta Externa** permite que você selecione uma conta incompatível com o recurso de personalização do Visual Studio, como o GitHub. Um navegador será exibido automaticamente na primeira vez que você usar um recurso do Live Share para que seja possível concluir a entrada.
>[!Tip]
>Você sabia que pode ir a **Ferramentas &gt; Opções &gt; Live Share &gt; Geral** para exibir todas as configurações do Live Share padrão? Personalize a experiência de colaboração de acordo com as suas necessidades! Você também pode experimentar os novos recursos do Live Share escolhendo **Avançado &gt; Recursos &gt; Insiders** nas configurações gerais do Live Share.  

Em caso de problemas, confira a [solução de problemas](../troubleshooting.md#sign-in) para obter mais dicas.

## <a name="share-a-project"></a>Compartilhar um projeto

Depois de baixar e instalar o Visual Studio Live Share, siga estas etapas para iniciar uma sessão de colaboração e convidar um colega para trabalhar com você.

1. **Entrar**

    Agora que você está conectado, está pronto para começar a sua própria sessão de colaboração.
    Você não está conectado? Para obter mais detalhes, confira [Entrar](#sign-in).

2. **Abrir uma solução, um projeto ou uma pasta**

    Use o fluxo de trabalho normal para abrir uma pasta, um projeto ou uma solução que queira compartilhar com os seus convidados.

3. **[Opcional] Atualizar arquivos ocultos ou excluídos**

    Por padrão, o Live Share **oculta** dos convidados todos os arquivos/pastas referenciados nos arquivos .gitignore do seu projeto. **Ocultar** um arquivo impede que ele apareça na árvore de arquivos, enquanto **excluí-lo** interrompe a sua transmissão mesmo durante operações como a depuração. Se você quiser ocultar/excluir arquivos diferentes, um arquivo **.vsls.json** poderá ser adicionado ao seu projeto com essas configurações. Confira [Controlar o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para saber mais detalhes.

4. **Iniciar uma sessão de colaboração**

    Agora basta clicar no botão "Live Share" no canto superior direito para começar a sessão Live Share.     O link compartilhável da sua sessão de colaboração será copiado automaticamente na área de transferência. 

    ![Botão Compartilhar do VS](../media/vs-share-button.png)

    Assim que a sessão de colaboração iniciar pela primeira vez, você verá a janela de ferramentas do Live Share. Certifique-se de encaixar esta janela para garantir que seja exibida na próxima vez que você iniciar uma sessão do Live Share.

   ![Janela de ferramentas do VS Live Share](../media/vs-live-share-tool-window.png)

    > [!NOTE]
    > Talvez o software de firewall do computador exija que o agente do Live Share tenha permissão para abrir uma porta no primeiro compartilhamento. Aceitar isso é totalmente opcional, mas habilita um "modo direto" seguro para melhorar o desempenho quando a pessoa com que você está trabalhando estiver na mesma rede que você. Confira o tópico sobre como [alterar o modo de conexão](../reference/connectivity.md#changing-the-connection-mode) para saber mais detalhes.

5. **[Opcional] Habilitar o modo somente leitura**

    Após iniciar a sessão de colaboração, configure a sessão como somente leitura para impedir que os convidados façam edições no código compartilhado.

    Após o compartilhamento, você receberá uma notificação de que o link de convite foi copiado para a área de transferência. Em seguida, você poderá selecionar a opção para definir a sessão como somente leitura.

    ![Modo somente leitura do VS](../media/vs-read-only-notification.png)

6. **Enviar o link para alguém**

    Envie o link por email, pelo Slack, pelo Skype etc. para as pessoas que você quer convidar. Observe que, considerando o nível de acesso que as sessões do Live Share podem conceder aos convidados, **você só deve compartilhar com pessoas em que confia** e considerar as implicações do que você está compartilhando.

    > **Dica de segurança:** Quer entender as implicações de segurança de alguns dos recursos de Live Share? Confira o artigo sobre [segurança](../reference/security.md).

    Se o convidado que você convidou tiver dúvidas, o artigo "[início rápido: ingressar em sua primeira sessão](../quickstart/join.md)" fornece mais informações sobre como entrar em funcionamento como convidado.

7. **[Opcional] Aprovar o convidado**

    Por padrão, os convidados ingressarão automaticamente na sessão de colaboração e você receberá uma notificação quando eles estiverem prontos para trabalhar com você. Embora essa notificação dê a opção de removê-los da sessão, você também pode optar por exigir uma "aprovação" explícita para os que estão ingressando.

    Basta alterar **Ferramentas > Opções > Live Share > exigir aprovação do convidado** para Verdadeiro para habilitar o recurso. Quando essa configuração for ativada, uma notificação solicitará que você aprove o convidado para que ele possa ingressar na sessão.

    ![Solicitação de aprovação para ingressar do Visual Studio](../media/vs-join-approval.png)

    Confira o tópico [convites e acesso para ingressar](../reference/security.md#invitations-and-join-access) a fim de obter detalhes adicionais sobre considerações de segurança de convite.

8. **Gerenciar sua sessão do Live Share**
    
    Depois que o convidado abrir o link para sua sessão compartilhada no VS Code ou Visual Studio, você os verá listados como participantes na janela da ferramenta Live Share. Agora você consegue ver em qual arquivo o seu convidado está no momento ao lado do seu nome.  
    
    ![Janela de ferramentas do VS Live Share](../media/vs-live-share-tool-window-participant.png)

    A janela de ferramentas do Live Share permite acessar todos os principais recursos em um único lugar para gerenciar suas sessões. 

    > [!TIP]
    > Não consegue mais ver a janela de ferramentas do Live Share durante as sessões? Você sempre pode ir a **Modo de exibição &gt; Outras Janelas &gt; Live Share** para encontrá-la!

### <a name="ending-the-collaboration-session"></a>Encerrando a sessão de colaboração

Como um host, você pode interromper completamente o compartilhamento e encerrar a sessão de colaboração clicando no botão compartilhar/estado de sessão (no canto superior direito) e selecionando "Encerrar Sessão de Colaboração".

![Parar compartilhamento](../media/vs-stop-sharing.png)

Todos os convidados serão notificados de que a sessão foi encerrada. Depois que a sessão for encerrada, os convidados não poderão mais acessar o conteúdo e todos os arquivos temporários serão apagados automaticamente.

Está tendo problemas com o compartilhamento? Verifique a [solução de problemas](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Ingressar em uma sessão de colaboração

Depois de baixar e instalar o Visual Studio Live Share, os convidados só precisam executar algumas etapas para ingressar em uma sessão de colaboração hospedada. Há duas maneiras de ingresso: [por navegador](#join-via-the-browser) e [manualmente](#join-manually).

> **Dica de segurança:** Como um convidado ingressando em uma sessão de colaboração, é importante entender que os hosts podem restringir o acesso a determinados arquivos ou recursos. Quer entender as implicações de segurança de alguns recursos e configurações do Live Share? Confira o artigo sobre [segurança](../reference/security.md).

### <a name="join-via-the-browser"></a>Ingressar pelo navegador

A maneira mais fácil de ingressar em uma sessão de colaboração é simplesmente abrir o link de convite em um navegador da Web. Veja a seguir o que esperar ao seguir esse fluxo.

1. **Entrar**

    Depois de instalar a extensão Live Share, convém entrar para permitir que outros colaboradores saibam quem é você. Por padrão, o Visual Studio usa sua conta de personalização, de modo que você pode ignorar totalmente esta etapa.

    Confira o tópico [Entrar](#sign-in) para obter mais detalhes.

2. **Clicar no link de convite/abrir o convite no navegador**

    Agora, basta abrir (ou reabrir) o link de convite em um navegador.

    > **Observação**: se você ainda não instalou a extensão de Live share, você receberá links para o Marketplace de extensão. Instale a extensão, reinicie a ferramenta e tente novamente.

    Você receberá uma notificação de que o navegador quer iniciar uma ferramenta habilitada para o Live Share. Ao permitir a inicialização da ferramenta selecionada, você será conectado à sessão de colaboração quando ela começar.

    ![Página Ingressar](../media/join-page.png)

    Se o host estiver offline, você receberá uma notificação. Você pode entrar em contato com o host e solicitar o compartilhamento novamente.

    > [!NOTE]
    > Ainda está com problemas? Confira [ingressar manualmente](#join-manually).

3. **Colaborar**

    E pronto! Em poucos instantes você será conectado e poderá iniciar a colaboração.

    Você verá a transição do botão "Live Share" para transmitir um "Estado de Sessão". Confira as informações do [estado de sessão](#session-states) abaixo para ver sua aparência.

    Você será automaticamente levado para o arquivo que o host está editando no momento assim que o ingresso for concluído.

### <a name="join-manually"></a>Ingressar manualmente

Também é possível ingressar manualmente sem usar um navegador da Web, o que pode ser útil nas situações em que a ferramenta que você quer usar já estiver em execução, se quiser usar uma ferramenta diferente do que usa normalmente ou se estiver tendo problemas em fazer os links de convite funcionarem por algum motivo. O processo é fácil:

1. **Entrar**

    Depois de instalar a extensão Live Share, convém entrar para permitir que outros colaboradores saibam quem é você. Por padrão, o Visual Studio usa sua conta de personalização, de modo que você pode ignorar totalmente esta etapa.

    Confira o tópico [Entrar](#sign-in) para obter mais detalhes.

2. **Usar o comando de ingresso**

    Basta acessar **Arquivo > Ingressar na Sessão de Live Share**

    ![Menu de ingresso do VS](../media/vs-join.png)

3. **Colar o link do convite**

    Cole a URL do convite que você recebeu e confirme.

4. **Colaborar!**

    Pronto! Em breve, você deverá estar conectado à sessão de colaboração.

    Você verá a transição do botão "Live Share" para transmitir um "Estado de Sessão". Confira as informações do [estado de sessão](#session-states) abaixo para ver sua aparência.

    Você será automaticamente levado para onde o host está editando no momento assim que o ingresso for concluído.

### <a name="leave-the-collaboration-session"></a>Sair da sessão de colaboração

Como um convidado, você pode sair da sessão de colaboração sem encerrá-la para outras pessoas, bastando para isso fechar a ferramenta ou clicar no botão compartilhar/estado de sessão e selecionar "Sair da Sessão de Colaboração".

![Menu de ingresso do VS](../media/vs-leave-session.png)

Todos os arquivos temporários são automaticamente apagados, de modo que não é preciso fazer mais nada.

Está tendo problemas para ingressar? Verifique a [solução de problemas](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Coedição

Depois que um convidado tiver ingressado em uma sessão de colaboração, todos os colaboradores poderão ver imediatamente as edições e seleções uns dos outros em tempo real. Tudo o que você precisa fazer é escolher um arquivo no explorador de arquivos e começar a editar. Hosts e convidados verão as edições à medida que você as cria e poderão contribuir com elas, facilitando a iteração e a rapidez das soluções.

> [!NOTE]
> Ingressar em uma sessão de colaboração somente leitura impede convidados de fazer edições nos arquivos. Um host pode [habilitar o modo somente leitura quando compartilha](#share-a-project). Como um convidado, você pode saber se ingressou em uma sessão somente leitura observando seu [estado de sessão](#session-states).

![Captura de tela mostrando a coedição](../media/vs-coedit.png)

> [!NOTE]
> A coedição tem algumas limitações para determinados idiomas. Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades por linguagem.

Além de cursores e edições, as seleções feitas também ficam visíveis para todos os participantes no mesmo arquivo. Isso facilita destacar onde podem ocorrer problemas ou transmitir ideias.

![Captura de tela mostrando o realce](../media/vs-highlight.png)

Melhor ainda, você e outros participantes podem navegar para qualquer arquivo no projeto compartilhado. Você pode fazer edições em conjunto ou separadamente, o que significa que é possível alternar facilmente entre investigação, fazer pequenos ajustes e edição totalmente colaborativa.

> [!NOTE]
> Por padrão, o Live Share também compartilha arquivos abertos externos à solução compartilhada. Se quiser desabilitar esse recurso, atualize Compartilhar Arquivos Externos em Ferramentas &gt; Opções &gt; Live Share para Falso.

As edições resultantes são mantidas no computador do host no salvamento, de modo que não há necessidade de sincronizar, efetuar push nem de enviar arquivos depois de fazer a edição. As edições "estão lá".

> **Dica de segurança:** Considerando que todos os participantes podem navegar e editar arquivos de forma independente, como um host, talvez você queira restringir quais arquivos os convidados podem acessar em seu projeto por meio de um arquivo. vsls. JSON. Como um convidado, também é importante entender que você talvez não veja determinados arquivos como consequência dessas configurações. Confira [Controlar o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para saber mais detalhes.

### <a name="changing-participant-flag-behaviors"></a>Alterando os comportamentos do sinalizador do participante

Por padrão, o Visual Studio Live Share exibe automaticamente um "sinalizador" ao lado do cursor em foco de um participante, ou quando ele edita, realça ou move o respectivo cursor. Em alguns casos, talvez você prefira alterar esse comportamento. Para fazer isso:

1. Vá para **Ferramentas > Opções > Live Share**
2. Altere a opção **Visibilidade do sinalizador** para um destes estados:

| Opção | Comportamento |
|--------|----------|
| OnHoverOnly | O sinalizador só fica visível quando você focaliza o cursor. |
| OnHoverOrActivity | Este é o padrão. O sinalizador fica visível na focalização ou se o participante editar, realçar ou mover o próprio cursor. |
| Sempre | O sinalizador está sempre visível.

## <a name="following"></a>Seguindo

Sempre que estiver em uma sessão de colaboração, você poderá ver as iniciais de cada participante no canto superior direito do editor, ao lado do botão de entrada. Passar o mouse sobre as iniciais mostra informações completas do participante.

![Captura de tela mostrando usuário](../media/vs-person.png)

Às vezes, você pode ter que explicar um problema ou um design que abrange vários arquivos ou locais no código. Nessas situações, pode ser útil seguir temporariamente um colega enquanto ele percorre o projeto. Por esse motivo, como convidado, ao ingressar em uma sessão de colaboração, você automaticamente "seguirá" o host. Ao seguir um participante, seu editor permanecerá em sincronização com o arquivo aberto, o cursor e a posição de rolagem dele do momento.

> [!NOTE]
> Por padrão, o Live Share também compartilha arquivos abertos externos à solução compartilhada. Se quiser desabilitar esse recurso, atualize Compartilhar Arquivos Externos em Ferramentas &gt; Opções &gt; Live Share para Falso.

Para que fique fácil sair do "modo seguir" e começar a editar por conta própria, você vai parar de seguir automaticamente na ocorrência de uma destas situações:

1. Você edita, move o cursor ou faz uma seleção
2. Você seleciona outro arquivo

Você também pode parar de seguir a qualquer momento clicando, no canto superior direito, nas iniciais da pessoa que está seguindo. O círculo em volta das iniciais do participante que indica que você o está seguindo desaparecerá.

![Participante do Visual Studio sendo seguido](../media/vs-pinned.png) ![Participante do Visual Studio não sendo seguido](../media/vs-pin-hover.png)

Você pode clicar em quaisquer iniciais nesse mesmo local para seguir qualquer host ou convidado na sessão de colaboração. Observe que, se você quiser apenas pular para o local de alguém, em vez de segui-lo, basta clicar duas vezes em suas iniciais.

## <a name="focusing"></a>Focando

Ocasionalmente, talvez seja conveniente que todas as pessoas em uma sessão de colaboração vejam algo que você esteja fazendo. O Live Share permite solicitar a todos que "foquem" a atenção em você com uma notificação que facilita para eles o seguirem de volta.

Basta clicar no botão compartilhar/ estado de sessão no canto superior direito e selecionar "Focar a atenção dos participantes".

![Opção de menu Focar](../media/vs-focus.png)

Todos na sessão de colaboração receberão a notificação de que você solicitou a atenção deles

![Notificação do sistema para Focar](../media/vs-focus-toast.png)

Eles poderão apenas clicar em "Seguir" diretamente na notificação quando estiverem prontos para focarem em você.

## <a name="co-debugging"></a>Codepuração

O recurso de depuração colaborativa do Visual Studio Live Share é uma maneira exclusiva e avançada de depurar um problema. Além de proporcionar uma experiência colaborativa para a solução de problemas, ele também dá a você e aos outros participantes a capacidade de investigar problemas que possam ser específicos do ambiente, fornecendo uma sessão de depuração compartilhada no computador do host.

> **Dica de segurança:** Considerando que todos os participantes podem navegar e editar arquivos de forma independente, como um host, talvez você queira restringir quais arquivos os convidados podem acessar em seu projeto por meio de um arquivo. vsls. JSON. Você também deve estar ciente de que o acesso ao Console/REPL significa que os participantes podem executar comandos em seu computador, de modo que você só deve codepurar com as pessoas em quem confia. Como um convidado, também é importante entender que talvez você não possa seguir o depurador, uma vez que ele intervém em determinados arquivos que são restringidos como resultado dessas configurações. Confira [Controlar o acesso a arquivos e visibilidade](../reference/security.md#controlling-file-access-and-visibility) para saber mais detalhes.

A utilização é simples. O host da sessão de colaboração só precisa iniciar a depuração pelos meios normais no Visual Studio.

![Botão Depuração do VS](../media/vs-debug-button.png)

Depois que o depurador for anexado no lado do host, todos os convidados também serão automaticamente anexados. Enquanto houver uma "sessão" de depuração em execução no computador do host, todos os participantes serão conectados a ela e terão a sua própria exibição.

> [!TIP]
> Se quiser alterar quando e como a codepuração acontece, você poderá mudar os comportamentos padrão usando as configurações em **Ferramentas > Opções > Live Share**.

![Depurador anexado do VS](../media/vs-debugger.png)

Qualquer pessoa pode passar pelo processo de depuração, que permite alternância perfeita entre colaboradores sem ter que negociar o controle.

> [!NOTE]
> Confira [Suporte de plataforma](../reference/platform-support.md) para obter o estado das funcionalidades de depuração por linguagem ou plataforma.

Cada colaborador pode investigar variáveis diferentes, pular para arquivos diferentes na pilha de chamadas, inspecionar variáveis e, até mesmo, adicionar ou remover pontos de interrupção. Os recursos de coedição permitem que cada orador participante rastreie onde as outras pessoas estão localizadas para fornecer a capacidade exclusiva de alternar diretamente entre investigar simultaneamente diferentes aspectos do problema e depurar de maneira colaborativa.

> [!NOTE]
> Enquanto estiver em uma sessão de colaboração somente leitura, um convidado não poderá passar pelo processo de depuração. No entanto, ele pode adicionar ou remover pontos de interrupção e inspecionar variáveis.

> [!TIP]
> Você também pode participar de sessões de depuração do VS Code no Visual Studio, e vice-versa! Confira as [instruções do Visual Studio](vscode.md#co-debugging) em codepuração para obter mais informações.

### <a name="automatic-web-app-sharing"></a>Compartilhamento automático do aplicativo Web

Para projetos de Aplicativo Web ASP.NET, por padrão, se o projeto do host estiver configurado para iniciar automaticamente um navegador da Web a fim de se conectar ao aplicativo Web em execução durante a depuração, o Live Share automaticamente fará o mesmo no computador de cada convidado! Isso é feito de maneira segura e, por padrão, o aplicativo Web remoto só estará disponível para os convidados durante a sessão de depuração.

Confira o tópico [compartilhar um servidor](#share-a-server) para obter informações sobre como compartilhar o acesso ao servidor para outros tipos de projeto e/ou enquanto durar a sessão.

> [!TIP]
> Se não gosta do comportamento automatizado de compartilhamento do navegador e quer mudá-lo, você poderá atualizar as configurações em **Ferramentas > Opções > Live Share**.

![Animação de depuração simultânea](../media/co-debug.gif)

### <a name="change-when-visual-studio-joins-debugging-sessions"></a>Alterar quando o Visual Studio ingressa em sessões de depuração

Por padrão, como um convidado, você vai ser automaticamente anexado às sessões de depuração quando elas forem compartilhadas pelo host. No entanto, em alguns casos, você pode achar esse comportamento incômodo. Felizmente, você pode alterá-lo da seguinte maneira:

1. Vá para **Ferramentas > Opções > Live Share**
2. Altere a **opção para Ingressar na sessão de depuração** para uma das seguintes:

| Opção | Comportamento |
|--------|----------|
| Automática | O padrão. Como um convidado, você ingressará automaticamente em qualquer sessão de depuração compartilhada iniciada pelo host. |
| Solicitado | Como um convidado, será perguntado se você deseja ingressar em uma sessão de depuração compartilhada quando ela for iniciada pelo host. |
| Manual | Como convidado, você precisará ingressar manualmente em qualquer sessão de depuração. Confira [desanexando e reanexando](#detaching-and-reattaching).|

### <a name="detaching-and-reattaching"></a>Desanexando e reanexando

Como um convidado, você pode querer interromper a depuração temporariamente. Felizmente, você pode simplesmente clicar no ícone "parar" na barra de ferramentas de depuração para desanexar o depurador sem afetar o anfitrião ou outros convidados.

Se você atualizou as configurações para que não seja mais possível a anexação automática ou se você simplesmente quer reanexar posteriormente, basta selecionar a sessão de depuração em execução desejada no menu suspenso "Selecionar Item de Inicialização...".

![Botão Depuração do VS](../media/vs-select-reattach.png)

... e, em seguida, clicar nela para anexar.

![Botão Depuração do VS](../media/vs-reattach.png)

## <a name="share-a-server"></a>Compartilhar um servidor

De tempos em tempos, como um host da sessão de colaboração, você pode achar conveniente compartilhar serviços ou servidores locais adicionais com convidados. Isso pode variar de outros pontos de extremidade RESTful a bancos de dados ou outros servidores. O Visual Studio Live Share permite que você especifique um número de porta local, se desejar, dê um nome a ele e, em seguida, o compartilhe com todos os convidados.

Os convidados poderão então acessar o servidor compartilhado por você nessa porta dos respectivos computadores locais nessa mesma porta. Por exemplo, se você compartilhou um servidor Web **em execução na porta 3000**, o convidado poderá acessar esse mesmo servidor Web em execução nos **próprios computadores** em http://localhost:3000! Isso é feito por meio de um túnel SSH ou SSL seguro entre o host e os convidados e autenticado por meio do serviço, de modo que você possa ter certeza de que apenas as pessoas na sessão de colaboração tenham acesso.

> **Dica de segurança:** Como um host, você deve ser muito seletivo com as portas que você compartilha com convidados e para portas de aplicativo (em vez de compartilhar uma porta do sistema). Para convidados, as portas compartilhadas se comportarão exatamente como fariam se o servidor/serviço estivesse em execução em seu próprio computador. Isso é muito útil, mas se a porta errada for compartilhada, isso também poderá ser um risco.

Por motivos de segurança, somente servidores em execução em portas que você especifica são disponibilizadas para outros convidados. Felizmente, é fácil adicionar um como o **host**da sessão de colaboração. Veja como:

1. Clique no botão compartilhar/estado de sessão no canto superior direito e selecione "Gerenciar Servidores Locais Compartilhados"

    ![Gerenciar Servidores Locais Compartilhados](../media/vs-share-local-servers.png)

2. Na caixa de diálogo que aparece, clique em "Adicionar", insira o número da porta em que o servidor está em execução localmente, informe um nome, pressione enter e OK.

    ![Gerenciar Servidores Locais Compartilhados](../media/vs-manage-local-shared-servers.png)

Pronto! O servidor na porta especificada agora será mapeado para o localhost de cada convidado na mesma porta (a menos que a porta já esteja ocupada)!

Se a porta já estiver em uso no computador de um convidado, outra será selecionada automaticamente. Felizmente, como um convidado, você pode ver uma lista de portas atualmente compartilhadas (por nome, se especificado) clicando no botão compartilhar/estado de sessão no canto superior direito e selecionando "Exibir Servidores Locais Compartilhados".

![Exibir Servidores Locais Compartilhados](../media/vs-view-shared-servers.png)

Observe que, por motivos de segurança, os *convidados não podem* controlar quais portas no computador do host são compartilhadas.

Para **interromper** o compartilhamento de um servidor local, o host só precisa clicar no botão compartilhar/estado de sessão no canto superior direito, como acima, selecionar "Gerenciar Servidores Locais Compartilhados", selecionar a porta adequada e clicar em "Remover".

## <a name="share-a-terminal"></a>Compartilhar um terminal

O desenvolvimento moderno faz uso frequente de uma ampla gama de ferramentas de linha de comando. Felizmente, o Live Share permite que você, como host, se desejar, "compartilhe um terminal" com os convidados. O terminal compartilhado pode ser somente leitura ou totalmente colaborativo, de modo que você e os convidados possam executar comandos e ver os resultados. Você pode dar aos convidados visibilidade da saída do terminal ou permitir que eles ganhem experiência e executem testes, compilações ou, até mesmo, façam triagem de problemas específicos de ambiente que acontecem somente em seu computador.

No entanto, os terminais **não** são compartilhados por padrão, pois eles dão aos convidados no mínimo acesso somente leitura à saída dos comandos que você executa (se não a capacidade de executar comandos por conta própria). Dessa maneira, é possível executar comandos livremente nos terminais locais sem riscos e compartilhar somente quando realmente for preciso. Além disso, somente hosts podem iniciar terminais compartilhados para impedir os convidados de iniciar um e fazer algo que você não está esperando nem observando.

Como um host, você pode compartilhar um terminal clicando no botão estado de sessão/compartilhar no canto superior direito e selecionando um dos itens de menu "Compartilhar Terminal".

![Menu do terminal](../media/vs-terminal-menu.png)

Neste ponto, você pode selecionar um terminal somente leitura ou leitura/gravação no menu. Quando o terminal for leitura/gravação, todos poderão digitar no terminal, incluindo o host, o que facilita a intervenção caso um convidado faça algo indesejável. No entanto, para que seja seguro, você deve **dar somente acesso de leitura/gravação aos convidados quando tiver ciência de que eles realmente precisam** e continuar com os terminais somente leitura para cenários em que deseja que o convidado veja apenas a saída dos comandos que você executa.

> [!NOTE]
> Se a sessão de colaboração estiver no modo somente leitura, somente os terminais somente leitura poderão ser compartilhados pelo host.

Uma vez selecionado o tipo de terminal compartilhado que você quer iniciar, um novo terminal compartilhado aparecerá para todos os participantes com as permissões corretas. Enquanto o Visual Studio Code tem um suporte de terminal interno, o Visual Studio não tem um pronto para uso. Portanto, por padrão, será exibida uma nova janela contendo o terminal. No entanto, no caso de uma [extensão Whack Whack Terminal](https://marketplace.visualstudio.com/items?itemName=DanielGriffen.WhackWhackTerminal), o Live Share criará um terminal integrado. O Visual Studio fornecerá um link para instá-lo na primeira vez que você iniciar um terminal compartilhado ou ingressar em um.

![Notificação do sistema de instalação de terminal](../media/vs-terminal-install.png)

Para encerrar a sessão de terminal, basta digitar sair (exit) ou fechar a janela do terminal e todos serão desconectados.

## <a name="session-states"></a>Estados de sessão

Depois de iniciar ou ingressar em uma sessão de colaboração e ter acesso ao conteúdo compartilhado, a aparência do botão "Live Share", no canto superior direito, será atualizada para refletir o estado da sessão de colaboração ativa.

Estes são os estados que você normalmente verá:

| Estado | Botão | Descrição |
|-------|--------|-------------|
| Inativo | ![Status do VS: inativo](../media/vs-status-share.png) | Nenhuma sessão de colaboração ativa e nada está compartilhado. |
| Host: compartilhamento em andamento | ![Status do VS: compartilhar em andamento](../media/vs-status-sharing.png) | Uma sessão de colaboração está iniciando e o compartilhamento do conteúdo começará em breve. |
| Host: compartilhamento | ![Status do VS: compartilhamento ativo ](../media/vs-status-active.png) | Uma sessão de colaboração está ativa e o conteúdo está compartilhado. |
| Host: compartilhamento somente leitura | ![Status do VS: compartilhamento somente leitura](../media/vs-status-sharing-read-only.png)| Compartilhando uma sessão de colaboração somente leitura. |
| Convidado: ingressando na sessão | ![Status do VS Code: ingressando](../media/vs-status-joining.png) | Ingressando em uma sessão de colaboração existente. |
| Convidado: Unido | ![Status do VS: ingressou](../media/vs-status-joined.png) | Ingressou e conectou-se a uma sessão de colaboração ativa e está recebendo conteúdo compartilhado. |
| Convidado: associado somente leitura | ![Status do VS: ingressou somente leitura](../media/vs-status-joined-read-only.png) | Ingressou e conectou-se a uma sessão de colaboração somente leitura. |

## <a name="guest-limitations"></a>Limitações do convidado

Embora, no momento, existam algumas falhas com as quais os usuários vão se deparar enquanto estiverem usando os recursos descritos acima, os hosts da sessão de colaboração mantêm a funcionalidade completa de sua ferramenta de escolha. Veja o seguinte para obter mais informações:

- [Suporte de idioma e plataforma](../reference/platform-support.md)
- [Suporte de extensão](../reference/extensions.md)
- [Todos os bugs, solicitações de recursos e limitações importantes](https://aka.ms/vsls-issues)
- [Todas as solicitações de recursos e limitações](https://aka.ms/vsls-feature-requests)

## <a name="next-steps"></a>Próximas etapas

Confira estes outros artigos para saber mais.

- [Início rápido: compartilhar seu primeiro projeto](../quickstart/share.md)
- [Início rápido: ingressar na sua primeira sessão](../quickstart/join.md)
- [Como colaborar usando o Visual Studio Code](vscode.md)
- [Requisitos de conectividade do Live Share](../reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](../reference/security.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
