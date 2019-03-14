---
title: Visão geral dos fluxos de processo empresarial | Microsoft Docs
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
- PowerApps
ms.assetid: 4469877e-bb95-481a-bc52-c9746f937ce5
caps.latest.revision: 16
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1e23a3ddfd4302c4a5429029ea4fb47f0ab9808
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462983"
---
# <a name="business-process-flows-overview"></a>Visão geral dos fluxos de processo empresarial

Você pode ajudar a garantir que as pessoas insiram dados de forma consistente e sigam as mesmas etapas toda vez que elas funcionarem com um cliente ao criar um fluxo de processo empresarial. Por exemplo, você pode desejar criar um fluxo de processo empresarial para que todos os usuários tratem as solicitações de serviço do cliente da mesma forma, ou para exigir que as pessoas obtenham aprovação para uma fatura antes de enviar um pedido. Fluxos de processo empresarial usam a mesma tecnologia subjacente que outros processos, mas as funcionalidades que eles fornecem são muito diferentes de outros recursos que usam processos. Para saber como criar ou editar um fluxo de processo empresarial, consulte [Criar um fluxo de processo empresarial](create-business-process-flow.md).  
  
 [Assista a um vídeo curto (4:49) sobre fluxos de processo empresarial.](https://go.microsoft.com/fwlink/p/?linkid=842226)  
  
<a name="BKMK_Why"></a>   
## <a name="why-use-business-process-flows"></a>Quando usar os fluxos de processo empresarial?  
Os fluxos de processo empresarial fornecem um guia para as pessoas realizarem o trabalho. Eles fornecem uma experiência de usuário simplificada que guia as pessoas por meio de processos definidos pela organização para interações que precisam ser adiantadas até uma conclusão de algum tipo. Essa experiência de usuário pode ser adaptada para que as pessoas com diferentes funções de segurança possam ter uma experiência que seja mais bem adequado ao trabalho realizado.  
  
 Use fluxos de processo empresarial para definir um conjunto de etapas para as pessoas seguirem para obtenção de um resultado desejado. Estas etapas fornecem um indicador visual que informa às pessoas onde elas estão no processo empresarial. Os fluxos de processo empresarial reduzem a necessidade de treinamento porque novos usuários não precisam se concentrar em qual entidade devem estar usando. Eles podem deixar que o processo os oriente. Você pode configurar fluxos de processo empresarial para dar suporte a metodologias de vendas comuns que podem ajudar seus grupos de vendas a obter resultados melhores. Para grupos de serviço, os fluxos de processo empresarial podem ajudar a nova equipe a começar a trabalhar mais rapidamente e evitar erros que poderiam resultar em clientes insatisfeitos.  
  
<a name="BKMK_What"></a>   
## <a name="what-can-business-process-flows-do"></a>O que os fluxos de processo empresarial podem fazer?  
 Com os fluxos de processo empresarial, você pode definir um conjunto de *estágios* e *etapas* que são exibidos em um controle na parte superior do formulário.  
  
 ![Processo empresarial com estágios](media/business-process-stages.png "Processos empresarial com estágios")  
  
 Cada estágio contém um grupo de etapas. Cada etapa representa um campo no qual os dados podem ser inseridos. As pessoas avançam para o próximo estágio usando o botão **Próximo estágio**. Você pode tornar uma etapa necessária para que as pessoas insiram dados no campo correspondente antes de prosseguirem para o próximo estágio. Isso é comumente chamado de "controle de estágio".  
  
 Os fluxos de processo empresarial parecem relativamente simples em comparação a outros tipos de processos, porque eles não fornecem qualquer lógica de negócios condicional ou automação além de fornecer a experiência simplificada para entrada de dados e controle da entrada em estágios. No entanto, quando combiná-los com outros processos e personalizações, eles podem desempenhar um papel importante na economia de tempo das pessoas, reduzindo os custos de treinamento e aumentando a adoção do usuário.  

<a name="BKMK_BPFwithOtherCustomizations"></a>   
### <a name="business-process-flows-integrated-with-other-customizations"></a>Fluxos de processo empresarial integrados a outras personalizações  
 Quando você ou o usuário insere dados usando fluxos de processo empresarial, as alterações de dados também são aplicadas aos campos de formulário para que qualquer automação fornecida pelas regras de negócios ou scripts de formulário possam ser aplicadas imediatamente. As etapas podem ser adicionadas para definir valores para os campos que não estão presentes no formulário e esses campos serão adicionados ao modelo de objeto `Xrm.Page` usado para scripts de formulário. Qualquer fluxo de trabalho que é iniciado por alterações nos campos incluídos em um fluxo de processo empresarial será aplicado quando os dados no formulário forem salvos. Se a automação for aplicada por um fluxo de trabalho em tempo real, as alterações serão imediatamente visíveis para o usuário quando os dados no formulário forem atualizados depois que o registro for salvo.  
  
 Embora o controle de fluxo do processo empresarial no formulário não forneça qualquer programação direta do lado do cliente, as alterações aplicadas por regras de negócio ou scripts de formulário são aplicadas automaticamente aos controles de fluxo do processo empresarial. Se você ocultar um campo em um formulário, esse campo também será ocultado no controle de fluxo de processo empresarial. Se você definir um valor usando as regras de negócios ou scripts de formulário, esse valor será definido no fluxo do processo empresarial.  
  
### <a name="concurrent-process-flows"></a>Fluxos de processos simultâneos  
 Os fluxos de processo empresarial simultâneos permitem que os personalizadores configurem vários processos empresariais e façam a associação com o mesmo registro inicial. Os usuários podem alternar entre vários processos empresariais em execução simultaneamente e retomar seu trabalho no estágio do processo em que estavam.  
  
<a name="BKMK_SystemBPF"></a>   
### <a name="system-business-process-flows"></a>Fluxos de processo empresarial do sistema  
 Os seguintes fluxos de processo empresarial são incluídos. Para entender como os fluxos do processo empresarial funcionam, examine esses fluxos do processo empresarial do sistema:  
  
-   Processo de vendas do cliente potencial à oportunidade  
  
-   Processo de vendas da oportunidade  
  
-   Processo de chamada ao caso  
  
<a name="BKMK_multipleEntities"></a>   
## <a name="multiple-entities-in-business-process-flows"></a>Várias entidades nos fluxos de processo empresarial  
 Você pode usar um fluxo de processo empresarial para uma única entidade ou abranger várias entidades. Por exemplo, você pode ter um processo que comece com uma oportunidade, em seguida, continuar para uma cotação, um pedido e, em seguida, uma fatura, antes de, finalmente, retornar para fechar a oportunidade.  
  
 Você pode criar fluxos de processo empresarial que unem os registros para até cinco entidades diferentes em um único processo para que as pessoas que usam o aplicativo possam se concentrar no fluxo de seus processos em vez de na entidade em que estão trabalhando. Eles podem navegar mais facilmente entre os registros de entidade relacionados.  
  
<a name="BKMK_MultipleBPF"></a>   
## <a name="multiple-business-process-flows-are-available-per-entity"></a>Vários fluxos de processo empresarial estão disponíveis por entidade  
 Nem todos os usuários em uma organização podem seguir o mesmo processo e condições diferentes podem exigir que um processo diferente seja aplicado. Você pode ter até 10 fluxos de processo empresarial ativos por entidade para fornecer processos apropriados para diferentes situações.  
  
<a name="BPF_controlsWhichBPF"></a>   
### <a name="control-which-business-process-flow-will-be-applied"></a>Controle qual fluxo de processo empresarial será aplicado  
 Você pode associar fluxos de processo empresarial com funções de segurança para que somente pessoas com essas funções de segurança possam ver ou usá-los. Você também pode definir a ordem dos fluxos de processo empresarial para que possa controlar qual fluxo de processo empresarial será definido por padrão. Isso funciona da mesma forma que vários formulários para uma entidade são definidos.  
  
 Quando alguém cria um novo registro de entidade, a lista de definição de processo empresarial ativa disponível é filtrada por função de segurança do usuário. A primeira definição de processo empresarial ativada disponível para a função de segurança do usuário de acordo com a lista de ordem de processo é aquela que é aplicada por padrão. Se mais de uma definição de processo empresarial ativa estiver disponível, os usuários poderão carregar outra na caixa de diálogo Alternar processo. Sempre que os processos forem alternados, o que estiver renderizado no momento ficará em segundo plano e será substituído por um selecionado, mas manterá seu estado e poderá ser alternado de volta. Cada registro pode ter várias instâncias do processo associadas (cada um para uma definição de fluxo de processo empresarial diferente, até um total de 10). No carregamento do formulário, apenas o fluxo do processo empresarial é renderizado. Quando qualquer usuário aplicar um processo diferente, esse processo poderá ser carregado apenas por padrão para esse usuário.  
  
 Para certificar-se de que um processo empresarial é carregado por padrão para todos os usuários (comportamento equivalente a "fixar" o processo), um script de API personalizada do cliente (recurso da Web) pode ser adicionado no carregamento de formulário que especificamente carrega uma instância do processo empresarial existente com base na ID de definição do processo empresarial. 
 
  
<a name="BKMK_Considerations"></a>   
## <a name="business-process-flow-considerations"></a>Considerações sobre o fluxo de processo empresarial  
 Você pode definir fluxos de processo empresarial somente para as entidades que dão suporte a eles. Você também precisa estar ciente dos limites para o número de processos, estágios e etapas que podem ser adicionados.  
  
### <a name="business-process-flows-that-call-a-workflow"></a>Fluxos de processo empresarial que chamam um fluxo de trabalho  
 Você pode chamar fluxos de trabalho sob demanda de dentro de um fluxo de processo empresarial. Você pode configurar isso por meio do novo designer do fluxo de processo empresarial ao arrastar o componente de fluxo de trabalho a um estágio do processo ou à seção de fluxos de trabalho globais. Para obter mais informações sobre como usar fluxos de trabalho em fluxos de processo empresarial, consulte [Blog: Automação de fluxo de processo empresarial no Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/).  
  
 Quando você inclui um fluxo de trabalho que deseja disparar na saída do estágio de um estágio em seu fluxo de processo empresarial e esse estágio é o último estágio no fluxo, o designer fornece a impressão de que o fluxo de trabalho será disparado quando o estágio estiver concluído. No entanto, o fluxo de trabalho não será disparado porque uma transição de estágio não será realizada. Você não receberá um aviso ou erro que evitará que você inclua o fluxo de trabalho no estágio. Quando um usuário interage com o fluxo do processo empresarial, concluir ou abandonar o processo não resulta em uma transição de estágio e, portanto, o fluxo de trabalho não será disparado. Considere os exemplos a seguir:  
  
-   Crie um fluxo de processo empresarial com dois estágios, S1 conectado a S2, com um fluxo de trabalho no estágio S2, e defina o gatilho como **Saída do estágio**.  
  
-   Crie um fluxo de processo empresarial com três estágios, S1 conectado a S2 e, depois, S2 ramificado em S3. Inclua um fluxo de trabalho em S2 e defina o gatilho como **Saída do estágio**.  
  
 O fluxo de trabalho não disparará em ambos os casos. Para contornar esse problema, você pode adicionar um fluxo de trabalho global e adicionar o fluxo de trabalho que deseja disparar a ele para que o fluxo de trabalho seja disparado para o processo empresarial em vez de um estágio do processo. Você pode definir o gatilho para um fluxo de trabalho global para o processo abandonado ou concluído para fazer com que o fluxo de trabalho seja disparado quando um usuário abandonar ou concluir o processo empresarial.  
  
<a name="BKMK_Entities"></a>   
### <a name="entities-that-can-use-business-process-flows"></a>Entidades que podem usar fluxos de processo empresarial  
 Todas as entidades personalizadas podem usar fluxos de processo empresarial. As seguintes entidades padrão também podem usar os fluxos de processo empresarial:  
  
-   Conta  
-   Compromisso  
-   Campanha  
-   Atividade da campanha  
-   Resposta da campanha  
-   Concorrente  
-   Contato  
-   Email  
-   Direito  
-   Fax  
-   Caso  
-   Fatura  
-   Cliente potencial  
-   Carta  
-   Lista de marketing  
-   Oportunidade  
-   Chamada telefônica  
-   Produto  
-   Item da lista de preços  
-   Cotação  
-   Compromisso recorrente  
-   Literatura de vendas  
-   Atividade social  
-   Pedido  
-   Usuário  
-   Tarefa  
-   Equipe  
  
 Para habilitar uma entidade personalizada para fluxos de processo empresarial, marque a caixa de seleção **Fluxos de processo empresarial (campos serão criados)** na definição de entidade. Observe que você não pode desfazer essa ação.  
  
> [!NOTE]
>  Se você navegar para o estágio de fluxo de processo empresarial que contém a entidade `Social Activity` e escolher o botão **Próximo estágio**, você verá a opção **Criar**. Quando você escolhe **Criar**, o formulário **Atividade social** é carregado. No entanto, como `Social Activity` não é válido para `Create` na interface do usuário do aplicativo, você não poderá salvar o formulário e você verá a mensagem de erro: "Erro inesperado".  
  
<a name="BPF_MaxNumbers"></a>   
### <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de processos, estágios e etapas  
 Para garantir um desempenho aceitável e a usabilidade da interface do usuário, há algumas limitações das quais você precisa estar ciente ao planejar usar fluxos de processo empresarial:  
  
-   Não pode haver mais de 10 processos de fluxo de processo empresarial ativados por entidade.  
  
-   Cada processo pode conter não mais do que 30 estágios.  
  
-   Os processos de várias entidades podem conter não mais do que cinco entidades.
  
## <a name="business-process-flow-entity-customization-support"></a>Suporte à personalização de entidade de fluxo do processo empresarial 

Lançadas no Dynamics 365 (online), atualização de versão 9.0, as entidades do processo empresarial podem aparecer no sistema para que os dados de registro de entidade possam ser disponibilizados em grades, exibições, gráficos e painéis. 

### <a name="use-business-process-flow-entity-records-with-grids-views-charts-and-dashboards"></a>Usar registros de entidade de fluxo de processo empresarial com grades, exibições, gráficos e painéis

Com os fluxos de processo empresarial disponíveis como uma entidade, agora você pode usar localizações avançadas, exibições, gráficos e painéis originados de dados de fluxo de processo empresarial para uma determinada entidade, como um cliente potencial ou uma oportunidade. Os personalizadores e os administradores do sistema podem criar grades, exibições, gráficos e painéis de fluxo de processo empresarial personalizados similares àqueles criados com qualquer outra entidade.

Fluxos de processo empresarial, como **Processo e vendas do cliente potencial à oportunidade**, aparecem como uma entidade personalizável no gerenciador de soluções.

![Gerenciador de soluções com a entidade do processo de cliente potencial à oportunidade](media/bpf-lead-solution-explorer.png)

Para acessar uma exibição de fluxo do processo empresarial padrão, abra o gerenciador de soluções, expanda **Entidades** > expanda o processo que você deseja, como **Processo de vendas do cliente potencial à oportunidade**, selecione **Exibições** e, em seguida, selecione a exibição que você deseja.

Várias exibições padrão estão disponíveis para você exibir como um gráfico, como a exibição **Processo de vendas de oportunidade ativo**. 

![Exibição do processo de vendas de oportunidade ativo](media/bpf-default-view.png)

### <a name="interact-with-the-business-process-flow-entity-from-a-workflow"></a>Interagir com a entidade de fluxo do processo empresarial de um fluxo de trabalho
Você também pode interagir com as entidades de fluxo do processo empresarial de um fluxo de trabalho. Por exemplo, você pode criar um fluxo de trabalho para o registro de entidade do fluxo do processo empresarial para alterar o estágio ativo quando um campo no registro de entidade de oportunidade for atualizado. Para obter mais informações sobre como fazer isso, consulte [Automatizar estágios de fluxo de processo empresarial usando fluxos de trabalho](https://blogs.msdn.microsoft.com/crminthefield/2017/12/18/automate-business-process-flow-stages-using-workflows).


### <a name="limitations-of-using-business-process-flow-entities"></a>Limitações do uso de entidades de fluxo de processo empresarial

- Atualmente, é possível criar formulários personalizados para entidades com base em um fluxo de processo de empresarial.
- Se uma solução inclui uma entidade de fluxo de processo empresarial, a entidade de fluxo de processo empresarial deve ser adicionada manualmente à solução antes de você exportá-la. Caso contrário, a entidade de fluxo de processo empresarial não será incluída no pacote de solução. Mais informações: [Adicionar componentes da solução](/powerapps/maker/model-driven-apps/create-solution#add-solution-components)

### <a name="next-steps"></a>Próximas etapas  
 [Assista a um vídeo curto (4:49) sobre fluxos de processo empresarial](https://go.microsoft.com/fwlink/p/?linkid=842226)   
 [Criar um fluxo de processo empresarial](create-business-process-flow.md)   
 [Aperfeiçoar os fluxos de processo empresarial com ramificação](enhance-business-process-flows-branching.md) <br/>
 [White paper: Habilitação de processo com o Dynamics 365](http://download.microsoft.com/download/C/3/B/C3B46E35-9445-43B9-800B-474E022EE352/Process%20Enablement%20with%20Microsoft%20Dynamics%20CRM%202013.pdf)</br>
