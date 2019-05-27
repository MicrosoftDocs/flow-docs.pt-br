---
title: Invocar ações personalizadas de um fluxo de trabalho| Microsoft Docs
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
ms.openlocfilehash: 938410cf4484f8bed6509beee1d36c8cb3718e6f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461360"
---
# <a name="invoke-custom-actions-from-a-workflow"></a>Invocar ações personalizadas de um fluxo de trabalho

Os fluxos de trabalho têm várias funcionalidades que dão suporte a cenários empresariais. Chamar ações básicas de operações de dados para um registro, como criar, atualizar e excluir, de dentro de um fluxo de trabalho resolve alguns cenários empresariais. No entanto, se combinar as funcionalidades dos fluxos de trabalho com o poder das ações personalizadas invocadas diretamente de dentro de um fluxo de trabalho, você adicionará uma gama totalmente nova de cenários empresariais ao seu aplicativo sem a necessidade de escrever o código.  
  
 Vejamos o cenário em que uma ação personalizada é invocada de um fluxo de trabalho. Invocaremos uma ação personalizada para solicitar a aprovação do gerente quando um desconto para uma oportunidade específica exceder 20%.  
  
<a name="action"></a>   
## <a name="dynamics-365-customer-engagement-example-create-a-custom-action-using-the-opportunity-entity"></a>Exemplo do Dynamics 365 Customer Engagement: Criar uma ação personalizada usando a entidade de oportunidade
  
1. No [gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), selecione **Processos**.  
  
2.  Na barra de navegação, escolha **Novo**. Nomeie o processo e escolha a categoria **Ação**.  
  
 Para solicitar uma aprovação para o desconto, estamos usando uma ação personalizada chamada **Processo de aprovação**. Adicionamos um parâmetro de entrada, **SpecialNotes**, e uma etapa **Enviar email** para criar uma nova mensagem e enviar uma solicitação de aprovação do gerente, como mostrado aqui.  
  
 ![Adicionar uma etapa &#45; enviar email](media/enable-custom-action-approval-proces-sadd-email.png "Adicionar uma etapa – enviar email")  
  
 Para configurar a mensagem de email, escolha **Definir propriedades**. Quando o formulário é aberto, use o **Assistente de formulário** para adicionar observações especiais e outras informações ao email, como destacado na captura de tela. Para adicionar observações especiais, coloque o cursor onde você deseja que elas apareçam na mensagem e, em seguida, em **Assistente de formulário**, em **Procurar**, escolha **Argumentos** na primeira lista suspensa e escolha **SpecialNotes** na segunda lista suspensa lista e, em seguida, escolha **OK**.  
  
 ![Configurar o email](media/enable-custom-action-approval-process-setup-email.png "Configurar o email")  
  
 Antes de invocar a ação de um fluxo de trabalho, você precisará ativá-la. Depois de ativar a ação, você pode exibir suas propriedades escolhendo **Exibir propriedades**.  
  
 ![Ativar a ação personalizada &#45; processo de aprovação](media/enable-custom-action-approval-process-activate-action.png "Ativar a ação personalizada – processo de aprovação")  
  
<a name="workflow"></a>   
## <a name="invoke-a-custom-action-from-a-workflow"></a>Invocar uma ação personalizada de um fluxo de trabalho  
  
1. No [gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer), selecione **Processos**.   
  
2.  Na barra de navegação, escolha **Novo**. Nomeie o processo e escolha a categoria **Fluxo de trabalho**.  
  
 Criamos um fluxo de trabalho que invoca a ação personalizada **Processo de aprovação** sempre que for necessária a aprovação do gerente para um desconto de mais de 20% para uma oportunidade.  
  
 ![Definir propriedades de ação de fluxo de trabalho](media/enable-custom-action-from-workflow.png "Definir propriedades de ação de fluxo de trabalho")  
  
 Você pode definir as propriedades de entrada da ação escolhendo **Definir propriedades**. Adicionamos um nome da conta relacionada à oportunidade nas observações especiais. No **Assistente de formulário**, em **Procurar**, escolha **Conta** na primeira lista suspensa, escolha **Nome da conta** na segunda lista suspensa e, em seguida, escolha **OK**. A propriedade **Destino** é exigida e é populada pelo sistema. A **{Opportunity(Opportunity)}** na propriedade **Destino** é a mesma oportunidade na qual o fluxo de trabalho de chamada está sendo executado. Como alternativa, você pode escolher uma oportunidade específica para a propriedade de destino usando a pesquisa.  
  
 ![Definir parâmetros de entrada para a ação ApprovalProcess](media/enable-customaction-workflow-set-properties.png "Definir parâmetros de entrada para a ação ApprovalProcess")  
  



