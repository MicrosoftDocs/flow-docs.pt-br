---
title: Microsoft Flow descoberta de solicitações de entidades de dados do GDPR | Microsoft Docs
description: Saiba como usar Microsoft Flow para responder a solicitações de descoberta de entidades de dados do às GPDR.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 197d9ebfc38fc4f5b52bf674aef61d419530f439
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548115"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Respondendo a solicitações de descoberta de entidade de dados GDPR para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

A primeira etapa para responder a um DSR é encontrar dados pessoais que sejam o assunto da solicitação. Essa primeira etapa ajuda a determinar se um DSR atende aos requisitos da sua organização para respeitar ou recusar uma solicitação de DSR. Por exemplo, depois de localizar e revisar os dados pessoais em questão, você pode determinar que a solicitação não atende aos requisitos da sua organização, pois isso pode afetar negativamente os direitos e as liberdades de outras pessoas.

Veja abaixo um resumo dos tipos de Microsoft Flow recursos que contêm dados pessoais para um usuário específico.

|**Recursos que contêm dados pessoais**|**Objetivo**|
|-----|-----|
|Logs gerados pelo sistema|Telemetria que captura eventos e histórico do sistema.|
|Histórico de execuções|O histórico de cada execução de fluxo dos últimos 28 dias. Esses dados incluem a hora de início, a hora de término, o status e todas as informações de entrada/saída para o fluxo. [Saiba Mais](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Feed de atividades| Fornece uma recapitulação de atividades de fluxo, incluindo status de execução, falhas e notificações.|
|Trabalhos do usuário|Não visto para o usuário, trabalhos do sistema que são executados em nome de um usuário para que os fluxos sejam executados.|
|Fluxo|A lógica de fluxo de trabalho que existe para um fluxo. [Saiba Mais](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Permissões de fluxo|Os fluxos podem ser compartilhados e atribuídos novamente a outros usuários. Existem listas de permissões para todos os fluxos. [Saiba Mais](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Detalhes do usuário|Detalhes, que não são vistos pelo usuário, que dão suporte à execução de fluxo.|
|Conexões|Usado por conectores e permite a conectividade com APIs, sistemas, bancos de dados, etc. [Saiba Mais](https://docs.microsoft.com/flow/add-manage-connections)|
|Permissões de conexão|Permissões para uma conexão específica. [Saiba Mais](https://docs.microsoft.com/flow/add-manage-connections)|
|Conectores personalizados|Conectores personalizados que um usuário criou e publicou que permitem a conectividade com sistemas personalizados ou de terceiros. [Saiba Mais](https://docs.microsoft.com/connectors/custom-connectors/)|
|Permissões de conector personalizado|Listas de permissões para conectores personalizados. [Saiba Mais](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|Os gateways são serviços de dados locais que podem ser instalados por um usuário para transferir dados de forma rápida e segura entre Microsoft Flow e uma fonte de dados que não está na nuvem. [Saiba Mais](https://docs.microsoft.com/flow/gateway-manage)|
|Permissões de gateway|Os gateways podem ser compartilhados com usuários em uma organização. [Saiba Mais](https://go.microsoft.com/fwlink/?linkid=872249)|
