---
title: Microsoft Flow solicitações de descoberta de entidade de dados GDPR para contas da Microsoft (MSA) | Microsoft Docs
description: Saiba como usar Microsoft Flow para responder a solicitações de descoberta de entidades de dados do às GPDR para contas da Microsoft.
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
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 06e88aa215089145f86f9027a6ad75b73c7cf627
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548114"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Responder a solicitações de descoberta de entidade de dados GDPR 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

A primeira etapa para responder a uma solicitação de DSR é encontrar os dados pessoais que são o assunto da solicitação.
Aqui está um resumo dos recursos de Microsoft Flow que contêm dados pessoais para um usuário que se autentica com sua MSA (conta da Microsoft).

|Kit|Objetivo|
|-----|-----|
|Histórico de execuções|Fornece o histórico da execução de cada fluxo nos últimos 28 dias. Esses dados incluem hora de início, hora de término, status e todas as informações de entrada/saída para cada execução de fluxo. Saiba mais sobre o [histórico de execução de fluxo](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Feed de atividades| Fornece uma recapitulação das atividades de cada fluxo, incluindo status de execução, falhas e notificações.|
|Fluxo|A lógica do fluxo de trabalho para um [fluxo](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Conexões|Usado por conectores e permite a conectividade com APIs, sistemas, bancos de dados e muito mais. Saiba mais sobre [conexões](add-manage-connections.md).|

