---
title: Criar um fluxo de trabalho de aprovação moderno com vários aprovadores | Microsoft Docs
description: 'Criar um fluxo de trabalho de aprovação moderno com vários aprovadores '
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: dd30051425906fdc305be536342eeb7e1762d1eb
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65019858"
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>Gerenciar aprovações sequenciais com o Microsoft Flow
Alguns fluxos de trabalho exigem aprovação prévia antes do aprovador final ser solicitado a desconectar. Por exemplo, uma empresa pode ter uma política de aprovação sequencial que requer aprovação prévia para faturas acima de $1000.00 antes de serem aprovadas pelo departamento de Finanças.

Neste passo a passo, podemos criar um fluxo sequencial de aprovação que gerencia as solicitações de férias do funcionário.

> [!NOTE]
> O SharePoint é usado aqui somente como um exemplo. Não é necessário usá-lo para criar fluxos de aprovação. Você pode escolher entre mais de 200 serviços com os quais o Microsoft Flow se integra para gerar fluxos.


## <a name="detailed-steps-in-the-flow"></a>Etapas detalhadas no fluxo
O fluxo:

1. É iniciado quando um funcionário cria uma solicitação de férias em uma [lista do SharePoint Online](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).
2. Adiciona a solicitação de férias ao centro de aprovação e, em seguida, envia a solicitação por email para o aprovador prévio.
3. Envia por email a decisão de aprovação prévia para o funcionário.
4. Atualiza a lista do SharePoint Online com a decisão e os comentários do aprovador prévio.
   
   Observação: se a solicitação for pré-aprovada, o fluxo continuará com estas etapas:
5. Envia a solicitação para o aprovador final.
6. Envia por email a decisão final para o funcionário.
7. Atualiza a lista do SharePoint com a decisão final.

