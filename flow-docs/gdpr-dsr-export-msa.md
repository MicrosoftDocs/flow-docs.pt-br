---
title: Solicitações de exportação de titular dos dados do RGPD do Microsoft Flow para contas da Microsoft (MSA) | Microsoft Docs
description: Saiba como usar o Microsoft Flow para responder às solicitações de exportação de titular dos dados do RGPD para contas da Microsoft.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
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
ms.openlocfilehash: 6f181a66453573c2f636cbe5130b7fc003a3b151
ms.sourcegitcommit: 5b27ac91b56078e91f45f993f1967731d14af92b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2019
ms.locfileid: "65035026"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Responder às solicitações de exportação de entidade de dados de GDPR do Microsoft Flow

Como parte do nosso comprometimento em firmar uma parceria com você em sua jornada rumo ao GDPR (Regulamento Geral sobre a Proteção de Dados), desenvolvemos uma documentação para ajudar em sua preparação. A documentação não apenas descreve o que estamos fazendo para nos prepararmos para o GDPR, mas também compartilha exemplos de etapas que você pode executar hoje com a Microsoft para estar em conformidade com o GDPR usando o Microsoft Flow.

## <a name="manage-export-requests"></a>Gerenciar solicitações de exportação

O *direito de portabilidade de dados* permite ao titular dos dados solicitar uma cópia dos respectivos dados pessoais em formato eletrônico (que é um "formato estruturado, normalmente usado, legível por máquina e interoperável"), que podem ser transmitidos para outro controlador de dados.

Use o [Painel de privacidade da Microsoft](https://account.microsoft.com/privacy/) ou o [Microsoft Flow](https://flow.microsoft.com/) para encontrar ou exportar dados pessoais de um usuário específico.

|Dados pessoais|Local|
|-----------------|-------------------|
|Atividade de produtos e serviços|Painel de privacidade da Microsoft|
|Fluxos|Portal para criadores do Microsoft Flow|
|Histórico de execuções|Portal para criadores do Microsoft Flow|
|Feed de Atividades|Portal para criadores do Microsoft Flow|
|Conexões|Portal para criadores do Microsoft Flow|

## <a name="export-product-and-service-activity"></a>Exportar atividade de produtos e serviços

1. Entre no [Painel de privacidade da Microsoft](https://account.microsoft.com/privacy/) usando sua conta da Microsoft (MSA).
1. Selecione **Histórico de atividades**.

    ![Histórico de Atividades](./media/gdpr-dsr-export-msa/activityhistory.png) É possível procurar o histórico de atividades dos diferentes aplicativos e serviços da Microsoft que você usa.
1. Para exportar os dados de **Atividade de produtos e serviços**, selecione **Baixar seus dados** e, em seguida, selecione **CRIAR NOVO ARQUIVO MORTO**.

    ![Baixar seus dados](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Selecione **Uso de aplicativos e serviços** e, em seguida, selecione **Criar arquivo morto**.

    ![Baixar seus dados](./media/gdpr-dsr-export-msa/create-archive.png)
1. Um novo arquivo morto é criado. Selecione **Baixar** para obter seus dados de atividades de produtos e serviços.

    ![Baixar](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Exportar um fluxo

Um usuário final que tenha acesso a um fluxo, poderá exportar o fluxo seguindo estas etapas:

1. Entre no [Microsoft Flow](https://flow.microsoft.com/).

1. Selecione **Meus fluxos** e, em seguida, selecione o fluxo a ser exportado.

1. Selecione **... Mais** e, em seguida, selecione **Exportar**.

    ![Exportar fluxo](./media/gdpr-dsr-export/export-flow.png)

1. Selecione o **Pacote (.zip)**.

Seu fluxo não estará disponível como um pacote compactado. Para saber mais, veja a postagem do blog sobre [como exportar e importar um fluxo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportar histórico de execução

O histórico de execução inclui uma lista de todas as execuções de um fluxo. Esses dados incluem o status do fluxo, a hora de início, a duração e os dados de entrada/saída para gatilhos e ações.

Um usuário final que tenha acesso ao fluxo poderá seguir estas etapas para exportar esses dados:

1. Entre no [Microsoft Flow](https://flow.microsoft.com/).
1. Selecione o link **Meus fluxos** e, depois, selecione o fluxo para o qual você deseja exportar o histórico de execuções.
1. No painel **HISTÓRICO DE EXECUÇÕES**, selecione **Ver todas**.

    ![Histórico de execuções](./media/gdpr-dsr-export/run-history.png)

1. Selecione **Baixar CSV**.

    ![Baixar CSV](./media/gdpr-dsr-export/download-csv.png)

O histórico de execução é baixado como um arquivo.csv para que possa ser aberto no Microsoft Excel ou em um editor de texto para análise dos resultados.

## <a name="export-a-users-activity-feed"></a>Exportar um feed de atividades do usuário

No [Microsoft Flow](https://flow.microsoft.com/), o feed de atividades mostra o histórico de atividades, falhas e notificações de um usuário. Os usuários podem exibir os próprios feeds de atividades executando estas etapas:

1. Entre no [Microsoft Flow](http://flow.microsoft.com/), selecione o ícone de sino no canto superior direito e selecione **Mostrar todas as atividades**.

    ![Mostrar feed de atividades](./media/gdpr-dsr-export/show-activity-feed.png)

1. Na tela **Atividade**, copie os resultados e cole-os em um editor de texto, como o Microsoft Word.

    ![Mostrar feed de atividades](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportar as conexões de um usuário

As conexões permitem que os fluxos se conectem a APIs, aplicativos SaaS e outros sistemas de terceiros. Execute estas etapas para exibir suas conexões:

1. Entre no [Microsoft Flow](http://flow.microsoft.com/), selecione o ícone de engrenagem no canto superior direito e selecione **Conexões**.

    ![Mostrar Conexões](./media/gdpr-dsr-export/show-connections.png)
1. Copie os resultados e cole-os em um editor de texto, como o Microsoft Word.
