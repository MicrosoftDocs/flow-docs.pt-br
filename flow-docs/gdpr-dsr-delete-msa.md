---
title: Solicitações de exclusão de titular dos dados do RGPD do Microsoft Flow para contas da Microsoft (MSA) | Microsoft Docs
description: Saiba como usar o Microsoft Flow para responder às solicitações de exclusão de titular dos dados do RGPD para contas da Microsoft.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e42da775d5c004bfbe0d6bb8923e6d05aaa5e976
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64454208"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Responder às solicitações de exclusão de titular dos dados do RGPD

O **direito de apagar** por meio da remoção de dados pessoais é uma proteção importante no RGPD. A remoção de dados pessoais inclui a remoção de todos os dados pessoais, com exceção das informações de log de auditoria.

O Microsoft Flow permite que os usuários criem fluxos de trabalho automatizados. Quando um usuário decide excluir seus dados pessoais do Microsoft Flow, ele pode examinar seus dados pessoais e determinar se deseja excluir apenas alguns ou todos eles.

A tabela a seguir mostra quais dados pessoais são excluídos automaticamente e quais dados precisam ser examinados e excluídos por um usuário de conta da Microsoft (MSA).

|Precisam ser examinados e excluídos por um usuário de MSA.|Excluídos automaticamente|
|------|------|
|Atividade de produtos e serviços|Histórico de execuções|
|Fluxos|Feed de Atividades|
|Conexões||

O Microsoft Flow oferece as seguintes experiências para ajudar os usuários a localizar, examinar ou alterar dados e recursos pessoais que não são excluídos automaticamente:

## <a name="manage-delete-requests"></a>Gerenciar solicitações de exclusão

As etapas a seguir descrevem como fazer o autoatendimento de solicitações de exclusão relacionadas ao RGPD.

### <a name="delete-product-and-service-activity"></a>Excluir a atividade de produtos e serviços

1. Entre no [Painel de privacidade da Microsoft](https://account.microsoft.com/privacy/) com sua MSA.
1. Selecione o link **Histórico de atividades**.

    ![Histórico de atividades](./media/gdpr-dsr-export-msa/activityhistory.png)

1. É possível pesquisar ou procurar o histórico de atividades dos diferentes aplicativos e serviços da Microsoft que você usa, incluindo o Microsoft Flow. Selecione **Excluir** para remover os eventos de atividade de produtos ou serviços.

    ![Excluir o evento](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Em alguns instantes, o item é excluído e removido do painel de privacidade.

### <a name="list-and-delete-flows"></a>Listar e excluir fluxos

Um usuário pode listar e excluir seus fluxos do [Microsoft Flow](https://flow.microsoft.com) seguindo estas etapas:

1. Entre no [Microsoft Flow](https://flow.microsoft.com) e, em seguida, selecione **Meus fluxos**.

1. Selecione **...** ao lado do fluxo que você está excluindo e, em seguida, selecione **Excluir**.

    ![Excluir o evento](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Excluir conexões

Os conectores usam conexões para comunicar-se com APIs e sistemas de SaaS. As conexões incluem referências ao usuário que as cria. O usuário pode excluir essas referências a qualquer momento seguindo estas etapas:

1. Entre no [Microsoft Flow](https://flow.microsoft.com), selecione o ícone de engrenagem e, em seguida, selecione **Conexões**.

    ![Excluir o evento](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Selecione a conexão que você deseja excluir, selecione **...** e, em seguida, selecione **Excluir**.

    ![Excluir o evento](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Selecione o ícone **Excluir** no prompt de confirmação.

    ![Excluir o evento](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Se outros fluxos usam a conexão que você está excluindo, haverá uma notificação de que uma nova conexão é necessária. Caso contrário, selecione **Excluir** para continuar.
>
>

## <a name="learn-more"></a>Saiba mais

* Introdução ao [Microsoft Flow](getting-started.md)
* Conheça as [novidades](release-notes.md) do Microsoft Flow
