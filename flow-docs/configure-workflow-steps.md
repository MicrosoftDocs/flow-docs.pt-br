---
title: Configurar estágios e etapas do fluxo de trabalho no PowerApps | MicrosoftDocs
description: Saiba como configurar etapas de fluxo de trabalho
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4239e939f9522b4b3a22e56dfc69275482b017a7
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547065"
---
# <a name="configure-workflow-stages-and-steps"></a>Configurar etapas e estágios do fluxo de trabalho
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Ao criar fluxos de trabalho, você tem a opção de conter a lógica que deseja executar em estágios e etapas.  
  
 **Fases**  
 Os estágios facilitam a leitura da lógica do fluxo de trabalho e explicam a lógica do fluxo de trabalho. No entanto, os estágios não afetam a lógica ou o comportamento dos fluxos de trabalho. Se um processo tiver estágios, todas as etapas dentro do processo deverão estar contidas em um estágio.  
  
 **Tarefas**  
 As etapas são uma unidade de lógica de negócios em um fluxo de trabalho. As etapas podem incluir condições, ações, outras etapas ou uma combinação desses elementos.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Ações que os processos de fluxo de trabalho podem executar  

 Os processos de fluxo de trabalho podem executar as ações listadas na tabela a seguir.  
  
|Action|Ndescrição|  
|------------|-----------------|  
|**Criar registro**|Cria um novo registro para uma entidade e atribui valores escolhidos para os atributos.|  
|**Atualizar registro**|Você pode atualizar o registro no qual o fluxo de trabalho está sendo executado, qualquer um dos registros vinculados a esse registro em relações N:1 ou quaisquer registros criados por etapas anteriores.|  
|**Atribuir registro**|Você pode atribuir o registro em que o fluxo de trabalho está em execução, qualquer um dos registros vinculados a esse registro com uma relação N:1 ou quaisquer registros criados por etapas anteriores.|  
|**Enviar email**|Envia um email. Você pode optar por criar uma nova mensagem de email ou usar um modelo de email configurado para a entidade do registro em que o fluxo de trabalho está sendo executado ou qualquer entidade que tenha uma relação N:1 com a entidade ou a entidade para quaisquer registros criados por etapas anteriores.|  
|**Iniciar fluxo de trabalho filho**|Inicia um processo de fluxo de trabalho que foi configurado como um fluxo de trabalho filho.|  
|**Alterar status**|Altera o status do registro em que o processo está sendo executado, qualquer um dos registros vinculados a esse registro com uma relação N:1 ou quaisquer registros criados por etapas anteriores.|  
|**Parar fluxo de trabalho**|Interrompe o fluxo de trabalho atual. Você pode definir um status de **êxito** ou **cancelado** e especificar uma mensagem de status.<br /><br /> Quando os fluxos de trabalho em tempo real são configurados para um evento, parar um fluxo de trabalho com um status de cancelado impedirá que a ação do evento seja concluída. Consulte [usando fluxos de trabalho em tempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows) para obter mais informações.|  
|**Etapa personalizada**|Os desenvolvedores podem criar etapas de fluxo de trabalho personalizadas que definem ações. Não há etapas personalizadas disponíveis por padrão.|  
  
### <a name="setting-record-values"></a>Definindo valores de registro  

 Ao criar um registro, você pode definir valores para o registro. Ao atualizar um registro, você pode definir, acrescentar, incrementar, decrementar, multiplicar ou limpar valores.  
  
 Quando você seleciona **definir propriedades**, uma caixa de diálogo é aberta mostrando o formulário padrão para a entidade.  
  
 Na parte inferior da caixa de diálogo, você pode ver uma lista de campos adicionais que não estão presentes no formulário.  
  
 Para qualquer campo, você pode definir um valor estático e que será definido pelo fluxo de trabalho.  
  
 No lado direito da caixa de diálogo, o **Assistente de formulário** oferece a capacidade de definir ou acrescentar valores dinâmicos do contexto do registro atual. Isso inclui valores de registros relacionados que podem ser acessados de relações N:1 (muitos para um) para a entidade.  
  
 As opções disponíveis no **Assistente de formulário** dependem do campo que você selecionou no formulário. Ao definir um valor dinâmico, você verá um espaço reservado amarelo conhecido como um "separador" que mostra onde os dados dinâmicos serão incluídos. Se você quiser remover o valor, basta selecionar o espaçador e excluí-lo. Para campos de texto, você pode usar uma combinação de dados estáticos e dinâmicos.  
  
 Com valores dinâmicos, você não sabe para certos que um campo ou entidade relacionada tem o valor que você deseja definir. Na verdade, você pode definir um número de campos para tentar e definir o valor e classificá-los em ordem usando as setas verdes. Se o primeiro campo não tiver dados, o segundo campo será tentado e assim por diante. Se nenhum dos campos tiver dados, você poderá especificar um valor padrão a ser usado.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Definindo condições para ações de fluxo de trabalho  

 As ações que você aplicará frequentemente dependem das condições. Os processos de fluxo de trabalho fornecem várias maneiras de definir condições e criar lógica de ramificação para obter os resultados desejados. Você pode verificar os valores do registro em que o processo de fluxo de trabalho está sendo executado, qualquer um dos registros vinculados a esse registro com uma relação N:1 ou valores dentro do próprio processo  
  
