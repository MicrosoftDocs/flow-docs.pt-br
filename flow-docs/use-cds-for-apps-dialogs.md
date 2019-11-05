---
title: Usar caixas de diálogo de Common Data Service para processos guiados (preterido) | MicrosoftDocs
description: Caixas de diálogo são processos síncronos ou interativos que coletam e processam informações usando scripts passo a passo para direcionar os usuários por meio de um processo
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.service: flow
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 05f0b9b72f2f9e2d7f02356ec40eeb520214a0cb
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548757"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Usar caixas de diálogo de Common Data Service para processos guiados (preterido)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

As [caixas de diálogo são preteridas](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Você deve substituir caixas de diálogo por fluxos de processo de negócios ou aplicativos de tela. Mais informações: [substituir caixas de diálogo por fluxos de processo de negócios ou aplicativos de tela](replace-dialogs.md) 

As caixas de diálogo são processos síncronos ou interativos no Common Data Service que coletam e processam informações usando scripts passo a passo para direcionar os usuários por meio de um processo. Por exemplo, você pode criar caixas de diálogo para atuar como um guia para seus representantes de serviço para resolução de caso e escalonamento de caso. Da mesma forma, você pode criar caixas de diálogo para padronizar processos de vendas, como qualificação de oportunidades e pontuação de Lead.

## <a name="differences-between-workflows-and-dialogs"></a>Diferenças entre fluxos de trabalho e caixas de diálogo

A tabela a seguir fornece informações sobre as diferenças entre Common Data Service fluxos de trabalho e caixas de diálogo.  


| fluxos     |    Caixas      |
|---------------|--------------|
|                                                                                                  Pode ser iniciado por um usuário ou pode ser automatizado.                                                                                                   |                                                                                          Deve ser iniciado por um usuário.                                                                                          |
|                                  São processos assíncronos ou em tempo real e não exigem que a entrada do usuário seja executada até a conclusão. Processos assíncronos são executados em segundo plano enquanto os processos em tempo real são executados imediatamente.                                   | São processos em tempo real que exigem que a entrada do usuário seja executada até a conclusão. Quando você executa esses processos, uma interface do tipo assistente é apresentada a você para que você possa fazer seleções apropriadas para executar os processos. |
|                                                    A entidade que armazena os detalhes sobre um fluxo de trabalho assíncrono em execução é `AsyncOperation` enquanto um `Process` é usado para um fluxo de trabalho em tempo real.                                                     |                                                       A entidade que armazena as informações geradas por uma caixa de diálogo em execução é a `ProcessSession` entidade.                                                       |
|                  Há suporte para gatilhos para fluxos de trabalho. Para obter uma lista de gatilhos com suporte, consulte [tipos com suporte, gatilhos e entidades para processos](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Não há suporte para gatilhos para caixas de diálogo.                                                                                    |
  
### <a name="see-also"></a>Consulte também
[Substituir caixas de diálogo por fluxos de processo de negócios ou aplicativos de tela](replace-dialogs.md)
