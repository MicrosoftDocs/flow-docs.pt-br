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
ms.openlocfilehash: ec3c6725ca6c0b1e03738f50132464b00c1f8695
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64469268"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>Criar fluxos de trabalho de aprovação paralela com o Microsoft Flow

Em um fluxo de trabalho de aprovação paralela, várias pessoas precisam aprovar itens, como faturas, ordens de compra, solicitações de férias, etc. A aprovação de cada pessoa é independente de todos os outros aprovadores.

Neste passo a passo, usamos o Microsoft Flow para criar um fluxo que automatiza um fluxo de trabalho de aprovação paralela. Este fluxo automatiza um processo de solicitação de férias de um funcionário que requer aprovação de todas as pessoas (ou equipes) que o funcionário suporta regularmente. Os funcionários usam uma [Lista do SharePoint](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) para a solicitação de férias. As aprovações de férias serão necessárias para o gerenciador direto do funcionário, a equipe de Vendas e a equipe de Recursos Humanos. Cada solicitação de férias é roteada para cada aprovador para uma decisão. O fluxo envia um email com alterações no status e, em seguida, atualiza o SharePoint com as decisões.

## <a name="prerequisites"></a>Pré-requisitos

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

A lista do SharePoint Online que você criar deve incluir as seguintes colunas:

   ![Colunas da lista do SharePoint](./media/parallel-modern-approvals/sharepoint-columns.png)

Anote o nome e a URL da lista do SharePoint Online. Esses itens serão usados mais tarde para configurar o gatilho **SharePoint – quando um item é criado**.

