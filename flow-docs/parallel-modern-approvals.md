---
title: Criar um fluxo de trabalho de aprovação moderna paralela | Microsoft Docs
description: Criar um fluxo de trabalho de aprovação moderna paralela
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbaaecf70e4f6549a790861130dcde0b5a888e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548943"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>Criar fluxos de trabalho de aprovação paralela com Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Em um fluxo de trabalho de aprovação paralela, várias pessoas são necessárias para aprovar itens como faturas, ordens de compra, solicitações de férias, etc. A aprovação de cada pessoa é independente de todos os outros Aprovadores.

Neste tutorial, usamos Microsoft Flow para criar um fluxo que automatiza um fluxo de trabalho de aprovação paralela. Esse fluxo automatiza um processo de solicitação de férias do funcionário que exige a aprovação de todas as pessoas (ou equipes) que o funcionário dá suporte regularmente. Os funcionários usam uma [lista do SharePoint](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) para solicitar férias. As aprovações de férias são necessárias do gerente direto do funcionário, da equipe de vendas e da equipe de recursos humanos. Cada solicitação de férias é roteada para cada aprovador para uma decisão. O fluxo envia email com alterações de status e, em seguida, atualiza o SharePoint com as decisões.

## <a name="prerequisites"></a>Pré-requisitos

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

A lista do SharePoint Online que você cria deve incluir as seguintes colunas:

   ![Colunas de lista do SharePoint](./media/parallel-modern-approvals/sharepoint-columns.png)

Anote o nome e a URL da lista do SharePoint Online. Usaremos esses itens posteriormente para configurar o gatilho **SharePoint-quando um item é criado** .

