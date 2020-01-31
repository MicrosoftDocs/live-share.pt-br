---
title: Detalhes da instalação do Linux-Visual Studio Live Share | Microsoft Docs
description: Informações detalhadas sobre como instalar o Visual Studio Live Share no Linux.
ms.custom: ''
ms.date: 10/6/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 69bc178ebb4052757f984d67482d216335f46dac
ms.sourcegitcommit: 5180aab73c086cbded6aae01aa01f71fb991dee1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818070"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Detalhes de Instalação do Linux

Linux é um ambiente altamente variável e, com o grande número de ambientes de desktop e distribuições, pode ser complicado trabalhar. Se você tiver as versões com suporte do **Ubuntu Desktop** (16.04 +), **CentOS 7**ou **Fedora Workstation** (27 +) e usar somente as **distribuições oficiais do vs Code**, você deverá encontrar o processo diretamente em frente. No entanto, se estiver usando uma configuração não padrão ou distribuição downstream, pode ser que você passe por alguns contratempos. Este documento fornece algumas informações sobre os requisitos e alguns detalhes de solução de problemas que podem ajudá-lo a entrar em funcionamento mesmo que sua configuração seja apenas compatível com a Comunidade. Observe que Live Share só dá suporte ao **Linux de 64 bits**.

## <a name="install-linux-prerequisites"></a>Instalar pré-requisitos do Linux

Algumas distribuições do Linux têm bibliotecas que o Live Share precisa para funcionar. Por padrão, o Live Share tenta detectar e instalar os pré-requisitos do Linux para você. Uma notificação será exibida quando o Live Share encontrar um problema que tenha sido originado pela ausência das bibliotecas, solicitando a você permissão para instalá-las.

![Notificação do sistema mostrando a mensagem de que os pré-requisitos do Linux estão ausentes](../media/vscode-linux-prereq-missing.png)

