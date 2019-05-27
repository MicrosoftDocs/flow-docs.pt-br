---
title: Monitorar e gerenciar processos de fluxo de trabalho com o PowerApps | Microsoft Docs
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
ms.openlocfilehash: 007caa66731870f359e8cb33ba0919390d3196cd
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64465809"
---
# <a name="monitor-and-manage-workflow-processes"></a>Monitorar e gerenciar processos de fluxo de trabalho

Para monitorar e gerenciar processos, é necessário localizar o processo, avaliar o status e executar quaisquer ações necessárias para resolver problemas.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Monitoramento de fluxos de trabalho em segundo plano  
 Fluxos de trabalho em segundo plano geram registros de trabalho do sistema para controlar o status. Você pode acessar informações sobre esses trabalhos de sistema em vários locais dentro do aplicativo:  
  
 **[Configurações](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Trabalhos do sistema**  
 Isso incluirá todos os tipos de trabalhos do sistema. Você precisará filtrar os registros para aqueles nos quais **Tipo de trabalho do sistema** é **Fluxo de trabalho**.  
  
 **Por meio do processo de fluxo de trabalho**  
 Abra a definição de fluxo de trabalho em segundo plano e vá para a guia **Sessão do processo**. Isso mostrará apenas os trabalhos do sistema para esse fluxo de trabalho em segundo plano.  
  
 **Por meio do registro**  
 Você pode editar o formulário de entidade para que a navegação inclua a relação **Processos em segundo plano**. Isso mostrará todos os trabalhos do sistema que foram iniciados no contexto do registro.  
  
> [!NOTE]
>  Se um trabalho de sistema assíncrono (fluxo de trabalho) falhar várias vezes consecutivas, o sistema será iniciado para adiar a execução do trabalho para intervalos de tempo mais longos para que o administrador ou o criador de aplicativos possa investigar e resolver o problema. Depois que o trabalho for iniciado tendo êxito novamente, ele continuará em execução normalmente.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Ações executando fluxos de trabalho em segundo plano  
 Durante a execução de um fluxo de trabalho em segundo plano, você tem opções para **Cancelar**, **Pausar** ou **Adiar** o fluxo de trabalho. Se você já tiver pausado um fluxo de trabalho anteriormente, você poderá **retomá-lo**.  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Monitoramento de ações e fluxos de trabalho em tempo real  
 Ações e fluxos de trabalho em tempo real não usam registros de trabalho do sistema porque ocorrem imediatamente. Os erros que ocorrem serão exibidos ao usuário no aplicativo com o título **Erro de processo empresarial**.  
  
 Não há nenhum log para operações bem-sucedidas. Você pode habilitar o log de erros marcando a opção **Manter logs para trabalhos de fluxo de trabalho que encontraram erros** na área **Retenção de log de fluxo de trabalho** na parte inferior da guia **Administração** para o processo.  
  
 Para exibir o log de erros para um processo específico, abra a definição de fluxo de trabalho ou ação em tempo real e vá para a guia **Sessão do processo**. Isso mostrará apenas os erros registrados em log para esse processo.  
  
 Se você quiser ver todos os erros para qualquer processo, acesse **Localização avançada** e crie uma exibição mostrando os erros na entidade de sessão do processo.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Status dos processos de fluxo de trabalho  
 Quando você vê uma lista de processos de fluxo de trabalho, qualquer processo individual pode ter um dos seguintes valores de **Estado** e **Motivo do status**:  
  
|Estado|Motivo do status|  
|-----------|-------------------|  
|Preparado|Aguardando recursos|  
|Suspenso|Aguardando|  
|Bloqueado|Em andamento<br /><br /> Pausando<br /><br /> Cancelando|  
|Concluído|Com êxito<br /><br /> Falha<br /><br /> Cancelado|  

## <a name="deleting-process-log-records"></a>Exclusão de registros de log do processo

Se sua organização usa fluxos de trabalho em segundo plano ou fluxos de processo empresarial que são executados com frequência, a quantidade de registros de log do processo pode se tornar grande o suficiente para causar problemas de desempenho, bem como consumir quantidades significativas de armazenamento. Para excluir registros de log do processo não removidos suficientemente por um dos trabalhos de exclusão de registros em massa padrão, você pode usar o recurso de trabalhos do sistema de exclusão em massa para criar um trabalho de exclusão de registro em massa personalizado.

1. Vá para **Configurações** > **Gerenciamento de Dados** > **Exclusão de registros em massa**.
2. Na área **Exclusão de registros em massa**, selecione **Novo**. 
3. Na página inicial **Assistente de exclusão em massa**, selecione **Avançar**.
4. Na lista **Pesquisar**, selecione **Trabalhos do sistema**.
5. As condições a seguir são usadas para criar um trabalho de exclusão de registros em massa para excluir registros de log do processo. 
 - **O tipo de trabalho do sistema é igual ao fluxo de trabalho**. Isso se destina a registros de fluxo de trabalho. 
 - **O status é igual a Concluído**. Somente fluxos de trabalho concluídos são válidos para executar o trabalho.
 - **O motivo do status é igual a Êxito**. Exclusão de trabalhos com falha, cancelados e bem-sucedidos.
 - **Concluído em mais de 30 dias**. Use o campo Concluído em somente para excluir os registros de log do processo de fluxo de trabalho com mais de 30 dias.
 ![custom-bulk-record-deletion.png](media/custom-bulk-record-deletion.png)
6. Clique em **Avançar**.
7. Defina a frequência com que seu trabalho de exclusão em massa será executado. Você pode agendar a execução de seu trabalho em intervalos definidos ou criar um trabalho de exclusão em massa ocasional [usando a opção imediatamente](#using-the-immediately-option). Neste exemplo, um trabalho recorrente é definido para ser executado em 21 de maio de 2018 e, depois disso, a cada 30 dias. 
![Opções de exclusão de registros em massa](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Usando a opção imediatamente

Observe que você tem a opção de executar uma verificação de exclusão em massa síncrona e imediata dos registros selecionando a opção **Imediatamente**. Esta exclusão é executada com a execução direta do SQL Server em vez de passar cada registro por meio do pipeline de evento de exclusão, que pode reduzir o impacto no desempenho do sistema. Isso é uma boa opção se você quer limpar rapidamente os registros de fluxo de trabalho adicionais, em vez da espera do trabalho de exclusão em massa na fila assíncrona para processamento. 

A opção **Imediatamente** é habilitada quando as seguintes condições forem verdadeiras: 
- O trabalho de exclusão em massa destina-se à entidade de trabalhos do sistema.
- Os critérios de pesquisa têm a condição tipo de trabalho do sistema igual ao fluxo de trabalho. 
- O usuário que está criando o trabalho de exclusão em massa tem profundidade global para o privilégio de exclusão na entidade AsyncOperation. A função de segurança de administrador do sistema tem esse privilégio.  

A exclusão em massa síncrona excluirá apenas os registros de AsyncOperation no estado concluído. Um máximo de um milhão de registros são processados para cada invocação. Você precisará executar o trabalho várias vezes se seu ambiente tiver mais de um milhão de registros a serem removidos.  
  
## <a name="next-steps"></a>Próximas etapas   
 [Melhores práticas para processos de fluxo de trabalho](best-practices-workflow-processes.md) <br />

