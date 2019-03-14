---
title: Detalhes da instalação Linux - Visual Studio Live Share | Microsoft Docs
description: Informações detalhadas sobre como instalar o Visual Studio Live Share no Linux.
ms.custom: ''
ms.date: 10/6/2018
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
ms.openlocfilehash: 013eb234e5acca02a39e90f0697a146039bb2a89
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255218"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Detalhes de instalação do Linux

Linux é um ambiente altamente variável e com o enorme número de distribuições e ambientes de desktop pode ser complicado para começar a trabalhar. Se você continuar com as versões com suporte do **área de trabalho do Ubuntu** (16.04 +), **CentOS 7**, ou **estação de trabalho do Fedora** (27 +) e usar apenas **distribuições oficiais do VS Código**, você deve encontrar o processo muito simples. No entanto, se você estiver usando uma configuração não padrão ou a distribuição de downstream, você pode ou não podem ser executadas em algumas dificuldades. Este documento fornece algumas informações sobre requisitos e alguns detalhes de solução de problemas que podem ajudá-lo a começar a trabalhar e suporte para a execução, mesmo se você configuração é somente comunidade. Observe que o Live Share só dá suporte a **Linux de 64 bits**.

## <a name="install-linux-prerequisites"></a>Instale os pré-requisitos do Linux

Algumas distribuições do Linux não têm bibliotecas que Live Share precisa para funcionar. Por padrão, Live Share tenta detectar e instalar os pré-requisitos do Linux para você. Você verá uma notificação quando o Live Share encontra um problema que pode ser originado de bibliotecas ausentes solicitando sua permissão para instalá-los.

![Mostrando mensagem de notificação de notificação do sistema que pré-requisitos do Linux estão ausentes](../media/vscode-linux-prereq-missing.png)

