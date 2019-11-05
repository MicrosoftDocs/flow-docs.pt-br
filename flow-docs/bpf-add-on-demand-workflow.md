---
title: Adicionar um fluxo de trabalho sob demanda a um fluxo de processo de negócios
description: ''
author: MSFTMAN
ms.author: Deonhe
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
ms.service: flow
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ab30f745d6465cff9551854034c25130697144ba
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546109"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Adicionar um fluxo de trabalho sob demanda a um fluxo de processo de negócios
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Você pode disparar fluxos de trabalho sob demanda de dentro de um fluxo de processo de negócios. Por exemplo, você pode adicionar um fluxo de trabalho sob demanda a um fluxo de processo de negócios para que uma atividade, como uma tarefa ou email, seja criada sempre que um estágio for concluído. 

Um fluxo de trabalho é ativado com base em onde você solta o fluxo de trabalho no designer de fluxo de processos de negócios.
- Processos de estágio sob demanda. Quando o fluxo de trabalho é Descartado em um estágio de fluxo de processo de negócios, o fluxo de trabalho é disparado na entrada ou saída do estágio. 
- Processos globais sob demanda. Quando o fluxo de trabalho é Descartado na área de **fluxos de trabalho globais** , o fluxo de trabalho é disparado na ativação do processo ou no arquivamento de processos (quando o status faz a transição para um estado aplicado, concluído, reativado ou abandonado). 

Observe os seguintes requisitos ao adicionar um fluxo de trabalho a um fluxo de processo de negócios.
- Para fluxos de trabalho adicionados a um estágio: você só pode usar fluxos de trabalho ativos e sob demanda criados para a mesma entidade do estágio em que você adiciona o fluxo de trabalho.  
- Para fluxos de trabalho globais: você só pode usar fluxos de trabalho ativos sob demanda criados para a entidade primária do fluxo do processo de negócios.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Adicionar um fluxo de trabalho sob demanda a um estágio de fluxo do processo de negócios

Você adiciona um fluxo de trabalho sob demanda do designer de fluxo de processo de negócios, arrastando o componente de fluxo de trabalho para um estágio de processo ou para a seção fluxos de trabalho globais. 

No site do [PowerApps](https://web.powerapps.com) , selecione **controlado por modelos** (canto inferior esquerdo do painel de navegação). 

Abra o designer de fluxo de processo de negócios. Você pode fazer isso de uma das duas maneiras.
- Se o fluxo do processo comercial já estiver adicionado a um aplicativo, vá para **aplicativos**, ao lado do aplicativo que você deseja selecionar **...** e, em seguida, selecione **Editar**. No designer de aplicativos, selecione o fluxo do processo de negócios e, em seguida, selecione ![abrir](media/dynamics365-open-designer.PNG)do designer de fluxo de processo empresarial.  
- Caso contrário, abra o [Gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), no painel de navegação esquerdo, selecione **processos**e, em seguida, selecione o fluxo do processo comercial desejado. 

Decida se deseja que o fluxo de trabalho sob demanda seja disparado por um dos seguintes eventos de fluxo de processo de negócios. 
- Processos de estágio sob demanda. Dispara o fluxo de trabalho na entrada ou na saída do estágio. 
- Processos globais sob demanda. Dispara o fluxo de trabalho na ativação do processo ou no arquivamento de processo (quando o status faz a transição para um estado aplicado, concluído, reativado ou abandonado). 

No exemplo a seguir, um fluxo de trabalho sob demanda chamado **meu fluxo de trabalho sob demanda** é adicionado ao **estágio 1** do fluxo do processo de negócios. 

1. Expanda estágio 1 para revelar a seção **processo disparado** . 
2. Selecione a guia **componentes** e arraste **fluxo de trabalho** para a seção **processo disparado** .
    ![adicionar fluxo de trabalho a um estágio](media/add-workflow-to-bpf-1.png) Alternativamente, você pode arrastar **fluxo de trabalho** para a seção **fluxos de trabalho globais** , que dispara o fluxo de trabalho na ativação do processo ou no arquivamento de processos.
 ![adicionar fluxo à ativação do processo ou](media/add-workflow-to-bpf-global.png) de arquivamento
3. Na caixa de pesquisa da guia **Propriedades** , insira e pesquise o nome do fluxo de trabalho sob demanda que você deseja adicionar ao estágio de fluxo do processo de negócios e, em seguida, selecione **aplicar**.
    ![Insira o nome e selecione aplicar](media/add-workflow-to-bpf-2.png)
4. Na guia **Propriedades** , em **gatilho** , selecione **entrada do estágio** ou **saída do estágio**.  
    ![selecionar gatilho de fluxo de trabalho](media/workflow-trigger.png)
   
    Como alternativa, quando você remove o fluxo de trabalho na seção **fluxos de trabalho globais** , as opções de gatilho são **processo aplicado**, **processo reativado**, **processo abandonado**e **processo concluído**.

5. Selecione **Atualizar** na barra de ferramentas do designer de fluxo de processo de negócios.
 
## <a name="next-steps"></a>Próximas etapas
[Usar processos de fluxo de trabalho para automatizar processos que não exigem interação do usuário](workflow-processes.md) <br/>
[Tutorial: criar um fluxo de processo comercial para padronizar processos](create-business-process-flow.md) <br/>
[Automação do fluxo de processos de negócios no Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
