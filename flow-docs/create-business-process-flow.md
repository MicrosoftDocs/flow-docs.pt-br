---
title: Criar um fluxo de processo empresarial no PowerApps | Microsoft Docs
description: Saiba como criar um fluxo de processo empresarial
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 33ae71ea6b0af6a94021f5b0a02690aae21f0043
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64458412"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Tutorial: Criar um fluxo de processo empresarial para padronizar processos

Este tutorial mostra como criar um fluxo de processo empresarial com o PowerApps. Para saber mais sobre por que você usa fluxos de processos empresariais, consulte [Visão geral de fluxos de processos empresariais](business-process-flows-overview.md). Para obter informações sobre como criar um fluxo de tarefas móvel, consulte [Criar um fluxo de tarefas móvel](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Quando um usuário inicia um fluxo de processo empresarial, os estágios e etapas do processo são exibidos na barra de processos na parte superior de um formulário:  
  
 ![Processo empresarial com estágios](media/business-process-stages.png "Processos empresarial com estágios")  
  
 > [!TIP]
 >  Após criar uma definição de fluxo de processo empresarial, será possível fornecer controle sobre quem pode criar, ler, atualizar ou excluir a instância do fluxo de processo empresarial. Por exemplo, para processos relacionados a serviços, você pode fornecer acesso completo para repositórios de atendimento ao cliente para alterar a instância do fluxo de processo empresarial, mas fornecer acesso somente leitura à instância para os representantes de vendas para que eles possam monitorar atividades de pós-venda para seus clientes. Para definir segurança para uma definição de fluxo de processo empresarial criada, selecione **Habilitar funções de segurança** na barra de ações.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Pré-requisitos

É necessário ter o [Microsoft Flow (Plano 2)](https://preview.flow.microsoft.com/pricing/) para criar fluxos de processos empresariais. Alguns planos de licença do Dynamics 365 incluem o Microsoft Flow (Plano 2).

## <a name="create-a-business-process-flow"></a>Criar um fluxo de processo empresarial  
  
1. Abra o [Gerenciador de Soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. No painel de navegação esquerdo, selecione **Processos**. 
  
3.  Na barra de ferramentas **Ações**, selecione **Novo**.  
  
4.  Na caixa de diálogo **Criar processo**, preencha os campos obrigatórios:  
  
    -   Insira um nome de processo. O nome do processo não precisa ser único, mas deve ser significativo para pessoas que precisam escolher um processo. É possível alterar isso posteriormente.  
  
    -   Na lista **Categoria**, selecione **Fluxo de processo empresarial**.  
  
         Não será possível alterar a categoria após criar o processo.  
  
    -   Na lista **Entidade**, selecione a entidade na qual você deseja basear o processo.  
  
         A entidade selecionada afeta os campos disponíveis para as etapas que podem ser adicionadas ao primeiro estágio do fluxo do processo. Se você não encontrar a entidade desejada, verifique se a entidade tem a opção Fluxos de processos empresariais (os campos serão criados) definida na definição de entidade. Não é possível alterar isso após salvar o processo.  
  
5. Selecione **OK**.  
  
     O novo processo é criado, e o designer do fluxo de processo empresarial é aberto com um único estágio já criado para você.  
  
 ![Janela do fluxo de processo empresarial mostrando os principais elementos](media/business-process-flow-window-showing-main-elements.png "Janela do fluxo de processo empresarial mostrando os principais elementos")  
  
6. **Adicionar estágios.** Se os usuários progredirem de um estágio de negócios para outro no processo:  
  
    1.  Arraste um componente **Estágio** da guia **Componentes** e solte-o em um sinal de + no designer.  
  
        ![Arrastar um estágio do processo empresarial](media/drag-business-process-stage.png "Arrastar um estágio do processo empresarial")  
  
    2.  Para definir as propriedades de um estágio, selecione o estágio e defina as propriedades na guia **Propriedades** do lado direito da tela:  
  
        -   Insira um nome de exibição.  
  
        -   Se desejado, selecione uma categoria para o estágio.  A categoria (como **Qualificar** ou **Desenvolver**) é exibida como uma divisa na barra de processos.  
  
            ![Divisa da barra de processos empresariais](media/business-process-bar-chevron.png "Divisa da barra de processos empresariais")  
  
        -   Quando você terminar a alteração de propriedades, selecione o botão **Aplicar**.  
  
7. **Adicionar etapas a um estágio.** Para ver as etapas em um estágio, selecione **Detalhes** no canto inferior direito do estágio. Para adicionar mais etapas:  
  
    1.  Arraste o componente **Etapa** para o estágio da guia **Componentes**.  
  
        ![Adicionar uma etapa a um estágio em um processo empresarial](media/add-step-stage-business-process.png "Adicionar uma etapa a um estágio em um processo empresarial")  
  
    2.  Selecione a etapa e, em seguida, defina propriedades na guia **Propriedades**:  
  
        1.  Insira um nome de exibição para a etapa.  
  
        2.  Se desejar que os usuários insiram dados para concluir uma etapa, selecione o campo adequado na lista suspensa.  
  
        3.  Selecione **Obrigatório** se as pessoas devem preencher o campo para concluir a etapa antes de passar para o próximo estágio do processo.  
  
        4.  Selecione **Aplicar** quando terminar.  
  
8. **Adicionar um branch (condição) ao processo.** Para adicionar uma condição de ramificação:  
  
    1.  Arraste o componente **Condição** da guia **Componentes** até um sinal de + entre dois estágios.  
  
        ![Adicionar uma condição a um fluxo de processo empresarial](media/add-condition-business-process-flow.png "Adicionar uma condição a um fluxo de processo empresarial")  
  
    2.  Selecione a condição e, em seguida, defina propriedades na guia **Propriedades**. Para obter mais informações sobre propriedades de ramificação, consulte [Aperfeiçoar os fluxos de processos empresariais com ramificação](enhance-business-process-flows-branching.md). Quando terminar de definir propriedades para a condição, selecione **Aplicar**.  
  
9. **Adicionar um fluxo de trabalho.** Para invocar um fluxo de trabalho:  
  
    1.  Arraste um componente **Fluxo de trabalho** da guia **Componentes** para um estágio ou até o item **Fluxo de trabalho global** no designer.   Ao qual você o adiciona depende do seguinte:  
  
       - **Arraste-o para um estágio** quando desejar disparar o fluxo de trabalho na entrada ou saída do estágio. O componente de fluxo de trabalho deve estar baseado na mesma entidade primária que o estágio.  
  
       - **Arraste-o para o item de fluxo de trabalho global** quando desejar disparar o fluxo de trabalho quando o processo for ativado ou quando o processo for arquivado (quando o status mudará para **Concluído** ou **Abandonado**). O componente de fluxo de trabalho deve estar baseado na mesma entidade primária que o processo.  
  
    2.  Selecione o fluxo de trabalho e, em seguida, defina propriedades na guia **Propriedades**:  
  
       1.  Insira um nome de exibição.  
  
       2.  Selecione quando o fluxo de trabalho deve ser disparado.  
  
       3.  Pesquise um fluxo de trabalho ativo sob demanda existente que corresponda à entidade de estágio ou crie um novo fluxo de trabalho selecionando **Novo**.  
  
       4.  Selecione **Aplicar** quando terminar.  
  
       Para obter mais informações sobre fluxos de trabalho, consulte [Processos de fluxos de trabalho](../common-data-service/workflow-processes.md).  
  
10. Para validar o fluxo de processo empresarial, selecione **Validar** na barra de ações.  
  
11. Para salvar o processo como um rascunho enquanto você continua trabalhando nele, selecione **Salvar** na barra de ações.  
  
    > [!IMPORTANT]
    >  Desde que um processo seja um rascunho, as pessoas não poderão usá-lo.  
  
12. Para ativar o processo e disponibilizá-lo à sua equipe, selecione **Ativar** na barra de ações.  

13. Para fornecer controle sobre quem pode criar, ler, atualizar ou excluir a instância de fluxo de processo empresarial, selecione **Editar funções de segurança** na barra de comandos do designer. Por exemplo, para processos relacionados a serviços, você pode fornecer acesso completo para repositórios de atendimento ao cliente para alterar a instância do fluxo de processo empresarial, mas fornecer acesso somente leitura à instância para os representantes de vendas para que eles possam monitorar atividades de pós-venda para seus clientes.

  Na tela **Funções de segurança**, selecione o nome de uma função para abrir a página de informações da função de segurança. Selecione a guia Fluxos de processos empresariais e, em seguida, atribua os privilégios adequados no fluxo de processo empresarial para uma função de segurança.

  > [!NOTE]
  > As funções de segurança Administrador do sistema e Personalizador do sistema têm acesso aos novos fluxos de processos empresariais por padrão.

   ![Atribuir privilégios a um fluxo de processo empresarial](media/bpf-assign-privileges.png)

  Especifique privilégios selecionando os botões de opção adequados e clique em Salvar. Para obter mais informações sobre privilégios, consulte [Business process flow privileges](business-process-flows-overview.md#BKMK_MultipleBPF) (Privilégios do fluxo de processo empresarial).

  Em seguida, não se esqueça de atribuir a função de segurança aos usuários adequados em sua organização.

> [!TIP] 
>  Veja algumas dicas a se ter em mente enquanto você trabalha em seu fluxo de tarefas na janela do designer:  
>   
> - Para tirar um instantâneo de tudo na janela do fluxo de processo empresarial, selecione **Instantâneo** na barra de ações. Isso é útil, por exemplo, se você deseja compartilhar e obter comentários sobre o processo de um membro da equipe.  
> - Use o minimapa para navegar rapidamente até diferentes partes do processo. Isso é útil quando você tem um processo complicado que desliza na tela.  
> - Para adicionar uma descrição do processo empresarial, selecione **Detalhes** no nome do processo no canto esquerdo da janela do fluxo de processo empresarial. É possível usar até 2000 caracteres.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Editar um fluxo de processo empresarial  
 Para editar fluxos de processos empresariais, abra o Gerenciador de Soluções, selecione **Processos** e, em seguida, selecione o **Fluxo de processo empresarial** na lista de processos que você deseja editar.  
  
 Ao selecionar o nome do fluxo de processo empresarial que você deseja editar na lista de processos, ele será aberto no designer, em que você poderá fazer as atualizações que desejar. Expanda **Detalhes** embaixo do nome do processo para renomeá-lo ou adicione uma descrição e exiba mais informações.  
  
 ![Seção expandida de detalhes de um fluxo de processo empresarial](media/business-process-flow-details.png "Seção expandida de detalhes de um fluxo de processo empresarial")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Outras coisas que você deve saber sobre fluxos de processos empresariais
 **Editar estágios**  
Fluxos de processos empresariais podem ter até 30 estágios.    
  
É possível adicionar ou alterar as seguintes propriedades de um estágio:  
  
- **Nome do estágio**  
  
- **Entidade**. É possível alterar a entidade de qualquer estágio, exceto o primeiro.  
  
- **Categoria do estágio**. Uma categoria permite agrupar estágios por um tipo de ação. É útil para relatórios que agruparão registros pelo estágio em que eles estão. As opções da categoria do estágio são provenientes do conjunto de opções globais Categoria do estágio. Será possível adicionar mais opções a esse conjunto de opções globais e alterar os rótulos das opções existentes se desejar. Também será possível excluir essas opções, se desejar, mas recomendamos que você mantenha as opções existentes. Não será possível adicionar a mesma opção de volta se você excluí-la. Se não desejar que sejam usadas, altere o rótulo para "Não usar".  
  
- **Relação**. Insira uma relação quando o estágio anterior no processo for baseado em uma entidade diferente. Para o estágio que está sendo definido no momento, escolha **Selecionar relações** para identificar uma relação a ser usada ao mover entre os dois estágios. É recomendável selecionar uma relação pelos seguintes benefícios:  
  
    -   Relações geralmente têm mapas de atributo definidos que transferem dados automaticamente entre registros, minimizando a entrada de dados.  
  
    -   Quando você seleciona **Próximo estágio** na barra de processos para um registro, quaisquer registros que usam a relação serão listados no fluxo de processo, promovendo, assim, a reutilização de registros no processo. Além disso, é possível usar os fluxos de trabalho para automatizar a criação de registros para o usuário simplesmente selecioná-lo, em vez de criar um para simplificar ainda mais o processo.  
  
**Editar etapas**  
 Cada estágio pode ter até 30 etapas.    
  
**Adicionar branch**  
Para saber como adicionar um branch a um estágio, consulte [Aperfeiçoar os fluxos de processos empresariais com ramificação](enhance-business-process-flows-branching.md).  
  
Para tornar um fluxo de processo empresarial disponível para ser usado pelas pessoas, é necessário ordenar o fluxo de processo, habilitar funções de segurança e ativá-lo.  
  
**Definir a ordem do fluxo do processo**  
 Quando você tiver mais de um fluxo de processo empresarial para uma entidade (tipo de registro), será necessário definir qual processo será atribuído automaticamente a novos registros. Na barra de comandos, selecione **Ordenar fluxo de processo**. Para novos registros ou recursos que ainda não têm um fluxo de processo associado a eles, o primeiro fluxo de processo empresarial ao qual um usuário tem acesso é o que será usado.  
  
**Habilitar funções de segurança**  
Os usuários têm acesso a um fluxo de processo empresarial que depende do privilégio definido no fluxo de processo empresarial na função de segurança atribuída ao usuário. 

Por padrão, somente as funções de segurança **Administrador do sistema** e **Personalizador do sistema** podem exibir um novo fluxo de processo empresarial. 

Para especificar privilégios em um fluxo de processo empresarial, abra o fluxo de processo empresarial para edição e, em seguida, selecione **Editar funções de segurança** na barra de comandos do designer do fluxo de processo empresarial. Consulte a etapa 13 em [Criar um fluxo de processo empresarial](#create-a-business-process-flow) listada anteriormente neste tópico.
  
**Ativar**  
Antes de que qualquer pessoa possa usar o fluxo de processo empresarial, é necessário ativá-lo. Na barra de comandos, selecione **Ativar**. Após confirmar a ativação, o fluxo de processo empresarial está pronto para uso. Se um fluxo de processo empresarial tiver erros, não será possível ativá-lo até que os erros sejam corrigidos.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Adicionar uma ação sob demanda a um fluxo de processo empresarial
A atualização do Dynamics 365 (online), versão 9.0 apresenta um recurso de fluxo de processo empresarial: automação do fluxo de processo empresarial com Etapas de ação. É possível adicionar um botão a um fluxo de processo empresarial que disparará uma ação ou fluxo de trabalho.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Adicionar fluxos de trabalho ou ações sob demanda usando uma etapa de ação
Suponha que, como parte do processo de qualificação de oportunidade, a organização Contoso requer que todas as oportunidades sejam revisadas por um revisor designado. Subsequentemente, a organização Contoso criou uma ação que: 

- Cria um registro de tarefa atribuído ao revisor de oportunidade. 
- Acrescenta "Pronto para revisão" ao tópico de oportunidade. 

Além disso, a Contoso precisa ser capaz de executar essas ações sob demanda. Para integrar essas tarefas ao processo de qualificação de oportunidade, as ações devem ser exibidas no fluxo de processo empresarial de oportunidade. Para habilitar essa funcionalidade, selecione **Como uma etapa de ação do Fluxo de processo empresarial**.
![Disponível para executar como um fluxo de processo empresarial.](media/action-available-to-run.png)

Em seguida, a etapa de ação é adicionada ao fluxo de processo empresarial de oportunidade da Contoso. Em seguida, o fluxo do processo é validado e atualizado.

![Ação adicionada ao fluxo de processo empresarial de oportunidade.](media/add-action-to-bpf.png)

Agora os membros da equipe de vendas da Contoso podem iniciar a ação na etapa do processo empresarial **Qualificação da oportunidade**, sob demanda, selecionando **Executar**.

![Ação Executar.](media/action-execute.png)

> [!IMPORTANT]
> - Para ser capaz de executar uma ação ou fluxo de trabalho sob demanda, o fluxo de processo empresarial deve incluir uma etapa de ação. Se a etapa de ação executar um fluxo de trabalho, ele deverá ser configurado para ser executado sob demanda.
> - A entidade associada à ação ou ao fluxo de trabalho deve ser a mesma que a entidade associada ao fluxo de processo empresarial.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitação do uso de etapas de ação em um fluxo de processo empresarial

- As ações não estarão disponíveis como etapas de ação se os parâmetros de entrada ou de saída forem os tipos Entity, EntityCollection ou OptionSet (lista de seleção). Ações com mais de um parâmetro de saída EntityReference ou qualquer número de parâmetros de entrada EntityReference não estão disponíveis como etapas de ação. Ações não associadas a uma entidade primária (ação global) não estão disponíveis como etapas de ação.

  
## <a name="next-steps"></a>Próximas etapas  
 [Visão geral dos fluxos de processos empresariais](business-process-flows-overview.md) </br>   
 [Aperfeiçoar os fluxos de processos empresariais com ramificação ](enhance-business-process-flows-branching.md)

