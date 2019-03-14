---
title: Security - compartilhamento ao vivo do Visual Studio | Microsoft Docs
description: Informações sobre os recursos de segurança do Visual Studio Live Share.
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 0bc97691ca7733f694190e86140b930e68657ade
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255224"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Recursos de segurança do Live Share

Sessões de colaboração no Visual Studio Live Share são poderosas, em que eles permitem que qualquer número de pessoas para ingressar em uma sessão e colaborativamente editar, depurar e muito mais. No entanto, devido a esse nível de acesso, você, sem dúvida, se interessará Live Share fornece os recursos de segurança. Neste artigo, forneceremos algumas recomendações e opções para proteger seu ambiente, conforme necessário.

**Assim como acontece com qualquer ferramenta de colaboração, lembre-se de que você só deve compartilhar seu código, conteúdo e aplicativos com pessoas que confiáveis.**

## <a name="connectivity"></a>Conectividade

Todas as conexões no Visual Studio Live Share são SSH ou SSL criptografadas e autenticadas em relação a um serviço central para garantir que somente aqueles na sessão de colaboração podem acessar seu conteúdo. Por padrão, o Live Share tenta uma conexão direta e volta em uma retransmissão de nuvem se não for possível estabelecer uma conexão entre o convidado e o host. Observe que a retransmissão de nuvem do Live Share não persiste qualquer tráfego roteado por ele e não "rastrear" o tráfego de qualquer forma. No entanto, se você preferir não usar a retransmissão, você pode alterar configurações sempre se conecte diretamente.

Para obter mais informações sobre como alterar esses comportamentos e os requisitos de conectividade do Live Share, consulte  **[requisitos de conectividade para Live Share](connectivity.md)**.

## <a name="invitations-and-join-access"></a>Convites e acesso de junção

Cada vez que você inicia uma nova sessão de colaboração, Live Share gera uma **novo identificador exclusivo** que é colocado no link de convite. Estes links fornecem uma base sólida e segura para convidar aqueles confiar, pois o identificador de link é "não adivinhar" e é _válido somente para a duração de uma sessão de colaboração único_.

### <a name="removing-an-unexpected-guest"></a>Removendo um convidado inesperado

Como um host, você será notificado automaticamente sempre que um convidado une a sessão de colaboração.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

Melhor ainda, a notificação fornece a capacidade de remover um convidado que ingressou se por alguma razão você não soubê-los. (Por exemplo, se você acidentalmente lançou seu link em um sistema de chat de toda a empresa e associados de um funcionário aleatório). Basta clicar no botão "Remover" na notificação que aparece, e eles serão ser desconsiderados da sessão de colaboração.

Na **VS Code**, mesmo se você tiver ignorado uma notificação de junção, você também tem a capacidade de remover um participante depois disso. Abrindo o modo de exibição do Live Share no Explorer ou na guia personalizada na barra de atividade do VS Code, passe o mouse sobre ou nome de um participante botão direito do mouse e selecione o ícone de "Remover participante" ou a opção.

