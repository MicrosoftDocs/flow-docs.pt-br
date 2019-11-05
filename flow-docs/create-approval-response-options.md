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
ms.openlocfilehash: eaaa87f9213c5ed04aee65e37ee642436e49dfca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547214"
---
# <a name="create-custom-response-options-for-approval-flows"></a>Criar opções de resposta personalizadas para fluxos de aprovação
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Digamos que você deseja enviar uma solicitação de aprovação sempre que um funcionário carregar um relatório de despesas no SharePoint e, em seguida, permitir que o aprovador responda com uma das três opções: aceitar, precisar de mais informações ou rejeitar.


## <a name="prerequisites"></a>Pré-requisitos

- Uma conta de Microsoft Flow.
- Uma lista do SharePoint para que os funcionários insiram seus relatórios de despesas.

## <a name="create-approval-flow"></a>Criar fluxo de aprovação
1. Entre no [Microsoft Flow](https://flow.microsoft.com).
1. Selecione **meus fluxos** na barra de navegação à esquerda.
1. Selecione **novo** > **criar em branco**.

    ![Opção criar com base em branco](media/create-approval-response-options/create-approval-response-options.png)

1. Na tela que é aberta, selecione **criar em branco**. 

    ![Selecione criar em branco](media/create-approval-response-options/create-from-blank.png)

1. Pesquise o **SharePoint** e, em seguida, selecione **quando um item for criado** na lista de gatilhos. 

1. Forneça o **endereço do site** do SharePoint e o **nome da lista**. 

1. Selecione **nova etapa**, Pesquisar **aprovação**e, em seguida, selecione **Iniciar e aguardar uma aprovação (v2)** .

1. Na barra **Iniciar e aguardar uma aprovação (v2)** , selecione a lista **tipo de aprovação** .

    ![Tipo de aprovação](media/create-approval-response-options/select-approval-type.png)

1. Selecione **respostas personalizadas – aguardar uma resposta (Premium)** .

    ![Respostas personalizadas](media/create-approval-response-options/select-custom-responses.png)

    Em seguida, você criará as respostas personalizadas que seus aprovadores usarão quando responderem a uma solicitação de aprovação para uma despesa de funcionário.


1. Na caixa de **Opções de resposta item-1** , digite **Accept** e, em seguida, selecione **Adicionar novo item**. 

    ![Resposta personalizada 1](media/create-approval-response-options/enter-response-1.png)

1. Na caixa **Opções de resposta item-2** , digite **rejeitar** e, em seguida, selecione **Adicionar novo item**.

    ![Resposta personalizada 2](media/create-approval-response-options/enter-response-2.png)

1. Na caixa **Opções de resposta item-3** , digite **precisa de mais informações**.

    ![Resposta personalizada 3](media/create-approval-response-options/enter-response-3.png)   
    

1. Insira um **título**, **atribuído a** (email para o aprovador) e **detalhes** (os detalhes a serem contidos na solicitação de aprovação).

    Aqui está um exemplo do que você pode incluir para sua organização.

    ![Detalhes de respostas personalizadas](media/create-approval-response-options/enter-title-assigned-to-details.png)


Agora que você criou suas respostas personalizadas, talvez queira fazer coisas diferentes em seu fluxo, dependendo da resposta do aprovador.


## <a name="use-approval-responses"></a>Usar respostas de aprovação 

Se a resposta à solicitação for **aceita**, talvez você queira enviar um email para o departamento de contabilidade, solicitando que ele reembolsa o funcionário pela despesa. 

Se a resposta for **rejeitada**, talvez você queira enviar um email para o funcionário, informando-o de que a solicitação foi rejeitada.

E, finalmente, se a resposta do aprovador **precisar de mais informações**, talvez você queira enviar um email para o funcionário, solicitando que o funcionário forneça mais informações.

Para fazer qualquer um deles no fluxo, adicione uma [**condição**](add-condition.md) ou uma ação de **comutação** ao seu fluxo e, em seguida, selecione o campo **resultado** da solicitação de aprovação no seletor de conteúdo dinâmico. Certifique-se de confirmar se o valor é aceito, precisar de mais informações ou rejeitar.

## <a name="respond-to-approval-requests-with-a-custom-response"></a>Responder a solicitações de aprovação com uma resposta personalizada

Os aprovadores recebem solicitações de aprovação por email. As solicitações também são exibidas no centro de aprovação em Microsoft Flow. 

![Email de solicitação de aprovação](media/create-approval-response-options/approval-request-email.png)

## <a name="learn-more"></a>Saiba Mais
- Criar [fluxos de aprovador único](modern-approvals.md)
- Criar [fluxos de aprovador sequenciais](sequential-modern-approvals.md)
