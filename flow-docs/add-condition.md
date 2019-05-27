---
title: Adicionar uma condição a um fluxo | Microsoft Docs
description: Especifique se um fluxo executa uma ou mais tarefas apenas se uma condição é verdadeira.
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
ms.openlocfilehash: b4407238f9d1782db802b47060b156b8b77c328b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456382"
---
# <a name="add-a-condition-to-a-flow"></a>Adicionar uma condição a um fluxo

Especifique se um fluxo executa uma ou mais tarefas apenas se uma condição é verdadeira. Por exemplo, especifique que você receberá um email somente se um tweet que contém uma palavra-chave for retweetado pelo menos 10 vezes.

## <a name="prerequisites"></a>Pré-requisitos

* [Criar um fluxo](get-started-logic-template.md) de um modelo: este tutorial [usa esse modelo](https://flow.microsoft.com/galleries/public/templates/e78571e5c70e4806a18eeacba5a897c8/) como exemplo

## <a name="add-a-condition"></a>Adicionar uma condição

1. Em [Microsoft Flow](https://flow.microsoft.com), selecione **Meus fluxos** na barra de navegação superior.

    Talvez seja necessário entrar se você ainda não estiver conectado.

1. Na lista de fluxos, selecione um dos fluxos criados.

    Este tutorial usa um exemplo com um gatilho do Twitter e uma ação do SharePoint.

1. Selecione **Editar fluxo**.

1. Na última ação, selecione **Nova etapa**.

1. Selecione **Adicionar uma condição**.

    ![Botão de condição](./media/add-condition/add-condition.png)

1. No cartão **Condição**, selecione uma área vazia na caixa à esquerda.

    A lista **Conteúdo dinâmico** é aberta.

1. Selecione o parâmetro **Retweetar contagem** para adicioná-lo à caixa.

1. Na caixa no meio do cartão **Condição**, selecione **é maior ou igual a**.

1. Na caixa à direita, insira **10**.

    ![A caixa NOME DO OBJETO contendo um parâmetro](./media/add-condition/specify-condition.png)

1. Selecione o cabeçalho da ação que você deseja usar dentro a condição (como **Criar item**) e arraste-o para baixo do texto que informa **Se sim**.

    Quando você solta o cursor, a ação se move para essa caixa.

    ![Arrastar ação](./media/add-condition/drag-action.png)

1. Configure a ação conforme a necessidade.

1. Salvar o fluxo.

## <a name="edit-in-advanced-mode"></a>Editar no modo avançado

Você também pode selecionar **Editar no modo avançado** para gravar as condições mais avançadas. Você pode usar qualquer expressão da *Linguagem de definição do fluxo de trabalho* no modo avançado. Saiba mais sobre todas as [expressões](https://msdn.microsoft.com/library/azure/mt643789.aspx) disponíveis.

## <a name="next-steps"></a>Próximas etapas

Saiba como [usar as expressões](use-expressions-in-conditions.md) nas condições no modo avançado.