![Remover o participante no VS Code](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>Exigir a aprovação de convidado

Normalmente, os participantes que ingressar em uma sessão de colaboração serão **entrou no Live Share** usando um trabalho da Microsoft ou conta de Estudante (AAD), conta pessoal da Microsoft ou conta do GitHub. Embora "notificação + remover" padrão para os usuários conectado fornece uma boa combinação de velocidade e controle para esses convidados, você talvez queira **bloquear coisas** um pouco mais, se você estiver fazendo algo confidenciais.

Além disso, em determinadas circunstâncias forçar todos os convidados para entrar para ingressar em uma colaboração de sessão pode ser problemática. Os exemplos incluem solicitando que alguém de novo no Live Share ingressar como convidado, cenários de aprendizado em sala de aula /, ou quando colaboram com alguém que não tem um dos tipos de conta com suporte. Por esses motivos, Live Share pode permitir que os usuários que estão **não tiver entrado** para ingressar em sessões de colaboração como **somente leitura** convidados. Enquanto o host precisa **aprovar** esses convidados para que possam participar por padrão, convém desabilitar esses convidados "anônimos" ou sempre aprová-las em vez disso.

#### <a name="requiring-guest-approval-for-signed-in-users"></a>Exigir aprovação do convidado para entrar em usuários

Se desejar impedir assinado em convidados ingressem sua colaboração sessões até ter "aprovado"-los, altere a seguinte configuração:

* Na **VS Code**, adicione o seguinte ao Settings (arquivo > Preferências > Configurações):

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* Na **Visual Studio**, conjunto de ferramentas > Opções > Live Share > "Exigir aprovação do convidado" como True.

    ![Janela de configurações do Visual Studio com a configuração de aprovação de convidado realçado](../media/vs-setting-guestapproval.png)

Desse ponto, você será solicitado a aprovar cada convidado que une.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-approval.png" width="100%" alt="Visual Studio Code join approval request" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-approval.png" width="100%" alt="Visual Studio join approval request"/>
    </td>
</tr>
</table>

Como um convidado, se você ingressar em uma sessão em que o host tem essa configuração habilitada, você será notificado na barra de status ou ingressar diálogo Live Share está aguardando o host para aprovar.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>Usuários aceitando ou rejeitando o automático não estiver conectados (anônimo)

Conforme descrito acima, o Live Share pode ser configurado para permitir **os usuários que não se conectaram** para ingressar em uma sessão de colaboração como **somente leitura** convidados.  Embora todos esses **convidados "anônimos" Insira um nome de** ao unir, um nome simples não fornece o mesmo nível de garantia de que uma entrada real. Portanto, **por padrão, o host é solicitado a aprovar** qualquer convidado anônimo, independentemente de "exigir aprovação do convidado" definindo descrito acima.

Você pode **sempre rejeitar** (desabilitar convidados anônimos) ou **sempre aceitar** usuários anônimos em vez da seguinte maneira:

* Na **VS Code**, defina `liveshare.anonymousGuestApproval` em Settings (arquivo > Preferências > Configurações) para `accept`, `reject`, ou `prompt` (o padrão) conforme apropriado.

* Na **Visual Studio**, conjunto de ferramentas > Opções > Live Share > "aprovação de convidado anônimo" para aceitar, rejeitar ou Prompt (o padrão), como apropriado.

 **Independentemente disso, lembre-se de que você só deve enviar Live Share links de convite a pessoas que você confiam.**

## <a name="controlling-file-access-and-visibility"></a>Visibilidade e controle de acesso de arquivo

Como um convidado, modelo de remoto do Live Share lhe dá acesso rápido de leitura/gravação a arquivos e pastas que o host tenha compartilhado com você, sem a necessidade de sincronizar todo o conteúdo de um projeto. Pode, portanto, independentemente navegar e editar arquivos na árvore de todo o arquivo compartilhado. **No entanto, essa liberdade representam alguns riscos para o host.** Em conceito, um desenvolvedor pode optar por entrar e modificar o código-fonte sem seu conhecimento ou consulte o código-fonte confidenciais ou "segredos" localizados em algum lugar na árvore de arquivos compartilhados. Consequentemente, como um host, não é sempre aconselhável convidado para ter acesso a todo um projeto que você está compartilhando. Felizmente, a vantagem desse modelo remoto é que você pode optar por arquivos que não deseja compartilhar com qualquer pessoa sem sacrificar a funcionalidade de "excluir". Os convidados podem participar de coisas como as que normalmente exigiriam acesso a esses arquivos, caso desejem fazê-lo em suas próprias sessões de depuração.

Você pode fazer isso adicionando um **. vsls.json** arquivo para a pasta ou o projeto que você está compartilhando. Todas as configurações que você adicionar a este arquivo com formato json altera como o Live Share processa arquivos. Além de fornecer a você controle direto, esses arquivos também podem ser confirmados ao controle do código-fonte para que qualquer pessoa a clonagem de um projeto seja capaz de tirar proveito dessas regras sem esforço adicional de sua parte.

Aqui está um exemplo. vsls.json arquivo:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"none",
    "excludeFiles":[
        "*.p12",
        "*.cer",
        "token",
        ".gitignore"
    ],
    "hideFiles": [
        "bin",
        "obj"
    ]
}
```

> [!NOTE]
> Você também pode tornar as todos os arquivos/pastas você compartilha **somente leitura** ao iniciar uma sessão de colaboração. Ver [abaixo](#read-only-mode) para obter detalhes.

Vamos examinar como essas propriedades para alterar o que eles podem fazer.

### <a name="properties"></a>Propriedades

O **excludeFiles** propriedade permite que você especifique uma lista de padrões de arquivo de glob (muito parecido com aqueles encontrados arquivos. gitignore muito) que impede que o Live Share abrir determinados arquivos ou pastas para os convidados. Lembre-se de que se trata inclui cenários como um convidado _seguir ou indo para seu local de edição, depuração em um arquivo durante a depuração de colaboração, quaisquer recursos de navegação de código, como ir para definição e muito mais._ Destina-se a arquivos que você nunca deseja compartilhar em nenhuma circunstância, como aqueles que contém segredos, certificados ou senhas. Por exemplo, já que elas controlam a segurança,. vsls.json arquivos sempre são excluídos.

O **hideFiles** propriedade é semelhante, mas não tão rígida. Esses arquivos simplesmente estão ocultos da árvore de arquivos. Por exemplo, se você entrar em um desses arquivos durante a depuração, ele ainda está aberto no editor. Essa propriedade é útil principalmente se você não tiver uma configuração de arquivo. gitignore (como seria o caso se você estiver usando um sistema de controle do código-fonte diferente), ou se você simplesmente deseja ampliar o que já está lá para evitar confusão ou confusão.

O **gitignore** configuração estabelece como Live Share deve processar o conteúdo dos arquivos. gitignore em pastas compartilhadas. Por padrão, qualquer globs encontradas nos arquivos. gitignore são tratados como se eles foram especificados na propriedade "hideFiles". No entanto, você pode escolher um comportamento diferente usando um dos seguintes valores:

| Opção    | Resultado                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | conteúdo. gitignore é visível para os convidados na árvore de arquivos (supondo que eles não são filtrados por um configuração do editor de convidado). |
| `hide`    | **O padrão.** Globs dentro de. gitignore são processados como se fossem na propriedade "hideFiles".                   |
| `exclude` | Globs dentro de. gitignore são processados como se fossem na propriedade "excludeFiles".                                 |

Uma desvantagem de `exclude` configuração é que o conteúdo de pastas como node_modules está frequentemente em. gitignore, mas pode ser útil para intervir durante a depuração. Consequentemente, o Live Share suporta a capacidade de reverter uma regra usando "!" na propriedade excludeFiles. Por exemplo, isso. arquivo vsls.json seria excluir tudo no ". gitignore", exceto node_modules:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

As regras de ocultar e excluir são processadas separadamente, portanto, se você ainda quiser ocultar node_modules para reduzir a desordem sem a exclusão, na verdade, ele, é possível simplesmente editar o arquivo da seguinte maneira:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ],
    "hideFiles":[
        "node_modules"
    ]
}
```

