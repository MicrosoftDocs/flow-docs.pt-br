---
title: Práticas recomendadas para o gerenciamento de processos de fluxo de trabalho | MicrosoftDocs
description: Entender as maneiras recomendadas de usar fluxos de trabalho
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ad9935b171568b62376232f450a62dbda4752cac
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546028"
---
# <a name="best-practices-for-workflow-processes"></a>Práticas recomendadas para processos de fluxo de trabalho
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este tópico contém as práticas recomendadas para criar e gerenciar processos de fluxo de trabalho.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Evitar loops infinitos  
 É possível criar lógica em um fluxo de trabalho que inicia um loop infinito, que consome recursos do servidor e afeta o desempenho. A situação típica em que um loop infinito pode ocorrer é se você tiver um fluxo de trabalho configurado para iniciar quando um atributo for atualizado e, em seguida, atualizar esse atributo na lógica do fluxo de trabalho. A ação de atualização dispara o mesmo fluxo de trabalho que atualiza o registro e dispara o fluxo de trabalho novamente.  
  
 Os fluxos de trabalho que você cria incluem lógica para detectar e parar loops infinitos. Se um processo de fluxo de trabalho for executado mais do que um determinado número de vezes em um registro específico em um curto período de tempo, o processo falhará com o seguinte erro: **esse trabalho de workflow foi cancelado porque o fluxo de trabalho que o iniciou incluiu um loop infinito. Corrija a lógica do fluxo de trabalho e tente novamente**. O limite de vezes é 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Usar modelos de fluxo de trabalho  
 Se você tiver fluxos de trabalho semelhantes e antecipar a criação de mais fluxos de trabalho que seguem o mesmo padrão, salve o fluxo de trabalho como um modelo de fluxo de trabalho. Dessa forma, na próxima vez que você precisar criar um fluxo de trabalho semelhante, crie o fluxo de trabalho usando o modelo e evite inserir todas as condições e ações do zero.  
  
 Na caixa de diálogo **criar processo** , escolha **novo processo de um modelo existente (selecione da lista)** .  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Usar fluxos de trabalho filho  
 Se você aplicar a mesma lógica em diferentes fluxos de trabalho ou em ramificações condicionais, defina essa lógica como um fluxo de trabalho filho para que não seja necessário replicar essa lógica manualmente em cada fluxo de trabalho ou ramificação condicional. Isso ajuda a tornar seus fluxos de trabalho mais fáceis de manter. Em vez de examinar muitos fluxos de trabalho que podem aplicar a mesma lógica, você pode apenas atualizar um fluxo de trabalho.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Excluir automaticamente trabalhos de fluxo de trabalho concluídos
Para fluxos de trabalho em segundo plano (assíncrono), é recomendável selecionar a opção **excluir automaticamente trabalhos de fluxo de trabalho concluídos (para economizar espaço em disco)** na definição de fluxo de trabalho. Marcar essa caixa permite que o sistema exclua logs de fluxo de trabalho para execuções bem-sucedidas para economizar espaço. Observe que os logs de execuções de fluxo de trabalho com falha sempre serão salvos para solução de problemas.  

![Retenção de trabalhos de fluxo de trabalho](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Manter logs de trabalhos de fluxo de trabalho que encontraram erros  
Para fluxos de trabalho que não são executados em segundo plano (síncrono), é recomendável selecionar a opção **manter logs para trabalhos de fluxo de trabalho que encontraram erros** na definição do fluxo de trabalho. A seleção dessa opção permite que os logs de execuções de fluxo de trabalho com falha sejam salvos para solução de problemas. Os logs de execuções de fluxo de trabalho síncronos bem-sucedidas sempre serão excluídos para economizar espaço.   

![Opção manter logs para fluxos de trabalho com falha](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Limitar o número de fluxos de trabalho que atualizam a mesma entidade
Executar mais de um fluxo de trabalho que atualiza a mesma entidade pode causar problemas de bloqueio de recursos. Imagine vários fluxos de trabalho em execução onde cada atualização de oportunidade dispara uma atualização para a conta associada. Várias instâncias desses fluxos de trabalho em execução e tentando atualizar o mesmo registro de conta ao mesmo tempo podem resultar em problemas de bloqueio de recursos. Falhas de fluxo de trabalho ocorrem e uma mensagem de erro, como **tempo limite SQL: não é possível obter o bloqueio no _nome do recurso_de recurso**, é registrado. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Use as anotações para manter o controle das alterações  
 Ao editar fluxos de trabalho, você deve usar a guia anotações e digitar o que fez e por que fez isso. Isso permite que outra pessoa entenda as alterações feitas.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Visão geral dos processos de fluxo de trabalho](workflow-processes.md)   
 [Configurar processos de fluxo de trabalho](configure-workflow-steps.md)   
 [Monitorar e gerenciar processos de fluxo de trabalho](monitor-manage-processes.md)
   
