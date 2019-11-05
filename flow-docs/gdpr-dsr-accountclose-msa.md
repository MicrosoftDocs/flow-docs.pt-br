---
title: Microsoft Flow solicitações de fechamento da conta de assunto de dados do GDPR para contas da Microsoft (MSA) | Microsoft Docs
description: Saiba como usar Microsoft Flow para responder a solicitações de fechamento da conta de entidade de dados do às GPDR para contas da Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 8665148baf4d752f1f384670b296a66bbfca6163
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548014"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Respondendo a solicitações de fechamento da conta de entidade de dados do GDPR para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O **direito de apagamento** de dados pessoais é uma proteção de chave no GDPR. Esse direito inclui a remoção de todos os dados pessoais, exceto as informações do log de auditoria. Quando os usuários decidem fechar sua conta da Microsoft (MSA), os dados subjacentes do usuário também são excluídos.

Esses recursos contêm dados pessoais que são excluídos automaticamente quando um usuário fecha um MSA:

|Recursos que contêm dados pessoais|
|------|
|Atividade de produto e serviço|
|Histórico de execuções|
|Fluxo|
|Feed de atividades|
|Detalhes do usuário|
|Conexões|

## <a name="account-close-requests"></a>Solicitações de fechamento de conta

Estas etapas descrevem como autoatendimento de solicitações de fechamento de conta para GDPR.

1. Entre no [portal de fechamento da conta da Microsoft](https://go.microsoft.com/fwlink/?LinkId=523898) usando sua conta da Microsoft e, em seguida, selecione **Avançar**.

    > [!NOTE]
    > Você está lembrado de cancelar assinaturas existentes ou de exportar dados de serviços existentes para os quais você pode ter assinado.
    >
    >

    ![Cancelar assinaturas](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Confirme que você entendeu o impacto de fechar o MSA e, em seguida, selecione **Marcar conta para encerramento**.

    Uma notificação é exibida, indicando que sua conta será fechada em 30 dias. Você pode reabrir essa conta a qualquer momento durante este período de 30 dias.

    ![Conta fechada](./media/gdpr-dsr-delete-msa/accountclosed.png)

    No final deste período de 30 dias, o processo para excluir todos os Microsoft Flow recursos para esse MSA começa.

## <a name="learn-more"></a>Saiba Mais

* Introdução ao [Microsoft Flow](getting-started.md)
* Saiba [o que há de novo com o](release-notes.md) Microsoft Flow
