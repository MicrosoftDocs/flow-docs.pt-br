---
title: Adicionar uma condição a um fluxo | Microsoft Docs
description: Especifique se um fluxo executa uma ou mais tarefas somente se uma condição for verdadeira.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c67991a008047b2c8c58de3b9ae8833a5874543
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544706"
---
# <a name="add-a-condition-to-a-flow"></a>Adicionar uma condição a um fluxo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Especifique se um fluxo executa uma ou mais tarefas somente se uma condição for verdadeira. Por exemplo, especifique que você receberá um email somente se um tweet que contém uma palavra-chave for retweetado pelo menos 10 vezes.

## <a name="prerequisites"></a>Pré-requisitos

* [Criar um fluxo](get-started-logic-template.md) de um modelo – este tutorial [usa este modelo](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) como o exemplo

## <a name="add-a-condition"></a>Adicionar uma condição

1. Em [Microsoft Flow](https://flow.microsoft.com), selecione **meus fluxos** na barra de navegação superior.

    Talvez seja necessário entrar se você ainda não tiver entrado.

1. Na lista de fluxos, selecione um dos fluxos que você criou.

    Este tutorial usa um exemplo com um gatilho do Twitter e uma ação do SharePoint.

1. Selecione **Editar fluxo**.

1. Na última ação, selecione **nova etapa**.

1. Selecione **Adicionar uma condição**.

    ![Botão de condição](./media/add-condition/add-condition.png)

1. No cartão **condição** , selecione uma área vazia na caixa à esquerda.

    A lista de **conteúdo dinâmico** é aberta.

1. Selecione o parâmetro **retweetar contagem** para adicioná-lo à caixa.

1. Na caixa no meio do cartão **condição** , selecione **é maior ou igual a**.

1. Na caixa à direita, digite **10**.

    ![A caixa nome do objeto com um parâmetro nele](./media/add-condition/specify-condition.png)

1. Selecione o cabeçalho da ação que você deseja usar dentro da condição (como **Criar item**) e arraste-o para baixo do texto que lê **se sim**.

    Quando você libera o cursor, a ação é movida para essa caixa.

    ![Ação de arrastar](./media/add-condition/drag-action.png)

1. Configure a ação conforme necessário.

1. Salve o fluxo.

## <a name="edit-in-advanced-mode"></a>Editar no modo avançado

Você também pode selecionar **Editar no modo avançado** para escrever condições mais avançadas. Você pode usar qualquer expressão da *linguagem de definição de fluxo de trabalho* no modo avançado. Saiba mais sobre todas as [expressões](https://msdn.microsoft.com/library/azure/mt643789.aspx)disponíveis.

## <a name="next-steps"></a>Próximas etapas

Saiba como [usar expressões](use-expressions-in-conditions.md) em condições no modo avançado.