Esta imagem resume as etapas anteriores:

   ![diagrama do Visio do fluxo](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Pré-requisitos
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Para fins deste passo a passo, a lista do SharePoint Online que você criar deverá incluir as seguintes colunas:

   ![Colunas da lista do SharePoint](./media/sequential-modern-approvals/sharepoint-columns.png)

Anote o nome e a URL da lista do SharePoint Online. Utilizamos esses itens posteriormente ao configurar o gatilho **SharePoint - Quando um novo item é criado**.

## <a name="create-your-flow-from-the-blank-template"></a>Crie seu fluxo a partir do modelo em branco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>adicione um gatilho
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![informações do SharePoint](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obter o gerente da pessoa que criou a solicitação de férias
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Forneça um nome para o fluxo e, em seguida, selecione **Criar fluxo** para salvar o trabalho que fizemos até agora.
   
    ![salvar fluxo](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Selecione **Atualizar fluxo** na parte superior da tela periodicamente para salvar as alterações ao seu fluxo.
   > 
   > 
   
    ![selecionar atualizar ação](./media/sequential-modern-approvals/update.png)

Depois de cada operação de salvamento, selecione **Editar fluxo** na parte superior da tela e, em seguida, continue fazendo alterações.

## <a name="add-an-approval-action-for-pre-approvals"></a>Adicionar uma ação de aprovação para aprovações prévias
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Observação: esta ação envia a solicitação de aprovação prévia para o endereço de email na caixa **Atribuído a**.

## <a name="add-a-condition"></a>Adicionar uma condição
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Esta condição verifica a resposta da ação **Iniciar uma aprovação**.
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Adicionar uma ação de email para aprovações prévias
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar o modelo de email aprovado previamente](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Adicionar uma ação de atualização para solicitações aprovadas previamente
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![atualizar configuração de item](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>Obter o gerenciador do aprovador prévio
1. Use as etapas [Obter o gerenciador da pessoa que criou a solicitação de férias](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) que fizemos anteriormente para adicionar e, em seguida, configurar outra ação **Obter gerenciador**. Desta vez obtivemos o gerenciador do aprovador prévio.
2. O cartão **Obter gerenciador 2** deve ser semelhante a esta imagem quando você tiver terminado. Use o token **Email** na categoria **Obter gerenciador** no cartão **Adicionar conteúdo dinâmico a partir de aplicativos e serviços usados neste fluxo**.
   
   ![obter o gerenciador do aprovador prévio](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Adicione a ação de aprovação final
1. Use as etapas [adicionar uma ação de aprovação para aprovações prévias](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) que fizemos anteriormente para adicionar e, em seguida, configurar outra ação **Iniciar uma aprovação**. Essa ação envia uma solicitação por email para aprovação final.
2. Quando terminar, o cartão deve ser semelhante a esta imagem:
   
    ![configurar a aprovação](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Adicionar a condição de aprovação final
1. Repita as etapas de [adicionar uma condição](sequential-modern-approvals.md#add-a-condition) para adicionar e, em seguida, configure uma **Condição** que verifica a decisão do aprovador final.

## <a name="send-email-with-final-approval"></a>Enviar email com a aprovação final
1. Use as etapas de [Adicionar uma ação de email para aprovações prévias](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) para adicionar e, em seguida, configurar uma ação que envia um email quando solicitações de férias forem aprovadas.
2. Quando terminar, seu cartão deve ser semelhante a esta imagem:
   
   ![modelo de email de aprovação final](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>Atualizar o SharePoint com aprovação
1. Use as etapas de [adicionar uma ação de atualização para solicitações pré-aprovadas](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) para adicionar e, em seguida, configurar uma ação que atualiza o SharePoint quando a solicitação de férias for aprovada.
2. Quando terminar, o cartão deve ser semelhante a esta imagem:
   
    ![atualizar configuração de item](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Enviar email com rejeição de aprovação prévia
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![configuração de solicitações rejeitadas](./media/sequential-modern-approvals/configure-rejected-email.png)

Observação: esta ação deve ser adicionada à ramificação **SE NÃO, NÃO FAÇA NADA**, abaixo do cartão **Condição**.

## <a name="update-sharepoint-with-pre-approval-rejection"></a>Atualizar o SharePoint com rejeição de aprovação prévia
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![atualizar o SharePoint para solicitações rejeitadas](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Enviar email com a rejeição final
1. Use as etapas de [Enviar email com rejeição de aprovação prévia](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) para adicionar e, em seguida, configurar uma ação que envia um email quando a solicitação de férias é rejeitada pelo aprovador final.
   
    Observação: esta ação deve ser adicionada à ramificação **SE NÃO, NÃO FAÇA NADA**, abaixo do cartão **Condição 2**.
2. Quando terminar, o cartão deve ser semelhante a esta imagem:
   
   ![configuração de solicitações rejeitadas](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Atualizar o SharePoint com rejeição final
1. Use as etapas de [Atualizar o SharePoint com rejeição de aprovação prévia](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) para adicionar e, em seguida, configurar uma ação que atualiza o SharePoint se o aprovador final rejeitar a solicitação de férias.
2. Quando terminar, o cartão deve ser semelhante a esta imagem:
   
   ![atualizar cartão do item](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. Selecione **Atualizar fluxo** para salvar o trabalho que fizemos.
   
   ![selecionar atualizar ação](./media/sequential-modern-approvals/update.png)

Se você acompanhou até aqui, o fluxo deve se parecer com esta imagem:

![visão geral do fluxo](./media/sequential-modern-approvals/completed-flow.png)

Agora que criamos o fluxo, vamos ver em ação.

## <a name="request-an-approval"></a>Solicitar uma aprovação
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

Sua solicitação deve ser semelhante a esta imagem:

![solicitação de férias](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Exibir solicitações de aprovação pendente
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Aprovar previamente uma solicitação
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>Aprovar a solicitação
As etapas para aprovar uma solicitação são idênticas às etapas para [aprovar previamente uma solicitação](sequential-modern-approvals.md#pre-approve-a-request)

Observação: o aprovador final receberá a solicitação de férias, somente após a aprovação prévia da solicitação.

## <a name="reject-a-request"></a>Rejeitar uma solicitação
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Mais informações
[Passo a passo das aprovações modernas do aprovador único](modern-approvals.md)