### <a name="vslsjson-files-in-sub-folders"></a>. vsls.json arquivos em subpastas

Por fim, assim como. gitignore,. vsls.json arquivos podem ser colocados em subpastas. Ocultar/excluir regras são determinadas pelo começando com o. vsls.json arquivo na pasta raiz que você compartilhou (se houver) e, em seguida, percorrer em cada subpasta de líderes lá para um determinado arquivo a ser procurado. vsls.json arquivos ao processo. O conteúdo de. vsls.json arquivos nas pastas mais abaixo na árvore de arquivos, em seguida, complementar (ou substituir) regras estabelecidas em níveis mais altos.

### <a name="disabling-external-file-sharing"></a>Desabilitar o compartilhamento de arquivo externo

Por padrão, Live Share também compartilhará todos os arquivos abre o host que são externos à pasta compartilhada / solução. Isso torna fácil abrir outros arquivos relacionados rapidamente sem precisar compartilhar novamente.

Se você preferir desabilitar esse recurso:

* Na **VS Code**, adicione o seguinte ao Settings:

    ```json
    "liveshare.shareExternalFiles": false
    ```

* Na **Visual Studio**, conjunto de ferramentas &gt; opções &gt; Live Share &gt; "Arquivos externos de compartilhamento" como False

## <a name="read-only-mode"></a>Modo somente leitura

Às vezes, quando você compartilha seu código como um host, você não deseja fazer edições os convidados. Talvez você precise sua convidada para dar uma olhada em alguns dos seus códigos, ou você está mostrando o seu projeto para um grande número de convidados e não quiser que todas as edições de desnecessárias ou acidentais sejam feitas. Compartilhamento ao vivo oferece a capacidade de compartilhar projetos no modo somente leitura.

Como um host, ao compartilhar, você tem a opção para habilitar o modo somente leitura para uma sessão de colaboração. Quando ingressa em um convidado, eles não poderão fazer edições ao código, embora você ainda pode ver uns dos outros cursores e destaca bem como navegar por meio do projeto.

Você ainda poderá depurar junto com convidados enquanto estiver no modo somente leitura. Os convidados não terá a capacidade de percorrer o processo de depuração, mas pode ainda adicionar ou remover pontos de interrupção e inspecionar variáveis. Além disso, você ainda pode compartilhar terminais (somente leitura) e servidores com convidados.

Você pode aprender mais sobre como iniciar uma sessão de colaboração de somente leitura: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>Codepuração

Quando você enfrenta problemas complexos de codificação ou bugs, pode ser realmente útil ter um par de olhos durante a depuração. Visual Studio Live Share permite que o "debugging colaborativa" ou "co debugging" compartilhando a sessão de depuração com todos os convidados, sempre que o host inicia a depuração.

Como um host, você está no controle total sobre quando uma sessão de depuração é iniciada ou paradas, mas a depuração de co representam alguns riscos, se você estiver compartilhando com alguém, você não confia. Compartilhamento ao vivo permite que os convidados convidar para executar comandos REPL/console e, portanto, há **um risco de execução de um comando que você não desejaria executá-los de um ator mal-intencionado**.

Consequentemente, você deve **depurar somente junto com aqueles você confia.**

