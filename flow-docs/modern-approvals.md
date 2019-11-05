---
title: Automatize facilmente os fluxos de trabalho de aprovação. | Microsoft Docs
description: Automatize fluxos de trabalho de aprovação que se integram ao SharePoint, Dynamics CRM, Salesforce, OneDrive for Business, zendesk ou WordPress.
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
ms.openlocfilehash: c46ac3dc65b6e1a3970bd0b9b4ef17df5bef16f8
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548710"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Criar e testar um fluxo de trabalho de aprovação com Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Com o Microsoft Flow, você pode gerenciar a aprovação de documentos ou processos em vários serviços, incluindo SharePoint, Dynamics 365, Salesforce, OneDrive for Business, zendesk ou WordPress.

Para criar um fluxo de trabalho de aprovação, adicione a ação **aprovações-iniciar uma aprovação** para qualquer fluxo. Depois de adicionar essa ação, o fluxo pode gerenciar a aprovação de documentos ou processos. Por exemplo, você pode criar fluxos de aprovação de documento que aprovem faturas, ordens de trabalho ou Cotações de venda. Você também pode criar fluxos de aprovação de processo que aprovem solicitações de férias, trabalho de horas extras ou planos de viagem.

Os aprovadores podem responder a solicitações de sua caixa de entrada de email, [do centro de aprovações](https://flow.microsoft.com/manage/approvals/received/) no site Microsoft Flow ou do aplicativo Microsoft Flow.

## <a name="create-an-approval-flow"></a>Criar um fluxo de aprovação
Aqui está uma visão geral do fluxo que criaremos e testaremos:

   ![Visão geral do Flow](./media/modern-approvals/create-flow-overview.png)

O fluxo executa as seguintes etapas:

1. Inicia quando alguém cria uma solicitação de férias em uma lista do SharePoint Online.
2. Adiciona a solicitação de férias ao centro de aprovação e, em seguida, envia-o por email para o aprovador.
3. Envia um email com a decisão do aprovador para a pessoa que solicitou férias.
4. Atualiza a lista do SharePoint Online com os comentários de decisão do aprovador.

## <a name="prerequisites"></a>Pré-requisitos
Para concluir este passo a passos, você deve ter acesso a:

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Crie essas colunas na sua lista do SharePoint Online:

   ![Colunas de lista do SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Anote o nome e a URL da lista do SharePoint Online. Você precisará desses itens mais tarde ao configurar o gatilho **SharePoint-quando um item é criado** .

## <a name="create-your-flow-from-the-blank-template"></a>Criar seu fluxo a partir do modelo em branco
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Adicionar um gatilho

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

O **endereço do site** e o **nome da lista** são os itens que você anotou anteriormente neste passo a passos.

![Informações do SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Adicionar uma ação de perfil

1. Selecione **nova etapa**e, em seguida, selecione **Adicionar uma ação**.
   
    ![Nova etapa](./media/modern-approvals/select-sharepoint-add-action.png)
2. Insira o **perfil** na caixa de pesquisa **escolher uma ação** .
   
    ![Pesquisar perfil](./media/modern-approvals/search-for-profile.png)
3. Localize e selecione a ação **usuários do Office 365 – obter meu perfil** .
   
    ![Selecionar usuários do Office](./media/modern-approvals/select-my-profile.png)
4. Forneça um nome para o fluxo e, em seguida, selecione **criar fluxo** para salvar o trabalho que fizemos até agora.
   
    ![salvar fluxo](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Adicionar uma ação de aprovação

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Essa ação envia a solicitação de aprovação para o endereço de email na caixa **atribuído a** .
>
>

## <a name="add-a-condition"></a>Adicionar uma condição

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Adicionar uma ação de email para aprovações

Siga estas etapas para enviar um email se a solicitação de férias for aprovada:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar modelo de email aprovado](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Adicionar uma ação de atualização para solicitações aprovadas

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> O **endereço do site**, o nome da **lista**, a **ID**e o **título** são obrigatórios.
>
>

![atualizar configuração do item](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Adicionar uma ação de email para rejeições

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configuração para solicitações rejeitadas](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Adicionar ação de atualização para solicitações rejeitadas

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > O **endereço do site**, o nome da **lista**, a **ID**e o **título** são obrigatórios.
   >
   >

![atualizar cartão de item](./media/modern-approvals/configure-update-item-no.png)

1. Selecione **Atualizar fluxo** para salvar o trabalho que fizemos.
   
    ![Selecionar ação de atualização](./media/modern-approvals/update.png)

Se você seguiu, seu fluxo deve ser semelhante a esta captura de tela:

![Visão geral do Flow](./media/modern-approvals/completed-flow.png)

Agora que criamos o fluxo, é hora de testá-lo!

## <a name="request-an-approval"></a>Solicitar uma aprovação

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>Criar aprovações de execução longa

Se for provável que o fluxo seja executado por mais de 30 dias, considere armazenar suas aprovações em Common Data Service. Isso possibilita que você crie fluxos que agem em respostas a solicitações de aprovação, mesmo após a execução do fluxo original atingir o tempo limite. Para fazer isso, use dois fluxos, um para enviar uma solicitação de aprovação e o outro para executar a lógica de negócios nas respostas para a solicitação de aprovação, com base na ação **criar uma aprovação (v2)** . Saiba mais sobre [aprovações de execução longa](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/long-lived-approvals-other-approval-improvements).

>[!TIP]
> Se você usar clientes de email modernos, não precisará se perguntar se uma solicitação ainda é necessária porque Microsoft Flow atualiza o email automaticamente para indicar que a aprovação foi concluída.

## <a name="cancel-an-approval-requests"></a>Cancelar solicitações de aprovação

Às vezes, você pode querer cancelar uma solicitação de aprovação que você enviou. Possivelmente, você cometeu um erro na solicitação ou não é mais relevante. Em ambos os casos, a pessoa que enviou a solicitação pode cancelá-la seguindo estas etapas:

1. Selecione a aprovação
1. Selecione **Cancelar aprovação** no painel lateral.

>[!TIP]
>Você sempre pode selecionar a guia **histórico** para exibir as solicitações de aprovação que você cancelou.

>[!NOTE]
> O recurso de cancelamento tem suporte na ação **criar uma aprovação (v2)** .

## <a name="request-approvals-from-guest-users"></a>Solicitar aprovações de usuários convidados

Você pode enviar solicitações de aprovações para pessoas fora da sua organização. Para fazer isso, use os usuários convidados do Azure Active Directory (Azure AD) [convidando usuários de outros locatários como convidados](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite).

Quando você atribui uma função a um convidado, isso dá ao convidado a permissão necessária para participar do processo de aprovação.

Agora que você criou e testou seu fluxo, lembre-se de deixar que outras pessoas saibam como usá-lo.

## <a name="learn-more"></a>Saiba Mais

* Exibir e gerenciar [solicitações de aprovação pendentes](approve-reject-requests.md)
* Criar [fluxos de aprovação sequencial.](sequential-modern-approvals.md)
* Criar [fluxos de aprovação paralela.](parallel-modern-approvals.md)
* Instale o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [Ios](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).
