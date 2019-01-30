---
title: Automatize facilmente os fluxos de trabalho de aprovação. | Microsoft Docs
description: Automatize os fluxos de trabalho de aprovação que se integram ao SharePoint, Dynamics CRM, Salesforce, OneDrive for Business, Zendesk, ou WordPress.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 50466c2cf51593a4e34796fdf1d7a285eb63d462
ms.sourcegitcommit: 31b578972f00e6ab2e50ea0b674142199b3b7a35
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54905646"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Crie e teste um fluxo de trabalho de aprovação com o Microsoft Flow

Com o Microsoft Flow, é possível gerenciar a aprovação de documentos ou de processos em vários serviços, inclusive no SharePoint, Dynamics 365, Salesforce, OneDrive para Empresas, Zendesk ou WordPress.

Para criar um fluxo de trabalho de aprovação, adicione a ação **Aprovações - Iniciar uma aprovação** a qualquer fluxo. Depois de adicionar esta ação, o fluxo pode gerenciar a aprovação de documentos ou processos. Por exemplo, você pode criar fluxos de aprovação de documento que aprovam faturas, ordens de trabalho ou cotações de venda. Você também pode criar fluxos de aprovação de processo que aprovam as solicitações de férias, trabalho de horas extras ou planos de viagem.

Os aprovadores podem responder a solicitações de sua caixa de entrada de email, [o centro de aprovações](https://flow.microsoft.com/manage/approvals/received/) no site do Microsoft Flow ou do aplicativo do Microsoft Flow.

## <a name="create-an-approval-flow"></a>Criar um fluxo de aprovação
Aqui está uma visão geral do fluxo que iremos criar e testar:

   ![visão geral do fluxo](./media/modern-approvals/create-flow-overview.png)

O fluxo executa as seguintes etapas:

1. É iniciado quando alguém cria uma solicitação de férias em uma lista do SharePoint Online.
2. Adiciona a solicitação de férias ao centro de aprovação e, em seguida, envia-a por email para o aprovador.
3. Envia um email com a decisão do aprovador para a pessoa que solicitou férias.
4. Atualiza a lista do SharePoint Online com os comentários de decisão do aprovador.

## <a name="prerequisites"></a>Pré-requisitos
Para concluir este passo a passo, você deve ter acesso a:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Crie essas colunas em sua lista do SharePoint Online:

   ![Colunas da lista do SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Anote o nome e a URL da lista do SharePoint Online. Você precisará desses itens mais tarde ao configurar o gatilho **SharePoint – quando um item é criado**.

## <a name="create-your-flow-from-the-blank-template"></a>Crie seu fluxo a partir do modelo em branco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>adicione um gatilho

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

O **Endereço do Site** e o **Nome da Lista** são os itens que você anotou anteriormente neste passo a passo.

![Informações do SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Adicionar uma ação de perfil

1. Selecione **Nova Etapa** e depois selecione **Adicionar uma ação**.
   
    ![nova etapa](./media/modern-approvals/select-sharepoint-add-action.png)
2. Digite **perfil** na caixa de pesquisa **Escolher uma ação** .
   
    ![procurar por perfil](./media/modern-approvals/search-for-profile.png)
3. Localize e selecione a ação **Usuários do Office 365 - Obter meu perfil**.
   
    ![selecione os usuários do Office](./media/modern-approvals/select-my-profile.png)
4. Forneça um nome para o fluxo e, em seguida, selecione **Criar fluxo** para salvar o trabalho que fizemos até agora.
   
    ![salvar fluxo](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Adicionar uma ação de aprovação

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Essa ação envia a solicitação de aprovação ao endereço de email na caixa **Atribuído A**.
>
>

## <a name="add-a-condition"></a>Adicionar uma condição

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Adicionar uma ação de email para aprovações

Siga estas etapas para enviar um email, se a solicitação de férias for aprovada:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar o modelo de email aprovados](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Adicionar uma ação de atualização para solicitações aprovadas

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> Os campos **Endereço do Site**, **Nome da Lista**, **ID** e **Título** são necessários.
>
>

![atualizar configuração de item](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Adicionar uma ação de email para rejeições

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configuração de solicitações rejeitadas](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Adicionar ação de atualização de solicitações rejeitadas

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > Os campos **Endereço do Site**, **Nome da Lista**, **ID** e **Título** são necessários.
   >
   >

![atualizar cartão do item](./media/modern-approvals/configure-update-item-no.png)

1. Selecione **Atualizar fluxo** para salvar o trabalho que fizemos.
   
    ![selecionar atualizar ação](./media/modern-approvals/update.png)

Se você acompanhou até aqui, o fluxo deve se parecer com esta captura de tela:

![visão geral do fluxo](./media/modern-approvals/completed-flow.png)

Agora que criamos o fluxo, é hora de testá-lo!

## <a name="request-an-approval"></a>Solicitar uma aprovação

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

Agora que você criou e testou seu fluxo, informe às outras pessoas sobre como usá-lo.

## <a name="learn-more"></a>Saiba mais

* Exibir e gerenciar as [solicitações de aprovação pendentes](approve-reject-requests.md)
* Crie [fluxos de aprovação sequencial.](sequential-modern-approvals.md)
* Crie [fluxos de aprovação paralela.](parallel-modern-approvals.md)
* Instale o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows).
