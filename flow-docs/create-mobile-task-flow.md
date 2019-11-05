---
title: Criar um fluxo de tarefas móveis com o PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ccd3b6c0e8cf97a490d01bb9ba5e5c3c4043fda5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546440"
---
# <a name="create-a-mobile-task-flow"></a>Criar um fluxo de tarefas móveis
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Crie um fluxo no Dynamics 365 para telefones ou Dynamics 365 para tablets com base em tarefas comuns que os usuários executam. Por exemplo, se eles precisarem executar regularmente uma série de etapas de acompanhamento após reuniões do cliente, crie um fluxo de tarefas. Quando os usuários tocam na nova tarefa em seu aplicativo móvel, ele os conduzirá do início ao fim para que não se esqueçam de uma etapa importante.  
  
 Os fluxos de tarefas podem usar formulários e lógica de várias entidades e podem ter uma lógica de formulário que é executada nas páginas de fluxo de tarefas.  
  
## <a name="create-a-task-flow"></a>Criar um fluxo de tarefas
  
1. Verifique se você tem o administrador do sistema ou a função de segurança do personalizador do sistema ou as permissões equivalentes. O gerente, vice-presidente ou CEO – gerente de negócios, funções de segurança também podem criar fluxos de tarefas móveis. 
  
2. Abra o [Gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e selecione **processos**.  
  
3.  Na barra de ferramentas **ações** , selecione **novo**.  
  
4.  Na caixa de diálogo **criar processo** , preencha os campos obrigatórios:  
  
    -   Insira um nome de processo.  
  
    -   Na lista **categoria** , selecione **fluxo de processo empresarial**.  
  
    -   Na lista **entidade** , selecione a entidade desejada.  
  
5.  Selecione a opção **Executar processo como um fluxo de tarefas (móvel online)** .  
  
6.  Selecione **OK**.
  
     O designer de fluxo de tarefas é aberto em uma nova janela.  
  
     ![Janela designer de fluxo de tarefas](media/task-flow-designer-window.png "Janela designer de fluxo de tarefas") 
  
7.  Se os usuários forem progredindo de uma página para outra em ordem, arraste o componente da **página** da guia **componentes** no lado direito da tela e solte-o no sinal de + no ponto apropriado. Para adicionar um nome para uma página, selecione a página, selecione a guia **Propriedades** , digite um novo nome e, em seguida, selecione **aplicar**.  
  
8.  Para adicionar uma ramificação ao fluxo de tarefas, arraste o componente **condição** da guia **componentes** e solte-o no sinal de + no ponto apropriado. Para definir as propriedades da condição, selecione a condição, defina as propriedades na guia **Propriedades** e, em seguida, selecione **aplicar**.  
  
    > [!NOTE]
    >  Ao adicionar páginas e condições ao fluxo de tarefas, você verá um minimapa no canto inferior esquerdo da janela que mostra todas as páginas e condições no fluxo de tarefas.  
  
9. Para adicionar um campo, rótulo ou rótulo de seção a uma página, arraste o **campo**, o **rótulo**ou o **rótulo de seção** da guia **componentes** para a página apropriada. Para alterar as propriedades de um desses itens, selecione o item, defina as propriedades na guia **Propriedades** e, em seguida, selecione **aplicar**.  
  
10. Para validar o fluxo de tarefas, selecione **validar** na barra de ação.  
  
11. Para salvar o processo como um rascunho, selecione **salvar** na parte superior da tela. (Desde que um processo seja um rascunho, as pessoas não poderão usá-lo.)  
  
12. Para ativar o fluxo de tarefas para que as pessoas possam usá-lo, selecione **Ativar**.  
  
> [!TIP]
>  Aqui estão algumas dicas para ter em mente enquanto você trabalha em seu fluxo de tarefas na janela do designer:  
>   
> -  Para tirar um instantâneo de tudo na janela fluxo de tarefas, selecione **instantâneo** na barra de ação.  
> -  Para conectar um componente válido a outro componente válido no designer, selecione **conector** na barra de ação.  
> -  Você pode tornar as imagens na tela maiores ou menores selecionando os botões **aumentar nível de zoom** ou **diminuir nível de zoom** no canto superior direito da tela. Selecione o botão **ajustar à tela** para apagar as imagens até o maior tamanho que cabe na tela.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Criar um fluxo de processo de negócios](create-business-process-flow.md)   

