---
title: Microsoft Flow solicitações de exclusão de entidade de dados GDPR para contas da Microsoft (MSA) | Microsoft Docs
description: Saiba como usar Microsoft Flow para responder a solicitações de exclusão de entidades de dados do às GPDR para contas da Microsoft.
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
ms.openlocfilehash: 379c88842b9724c7bdb6adfed79e2bb11497694d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548054"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Responder a solicitações de exclusão de entidade de dados GDPR
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O **direito de apagamento** pela remoção de dados pessoais é uma proteção de chave no GDPR. A remoção de dados pessoais inclui a remoção de todos os dados pessoais, exceto informações do log de auditoria.

Microsoft Flow permite que os usuários criem fluxos de trabalho automatizados. Quando um usuário decide excluir seus dados pessoais do Microsoft Flow, o usuário pode revisar seus dados pessoais e determinar se deseja excluir alguns ou todos eles.

A tabela a seguir mostra quais dados pessoais são excluídos automaticamente e quais dados exigem um usuário da conta da Microsoft (MSA) para revisá-los e excluí-los.

|Requer que o usuário do MSA revise e exclua|Excluído automaticamente|
|------|------|
|Atividade de produto e serviço|Histórico de execuções|
|Fluxo|Feed de atividades|
|Conexões||

O Microsoft Flow oferece as seguintes experiências para ajudar os usuários a localizar, examinar ou alterar dados pessoais e recursos que não são excluídos automaticamente:

## <a name="manage-delete-requests"></a>Gerenciar solicitações de exclusão

As etapas a seguir descrevem como autoatendimento de solicitações de exclusão para GDPR.

### <a name="delete-product-and-service-activity"></a>Excluir atividade de produto e serviço

1. Entre no [painel de privacidade da Microsoft](https://account.microsoft.com/privacy/) com seu MSA.
1. Selecione o link **histórico de atividade** .

    ![Histórico de atividades](./media/gdpr-dsr-export-msa/activityhistory.png)

1. Você pode pesquisar ou procurar o histórico de atividades para os diferentes aplicativos e serviços da Microsoft que você usa, incluindo Microsoft Flow. Selecione **excluir** para remover eventos específicos de atividade de serviço ou produto.

    ![Excluir evento](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Em alguns instantes, o item é excluído e removido do painel de privacidade.

### <a name="list-and-delete-flows"></a>Listar e excluir fluxos

Um usuário pode listar e excluir seus fluxos de [Microsoft Flow](https://flow.microsoft.com) seguintes estas etapas:

1. Entre no [Microsoft Flow](https://flow.microsoft.com)e, em seguida, selecione em **meus fluxos**.

1. Selecione **...** ao lado do fluxo que você está excluindo e, em seguida, selecione **excluir**.

    ![Excluir evento](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Excluir conexões

Os conectores usam conexões para se comunicar com APIs e sistemas SaaS. As conexões incluem referências ao usuário que as cria. O usuário pode excluir essas referências a qualquer momento, seguintes estas etapas:

1. Entre [Microsoft Flow](https://flow.microsoft.com), selecione o ícone de engrenagem e, em seguida, selecione **conexões**.

    ![Excluir evento](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Selecione a conexão que você deseja excluir, selecione **...** e, em seguida, selecione **excluir**.

    ![Excluir evento](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Selecione o ícone **excluir** no prompt de confirmação.

    ![Excluir evento](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Se outros fluxos usam a conexão, você está excluindo, você é notificado de que uma nova conexão é necessária. Caso contrário, selecione **excluir** para continuar.
>
>

## <a name="learn-more"></a>Saiba Mais

* Introdução ao [Microsoft Flow](getting-started.md)
* Saiba [o que há de novo com o](release-notes.md) Microsoft Flow
