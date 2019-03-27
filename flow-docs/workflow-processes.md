---
title: Fluxos de trabalho clássicos do Common Data Service | MicrosoftDocs
ms.custom: ''
ms.date: 08/06/2018
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
ms.openlocfilehash: b48fd51fcdf5ea85b564f7e422f72afa3f318060
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58352839"
---
# <a name="classic-common-data-service-workflows"></a>Fluxos de trabalho clássicos do Common Data Service 

Os fluxos de trabalho automatizam processos empresariais sem uma interface do usuário. As pessoas geralmente usam processos de fluxo de trabalho para iniciar a automação que não requer nenhuma interação do usuário.  
  
 Cada processo de fluxo de trabalho está associado a uma única entidade. Ao configurar fluxos de trabalho, você tem quatro áreas principais a serem consideradas:  
  
-   Quando iniciá-los?  
  
-   Eles devem ser executados como um fluxo de trabalho em tempo real ou um fluxo de trabalho em segundo plano?  
  
-   Quais ações eles devem executar?  
  
-   Em quais condições as ações devem ser executadas?  
  
 Este tópico apresenta como localizar os processos de fluxo de trabalho e descreve quando iniciá-los e se eles devem ser executados em tempo real ou em segundo plano. Para obter informações sobre as ações que eles devem executar, bem como as condições, consulte [Configuração de processos de fluxo de trabalho](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Onde você personaliza os processos de fluxo de trabalho?  
 Você pode ver os fluxos de trabalho em sua organização exibindo o nó **Processos** na **Solução padrão** e filtrando os processos que têm a **Categoria** **Fluxo de trabalho**.  
  
 ![Processos filtrados por fluxo de trabalho no Dynamics 365](media/workflow-processes-filtered.PNG "Processos filtrado pelo fluxo de trabalho no Dynamics 365")  
  
 Dependendo de como o aplicativo é criado, os usuários podem criar ou modificar seus fluxos de trabalho no aplicativo. 
 
Os desenvolvedores podem criar fluxos de trabalho usando as informações no [Guia do desenvolvedor de participação do cliente do Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-guide) e as soluções que você compra podem incluir fluxos de trabalho que podem ser modificados.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Propriedades do fluxo de trabalho  
 No gerenciador de soluções, selecione **Processos** e clique em **Novo**.  
  
 Quando você cria um fluxo de trabalho, a caixa de diálogo **Criar processo** exige que você defina três propriedades que todos os processos tenham:  
  
 ![Criando um fluxo de trabalho no Dynamics 365](media/create-workflow.PNG "Criando um fluxo de trabalho no Dynamics 365")  
  
 **Nome do processo**  
 O nome do processo de fluxo de trabalho não precisa ser exclusivo, mas, se você espera ter muitos fluxos de trabalho, talvez queira usar uma convenção de nomenclatura para diferenciar claramente seus processos. Você talvez queira aplicar prefixos padrão ao nome do fluxo de trabalho. O prefixo pode descrever a função do fluxo de trabalho ou o departamento dentro da empresa. Isso ajudará você a agrupar itens semelhantes na lista de fluxos de trabalho.  
  
 **Categoria**  
 Essa propriedade estabelece que se trata de um processo de fluxo de trabalho.  
  
 **Entidade**  
 Cada processo de fluxo de trabalho deve ser definido como uma única entidade. Você não pode alterar a entidade depois que o processo de fluxo de trabalho é criado.  
  
 **Executar este fluxo de trabalho em segundo plano (recomendado)**  
 Essa opção aparece quando você seleciona o fluxo de trabalho como a categoria. Essa configuração determina se o workflow é em tempo real ou em segundo plano. Os fluxos de trabalho em tempo real são executados imediatamente (de forma síncrona) e os fluxos de trabalho em segundo plano são executados de forma assíncrona. As opções de configuração disponíveis dependem de sua escolha para essa configuração. Fluxos de trabalho em segundo plano permitem condições de espera que não estão disponíveis para os fluxos de trabalho em tempo real. Desde que você não use as condições de espera, em um momento posterior, você poderá converter os fluxos de trabalho em segundo plano para fluxos de trabalho em tempo real e fluxos de trabalho em tempo real para fluxos de trabalho em segundo plano. Para obter mais informações sobre condições de espera, consulte [Configurar condições para ações de fluxo de trabalho](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 Você também tem a opção **Tipo** para especificar se deseja criar um novo fluxo de trabalho do zero ou optar por iniciar por meio de um modelo existente. Ao escolher **Novo processo de um modelo existente (selecione na lista)**, você pode escolher entre os processos de fluxos de trabalho disponíveis que foram salvos anteriormente como um modelo de processo.  
  
 Depois de criar o fluxo de trabalho ou se você editar um já existente, você terá as seguintes propriedades adicionais:  
  
 ![Guia Geral em um fluxo de trabalho](media/create-workflow-general-tab.PNG "Guia Geral em um fluxo de trabalho")  
  
 **Ativar como**  
 Você pode escolher o **Modelo de processo** para criar um ponto de partida avançado para outros modelos. Se você escolher essa opção, depois de ativar o fluxo de trabalho, ele não será aplicado, mas, em vez disso, ele estará disponível para seleção na caixa de diálogo **Criar processo** se você selecionar **Tipo**: **Novo processo de um modelo existente (selecionar na lista)**  
  
 Os modelos de processo são convenientes quando você tem um número de processos de fluxo de trabalho semelhantes e deseja defini-los sem duplicar a mesma lógica.  
  
> [!NOTE]
>  Editar um modelo de processo não altera os comportamentos de outros processos de fluxo de trabalho criados anteriormente usando-o como um modelo. Um novo fluxo de trabalho criado usando um modelo é uma cópia do conteúdo no modelo.  
  
 **Disponível para execução**  
 Esta seção contém as opções que descrevem como o fluxo de trabalho está disponível para ser executado.  
  
 **Executar este fluxo de trabalho em segundo plano (recomendado)**  
 Essa caixa de seleção reflete a opção que você selecionou ao criar o fluxo de trabalho. Essa opção é desabilitada, mas você pode alterá-la no menu **Ações** ao escolher **Converter para um fluxo de trabalho em tempo real** ou **Converter em um fluxo de trabalho em segundo plano**.  
  
 **Como um processo sob demanda**  
 Escolha esta opção se você quiser permitir que usuários executem esse fluxo de trabalho usando o comando **Executar fluxo de trabalho**.  
  
 **Como um processo filho**  
 Escolha esta opção se você quiser permitir que o fluxo de trabalho esteja disponível para ser iniciado por meio de outro fluxo de trabalho.  
  
 **Retenção de trabalho de fluxo de trabalho**  
 Esta seção contém uma opção para excluir um fluxo de trabalho depois que a execução do fluxo de trabalho for concluída.  
  
 **Excluir automaticamente os trabalhos de fluxo de trabalho concluído (para economizar espaço em disco)**  
 Escolha esta opção se você quiser que um trabalho de fluxo de trabalho concluído seja excluído automaticamente.  
  
> [!NOTE]
>  Os trabalhos de fluxo de trabalho não são excluídos imediatamente após a conclusão, mas, logo depois, por meio de um processo em lote.  
  
 **Escopo**  
 Para entidades de propriedade do usuário, as opções são **Organização**, **Divisões Primária e Secundárias**, **Unidade de Negócios** ou **Usuário**. Para entidades de propriedade da organização a única opção é **Organização**.  
  
 Se o escopo for **Organização**, a lógica de fluxo de trabalho poderá ser aplicada a qualquer registro na organização. Caso contrário, o fluxo de trabalho só pode ser aplicado a um subconjunto de registros que estão dentro do escopo.  
  
> [!NOTE]
>  O valor de escopo padrão é **Usuário**. Certifique-se de verificar se o valor do escopo é apropriado antes de ativar o fluxo de trabalho.  
  
 **Iniciar quando**  
 Use as opções nesta seção para especificar quando um fluxo de trabalho deve ser iniciado automaticamente. Você pode configurar um fluxo de trabalho em tempo real para ser executado antes de determinados eventos. Essa é uma funcionalidade muito avançada porque o fluxo de trabalho pode parar a ação antes que ela ocorra. Mais informações: [Usando fluxos de trabalho em tempo real](configure-workflow-steps.md#BKMK_SynchronousWorkflows). As opções são:  
  
- **O registro é criado**  
  
- **O status do registro é alterado**  
  
- **O registro é atribuído**  
  
- **Os campos do registro são alterados**  
  
- **O registro é excluído**  
  
> [!NOTE]
>  Tenha em mente que as ações e as condições que você definir para o fluxo de trabalho não estarão cientes de quando o fluxo de trabalho será executado. Por exemplo, se você definir um fluxo de trabalho para atualizar o registro, essa ação não poderá ser executada por um fluxo de trabalho em tempo real antes de o registro ser criado. Um registro que não existe não pode ser atualizado. Da mesma forma, um fluxo de trabalho em segundo plano não pode atualizar um registro que foi excluído, mesmo que você possa definir essa ação para o fluxo de trabalho. Se você configurar um fluxo de trabalho para executar uma ação que não pode ser executada, ela falhará e o fluxo de trabalho inteiro falhará.  
  
 **Executar como**  
 Essa opção só estará disponível se você desmarcar a opção **Executar este fluxo de trabalho em segundo plano (recomendado)** ao criar o fluxo de trabalho ou se você tiver convertido, posteriormente, um fluxo de trabalho em segundo plano para ser um fluxo de trabalho em tempo real.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contexto de segurança de processos de fluxo de trabalho  
 Quando um fluxo de trabalho em segundo plano está configurado como um processo sob demanda e é iniciado por um usuário usando o comando **Executar o fluxo de trabalho**, as ações que o fluxo de trabalho pode executar são limitadas para aquelas que o usuário pode executar com base nos privilégios e níveis de acesso definidos por funções de segurança definidas para a conta de usuário.  
  
 Quando um fluxo de trabalho em segundo plano é iniciado com base em um evento, o fluxo de trabalho opera no contexto da pessoa que o possui, geralmente é a pessoa que criou o fluxo de trabalho.  
  
 Para fluxos de trabalho em tempo real, você tem a opção **Executar como** e pode escolher se o fluxo de trabalho deve aplicar o contexto de segurança do proprietário do fluxo de trabalho ou o usuário que fez alterações no registro. Se seu fluxo de trabalho inclui as ações que todos os usuários não seriam capazes de executar com base nas restrições de segurança, você deve optar por executar o fluxo de trabalho como o proprietário do fluxo de trabalho.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Ativar um fluxo de trabalho  
 Fluxos de trabalho só podem ser editados enquanto eles estiverem desativados. Antes de um fluxo de trabalho poder ser usado manualmente ou ser aplicado devido a eventos, ele deve ser ativado. Antes de um fluxo de trabalho pode ser ativado, ele deve conter pelo menos uma etapa. Para obter informações sobre como configurar as etapas, consulte [Configurando os processos de fluxo de trabalho](configure-workflow-steps.md)  
  
 Um fluxo de trabalho só pode ser ativado ou desativado pelo proprietário do fluxo de trabalho ou por uma pessoa com o privilégio **Agir em nome de outro usuário**, como o administrador do sistema.  A razão para isso é que um usuário mal-intencionado poderia modificar o fluxo de trabalho de outra pessoa sem essa pessoa estar ciente da alteração. Você pode reatribuir um fluxo de trabalho que possui alterando o proprietário. Este campo está na guia **Administração**. Se não for o administrador do sistema e precisar editar um fluxo de trabalho que pertence a outro usuário, você precisará dele para desativá-lo e atribuí-lo a você. Depois de terminar de editar o fluxo de trabalho, você pode atribuí-lo de volta ao usuário para que ele possa ativá-lo.  
  
 Os fluxos de trabalho em tempo real exigem que o usuário tenha o privilégio **Ativar processos em tempo real**. Como os fluxos de trabalho em tempo real têm um risco maior de afetar o desempenho do sistema, somente as pessoas que podem avaliar o risco potencial devem receber esse privilégio.  
  
 Os fluxos de trabalho são salvos quando são ativados, portanto, não é necessário salvá-los antes de ativá-los.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Configurando os processos de fluxo de trabalho](configure-workflow-steps.md)  <br/>
[Adicionar um fluxo de trabalho sob demanda a um fluxo de processo empresarial](bpf-add-on-demand-workflow.md) 

