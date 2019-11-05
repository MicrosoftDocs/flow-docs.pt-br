---
title: Fluxos de trabalho do Common Data Service clássico | MicrosoftDocs
ms.custom: ''
ms.date: 08/27/2019
ms.reviewer: matp
ms.service: flow
ms.topic: article
ms.assetid: 1f3c9780-26ad-49ec-a3fb-fc226def19c5
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 42ac7bd75268010a8d7e2bf88a600621504dda39
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548327"
---
# <a name="classic-common-data-service-workflows"></a>Fluxos de trabalho do Common Data Service clássico 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os fluxos de trabalho automatizam processos de negócios sem uma interface do usuário. As pessoas geralmente usam processos de fluxo de trabalho para iniciar a automação que não exige nenhuma interação do usuário.

> [!IMPORTANT]
> Use fluxos em vez de fluxos de trabalho clássicos para automatizar seus processos de negócios. Mais informações: [substituir os fluxos de trabalho de Common Data Service clássicas por fluxos](replace-workflows-with-flows.md)  
  
 Cada processo de fluxo de trabalho é associado a uma única entidade. Ao configurar fluxos de trabalho, você tem quatro áreas principais a serem consideradas:  
  
-   Quando iniciá-los?  
  
-   Eles devem ser executados como um fluxo de trabalho em tempo real ou um fluxo de trabalho em segundo plano?  
  
-   Quais ações devem ser executadas?  
  
