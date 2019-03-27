---
title: Usar as caixas de diálogo do Common Data Service para processos guiados (preterido) | MicrosoftDocs
description: As caixas de diálogo são os processos síncronos ou interativos que coletam e processam informações usando scripts passo a passo para direcionar os usuários por meio de um processo
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
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
ms.openlocfilehash: 90bdbc0ecf9b778ec6da3e4cac2b32b44e361fb0
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58352908"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Usar as caixas de diálogo do Common Data Service para processos guiados (preterido)

[As caixas de diálogo estão preteridas](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Você deve substituir caixas de diálogo por fluxos de processo empresarial ou aplicativos de tela. Mais informações: [Substituir caixas de diálogo por fluxos de processo empresarial ou aplicativos de tela](replace-dialogs.md) 

As caixas de diálogo são os processos síncronos ou interativos no Common Data Service que coletam e processam informações usando scripts passo a passo para direcionar os usuários ao longo de um processo. Por exemplo, você pode criar caixas de diálogo para atuar como um guia para os representantes de serviço para resolução do caso e escalonamento de caso. Da mesma forma, você pode criar caixas de diálogo para padronizar processos de vendas, como qualificação de oportunidades e pontuações de clientes potenciais. Para obter mais informações, consulte [Usar caixas de diálogo para processos guiados](/dynamics365/customer-engagement/developer/use-dialogs-guided-processes) no Guia do desenvolvedor de participação do cliente do Dynamics 365.

## <a name="differences-between-workflows-and-dialogs"></a>Diferenças entre os fluxos de trabalho e as caixas de diálogo

A tabela a seguir fornece informações sobre as diferenças entre os fluxos de trabalho e as caixas de diálogo do Common Data Service.  


| Fluxos de trabalho     |    Caixas de diálogo      |
|---------------|--------------|
|                                                                                                  Podem ser iniciadas por um usuário ou podem ser automatizadas.                                                                                                   |                                                                                          Devem ser iniciadas por um usuário.                                                                                          |
|                                  São processos assíncronos ou em tempo real e não exigem a entrada do usuário para execução até a conclusão. Processos assíncronos são executados em segundo plano enquanto processos em tempo real são executados imediatamente.                                   | São processos em tempo real que exigem a entrada do usuário para execução até a conclusão. Quando você executa esses processos, uma interface de assistente é apresentada a você para que possa fazer as seleções apropriadas para executar os processos. |
|                                                    A entidade que armazena os detalhes sobre um fluxo de trabalho assíncrono em execução é `AsyncOperation` enquanto um `Process` é usado para um fluxo de trabalho em tempo real.                                                     |                                                       A entidade que armazena informações geradas por uma caixa de diálogo em execução é a entidade `ProcessSession`.                                                       |
|                  Há suporte para gatilhos para fluxos de trabalho. Para obter uma lista de gatilhos com suporte, consulte [Tipos, gatilhos e entidades para processos com suporte](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Não há suporte para gatilhos para caixas de diálogo.                                                                                    |
  
### <a name="see-also"></a>Consulte também
[Substituir caixas de diálogo por fluxos de processo empresarial ou aplicativos de tela](replace-dialogs.md)
