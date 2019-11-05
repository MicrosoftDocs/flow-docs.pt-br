---
title: Visão geral dos fluxos de processos de negócios | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 230c35947c4e499c5e26fc37bb87828ec787a469
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545514"
---
# <a name="business-process-flows-overview"></a>Visão geral dos fluxos de processos de negócios
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Você pode ajudar a garantir que as pessoas insiram dados de forma consistente e siga as mesmas etapas sempre que trabalharem com um cliente criando um fluxo de processo empresarial. Por exemplo, talvez você queira criar um fluxo de processo de negócios para que todos lidem com as solicitações de atendimento ao cliente da mesma forma ou para exigir que as pessoas obtenham aprovação para uma fatura antes de enviar um pedido. Os fluxos de processos de negócios usam a mesma tecnologia subjacente que outros processos, mas os recursos que eles fornecem são muito diferentes de outros recursos que usam processos. Para saber como criar ou editar um fluxo de processo de negócios, consulte [criar um fluxo de processo comercial](create-business-process-flow.md).  
  
 [Assista a um vídeo curto (4:49) sobre fluxos de processo de negócios.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Por que usar fluxos de processos empresariais?  
Os fluxos de processos de negócios fornecem um guia para que as pessoas realizem o trabalho. Eles fornecem uma experiência de usuário simplificada que conduz as pessoas pelos processos que sua organização definiu para interações que precisam ser avançadas para uma conclusão de algum tipo. Essa experiência do usuário pode ser adaptada para que as pessoas com diferentes funções de segurança possam ter uma experiência que os melhores pacotes façam do trabalho.  
  
 Use fluxos de processo de negócios para definir um conjunto de etapas para as pessoas seguirem para levá-las a um resultado desejado. Essas etapas fornecem um indicador visual que informa às pessoas onde elas estão no processo de negócios. Os fluxos de processos de negócios reduzem a necessidade de treinamento porque novos usuários não precisam se concentrar em qual entidade eles devem usar. Eles podem permitir que o processo o Oriente. Você pode configurar fluxos de processos empresariais para dar suporte a metodologias de vendas comuns que podem ajudar seus grupos de vendas a obter resultados melhores. Para grupos de serviços, os fluxos de processos comerciais podem ajudar a nova equipe a se familiarizar mais rapidamente e evitar erros que possam resultar em clientes não satisfeitos.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>O que os fluxos de processos comerciais podem fazer?  
 Com os fluxos de processos de negócios, você define um conjunto de *estágios* e *etapas* que são exibidos em um controle na parte superior do formulário.  
  
 ![Processo comercial com estágios](media/business-process-stages.png "Processo comercial com estágios")  
  
 Cada estágio contém um grupo de etapas. Cada etapa representa um campo onde os dados podem ser inseridos. As pessoas avançam para o próximo estágio usando o botão **próximo estágio** . Você pode fazer uma etapa necessária para que as pessoas precisem inserir dados para o campo correspondente antes que possam prosseguir para o próximo estágio. Isso é normalmente chamado de "estágio-retenção".  
  
 Os fluxos de processos de negócios parecem relativamente simples em comparação com outros tipos de processos porque não fornecem nenhuma lógica de negócios condicional ou automação além de fornecer a experiência simplificada para entrada de dados e controle de entrada em estágios. No entanto, quando você os combina com outros processos e personalizações, eles podem desempenhar um papel importante ao economizar tempo de pessoal, reduzir os custos de treinamento e aumentar a adoção do usuário.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Fluxos de processos de negócios integrados a outras personalizações  
 Quando você ou o usuário insere dados usando fluxos de processo de negócios, as alterações de dados também são aplicadas a campos de formulário para que qualquer automação fornecida por regras de negócio ou scripts de formulário possa ser aplicada imediatamente. As etapas podem ser adicionadas para definir valores para campos que não estão presentes no formulário e esses campos serão adicionados ao modelo de objeto `Xrm.Page` usado para scripts de formulário. Todos os fluxos de trabalho iniciados por alterações em campos incluídos em um fluxo de processo comercial serão aplicados quando os dados no formulário forem salvos. Se a automação for aplicada por um fluxo de trabalho em tempo real, as alterações serão imediatamente visíveis para o usuário quando os dados no formulário forem atualizados depois que o registro for salvo.  
  
 Embora o controle de fluxo do processo de negócios no formulário não forneça nenhuma programação direta no lado do cliente, as alterações aplicadas por regras de negócio ou scripts de formulário são aplicadas automaticamente aos controles de fluxo do processo de negócios. Se você ocultar um campo em um formulário, esse campo também será ocultado no controle de fluxo do processo de negócios. Se você definir um valor usando regras de negócio ou scripts de formulário, esse valor será definido no fluxo do processo de negócios.  
  
### <a name="concurrent-process-flows"></a>Fluxos de processo simultâneos  
 Fluxos de processos de negócios simultâneos permitem que os personalizadores configurem vários processos de negócios e os associem ao mesmo registro inicial. Os usuários podem alternar entre vários processos de negócios em execução simultaneamente e retomar seu trabalho no estágio no processo em que estavam.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Fluxos de processos empresariais do sistema  
 Os fluxos de processo de negócios a seguir estão incluídos. Para entender como os fluxos de processos de negócios funcionam, examine estes fluxos de processos empresariais do sistema:  
  
-   Processo de vendas do cliente potencial para oportunidade  
  
-   Processo de vendas da oportunidade  
  
-   Telefone para o processo de caso  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Várias entidades nos fluxos de processos de negócios  
 Você pode usar um fluxo de processo de negócios para uma única entidade ou abranger várias entidades. Por exemplo, você pode ter um processo que começa com uma oportunidade e, em seguida, continua a uma cotação, um pedido e uma fatura, antes de finalmente retornar para fechar a oportunidade.  
  
 Você pode criar fluxos de processo de negócios que unem os registros de até cinco entidades diferentes em um único processo para que as pessoas que usam o aplicativo possam se concentrar no fluxo de seu processo, e não em qual entidade eles estão trabalhando. Eles podem navegar mais facilmente entre os registros de entidade relacionados.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Vários fluxos de processo comercial estão disponíveis por entidade  
 Nem todos os usuários em uma organização podem seguir o mesmo processo e diferentes condições podem exigir que um processo diferente seja aplicado. Você pode ter até 10 fluxos de processo de negócios ativos por entidade para fornecer os processos apropriados para diferentes situações.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Controlar qual fluxo de processo de negócios será aplicado  
 Você pode associar fluxos de processo de negócios com funções de segurança para que somente pessoas com essas funções de segurança possam vê-las ou usá-las. Você também pode definir a ordem dos fluxos de processo de negócios para que você possa controlar qual fluxo de processo de negócios será definido por padrão. Isso funciona da mesma maneira que vários formulários de uma entidade são definidos.  
  
 Quando alguém cria um novo registro de entidade, a lista de definições de processos de negócios ativos disponíveis é filtrada pela função de segurança do usuário. A primeira definição de processo de negócios ativada disponível para a função de segurança do usuário de acordo com a lista de ordem de processo é aquela aplicada por padrão. Se mais de uma definição de processo de negócios ativo estiver disponível, os usuários poderão carregar outro na caixa de diálogo alternar processo. Sempre que os processos são alternados, aquele atualmente renderizado passa para o plano de fundo e é substituído pelo selecionado, mas mantém seu estado e pode ser revertido. Cada registro pode ter várias instâncias de processo associadas (cada uma para uma definição de fluxo de processo comercial diferente, até um total de 10). No carregamento de formulário, apenas um fluxo de processo de negócios é renderizado. Quando qualquer usuário aplica um processo diferente, esse processo só pode ser carregado por padrão para esse usuário específico.  
  
 Para garantir que um processo comercial seja carregado por padrão para todos os usuários (comportamento equivalente a "fixação" do processo), um script de API de cliente personalizado (recurso da Web) pode ser adicionado na carga de formulário que carrega especificamente uma instância de processo comercial existente com base na empresa ID de definição de processo. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Considerações de fluxo do processo de negócios  
 Você pode definir fluxos de processo de negócios somente para as entidades que dão suporte a eles. Você também precisa estar ciente dos limites do número de processos, estágios e etapas que podem ser adicionados.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Fluxos de processos de negócios que chamam um fluxo de trabalho  
 Você pode chamar fluxos de trabalho sob demanda de dentro de um fluxo de processo de negócios. Você pode configurar isso no novo designer de fluxo de processo de negócios, arrastando um componente de fluxo de trabalho para um estágio de processo ou para a seção fluxos de trabalho globais. Para obter mais informações sobre como usar fluxos de trabalho em fluxos de processo de negócios, consulte [blog: automação de fluxo de processo empresarial no Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Quando você inclui um fluxo de trabalho que deseja disparar na saída do estágio de um estágio no fluxo do processo de negócios e esse estágio é o último estágio no fluxo, o designer dá a impressão de que o fluxo de trabalho será disparado quando esse estágio for concluído. No entanto, o fluxo de trabalho não será disparado porque uma transição de estágio não ocorre. Você não receberá um aviso ou um erro impedindo a inclusão do fluxo de trabalho no estágio. Quando um usuário interage com o fluxo do processo de negócios, concluir ou abandonar o processo não resulta em uma transição de estágio e, portanto, o fluxo de trabalho não é disparado. Considere os seguintes exemplos:  
  
-   Você cria um fluxo de processo de negócios com dois estágios, S1 se conecta a S2, com um fluxo de trabalho no estágio S2 e define o gatilho para a **saída do preparo**.  
  
-   Você cria um fluxo de processo de negócios com três estágios, S1 conecta-se a S2 e, em seguida, as ramificações S2 para S3. Você inclui um fluxo de trabalho em S2 e define o gatilho para a **saída de preparo**.  
  
 O fluxo de trabalho não será disparado em nenhum caso. Para contornar esse problema, você pode adicionar um fluxo de trabalho global e adicionar o fluxo de trabalho que deseja disparar para que o fluxo de trabalho seja disparado para o processo comercial em vez de um estágio do processo. Você pode definir o gatilho para um fluxo de trabalho global para processar abandonado ou o processo concluído para fazer com que o fluxo de trabalho seja disparado quando um usuário abandonar ou concluir o processo comercial.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entidades que podem usar fluxos de processo de negócios  
 Todas as entidades personalizadas podem usar fluxos de processo de negócios. As entidades padrão a seguir também podem usar fluxos de processo de negócios:  
  
-   Considerar  
-   Entrevistas  
-   Atividade  
-   Atividade de campanha  
-   Resposta da campanha  
-   Fornecedor  
-   Contactar  
-   Email  
-   Direito  
-   Fax  
-   Casos  
-   Fatura  
-   leva  
-   Letras  
-   Lista de marketing  
-   Oportunidade  
-   Chamada telefônica  
-   Remessa  
-   Item de lista de preços  
-   Citar  
-   Compromisso recorrente  
-   Literatura de vendas  
-   Atividade social  
-   Ordene  
-   Usuário  
-   Agenda  
-   Time  
  
 Para habilitar uma entidade personalizada para fluxos de processo de negócios, marque a caixa de seleção **fluxos de processo de negócios (campos serão criados)** na definição de entidade. Observe que não é possível desfazer essa ação.  
  
> [!NOTE]
>  Se você navegar até o estágio de fluxo do processo de negócios que contém a entidade `Social Activity` e escolher o botão **próximo estágio** , verá a opção **criar** . Quando você escolhe **criar**, o formulário **atividade social** é carregado. No entanto, como `Social Activity` não é válido para `Create` da interface do usuário do aplicativo, você não poderá salvar o formulário e verá a mensagem de erro: "erro inesperado".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de processos, estágios e etapas  
 Para garantir o desempenho aceitável e a usabilidade da interface do usuário, há algumas limitações que você precisa saber quando planeja usar fluxos de processo de negócios:  
  
-   Não pode haver mais de 10 processos de fluxo de processo de negócios ativados por entidade.  
  
-   Cada processo pode conter até 30 estágios.  
  
-   Processos de várias entidades não podem conter mais de cinco entidades.
  
## <a name="business-process-flow-entity-customization-support"></a>Suporte à personalização de entidade de fluxo de processos de negócios 

Introduzidos na atualização da versão 9,0 do Dynamics 365 (online), as entidades de fluxo do processo de negócios podem aparecer no sistema para que os dados de registro de entidade possam ser disponibilizados em grades, exibições, gráficos e painéis. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Usar registros de entidade de fluxo de processo de negócios com grades, exibições, gráficos e painéis

Com os fluxos de processos de negócios disponíveis como uma entidade, agora você pode usar localizações, exibições, gráficos e painéis avançados originados de dados de fluxo do processo de negócios para uma determinada entidade, como um cliente potencial ou uma oportunidade. Os administradores e os personalizadores de sistema podem criar grades de fluxo de processo de negócios, exibições, gráficos e painéis personalizados semelhantes àqueles criados com qualquer outra entidade.

Fluxos de processos de negócios, como o **processo de vendas de Lead to oportunidade**, aparecem como uma entidade personalizável no Gerenciador de soluções.

![Gerenciador de Soluções com entidade de processo de cliente potencial para oportunidade](media/bpf-lead-solution-explorer.png)

Para acessar uma exibição de fluxo de processo de negócios padrão, abra o Gerenciador de soluções, expanda **entidades** > expanda o processo desejado, como o **processo de vendas de cliente potencial para oportunidade**, selecione **exibições**e, em seguida, selecione a exibição desejada.

Várias exibições padrão estão disponíveis que você pode exibir como um gráfico, como o modo de exibição de **processo de vendas da oportunidade ativa** . 

![Exibição do processo de vendas da oportunidade ativa](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interagir com a entidade de fluxo do processo de negócios de um fluxo de trabalho
Você também pode interagir com entidades de fluxo de processo de negócios de um fluxo de trabalho. Por exemplo, você pode criar um fluxo de trabalho para o registro de entidade do fluxo de processos de negócios para alterar o estágio ativo quando um campo no registro de entidade da oportunidade for atualizado. Para obter mais informações sobre como fazer isso, consulte [automatizar estágios de fluxo de processo de negócios usando fluxos de trabalho](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>Limitações do uso de entidades de fluxo de processo de negócios

- No momento, você não pode criar formulários personalizados para entidades com base em um fluxo de processo de negócios.
- Se uma solução incluir uma entidade de fluxo de processo de negócios, a entidade de fluxo do processo de negócios deverá ser adicionada manualmente à solução antes de você exportá-la. Caso contrário, a entidade de fluxo do processo de negócios não será incluída no pacote de solução. Mais informações: [adicionar componentes da solução](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Próximas etapas  
 [Assista a um vídeo curto (4:49) sobre fluxos de processo de negócios](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Criar um  de fluxo de processo de negócios](create-business-process-flow.md)  
 [Aprimore os fluxos de processos de negócios com a ramificação](enhance-business-process-flows-branching.md) <br/>
 [Whitepaper: habilitação de processo com o Dynamics 365](https://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
