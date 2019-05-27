---
title: Solicitações de descoberta de entidade de dados de GDPR do Microsoft Flow | Microsoft Docs
description: Saiba como usar o Microsoft Flow para responder às Solicitações de descoberta de entidade de dados de GPDR.
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
ms.date: 4/17/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 9ec66eefdbf2f6b6a9047678e9c29cb66900eda2
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64454081"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Responder às Solicitações de descoberta de entidade de dados de GDPR do Microsoft Flow

A primeira etapa para responder a um DSR é localizar os dados pessoais que são o assunto da solicitação. A primeira etapa ajuda a determinar se um DSR atende aos requisitos da sua organização para aceitar ou recusar uma solicitação de DSR. Por exemplo, depois de localizar e revisar os dados pessoais em questão, você pode determinar que a solicitação não atende aos requisitos de sua organização, pois isso pode afetar os direitos e a liberdade de outras pessoas.

Veja abaixo um resumo dos tipos de recursos do Microsoft Flow que contêm dados pessoais de um usuário específico.

|**Recursos que contêm dados pessoais**|**Finalidade**|
|-----|-----|
|Logs gerados pelo sistema|Telemetria que captura eventos e histórico do sistema.|
|Histórico de execuções|O histórico de cada execução de fluxo nos últimos 28 dias. Esses dados incluem a hora de início, hora de término, status e todas as informações de entrada/saída do fluxo. [Saiba mais](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Feed de atividades| Fornece uma recapitulação das atividades de fluxo, incluindo status da execução, falhas e notificações.|
|Trabalhos de usuário|Trabalhos do sistema, que não aparecem para o usuário, executados em nome do usuário a fim de executar os fluxos.|
|Fluxos|A lógica de fluxo de trabalho que existe para um fluxo. [Saiba mais](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Permissões do Flow|É possível compartilhar e reatribuir os fluxos a outros usuários. Há listas de permissões para todos os fluxos. [Saiba mais](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Detalhes do usuário|Os detalhes, que não são vistos pelo usuário, que oferecem suporte à execução do fluxo.|
|Conexões|Usados pelos conectores, e permitem a conectividade com APIs, sistemas, bancos de dados etc. [Saiba mais](https://docs.microsoft.com/flow/add-manage-connections)|
|Permissões de conexão|Permissões para uma conexão específica. [Saiba mais](https://docs.microsoft.com/flow/add-manage-connections)|
|Conectores personalizados|Os conectores personalizados criados e publicados por um usuário, que permitem a conectividade com sistemas personalizados ou de terceiros. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/)|
|Permissões do conector personalizado|Lista de permissão para conectores personalizados. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Gateway|Os gateways são serviços de dados locais que podem ser instalados por um usuário para transferir dados rapidamente e com segurança entre o Microsoft Flow e uma fonte de dados que não esteja na nuvem. [Saiba mais](https://docs.microsoft.com/flow/gateway-manage)|
|Permissões de gateway|Os gateways podem ser compartilhados com usuários em uma organização. [Saiba mais](https://go.microsoft.com/fwlink/?linkid=872249)|
