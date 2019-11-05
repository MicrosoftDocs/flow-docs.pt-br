---
title: Aprenda a criar fluxos que postam cartões adaptáveis ao Microsoft Teams | Microsoft Docs
description: Aprenda a criar fluxos que postam conteúdo com formatação avançada com cartões adaptáveis para o Microsoft Teams.
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
ms.openlocfilehash: 0aa5b4727bea569732fe5b76f717a87d8d7ddb02
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546489"
---
<!--from editor: I notice that adaptive cards is capitalized on the page opened by the link in the first paragraph. But the screenshots in this file don't show it being capitalized. So I'm unsure if it should change.-->


# <a name="use-adaptive-cards-in-microsoft-teams"></a>Usar cartões adaptáveis no Microsoft Teams
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Você pode criar um fluxo que posta [cartões adaptáveis](https://adaptivecards.io) em um canal do Microsoft Teams. Com os cartões adaptáveis, você pode usar formatação avançada para tornar suas postagens mais claras, interativas e atraentes. Os cartões adaptáveis podem conter componentes como imagens, grafos, texto com formatação avançada e muito mais.

## <a name="create-a-flow-that-posts-adaptive-cards-to-a-team"></a>Criar um fluxo que posta cartões adaptáveis em uma equipe

Siga estas etapas para criar um fluxo que posta um cartão adaptável para o canal geral na equipe de estratégia e planejamento. O fluxo que criamos usa o **seu próprio cartão adaptável como o bot de fluxo para uma ação de canal (versão prévia)** para postar o conteúdo do cartão adaptável para o canal da equipe semanalmente.

1. Entre no Microsoft Teams.
1. Selecione o ícone **equipes** na barra de navegação à esquerda e, em seguida, selecione a equipe de **estratégia e planejamento** .

    ![Selecionar equipes](media/create-adaptive-cards-teams/select-teams-team.png)

1. Selecione a guia **fluxo** na parte superior da tela.
1. Selecione o ícone de **+** (criar a partir de em branco).
1. Pesquise **recorrência**e, em seguida, selecione o gatilho **recorrência** .

    ![Cartão de recorrência](media/create-adaptive-cards-teams/select-recurrence.png)

1. Defina o agendamento da seguinte maneira para repetir a cada semana, em um fuso horário e horário de sua escolha:
    
    ![Cartão de recorrência](media/create-adaptive-cards-teams/recurrence-card.png)
    
1. Selecione **nova etapa**.
1. Pesquise por **adaptável**, selecione **Microsoft Teams**e, em seguida, selecione a ação **postar seu próprio cartão adaptável como o bot de fluxo para um canal (versão prévia)** .

   ![Cartão adaptável](media/create-adaptive-cards-teams/select-adaptive-post-message-action.png)

1. Forneça uma **equipe**, **canal**e **mensagem** no cartão **poste seu próprio adaptador adaptável como o bot de fluxo para um canal (versão prévia)** para indicar a equipe e o canal para o qual a **mensagem** de cartão adaptável será postada.

   ![Cartão adaptável](media/create-adaptive-cards-teams/adaptive-card-message.png)

   Você pode usar este conteúdo JSON de exemplo para a **mensagem**:

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


1. Dê um nome ao seu fluxo e salve-o.


## <a name="run-the-flow"></a>Executar o fluxo

Observe que, após decorrer o tempo de recorrência, o fluxo envia o conteúdo do cartão adaptável para o canal de equipe que você definiu.

![Executar o fluxo](media/create-adaptive-cards-teams/flow-run-result.png)

## <a name="learn-more"></a>Saiba Mais

- Introdução aos [exemplos de cartões adaptáveis](https://adaptivecards.io/samples/).
- Crie [conteúdo de cartão adaptável](https://adaptivecards.io) da maneira fácil.



