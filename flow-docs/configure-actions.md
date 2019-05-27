---
title: Configurar ações para fluxos de trabalho no PowerApps | Microsoft Docs
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
author: Mattp123
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c1b8686000b7723f2d942f3c6c5ebe685d98429d
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64458745"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Configurar ações personalizadas de um fluxo de trabalho

Você pode habilitar uma ação personalizada de um fluxo de trabalho sem escrever o código. Mais informações: [Invocar ações personalizadas de um fluxo de trabalho](invoke-custom-actions-workflow-dialog.md).  
  
 Você também pode criar uma ação para que um desenvolvedor possa usá-la no código ou você pode precisar editar uma ação que foi definida anteriormente. Assim como processos de fluxo de trabalho, considere o seguinte:  
  
-   O que a ação deve fazer?  
  
-   Em quais condições a ação deve ser executada?  
  
 
Ao contrário de processos de fluxo de trabalho, você não precisa definir as seguintes opções:  
  
- **Iniciar quando**: As ações iniciam quando o código chama a mensagem gerada para elas.  
  
- **Escopo**: As ações sempre são executadas no contexto do usuário da chamada.  
  
- **Executar em segundo plano**: As ações são sempre fluxos de trabalho em tempo real.  
  
As ações têm algo que os processos de fluxo de trabalho não têm: argumentos de entrada e saída. Mais informações: [Definir argumentos de processo](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Criar uma ação  
  
> [!IMPORTANT]
>  Se você estiver criando uma ação para incluir como parte de uma solução que será distribuída, você deverá criá-la no contexto da solução. Acesse **[Configurações](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Soluções** e localize a solução não gerenciada da qual essa ação fará parte. Em seguida, na barra de menus, selecione **Novo** > **Processo**. Isso garante que o prefixo de personalização associado ao nome da ação será consistente com outros componentes na solução. Depois de criar a ação, você não pode alterar o prefixo.  
  
 Assim como com processos de fluxo de trabalho, as ações têm as seguintes propriedades na caixa de diálogo **Criar processo**.  
  
 **Nome do processo**  
 Depois de inserir um nome para o processo, um nome exclusivo será criado para ele, removendo quaisquer espaços ou caracteres especiais do nome do processo.  
  
 **Categoria**  
 Essa propriedade estabelece que se trata de um processo de ação. Não é possível alterar isso após salvar o processo.  
  
 **Entidade**  
 Com processos de ações, você pode selecionar uma entidade para fornecer contexto para o fluxo de trabalho assim como com outros tipos de processos, mas você também tem a opção de escolher **Nenhum (global)**. Use essa opção se a ação não exigir o contexto de uma entidade específica. Não é possível alterar isso após salvar o processo.  
  
 **Tipo**  
 Use essa propriedade para escolher se deseja criar uma nova ação do zero ou iniciar por meio de um modelo existente.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Editar uma ação  
 Você deve desativar processos antes de poder editá-los.  
  
 Você pode editar uma ação que foi criada como parte de uma solução não gerenciada ou incluída em uma solução instalada em sua organização. Se a solução for uma solução gerenciada, você não poderá editá-la. O editor de soluções tem a opção de editar as propriedades gerenciadas para que a ação instalada com uma solução gerenciada não possa ser editada.  
  
 Quando uma ação é salva, um nome exclusivo é gerado com base no nome do processo. Esse nome exclusivo tem o prefixo de personalização adicionado do editor de soluções. Esse é o nome da mensagem que um desenvolvedor usará em seu código.  
  
 Ao editar uma ação, você tem as seguintes opções:  
  
 **Nome do processo**  
 Depois que o processo é criado e o nome exclusivo é gerado do nome do processo, você pode editar o nome do processo. Você talvez queira aplicar uma convenção de nomenclatura para facilitar a localização de processos específicos.  
  
 **Nome exclusivo**  
 Quando uma ação é salva, um nome exclusivo é gerado com base no nome do processo. Esse nome exclusivo tem o prefixo de personalização do editor de soluções adicionado. Esse é o nome da mensagem que um desenvolvedor usará em seu código. Não altere esse nome exclusivo se o processo tiver sido ativado e o código estiver em vigor esperando para chamar a ação usando esse nome.  
  
> [!IMPORTANT]
>  Depois que a ação é ativada e o código é escrito para usar um nome exclusivo, o nome exclusivo não deve ser alterado sem alterar também o código que faz referência a ele.  
  
 **Habilitar reversão**  
 Em geral, os processos que dão suporte a transações vão “desfazer” (ou reverter) toda a operação se qualquer parte deles falhar. Há algumas exceções a isso. Algumas ações que os desenvolvedores podem fazer no código iniciado pela ação podem não dar suporte a transações. Por exemplo, se o código executar ações em outros sistemas que estão além do escopo da transação. Isso não poderá ser revertido pela ação em execução em um aplicativo. Algumas mensagens na plataforma não dão suporte às transações. Mas tudo o que você pode fazer apenas com a interface do usuário da ação dará suporte às transações. Todas as ações que fazem parte de um fluxo de trabalho em tempo real são consideradas na transação, mas, com as ações, você tem a opção de recusar.  
  
 Você deve consultar o desenvolvedor que usará esta mensagem para determinar se isso deve estar na transação ou não. Geralmente, uma ação deverá estar na transação se as ações executadas pelo processo empresarial não fizerem sentido, a menos que todas elas sejam concluídas com êxito. O exemplo clássico está transferindo fundos entre duas contas bancárias. Se você retirar os fundos de uma conta, eles deverão ser depositados em outra. Se um dos dois falhar, ambos falharão.  
  
> [!NOTE]
>  Você não poderá habilitar a reversão se uma ação personalizada for invocada diretamente de dentro de um fluxo de trabalho. Você poderá habilitar a reversão se uma ação for disparada por uma mensagem de serviços Web do PowerApps.  
  
 **Ativar como**  
 Assim como todos os processos, você pode ativar o processo como um modelo e usá-lo como um ponto de partida avançado para processos que seguem um padrão semelhante.  
  
 **Definir argumentos de processo**  
 Nessa área, você especificará os dados que a ação espera iniciar e quais dados serão passados para a ação. Mais informações: [Definir argumentos de processo](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Adicionar estágios, condições e ações**  
 Assim como com outros processos, você especifica quais ações a serem executadas e quando executá-las. Mais informações: [Adicionar estágios, condições e ações](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>Definir argumentos de processo  
 Quando um desenvolvedor usa uma mensagem, eles podem começar com alguns dados que podem passar na mensagem. Por exemplo, para criar um novo registro de caso, pode haver um caso em que o valor do título é passado como um argumento de entrada.  
  
 Quando a mensagem é concluída, o desenvolvedor pode precisar passar alguns dados que foram alterados ou gerados pela mensagem para outra operação no código. Esses dados são o argumento de saída.  
  
 Os argumentos de entrada e de saída devem ter um nome, um tipo e algumas informações sobre se o argumento é sempre necessário. Você também pode fornecer uma descrição.  
  
 O nome da mensagem e as informações sobre todos os argumentos do processo representam a "assinatura" para a mensagem. Depois que uma ação for ativada e estiver sendo usada no código, a assinatura não deverá ser alterada. Se essa assinatura for alterada, qualquer código que usar a mensagem falhará. A única exceção a isso pode ser alterar um dos parâmetros para que não seja sempre é necessário.  
  
 Você pode alterar a ordem dos argumentos classificando-os ou movendo-os para cima ou para baixo, porque os argumentos são identificados pelo nome, não por ordem. Além disso, alterar a descrição não interromperá o código que está usando a mensagem.  
  
#### <a name="action-process-argument-types"></a>Tipos de argumento do processo de ação  
 A tabela a seguir descreve os tipos de argumento do processo de ação.  
  
|Tipo|Descrição|  
|----------|-----------------|  
|Booliano|Um valor `true` ou `false`.|  
|DateTime|Um valor que armazena as informações de data e hora.|  
|Decimal|Um valor numérico com precisão decimal. Usado quando a precisão é extremamente importante.|  
|Entidade|Um registro para a entidade especificada. Quando você seleciona a entidade, na lista suspensa é habilitada e permite que você selecione o tipo de entidade.|  
|EntityCollection|Uma coleção de registros de entidade.|  
|EntityReference|Um objeto que contém o nome, a ID e o tipo de um registro de entidade que o identifica de modo exclusivo. Quando você seleciona EntityReference, a lista suspensa é habilitada e permite que você selecione o tipo de entidade.|  
|Flutuante|Um valor numérico com precisão decimal. Usado quando os dados vêm de uma medida que não é absolutamente precisa.|  
|Inteiro|Um número inteiro.|  
|Dinheiro|Um valor que armazena dados sobre uma quantia em dinheiro.|  
|Lista de seleção|Um valor que representa uma opção para um atributo de OptionSet.|  
|Cadeia de caracteres|Um valor de texto.|  
  
> [!NOTE]
> Os valores do argumento **EntityCollection** não podem ser definidos na interface do usuário para condições ou ações. Eles são fornecidos para uso por desenvolvedores em código personalizado. Mais informações: [Criar suas próprias ações](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Adicionar estágios e etapas  
 As ações são um tipo de processo muito semelhante aos fluxos de trabalho em tempo real. Todas as etapas que podem ser usadas em fluxos de trabalho em tempo real podem ser usadas em ações. Para obter informações sobre as etapas que podem ser usadas para fluxos de trabalho em tempo real e ações, consulte [Etapas e estágios de fluxo de trabalho](configure-workflow-steps.md).  
  
 Além das etapas que podem ser usadas para fluxos de trabalho em tempo real, as ações também têm a etapa **Atribuir valor**.  Nas ações, isso pode ser usado apenas para definir argumentos de saída. Você pode usar o assistente de formulário para definir argumentos de saída para valores específicos ou, mais provavelmente, para valores do registro no qual a ação está em execução, registros relacionados ao registro com uma relação muitos para um, registros criados em uma etapa anterior ou valores que fazem parte do próprio processo.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Ações](actions.md)  

 [Invocar ações personalizadas de um fluxo de trabalho](invoke-custom-actions-workflow-dialog.md)   
 [Monitoramento de ações e fluxos de trabalho em tempo real](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
