---
title: Solicitações de encerramento de conta do titular dos dados do RGPD do Microsoft Flow para contas da Microsoft (MSA) | Microsoft Docs
description: Saiba como usar o Microsoft Flow para responder às solicitações de encerramento de conta do titular dos dados do RGPD para contas da Microsoft.
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
ms.openlocfilehash: 6480fe6a7e6ca26a7dbad3952b6608a9e0a880ae
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035082"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Respondendo às solicitações de encerramento de conta do titular dos dados do RGPD do Microsoft Flow

O **direito de apagar** dados pessoais é uma proteção importante no RGPD. Esse direito inclui a remoção de todos os dados pessoais, com exceção das informações de log de auditoria. Quando um usuário decide encerrar a respectiva conta Microsoft, os dados subjacentes desse usuário também são excluídos.

Esses recursos contêm dados pessoais que são excluídos automaticamente quando um usuário encerra uma MSA:

|Recursos que contêm dados pessoais|
|------|
|Atividade de produtos e serviços|
|Histórico de execuções|
|Fluxos|
|Feed de Atividades|
|Detalhes do usuário|
|Conexões|

## <a name="account-close-requests"></a>Solicitações de encerramento de conta

Estas etapas descrevem como fazer o autoatendimento de solicitações de encerramento de conta relacionadas ao RGPD.

1. Entre no [Portal de Encerramento de conta da Microsoft](http://go.microsoft.com/fwlink/?LinkId=523898) usando sua conta da Microsoft e, em seguida, selecione **Avançar**.

    > [!NOTE]
    > Você será lembrado de cancelar as assinaturas existentes ou de exportar dados dos serviços existentes aos quais você esteja inscrito.
    >
    >

    ![Cancelar assinaturas](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Confirme se você entendeu o impacto de encerrar sua MSA e, em seguida, selecione **Marcar conta para encerramento**.

    Uma notificação será exibida, indicando que sua conta será encerrada em 30 dias. Você poderá reabrir essa conta a qualquer momento durante esse período de 30 dias.

    ![Conta encerrada](./media/gdpr-dsr-delete-msa/accountclosed.png)

    No final desse período de 30 dias, será iniciado o processo para excluir todos os recursos do Microsoft Flow dessa MSA.

## <a name="learn-more"></a>Saiba mais

* Introdução ao [Microsoft Flow](getting-started.md)
* Conheça as [novidades](release-notes.md) do Microsoft Flow
