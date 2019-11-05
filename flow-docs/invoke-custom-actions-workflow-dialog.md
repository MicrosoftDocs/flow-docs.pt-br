---
title: Invocar ações personalizadas de um fluxo de trabalho | MicrosoftDocs
description: Saiba como invocar uma ação personalizada de um fluxo de trabalho
ms.custom: ''
ms.date: 11/22/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 1fd5d39e-3dc8-4d1a-8b4b-ccaa303f4bbb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9ed3c2114bfb167eb8d4d6a5670ccec8050ee9d0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547425"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Invocar ações personalizadas de um fluxo de trabalho
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os fluxos de trabalho têm vários recursos que dão suporte a cenários de negócios. Chamar ações básicas de operação de dados para um registro, como criar, atualizar e excluir, de dentro de um fluxo de trabalho resolve alguns cenários de negócios. No entanto, se você acoplar os recursos dos fluxos de trabalho com o poder das ações personalizadas invocadas diretamente de dentro de um fluxo de trabalho, adicionará um novo intervalo de cenários de negócios ao seu aplicativo sem a necessidade de escrever código.  
  
 Vamos examinar o cenário no qual uma ação personalizada é invocada de um fluxo de trabalho. Invocaremos uma ação personalizada para solicitar a aprovação do gerente quando um desconto para uma oportunidade específica exceder 20%.  
  
<a name="action"></a>   
## <a name="example-create-a-custom-action-using-the-opportunity-entity"></a>Exemplo: criar uma ação personalizada usando a entidade oportunidade
  
1. No [Gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) , selecione **processos**.  
  
2.  Na barra de navegação, escolha **novo**. Dê um nome ao processo e escolha a categoria de **ação** .  
  
 Para solicitar uma aprovação para o desconto, estamos usando uma ação personalizada chamada **processo de aprovação**. Adicionamos um parâmetro de entrada, **SpecialNotes**, e uma etapa **Enviar email** para criar uma nova mensagem e enviar uma solicitação para a aprovação do gerente, como mostrado aqui.  
  
 ![Adicionar uma etapa &#45; enviar email](media/enable-custom-action-approval-proces-sadd-email.png "Adicionar uma etapa – enviar email")  
  
 Para configurar a mensagem de email, escolha **definir propriedades**. Quando o formulário for aberto, use o **Assistente de formulário** para adicionar observações especiais e outras informações ao email, conforme realçado na captura de tela. Para adicionar as observações especiais, coloque o cursor onde você deseja que eles apareçam na mensagem e, em seguida, no **Assistente de formulário**, em **procurar**, escolha os **argumentos** na primeira lista suspensa e escolha **SpecialNotes** no segundo e, em seguida, escolha **OK**.  
  
 ![Configurar email](media/enable-custom-action-approval-process-setup-email.png "Configurar email")  
  
 Antes de poder invocar a ação de um fluxo de trabalho, você precisa ativá-la. Depois de ativar a ação, você pode exibir suas propriedades escolhendo **Exibir Propriedades**.  
  
 ![Ativar processo de &#45; aprovação de ação personalizada](media/enable-custom-action-approval-process-activate-action.png "Ativar ação personalizada-processo de aprovação")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Invocar uma ação personalizada de um fluxo de trabalho  
  
1. No [Gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) , selecione **processos**.   
  
2.  Na barra de navegação, escolha **novo**. Dê um nome ao processo e escolha a categoria de **fluxo de trabalho** .  
  
 Criamos um fluxo de trabalho que invoca a ação personalizada do **processo de aprovação** sempre que a aprovação do gerente para um desconto acima de 20% para uma oportunidade for necessária.  
  
 ![Definir propriedades de ação do fluxo de trabalho](media/enable-custom-action-from-workflow.png "Definir propriedades de ação do fluxo de trabalho")  
  
 Você pode definir as propriedades de entrada da ação escolhendo **definir propriedades**. Adicionamos um nome à conta relacionada à oportunidade nas observações especiais. No **Assistente de formulário**, em **procurar**, escolha **conta** na primeira lista suspensa, escolha **nome da conta** na segunda lista suspensa e, em seguida, escolha **OK**. A propriedade de **destino** é necessária e é populada pelo sistema. A **{oportunidade (oportunidade)}** na propriedade de **destino** é a mesma oportunidade em que o fluxo de trabalho de chamada está sendo executado. Como alternativa, você pode escolher uma oportunidade específica para a propriedade de destino usando Lookup.  
  
 ![Definir parâmetros de entrada para a ação ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Definir parâmetros de entrada para a ação ApprovalProcess")  
  



