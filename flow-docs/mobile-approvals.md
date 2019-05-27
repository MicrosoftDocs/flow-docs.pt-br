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
ms.openlocfilehash: b41397d74c7396081154526ad2e248cb293e2460
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64468168"
---
# <a name="approve-requests-on-your-mobile-device-by-using-microsoft-flow"></a>Aprovar solicitações em seu dispositivo móvel usando o Microsoft Flow
Se um fluxo o identifica como um aprovador e você instalou o aplicativo móvel do Microsoft Flow, receberá uma notificação por push sempre que for solicitada sua aprovação.

Este artigo explica alguns dos cenários comuns que você provavelmente encontrará enquanto gerencia solicitações de aprovação no aplicativo móvel do Microsoft Flow.

> [!NOTE]
> As imagens neste tópico são de um dispositivo Android. No entanto, a experiência do iOS é semelhante.
> 
> 

## <a name="prerequisites"></a>Pré-requisitos
Para concluir este passo a passo, você precisa:

* Um dispositivo [Android](https://aka.ms/flowmobiledocsandroid) ou [iOS](https://aka.ms/flowmobiledocsios) executando o aplicativo móvel do Microsoft Flow.
* Para ser designado como o aprovador em um fluxo de aprovação.
* Solicitações pendentes para aprovação.

## <a name="view-pending-requests"></a>Exibir solicitações pendentes
1. Abra o aplicativo móvel do Microsoft Flow.
   
    ![iniciar o aplicativo móvel](./media/mobile-approvals/open-app.png)
2. Selecione **APROVAÇÕES** no canto superior direito.
   
    ![selecionar aprovações](./media/mobile-approvals/select-approvals.png)
3. Exibir todas as aprovações pendentes:
   
    ![confira as solicitações de aprovação pendentes](./media/mobile-approvals/show-pending-approval-requests.png)

Se você não tiver nenhuma solicitação de aprovação pendente, crie um [fluxo de aprovação](modern-approvals.md), defina você mesmo como um aprovador e então dispare o fluxo. As solicitações de aprovação aparecem no centro de aprovações alguns segundos depois que o fluxo dispara e envia uma solicitação para aprovação.

## <a name="approve-requests-and-leave-an-optional-comment"></a>Aprovar solicitações e deixar um comentário opcional
1. Se você ainda não fez isso, siga as etapas anteriores para [exibir solicitações pendentes](mobile-approvals.md#view-pending-requests).
2. Selecione **APROVAR** na solicitação que você deseja aprovar.
   
    ![selecione aprovar](./media/mobile-approvals/select-approve.png)
3. (Opcional) selecione **Adicionar comentário (opcional)**.
   
    ![selecione adicionar um comentário](./media/mobile-approvals/select-add-comment.png)
   
    Insira um comentário na tela **Adicionar comentário**.
   
    ![insira seu comentário](./media/mobile-approvals/enter-comment-for-approval.png)
4. Selecione **CONFIRMAR** no canto superior direito.
   
    ![confirme quando terminar](./media/mobile-approvals/tap-confirm-button.png)
   
    A tela de sucesso é exibida depois que o fluxo registra sua decisão.
   
    ![tela de sucesso](./media/mobile-approvals/approved.png)

## <a name="reject-requests-and-leave-an-optional-comment"></a>Rejeitar solicitações e deixar um comentário opcional
Siga as [etapas para aprovar uma solicitação](mobile-approvals.md#approve-requests-and-leave-an-optional-comment), mas selecione **REJEITAR** na segunda etapa.

## <a name="learn-more"></a>Saiba mais
[Criar fluxos de aprovação modernos](modern-approvals.md).