-   Em quais condições as ações devem ser executadas?  
  
 Este tópico apresenta como localizar processos de fluxo de trabalho e descreve quando iniciá-los e se eles devem ser executados como em tempo real ou em segundo plano. Para obter informações sobre as ações que devem ser executadas e as condições, consulte [Configurando processos de fluxo de trabalho](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Onde você personaliza os processos de fluxo de trabalho?  
 Você pode ver os fluxos de trabalho em sua organização exibindo o nó **processos** na **solução padrão** e filtrando os processos que têm o **fluxo de trabalho**da **categoria** .  
  
 ![Processos filtrados pelo fluxo de trabalho no Dynamics 365](media/workflow-processes-filtered.PNG "Processos filtrados pelo fluxo de trabalho no Dynamics 365")  
  
 Dependendo de como o aplicativo é criado, os usuários podem criar ou modificar seus fluxos de trabalho no aplicativo. 
 
Os desenvolvedores podem criar fluxos de trabalho usando informações no [Guia do desenvolvedor Common Data Service](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions) e as soluções que você compra podem incluir fluxos de trabalho que você pode modificar.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Propriedades do fluxo de trabalho  
 No Gerenciador de soluções, selecione **processos** e clique em **novo**.  
  
 Quando você cria um fluxo de trabalho, a caixa de diálogo **criar processo** requer que você defina três propriedades que todos os processos têm:  
  
 ![Criando um fluxo de trabalho no Dynamics 365](media/create-workflow.PNG "Criando um fluxo de trabalho no Dynamics 365")  
  
 **Nome do processo**  
 O nome do processo de fluxo de trabalho não precisa ser exclusivo, mas se você esperar que terá muitos fluxos de trabalho, convém usar uma Convenção de nomenclatura para diferenciar seus processos claramente. Talvez você queira aplicar prefixos padrão ao nome do fluxo de trabalho. O prefixo pode descrever a função do fluxo de trabalho ou do departamento dentro da empresa. Isso ajudará você a agrupar itens semelhantes na lista de fluxos de trabalho.  
  
 **Categorias**  
 Essa propriedade estabelece que esse é um processo de fluxo de trabalho.  
  
 **Entidade**  
 Cada processo de fluxo de trabalho deve ser definido como uma única entidade. Não é possível alterar a entidade após a criação do processo de fluxo de trabalho.  
  
 **Executar este fluxo de trabalho em segundo plano (recomendado)**  
 Essa opção é exibida quando você seleciona fluxo de trabalho como a categoria. Essa configuração determina se o fluxo de trabalho é um fluxo de trabalho em tempo real ou em segundo plano. Fluxos de trabalho em tempo real são executados imediatamente (de forma síncrona) e fluxos de trabalho em segundo plano são executados de modo assíncrono. As opções de configuração disponíveis dependem de sua escolha para essa configuração. Os fluxos de trabalho em segundo plano permitem condições de espera que não estão disponíveis para fluxos de trabalho em tempo real. Desde que você não use essas condições de espera, mais tarde poderá converter fluxos de trabalho em segundo plano em fluxos de trabalho em tempo real e fluxos de trabalho em tempo real para fluxos de trabalho em segundo plano. Para obter mais informações sobre condições de espera, consulte [definindo condições para ações de fluxo de trabalho](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 Você também tem a opção de **tipo** para especificar se deseja criar um novo fluxo de trabalho do zero ou optar por iniciar com base em um modelo existente. Quando você escolhe **novo processo de um modelo existente (selecionar na lista)** , pode escolher entre os processos de fluxos de trabalho disponíveis que foram salvos anteriormente como um modelo de processo.  
  
 Depois de criar o fluxo de trabalho ou se editar um existente, você terá as seguintes propriedades adicionais:  
  
 ![Guia geral em um fluxo de trabalho](media/create-workflow-general-tab.PNG "Guia geral em um fluxo de trabalho")  
  
 **Ativar como**  
 Você pode escolher o **modelo de processo** para criar um ponto de partida avançado para outros modelos. Se você escolher essa opção, depois de ativar o fluxo de trabalho, ele não será aplicado, mas, em vez disso, estará disponível para seleção na caixa de diálogo **criar processo** se você selecionar **tipo**: **novo processo de um modelo existente (selecionar da lista)**  
  
 Os modelos de processo são convenientes quando você tem vários processos de fluxo de trabalho semelhantes e deseja defini-los sem duplicar a mesma lógica.  
  
> [!NOTE]
>  Editar um modelo de processo não altera os comportamentos de nenhum outro processo de fluxo de trabalho criado anteriormente usando-o como um modelo. Um novo fluxo de trabalho criado usando um modelo é uma cópia do conteúdo no modelo.  
  
 **Disponível para execução**  
 Esta seção contém opções que descrevem como o fluxo de trabalho está disponível para ser executado.  
  
 **Executar este fluxo de trabalho em segundo plano (recomendado)**  
 Essa caixa de seleção reflete a opção que você selecionou ao criar o fluxo de trabalho. Essa opção está desabilitada, mas você pode alterá-la no menu **ações** , escolhendo **converter em um fluxo de trabalho em tempo real** ou **converter em um fluxo de trabalho em segundo plano**.  
  
 **Como um processo sob demanda**  
 Escolha esta opção se desejar permitir que os usuários executem esse fluxo de trabalho no comando **executar fluxo de trabalho** .  
  
 **Como um processo filho**  
 Escolha esta opção se desejar permitir que o fluxo de trabalho esteja disponível para ser iniciado a partir de outro fluxo de trabalho.  
  
 **Retenção de trabalhos de fluxo de trabalho**  
 Esta seção contém uma opção para excluir um fluxo de trabalho após a conclusão da execução do fluxo de trabalho.  
  
 **Excluir automaticamente trabalhos de fluxo de trabalho concluídos (para economizar espaço em disco)**  
 Escolha esta opção se desejar que um trabalho de fluxo de trabalhos concluído seja excluído automaticamente.  
  
> [!NOTE]
>  Os trabalhos de fluxo de trabalho não são excluídos imediatamente após a conclusão, mas logo após, por meio de um processo em lote.  
  
 **Com**  
 Para entidades de Propriedade do usuário, as opções são **organização**, **pai: unidades de negócios filho**, **unidade de negócios**ou **usuário**. Para entidades de propriedade da organização, a única opção é **organização**.  
  
 Se o escopo for **organização**, a lógica do fluxo de trabalho poderá ser aplicada a qualquer registro na organização. Caso contrário, o fluxo de trabalho só poderá ser aplicado a um subconjunto de registros que se enquadram no escopo.  
  
> [!NOTE]
>  O valor de escopo padrão é **usuário**. Certifique-se de verificar se o valor do escopo é apropriado antes de ativar o fluxo de trabalho.  
  
 **Iniciar quando**  
 Use as opções desta seção para especificar quando um fluxo de trabalho deve ser iniciado automaticamente. Você pode configurar um fluxo de trabalho em tempo real para ser executado antes de determinados eventos. Esse é um recurso muito eficiente, pois o fluxo de trabalho pode interromper a ação antes que ela ocorra. Mais informações: [usando fluxos de trabalho em tempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows). As opções são:  
  
- **O registro é criado**  
  
- **Alterações de status do registro**  
  
- **O registro é atribuído**  
  
- **Alterar campos de registro**  
  
- **O registro foi excluído**  
  
> [!NOTE]
>  Tenha em mente que as ações e condições que você define para o fluxo de trabalho não estão cientes de quando o fluxo de trabalho é executado. Por exemplo, se você definir um fluxo de trabalho para atualizar o registro, essa ação não poderá ser executada por um fluxo de trabalho em tempo real antes de o registro ser criado. Não é possível atualizar um registro que não existe. Da mesma forma, um fluxo de trabalho em segundo plano não pode atualizar um registro que tenha sido excluído, mesmo que você possa definir essa ação para o fluxo de trabalho. Se você configurar um fluxo de trabalho para executar uma ação que não pode ser executada, ocorrerá uma falha e todo o fluxo de trabalho falhará.  
  
 **Executar como**  
 Essa opção só estará disponível se você desmarcar a opção **executar este fluxo de trabalho na plano de fundo (recomendado)** ao criar o fluxo de trabalho ou se você tiver convertido posteriormente um fluxo de trabalho em segundo plano para ser um fluxo de trabalho em tempo real.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contexto de segurança dos processos de fluxo de trabalho  
 Quando um fluxo de trabalho em segundo plano é configurado como um processo sob demanda e é iniciado por um usuário usando o comando **executar fluxo de trabalho** , as ações que o fluxo de trabalho pode executar são limitadas àqueles que o usuário pode executar com base nos privilégios e níveis de acesso definidos por as funções de segurança definidas para sua conta de usuário.  
  
 Quando um fluxo de trabalho em segundo plano é iniciado com base em um evento, o fluxo de trabalho opera no contexto da pessoa que o possui, normalmente a pessoa que criou o fluxo de trabalho.  
  
 Para fluxos de trabalho em tempo real, você tem a opção **Executar como** e pode escolher se o fluxo de trabalho deve aplicar o contexto de segurança do proprietário do fluxo de trabalho ou o usuário que fez alterações no registro. Se o fluxo de trabalho incluir ações que não poderiam ser executadas por todos os usuários com base nas restrições de segurança, você deverá optar por fazer com que o fluxo de trabalho seja executado como o proprietário do fluxo de trabalho.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Ativar um fluxo de trabalho  
 Os fluxos de trabalho só podem ser editados enquanto são desativados. Antes de um fluxo de trabalho poder ser usado manualmente ou ser aplicado devido a eventos que ele precisa ser ativado. Antes que um fluxo de trabalho possa ser ativado, ele deve conter pelo menos uma etapa. Para obter informações sobre como configurar as etapas, consulte [Configurando processos de fluxo de trabalho](configure-workflow-steps.md)  
  
 Um fluxo de trabalho só pode ser ativado ou desativado pelo proprietário do fluxo de trabalho ou por alguém com o **Act em nome de outro privilégio de usuário** , como o administrador do sistema.  O motivo disso é que um usuário mal-intencionado poderia modificar o fluxo de trabalho de alguém sem que esteja atento à alteração. Você pode reatribuir um fluxo de trabalho que você possui alterando o proprietário. Esse campo está na guia **Administração** . Se você não for o administrador do sistema e precisar editar um fluxo de trabalho pertencente a outro usuário, será necessário desativá-lo e atribuí-lo a você. Depois de concluir a edição do fluxo de trabalho, você pode atribuí-lo de volta para ele para que ele possa ativá-lo.  
  
 Os fluxos de trabalho em tempo real exigem que o usuário tenha o privilégio **Ativar processos em tempo real** . Como os fluxos de trabalho em tempo real têm um risco maior de afetar o desempenho do sistema, somente as pessoas que podem avaliar o risco potencial devem receber esse privilégio.  
  
 Os fluxos de trabalho são salvos quando são ativados, portanto, não é necessário salvá-los antes de ativá-los.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Configurando processos de fluxo de trabalho](configure-workflow-steps.md)  <br/>
[Adicionar um fluxo de trabalho sob demanda a um fluxo de processo de negócios](bpf-add-on-demand-workflow.md) 

