---
title: Monitorar e gerenciar processos de fluxo de trabalho com o PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
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
ms.assetid: a987a803-4674-4eb0-87de-caefa003b1eb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 00d20d361dd7b3db9f55d6b975c472bea0c4160e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549001"
---
# <a name="monitor-and-manage-workflow-processes"></a>Monitorar e gerenciar processos de fluxo de trabalho
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Para monitorar e gerenciar processos, você deve localizar o processo, avaliar o status e executar as ações necessárias para resolver problemas.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Monitorando fluxos de trabalho em segundo plano  
 Fluxos de trabalho em segundo plano geram registros de trabalhos do sistema para controlar seu status. Você pode acessar informações sobre esses trabalhos do sistema em vários locais dentro do aplicativo:  
  
 **[Configurações](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > trabalhos do sistema**  
 Isso incluirá todos os tipos de trabalhos do sistema. Você precisará filtrar os registros para aqueles em que o **tipo de trabalho do sistema** é **Workflow**.  
  
 **Do processo de fluxo de trabalho**  
 Abra a definição de fluxo de trabalho em segundo plano e vá para a guia **processar sessão** . Isso mostrará apenas os trabalhos do sistema para este fluxo de trabalho em segundo plano.  
  
 **Do registro**  
 Você pode editar o formulário de entidade para que a navegação inclua a relação **processos em segundo plano** . Isso mostrará todos os trabalhos do sistema que foram iniciados no contexto do registro.  
  
> [!NOTE]
>  Se um trabalho assíncrono do sistema (Workflow) falhar várias vezes consecutivamente, o sistema começará a adiar a execução desse trabalho por intervalos de tempo mais longos e longos para que o administrador ou o criador de aplicativos possa investigar e resolver o problema. Depois que o trabalho começar a ser executado novamente, ele continuará executando normalmente.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Ações na execução de fluxos de trabalho em segundo plano  
 Enquanto um fluxo de trabalho em segundo plano estiver em execução, você terá opções para **Cancelar**, **Pausar**ou **adiar** o fluxo de trabalho. Se você tiver pausado um fluxo de trabalho anteriormente, poderá **retomá** -lo.  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Monitoramento de fluxos de trabalho e ações em tempo real  
 Fluxos de trabalho e ações em tempo real não usam registros de trabalhos do sistema porque ocorrem imediatamente. Todos os erros que ocorrerem serão exibidos para o usuário no aplicativo com o cabeçalho **erro de processo comercial**.  
  
 Não há log para operações bem-sucedidas. Você pode habilitar o log de erros verificando a opção **manter logs de trabalhos de fluxo de trabalho que encontraram erros** na área de **retenção log de fluxo** de trabalho na parte inferior da guia **Administração** do processo.  
  
 Para exibir o log de erros de um processo específico, abra o fluxo de trabalho em tempo real ou a definição de ação e vá para a guia **processar sessão** . Isso mostrará apenas os erros registrados para esse processo.  
  
 Se você quiser uma exibição de todos os erros de qualquer processo, vá para **Localização avançada** e crie uma exibição mostrando erros na entidade de sessão do processo.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Status dos processos de fluxo de trabalho  
 Quando você exibe uma lista de processos de fluxo de trabalho, qualquer processo individual pode ter um dos seguintes valores de **estado** e **razão de status** :  
  
|Status|Motivo do status|  
|-----------|-------------------|  
|Esteja|Aguardando recursos|  
|Suspenso|Dando|  
|Trava|Em andamento<br /><br /> Pausa<br /><br /> Cancelando|  
|Conclusão|foi<br /><br /> Falha ao<br /><br /> Cancel|  

## <a name="deleting-process-log-records"></a>Excluindo registros de log de processo

Se sua organização usa fluxos de trabalho em segundo plano ou fluxos de processo de negócios executados com frequência, a quantidade de registros de log de processo pode se tornar grande o suficiente para causar problemas de desempenho, bem como consumir quantidades significativas de armazenamento. Para excluir os registros de log do processo que não foram removidos suficientemente por um dos trabalhos de exclusão de registro em massa padrão, você pode usar o recurso de trabalhos do sistema de exclusão em massa para criar um trabalho de exclusão de registro em massa personalizado.

1. Vá para **configurações** > **Gerenciamento de dados** > **exclusão de registros em massa**.
2. Na área de **exclusão do registro em massa** , selecione **novo**. 
3. Na página inicial do **Assistente de exclusão em massa** , selecione **Avançar**.
4. Na lista **procurar** , selecione trabalhos do **sistema**.
5. As condições a seguir são usadas para criar um trabalho de exclusão de registro em massa para excluir registros de log de processo. 
 - O **tipo de trabalho do sistema é igual a Workflow**. Isso direciona os registros de fluxo de trabalho. 
 - O **status é igual a concluído**. Somente os fluxos de trabalho concluídos são válidos para executar a tarefa.
 - O **motivo do status é igual a bem-sucedido**. Excluir trabalhos bem-sucedidos, cancelados e com falha.
 - **Concluído em mais de X dias 30**. Use o campo concluído em para excluir somente os registros de log do processo de fluxo de trabalho com mais de 30 dias.
 ![Custom-Bulk-Record-deletion. png](media/custom-bulk-record-deletion.png)
6. Clique em **Avançar**.
7. Defina a frequência com que seu trabalho de exclusão em massa será executado. Você pode agendar seu trabalho para ser executado em intervalos definidos ou criar um trabalho de exclusão em massa único [usando a opção imediatamente](#using-the-immediately-option). Neste exemplo, um trabalho recorrente é definido para ser executado em 21 de maio de 2018 e a cada 30 dias depois. 
![opções de exclusão de registros em massa](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Usando a opção imediatamente

Observe que você tem a opção de executar uma exclusão em massa síncrona imediata dos registros selecionando a opção **imediatamente** . Essa exclusão é executada com a execução de SQL Server direta, em vez de passar cada registro por meio do pipeline de evento de exclusão, o que pode reduzir o impacto no desempenho do sistema. Essa é uma boa opção se você quiser limpar rapidamente os registros de fluxo de trabalho extras, em vez da tarefa de exclusão em massa que está aguardando na fila assíncrona para processamento. 

A opção **imediatamente** é habilitada quando as seguintes condições são verdadeiras: 
- O trabalho de exclusão em massa é para a entidade trabalhos do sistema.
- Os critérios de pesquisa têm o tipo de trabalho do sistema de condição igual a fluxo. 
- O usuário que cria o trabalho de exclusão em massa tem profundidade global para o privilégio de exclusão na entidade AsyncOperation. A função de segurança administrador do sistema tem esse privilégio.  

A exclusão em massa síncrona excluirá somente os registros AsyncOperation no estado concluído. Um máximo de 1 milhão registros são processados para cada invocação. Você precisará executar o trabalho várias vezes se o seu ambiente tiver mais de 1 milhão registros a serem removidos.  
  
## <a name="next-steps"></a>Próximas etapas   
 [Práticas recomendadas para processos de fluxo de trabalho](best-practices-workflow-processes.md) <br />