## <a name="create-your-flow-from-the-blank-template"></a>Criar seu fluxo a partir do modelo em branco

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Adicionar um gatilho

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Informações do SharePoint](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obter o gerente da pessoa que criou a solicitação de férias

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Nomeie e salve seu fluxo

1. Forneça um nome para o fluxo e, em seguida, selecione o ícone **salvar** para salvar o trabalho que fizemos até agora.

   ![salvar fluxo](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Selecione o ícone **salvar** periodicamente para salvar as alterações em seu fluxo.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Adicionar uma ação de aprovação para o Gerenciador imediato

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Essa ação envia a solicitação de férias para o endereço de email na caixa **atribuído a** , portanto, insira o token de **email** da lista **obter Gerenciador (v2)** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Inserir uma ação de aprovação de ramificação paralela para a equipe de vendas

1. Selecione a seta para baixo que está localizada entre o **Gerenciador Get (v2)** e os cartões **iniciar uma aprovação** .
2. Selecione o sinal de adição que aparece na seta para baixo depois de selecioná-lo.
3. Selecione **Adicionar uma ramificação paralela**.
4. Selecione **Adicionar uma ação**.

    ![obter configuração do Gerenciador](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Procure, selecione e configure uma ação **iniciar uma aprovação** que envia a solicitação de férias para a equipe de vendas. Consulte as [etapas usadas para adicionar uma ação de aprovação para o Gerenciador imediato](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) se você não tiver certeza de como adicionar a ação **iniciar uma aprovação** .

> [!IMPORTANT]
> Use o endereço de email da equipe de vendas na caixa **atribuído a** da ação **iniciar uma aprovação 2** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Inserir uma ação de aprovação de ramificação paralela para a equipe de recursos humanos

1. Repita as etapas para [Inserir uma ramificação paralela para a equipe de vendas](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) a ser adicionada e, em seguida, configure uma ação **iniciar uma aprovação** para enviar solicitações de férias aos recursos humanos.

> [!IMPORTANT]
> Use o endereço de email da equipe de recursos humanos na caixa **atribuído a** da ação **iniciar uma aprovação 3** .
> 
> 

Se você seguiu, seu fluxo deve ser semelhante a este exemplo:

   ![fluxo com branches paralelos](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Opções depois de Adicionar ramificações paralelas

Depois de adicionar ações a ramificações paralelas, você tem duas opções para adicionar mais etapas ao seu fluxo:

1. Use o botão pequeno **Inserir uma nova etapa** (o botão de adição circular que aparece quando você seleciona qualquer espaço em branco em uma ramificação ou a área imediatamente abaixo de uma ramificação). Esse botão adiciona uma etapa a esse **Branch específico**. As etapas adicionadas com esse botão são executadas após a conclusão dessa ramificação específica.
1. Use o botão **nova etapa** maior na parte inferior do fluxo de trabalho inteiro. As etapas adicionadas com esse botão são executadas após a conclusão de todas as ramificações.

Nas seções a seguir, usamos o botão pequeno **Inserir uma nova etapa** para executar essas etapas em cada ramificação:

* Adicione uma condição que verifica se a solicitação de férias foi aprovada ou rejeitada.
* Envie um email informando o funcionário da decisão.
* Atualize a solicitação de férias no SharePoint com a decisão de aprovação.

Em seguida, usamos o botão **nova etapa** maior para enviar um email que resume todas as decisões tomadas na solicitação de férias.

Vamos continuar:

## <a name="add-a-condition-to-each-branch"></a>Adicionar uma condição a cada ramificação

1. Selecione qualquer espaço em branco na ramificação **iniciar uma aprovação** .
2. Selecione o botão pequeno **Inserir uma nova etapa** (o botão de adição circular que aparece depois de selecionar o espaço em branco na etapa anterior).
3. Selecione **Adicionar uma condição** no menu que aparece.
4. Selecione a primeira caixa no cartão **condição** e, em seguida, selecione o token de **resposta** na categoria **iniciar uma aprovação** na lista conteúdo dinâmico.

    ![fluxo com condição de ramificações paralelas](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Confirme se a lista (no meio do **cartão de condição**) está definida como **é igual a**.
6. Insira **aprovar** (esse texto diferencia maiúsculas de minúsculas) na última caixa.
7. Seu cartão de condição agora deve ser semelhante a este exemplo:

    ![fluxo com condição de ramificações paralelas](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Essa condição verifica a resposta da ação **iniciar uma aprovação** que vai para o gerente do funcionário.
   > 
   > 
8. Repita as etapas anteriores na ramificação **iniciar uma aprovação 2** (a solicitação de aprovação para vendas) e **iniciar uma aprovação 3** (a solicitação de aprovação para recursos humanos).

## <a name="add-email-actions-to-each-branch"></a>Adicionar ações de email a cada ramificação

Execute as etapas a seguir no lado **se sim** da ramificação **condição** .

   Observação: seu fluxo usa estas etapas para enviar um email quando a solicitação é aprovada:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar o modelo de email pré-aprovado](includes/media/parallel-modern-approvals/yes-email-config.png)

Para enviar um email quando uma solicitação for rejeitada, use o lado **se não** da ramificação **condição** e repita as etapas anteriores para adicionar um modelo para o email de rejeição.

Repita as etapas anteriores na ramificação **iniciar uma aprovação 2** (a solicitação de aprovação para vendas) e **iniciar uma aprovação 3** (a solicitação de aprovação para recursos humanos).

## <a name="update-the-vacation-request-with-the-decision"></a>Atualizar a solicitação de férias com a decisão

Execute as etapas a seguir para atualizar o SharePoint quando forem tomadas decisões.

   Observação: Certifique-se de executar essas etapas nos lados **se sim** e **se não** no Branch.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![atualizar configuração do item](./media/parallel-modern-approvals/configure-update-item.png)

Repita as etapas anteriores nas ramificações **iniciar uma aprovação 2** e **iniciar uma aprovação 3** .

## <a name="complete-the-flow"></a>Concluir o fluxo

1. Selecione **nova etapa** > **Adicionar uma ação**

    ![atualizar configuração do item](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Use as etapas fornecidas anteriormente para enviar um email que resume os resultados de cada aprovação. Envie este email para o funcionário que solicitou férias. Seu cartão pode ser semelhante a este exemplo:

   ![atualizar configuração do item](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Saiba mais sobre as aprovações modernas

[Introdução às aprovações modernas](modern-approvals.md)

