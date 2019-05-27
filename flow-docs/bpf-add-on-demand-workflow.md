---
title: Adicionar um fluxo de trabalho sob demanda a um fluxo de processo empresarial
description: ''
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
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
ms.openlocfilehash: aa061d5e2f668e8950a6cdab89992996f64c6fe8
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460908"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Adicionar um fluxo de trabalho sob demanda a um fluxo de processo empresarial

Você pode disparar fluxos de trabalho sob demanda de dentro de um fluxo de processo empresarial. Por exemplo, você pode adicionar um fluxo de trabalho sob demanda a um fluxo de processo empresarial para que uma atividade, como uma tarefa ou um email, seja criada sempre que uma etapa for concluída. 

Um fluxo de trabalho torna-se ativo com base em onde você solta o fluxo de trabalho no designer de fluxo do processo empresarial.
- Processos de estágio sob demanda. Quando o fluxo de trabalho é solto no estágio de fluxo do processo empresarial, o fluxo de trabalho é disparado na entrada ou saída do estágio. 
- Processos globais sob demanda. Quando o fluxo de trabalho é solto na área **Fluxos de trabalho globais**, o fluxo de trabalho é disparado na ativação de processo ou no arquivamento do processo (quando o status faz a transição para um estado aplicado, concluído, reativado ou abandonado). 

Observe os seguintes requisitos quando você adiciona um fluxo de trabalho a um fluxo de processo empresarial.
- Para adicionar a um estágio de fluxos de trabalho: Você só pode usar o Active Directory, sob demanda fluxos de trabalho criados para a mesma entidade do estágio de onde você pode adicionar o fluxo de trabalho.  
- Para fluxos de trabalho globais: Você só pode usar o Active Directory sob demanda fluxos de trabalho criados para a entidade principal do fluxo de processos de negócios.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Adicionar um fluxo de trabalho sob demanda a um estágio de fluxo de processo empresarial

Você adiciona um fluxo de trabalho sob demanda por meio do designer de fluxo de processo empresarial ao arrastar o componente de fluxo de trabalho a um estágio do processo ou à seção de fluxos de trabalho globais. 

No site do [PowerApps](https://web.powerapps.com), selecione **Controlado por modelos** (canto inferior esquerdo do painel de navegação). 

Abra o designer de fluxo do processo empresarial. Você pode fazer isso de duas maneiras.
- Se o fluxo do processo empresarial já tiver sido adicionado a um aplicativo, acesse **Aplicativos**, ao lado do aplicativo que você deseja selecionar **…** e, em seguida, selecione **Editar**. No designer de aplicativo, selecione o fluxo do processo empresarial e, em seguida, selecione ![Abrir designer de fluxo do processo empresarial](media/dynamics365-open-designer.PNG).  
- Caso contrário, abra o [Gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer), no painel de navegação à esquerda, selecione **Processos** e, em seguida, selecione o fluxo do processo empresarial que você deseja. 

Decida se deseja que o fluxo de trabalho sob demanda seja disparado por um dos seguintes eventos de fluxo de processo empresarial. 
- Processos de estágio sob demanda. Dispara o fluxo de trabalho na entrada ou na saída do estágio. 
- Processos globais sob demanda. O fluxo de trabalho é disparado na ativação de processo ou no arquivamento do processo (quando o status faz a transição para um estado aplicado, concluído, reativado ou abandonado). 

No exemplo a seguir, um fluxo de trabalho sob demanda denominado **Meu fluxo de trabalho sob demanda** é adicionado ao **Estágio 1** do fluxo de processo empresarial. 

1. Expanda o estágio 1 para revelar a seção **Processo disparado**. 
2. Selecione a guia **Componentes** e arraste **Fluxo de trabalho** para a seção **Processo disparado**.
    ![Adicionar fluxo de trabalho a um estágio](media/add-workflow-to-bpf-1.png) Como alternativa, você pode arrastar o **Fluxo de trabalho** para a seção **Fluxos de trabalho globais**, que dispara o fluxo de trabalho na ativação do processo ou no arquivamento do processo.
 ![Adicionar fluxo de trabalho ao arquivamento ou ativação do processo](media/add-workflow-to-bpf-global.png)
3. Na caixa de pesquisa da guia **Propriedades**, insira e pesquise o nome do fluxo de trabalho sob demanda que deseja adicionar ao estágio de fluxo do processo empresarial e, em seguida, selecione **Aplicar**.
    ![Insira o nome e selecione Aplicar](media/add-workflow-to-bpf-2.png)
4. Na guia **Propriedades**, sob **Gatilho**, selecione **Entrada do estágio** ou **Saída do estágio**.  
    ![Selecione o gatilho do fluxo de trabalho](media/workflow-trigger.png)
   
    Como alternativa, quando você solta o fluxo de trabalho na seção **Fluxos de trabalho globais**, as opções de gatilho são **Processo aplicado**, **Processo reativado**, **Processo abandonado** e **Processo concluído**.

5. Selecione **Atualizar** na barra de ferramentas do designer do fluxo de processo empresarial.
 
## <a name="next-steps"></a>Próximas etapas
[Use processos de fluxo de trabalho para automatizar processos que não exigem interação do usuário](workflow-processes.md) <br/>
[Tutorial: Criar um fluxo de processo empresarial para padronizar processos](create-business-process-flow.md) <br/>
[Automação de fluxo de processo empresarial no Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
