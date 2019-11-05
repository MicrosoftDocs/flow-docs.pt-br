---
title: Criar lógica de negócios personalizada por meio de processos com o PowerApps | MicrosoftDocs
description: Saiba mais sobre os diferentes tipos de lógica de negócios que você pode usar em seu aplicativo
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b3072cc5897b8a2ef5a2a92ec3a07a0e31b57898
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545342"
---
# <a name="create-custom-business-logic-through-processes"></a>Criar lógica de negócios personalizada por meio de processos
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

A definição e a imposição de processos de negócios consistentes é uma das principais razões pelas quais as pessoas usam aplicativos baseados em modelos. Processos consistentes ajudam a garantir que as pessoas que usam o sistema possam se concentrar em seu trabalho e não em se lembrar de executar um conjunto de etapas manuais. Os processos podem ser simples ou complexos e podem mudar ao longo do tempo.  
  
O PowerApps inclui vários tipos de processos, cada um projetado para uma finalidade diferente:  
  
-   Fluxos de processos de negócios  
  
-   Fluxos de tarefas móveis  
  
-   fluxos  
  
-   Ações  
  
 Semelhante aos processos, você também pode criar regras de negócio e recomendações. Para obter mais informações, consulte [criar regras de negócio e recomendações para aplicar a lógica em um formulário](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  O uso de processos pode afetar os requisitos de licença do PowerApps e dos fluxos. Para obter mais informações, consulte [requisitos de licença de entidade](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Quando usar fluxos de processo de negócios  
 Use um fluxo de processo de negócios quando desejar que a equipe passe pelos mesmos estágios e siga as mesmas etapas para interagir com um cliente. Por exemplo, use um fluxo de processo de negócios se desejar que todos manipulem solicitações de atendimento ao cliente da mesma forma ou exijam que a equipe receba aprovação para uma fatura antes de enviar um pedido.  
  
 Seu ambiente inclui vários fluxos de processos comerciais prontos para uso para tarefas comuns de vendas, serviços e marketing que você pode usar com pouca ou nenhuma alteração necessária. Ou você pode criar o seu próprio. Consulte o tópico a seguir para obter mais informações sobre fluxos de processos empresariais:  
  
-   [Criar um fluxo de processo de negócios](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Quando usar fluxos de trabalho  
 Use fluxos de trabalho para automatizar processos de negócios nos bastidores. Os fluxos de trabalho são normalmente iniciados por eventos do sistema para que o usuário não precise estar ciente de que estão em execução. Os fluxos de trabalho que operam em segundo plano são "assíncronos". Os fluxos de trabalho também podem ser configurados para que as pessoas os iniciem manualmente. Quando você deseja automatizar tarefas comuns, como enviar automaticamente um email de confirmação para um cliente quando um pedido é enviado. Os fluxos de trabalho que operam em tempo real são "síncronos". Para obter mais informações sobre fluxos de trabalho, consulte [processos de fluxo de trabalho](workflow-processes.md)  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Quando usar ações  
 Use ações quando desejar automatizar uma série de comandos no sistema. As ações expandem o vocabulário disponível para desenvolvedores para expressar processos de negócios. Com verbos principais como criar, atualizar, excluir e atribuir fornecidos pelo sistema, uma ação usa esses verbos principais para criar verbos mais expressivos como aprovar, escalonar, rotear ou agendar. Se a definição de um processo comercial for alterada, alguém que não seja um desenvolvedor poderá editar a ação para que o código não precise ser alterado.  Para obter mais informações sobre ações, consulte [ações](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Quando usar Microsoft Flow  
 Use Microsoft Flow quando precisar criar fluxos de trabalho automatizados que executam ações entre seu ambiente e aplicativo ou serviço favorito, como o Dynamics 365, Twitter, Dropbox, Google Services, Office 365 e SharePoint. Você pode disparar um fluxo com base em uma ação específica ou invocar de dentro de seu aplicativo. Mais informações: [usar Microsoft Flow para automatizar processos entre serviços](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Onde posso criar processos?  
 Há dois caminhos para navegar até os processos:  
  
- Abra o [Gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e vá para **componentes > processos.** Esse caminho fornece acesso conveniente quando você está fazendo outras tarefas de personalização nas ferramentas de personalização.  

- **[Configurações](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > processos.** Esse caminho permite que você use modos de exibição definidos para a entidade processo, incluindo quaisquer exibições personalizadas.  
  
 Os fluxos de processos empresariais individuais também podem ser editados usando o botão **Editar processo** na barra de comandos para o formulário em que o fluxo do processo empresarial está ativo.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Quem pode criar processos?  
 Somente as pessoas com a função de segurança administrador do sistema, personalizador de sistema ou CEO – gerente de negócios podem criar processos que se aplicam a todo o ambiente. As pessoas com outras funções podem criar processos com nível de acesso limitado. Por exemplo, as pessoas com o nível de acesso do usuário podem criar fluxos de trabalho para seu próprio uso com os registros que eles possuem.  
  
 A tabela a seguir mostra o nível de acesso de processos com base em funções de segurança padrão.  
  
|||  
|-|-|  
|**Função de segurança**|**Nível de acesso**|  
|CEO – gerente de negócios|Organizações|  
|Administrador do sistema|Organizações|  
|Personalizador do sistema|Organizações|  
|Vice-Presidente de marketing|Pai: unidades de negócios filho|  
|Vice-Presidente de vendas|Pai: unidades de negócios filho|  
|Service Manager|Unidade de negócios|  
|Gerente de marketing|Unidade de negócios|  
|Gerente de vendas|Unidade de negócios|  
|Gerenciador de agendamento|Unidade de negócios|  
|Representante do atendimento ao cliente|Usuário|  
|Profissional de marketing|Usuário|  
|Representante|Usuário|  
|Agendador|Usuário|  
  
> [!NOTE]
>  Embora as pessoas possam criar fluxo de processo empresarial, fluxo de trabalho em tempo real ou processos de ação, eles precisarão ter o **processo de ativação de fluxos** de processos de negócios ou ativar os privilégios em **tempo real** para ativá-los.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Mais sobre fluxos de trabalho e ações  
 Os processos podem verificar condições, aplicar lógica de ramificação e executar ações. Eles executam essas ações em uma série de etapas. A tabela a seguir descreve as etapas disponíveis no fluxo de trabalho e nos processos de ação. Para obter mais detalhes, consulte os tópicos para cada tipo de processo.  
  
|Etapa|Tipo de processo|Ndescrição|  
|----------|------------------|-----------------|  
|**Test**|Fluxo de trabalho, ação|Os estágios facilitam a leitura da lógica do fluxo de trabalho e explicam a lógica do fluxo de trabalho. No entanto, os estágios não afetam a lógica ou o comportamento dos fluxos de trabalho. Se um processo tiver estágios, todas as etapas no processo deverão estar contidas em um estágio.|  
|**Verificar condição**|Fluxo de trabalho, ação|Uma instrução "If-\<Condition >" lógica.<br /><br /> Você pode verificar valores para o registro em que o fluxo de trabalho está em execução, qualquer um dos registros vinculados a esse registro em uma relação N:1 ou quaisquer registros criados por etapas anteriores. Com base nesses valores, você pode definir etapas adicionais quando a condição é `true`.|  
|**Ramificação condicional**|Fluxo de trabalho, ação|Uma instrução "else-if-then" lógica, o editor usa o texto "caso contrário, se \<condição > então:"<br /><br /> Selecione uma condição de verificação que você definiu anteriormente e você pode adicionar uma ramificação condicional para definir etapas adicionais quando a condição de verificação retornar `false`.|  
|**Ação padrão**|Fluxo de trabalho, ação|Uma instrução "else" lógica. o editor usa o texto "caso contrário:"<br /><br /> Selecione uma condição de verificação, ramificação condicional, condição de espera ou ramificação de espera paralela que você definiu anteriormente e você pode usar uma ação padrão para definir etapas para todos os casos que não correspondem aos critérios definidos em elementos de condição ou ramificação.|  
|**Condição de espera**|Somente fluxo de trabalho em segundo plano|Permite que um fluxo de trabalho em segundo plano se Pause até que os critérios definidos pela condição tenham sido atendidos. O fluxo de trabalho é iniciado novamente automaticamente quando os critérios na condição de espera foram atendidos.|  
|**Ramificação de espera paralela**|Somente fluxo de trabalho em segundo plano|Define uma condição de espera alternativa para um fluxo de trabalho em segundo plano com um conjunto correspondente de etapas adicionais que são executadas somente quando o critério inicial é atendido. Você pode usar branches de espera paralela para criar limites de tempo em sua lógica de fluxo de trabalho. Eles ajudam a impedir que o fluxo de trabalho aguarde indefinidamente até que os critérios definidos em uma condição de espera tenham sido atendidos.|  
|**Atribuir valor**|Action|Define um valor para um parâmetro de variável ou de saída no processo.|  
|**Criar registro**|Fluxo de trabalho, ação|Cria um novo registro para uma entidade e atribui valores a atributos.|  
|**Atualizar registro**|Fluxo de trabalho, ação|Você pode atualizar o registro no qual o fluxo de trabalho está sendo executado, qualquer um dos registros vinculados a esse registro em uma relação N:1 ou quaisquer registros criados por etapas anteriores.|  
|**Atribuir registro**|Fluxo de trabalho, ação|Você pode atribuir o registro em que o fluxo de trabalho está em execução, qualquer um dos registros vinculados a esse registro com uma relação N:1 ou quaisquer registros criados por etapas anteriores.|  
|**Enviar email**|Fluxo de trabalho, ação|Envia um email. Você pode optar por criar uma nova mensagem de email ou usar um modelo de email configurado para a entidade do registro em que o fluxo de trabalho está sendo executado ou qualquer entidade que tenha uma relação N:1 com a entidade ou a entidade para quaisquer registros criados por etapas anteriores.|  
|**Iniciar fluxo de trabalho filho**|Fluxo de trabalho, ação|Inicia um processo de fluxo de trabalho que foi configurado como um fluxo de trabalho filho.|  
|**Alterar status**|Fluxo de trabalho, ação|Altera o status do registro em que o processo está sendo executado, qualquer um dos registros vinculados a esse registro com uma relação N:1 ou quaisquer registros criados por etapas anteriores.|  
|**Parar fluxo de trabalho**|Fluxo de trabalho, ação|Interrompe o fluxo de trabalho ou a ação atual. Você pode definir um status de **êxito** ou **cancelado** e especificar uma mensagem de status.|  
|**Etapa personalizada**|Fluxo de trabalho, ação|Fornece extensões para os elementos lógicos disponíveis por padrão. As etapas podem incluir condições, ações, outras etapas ou uma combinação desses elementos. Os desenvolvedores podem criar etapas de fluxo de trabalho personalizadas. Por padrão, não há etapas personalizadas disponíveis.|

  

