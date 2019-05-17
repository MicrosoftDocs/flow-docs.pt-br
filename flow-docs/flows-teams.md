---
title: Saiba mais sobre como criar e gerenciar fluxos no Microsoft Teams | Microsoft Docs
description: Crie e gerencie fluxos para postar mensagens sob demanda, usuários e canais do @mention, postar cartões com opções de resposta e muito mais.
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
ms.openlocfilehash: 4987d1f4fb504c0279540eb86dcb6ad1b983ff4a
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65061838"
---
# <a name="microsoft-flow-in-teams"></a>Microsoft Flow no Teams

### <a name="prerequisites"></a>Pré-requisitos

1. Acesso ao Microsoft Teams.
1. Acesso ao Microsoft Flow.

## <a name="install-the-microsoft-flow-app-in-teams"></a>Instalar o aplicativo Microsoft Flow no Teams

Siga os procedimentos a seguir para instalar o aplicativo Microsoft Flow no Microsoft Teams.

1. Entre no Microsoft Teams.

1. Toque no ícone **Aplicativos** na parte inferior esquerda da barra de navegação do Teams.

    ![Selecionar aplicativos](media/flows-teams/apps.png)

1. Selecione o aplicativo **Flow**. Talvez seja necessário procurar o **Flow**, caso você não o veja.

    ![Selecionar o aplicativo Flow](media/flows-teams/select-flow-app.png)

1. Selecione **Instalar**.

    ![Botão Instalar](media/flows-teams/select-install.png)

1. O Microsoft Flow já está instalado.

    ![Instalado](media/flows-teams/flow-installed.png)


## <a name="create-a-flow-in-teams"></a>Criar um fluxo no Teams

1. Entre no Microsoft Teams.

1. Selecione o link **Mais aplicativos adicionados** (...) na barra de navegação e, em seguida, selecione o aplicativo **Flow**.

    ![Ícone Aplicativos adicionados](media/flows-teams/added-apps-icon.png)

1. Talvez seja necessário entrar e conceder permissões, caso ainda não o tenha feito.

    ![Entrar](media/flows-teams/grant-permissions-sign-in.png)


    Observe as seguintes guias:

    ![Página de aterrissagem do Flow](media/flows-teams/flow-landing-page.png)

    Nome|Finalidade
    ----|-----|
    Conversação|Interagir com o bot do Flow.
    Fluxos|Criar e gerenciar fluxos.
    Aprovações|Relaciona as solicitações de aprovação enviadas e recebidas.
    Sobre|Exibe a versão e outras informações sobre o Microsoft Flow.


    Agora, todos os fluxos criados no Designer do Microsoft Flow estão visíveis (quando for o caso). 

    Você pode inclusive criar fluxos com base em um modelo personalizado ou em branco, exatamente como o faz usando o Designer do Microsoft Flow. 

## <a name="manage-approvals"></a>Gerenciar aprovações

Você pode gerenciar as [aprovações](modern-approvals.md) no Microsoft Teams, da mesma maneira que o faria no Microsoft Flow. Siga estes procedimentos para gerenciar suas aprovações:

1. Entre no Microsoft Teams.
1. Selecione a guia **Aprovações**.

    ![Guia Aprovações](media/flows-teams/approvals-tab.png)

    Confira as seguintes subguias:

    Guia|Finalidade
    ----|-----|
    Recebidas|Relaciona as solicitações de aprovação recebidas e que aguardam que você realize uma ação.
    Enviadas|Relaciona as solicitações de aprovação enviadas e aguarda uma ação de outras pessoas.
    Histórico|Relaciona as solicitações de aprovação enviadas e recebidas.
    Criar fluxo de aprovação|Criar fluxos de aprovação.

1. Para saber mais, selecione as guias **Recebidas**, **Enviadas** ou **Histórico**.

    ![Guia Aprovações](media/flows-teams/approvals-tab-2.png)

1. Para criar um fluxo de aprovação, selecione **Criar fluxo de aprovação**.

    ![Guia Aprovações](media/flows-teams/approvals-tab-3.png)

## <a name="use-the-bot-with-flows"></a>Usar o bot com fluxos

### <a name="list-and-launch-flows-with-the-bot"></a>Relacionar e iniciar fluxos com o bot

> [!TIP]
> O bot relaciona e executa fluxos que são acionados por um cronograma ou acionados manualmente sem entrada do usuário.

1. Entre no Microsoft Teams.
1. Selecione o link **Mais aplicativos adicionados** (...) na barra de navegação e, em seguida, selecione o aplicativo **Flow**.

    ![Ícone Aplicativos adicionados](media/flows-teams/added-apps-icon.png)
    
1. Selecione a guia **Conversa**.

    ![Guia Conversa](media/flows-teams/conversations-tab.png)

Na guia **Conversa**, você pode enviar comandos para o bot, que responde realizando as ações atribuídas a ele. Por exemplo, para relacionar os fluxos e executar o fluxo com índice 1, execute os seguintes comandos:

- ```List flows``` – o bot exibe uma lista dos fluxos prefixados por um número de índice.
- ```Run flow 1``` – executa o fluxo número 1. Nesse caso, *1* representa o número de índice do fluxo que você quer executar.

   ![Comandos do bot](media/flows-teams/bot-commands.png)

### <a name="get-the-description-for-flows"></a>Obter a descrição dos fluxos

Para obter a descrição do fluxo com índice 1 da lista de fluxos, execute ```describe flow 1```. A resposta do bot será semelhante à imagem abaixo:

   ![Descrever fluxos](media/flows-teams/bot-describe.png)

### <a name="get-the-list-of-commands-for-the-bot"></a>Obter a lista de comandos do bot

Para obter a lista de comandos tratados pelo bot, solicite-a com o seguinte comando: ```learn more``` 

A resposta do bot será semelhante à imagem abaixo:

![Descrever fluxos](media/flows-teams/bot-learn-more.png) 