Saiba Mais: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>Um servidor de local de compartilhamento

Durante a codepuração, pode ser muito útil obter acesso a diferentes partes do aplicativo que está sendo fornecido pelo host para a sessão de depuração. Você talvez queira acessar o aplicativo em um navegador, acessar um banco de dados local ou um ponto de extremidade REST de suas ferramentas de ocorrências. Compartilhamento ao vivo permite que você "compartilhamento de um servidor" que mapeia uma porta local na máquina do host para a mesma porta exata na máquina do convidado. Como um convidado, você pode interagir com o aplicativo exatamente como se fosse executado localmente em seu computador (por exemplo, o host e convidado podem ambos acessar um aplicativo web em execução no http://localhost:3000).

No entanto, como um host, você deve **ser muito seletiva com as portas que você compartilhe** com convidados e apenas o compartilhamento em vez disso, as portas do sistema de portas de aplicativo. Para convidados, portas compartilhadas se comportará exatamente como fariam se o serviço do servidor/estava em execução no seu próprio computador. Isso é muito útil, mas se a porta errada for compartilhada também pode ser arriscado. Por esse motivo, o Live Share não faz nenhuma suposição sobre o que deve ou não deve ser compartilhado sem uma definição de configuração e o host executando uma ação.

No Visual Studio, o **porta do aplicativo de web** especificado em projetos do ASP.NET é **compartilhadas automaticamente durante a depuração somente** para facilitar o acesso de convidado para o aplicativo web durante a execução. No entanto, você pode desativar essa automação definindo Ferramentas > Opções > Live Share > "Compartilhamento web app em debug" como "False" Se você preferir.

No Visual Studio Code, Live Share tenta **detectar as portas do aplicativo apropriado** e compartilhá-los. No entanto, é possível desabilitar isso adicionando o seguinte para Settings:

        liveshare.autoShareServers: false

Em ambos os casos, tenha cuidado ao compartilhar portas adicionais.

Você pode aprender mais sobre como configurar o recurso aqui: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>Um terminal de compartilhamento

O desenvolvimento moderno faz uso frequente de uma ampla gama de ferramentas de linha de comando. Felizmente, o Live Share permite que você, como host, opcionalmente, "compartilhe um terminal" com os convidados. Terminal compartilhado pode ser somente leitura ou totalmente colaborativo para que você e os convidados possam executar comandos e ver os resultados. Como o host, você é capaz de permitir que outros colaboradores como apenas ver a saída ou para usar qualquer número de linha de comando de ferramentas para executar testes, compilações, ou até mesmo triagem problemas específicos do ambiente.

Somente os hosts podem começar a terminais compartilhados para impedir que os convidados da inicialização de um e fazendo algo não estiver esperando ou assistindo. Quando você inicia um terminal compartilhado como um host, você pode especificar se ele deve ser somente leitura ou leitura/gravação. Quando o terminal é leitura/gravação, todas as pessoas podem digitar no terminal, incluindo o que torna mais fácil interfira, se um convidado está fazendo algo que você não gosta do host. No entanto, para ser seguro, você deve **conceda acesso de leitura/gravação para os convidados somente quando você sabe que eles realmente precisam** e permanecer fiel a terminais de somente leitura para cenários em que você deseja apenas convidado para ver a saída de qualquer comando executado.

No Visual Studio, os terminais não são compartilhadas por padrão. No VS Code, terminais são compartilhadas automaticamente **somente leitura** por padrão. No entanto, é possível desabilitar isso adicionando o seguinte para Settings:

```json
"liveshare.autoShareTerminals": false
```

Saiba Mais: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>Consentimento do administrador AAD

Quando entrar usando um Microsoft feito **corporativa ou de estudante de endereço de email** você poderá ver uma mensagem informando que **"Precisa de aprovação de administrador"** ao entrar. Isso ocorre porque o Live Share requer acesso de leitura às informações de usuário para seus recursos de segurança e seu locatário do AD do Azure está configurado para exigir "consentimento do administrador" para novos aplicativos acessando o conteúdo do diretório.

Seu administrador do AD precisa resolver o problema para você usando as seguintes informações:

* **Nome do aplicativo**: Compartilhamento ao vivo do Visual Studio (Insiders)
* **Tipo de aplicativo**: Aplicativo Web
* **Status de aplicativos**: Produção
* **Permissões delegadas**: User.Read
* **URL do aplicativo**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **A URL de resposta**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Isso só precisa ser feito uma vez para qualquer pessoa que usar o Live Share. Ver [aqui](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) e [aqui](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) para obter detalhes.

## <a name="see-also"></a>Consulte também

* [Como: Colaborar usando o Visual Studio Code](../use/vscode.md)
* [Como: Colaborar usando o Visual Studio](../use/vs.md)
* [Requisitos de conectividade do Live Share](connectivity.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
