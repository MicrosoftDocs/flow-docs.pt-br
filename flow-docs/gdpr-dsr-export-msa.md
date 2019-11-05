---
title: Microsoft Flow solicitações de exportação de entidade de dados GDPR para contas da Microsoft (MSA) | Microsoft Docs
description: Saiba como usar Microsoft Flow para responder a solicitações de exportação de entidade de dados às GPDR para contas da Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: Deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 253d6785228fb28b5c78d0cae629a237a2e176da
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548146"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Respondendo a solicitações de exportação de entidade de dados GDPR para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Como parte do nosso compromisso de fazer parceria com você em sua jornada com o Regulamento Geral sobre a Proteção de Dados (GDPR), desenvolvemos a documentação para ajudá-lo a se preparar. A documentação não apenas descreve o que estamos fazendo para se preparar para o GDPR, mas também compartilha exemplos de etapas que você pode adotar hoje com a Microsoft para dar suporte à conformidade com o GDPR ao usar o Microsoft Flow.

## <a name="manage-export-requests"></a>Gerenciar solicitações de exportação

O *direito de portabilidade de dados* permite que entidades de dados solicitem uma cópia de seus dados pessoais em um formato eletrônico (que é um "formato estruturado, comumente usado, legível por computador e interoperável") que pode ser transmitido para outro controlador de dados.

Use o [painel de privacidade da Microsoft](https://account.microsoft.com/privacy/)ou [Microsoft Flow](https://flow.microsoft.com/) para localizar ou exportar dados pessoais para um usuário específico.

|Dados pessoais|Local|
|-----------------|-------------------|
|Atividade de produto e serviço|Painel de privacidade da Microsoft|
|Fluxo|Portal do Microsoft Flow Maker|
|Histórico de execuções|Portal do Microsoft Flow Maker|
|Feed de atividades|Portal do Microsoft Flow Maker|
|Conexões|Portal do Microsoft Flow Maker|

## <a name="export-product-and-service-activity"></a>Exportar atividade de produto e serviço

1. Entre no [painel de privacidade da Microsoft](https://account.microsoft.com/privacy/) usando sua conta da Microsoft (MSA).
1. Selecione **histórico de atividade**.

    ![histórico de atividades](./media/gdpr-dsr-export-msa/activityhistory.png) você pode procurar o histórico de atividades para os diferentes aplicativos e serviços da Microsoft que você usa.
1. Para exportar dados de **atividade de produtos e serviços** , selecione **baixar seus dados**e, em seguida, selecione **criar novo arquivo**.

    ![Baixar seus dados](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Selecione **aplicativo & uso do serviço**e, em seguida, selecione **criar arquivo**.

    ![Baixar seus dados](./media/gdpr-dsr-export-msa/create-archive.png)
1. Um novo arquivo é criado. Selecione **baixar** para obter seus dados de atividade de serviço e produto exportados.

    ![Baixar](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Exportar um fluxo

Um usuário final que tem acesso a um fluxo pode exportar o fluxo seguindo estas etapas:

1. Entre [Microsoft Flow](https://flow.microsoft.com/).

1. Selecione os **meus fluxos**e, em seguida, selecione o fluxo a ser exportado.

1. Selecionar **... Mais**e, em seguida, selecione **Exportar**.

    ![Fluxo de exportação](./media/gdpr-dsr-export/export-flow.png)

1. Selecione **pacote (. zip)** .

Seu fluxo agora estará disponível como um pacote compactado. Para obter mais informações, consulte a postagem no blog sobre [como exportar e importar um fluxo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportar histórico de execução

O histórico de execuções inclui uma lista de todas as execuções para um fluxo. Esses dados incluem o status do fluxo, a hora de início, a duração e os dados de entrada/saída para gatilhos e ações.

Um usuário final que tem acesso ao fluxo pode seguir estas etapas para exportar esses dados:

1. Entre [Microsoft Flow](https://flow.microsoft.com/).
1. Selecione o link **meus fluxos** e, em seguida, selecione o fluxo para o qual você deseja exportar o histórico de execução.
1. No painel **histórico de execuções** , selecione **ver tudo**.

    ![Histórico de execuções](./media/gdpr-dsr-export/run-history.png)

1. Selecione **baixar CSV**.

    ![Baixar CSV](./media/gdpr-dsr-export/download-csv.png)

O histórico de execuções é baixado como um arquivo. csv para que você possa abri-lo no Microsoft Excel ou em um editor de texto para analisar os resultados.

## <a name="export-a-users-activity-feed"></a>Exportar o feed de atividades de um usuário

No [Microsoft Flow](https://flow.microsoft.com/), o feed de atividades mostra o histórico de atividades, falhas e notificações de um usuário. Os usuários podem exibir seu feed de atividades seguindo estas etapas:

1. Entre [Microsoft Flow](https://flow.microsoft.com/), selecione o ícone de sino próximo ao canto superior direito e, em seguida, selecione **Mostrar todas as atividades**.

    ![Mostrar feed de atividade](./media/gdpr-dsr-export/show-activity-feed.png)

1. Na tela **atividade** , copie os resultados e cole-os em um editor de texto como o Microsoft Word.

    ![Mostrar feed de atividade](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportar as conexões de um usuário

As conexões permitem que os fluxos se conectem a APIs, aplicativos SaaS e outros sistemas de terceiros. Siga estas etapas para exibir suas conexões:

1. Entre [Microsoft Flow](https://flow.microsoft.com/), selecione o ícone de engrenagem próximo ao canto superior direito e, em seguida, selecione **conexões**.

    ![Mostrar conexões](./media/gdpr-dsr-export/show-connections.png)
1. Copie os resultados e cole-os em um editor de texto como o Microsoft Word.