Quando você clicar em "instalar", uma janela do terminal será exibida onde seu sistema operacional solicitará que você insira sua senha de administrador/raiz (sudo) para continuar. Supondo que o script seja concluído com êxito, recarregue Visual Studio Code quando solicitado que você esteja tudo definido! Talvez você também queira conferir as **[dicas por distribuição](#tips-by-distribution)** para ver outras dicas e soluções alternativas, caso haja alguma.

Caso seja exibida uma mensagem indicando que o script não dá suporte à sua distribuição, confira **[dicas para distribuição suportada pela comunidade](#tips-for-unsupported-distros)** para obter informações compartilhadas conosco pela comunidade.

Se **preferir não ter vs Code executar o comando para você**, você também poderá optar por executar novamente a versão mais recente desse script a qualquer momento, usando o seguinte comando em uma janela de terminal:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>Dicas por distribuição

Embora o script de instalação de pré-requisito acima cubra uma variedade de distribuições, você pode estar se perguntando o que normalmente está faltando nas instalações da baunilha. A lista a seguir mostra as principais bibliotecas que estavam ausentes em uma instalação nova de uma determinada distribuição. A lista também fornece algumas dicas que podem ajudá-lo a entrar em funcionamento se você clicar em um problema.

| Ponto de | Bibliotecas ausentes da instalação da baunilha | Etapas adicionais |
|--------|-------------------|----|
| Ubuntu Desktop 18, 4 (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu Desktop 16, 4 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18, 4 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16, 4 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18, 4 (64 bits) |&lt;none&gt;  | <ul><li>Verifique se "Iniciar serviços GNOME na inicialização" está marcado na guia "avançado" de "sessão e inicialização".</li><li>Se você tiver problemas de entrada, instale `seahorse`, inicie "senhas e chaves", verifique se você tem o anel de acesso de "logon" e se pode desbloqueá-lo.</li></ul> |
| Xubuntu 16, 4 (64 bits) | &lt;none&gt; | <ul><li>Verifique se "Iniciar serviços GNOME na inicialização" está marcado na guia "avançado" de "sessão e inicialização".</li><li>Se você tiver problemas de entrada, instale `seahorse`, inicie "senhas e chaves", verifique se você tem o anel de acesso de "logon" e se pode desbloqueá-lo.</li></ul> |
| Menta 19 Cinnamon (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Menta 18,3 Cinnamon (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Teste do Debian 10 (Buster) (64 bits) | Versão não estável, portanto desconhecida. | <ul><li>Não há suporte oficialmente para teste de Debian e instável (SID).</li><li>Há um [problema conhecido](https://github.com/dotnet/corefx/issues/33179) no .NET Core que afeta Live share. </li><li>Consulte [aqui para obter uma solução alternativa](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249).</li></ul> |
| Desktop de GNOME do Debian 9 (64 bits) | &lt;none&gt; | <ul><li>Talvez seja necessário instalar `sudo` e adicionar o usuário ao grupo sudo para usar o script de instalação automatizada.</li>  |
| Fedora Workstation 29 (64 bits) | `openssl-compat10` | &lt;none&gt; |
| Estação de trabalho Fedora 28 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Estação de trabalho Fedora 27 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Área de trabalho de GNOME do CentOS 7 (64 bits) | &lt;none&gt; | &lt;none&gt; |

Confira as **[dicas para distribuições com suporte da Comunidade](#tips-for-community-supported-distros)** para obter informações sobre outras distribuições baseadas no não Debian/Ubuntu ou RHL.

Detalhes adicionais também podem ser encontrados [abaixo](#detailed-library-requirements) sobre as bibliotecas específicas Live share necessidades.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>Dicas para distribuições com suporte da Comunidade

As distribuições fora das árvores Debian/Ubuntu ou RHL não são oficialmente suportadas pelo Visual Studio Code ou pelo .NET Core. Portanto, por extensão, eles não têm suporte oficialmente pelo Visual Studio Live Share. No entanto, a Comunidade contribuiu com algumas informações úteis sobre como colocar Live Share em funcionamento em várias distribuições adicionais.

> **PRS bem-vindo:** Se você estiver interessado em atualizar essas informações com sua distribuição favorita, envie uma PR para [esse arquivo](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) em nosso repositório GitHub de documentos. Melhor ainda, se você quiser obter o instalador de dependências que oferece suporte à sua distribuição favorita, você pode enviar uma PR [para esse arquivo](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh).

| Ponto de | Trabalhando? | Bibliotecas ausentes da instalação da baunilha | Etapas adicionais |
|--------------|----------|-------------------|------------------|
| Arch Linux (64 bits) | Sim | Consoante. Bibliotecas possíveis: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>Com suporte do [script de instalação de pré-requisito](#install-linux-prerequisites).</li><li>Use o pacote Aur do [Visual-Studio-Code-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) para vs Code.</li><li>`sudo` precisará ser instalado para usar o script de instalação de pré-requisito automatizado.</li><li>`gnome-keyring` pode exigir [etapas de configuração](https://wiki.archlinux.org/index.php/GNOME/Keyring) adicionais em alguns ambientes de área de trabalho.</ul> |
| Manjaro 17,1 (64 bits) | Sim | `xorg-xprop liburcu` | <ul><li>Com suporte do [script de instalação de pré-requisito](#install-linux-prerequisites).</li><li>Use o pacote Aur do [Visual-Studio-Code-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) para vs Code.</li></ul> |
| openSuSE LEAP 15 KDE (64 bits) | Sim | `libopenssl1_0_0 gnome-keyring` | <ul><li>Com suporte do script de instalação de pré-requisito.</li></ul> |
| Solus 3 (64 bits) | Sim | `xprop` | <ul><li>Com suporte do [script de instalação de pré-requisito](#install-linux-prerequisites).</li><li>As versões do pacote de `vscode` antes da versão 57 não tinham valores Product. JSON necessários ([Veja abaixo](#vs-code-oss-issues)). Atualize o pacote de `vscode` para resolver esse problema.</li></ul> |
| Gentoo (64 bits) | Sim | Altamente variável. Possíveis pacotes ausentes: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>O pacote de `visual-studio-code` na sobreposição de **jorgicio** é conhecido por funcionar.</li></ul>

## <a name="install-prerequisites-manually"></a>Instalar pré-requisitos manualmente

 Embora seja recomendável usar o **script de instalação de dependência**do Live share, esta seção fornece mais detalhes sobre os requisitos de biblioteca no evento que você deseja executar essas etapas ou usar uma distribuição sem suporte pelo script.

Bibliotecas típicas ausentes em instalações de baunilha podem ser encontradas nas seções [dicas por distribuição](#tips-by-distribution) e [dicas para distribuições com suporte da Comunidade](#tips-for-unsupported-distros) .

### <a name="detailed-library-requirements"></a>Requisitos de biblioteca detalhados

Os requisitos da biblioteca nativa do Visual Studio Live Share vêm de seu uso do .NET Core 2,1, libsecret para manter as credenciais e sua integração com o navegador. A tabela a seguir resume esses requisitos para distribuições oficialmente suportadas pelo .NET Core.

| Ponto de | Requisitos do .NET Core | Requisitos de armazenamento de credenciais| Requisitos de integração de navegador |
|--------------|-----------|--------------------|------------|
| Distribuições do Ubuntu e downstream | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (para Ubuntu 16, 4, menta 18,3) ou `libicu57` (para Ubuntu 17,10) ou `libicu60` (para Ubuntu 18, 4, menta 19) | `libsecret-1-0 gnome-keyring` (ou libsecret com suporte para keyring-KWallet não dá suporte a libsecret) | `desktop-file-utils x11-utils` |
| Distribuições do Debian 9 e downstream | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (ou libsecret com suporte para keyring-KWallet não dá suporte a libsecret) | `desktop-file-utils x11-utils` |
| RHL/CentOS/Fedora | `openssl-libs krb5-libs zlib libicu` Fedora também requer `compat-openssl10`| `libsecret gnome-keyring` (ou libsecret com suporte para keyring-KWallet não dá suporte a libsecret) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (ou libsecret com suporte para keyring-KWallet não dá suporte a libsecret) | `desktop-file-utils xprop`

Enquanto outras distribuições exigem as mesmas bibliotecas, seus nomes de pacote podem variar. Você pode encontrar alguns deles na seção [dicas para distribuições com suporte da Comunidade](#tips-for-unsupported-distros) .

### <a name="debian--ubuntu"></a>Debian/Ubuntu

As bibliotecas podem ser instaladas em distribuições baseadas em Debian/Ubuntu executando `sudo apt install <library-name>` em um terminal.

Para distribuições baseadas no Ubuntu, incluindo menta, execute:

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Para distribuições downstream do Debian 9 e não do Ubuntu, execute:

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora / CentOS / RHL

As bibliotecas podem ser instaladas em distribuições baseadas em Fedora/CentOS/RHL executando `sudo yum install <library-name>` em um terminal. Por exemplo, isso instalará tudo:

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>Problemas de VS Code OSS

> **Usuários do Manjaro/Linux Arch:** Use o pacote do [Visual-Studio-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) Aur para evitar esse problema.

Pacotes de Visual Studio Code que são versões baunilha ou modificadas do VS Code OSS podem ter um valor crítico ausente no arquivo `product.json` que impede que o Visual Studio Live Share seja ativado.

Uma maneira rápida de ver que você pode estar atingindo esse problema é acessar a ajuda > "alternar Ferramentas para Desenvolvedores" e ver se você encontra um rastreamento de pilha indicando que a extensão Live Share não foi ativada porque estava usando uma "API proposta".

Para verificar se esse é o seu problema, verifique o conteúdo de `product.json`. O local do arquivo varia de acordo com o pacote, mas geralmente está em um dos seguintes locais:

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

Se a propriedade `extensionAllowedProposedApi` estiver ausente ou se você não vir "MS-vsliveshare. vsliveshare" referenciado, você está usando uma versão do OSS com esse problema.

Como **alternativa**, você pode adicionar o seguinte ao Product. JSON:

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

Veja [acima](#tips-for-community-supported-distros) para obter detalhes adicionais sobre se a distribuição que você está usando é conhecida como trabalho.

## <a name="linux-browser-integration"></a>Integração do navegador do Linux

Geralmente, o Visual Studio Live Share **não exige etapas de instalação adicionais** para permitir a integração do navegador no Linux.

Para fazer isso, Live Share coloca automaticamente um arquivo de área de trabalho em `~/.local/share/applications` e o iniciador necessário em `~/.local/share/vsliveshare` quando a extensão é inicializada pela primeira vez. Nenhuma ação será necessária em sua parte se isso tiver sucesso.

Em alguns casos, as distribuições não dão suporte a esse local ou exigem ajustes para que funcionem com suas instalações de baunilha. Nesses casos, Live Share voltar a usar `/usr/local/share` em vez disso. Como resultado, **você pode ser notificado de que sua senha de administrador (sudo) é necessária** para concluir o processo de instalação. Uma janela do terminal será exibida informando a você onde o inicializador do navegador será instalado. Basta digitar a senha quando solicitado e pressionar enter assim que a instalação for concluída para fechar janela do terminal.

Se preferir executar o comando por conta própria, clique em "copiar", que copiará o comando de terminal para a área de transferência em vez disso.

Por fim, se você optar por ignorar essa etapa por completo, ainda poderá [unir as sessões de colaboração manualmente](../use/vscode.md#join-manually), mas não poderá ingressar abrindo um link de convite no navegador. Observe que você sempre pode acessar o comando mais tarde, pressionando **Ctrl + Shift + P/Cmd + Shift + P** e selecionando o comando "Live share: setup do Launcher".

## <a name="see-also"></a>Veja também

- [Como colaborar usando o Visual Studio Code](../use/vscode.md)
- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
