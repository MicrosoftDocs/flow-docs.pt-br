---
title: Criar um fluxo de lembretes para itens do SharePoint | Microsoft Docs
description: Crie fluxos que o lembram de datas de conclusão para itens do SharePoint.
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
ms.date: 04/30/2019
ms.author: deonhe
ms.openlocfilehash: c7c87df5288ba58d303de441b41e7493cd713f4a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547562"
---
# <a name="sharepoint-remind-me"></a>Lembrar do SharePoint
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

As listas e bibliotecas do SharePoint permitiam que você definisse colunas de metadados personalizadas para controlar as datas. Com a integração do Microsoft Flow com o SharePoint, você pode criar facilmente fluxos de lembretes com base em colunas DateTime no SharePoint. Com os fluxos de lembretes, você recebe um alerta de email pessoal um número predeterminado de dias antes de uma data em qualquer documento ou item no SharePoint.

## <a name="prerequisites"></a>Pré-requisitos
- Acesso ao Microsoft SharePoint Online.
- Uma lista do SharePoint ou uma biblioteca com uma coluna DateTime.
- Acesso a Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Criar um fluxo de lembretes

 1. Crie uma [lista do SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) com pelo menos uma coluna DateTime na exibição atual. 
 1. Selecione **Flow** > **definir um lembrete** > **data de desativação** (essa é a coluna com DateTime para o lembrete).

     ![Selecionar fluxo de lembretes](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Forneça um **nome de fluxo** e o número de dias antes da entrada da coluna DateTime quando você quiser receber o alerta de lembrete no cartão **definir um lembrete** .

    ![Definir detalhes do fluxo de lembretes](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Selecione **criar** no cartão **definir um lembrete** .

1. Você receberá a seguinte mensagem, indicando que o fluxo foi criado:

    ![Fluxo de lembretes criado](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Confirmar lembretes recebidos

Você receberá um lembrete por email, com base nos **Lembre-me de que este número de dias na entrada antecipada** fez no **conjunto um fluxo de lembrete** criado anteriormente. 

## <a name="edit-your-flow"></a>Editar seu fluxo

O fluxo de lembretes é como qualquer outro fluxo, para que você possa acessá-lo e editá-lo por meio de [Microsoft Flow](https://flow.microsoft.com).

## <a name="learn-more"></a>Saiba Mais

- Introdução ao [Microsoft Flow](https://flow.microsoft.com).
- Definir um [fluxo de lembretes](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) no SharePoint.


