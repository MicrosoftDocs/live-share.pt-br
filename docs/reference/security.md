---
title: Segurança-Visual Studio Live Share | Microsoft Docs
description: Informações sobre os recursos de segurança do Visual Studio Live Share.
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 2d471a6d5ba84efb192073799444a13f2be62279
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2020
ms.locfileid: "80295965"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Recursos de segurança do Live Share

As sessões de colaboração no Visual Studio Live Share são poderosas, pois permitem que qualquer número de pessoas ingresse em uma sessão e edite, depure e mais de forma colaborativa. No entanto, considerando esse nível de acesso, sem dúvida você estará interessado nos recursos de segurança que o Live Share fornece. Neste artigo, forneceremos algumas recomendações e opções para proteger seu ambiente, conforme necessário.

**Assim como acontece com qualquer ferramenta de colaboração, lembre-se de que você só deve compartilhar seu código, conteúdo e aplicativos com as pessoas confiáveis.**

## <a name="connectivity"></a>Conectividade

Ao iniciar uma sessão entre os pares, Live Share tenta estabelecer uma conexão ponto a ponto e somente se isso não for possível (por exemplo, devido a firewalls/NATs), ele retornará ao uso de uma retransmissão de nuvem. No entanto, em ambos os tipos de conexão (P2P ou Relay), todos os dados transmitidos entre os pares são criptografados de ponta a ponta usando o protocolo SSH. No caso de uma conexão de retransmissão, a criptografia SSH é encaixada na parte superior dos WebSockets criptografados por TLS. Isso significa que Live Share não depende do serviço de retransmissão de nuvem para segurança. Mesmo que a retransmissão tenha sido comprometida, não foi possível descriptografar nenhuma das Live Share comunicação.

A função do serviço de Live Share é limitada à autenticação de usuário e à descoberta de sessão. O serviço em si não armazena ou nunca tem acesso a qualquer conteúdo de uma sessão. Todo o conteúdo do usuário no Live Share é transmitido pela sessão SSH. Isso inclui código, terminais, servidores compartilhados e quaisquer outros recursos de colaboração fornecidos por Live Share ou extensões que se baseiam nele.

Para saber mais sobre como alterar esses comportamentos e os requisitos de conectividade de Live Share, consulte **[requisitos de conectividade para Live share](connectivity.md)** .

### <a name="wire-encryption"></a>Criptografia de transmissão 

O protocolo SSH usa uma troca de chaves Diffie-Hellman para estabelecer um segredo compartilhado para a sessão e deriva de uma chave para a criptografia simétrica AES. A chave de criptografia é girada periodicamente durante a duração da sessão. O segredo da sessão compartilhada e todas as chaves de criptografia só são mantidas na memória por ambos os lados e só são válidas durante a sessão. Eles nunca são gravados em disco ou enviados a qualquer serviço (incluindo Live Share).

### <a name="peer-authentication"></a>Autenticação de mesmo nível

A sessão SSH também é autenticada duas vias. O host (função de servidor SSH) usa a autenticação de chave pública/privada como é o padrão para o protocolo SSH. Quando um host compartilha uma sessão de Live Share, ele gera um par de chaves pública/privada RSA exclusivo para a sessão. A chave privada do host é mantida somente na memória no processo do host; Ele nunca é gravado em disco ou enviado para qualquer serviço, incluindo o serviço Live Share. A chave pública do host é publicada no serviço de Live Share, juntamente com as informações de conexão da sessão (endereço IP e/ou ponto de extremidade de retransmissão), em que os convidados podem acessá-lo por meio do link de convite. Quando um convidado se conecta à sessão SSH do host, o convidado usa o protocolo de autenticação de host SSH para validar se o host contém a chave privada correspondente à chave pública publicada (sem que o convidado realmente Veja a chave privada).

O convidado usa um token Live Share para se autenticar com o host. O token é um JWT assinado emitido pelo serviço de Live Share que inclui declarações sobre a identidade do usuário (obtida via MSA, AAD ou entrada do GitHub). O token também tem declarações que indicam que o convidado tem permissão para acessar essa sessão de Live Share específica (porque elas tinham o link de convite e/ou foram especificamente convidadas pelo host). O host valida esse token e verifica as declarações (e dependendo das opções podem solicitar o usuário host) antes de permitir que o convidado ingresse na sessão.

