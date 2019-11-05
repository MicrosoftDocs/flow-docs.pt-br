---
title: Iniciar fluxos com bttns | Microsoft Docs
description: Saiba como iniciar seus fluxos com um BTTN
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5835593c7bd020cdfce5f463a7fc198907c4ba6c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545681"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Executar seus fluxos com botões físicos (bttns) no botão Corporation (versão prévia)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Dispare seus fluxos pressionando um BTTN (um botão físico feito pelo [botão Corporation](https://my.bt.tn/)). Por exemplo, você pode pressionar um BTTN que dispara um fluxo para executar estas tarefas:

* entra em contato com a assistência técnica com informações de localização
* envia um email para sua equipe
* bloqueia seu calendário
* Reordena os suprimentos

> [!IMPORTANT]
> Você deve [registrar](https://my.bt.tn/) seu BTTN antes de poder usá-lo em um fluxo.
> 
> [!TIP]
> Configure todas as propriedades BTTN, como nome, local e endereço de email no [site do BTTN](https://my.bt.tn/) , antes de criar o fluxo.
> 
> 

Você também pode disparar um fluxo usando um [botão físico Flic](flic-button-flows.md).

## <a name="prerequisites"></a>Pré-requisitos
* Acesso a [Microsoft Flow](https://flow.microsoft.com).
* Pelo menos um [BTTN registrado](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Criar um fluxo que é disparado de um BTTN
Neste tutorial, usamos um modelo de assistência técnica para criar um fluxo que você pode disparar com um único pressionamento de um [BTTN](https://my.bt.tn/). Quando o fluxo é executado, ele gera uma solicitação de suporte e a envia para o suporte técnico. A solicitação de suporte fornece a assistência técnica com o local da sala onde a ajuda é necessária. Este tutorial demonstra como criar esse fluxo a partir de um modelo, mas você pode usar o modelo em branco, que lhe dá controle total sobre todos os aspectos do seu fluxo.

Você pode usar qualquer um desses modelos para criar fluxos rapidamente para seu BTTN e conectar-se ao zendesk, Google e SharePoint, entre outros:

![modelos de BTTN](./media/bttn-button-flows/bttn-templates.png)

Dica: para os fins deste passo a passos, dê ao seu BTTN um nome que represente uma sala de conferência em um prédio típico do Office.

As configurações para seu BTTN devem ser semelhantes a este exemplo (do site BTTN):

![modelos de BTTN](./media/bttn-button-flows/bttn-config.png)

Agora que você registrou e configurou seu BTTN, vamos começar a criar nosso fluxo.

### <a name="sign-in-and-select-a-template"></a>Entrar e selecionar um modelo
1. Entre [Microsoft Flow](https://flow.microsoft.com).
   
    ![Entrar](./media/bttn-button-flows/sign-into-flow.png)
   
    Observação: como alternativa, você pode criar fluxos no aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [Ios](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).
2. Insira **BTTN** na caixa de pesquisa e, em seguida, selecione o ícone de pesquisa.
   
    ![Procurando](./media/bttn-button-flows/bttn-search-template.png)
   
    Depois de selecionar o ícone de pesquisa, todos os modelos que você pode usar com bttns aparecem.
3. Selecione o modelo **usar BTTN para chamar o suporte técnico para a sala de reunião** .
   
    ![modelo de suporte](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Autorizar Microsoft Flow a se conectar ao seu BTTN
1. Se solicitado, entre no BTTN e nos serviços do Outlook do Office 365, o que habilitará o botão **continuar** .
   
    ![fornecidas](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Quando você entra no serviço BTTN, autorize Microsoft Flow a usar seu bttns.
   
    **Importante**: se você não autorizar Microsoft Flow para usar o bttns, não poderá vê-los ou conectá-los a partir de Microsoft Flow.
   
    ![autoriza](./media/bttn-button-flows/authorize-bttn.png)
3. Depois de entrar em ambos os serviços, selecione **continuar**.
   
    ![Continua](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Selecione o BTTN que dispara o fluxo
1. No cartão **quando um BTTN é pressionado** , abra a lista de IDs de BTTN e selecione o BTTN que você deseja usar.
   
    ![selecionar BTTN](./media/bttn-button-flows/bttn-id.png)
   
    Seu fluxo agora deve ser semelhante a este exemplo.
   
    ![Visão geral do Flow](./media/bttn-button-flows/bttn-done.png)
2. Dê um nome ao seu fluxo e, em seguida, selecione **criar fluxo** para salvá-lo.
   
    ![salvar fluxo](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Testar seu fluxo e confirmar os resultados
1. Pressione o botão em seu BTTN.
2. Exiba o histórico de execução do fluxo para confirmar que ele foi executado com êxito.
   
    Você pode verificar o histórico de execuções no site Microsoft Flow ou em seu dispositivo móvel.
   
    Observação: o status de execução é definido como **em execução** até que alguém selecione **reconhecer** no email de solicitação de suporte.
3. Você também pode confirmar que o email foi enviado para a equipe de suporte.
   
    Se você seguiu, o email de suporte é semelhante a este exemplo:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Solução
* Se o fluxo não foi disparado, entre no site da corporação do botão e confirme se a atividade do botão (pressionamentos) está sendo registrada.
* Você também pode analisar a atividade de execução no site Microsoft Flow e verificar se há mensagens de erro.

## <a name="more-information"></a>Mais informações
* [Compartilhar fluxos de botão](share-buttons.md).
* Aprenda a usar [tokens de gatilho de botão](introduction-to-button-trigger-tokens.md) para enviar dados atuais quando o fluxo de botão for executado.
* [Instale o aplicativo Microsoft Flow para Android](https://aka.ms/flowmobiledocsandroid).
* [Instale o aplicativo Microsoft Flow para IOS](https://aka.ms/flowmobiledocsios).

