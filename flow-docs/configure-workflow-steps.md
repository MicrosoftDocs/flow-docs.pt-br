---
title: Configurar os estágios e as etapas do fluxo de trabalho no PowerApps | Microsoft Docs
description: Saiba como configurar as etapas do fluxo de trabalho
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
ms.openlocfilehash: 9ebdb1eddaea1f2fd7918c968879f5da37c287fe
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456158"
---
# <a name="configure-workflow-stages-and-steps"></a>Configurar os estágios e as etapas do fluxo de trabalho

Quando você cria fluxos de trabalho, você tem a opção para conter a lógica que você deseja executar em estágios e etapas.  
  
 **Estágios**  
 Os estágios facilitam a leitura da lógica do workflow e a explicam. No entanto, os estágios não afetam a lógica ou o comportamento dos fluxos de trabalho. Se um processo tiver estágios, todas as etapas no processo deverão estar contidas em um estágio.  
  
 **Etapas**  
 As etapas são uma unidade de lógica de negócios dentro de um fluxo de trabalho. Essas etapas podem incluir condições, ações, outras etapas ou uma combinação desses elementos.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Ações que podem ser executadas por processos de fluxo de trabalho  

 Processos de fluxo de trabalho podem executar as ações listadas na tabela a seguir.  
  
|Ação|Descrição|  
|------------|-----------------|  
|**Criar registro**|Cria um novo registro para uma entidade e atribui valores aos atributos.|  
|**Atualizar registro**|É possível atualizar o registro no qual o fluxo de trabalho é executado, qualquer registro vinculado a um registro em uma relação de N:1 ou todos os registros criados pelas etapas anteriores.|  
|**Atribuir registro**|É possível atribuir o registro no qual o fluxo de trabalho é executado, qualquer registro vinculado a um registro em uma relação de N:1 ou todos os registros criados pelas etapas anteriores.|  
|**Enviar email**|Envia um email. Você pode optar por criar uma nova mensagem de email ou usar um modelo de email configurado para a entidade do registro em que o fluxo de trabalho está em execução ou qualquer entidade que tenha uma relação N:1 com a entidade ou a entidade para todos os registros criados pelas etapas anteriores.|  
|**Iniciar fluxo de trabalho filho**|Inicia um processo de fluxo de trabalho que foi configurado como um fluxo de trabalho filho.|  
|**Alterar status**|Altera o status do registro no qual o processo é executado, qualquer registro vinculado a um registro em uma relação de N:1 ou todos os registros criados pelas etapas anteriores.|  
|**Interromper fluxo de trabalho**|Interrompe o fluxo de trabalho atual. Você pode definir um status de **Bem-sucedido** ou **Cancelado** e especificar uma mensagem de status.<br /><br /> Quando os fluxos de trabalho em tempo real são configurados para um evento, interromper um fluxo de trabalho com um status de cancelado impedirá que a ação de evento seja concluída. Consulte [Usando fluxos de trabalho em tempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows) para mais informações.|  
|**Etapa personalizada**|Os desenvolvedores podem criar etapas de fluxo de trabalho personalizadas que definem ações. Por padrão, não há etapa personalizada disponível.|  
  
### <a name="setting-record-values"></a>Configuração de valores de registro  

 Quando você cria um registro, você pode definir valores para o registro. Quando atualiza um registro, você pode definir, acrescentar, incrementar, decrementar, multiplicar ou limpar os valores.  
  
 Quando você seleciona **Definir propriedades**, uma caixa de diálogo é aberta mostrando o formulário padrão para a entidade.  
  
 Na parte inferior da caixa de diálogo, você pode ver uma lista de campos adicionais que não está presente no formulário.  
  
 Para qualquer campo, você pode definir um valor estático e que será definido pelo fluxo de trabalho.  
  
 No lado direito da caixa de diálogo do **Assistente de formulário** você pode definir ou acrescentar valores dinâmicos do contexto do registro atual. Isso inclui os valores dos registros relacionados que podem ser acessados de relações N:1 (muitos para um) para a entidade.  
  
 As opções disponíveis no **Assistente de formulário** dependem do campo que você selecionou no formulário. Ao definir um valor dinâmico, você verá um espaço reservado amarelo, conhecido como um “campo de dados dinâmico”, que mostra onde os dados dinâmicos serão incluídos. Se você quiser remover o valor, basta selecionar o campo de dados dinâmico e excluí-lo. Para campos de texto, você pode usar uma combinação de dados estáticos e dinâmicos.  
  
 Com valores dinâmicos, você não tenha certeza de que um campo ou entidade relacionada tem o valor que você deseja definir. Você pode definir um número de campos para testar e definir o valor e classificá-los em ordem usando as setas verdes. Se o primeiro campo não tiver dados, o segundo campo será testado e assim por diante. Se nenhum dos campos tiver dados, você poderá especificar um valor padrão a ser usado.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Definir condições para ações de fluxo de trabalho  

 As ações que serão aplicadas geralmente dependem de condições. Os processos de fluxo de trabalho fornecem várias maneiras de definir as condições e criar a lógica de ramificação para obter os resultados desejados. Você pode verificar os valores do registro no qual o processo de fluxo de trabalho é executado, qualquer um dos registros vinculados a esse registro com uma relação N:1 ou valores dentro do próprio processo  
  
