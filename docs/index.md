---
title: Visão geral | Microsoft Docs
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
ms.openlocfilehash: 3ae7ba22225ce537c28daca0a9036872f227a8ce
ms.sourcegitcommit: 9deed590c0876b732c8eb150a9a23498a8243efc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/27/2021
ms.locfileid: "98870585"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>O que é o Visual Studio Live Share?

Bem-vindo ao Visual Studio Live Share! O Live Share permite que você edite e depure em colaboração com outras pessoas em tempo real, sejam quais forem as linguagens de programação usadas ou os tipos de aplicativo criados. É possível compartilhar o projeto atual instantaneamente e com segurança, iniciar uma sessão de depuração conjunta, compartilhar instâncias de terminal, encaminhar aplicativos Web do localhost, realizar chamadas de voz e muito mais!

 Ao contrário da programação em par tradicional, o Visual Studio Live Share permite que os desenvolvedores trabalhem em conjunto, mantendo suas preferências pessoais de editor (por exemplo, tema, associações de teclas), além de terem seu próprio cursor. Isso permite que você faça uma transição tranquila entre a capacidade de seguir uns aos outros e de explorar ideias/tarefas por conta própria. Essa capacidade de trabalhar em conjunto e de modo independente fornece uma experiência de colaboração que se parece muito com a colaboração _presencial_.

Pronto para começar? Neste artigo, explicaremos alguns conceitos e como instalar as extensões necessárias. Caso esteja procurando uma versão resumida, confira os Inícios Rápidos [Compartilhar](quickstart/share.md) e [Ingressar](quickstart/join.md).

> [!TIP]
> Você sabia que agora é possível *ingressar em uma sessão de Live share do navegador*? Isso significa que você não precisa mais instalar um cliente de desktop para colaborar! Basta clicar no link compartilhado com você e você poderá obter uma experiência de editor de VS Code de fidelidade total no navegador. Saiba mais [aqui](quickstart/browser-join.md)

## <a name="install-visual-studio-live-share"></a>Instalar o Visual Studio Live Share

Antes de começar, você precisa confirmar se tem uma versão do Visual Studio ou do Visual Studio Code instalada que atenda aos requisitos principais do Live Share.

- **Visual Studio Code 1.22.0 ou posterior** – Windows 7, 8.1 ou 10, macOS *(somente High Sierra 10.13 ou posterior)* e Linux de 64 bits *(Ubuntu Desktop de 64 bits 16.04 ou posterior, Fedora 27 ou posterior, recomendado – [ver detalhes](use/vscode.md#installation))*.
- **Visual Studio 2019** (qualquer edição) – Windows 7, 8.1 ou 10.
- **Visual Studio 2017 15.6 ou posterior** (qualquer edição) – Windows 7, 8.1 ou 10.

Depois disso, o download e a instalação da extensão do Visual Studio Live Share são muito simples:

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0 ou posterior)</strong><br />
        1.Instale o <a href="https://code.visualstudio.com/">Visual Studio Code</a> para Windows (7, 8.1 ou 10), macOS <b>(High Sierra 10.13 ou posterior)</b> e Linux 64 bits <b>(<a href="use/vscode.md#installation">detalhes</a>)</b><br />
        2. Baixe e instale a extensão do Visual Studio Live Share por meio do marketplace. <br />
        3. Recarregue-a e aguarde até as dependências serem baixadas e instaladas (veja a barra de status).<br />
        4. <strong>Linux</strong>: se for solicitado a <a href="reference/linux.md#install-linux-prerequisites">instalar bibliotecas</a>, clique em instalar, digite a senha, reinicie vs Code quando terminar.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. Instale o <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
        2. Instale uma <a href="reference/platform-support.md">carga de trabalho compatível</a>. (por exemplo, ASP.NET, .NET Core, C++, Python e/ou Node.js)<br />
        3. O Visual Studio Live Share é instalado por padrão com essas cargas de trabalho. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 ou posterior</strong><br />
        1. Instale a última versão do <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a> (15.6 ou posterior) no Windows (7, 8.1 ou 10).<br/>
        2. Instale uma <a href="reference/platform-support.md">carga de trabalho compatível</a>. (por exemplo, ASP.NET, .NET Core, C++ e/ou Node.js)<br />
        3. Baixe e instale a extensão do Visual Studio Live Share por meio do marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

Ao baixar e usar o Visual Studio Live Share, você concorda com os [termos de licença](https://aka.ms/vsls-license) e a [política de privacidade](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Confira [Solução de problemas](troubleshooting.md) caso tenha problemas.

Isso é tudo! Agora você deverá ver uma barra de status de entrada no canto inferior esquerdo do VS Code e um botão de compartilhamento na parte superior direita do Visual Studio. Confira o restante da documentação para saber o que fazer em seguida.


## <a name="see-also"></a>Veja também

Guias de Início Rápido

- [Compartilhar seu primeiro projeto](quickstart/share.md)
- [Ingressar em sua primeira sessão](quickstart/join.md)

Instruções

- [Colaborar usando o Visual Studio Code](use/vscode.md)
- [Colaborar usando o Visual Studio](use/vs.md)

Referência

- [Requisitos de conectividade do Live Share](reference/connectivity.md)
- [Funcionalidades de segurança do Live Share](reference/security.md)
- [Suporte de idioma e plataforma](reference/platform-support.md)
- [Suporte de extensão](reference/extensions.md)
- [Notas sobre a versão](https://aka.ms/vsls-releases)

Está tendo problemas? Confira [Solução de problemas](troubleshooting.md) ou [envie comentários](support.md).
