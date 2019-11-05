---
title: Criar um fluxo de processos de negócios no PowerApps | MicrosoftDocs
description: Saiba como criar um fluxo de processo de negócios
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3bd154935e06031b031432e10fa977f23e1a2c54
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546530"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Tutorial: criar um fluxo de processo comercial para padronizar processos
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este tutorial mostra como criar um fluxo de processo empresarial com o PowerApps. Para saber mais sobre por que você usa fluxos de processo de negócios, consulte [visão geral de fluxos de processos de negócios](business-process-flows-overview.md). Para obter informações sobre como criar um fluxo de tarefas móveis, consulte [criar um fluxo de tarefas móveis](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Quando um usuário inicia um fluxo de processo de negócios, os estágios e as etapas do processo são exibidos na barra de processos na parte superior de um formulário:  
  
 ![Processo comercial com estágios](media/business-process-stages.png "Processo comercial com estágios")  
  
 > [!TIP]
 >  Depois de criar uma definição de fluxo de processo de negócios, você pode fornecer controle sobre quem pode criar, ler, atualizar ou excluir a instância de fluxo do processo de negócios. Por exemplo, para processos relacionados ao serviço, você pode fornecer acesso completo aos representantes do serviço de atendimento ao cliente para alterar a instância do fluxo do processo de negócios, mas fornecer acesso somente leitura à instância para representantes de vendas para que possam monitorar as atividades de pós-vendas para seus utilizam. Para definir a segurança para uma definição de fluxo de processo de negócios que você criar, selecione **habilitar funções de segurança** na barra de ação.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Pré-requisitos

Você precisa do [plano de fluxo 2](https://preview.flow.microsoft.com/pricing/) para criar fluxos de processo de negócios. Alguns planos de licença do Dynamics 365 incluem o plano de fluxo 2.

## <a name="create-a-business-process-flow"></a>Criar um fluxo de processo de negócios  
  
1. Abra o [Gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. No painel de navegação à esquerda, selecione **processos**. 
  
3.  Na barra de ferramentas **ações** , selecione **novo**.  
  
4.  Na caixa de diálogo **criar processo** , preencha os campos obrigatórios:  
  
    -   Insira um nome de processo. O nome do processo não precisa ser exclusivo, mas deve ser significativo para as pessoas que precisam escolher um processo. Você pode alterar isso mais tarde.  
  
    -   Na lista **categoria** , selecione **fluxo de processo empresarial**.  
  
         Você não pode alterar a categoria depois de criar o processo.  
  
    -   Na lista **entidade** , selecione a entidade na qual você deseja basear o processo.  
  
         A entidade selecionada afeta os campos disponíveis para as etapas que podem ser adicionadas ao primeiro estágio do fluxo do processo. Se você não encontrar a entidade que deseja, verifique se a entidade tem a opção fluxos de processo de negócios (campos serão criados) definida na definição de entidade. Você não pode alterar isso depois de salvar o processo.  
  
5. Selecione **OK**.  
  
     O novo processo é criado e o designer de fluxo de processos de negócios é aberto com um único estágio já criado para você.  
  
 ![Janela de fluxo do processo de negócios mostrando elementos principais](media/business-process-flow-window-showing-main-elements.png "Janela de fluxo do processo de negócios mostrando elementos principais")  
  
6. **Adicionar estágios.** Se os usuários forem progredindo de um estágio de negócios para outro no processo:  
  
    1.  Arraste um componente de **estágio** da guia **componentes** e solte-o em um sinal de + no designer.  
  
        ![Arraste um estágio de processo de negócios](media/drag-business-process-stage.png "Arraste um estágio de processo de negócios")  
  
    2.  Para definir as propriedades de um estágio, selecione o estágio e, em seguida, defina as propriedades na guia **Propriedades** no lado direito da tela:  
  
        -   Insira um nome de exibição.  
  
        -   Se desejar, selecione uma categoria para o estágio.  A categoria (como **qualificar** ou **desenvolver**) aparece como uma divisa na barra de processos.  
  
            ![Divisa da barra de processos de negócios](media/business-process-bar-chevron.png "Divisa da barra de processos de negócios")  
  
        -   Quando terminar de alterar as propriedades, selecione o botão **aplicar** .  
  
7. **Adicione etapas a um estágio.** Para ver as etapas em um estágio, selecione **detalhes** no canto inferior direito do palco. Para adicionar mais etapas:  
  
    1.  Arraste o componente **etapa** para o estágio da guia **componentes** .  
  
        ![Adicionar etapa a um estágio em um processo de negócios](media/add-step-stage-business-process.png "Adicionar etapa a um estágio em um processo de negócios")  
  
    2.  Selecione a etapa e, em seguida, defina propriedades na guia **Propriedades** :  
  
        1.  Insira um nome de exibição para a etapa.  
  
        2.  Se você quiser que os usuários insiram dados para concluir uma etapa, selecione o campo apropriado na lista suspensa.  
  
        3.  Selecione **necessário** se as pessoas precisarem preencher o campo para concluir a etapa antes de passar para o próximo estágio do processo.  
  
        4.  Selecione **aplicar** quando terminar.  
  
8. **Adicione uma ramificação (condição) ao processo.** Para adicionar uma condição de ramificação:  
  
    1.  Arraste o componente **condição** da guia **componentes** para um sinal de + entre dois estágios.  
  
        ![Adicionar uma condição a um fluxo de processo de negócios](media/add-condition-business-process-flow.png "Adicionar uma condição a um fluxo de processo de negócios")  
  
    2.  Selecione a condição e, em seguida, defina propriedades na guia **Propriedades** . Para obter mais informações sobre as propriedades de ramificação, consulte [melhorar os fluxos de processos empresariais com a ramificação](enhance-business-process-flows-branching.md). Quando terminar de definir as propriedades para a condição, selecione **aplicar**.  
  
9. **Adicionar um fluxo de trabalho.** Para invocar um fluxo de trabalho:  
  
    1.  Arraste um componente de **fluxo de trabalho** da guia **componentes** para um estágio ou para o item de **fluxo de trabalho global** no designer.   A qual você o adiciona dependerá do seguinte:  
  
       - **Arraste-o para um estágio** quando desejar disparar o fluxo de trabalho na entrada ou sair do estágio. O componente de fluxo de trabalho deve ser baseado na mesma entidade principal que o estágio.  
  
       - **Arraste-o para o item de fluxo de trabalho global** quando desejar disparar o fluxo de trabalho quando o processo for ativado ou quando o processo for arquivado (quando o status for alterado para **concluído** ou **abandonado**). O componente de fluxo de trabalho deve ser baseado na mesma entidade primária que o processo.  
  
    2.  Selecione o fluxo de trabalho e, em seguida, defina propriedades na guia **Propriedades** :  
  
       1.  Insira um nome de exibição.  
  
       2.  Selecione quando o fluxo de trabalho deve ser disparado.  
  
       3.  Procure um fluxo de trabalho ativo sob demanda existente que corresponda à entidade de estágio ou crie um novo fluxo de trabalho selecionando **novo**.  
  
       4.  Selecione **aplicar** quando terminar.  
  
       Para obter mais informações sobre fluxos de trabalho, consulte [processos de fluxo de trabalho](../common-data-service/workflow-processes.md).  
  
10. Para validar o fluxo do processo de negócios, selecione **validar** na barra de ação.  
  
11. Para salvar o processo como um rascunho enquanto você continua a trabalhar nele, selecione **salvar** na barra de ação.  
  
    > [!IMPORTANT]
    >  Desde que um processo seja um rascunho, as pessoas não poderão usá-lo.  
  
12. Para ativar o processo e torná-lo disponível para sua equipe, selecione **Ativar** na barra de ação.  

13. Para fornecer controle sobre quem pode criar, ler, atualizar ou excluir a instância de fluxo do processo de negócios, selecione **Editar funções de segurança** na barra de comandos do designer. Por exemplo, para processos relacionados ao serviço, você pode fornecer acesso completo aos representantes do serviço de atendimento ao cliente para alterar a instância do fluxo do processo de negócios, mas fornecer acesso somente leitura à instância para representantes de vendas para que possam monitorar as atividades de pós-vendas para seus utilizam.

  Na tela **funções de segurança** , selecione o nome de uma função para abrir a página de informações da função de segurança. Selecione a guia fluxos de processo de negócios e, em seguida, atribua os privilégios apropriados no fluxo do processo de negócios para uma função de segurança.

  > [!NOTE]
  > O administrador do sistema e as funções de segurança do personalizador do sistema têm acesso a novos fluxos de processos de negócios por padrão.

   ![Atribuir privilégios a um fluxo de processo de negócios](media/bpf-assign-privileges.png)

  Especifique os privilégios selecionando os botões de opção apropriados e clique em salvar. Para obter mais informações sobre privilégios, consulte [privilégios de fluxo do processo de negócios](business-process-flows-overview.md#BKMK_MultipleBPF).

  Em seguida, não se esqueça de atribuir a função de segurança aos usuários apropriados em sua organização.

> [!TIP] 
>  Aqui estão algumas dicas para ter em mente enquanto você trabalha em seu fluxo de tarefas na janela do designer:  
>   
> - Para tirar um instantâneo de tudo na janela de fluxo do processo de negócios, selecione **instantâneo** na barra de ação. Isso é útil, por exemplo, se você quiser compartilhar e obter comentários sobre o processo de um membro da equipe.  
> - Use o mini-map para navegar rapidamente para partes diferentes do processo. Isso é útil quando você tem um processo complicado que rola para fora da tela.  
> - Para adicionar uma descrição para o processo comercial, selecione **detalhes** no nome do processo no canto esquerdo da janela fluxo do processo de negócios. Você pode usar até 2000 caracteres.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Editar um fluxo de processo de negócios  
 Para editar fluxos de processo de negócios, abra o Gerenciador de soluções, selecione **processos**e, em seguida, selecione o **fluxo do processo comercial** na lista de processos que você deseja editar.  
  
 Quando você seleciona o nome do fluxo do processo empresarial que deseja editar na lista de processos, ele é aberto no designer, onde você pode fazer as atualizações desejadas. Expanda **detalhes** sob o nome do processo para renomeá-lo ou adicionar uma descrição e exibir informações adicionais.  
  
 ![Seção de detalhes expandida de um fluxo de processo de negócios](media/business-process-flow-details.png "Seção de detalhes expandida de um fluxo de processo de negócios")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Outras coisas a saber sobre fluxos de processo de negócios
 **Editar estágios**  
Os fluxos de processos de negócios podem ter até 30 estágios.    
  
Você pode adicionar ou alterar as seguintes propriedades de um estágio:  
  
- **Nome do estágio**  
  
- **Entidade**. Você pode alterar a entidade para qualquer estágio, exceto a primeira.  
  
- **Categoria do estágio**. Uma categoria permite agrupar estágios por um tipo de ação. É útil para relatórios que agruparão registros pelo estágio em que estão. As opções para a categoria de estágio são provenientes do conjunto de opções globais da categoria de estágio. Você pode adicionar mais opções a esse conjunto de opções globais e alterar os rótulos das opções existentes, se desejar. Você também pode excluir essas opções, se desejar, mas é recomendável manter as opções existentes. Você não poderá adicionar exatamente a mesma opção se excluí-la. Se você não quiser que eles sejam usados, altere o rótulo para "não usar".  
  
- **Relação**. Insira uma relação quando o estágio anterior no processo for baseado em uma entidade diferente. Para o estágio que está sendo definido no momento, escolha **selecionar relações** para identificar uma relação a ser usada ao mover entre os dois estágios. É recomendável selecionar uma relação para os seguintes benefícios:  
  
    -   As relações geralmente têm mapas de atributos definidos que carregam automaticamente dados entre registros, minimizando a entrada de dados.  
  
    -   Quando você seleciona **próximo estágio** na barra de processos para um registro, todos os registros que usam a relação serão listados no fluxo do processo, promovendo assim a reutilização de registros no processo. Além disso, você pode usar fluxos de trabalho para automatizar a criação de registros para que o usuário simplesmente o Selecione em vez de criar um para simplificar ainda mais o processo.  
  
**Editar etapas**  
 Cada estágio pode ter até 30 etapas.    
  
**Adicionar ramificação**  
Para saber mais sobre como adicionar uma ramificação a um estágio, confira [melhorar os fluxos de processos empresariais com a ramificação](enhance-business-process-flows-branching.md).  
  
Para disponibilizar um fluxo de processo de negócios para as pessoas usarem, você deve solicitar o fluxo do processo, habilitar funções de segurança e ativá-lo.  
  
**Definir ordem de fluxo de processo**  
 Quando você tiver mais de um fluxo de processo de negócios para uma entidade (tipo de registro), precisará definir qual processo será atribuído automaticamente a novos registros. Na barra de comandos, selecione **pedido fluxo de processo**. Para novos registros ou registros que ainda não têm um fluxo de processo associado a eles, o primeiro fluxo do processo de negócios ao qual um usuário tem acesso é aquele que será usado.  
  
**Habilitar funções de segurança**  
Os usuários têm acesso a um fluxo de processo de negócios dependendo do privilégio definido no fluxo do processo de negócios na função de segurança atribuída ao usuário. 

Por padrão, somente as funções de segurança **administrador do sistema** e **personalizador de sistema** podem exibir um novo fluxo de processo comercial. 

Para especificar privilégios em um fluxo de processo de negócios, abra o fluxo do processo de negócios para edição e, em seguida, selecione **Editar funções de segurança** na barra de comandos do designer de fluxo de processos de negócios. Consulte a etapa 13 em [criar um fluxo de processo comercial](#create-a-business-process-flow) listado anteriormente neste tópico.
  
**Activate**  
Antes que qualquer pessoa possa usar o fluxo do processo de negócios, você deve ativá-lo. Na barra de comandos, selecione **Ativar**. Depois de confirmar a ativação, o fluxo do processo de negócios estará pronto para uso. Se um fluxo de processos de negócios tiver erros, você não poderá ativá-lo até que os erros sejam corrigidos.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Adicionar uma ação sob demanda a um fluxo de processo de negócios
A atualização da versão 9,0 do Dynamics 365 (online) apresenta um recurso de fluxo de processo de negócios: automação do fluxo de processos empresariais com etapas de ação. Você pode adicionar um botão a um fluxo de processo de negócios que disparará uma ação ou um fluxo de trabalho.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Adicionar fluxos de trabalho ou ações sob demanda usando uma etapa de ação
Suponha que, como parte do processo de qualificação de oportunidade, a organização Contoso exija que todas as oportunidades sejam revisadas por um revisor designado. Subsequentemente, a organização Contoso criou uma ação que: 

- Cria um registro de tarefa que é atribuído ao revisor de oportunidade. 
- Anexa "pronto para revisão" ao tópico da oportunidade. 

Além disso, a contoso precisa ser capaz de executar essas ações sob demanda. Para integrar essas tarefas ao processo de qualificação de oportunidade, as ações devem aparecer no fluxo do processo corporativo de oportunidade. Para habilitar essa funcionalidade, selecione **como uma etapa de ação de fluxo de processo de negócios**.
![disponível para execução como um fluxo de processo de negócios.](media/action-available-to-run.png)

Em seguida, a etapa de ação é adicionada ao fluxo do processo comercial de oportunidade da contoso. Em seguida, o fluxo do processo é validado e atualizado.

![Ação adicionada ao fluxo do processo comercial da oportunidade.](media/add-action-to-bpf.png)

Agora, os membros do Salesforce da Contoso podem iniciar a ação da etapa de processo comercial **qualificada** , sob demanda, selecionando **executar**.

![Executar ação.](media/action-execute.png)

> [!IMPORTANT]
> - Para poder executar uma ação ou um fluxo de trabalho sob demanda, o fluxo do processo de negócios deve incluir uma etapa de ação. Se a etapa de ação executar um fluxo de trabalho, o fluxo de trabalho deverá ser configurado para ser executado sob demanda.
> - A entidade associada à ação ou ao fluxo de trabalho deve ser a mesma que a entidade associada ao fluxo do processo de negócios.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitação do uso de etapas de ação em um fluxo de processo de negócios

- As ações não estarão disponíveis como etapas de ação se os parâmetros de entrada ou saída forem tipos de entidade, Entidadecollection ou OptionSet (lista de seleção). Ações com mais de um parâmetro de saída EntityReference ou qualquer número de parâmetros de entrada EntityReference não estão disponíveis como etapas de ação. As ações não associadas a uma entidade primária (ação global) não estão disponíveis como etapas de ação.

## <a name="instant-flows-in-business-process-flows"></a>Fluxos instantâneos em fluxos de processos de negócios

Você pode executar um **fluxo instantâneo** para automatizar tarefas repetitivas, gerar documentos, acompanhar aprovações e muito mais, de dentro de um estágio em um processo empresarial.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>Adicionar um fluxo instantâneo como uma etapa em um processo de negócios

Vamos supor que você venda impressoras e use o **processo de vendas de Lead to oportunidade** para fechar as negociações. Como parte desse processo, você gostaria que o líder da equipe revisasse e aprovasse as propostas que a equipe de vendas reuniu em um estágio anterior do fluxo do processo de negócios antes de compartilhá-la com o cliente.

Para fazer isso, você precisará fazer duas coisas:
1. Crie um fluxo instantâneo que solicite a revisão e a aprovação da proposta da equipe.
1. Adicione o fluxo instantâneo como uma etapa no **processo de vendas de Lead to oportunidade**.

> [!TIP]
> Somente os [fluxos com reconhecimento de solução](https://docs.microsoft.com/flow/overview-solution-flows) podem ser adicionados como uma etapa em um processo empresarial. 

### <a name="build-an-instant-flow"></a>Criar um fluxo instantâneo

1. Em Microsoft Flow, selecione **soluções** no menu de navegação.
1. Selecione **solução padrão** na lista de soluções que aparece. 
1. Selecione o menu **+ novo** e, em seguida, selecione **fluxo** na lista exibida.
1. Procure e selecione o conector de **Common Data Service** .
1. Procure e selecione o gatilho **quando um registro é selecionado** na lista de gatilhos de **Common Data Service** .
1. Defina **ambiente** como **padrão**e, em seguida, defina **nome da entidade** como **cliente potencial para o processo de vendas da oportunidade**.
1. Adicione um campo de entrada de texto para que o usuário insira o link para a proposta.

   ![Gatilho de fluxo instantâneo](media/instant-flow-trigger.png "Gatilho de fluxo instantâneo")

   Precisaremos de informações da instância do fluxo do processo de negócios para ajudar a fornecer contexto para a solicitação de aprovação, portanto, siga estas etapas para fazer isso.

1. Adicione a ação **analisar JSON** . 
1. Defina o **conteúdo** como **entidade** selecionando-o na lista de valores dinâmicos para o gatilho **quando um registro é selecionado** .
1. Cole o conteúdo a seguir no campo **esquema** .

    ```json
    {
        "type": "object",
        "properties": {
        "entity": {
            "type": "object",
            "properties": {
                "FlowsWorkflowLogId": {
                    "type": "string"
                },
                "BPFInstanceId": {
                    "type": "string"
                },
                "BPFInstanceEntityName": {
                    "type": "string"
                },
                "BPFDefinitionId": {
                    "type": "string"
                },
                "BPFDefinitionEntityName": {
                    "type": "string"
                },
                "StepId": {
                    "type": "string"
                },
                "BPFDefinitionName": {
                    "type": "string"
                },
                "BPFInstanceName": {
                    "type": "string"
                },
                "BPFFlowStageLocalizedName": {
                    "type": "string"
                },
                "BPFFlowStageEntityName": {
                    "type": "string"
                },
                "BPFFlowStageEntityCollectionName": {
                    "type": "string"
                },
                "BPFFlowStageEntityRecordId": {
                    "type": "string"
                },
                "BPFActiveStageId": {
                    "type": "string"
                },
                "BPFActiveStageEntityName": {
                    "type": "string"
                },
                "BPFActiveStageLocalizedName": {
                    "type": "string"
                }
            }
          }
        }
   }
   ```

   As coisas devem se parecer com isso agora:

   ![Analisar JSON](media/instant-flow-json-date.png "Analisar JSON")

  1. Adicione a ação **obter registro** do conector de **Common Data Service** .
  1. Defina o **ambiente** como **(atual)** , **nome da entidade** para **levar ao processo de vendas da oportunidade**e o identificador do **Item** para **BPFFlowStageEntityRecordID**.

     ![Adicionar um registro](media/instant-flow-add-record.png)

     Agora que temos os dados, defina o processo de aprovação adicionando a ação **Iniciar e aguardar uma aprovação (v2)** e, em seguida, preenchendo as informações relevantes. Saiba mais sobre [aprovações]( sequential-modern-approvals.md) se você não estiver familiarizado.

     > [!TIP]
     > - Use o seletor de conteúdo dinâmico para adicionar campos da ação **obter registro** para adicionar informações relevantes à solicitação de aprovação para que os Aprovadores possam saber facilmente o que é a solicitação. 
     > - Para fornecer mais contexto sobre o estágio ativo em que o processo de negócios está, adicione o campo **BPFActiveStageLocalizedName** da lista de valores dinâmicos.

     O **início e a espera de um cartão de aprovação (v2)** podem ter uma aparência semelhante a esta:

      ![Cartão de aprovação](media/instant-flow-add-approval-action.png)

1. Por fim, salve o fluxo e, em seguida, ative-o.

### <a name="add-this-flow-as-a-step-in-the-lead-to-opportunity-sales-process"></a>Adicione esse fluxo como uma etapa no processo de vendas de Lead to oportunidade.

Agora que você criou o fluxo instantâneo, tudo o que é necessário é que você o adicione ao fluxo do processo de negócios. 

1. Abra o **processo de vendas de cliente potencial para oportunidade** no designer de fluxo de processo de negócios. 
1. Arraste e solte a **etapa de fluxo (versão prévia)** da lista de **componentes** no estágio de **proposta** .
1. Em seguida, selecione o ícone de pesquisa no campo **selecionar um fluxo** para listar todos os fluxos que você pode adicionar a um fluxo de processo de negócios.
1. Selecione um fluxo na lista e salve as alterações selecionando o botão **aplicar** na parte inferior do painel Propriedades.
1. Por fim, selecione o botão **Atualizar** para tornar este fluxo de processo comercial com sua nova etapa de fluxo instantânea disponível para seus usuários.
  
## <a name="next-steps"></a>Próximas etapas

 - [Visão geral dos fluxos de processos de negócios](business-process-flows-overview.md)  
 - [Aprimore os fluxos de processos de negócios com a ramificação](enhance-business-process-flows-branching.md)
 - [Visão geral das aprovações](sequential-modern-approvals.md)
 - [Etapas detalhadas para adicionar um fluxo instantâneo a um fluxo de processo de negócios](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


