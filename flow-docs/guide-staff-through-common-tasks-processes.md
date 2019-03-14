---
title: Criar a lógica de negócios personalizada por meio de processos com o PowerApps | Microsoft Docs
description: Saiba mais sobre os diferentes tipos de lógica de negócios que você pode usar no seu aplicativo
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 5e123fa2abc8955d90fad2c9b09da76e449bf4b1
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462937"
---
# <a name="create-custom-business-logic-through-processes"></a>Criar a lógica de negócios personalizada por meio de processos

Definir e impor processos empresariais consistentes são os principais motivos para as pessoas usarem aplicativos controlados por modelos. Processos consistentes ajudam a garantir que as pessoas que usam o sistema podem se concentrar em seu trabalho e não em lembrar de executar um conjunto de etapas manuais. Os processos podem ser simples ou complexos, e podem mudar com o passar do tempo.  
  
Os PowerApps incluem vários tipos de processos, cada um desenvolvido para uma finalidade diferente:  
  
-   Fluxos de processos empresariais  
  
-   Fluxos de tarefas móveis  
  
-   Fluxos de trabalho  
  
-   Ações  
  
 Semelhante aos processos, também é possível criar regras de negócios e recomendações. Para obter mais informações, veja [Criar regras de negócios e recomendações para aplicar a lógica em um formulário](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  Usar os processos pode afetar os requisitos de licença para o PowerApps e os fluxos. Para obter mais informações, consulte [Requisitos de licença de entidade](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Quando usar os fluxos de processos empresariais  
 Use um fluxo de processos empresariais quando desejar que a equipe percorra os mesmos estágios e siga as mesmas etapas para interagir com um cliente. Por exemplo, use um fluxo de processos empresariais se você quiser que todos os usuários tratem as solicitações de serviço do cliente da mesma forma, ou para exigir que a equipe obtenha aprovação para uma nota fiscal antes de enviar um pedido.  
  
 Seus ambientes incluem vários fluxos de processos empresariais prontos para uso para tarefas comuns de vendas, serviço e marketing que podem ser usadas sem com pouca ou nenhuma alteração necessária. Ou, então você pode criar seus próprios. Consulte o tópico a seguir para obter mais informações sobre os fluxos de processos empresariais:  
  
-   [Criar um fluxo de processos empresariais](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Quando usar fluxos de trabalho  
 Use fluxos de trabalho para automatizar os processos de negócios por trás dos bastidores. Fluxos de trabalho normalmente são iniciados por eventos do sistema para que o usuário não precise estar ciente que eles estejam em execução. Fluxos de trabalho que operam em segundo plano são “assíncronos”. Fluxos de trabalho também podem ser configurados para que as pessoas possam iniciá-los manualmente. Quando você deseja automatizar tarefas comuns, como o envio automático de um email de confirmação para um cliente quando um pedido for enviado. Fluxos de trabalho que operam em tempo real são “síncronos”. Para obter mais informações sobre fluxos de trabalho, veja [Processos de fluxos de trabalho](workflow-processes.md).  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Quando usar as Ações  
 Use Ações quando desejar automatizar uma série de comandos no sistema. Ações expandem o vocabulário disponível para os desenvolvedores expressem os processos empresariais. Com os principais verbos como Criar, Atualizar, Excluir e Atribuir fornecidos pelo sistema, uma Ação usa esses verbos principais para criar verbos mais expressivos como Aprovar, Escalar, Rotear e Agendar. Se a definição de um processo empresarial mudar, alguém que não é um desenvolvedor poderá editar a Ação para que o código não precise ser alterado.  Para obter mais informações sobre as Ações, consulte [Ações](create-actions.md)  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Quando usar o Microsoft Flow  
 Use o Microsoft Flow quando precisar criar fluxos de trabalho automatizados que executam ações entre seu ambiente e aplicativo ou serviço favorito, como o Dynamics 365, Twitter, Dropbox, serviços do Google, Office 365 e SharePoint. Você pode disparar um fluxo baseado em uma ação específica ou invocá-lo de dentro do aplicativo. Mais informações: [Usar o Microsoft Flow para automatizar processos entre os serviços](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
)  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Onde ir para criar processos?  
 Há dois caminhos para navegar até os processos:  
  
- Abra o [gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e vá para **Componentes > Processos.** Esse caminho fornece um acesso conveniente quando você estiver realizando outro trabalho de personalização nas ferramentas de personalização.  

- **[Configurações](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Processos.** Esse caminho permite usar as exibições definidas para a Entidade de processo, incluindo as exibições personalizadas.  
  
 Fluxos de processos empresariais individuais também podem ser editados usando o botão **Editar processo** na barra de comandos para o formulário no qual o fluxo de processos empresariais está ativo.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Quem pode criar processos?  
 Somente as pessoas com as funções de segurança de Administrador do sistema, Personalizador do sistema ou CEO Gerente de negócios podem criar processos que se aplicam a todo o ambiente. Pessoas com outras funções podem criar processos com nível de acesso limitado. Por exemplo, pessoas com o nível de acesso de Usuário podem criar fluxos de trabalho para uso próprio com seus próprios registros.  
  
 A tabela a seguir mostra o nível de acesso de processos baseados em funções de segurança padrão.  
  
|||  
|-|-|  
|**Função de segurança**|**Nível de acesso**|  
|CEO Gerente de negócios|Organização|  
|Administrador de Sistema|Organização|  
|Personalizador do sistema|Organização|  
|Vice-presidente de marketing|Divisões Primária e Secundárias|  
|Vice-presidente de vendas|Divisões Primária e Secundárias|  
|Service Manager|Unidade de negócios|  
|Gerente de marketing|Unidade de negócios|  
|Gerente de vendas|Unidade de negócios|  
|Gerenciador de agendamento|Unidade de negócios|  
|Representante de atendimento ao cliente|Usuário|  
|Profissional de marketing|Usuário|  
|Vendedor|Usuário|  
|Agendador|Usuário|  
  
> [!NOTE]
>  Embora as pessoas possam criar o fluxo de processos empresariais, um fluxo de trabalho em tempo real ou processos de ação, elas precisarão ter os privilégios **Ativar fluxos de processos empresariais** ou **Ativar processos em tempo real** para ativá-los.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>Mais informações sobre fluxos de trabalho e Ações  
 Os processos podem verificar as condições, aplicar a lógica de ramificação e executar ações. Eles executam essas ações em uma série de etapas. A tabela a seguir descreve as etapas disponíveis no fluxo de trabalho e nos processos de ação. Para obter mais detalhes, consulte os tópicos para cada tipo de processo.  
  
|Etapa|Tipo de processo|Descrição|  
|----------|------------------|-----------------|  
|**Estágio**|Fluxo de trabalho, Ação|Estágios facilitam a leitura da lógica do fluxo de trabalho e a explicam. No entanto, os estágios não afetam a lógica ou o comportamento dos fluxos de trabalho. Se um processo tiver estágios, todas as etapas no processo deverão estar contidas em um estágio.|  
|**Condição de verificação**|Fluxo de trabalho, Ação|Uma instrução lógica “if-\<condition> then”.<br /><br /> Você pode verificar os valores do registro que o fluxo de trabalho executa, qualquer registro vinculado a um registro em uma relação de N:1 ou todos os registros criados pelas etapas anteriores. Com base nesses valores, é possível definir as etapas adicionais quando a condição é `true`.|  
|**Branch condicional**|Fluxo de trabalho, Ação|Uma instrução lógica “else-if-then”, o editor usa o texto “Otherwise, if \<condition>, then:”<br /><br /> Selecione uma condição de verificação que você definiu anteriormente e será possível adicionar um branch condicional para definir as etapas adicionais quando a condição de verificação retornar `false`.|  
|**Ação padrão**|Fluxo de trabalho, Ação|Uma instrução lógica “else”. o editor usa o texto “Otherwise:”<br /><br /> Selecione uma condição de verificação, branch condicional, condição de espera ou um branch de espera paralelo previamente definido e será possível usar uma ação padrão para definir as etapas para todos os casos que não correspondem aos critérios definidos nos elementos de condição ou de branch.|  
|**Condição de espera**|Somente fluxo de trabalho em segundo plano|Permite que um fluxo de trabalho em segundo plano pause a si mesmo até que os critérios definidos pela condição sejam atendidos. O fluxo de trabalho é iniciado novamente automaticamente quando os critérios na condição de espera tiverem sido atendidos.|  
|**Branch de espera paralelo**|Somente fluxo de trabalho em segundo plano|Define uma condição de espera alternativa para um fluxo de trabalho em segundo plano com um conjunto correspondente de etapas adicionais que são executadas somente quando o critério inicial é atendido. Você pode usar ramificações de espera paralelos para criar limites de tempo na sua lógica de fluxo de trabalho. Eles ajudam a impedir que o fluxo de trabalho aguarde infinitamente até que os critérios definidos em uma condição de espera tenham sido atendidos.|  
|**Atribuir valor**|Ação|Define um valor para uma variável ou parâmetro de saída no processo.|  
|**Criar registro**|Fluxo de trabalho, Ação|Cria um novo registro para uma entidade e atribui valores aos atributos.|  
|**Atualizar registro**|Fluxo de trabalho, Ação|É possível atualizar o registro no qual o fluxo de trabalho é executado, qualquer registro vinculado a um registro em uma relação de N:1 ou todos os registros criados pelas etapas anteriores.|  
|**Atribuir registro**|Fluxo de trabalho, Ação|É possível atribuir o registro no qual o fluxo de trabalho é executado, qualquer registro vinculado a um registro em uma relação de N:1 ou todos os registros criados pelas etapas anteriores.|  
|**Enviar email**|Fluxo de trabalho, Ação|Envia um email. Você pode optar por criar uma nova mensagem de email ou usar um modelo de email configurado para a entidade do registro em que o fluxo de trabalho está em execução ou qualquer entidade que tenha uma relação N:1 com a entidade ou a entidade para todos os registros criados pelas etapas anteriores.|  
|**Iniciar fluxo de trabalho filho**|Fluxo de trabalho, Ação|Inicia um processo de fluxo de trabalho que foi configurado como um fluxo de trabalho filho.|  
|**Alterar status**|Fluxo de trabalho, Ação|Altera o status do registro no qual o processo é executado, qualquer registro vinculado a um registro em uma relação de N:1 ou todos os registros criados pelas etapas anteriores.|  
|**Interromper fluxo de trabalho**|Fluxo de trabalho, Ação|Interrompe o fluxo de trabalho atual ou a ação. Você pode definir um status de **Bem-sucedido** ou **Cancelado** e especificar uma mensagem de status.|  
|**Etapa personalizada**|Fluxo de trabalho, Ação|Fornece extensões para os elementos lógicos disponíveis por padrão. Essas etapas podem incluir condições, ações, outras etapas ou uma combinação desses elementos. Os desenvolvedores podem criar etapas de fluxo de trabalho personalizadas. Por padrão, nenhuma etapa não personalizada disponível.|

Para obter mais informações para desenvolvedores, consulte o tópico do Guia do Desenvolvedor [Automatizar seus processos de negócios no compromisso com o cliente](https://docs.microsoft.com/dynamics365/customer-engagement/developer/automate-business-processes-customer-engagement
).
  

