---
title: Aprenda a criar e gerenciar fluxos no Microsoft Teams | Microsoft Docs
description: Crie e gerencie fluxos para postar mensagens sob demanda, @mention usuários e canais, lançar cartões com opções de resposta e muito mais.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 34cb8577d57d70686fd9811db9146443b56a07b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547989"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow em equipes
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

### <a name="prerequisites"></a>Pré-requisitos

1. Acesso ao Microsoft Teams.
1. Acesso a Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Instalar o aplicativo Microsoft Flow no Teams

Siga estas etapas para instalar o aplicativo Microsoft Flow no Microsoft Teams.

1. Entre no Microsoft Teams.

1. Toque no ícone **aplicativos** na parte inferior esquerda da barra de navegação das equipes.

    ![Selecionar aplicativos](media/flows-teams/apps.png)

1. Selecione o aplicativo de **fluxo** . Talvez seja necessário pesquisar o **Flow** se você não o vir.

    ![Selecionar aplicativo de fluxo](media/flows-teams/select-flow-app.png)

1. Selecione **instalar**.

    ![Botão instalar](media/flows-teams/select-install.png)

1. O Microsoft Flow agora está instalado.

    ![Recém-instalado](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Criar um fluxo em equipes

1. Entre no Microsoft Teams.

1. Selecione o link **aplicativos mais adicionados** (...) na barra de navegação e, em seguida, selecione o aplicativo de **fluxo** .

    ![Ícone de aplicativos adicionados](media/flows-teams/added-apps-icon.png)

1. Se você ainda não fez isso antes, talvez seja necessário entrar e conceder permissões.

    ![Entrar](media/flows-teams/grant-permissions-sign-in.png)


    Observe as seguintes guias:

    ![Página de aterrissagem do fluxo](media/flows-teams/flow-landing-page.png)

    Nomes|Objetivo
    ----|-----|
    Escreve|Interaja com o bot de fluxo.
    Fluxo|Criar e gerenciar fluxos.
    Aprovações|Lista as solicitações de aprovação recebidas e enviadas.
    Pensar|Exibe a versão e outras informações sobre Microsoft Flow.


    Agora você verá todos os fluxos que criou do designer de Microsoft Flow (se houver). 

    Você também pode criar fluxos de um modelo personalizado ou de um modelo em branco, assim como faz no designer de Microsoft Flow. 

## <a name="manage-approvals"></a>Gerenciar aprovações

Você pode gerenciar [aprovações](modern-approvals.md) no Microsoft Teams, assim como faria em Microsoft Flow. Siga estas etapas para gerenciar suas aprovações:

1. Entre no Microsoft Teams.
1. Selecione a guia **aprovações** .

    ![Guia Aprovações](media/flows-teams/approvals-tab.png)

    Você observará as seguintes subguias:

    Abas|Objetivo
    ----|-----|
    Recepção|Lista as solicitações de aprovação que você recebeu e as ações pendentes de você.
    Enviados|Lista as solicitações de aprovação que você enviou e estão com ações pendentes de outras.
    Cliques|Lista as solicitações de aprovação recebidas e enviadas.
    Criar fluxo de aprovação|Criar fluxos de aprovação.

1. Selecione as guias **recebido**, **enviado**ou **histórico** para saber mais.

    ![Guia Aprovações](media/flows-teams/approvals-tab-2.png)

1. Selecione **criar fluxo de aprovação** para criar um fluxo de aprovação.

    ![Guia Aprovações](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Usar o bot com fluxos

### <a name="list-and-launch-flows-with-the-bot"></a>Listar e iniciar fluxos com o bot

> [!TIP]
> O bot lista e executa fluxos que são disparados por um agendamento ou disparados manualmente sem entrada do usuário.

1. Entre no Microsoft Teams.
1. Selecione o link **aplicativos mais adicionados** (...) na barra de navegação e, em seguida, selecione o aplicativo de **fluxo** .

    ![Ícone de aplicativos adicionados](media/flows-teams/added-apps-icon.png)
    
1. Selecione a guia **conversa** .

    ![Guia de conversa](media/flows-teams/conversations-tab.png)

Na guia **conversa** , você pode enviar comandos para o bot, que responde executando as ações que você comando para executar. Por exemplo, para listar seus fluxos e executar o fluxo com o índice 1, execute os seguintes comandos:

- ```List flows```-o bot exibe uma lista de seus fluxos, prefixados por um número de índice.
- ```Run flow 1```-executa o fluxo número 1. Aqui, *1* é o número de índice do fluxo que você deseja executar.

   ![Comandos de bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Obter a descrição dos fluxos

Para obter a descrição do fluxo com o índice 1 da sua lista de fluxos, execute ```describe flow 1```. A resposta do bot será semelhante a esta imagem:

   ![Descrever fluxos](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Obter a lista de comandos para o bot

Para obter a lista de comandos que o bot manipula, pergunte com este comando: ```learn more``` 

A resposta do bot será semelhante a esta imagem:

![Descrever fluxos](media/flows-teams/bot-learn-more.png) 