## <a name="invitations-and-join-access"></a>Convites e ingressar no acesso

Cada vez que você inicia uma nova sessão de colaboração, o Live Share gera um **novo identificador exclusivo** que é colocado no link de convite. Esses links fornecem uma base sólida e segura para convidar quem você confia, pois o identificador no link é "não-adivinhable" e _só é válido pela duração de uma única sessão de colaboração_.

### <a name="removing-an-unexpected-guest"></a>Removendo um convidado inesperado

Como um host, você será notificado automaticamente sempre que um convidado ingressar na sessão de colaboração.

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

Melhor ainda, a notificação fornece a capacidade de remover um convidado que ingressou se, por alguma razão, você não souber. (Por exemplo, se você postou acidentalmente seu link em um sistema de bate-papo de toda a empresa e um funcionário aleatoriamente ingressado.) Basta clicar no botão "remover" na notificação que aparece e eles serão ejetados da sessão de colaboração.

Em **vs Code**, mesmo se você tiver Descartado uma notificação de junção, também poderá remover um participante depois disso. Ao abrir o modo de exibição de Live Share no Explorer ou na guia personalizado na barra de atividade do VS Code, você pode passar o mouse sobre o nome de um participante ou clicar com o botão direito e selecionar o ícone ou a opção "remover participante".

