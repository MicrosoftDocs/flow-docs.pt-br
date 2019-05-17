---
title: Saiba mais sobre como criar fluxos para postagem de cartões adaptáveis no Microsoft Teams | Microsoft Docs
description: Saiba mais sobre como criar fluxos para postagem de conteúdo com formatação avançada usando cartões adaptáveis no Microsoft Teams.
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
ms.openlocfilehash: d6bb4bb55fe876db1d8b64c157d3b4967e5d067f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65061562"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Usar cartões adaptáveis no Microsoft Teams

É possível criar um fluxo para postagem de [cartões adaptáveis](https://adaptivecards.io) em um canal do Microsoft Teams. Você pode usar uma formatação avançada com os cartões adaptáveis para tornar as postagens mais claras, interativas e envolventes. Os cartões adaptáveis podem incluir componentes como imagens, representações em gráfico, texto com formatação avançada e muito mais.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Criar um fluxo para postagem de cartões adaptáveis em uma equipe

Faça os procedimentos a seguir a fim de criar um fluxo para postagem de um cartão adaptável, no canal geral da equipe de Estratégia e planejamento. O fluxo que criamos usa a ação **Postar seu próprio cartão adaptável como o bot do Flow em um canal (versão prévia)** para postar o conteúdo do cartão adaptável semanalmente, no canal da equipe.

1. Entre no Microsoft Teams.
1. Selecione o ícone do **Teams**, na barra de navegação à esquerda, e selecione a equipe de **Estratégia e planejamento**.

    ![Selecionar equipes](media/create-adaptive-cards-teams/select-teams-team.png)

1. Selecione a guia **Fluxo**, no início da tela.
1. Selecione o ícone **+** (Criar do zero).
1. Procure **recorrência** e, em seguida, escolha o gatilho **Recorrência**.

    ![Cartão de recorrência](media/create-adaptive-cards-teams/select-recurrence.png)

1. Defina o agendamento para repetição semanal com a hora de início e o fuso horário desejados, de acordo com a imagem abaixo:
    
    ![Cartão de recorrência](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Selecione **Nova etapa**.
1. Procure **adaptável**, selecione o **Microsoft Teams** e escolha a ação **Postar seu próprio cartão adaptável como o bot do Flow em um canal (versão prévia)**.

   ![Cartão adaptável](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Forneça uma **equipe**, um **canal** e uma **mensagem** no cartão **Postar seu próprio cartão adaptável como o bot do Flow em um canal (versão prévia)** para indicar a equipe e o canal nos quais a **Mensagem** do cartão adaptável será postada.

   ![Cartão adaptável](media/create-adaptive-cards-teams/adaptive-card-message.png)

   Você pode usar o seguinte conteúdo JSON de exemplo para a **Mensagem**:

    ````
        {
    "$schema": "http://adaptivecards.io/schemas/adaptive-card.json",
    "type": "AdaptiveCard",
    "version": "1.0",
    "speak": "Our team meeting is starting soon. Do you want to snooze  or do you want to send a late notification to the attendees?",
    "body": [
        {
        "type": "TextBlock",
        "text": "Strategy and Planning Weekly Team meeting",
        "size": "large",
        "weight": "bolder"
        },
        {
        "type": "TextBlock",
        "text": "Conf Room 112/3377 (10)",
        "isSubtle": true
        },
        {
        "type": "TextBlock",
        "text": "12:30 PM - 1:30 PM",
        "isSubtle": true,
        "spacing": "none"
        },
        {
        "type": "TextBlock",
        "text": "Snooze for"
        },
        {
        "type": "Input.ChoiceSet",
        "id": "snooze",
        "style": "compact",
        "value": "5",
        "choices": [
            {
            "title": "5 minutes",
            "value": "5",
            "isSelected": true
            },
            {
            "title": "15 minutes",
            "value": "15"
            },
            {
            "title": "30 minutes",
            "value": "30"
            }
        ]
        }
    ],
    "actions": [
        {
        "type": "Action.Submit",
        "title": "Snooze",
        "data": {
            "x": "snooze"
        }
        },
        {
        "type": "Action.Submit",
        "title": "I'll be late",
        "data": {
            "x": "late"
        }
        }
    ]
    }
    ````


1. Atribua um nome ao fluxo e salve-o.


## <a name="run-the-flow"></a>Executar o fluxo

Após a passagem do tempo de recorrência, o fluxo postará o conteúdo do cartão adaptável no canal da equipe que você definiu.

![Executar o fluxo](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Saiba mais

- Introdução aos [exemplos de cartões adaptáveis](https://adaptivecards.io/samples/).
- Crie [conteúdo de cartão adaptável](https://adaptivecards.io) da maneira mais fácil.