Quando você clica em "Instalar", aparecerá uma janela de terminal em que o seu sistema operacional solicitará que você insira seu administrador / raiz (sudo) senha para continuar. Supondo que o script for concluído com êxito, recarregue o Visual Studio Code, quando solicitado, você deve ser tudo pronto! Talvez você queira fazer check-out **[dicas de distribuição](#tips-by-distribution)** para outras dicas e soluções alternativas, se existir alguma.

Se você vir uma mensagem indicando que o script não dá suporte a sua distribuição, consulte **[dicas para distribuições de suporte da comunidade](#tips-for-unsupported-distros)** para obter informações a comunidade tiver compartilhado conosco.

Se você **prefere não ter o VS Code, execute o comando para você**, você também pode para executar novamente a versão mais recente deste script a qualquer momento manualmente usando o seguinte comando em uma janela de Terminal:

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>Dicas de distribuição

Ao instalar o pré-requisito script acima cobre uma variedade de distribuições, você deve estar imaginando o que está faltando normalmente de baunilha instalações. A lista a seguir mostra as bibliotecas principais que estavam ausentes em uma instalação nova de uma determinada distribuição. A lista também fornece algumas dicas que podem ajudar você a entrar em funcionamento, se você encontrar um problema.

| Distribuição | Baunilha instalar bibliotecas ausentes | Etapas adicionais |
|--------|-------------------|----|
| Área de trabalho do Ubuntu 18.04 (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Área de trabalho do Ubuntu 16.04 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18.04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16.04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18.04 (64 bits) |&lt;none&gt;  | <ul><li>Certifique-se "Iniciar serviços GNOME na inicialização" está marcado na guia "Avançado" de "Sessão e inicialização".</li><li>Se você enfrentar problemas ao entrar, instale `seahorse`, iniciar "Senhas e chaves", verifique se você tiver o token de autenticação de "Logon" e que você pode desbloqueá-la.</li></ul> |
| Xubuntu 16.04 (64 bits) | &lt;none&gt; | <ul><li>Certifique-se "Iniciar serviços GNOME na inicialização" está marcado na guia "Avançado" de "Sessão e inicialização".</li><li>Se você enfrentar problemas ao entrar, instale `seahorse`, iniciar "Senhas e chaves", verifique se você tiver o token de autenticação de "Logon" e que você pode desbloqueá-la.</li></ul> |
| Menta canela 19 (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Mint 18,3 canela (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Debian 10 (Buster) teste (64 bits) | Versão não é estável, portanto, desconhecido. | <ul><li>Debian teste e instável (Sid) não são suportadas oficialmente.</li><li>Há um [problema conhecido](https://github.com/dotnet/corefx/issues/33179) no .NET Core que afeta o Live Share. </li><li>Ver [aqui para uma solução alternativa](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249).</li></ul> |
| Debian 9 GNOME Desktop (64 bits) | &lt;none&gt; | <ul><li>Talvez você precise instalar `sudo` e adicione o usuário ao grupo sudo para usar o script de instalação automatizada.</li>  |
| Estação de trabalho do Fedora (64 bits) de 29 | `openssl-compat10` | &lt;none&gt; |
| Estação de trabalho do Fedora 28 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Estação de trabalho do Fedora 27 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| CentOS 7 GNOME Desktop (64 bits) | &lt;none&gt; | &lt;none&gt; |

Ver **[dicas para distribuições de suporte da comunidade](#tips-for-community-supported-distros)** para obter informações sobre outro não Debian / Ubuntu ou RHL com distribuições de base.

Detalhes adicionais também podem ser encontradas [abaixo](#detailed-library-requirements) sobre as bibliotecas específicas Live Share precisa.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>Dicas para distribuições de suporte da comunidade

Distribuições de fora a Debian / Ubuntu ou RHL árvores não são suportadas oficialmente pelo Visual Studio Code ou o .NET Core. Portanto, por extensão, eles não são oficialmente suportados pelo Visual Studio Live Share tanto. No entanto, a comunidade contribuiu com algumas informações úteis sobre o Live Share em funcionamento em um número de distribuições adicionais.

> **Bem-vindo de solicitações de pull:** Se você estiver interessado em atualizar essas informações com sua distribuição favorita, envie uma PR para [esse arquivo](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) em nosso repositório GitHub do docs. Melhor ainda, se você quisesse obter o instalador de dependência que dão suporte a sua distribuição Favoritos, você pode enviar uma solicitação pull [para este arquivo](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh).

| Distribuição | Trabalhando? | Baunilha instalar bibliotecas ausentes | Etapas adicionais |
|--------------|----------|-------------------|------------------|
| Arch Linux (64 bits) | Sim | Varia de acordo. Bibliotecas de possíveis: `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>Compatível com o [script de instalação de pré-requisito](#install-linux-prerequisites).</li><li>Use o [visual studio-código bin](https://aur.archlinux.org/packages/visual-studio-code-bin) pacote AUR para VS Code.</li><li>`sudo` precisa ser instalado para usar o pré-requisito automatizado instalará script.</li><li>`gnome-keyring` pode exigir adicionais [etapas de instalação](https://wiki.archlinux.org/index.php/GNOME/Keyring) em alguns ambientes de área de trabalho.</ul> |
| Manjaro 17.1 (64 bits) | Sim | `xorg-xprop liburcu` | <ul><li>Compatível com o [script de instalação de pré-requisito](#install-linux-prerequisites).</li><li>Use o [visual studio-código bin](https://aur.archlinux.org/packages/visual-studio-code-bin) pacote AUR para VS Code.</li></ul> |
| openSuSE LEAP KDE 15 (64 bits) | Sim | `libopenssl1_0_0 gnome-keyring` | <ul><li>Suporte para o script de instalação de pré-requisito.</li></ul> |
| Solus 3 (64 bits) | Sim | `xprop` | <ul><li>Compatível com o [script de instalação de pré-requisito](#install-linux-prerequisites).</li><li>Versões dos `vscode` pacote antes do lançamento 57 estavam ausentes necessárias product.json valores ([veja abaixo](#vs-code-oss-issues)). Atualizar o `vscode` pacote para resolver esse problema.</li></ul> |
| Gentoo (64 bits) | Sim | Altamente variável. Pacotes ausentes possíveis: `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>O `visual-studio-code` de pacote em de **jorgicio** sobreposição é conhecida por funcionar.</li></ul>

## <a name="install-prerequisites-manually"></a>Instalar os pré-requisitos manualmente

 Embora seja recomendável usar o Live Share **script de instalação de dependência**, esta seção fornece mais detalhes sobre os requisitos de biblioteca no caso de você deseja executar essas etapas por conta própria ou estiver usando uma distribuição que não oferece suporte para o script.

Bibliotecas ausentes típicas em instalações de baunilha podem ser encontradas no [dicas de distribuição](#tips-by-distribution) e [dicas para distribuições de suporte da comunidade](#tips-for-unsupported-distros) seções.

### <a name="detailed-library-requirements"></a>Requisitos da biblioteca detalhadas

Requisitos da Visual Studio Live Share biblioteca nativa provenientes de seu uso do .NET Core 2.1, libsecret para persistir as credenciais e sua integração de navegador. A tabela a seguir resume esses requisitos para distribuições oficialmente com suporte pelo .NET Core.

| Distribuição | Solicitações do .NET core | Solicitações de armazenamento de credencial| Solicitações de integração de navegador |
|--------------|-----------|--------------------|------------|
| Distribuições de downstream e Ubuntu | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (para o Ubuntu 16.04, forjar 18,3) ou `libicu57` (para o Ubuntu 17.10) ou `libicu60` (para o Ubuntu 18.04, forjar 19) | `libsecret-1-0 gnome-keyring` (ou token de autenticação com suporte do libsecret - Kwallet não oferece suporte a libsecret) | `desktop-file-utils x11-utils` |
| Debian 9 e downstream de distribuições | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (ou token de autenticação com suporte do libsecret - Kwallet não oferece suporte a libsecret) | `desktop-file-utils x11-utils` |
| RHL / CentOS/ Fedora | `openssl-libs krb5-libs zlib libicu` Fedora também exige `compat-openssl10`| `libsecret gnome-keyring` (ou token de autenticação com suporte do libsecret - Kwallet não oferece suporte a libsecret) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (ou token de autenticação com suporte do libsecret - Kwallet não oferece suporte a libsecret) | `desktop-file-utils xprop`

Enquanto outras distribuições exigem as mesmas bibliotecas, seus nomes de pacote podem variar. Você pode encontrar alguns da [dicas para distribuições de suporte da comunidade](#tips-for-unsupported-distros) seção.

### <a name="debian--ubuntu"></a>Debian / Ubuntu

Bibliotecas podem ser instaladas em distribuições com base em Debian/Ubuntu executando `sudo apt install <library-name>` em um terminal.

Para distribuições do Ubuntu com base em incluindo Mint, execute:

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Para Debian 9 e distribuições de downstream não Ubuntu, execute:

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora / CentOS / RHL

Bibliotecas podem ser instaladas em distribuições Fedora/CentOS/RHL com base em executando `sudo yum install <library-name>` em um terminal. Por exemplo, isso irá instalar tudo:

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>Problemas de sistemas operacionais de código do VS

> **Usuários de Linux/Manjaro arcos:** Use o [visual-studio-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) pacote AUR para evitar esse problema.

Pacotes do Visual Studio Code qualquer baunilha ou modificadas versões dos sistemas operacionais de código do VS podem estar faltando um valor crítico no `product.json` que impede que o Visual Studio Live Share ativando o arquivo.

Uma maneira rápida para ver o que pode ser atingido por esse problema é a Ajuda de ir para > "Ativar/desativar Developer Tools" e veja se você encontrar um rastreamento de pilha que indica a extensão de compartilhamento ao vivo não ativou porque estava usando uma "API proposta".

Para verificar se esse é o problema, verifique o conteúdo do `product.json`. O local do arquivo varia de acordo com o pacote, mas é geralmente em um dos seguintes locais:

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

Se o `extensionAllowedProposedApi` propriedade está ausente ou você não vir "ms-vsliveshare.vsliveshare" referenciados, você estiver usando uma versão de sistemas operacionais com esse problema.

Como uma **solução alternativa**, você pode adicionar o seguinte para o product.json:

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

Ver [acima](#tips-for-community-supported-distros) para obter detalhes adicionais sobre se a distribuição que você está usando é conhecida por funcionar.

## <a name="linux-browser-integration"></a>Integração de navegador do Linux

Live do Visual Studio normalmente compartilham **não exige etapas adicionais de instalação** para habilitar a integração de navegador no Linux.

Para fazer isso, o Live Share coloca automaticamente um arquivo da área de trabalho no `~/.local/share/applications` e o próprio iniciador necessário em `~/.local/share/vsliveshare` quando primeiro inicializa a extensão. Nenhuma ação é necessária de sua parte, se isso for bem-sucedido.

Em alguns casos, distribuições não dar suporte a esse local ou exigir ajustes para fazê-lo funcionar com suas instalações de baunilha. Nesses casos, Live Share voltará a usar `/usr/local/share` em vez disso. Como resultado, **poderá ser notificado de que sua senha de administrador (sudo) é necessária** para concluir o processo de instalação. Uma janela do terminal será exibida informando a você onde o iniciador do navegador será instalado. Basta digitar a senha quando solicitado e pressione enter após a conclusão da instalação para fechar a janela do terminal.

Se você preferir executar o comando por conta própria em vez disso, você pode clicar em "Copiar em vez disso," que irá copiar o comando de terminal na área de transferência em vez disso.

Por fim, se você optar por ignorar esta etapa inteiramente, você ainda poderá [sessões de colaboração de junção manualmente](../use/vscode.md#join-manually), mas você não poderá ingressar abrindo um link de convite no navegador. Observe que você pode sempre acessar o comando novamente mais tarde, atingindo **Ctrl + Shift + P / Cmd + Shift + P** e selecionando o "compartilhamento ao vivo: Comando de instalação do iniciador".

## <a name="see-also"></a>Consulte também

- [Como: Colaborar usando o Visual Studio Code](../use/vscode.md)
- [Requisitos de conectividade do Live Share](connectivity.md)
- [Funcionalidades de segurança do Live Share](security.md)

Está tendo problemas? Confira [Solução de problemas](../troubleshooting.md) ou [envie comentários](../support.md).
