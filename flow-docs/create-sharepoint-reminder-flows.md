---
title: Criar um fluxo de lembrete para itens do SharePoint | Microsoft Docs
description: Crie fluxos que enviem lembretes com datas de conclusão para itens do SharePoint.
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
ms.openlocfilehash: b0f1aa80fb92c9718d2b0697d3abb0b0d2478013
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061102"
---
# <a name="sharepoint-remind-me"></a>Lembretes do SharePoint

As bibliotecas e listas do SharePoint permitiam definir colunas de metadados personalizadas para controlar datas. Com a integração do Microsoft Flow ao SharePoint, é possível facilmente criar fluxos de lembretes com base em colunas DateTime no SharePoint. Com os fluxos de lembretes, você recebe um alerta de email pessoal, em um número predeterminado de dias de antecedência de uma data específica, sobre documentos ou itens do SharePoint.

## <a name="prerequisites"></a>Pré-requisitos
- Acesso ao Microsoft SharePoint Online.
- Uma lista ou biblioteca do SharePoint com uma coluna DateTime.
- Acesso ao Microsoft Flow.

## <a name="create-a-reminder-flow"></a>Criar um fluxo de lembrete

 1. Crie uma [lista do SharePoint](https://support.office.com/article/Create-a-list-in-SharePoint-0D397414-D95F-41EB-ADDD-5E6EFF41B083) com pelo menos uma coluna DateTime no modo de exibição atual. 
 1. Selecione **Fluxo** > **Definir um lembrete** > **Data da desativação** (Esta é a coluna com a Data/Hora do lembrete).

     ![Selecionar um fluxo de lembrete](media/create-sharepoint-reminder-flows/select-reminder-flow.png)

1. Atribua o **Nome do fluxo** e insira o número de dias de antecedência em que deseja receber um alerta de lembrete, na entrada da coluna DateTime do cartão **Definir um lembrete**.

    ![Detalhes em Definir fluxo de lembrete](media/create-sharepoint-reminder-flows/set-reminder-details.png)

1. Selecione **Criar**, no cartão **Definir um lembrete**.

1. Você receberá a seguinte mensagem, indicando que o fluxo foi criado:

    ![Fluxo de lembrete criado](media/create-sharepoint-reminder-flows/success.png)
    

## <a name="confirm-reminders-received"></a>Confirmar lembretes recebidos

Você receberá um lembrete por email, de acordo com a entrada **Lembrar-me com estes dias de antecedência** inserida no fluxo **Definir um lembrete** criado anteriormente. 

## <a name="edit-your-flow"></a>Editar o fluxo

O fluxo de lembrete é parecido com qualquer outro fluxo, portanto você pode acessá-lo e editá-lo por meio do [Microsoft Flow](https://flow.microsoft.com).

## <a name="learn-more"></a>Saiba mais

- Introdução ao [Microsoft Flow](https://flow.microsoft.com).
- Definir um [fluxo de lembrete](https://support.office.com/article/set-a-reminder-flow-23c0e172-1fc1-4ac8-a9db-cd0b81d634d8) no SharePoint.