![Remover participante em VS Code](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>Exigindo aprovação de convidado

Normalmente, os participantes que ingressarem em uma sessão de colaboração entrarão **em Live share** usando uma conta corporativa ou de estudante (AAD) da Microsoft, conta Microsoft pessoal ou um github. Embora o padrão "notificação + remover" para usuários conectados forneça uma boa combinação de velocidade e controle para esses convidados, talvez você queira bloquear as **coisas** um pouco mais se estiver fazendo algo confidencial.

Além disso, em determinadas circunstâncias, forçar a entrada de todos os convidados para ingressar em uma sessão de colaboração pode ser problemática. Os exemplos incluem solicitar que alguém novo Live Share ingresse como um convidado, cenários de aprendizado/sala de aula ou ao colaborar com alguém que não tenha um dos tipos de conta com suporte. Por esses motivos, Live Share pode permitir que os usuários que **não estão conectados** ingressem sessões de colaboração como convidados **somente leitura** . Embora o host precise **aprovar** esses convidados antes que possam ingressar por padrão, convém não permitir esses convidados "anônimos" ou sempre aprová-los.

#### <a name="requiring-guest-approval-for-signed-in-users"></a>Exigindo aprovação de convidado para usuários conectados

Se desejar impedir que os convidados conectados ingressem em suas sessões de colaboração até que você os tenha "aprovado", altere a seguinte configuração:

* Em **vs Code**, adicione o seguinte a Settings. JSON (arquivo > Preferências > configurações):

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* No **Visual Studio**, defina ferramentas > opções > Live share > "exigir aprovação de convidado" para verdadeiro.

    ![Janela Configurações do Visual Studio com configuração de aprovação de convidado realçada](../media/vs-setting-guestapproval.png)

Deste ponto em diante, você será solicitado a aprovar cada convidado que ingressar.

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

Como convidado, se você ingressar em uma sessão na qual o host tem essa configuração habilitada, você será notificado na barra de status ou na caixa de diálogo de junção que Live Share está aguardando o host para aprovar.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>Rejeição automática ou aceitação de usuários que não estão conectados (anônimo)

Conforme descrito acima, Live Share pode ser configurado para permitir **que os usuários que não estão conectados** ingressem em uma sessão de colaboração como convidados **somente leitura** .  Embora esses **convidados "anônimos" devam inserir um nome** ao ingressar, um nome simples não fornece o mesmo nível de garantia que uma entrada real. Portanto, **por padrão, o host é solicitado a aprovar** qualquer convidado anônimo, independentemente da configuração "exigir aprovação de convidado", descrita acima.

Você **sempre pode rejeitar** (desabilitar convidados anônimos) ou **sempre aceitar** usuários anônimos da seguinte maneira:

* Em **vs Code**, defina `liveshare.anonymousGuestApproval` em Settings. JSON (arquivo > Preferências > configurações) para `accept`, `reject`ou `prompt` (o padrão), conforme apropriado.

* No **Visual Studio**, defina ferramentas > opções > Live Share > "aprovação de convidado anônimo" para aceitar, rejeitar ou solicitar (o padrão), conforme apropriado.

 **Independentemente, lembre-se de que você só deve enviar Live Share links de convite para pessoas confiáveis.**

## <a name="controlling-file-access-and-visibility"></a>Controlando o acesso e a visibilidade do arquivo

Como convidado, o modelo remoto de Live Share fornece acesso rápido de leitura/gravação a arquivos e pastas que o host compartilhou com você sem precisar sincronizar todo o conteúdo de um projeto. Portanto, você pode navegar e editar arquivos de forma independente em toda a árvore de arquivos compartilhados. **No entanto, essa liberdade apresenta alguns riscos ao host.** Em conceito, um desenvolvedor poderia optar por ir e modificar o código-fonte sem seu conhecimento ou ver o código-fonte confidencial ou "segredos" localizados em algum lugar na árvore de arquivos compartilhados. Consequentemente, como um host, talvez você nem sempre queira que o convidado tenha acesso a todo o projeto que você está compartilhando. Felizmente, uma vantagem adicional desse modelo remoto é que você pode optar por "excluir" arquivos que não deseja compartilhar com ninguém sem sacrificar a funcionalidade. Seus convidados ainda podem participar de tarefas como depuração de sessões que normalmente exigirão acesso a esses arquivos se quisessem fazer isso por conta própria.

Você pode fazer isso adicionando um arquivo **. vsls. JSON** à pasta ou ao projeto que você está compartilhando. As configurações adicionadas a esse arquivo formatado em JSON alteram a maneira como o Live Share processa arquivos. Além de fornecer o controle direto, esses arquivos também podem ser confirmados no controle do código-fonte, de modo que qualquer pessoa que possa clonar um projeto poderá aproveitar essas regras sem nenhum esforço adicional de sua parte.

Aqui está um exemplo de arquivo. vsls. JSON:

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
> Você também pode fazer com que todos os arquivos/pastas compartilhem **somente leitura** ao iniciar uma sessão de colaboração. Consulte [abaixo](#read-only-mode) para obter detalhes.

Vamos examinar como essas propriedades mudam o que os convidados podem fazer.

### <a name="properties"></a>{1&gt;Propriedades&lt;1}

A propriedade **excludeFiles** permite que você especifique uma lista de padrões de arquivo glob (muito parecido com os encontrados arquivos. gitignore) que impede Live share de abrir determinados arquivos ou pastas para convidados. Lembre-se de que isso é inclusivo de cenários como um convidado _após ou saltando para o local de edição, passando para um arquivo durante a depuração colaborativa, quaisquer recursos de navegação de código como ir para a definição e muito mais._ Ele é destinado a arquivos que você nunca deseja compartilhar sob nenhuma circunstância, como aquelas que contêm segredos, certificados ou senhas. Por exemplo, como eles controlam a segurança, os arquivos. vsls. JSON são sempre excluídos.

A propriedade **hideFiles** é semelhante, mas não tão estrita. Esses arquivos são simplesmente ocultos da árvore de arquivos. Por exemplo, se você tiver ocorrido uma etapa em um desses arquivos durante a depuração, ele ainda estará aberto no editor. Essa propriedade será útil principalmente se você não tiver uma configuração de arquivo. gitignore (como seria o caso se você estiver usando um sistema de controle do código-fonte diferente) ou se simplesmente quiser aumentar o que já existe para evitar confusão ou confusão.

A configuração **gitignore** estabelece como Live share deve processar o conteúdo de arquivos. gitignore em pastas compartilhadas. Por padrão, quaisquer globs encontradas nos arquivos. gitignore são tratados como se fossem especificados na propriedade "hideFiles". No entanto, você pode escolher um comportamento diferente usando um dos seguintes valores:

| {1&gt;Opção&lt;1}    | Resultado                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | os conteúdos. gitignore são visíveis para convidados na árvore de arquivos (supondo que eles não são filtrados por uma configuração de editor convidado). |
| `hide`    | **O padrão.** Globs dentro de. gitignore são processados como se estivessem na propriedade "hideFiles".                   |
| `exclude` | Globs dentro de. gitignore são processados como se estivessem na propriedade "excludeFiles".                                 |

Uma desvantagem da configuração de `exclude` é que o conteúdo de pastas como node_modules geralmente está em. gitignore, mas pode ser útil para entrar durante a depuração. Consequentemente, Live Share dá suporte à capacidade de reverter uma regra usando "!" na propriedade excludeFiles. Por exemplo, esse arquivo. vsls. JSON excluiria tudo em ". gitignore", exceto por node_modules:

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

As regras ocultar e excluir são processadas separadamente, portanto, se você ainda quisesse ocultar node_modules para reduzir a aglomeração sem realmente excluí-la, poderá simplesmente editar o arquivo da seguinte maneira:

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

### <a name="vslsjson-files-in-sub-folders"></a>arquivos. vsls. JSON em subpastas

Por fim, assim como. gitignore, os arquivos. vsls. JSON podem ser colocados em subpastas. As regras de ocultar/excluir são determinadas começando com o arquivo. vsls. JSON na pasta raiz que você compartilhou (se houver) e, em seguida, percorrendo em cada subpasta de lá, levando a um determinado arquivo para procurar arquivos. vsls. JSON a serem processados. O conteúdo de arquivos. vsls. JSON em pastas mais distante da árvore de arquivos e, em seguida, as regras de complemento (ou substituição) estabelecidas em níveis mais altos.

### <a name="disabling-external-file-sharing"></a>Desabilitando o compartilhamento de arquivos externos

Por padrão, Live Share também compartilhará todos os arquivos que o host abrir, que são externos à pasta/solução compartilhada. Isso facilita a abertura rápida de outros arquivos relacionados sem a necessidade de um novo compartilhamento.

Se você preferir desabilitar esse recurso:

* Em **vs Code**, adicione o seguinte a Settings. JSON:

    ```json
    "liveshare.shareExternalFiles": false
    ```

* No **Visual Studio**, defina ferramentas &gt; opções &gt; Live share &gt; "compartilhar arquivos externos" como falso

## <a name="read-only-mode"></a>Modo somente leitura

Às vezes, quando você compartilha seu código como um host, não quer que seus convidados façam edições. Talvez você precise de seu convidado para dar uma olhada em algum código, ou você está mostrando seu projeto para um grande número de convidados e não deseja que sejam feitas edições desnecessárias ou acidentais. O Live Share oferece a capacidade de compartilhar projetos no modo somente leitura.

Como um host, ao compartilhar, você tem a opção de habilitar o modo somente leitura para uma sessão de colaboração. Quando um convidado se une, ele não poderá fazer edições no código, embora você ainda possa ver os cursores e os destaques uns dos outros, bem como navegar pelo projeto.

Você ainda pode codepurar com convidados enquanto estiver no modo somente leitura. Os convidados não terão a capacidade de percorrer o processo de depuração, mas ainda poderão adicionar ou remover pontos de interrupção e inspecionar variáveis. Além disso, você ainda pode compartilhar servidores e terminais (somente leitura) com convidados.

Você pode saber mais sobre como iniciar uma sessão de colaboração somente leitura: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [![vs](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>Codepuração

Quando você está lidando com problemas de codificação difíceis ou bugs, ter um par extra de olhos quando a depuração pode ser realmente útil. Visual Studio Live Share habilita a "depuração colaborativa" ou a "codepuração" compartilhando a sessão de depuração com todos os convidados sempre que o host inicia a depuração.

Como um host, você tem controle total sobre quando uma sessão de depuração é iniciada ou interrompida, mas a codepuração apresenta alguns riscos se você estiver compartilhando com alguém que não confia. Live Share permite que os convidados que você convidar executem comandos do console/REPL e, portanto, haja **um risco de um ator mal-intencionado executar um comando que você não deseja que eles executem**.

Consequentemente, você deve **apenas codepurar com aqueles confiáveis.**

Saiba mais: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [![vs](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>Compartilhando um servidor local

Durante a codepuração, pode ser muito útil obter acesso a diferentes partes do aplicativo que está sendo fornecido pelo host para a sessão de depuração. Talvez você queira acessar o aplicativo em um navegador, acessar um banco de dados local ou obter um ponto de extremidade REST de suas ferramentas. Live Share permite que você "Compartilhe um servidor" que mapeia uma porta local na máquina do host para a mesma porta exata no computador do convidado. Como convidado, você pode interagir com o aplicativo exatamente como se ele estivesse sendo executado localmente em seu computador (por exemplo, o host e o convidado podem acessar um aplicativo Web em execução no http://localhost:3000).

No entanto, como um host, você deve **ser muito seletivo com as portas que você compartilha** com convidados e só compartilhar portas de aplicativo em vez de portas do sistema. Para convidados, as portas compartilhadas se comportarão exatamente como fariam se o servidor/serviço estivesse em execução em seu próprio computador. Isso é muito útil, mas se a porta errada for compartilhada, isso também poderá ser um risco. Por esse motivo, Live Share não faz suposições sobre o que deve ou não ser compartilhado sem uma definição de configuração e o host que executa uma ação.

No Visual Studio, a **porta do aplicativo Web** especificada em projetos ASP.net é **automaticamente compartilhada durante a depuração apenas** para facilitar o acesso de convidado ao aplicativo Web durante a execução. No entanto, você pode desativar essa automação definindo ferramentas > Opções > Live Share > "compartilhar aplicativo Web em depuração" como "falso", se preferir.

No Visual Studio Code, Live Share tenta **detectar as portas de aplicativo adequadas** e compartilhá-las. No entanto, você pode desabilitar isso adicionando o seguinte a Settings. JSON:

        liveshare.autoShareServers: false

Em ambos os casos, tome cuidado ao compartilhar portas adicionais.

Você pode saber mais sobre como configurar o recurso aqui: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [![vs](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>Compartilhando um terminal

O desenvolvimento moderno faz uso frequente de uma ampla gama de ferramentas de linha de comando. Felizmente, o Live Share permite que você, como host, opcionalmente, "compartilhe um terminal" com os convidados. O terminal compartilhado pode ser somente leitura ou totalmente colaborativo, de modo que você e os convidados possam executar comandos e ver os resultados. Como o host, você pode permitir que outros colaboradores vejam apenas a saída ou que usem qualquer número de ferramentas de linha de comando para executar testes, compilações ou até mesmo triagem de problemas específicos do ambiente.

Somente os hosts podem iniciar terminais compartilhados para impedir que os convidados iniciem um e fazer algo que você não está esperando ou assistindo. Ao iniciar um terminal compartilhado como um host, você pode especificar se ele deve ser somente leitura ou de leitura/gravação. Quando o terminal for leitura/gravação, todos poderão digitar no terminal, incluindo o host, o que facilita a intervenção caso um convidado faça algo indesejável. No entanto, para que seja seguro, você deve **dar somente acesso de leitura/gravação aos convidados quando tiver ciência de que eles realmente precisam** e continuar com os terminais somente leitura para cenários em que deseja que o convidado veja apenas a saída dos comandos que você executa.

No Visual Studio, os terminais não são compartilhados por padrão. No VS Code, os terminais são automaticamente compartilhados **somente leitura** por padrão. No entanto, você pode desabilitar isso adicionando o seguinte a Settings. JSON:

```json
"liveshare.autoShareTerminals": false
```

Saiba mais: [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [![vs](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>Consentimento do administrador do AAD

Ao entrar usando um **endereço de email corporativo ou de estudante** com suporte da Microsoft, você poderá ver uma mensagem dizendo **"precisar de aprovação do administrador"** ao entrar. Isso ocorre porque Live Share requer acesso de leitura às informações do usuário para seus recursos de segurança e seu locatário do Azure AD é configurado para exigir "consentimento do administrador" para novos aplicativos que acessam o conteúdo do diretório.

O administrador do AD precisaria resolver isso para você usando as seguintes informações:

* **Nome do aplicativo**: Visual Studio Live share (pessoas)
* **Tipo de aplicativo**: aplicativo Web
* **Status de aplicativos**: produção
* **Permissões delegadas**: user. Read
* **URL do aplicativo**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **URL de Resposta**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Isso só precisaria ser feito uma vez para qualquer pessoa que estivesse usando Live Share. Consulte [aqui](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) e [aqui](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) para obter detalhes.

## <a name="see-also"></a>Consulte também

* [Como colaborar usando o Visual Studio Code](../use/vscode.md)
* [Como colaborar usando o Visual Studio](../use/vs.md)
* [Requisitos de conectividade do Live Share](connectivity.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
