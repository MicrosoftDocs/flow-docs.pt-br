---
title: Criar um fluxo de tarefa móvel com o PowerApps | Microsoft Docs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 7f15f11a4e66d80762384f8183af7973fcca76bf
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462753"
---
# <a name="create-a-mobile-task-flow"></a>Criar um fluxo de tarefa móvel

Crie um fluxo no Dynamics 365 para telefones ou Dynamics 365 para tablets com base em tarefas comuns executadas pelos seus usuários. Por exemplo, se eles precisarem executar regularmente uma série de etapas de acompanhamento depois de reuniões com clientes, crie um fluxo de tarefa. Quando os usuários tocam na nova tarefa em seu aplicativo móvel, eles são direcionados do início ao fim, para que não se esqueçam de alguma etapa importante.  
  
 Os fluxos de tarefa podem usar formulários de várias entidades e lógica e podem ter lógica de formulário executada entre as páginas de fluxo de tarefa.  
  
## <a name="create-a-task-flow"></a>Criar um fluxo de tarefas
  
1. Certifique-se de que você tenha o administrador do sistema, ou as permissões de função de segurança do personalizador do sistema ou equivalentes. Se você usar a participação do cliente do Dynamics 365, gerente, vice-presidente ou gerente de negócios e CEO, as funções de segurança também poderão criar fluxos de tarefas móveis. 
  
2. Abra o [gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e selecione **Processos**.  
  
3.  Na barra de ferramentas **Ações**, selecione **Novo**.  
  
4.  Na caixa de diálogo **Criar processo**, preencha os campos obrigatórios:  
  
    -   Insira um nome de processo.  
  
    -   Na lista **Categoria**, selecione **Fluxo de processo empresarial**.  
  
    -   Na lista **Entidade**, selecione a entidade desejada.  
  
5.  Selecione a opção **Executar processo como um fluxo de tarefa (online para dispositivo móvel)**.  
  
6.  Selecione **OK**.
  
     O designer de fluxo de tarefa é aberto em uma nova janela.  
  
     ![Janela do designer de fluxo de tarefa](media/task-flow-designer-window.png "Janela do designer de fluxo de tarefa") 
  
7.  Se seus usuários progredirem de uma página para outra em ordem, arraste o componente **Página** da guia **Componentes** no lado direito da tela e solte-o no sinal “+” no ponto apropriado. Para adicionar um nome a uma página, selecione a página, selecione a guia **Propriedades**, digite um novo nome e, em seguida, selecione **Aplicar**.  
  
8.  Para adicionar uma ramificação ao fluxo de tarefas, arraste o componente **Condição** da guia **Componentes** e solte-o no sinal “+” no ponto apropriado. Para definir propriedades para a condição, selecione a condição, defina as propriedades na guia **Propriedades** e, em seguida, selecione **Aplicar**.  
  
    > [!NOTE]
    >  Conforme adicionar páginas e as condições ao fluxo de tarefas, você verá um minimapa no canto inferior esquerdo da janela que mostra todas as páginas e as condições no fluxo de tarefa.  
  
9. Para adicionar um campo, um rótulo ou um rótulo de seção a uma página, arraste **Campo**, **Rótulo** ou **Rótulo de seção** da guia **Componentes** para a página apropriada. Para alterar as propriedades para um desses itens, selecione o item, defina as propriedades na guia **Propriedades** e, em seguida, selecione **Aplicar**.  
  
10. Para validar o fluxo de tarefa, selecione **Validar** na barra de ações.  
  
11. Para salvar o processo como um rascunho, selecione **Salvar** na parte superior da tela. (Se um processo for um rascunho, as pessoas não poderão usá-lo.)  
  
12. Para ativar o fluxo de tarefas para que as pessoas possam usá-lo, selecione **Ativar**.  
  
> [!TIP]
>  Veja algumas dicas a se ter em mente enquanto você trabalha em seu fluxo de tarefas na janela do designer:  
>   
> -  Para tirar um instantâneo de tudo na janela do fluxo de tarefa, selecione **Instantâneo** na barra de ações.  
> -  Para conectar a um componente válido a outro componente válido no designer, selecione **Conector** na barra de ações.  
> -  Você pode fazer as imagens na tela ficarem maiores ou menores selecionando os botões **Aumentar o nível de zoom** ou **Diminuir o nível de zoom** no canto superior direito da tela. Selecione o botão **Ajustar à tela** para ampliar as imagens até o maior tamanho que se ajuste à tela.  
  
## <a name="next-steps"></a>Próximas etapas  
 [Criar um fluxo de processo empresarial](create-business-process-flow.md)   