## <a name="create-your-flow-from-the-blank-template"></a>Crie seu fluxo a partir do modelo em branco

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>adicione um gatilho

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Informações do SharePoint](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obter o gerente da pessoa que criou a solicitação de férias

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Nomear e salvar seu fluxo

1. Forneça um nome para o fluxo e, em seguida, selecione o ícone **Salvar** para salvar o trabalho que fizemos até agora.

   ![salvar fluxo](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Selecione o ícone **Salvar** periodicamente para salvar as alterações no fluxo.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Adicionar uma ação de aprovação para o gerenciador imediato

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Essa ação envia a solicitação de férias ao endereço de email na caixa **Atribuído A**, portanto, insira o token **Email** da lista **Obter gerenciador (v2)**.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Insira uma ação de aprovação de ramificação paralela para a equipe de vendas

1. Selecione a seta para baixo que está localizada entre o cartão **Obter gerenciador (v2)** e o cartão **Iniciar uma aprovação**.
2. Selecione o sinal de adição que aparecerá na seta para baixo, depois de você selecioná-la.
3. Selecione **Adicionar uma ramificação paralela**.
4. Selecione **Adicionar uma ação**.

    ![obter a configuração do gerenciador](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Pesquise, selecione e, em seguida, configure uma ação **Iniciar uma aprovação** que envia a solicitação de férias à equipe de vendas. Confira as [etapas usadas para Adicionar uma ação de aprovação para o gerenciador imediato](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) se você não tiver certeza sobre como adicionar a ação **Iniciar uma aprovação**.

> [!IMPORTANT]
> Use o endereço de email da equipe de vendas na caixa **Atribuído A** da ação **Iniciar uma aprovação 2**.
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Insira uma ação de aprovação de ramificação paralela para a equipe de recursos humanos

1. Repita as etapas para [inserir uma ramificação paralela para a equipe de vendas](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) para adicionar e, em seguida, configure uma ação **Iniciar uma aprovação** para enviar solicitações de férias para os recursos humanos.

> [!IMPORTANT]
> Use o endereço de email da equipe de recursos humanos na caixa **Atribuído A** da ação **Iniciar uma aprovação 3**.
> 
> 

Se você acompanhou até aqui, o fluxo deve se parecer com este exemplo:

   ![fluxo com ramificações paralelas](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Opções depois de adicionar ramificações paralelas

Depois de adicionar ações a ramificações paralelas, você tem duas opções para adicionar mais etapas ao seu fluxo:

1. Use o pequeno botão **Inserir uma nova etapa** (botão de adição circular que aparece quando você seleciona qualquer espaço em branco em uma ramificação ou área de imediatamente abaixo de uma ramificação). Este botão adiciona uma etapa à essa **ramificação específica**. As etapas que você adiciona com este botão são executadas após a conclusão desta ramificação específica.
1. Use o botão maior **Nova etapa** na parte inferior do fluxo de trabalho inteiro. As etapas que você adiciona com este botão são executadas após a conclusão de todas as ramificações.

Nas seções a seguir, usamos o botão pequeno **Inserir uma nova etapa** para executar as seguintes etapas em cada branch:

* Adicione uma condição que verifica se a solicitação de férias foi aprovada ou rejeitada.
* Envie um email que informa a decisão ao funcionário.
* Atualize a solicitação de férias no SharePoint com a decisão de aprovação.

Em seguida, usamos o botão maior **Nova etapa** para enviar um email que resume todas as decisões tomadas na solicitação de férias.

Vamos continuar:

## <a name="add-a-condition-to-each-branch"></a>Adicionar uma condição a cada ramificação

1. Selecione qualquer espaço em branco na ramificação **Iniciar uma aprovação**.
2. Selecione o botão pequeno **Inserir uma nova etapa** (um botão de adição circular que aparece depois de selecionar o espaço em branco na etapa anterior).
3. Selecione **Adicionar uma condição** no menu que aparece.
4. Selecione a primeira caixa no cartão **Condição** e, em seguida, selecione o token **Resposta** da categoria **Iniciar uma aprovação** na lista de conteúdo dinâmica.

    ![fluxo com condição de ramificações paralelas](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Confirme se a lista (no meio do **cartão de Condição**) está definida como **é igual a**.
6. Insira **Aprovar** (este texto diferencia maiúsculas de minúsculas) na última caixa.
7. Seu cartão de condição agora deve ser semelhante a este exemplo:

    ![fluxo com condição de ramificações paralelas](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Esta condição verifica a resposta da ação **Iniciar uma aprovação** que vai para o gerenciador do funcionário.
   > 
   > 
8. Repita as etapas anteriores nas ramificações **Iniciar uma aprovação 2** (a solicitação de aprovação para vendas) e **Iniciar uma aprovação 3** (a solicitação de aprovação para recursos humanos).

## <a name="add-email-actions-to-each-branch"></a>Adicionar ações de email para cada ramificação

Execute as seguintes etapas do lado de **SE SIM** do branch **Condição**.

   Observação: Seu fluxo usa estas etapas para enviar um email quando a solicitação for aprovada:

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurar o modelo de email aprovado previamente](includes/media/parallel-modern-approvals/yes-email-config.png)

Para enviar um email quando uma solicitação é rejeitada, use o lado **SE NÃO** do branch **Condição** e, em seguida, repita as etapas anteriores para adicionar um modelo ao email de rejeição.

Repita as etapas anteriores nas ramificações **Iniciar uma aprovação 2** (a solicitação de aprovação para vendas) e **Iniciar uma aprovação 3** (a solicitação de aprovação para recursos humanos).

## <a name="update-the-vacation-request-with-the-decision"></a>Atualize a solicitação de férias com a decisão

Execute as seguintes etapas para atualizar o SharePoint ao tomar decisões.

   Observação: Ser claro que executar essas etapas em ambos os **se Sim** e o **se não** lados da ramificação.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![atualizar configuração de item](./media/parallel-modern-approvals/configure-update-item.png)

Repita as etapas anteriores nas ramificações **Iniciar uma aprovação 2** e **Iniciar uma aprovação 3**.

## <a name="complete-the-flow"></a>Concluir o fluxo

1. Selecione **Nova etapa** > **Adicionar uma ação**

    ![atualizar configuração de item](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Use as etapas fornecidas anteriormente para enviar um email que resume os resultados de cada aprovação. Envie este email para o funcionário que solicitou férias. O cartão pode ser semelhante a este exemplo:

   ![atualizar configuração de item](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>Saiba mais sobre as aprovações modernas

[Introdução às aprovações modernas](modern-approvals.md)

