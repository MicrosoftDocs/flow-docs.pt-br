---
title: Aprovar solicitações em um dispositivo móvel | Microsoft Docs
description: Use um dispositivo móvel para aprovar solicitações criadas no Microsoft Flow.
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
ms.openlocfilehash: a71d1e53199f0dacfc2086812cc3cd2fd9585f4d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548686"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Aprovar solicitações em seu dispositivo móvel usando Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Se um fluxo o identificar como Aprovador e você tiver instalado o aplicativo móvel para Microsoft Flow, você receberá uma notificação por push sempre que sua aprovação for solicitada.

Este artigo orienta você por alguns cenários comuns que você provavelmente encontrará enquanto gerencia solicitações de aprovação no aplicativo móvel para Microsoft Flow.

> [!NOTE]
> As imagens neste tópico são de um dispositivo Android; no entanto, a experiência no iOS é semelhante.
> 
> 

## <a name="prerequisites"></a>Pré-requisitos
Para concluir este passo a passos, você precisa de:

* Um dispositivo [Android](https://aka.ms/flowmobiledocsandroid) ou [Ios](https://aka.ms/flowmobiledocsios) executando o aplicativo móvel para Microsoft Flow.
* A ser designado como Aprovador em um fluxo de aprovação.
* Solicitações pendentes para aprovação.

## <a name="view-pending-requests"></a>Exibir solicitações pendentes
1. Abra o aplicativo móvel para Microsoft Flow.
   
    ![iniciar o aplicativo móvel](./media/mobile-approvals/open-app.png)
2. Selecione **aprovações** no canto superior direito.
   
    ![selecionar aprovações](./media/mobile-approvals/select-approvals.png)
3. Exibir todas as aprovações pendentes:
   
    ![consulte solicitações de aprovação pendentes](./media/mobile-approvals/show-pending-approval-requests.png)

Se você não tiver nenhuma solicitação de aprovação pendente, crie um [fluxo de aprovação](modern-approvals.md), defina-o como um Aprovador e, em seguida, acione o fluxo. As solicitações de aprovação aparecem no centro de aprovação alguns segundos depois que o fluxo é disparado e envia uma solicitação de aprovação.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Aprovar solicitações e deixar um comentário opcional
1. Se você ainda não fez isso, siga as etapas anteriores para [exibir as solicitações pendentes](mobile-approvals.md#view-pending-requests).
2. Selecione **aprovar** na solicitação que você deseja aprovar.
   
    ![Selecione aprovar](./media/mobile-approvals/select-approve.png)
3. (Opcional) selecione **adicionar comentário (opcional)** .
   
    ![selecione Adicionar um comentário](./media/mobile-approvals/select-add-comment.png)
   
    Insira um comentário na tela **adicionar comentário** .
   
    ![Insira seu comentário](./media/mobile-approvals/enter-comment-for-approval.png)
4. Selecione **confirmar** no canto superior direito.
   
    ![Confirme que você terminou](./media/mobile-approvals/tap-confirm-button.png)
   
    A tela êxito é exibida depois que o fluxo registra sua decisão.
   
    ![tela de êxito](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Rejeitar solicitações e deixar um comentário opcional
Siga as [etapas para aprovar uma solicitação](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), mas selecione **rejeitar** na segunda etapa.

## <a name="learn-more"></a>Saiba Mais
[Crie fluxos de aprovação modernos](modern-approvals.md).

