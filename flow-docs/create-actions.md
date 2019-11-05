---
title: Criar uma ação personalizada | MicrosoftDocs
description: Use ações personalizadas quando desejar automatizar uma série de comandos no sistema. As ações expandem o vocabulário disponível para desenvolvedores para expressar processos de negócios.
ms.custom: ''
ms.date: 08/06/2018
ms.reviewer: matp
ms.service: flow
ms.topic: article
author: msftman
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8b00e6e0b3ca2da357eb98d1b6de7756ff5cc75
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546819"
---
# <a name="create-a-custom-action"></a>Criar uma ação personalizada
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Use ações personalizadas quando desejar automatizar uma série de comandos no sistema. As ações expandem o vocabulário disponível para desenvolvedores para expressar processos de negócios. Com verbos principais como criar, atualizar, excluir e atribuir fornecidos pelo sistema, uma ação usa esses verbos principais para criar verbos mais expressivos como aprovar, escalonar, rotear ou agendar. Se a definição de um processo comercial for alterada, alguém que não seja um desenvolvedor poderá editar a ação personalizada para que o código não precise ser alterado.  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Criar uma ação  
  
> [!IMPORTANT]
>  Se você estiver criando uma ação a ser incluída como parte de uma solução que será distribuída, crie-a no contexto da solução. Vá para **[configurações](/powerapps/maker/model-driven-apps/advanced-navigation#settings)**  > **soluções** e localize a solução não gerenciada da qual essa ação fará parte. Em seguida, na barra de menus, selecione novo **processo**de > . Isso garante que o prefixo de personalização associado ao nome da ação será consistente com outros componentes na solução. Depois de criar a ação, você não pode alterar o prefixo.  
  
 Assim como os processos de fluxo de trabalho, as ações têm as seguintes propriedades na caixa de diálogo **criar processo** .  
  
 **Nome do processo**  
 Depois de inserir um nome para o processo, um nome exclusivo será criado para ele removendo espaços ou caracteres especiais do nome do processo.  
  
 **Categorias**  
 Essa propriedade estabelece que esse é um processo de ação. Você não pode alterar isso depois de salvar o processo.  
  
 **Entidade**  
 Com processos de ações, você pode selecionar uma entidade para fornecer contexto para o fluxo de trabalho assim como outros tipos de processos, mas também tem a opção de escolher **nenhum (global)** . Use isso se a ação não exigir o contexto de uma entidade específica. Você não pode alterar isso depois de salvar o processo.  
  
 **Escreva**  
 Use essa propriedade para escolher se deseja criar uma nova ação a partir do zero ou iniciar com base em um modelo existente.  
 
Ao contrário dos processos de fluxo de trabalho, você não precisa definir as seguintes opções:  
  
- **Iniciar quando**: as ações são iniciadas quando o código chama a mensagem gerada para elas.  
  
- **Escopo**: as ações sempre são executadas no contexto do usuário que está chamando.  
  
- **Executar em segundo plano**: as ações são sempre fluxos de trabalho em tempo real.  
  
As ações também têm algo que processos de fluxo de trabalho não – argumentos de entrada e saída.

> [!NOTE]
> Você pode habilitar uma ação personalizada de um fluxo de trabalho sem escrever código. Mais informações: [invocar ações personalizadas de um fluxo de trabalho](invoke-custom-actions-workflow-dialog.md).
 
<a name="edit"></a>   
## <a name="edit-an-action"></a>Editar uma ação  
 Você deve desativar os processos antes de poder editá-los.  
  
 Você pode editar uma ação que foi criada como parte de uma solução não gerenciada ou incluída em uma solução instalada em sua organização. Se a solução for uma solução gerenciada, talvez você não consiga editá-la. O editor da solução tem a opção de editar as propriedades gerenciadas para que a ação instalada com uma solução gerenciada não possa ser editada.  
  
 Quando uma ação é salva, um nome exclusivo é gerado com base no nome do processo. Esse nome exclusivo tem o prefixo de personalização adicionado do editor da solução. Esse é o nome da mensagem que um desenvolvedor usará em seu código.  
  
 Ao editar uma ação, você tem as seguintes opções:  
  
 **Nome do processo**  
 Depois que o processo é criado e o nome exclusivo é gerado a partir do nome do processo, você pode editar o nome do processo. Talvez você queira aplicar uma Convenção de nomenclatura para facilitar a localização de processos específicos.  
  
 **Nome exclusivo**  
 Quando uma ação é salva, um nome exclusivo é gerado com base no nome do processo. Esse nome exclusivo tem o prefixo de personalização do Publicador da solução adicionado. Esse é o nome da mensagem que um desenvolvedor usará em seu código. Não altere esse nome exclusivo se o processo tiver sido ativado e o código estiver em vigor esperando chamar a ação usando esse nome.  
  
> [!IMPORTANT]
>  Depois que a ação é ativada e o código é escrito para usar um nome exclusivo, o nome exclusivo não deve ser alterado sem alterar também o código que faz referência a ele.  
  
 **Habilitar reversão**  
 Em geral, os processos que dão suporte a transações serão "desfazer" (ou reverter) toda a operação se qualquer parte delas falhar. Há algumas exceções a isso. Algumas ações que os desenvolvedores podem fazer no código iniciado pela ação podem não dar suporte a transações. Por exemplo, se o código executar ações em outros sistemas que estão além do escopo da transação. Eles não podem ser revertidos pela ação em execução em um aplicativo. Algumas mensagens na plataforma não dão suporte a transações. Mas tudo o que você pode fazer apenas com a interface do usuário da ação dará suporte a transações. Todas as ações que fazem parte de um fluxo de trabalho em tempo real são consideradas na transação, mas com ações você tem a opção de recusar isso.  
  
 Você deve consultar o desenvolvedor que usará essa mensagem para determinar se ela deve estar na transação ou não. Em geral, uma ação deve ser na transação se as ações executadas pelo processo de negócios não fizerem sentido, a menos que todas elas sejam concluídas com êxito. O exemplo clássico é a transferência de fundos entre duas contas bancárias. Se você retirar os fundos de uma conta, deverá deposita-los no outro. Se ocorrer uma falha, ambas devem falhar.  
  
> [!NOTE]
>  Você não poderá habilitar a reversão se uma ação personalizada for invocada diretamente de dentro de um fluxo de trabalho. Você poderá habilitar a reversão se uma ação for disparada por uma mensagem de serviços Web do PowerApps.  
  
 **Ativar como**  
 Como todos os processos, você pode ativar o processo como um modelo e usá-lo como um ponto de partida avançado para processos que seguem um padrão semelhante.  
  
 **Definir argumentos de processo**  
 Nessa área, você especificará todos os dados que a ação espera iniciar e quais dados serão passados da ação. Mais informações: [Definir argumentos de processo](#define-process-arguments)  
  
 **Adicionar estágios e etapas**  
 Como outros processos, você especifica quais ações executar e quando executá-las. Mais informações: [Adicionar estágios e etapas](#add-stages-and-steps)

<a name="BKMK_DefineProcessArgs"></a>   
## <a name="define-process-arguments"></a>Definir argumentos de processo  
 Quando um desenvolvedor usa uma mensagem, ele pode começar com alguns dados que podem passar para a mensagem. Por exemplo, para criar um novo registro de caso, pode haver o valor de título do caso que é passado como um argumento de entrada.  
  
 Quando a mensagem for concluída, o desenvolvedor poderá precisar passar alguns dados que foram alterados ou gerados pela mensagem para outra operação em seu código. Esses dados são o argumento de saída.  
  
 Os argumentos de entrada e saída devem ter um nome, um tipo e algumas informações sobre se o argumento é sempre necessário. Você também pode fornecer uma descrição.  
  
 O nome da mensagem e as informações sobre todos os argumentos de processo representam a "assinatura" para a mensagem. Depois que uma ação é ativada e está sendo usada no código, a assinatura não deve ser alterada. Se essa assinatura for alterada, qualquer código que use a mensagem falhará. A única exceção a isso pode estar alterando um dos parâmetros para que ele nem sempre seja necessário.  
  
 Você pode alterar a ordem dos argumentos classificando-os ou movendo-os para cima ou para baixo, pois os argumentos são identificados pelo nome, não pela ordem. Além disso, a alteração da descrição não interromperá o código usando a mensagem.  
  
### <a name="action-process-argument-types"></a>Tipos de argumento de processo de ação  
 A tabela a seguir descreve os tipos de argumento de processo de ação.  
  
|Escreva|Ndescrição|  
|----------|-----------------|  
|Boolean|Um valor `true` ou `false`.|  
|Horário|Um valor que armazena informações de data e hora.|  
|Vírgula|Um valor numérico com precisão decimal. Usado quando a precisão é extremamente importante.|  
|Entidade|Um registro para a entidade especificada. Quando você seleciona entidade, a lista suspensa é habilitada e permite que você selecione o tipo de entidade.|  
|EntityCollection|Uma coleção de registros de entidade.|  
|EntityReference|Um objeto que contém o nome, a ID e o tipo de um registro de entidade que o identifica exclusivamente. Quando você seleciona EntityReference, a lista suspensa é habilitada e permite que você selecione o tipo de entidade.|  
|Barra|Um valor numérico com precisão decimal. Usado quando os dados vêm de uma medida que não é absolutamente precisa.|  
|valores|Um número inteiro.|  
|gastar|Um valor que armazena dados sobre uma quantia de dinheiro.|  
|Seleção|Um valor que representa uma opção para um atributo OptionSet.|  
|Strings|Um valor de texto.|  
  
> [!NOTE]
> Os valores de argumento **EntityCollection** não podem ser definidos na interface do usuário para condições ou ações. Eles são fornecidos para uso por desenvolvedores em código personalizado. Mais informações: [criar suas próprias ações](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Adicionar estágios e etapas  
 As ações são um tipo de processo muito semelhante aos fluxos de trabalho em tempo real. Todas as etapas que podem ser usadas em fluxos de trabalho em tempo real podem ser usadas em ações. Para obter informações sobre as etapas que podem ser usadas para fluxos de trabalho em tempo real e ações, consulte [fases e etapas de fluxo de trabalho](configure-workflow-steps.md).  
  
 Além das etapas que podem ser usadas para fluxos de trabalho em tempo real, as ações também têm a etapa **atribuir valor** .  Em ações, elas podem ser usadas somente para definir argumentos de saída. Você pode usar o assistente de formulário para definir argumentos de saída para valores específicos ou, mais provavelmente, para valores do registro em que a ação está sendo executada, registros relacionados a esse registro com uma relação muitos para um, registros criados em uma etapa anterior ou valores que fazem parte do processo em si.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Invocar ações personalizadas de um fluxo de trabalho](invoke-custom-actions-workflow-dialog.md)   

 
 
