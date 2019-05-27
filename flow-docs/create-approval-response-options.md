---
title: Criar fluxos de aprovação com respostas personalizadas | Microsoft Docs
description: Crie fluxos de aprovação com respostas personalizadas.
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
ms.date: 05/04/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- maker
ms.openlocfilehash: d1f4b6d6dad3138bf935947076be4fe75661e36e
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65061700"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Criar opções de resposta personalizada para fluxos de aprovação

Digamos que você queira enviar uma solicitação de aprovação sempre que um funcionário carregar um relatório de despesas no SharePoint e, em seguida, permitir que o aprovador responda com uma dessas três opções: Aceitar, Precisamos de mais informações ou Rejeitar.


## <a name="prerequisites"></a>Pré-requisitos

- Uma conta do Microsoft Flow com uma licença do Plano 2 (para usar os recursos premium, como as aprovações, será necessário ter esse plano).
- Uma lista do SharePoint para que os funcionários possam inserir os respectivos relatórios de despesas.

## <a name="create-approval-flow"></a>Criar fluxo de aprovação
1. Entre no [Microsoft Flow](https://flow.microsoft.com).
1. Selecione **Meus fluxos**, na barra de navegação esquerda.
1. Selecione **Novo** > **Criar do zero**.

    ![Opção Criar do zero](media/create-approval-response-options/create-approval-response-options.png)

1. Selecione **Criar do zero** na tela exibida. 

    ![Selecione Criar do zero](media/create-approval-response-options/create-from-blank.png)

1. Procure o **SharePoint** e escolha a opção **Quando um item é criado** na lista de gatilhos. 

1. Forneça o **Endereço do Site** e o **Nome da lista** do SharePoint. 

1. Selecione **Nova etapa**, procure a opção **Aprovação** e escolha **Iniciar e aguardar uma aprovação (V2)**.

1. No cartão **Iniciar e aguardar uma aprovação (V2)**, selecione a lista **Tipo de aprovação**.

    ![Tipo de aprovação](media/create-approval-response-options/select-approval-type.png)

1. Selecione **Respostas Personalizadas - Aguardar uma resposta (Premium)**.

    ![Respostas personalizadas](media/create-approval-response-options/select-custom-responses.png)

    Veja a seguir como criar as respostas personalizadas que os aprovadores usarão ao responder às solicitações de aprovação de despesas dos funcionários.


1. Na caixa **Opções de resposta - Item 1**, insira **Aceitar** e selecione **Adicionar novo item**. 

    ![Resposta personalizada 1](media/create-approval-response-options/enter-response-1.png)

1. Na caixa **Opções de resposta - Item 2**, insira **Rejeitar** e selecione **Adicionar novo item**.

    ![Resposta personalizada 2](media/create-approval-response-options/enter-response-2.png)

1. Na caixa **Opções de resposta - Item 3**, insira **Precisamos de mais Informações**.

    ![Resposta personalizada 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Insira as informações, como **Título**, **Atribuído a** (email do aprovador) e **Detalhes** (os detalhes que serão incluídos na solicitação de aprovação).

    Veja um exemplo do que você pode incluir para sua organização.

    ![Detalhes de respostas personalizadas](media/create-approval-response-options/enter-title-assigned-to-details.png)


Depois de criar as respostas personalizadas, talvez você queira fazer outras coisas no fluxo, dependendo da resposta do aprovador.


## <a name="use-approval-responses"></a>Usar respostas de aprovação 

Se a resposta à solicitação for **Aceitar**, você pode enviar um email ao departamento de contabilidade, solicitando o reembolso da despesa para o funcionário. 

Se a resposta for **Rejeitar**, você pode enviar um email ao funcionário informando a ele que a solicitação foi rejeitada.

Por fim, se a resposta do aprovador for **Precisamos de mais informações**, é possível enviar um email ao funcionário solicitando mais informações.

Para fazer isso tudo, adicione uma [**Condição**](add-condition.md) ou uma ação de **Alternância** ao fluxo e selecione o campo **Resultado** da solicitação de aprovação no seletor de conteúdo dinâmico. Verifique se os valores são Aceitar, Precisamos de mais informações, ou Rejeitar.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Responder às solicitações de aprovação com uma resposta personalizada

Os aprovadores recebem solicitações de aprovação por email. As solicitações também são exibidas no Centro de Aprovação do Microsoft Flow. 

![Email com uma solicitação de aprovação](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Saiba mais
- Criar [fluxos de aprovação simples](modern-approvals.md)
- Criar [fluxos de aprovação sequenciais](sequential-modern-approvals.md)