|Tipo de condição|Descrição|  
|--------------------|-----------------|  
|**Condição de verificação**|Uma instrução lógica "if-\<condition> then".<br /><br /> Você pode verificar os valores atuais do registro que o fluxo de trabalho executa, qualquer registro vinculado a um registro em uma relação de N:1 ou todos os registros criados pelas etapas anteriores. Com base nesses valores, é possível definir as etapas adicionais quando a condição é verdadeira.<br /><br /> Na instrução "if-\<condição> then", você pode usar os seguintes operadores: **É Igual a**, **É Diferente de**, **Contém Dados**, **Não Contém Dados**, **Abaixo de** e **Não Abaixo de**. **Observação:**  **Abaixo de** e **Não Abaixo de** são operadores hierárquicos. Eles somente podem ser usados nas entidades que têm uma relação hierárquica definida. Se você estiver tentando usar esses operadores nas entidades que não tiverem a relação hierárquica definida, verá a mensagem de erro: "Você está usando um operador hierárquico em uma entidade que não tem uma relação hierárquica definida. Torne a entidade hierárquica (marcando uma relação como hierárquica) ou use um operador diferente". Para obter mais informações sobre as relações hierárquicas, consulte [Definir e consultar dados hierarquicamente relacionados](/powerapps/maker/common-data-service/define-query-hierarchical-data). Uma captura de tela que segue a tabela é um exemplo da definição do processo de fluxo de trabalho que usa os operadores hierárquicos **Abaixo de** e **Não Abaixo de**.|  
|**Ramificação condicional**|Uma instrução lógica “else-if-then”, o editor usa o texto “Otherwise, if \<condition>, then:”<br /><br /> Selecione uma condição de verificação que você definiu anteriormente e será possível adicionar uma ramificação condicional para definir as etapas adicionais quando a condição de verificação retornar false.|  
|**Ação padrão**|Uma instrução lógica “else”. o editor usa o texto “Otherwise:”<br /><br /> Selecione uma condição de verificação, ramificação condicional, condição de espera ou uma ramificação de espera paralelo previamente definido e será possível usar uma ação padrão para definir as etapas para todos os casos que não correspondem aos critérios definidos nos elementos de condição ou de ramificação.|  
|**Condição de espera**|Permite que um fluxo de trabalho em segundo plano pause a si mesmo até que os critérios definidos pela condição sejam atendidos. O fluxo de trabalho é iniciado novamente automaticamente quando os critérios na condição de espera tiverem sido atendidos.<br /><br /> Fluxos de trabalho em tempo real não podem usar condições de espera.|  
|**Ramificação de espera paralela**|Define uma condição de espera alternativa para um fluxo de trabalho em segundo plano com um conjunto correspondente de etapas adicionais que são executadas somente quando o critério inicial é atendido. Você pode usar ramificações de espera paralelos para criar limites de tempo na sua lógica de fluxo de trabalho. Eles ajudam a impedir que o fluxo de trabalho aguarde infinitamente até que os critérios definidos em uma condição de espera tenham sido atendidos.|  
|**Etapa personalizada**|Os desenvolvedores podem criar etapas de fluxo de trabalho personalizadas que definem condições. Por padrão, não há etapa personalizada disponível.|  
  
 A captura de tela a seguir contém um exemplo da definição do processo de fluxo de trabalho que usa os operadores hierárquicos **Abaixo de** e **Não Abaixo de**. Em nosso exemplo, conseguimos aplicar dois descontos diferentes para dois grupos de contas. Em **Adicionar etapa**, selecionamos **Verificar condição** para especificar a condição **if-then** que contém os operadores **Abaixo de** ou **Não Abaixo de**. A primeira condição **if-then** se aplica a todas as contas que estão **Sob** a conta do Alpine Ski House. Essas contas recebem um desconto de 10% em serviços e produtos comprados. A segunda condição **if-then** se aplica a todas as contas que **Não Abaixo de** a conta do Alpine Ski House e elas recebem um desconto de 5%. Em seguida, selecionamos **Atualizar registro** definir a ação a ser executada com base na condição.  
  
 ![Processo de fluxo de trabalho com os operadores Abaixo de&#47;Não Abaixo de](media/wfp-under-not-under.PNG "Processo de fluxo de trabalho com os operadores Abaixo de/Não Abaixo de")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Usando fluxos de trabalho em tempo real  

 Você pode configurar fluxos de trabalho em tempo real, mas deve usá-los com cuidado. Os fluxos de trabalho em segundo plano geralmente são recomendados porque eles permitem que o sistema os aplique como recursos no servidor disponível. Isso ajuda a amenizar o trabalho que o servidor tem que fazer e ajuda a manter o melhor desempenho para todos que usam o sistema. A desvantagem é que as ações definidas pelos fluxos de trabalho em segundo plano não são imediatas. Você não pode prever quando elas serão aplicadas, mas, geralmente, leva alguns minutos. Para a maioria da automação de processos empresariais isso é bom porque as pessoas que usam o sistema não precisam ter consciência de que o processo está em execução.  
  
 Use fluxos de trabalho em tempo real quando um processo empresarial exigir que alguém veja imediatamente os resultados do processo ou se você quiser a capacidade de cancelar uma operação. Por exemplo, você talvez queira definir determinados valores padrão para um registro na primeira vez que ele for salvo, ou você deseja certificar-se de que alguns registros não sejam excluídos.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Converter entre fluxos de trabalho em segundo plano e em tempo real  

 Você pode alterar um fluxo de trabalho em tempo real em um fluxo de trabalho em segundo plano, escolhendo **Converter em um fluxo de trabalho em segundo plano** na barra de ferramentas.  
  
 Você pode alterar um fluxo de trabalho em segundo plano em um fluxo de trabalho em tempo real, escolhendo **Converter em um fluxo de trabalho em tempo real** na barra de ferramentas. Se o fluxo de trabalho em segundo plano usar uma condição de espera, ele se tornará inválido e não será possível ativá-lo até que você remova a condição de espera.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Iniciar fluxos de trabalho em tempo real antes ou após as alterações de status  

 Quando você configura as **Opções para processos automáticos** para fluxos de trabalho em tempo real, as opções **Iniciar quando** para o evento de alterações de status permitem que você selecione **Após** ou **Antes** para quando o status for alterado. A opção padrão é **Após**.  
  
 Ao selecionar **Antes**, você está dizendo que deseja que a lógica no fluxo de trabalho seja aplicada antes de a alteração de dados no status ser salva. Isso fornece a capacidade de verificar os valores antes de outra lógica ser aplicada após a operação e impede que mais lógica seja executada. Por exemplo, você pode ter uma lógica adicional em uma ação de fluxo de trabalho personalizado ou plug-in que pode iniciar as ações em outro sistema. Interromper o processamento adicional pode evitar casos em que os sistemas externos são afetados. Aplicar fluxos de trabalho em tempo real antes desse evento também significa que as outras ações de fluxo de trabalho ou plug-in que possam ter salvado dados não precisem ser "revertidas" quando a operação for cancelada.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Usar a ação Interromper fluxo de trabalho com fluxos de trabalho em tempo real  

 Quando você aplica uma ação **Interromper fluxo de trabalho** em um fluxo de trabalho, você tem a opção de especificar uma condição de status que pode ser **Bem-sucedido** ou **Cancelado**. Ao definir o status para cancelado, você impede a operação. Uma mensagem de erro que contém o texto da mensagem de status da ação de interrupção será exibida para o usuário com o título **Erro de processo empresarial**.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Criar lógica de negócios personalizada com processos](guide-staff-through-common-tasks-processes.md)   
 [Visão geral dos processos de fluxo de trabalho](workflow-processes.md)   
 [Monitorar e gerenciar processos de fluxo de trabalho](monitor-manage-processes.md)   
 [Melhores práticas para processos de fluxo de trabalho](best-practices-workflow-processes.md)