|Tipo de condição|Ndescrição|  
|--------------------|-----------------|  
|**Verificar condição**|Uma instrução "If-\<Condition >" lógica.<br /><br /> Você pode verificar os valores atuais do registro em que o fluxo de trabalho está em execução, qualquer um dos registros vinculados a esse registro em relações N:1 ou quaisquer registros criados por etapas anteriores. Com base nesses valores, você pode definir etapas adicionais quando a condição for verdadeira.<br /><br /> Na instrução "If-\<Condition > then", você pode usar os seguintes operadores: **Equals**, não é **igual**, **contém dados**, não **contém dados**, **em** e **não em**. **Observação:**  O **em** e **não em** são operadores hierárquicos. Eles só podem ser usados nas entidades que têm uma relação hierárquica definida. Se você estiver tentando usar esses operadores nas entidades que não têm a relação hierárquica definida, verá a mensagem de erro: "você está usando um operador hierárquico em uma entidade que não tem uma relação hierárquica definida. Torne a entidade hierárquica (marcando uma relação como hierárquica) ou use um operador diferente. " Para obter mais informações sobre relações hierárquicas, consulte [definir e consultar dados relacionados hierarquicamente](/powerapps/maker/common-data-service/define-query-hierarchical-data). Uma captura de tela que segue a tabela é um exemplo da definição do processo de fluxo de trabalho que usa o **em** e **não em** operadores hierárquicos.|  
|**Ramificação condicional**|Uma instrução "else-if-then" lógica, o editor usa o texto "caso contrário, se \<condição > então:"<br /><br /> Selecione uma condição de verificação que você definiu anteriormente e você pode adicionar uma ramificação condicional para definir etapas adicionais quando a condição de verificação retornar false.|  
|**Ação padrão**|Uma instrução "else" lógica. o editor usa o texto "caso contrário:"<br /><br /> Selecione uma condição de verificação, ramificação condicional, condição de espera ou ramificação de espera paralela que você definiu anteriormente e você pode usar uma ação padrão para definir etapas para todos os casos que não correspondam aos critérios definidos nos elementos da condição ou da ramificação.|  
|**Condição de espera**|Permite que um fluxo de trabalho em segundo plano se Pause até que os critérios definidos pela condição tenham sido atendidos. O fluxo de trabalho é iniciado novamente automaticamente quando os critérios na condição de espera foram atendidos.<br /><br /> Os fluxos de trabalho em tempo real não podem usar condições de espera.|  
|**Ramificação de espera paralela**|Define uma condição de espera alternativa para um fluxo de trabalho em segundo plano com um conjunto correspondente de etapas adicionais que são executadas somente quando o critério inicial é atendido. Você pode usar branches de espera paralela para criar limites de tempo em sua lógica de fluxo de trabalho. Eles ajudam a impedir que o fluxo de trabalho aguarde indefinidamente até que os critérios definidos em uma condição de espera tenham sido atendidos.|  
|**Etapa personalizada**|Os desenvolvedores podem criar etapas de fluxo de trabalho personalizadas que definem condições. Não há etapas personalizadas disponíveis por padrão.|  
  
 A captura de tela a seguir contém um exemplo da definição do processo de fluxo de trabalho com os operadores **em** e **não sob** hierarquia. Em nosso exemplo, aplicamos dois descontos diferentes a dois grupos de contas. Em **Adicionar etapa**, selecionamos a **condição de verificação** para especificar a condição **if-then** que contém o **em** ou **não em** operadores. A primeira condição **if-then** se aplica a todas as contas que estão **na** conta da Alpine Ski House. Essas contas recebem um desconto de 10% em bons e serviços adquiridos. A segunda condição **if-then** se aplica a todas as contas que **não estão sob** a conta da Alpine Ski House e recebem um desconto de 5%. Em seguida, selecionamos **Atualizar Registro** para definir a ação a ser executada com base na condição.  
  
 ![Processo de fluxo de&#47;trabalho com sob operadores not by](media/wfp-under-not-under.PNG "Processo de fluxo de trabalho com menos de/não sob operadores")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Usando fluxos de trabalho em tempo real  

 Você pode configurar fluxos de trabalho em tempo real, mas você deve usá-los com cuidado. Fluxos de trabalho em segundo plano geralmente são recomendados porque permitem que o sistema os aplique como recursos no servidor estão disponíveis. Isso ajuda a suavizar o trabalho que o servidor precisa fazer e ajudar a manter o melhor desempenho para todos que usam o sistema. A desvantagem é que as ações definidas pelos fluxos de trabalho em segundo plano não são imediatas. Você não pode prever quando eles serão aplicados, mas, em geral, levará alguns minutos. Para a maior parte da automação dos processos de negócios, isso é bom porque as pessoas que usam o sistema não precisam saber atentamente que o processo está em execução.  
  
 Use fluxos de trabalho em tempo real quando um processo de negócios exigir que alguém veja imediatamente os resultados do processo ou se você quiser a capacidade de cancelar uma operação. Por exemplo, talvez você queira definir certos valores padrão para um registro na primeira vez que ele é salvo ou você deseja certificar-se de que alguns registros não sejam excluídos.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Convertendo entre fluxos de trabalho em tempo real e em segundo plano  

 Você pode alterar um fluxo de trabalho em tempo real para um fluxo de trabalho em segundo plano, escolhendo **converter em um fluxo de trabalho em segundo plano** na barra de ferramentas.  
  
 Você pode alterar um fluxo de trabalho em segundo plano em um fluxo de trabalho em tempo real, escolhendo **converter em um fluxo de trabalho em tempo real** na barra de ferramentas. Se o fluxo de trabalho em segundo plano usar condições de espera, ela se tornará inválida e você não poderá ativá-la até remover a condição de espera.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Iniciando fluxos de trabalho em tempo real antes ou depois das alterações de status  

 Quando você configura **opções para processos automáticos** para fluxos de trabalho em tempo real, as opções **Iniciar quando** para o evento de alterações de status permitem selecionar **após** ou **antes** quando o status é alterado. A opção padrão é **After**.  
  
 Quando você seleciona **antes** de estar dizendo que deseja que a lógica no fluxo de trabalho seja aplicada antes que os dados que alteram o status sejam salvos. Isso fornece a capacidade de verificar os valores antes que outra lógica tenha sido aplicada após a operação e impedir que uma lógica adicional seja executada. Por exemplo, você pode ter uma lógica adicional em um plug-in ou uma ação de fluxo de trabalho personalizada que pode iniciar ações em outro sistema. Ao interromper o processamento, você pode evitar casos em que sistemas externos são afetados. Aplicar fluxos de trabalho em tempo real antes desse evento também significa que outras ações de fluxo de trabalho ou plug-in que podem ter dados salvos não precisam ser "revertidas" quando a operação é cancelada.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Usando a ação parar fluxo de trabalho com fluxos de trabalho em tempo real  

 Ao aplicar uma ação **parar fluxo de trabalho** em um fluxo de trabalho, você tem a opção de especificar uma condição de status que pode ser **bem-sucedida** ou **cancelada**. Ao definir o status como cancelado, você impede a operação. Uma mensagem de erro que contém o texto da mensagem de status de ação de parada será exibida para o usuário com o cabeçalho **erro de processo comercial**.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Criar lógica de negócios personalizada com processos](guide-staff-through-common-tasks-processes.md)   
 [Visão geral dos processos de fluxo de trabalho](workflow-processes.md)   
 [Monitorar e gerenciar processos de fluxo de trabalho](monitor-manage-processes.md)   
 [Práticas recomendadas para processos de fluxo de trabalho](best-practices-workflow-processes.md)
