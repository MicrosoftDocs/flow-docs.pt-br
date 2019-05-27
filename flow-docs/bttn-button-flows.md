---
title: Iniciar os fluxos com botões | Microsoft Docs
description: Saiba como iniciar seus fluxos com um bttn
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
ms.openlocfilehash: 813ad16dbc9514975daadac456b73d98fc30db79
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64462208"
---
# <a name="run-your-flows-with-physical-buttons-bttns-from-the-button-corporation-preview"></a>Execute seus fluxos com botões físicos (bttns) a partir do The Button Corporation (versão prévia)
Dispare seus fluxos pressionando um bttn (um botão físico feito por [The Button Corporation](https://my.bt.tn/)). Por exemplo, você pode pressionar uma bttn que dispara um fluxo para executar estas tarefas:

* entra em contato com a assistência técnica com informações de localização
* envia um email para sua equipe
* bloqueia o calendário
* reorganiza fontes

> [!IMPORTANT]
> Você deve [registrar](https://my.bt.tn/) seu bttn antes que você possa usá-lo em um fluxo.
> 
> [!TIP]
> Configure todas as propriedades de bttn como nome, local e endereço de email no [site bttn](https://my.bt.tn/) antes de criar o fluxo.
> 
> 

Você também pode disparar um fluxo usando um [botão físico Flic](flic-button-flows.md).

## <a name="prerequisites"></a>Pré-requisitos
* acesso ao [Microsoft Flow](https://flow.microsoft.com).
* Pelo menos um [bttn registrado](https://my.bt.tn/).

## <a name="create-a-flow-thats-triggered-from-a-bttn"></a>Criar um fluxo que seja disparado a partir de um bttn
Neste passo a passo, usamos um modelo de suporte técnico para criar um fluxo que você pode disparar com um único pressionamento de um [bttn](https://my.bt.tn/). Quando o fluxo é executado, ele gera uma solicitação de suporte e, em seguida, envia para o suporte técnico. A solicitação de suporte fornece o suporte técnico com o local da sala onde a ajuda é necessária. Este passo a passo mostra como criar esse fluxo de um modelo, mas você pode usar o modelo em branco, o que lhe dá controle total sobre todos os aspectos do seu fluxo.

Você pode usar qualquer um desses modelos para criar rapidamente fluxos para sua bttn e conectar-se ao Zendesk, Google e ao SharePoint, entre outros:

![Modelos de bttn](./media/bttn-button-flows/bttn-templates.png)

Dica: Para os fins deste passo a passo, nomeie seu bttn que represente uma sala de conferência em um edifício de escritórios típico.

As configurações para seu bttn devem ser semelhantes a este exemplo (do site bttn):

![Modelos de bttn](./media/bttn-button-flows/bttn-config.png)

Agora que você registrou e configurou seu bttn, vamos começar criando o nosso fluxo.

### <a name="sign-in-and-select-a-template"></a>Entre e selecione um modelo
1. Entre no [Microsoft Flow](https://flow.microsoft.com).
   
    ![entrar](./media/bttn-button-flows/sign-into-flow.png)
   
    Observação: Como alternativa, você pode criar fluxos no aplicativo móvel do Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows).
2. Digite **bttn** na caixa de pesquisa e selecione o ícone de pesquisa.
   
    ![pesquisar](./media/bttn-button-flows/bttn-search-template.png)
   
    Depois de selecionar o ícone de pesquisa, todos os modelos que você pode usar com bttns serão exibidos.
3. Selecione o modelo **Usar Bttn para chamar o suporte técnico para o espaço de reunião**.
   
    ![modelo de suporte](./media/bttn-button-flows/bttn-select-template.png)

### <a name="authorize-microsoft-flow-to-connect-to-your-bttn"></a>Autorize o Microsoft Flow para se conectar ao seu bttn
1. Se solicitado, entre no bttn e nos serviços do Outlook do Office 365, que irão habilitar o botão **Continuar**.
   
    ![credenciais](./media/bttn-button-flows/bttn-provide-credentials.png)
2. Ao entrar no serviço bttn, autorize o Microsoft Flow a usar seu bttns.
   
    **Importante**: Se você não autorizar o Microsoft Flow a usar seus bttns, é possível ver ou conectá-los do Microsoft Flow.
   
    ![autorizar](./media/bttn-button-flows/authorize-bttn.png)
3. Depois de entrar com ambos os serviços, selecione **Continuar**.
   
    ![Continuar](./media/bttn-button-flows/continue.png)

### <a name="select-the-bttn-that-triggers-the-flow"></a>Selecione o bttn que dispara o fluxo
1. No cartão **Quando um bttn é pressionado**, abra a lista de IDs de bttn e, em seguida, selecione o bttn que você deseja usar.
   
    ![selecionar bttn](./media/bttn-button-flows/bttn-id.png)
   
    O fluxo agora deve ser semelhante a este exemplo.
   
    ![visão geral do fluxo](./media/bttn-button-flows/bttn-done.png)
2. Nomeie seu fluxo e, em seguida, selecione **Criar fluxo** para salvá-lo.
   
    ![salvar fluxo](./media/bttn-button-flows/save.png)

## <a name="test-your-flow-and-confirm-results"></a>Teste seu fluxo e confirme os resultados
1. Pressione o botão em seu bttn.
2. Exiba o histórico de execução do fluxo para confirmar que ele foi executado com êxito.
   
    Você pode verificar o histórico de execução no site do Microsoft Flow ou em seu dispositivo móvel.
   
    Observação: O status de execução é definido como **em execução** até que alguém selecione **confirmação** no email de solicitação de suporte.
3. Você também pode confirmar que o email foi enviado para a equipe de suporte.
   
    Se você acompanhou até aqui, o email de suporte é semelhante a este exemplo:
   
    ![](./media/bttn-button-flows/support-request-email.png)

## <a name="troubleshooting"></a>Solução de problemas
* Se o fluxo não foi disparado, entre no site do The Button Corporation e confirme se a atividade de botão (pressionamentos) está sendo registrada.
* Você também pode detalhar a atividade de execução no site do Microsoft Flow e verificar as mensagens de erro.

## <a name="more-information"></a>Mais informações
* [Compartilhe os fluxos do botão](share-buttons.md)
* Aprenda a usar os [tokens de gatilho do botão](introduction-to-button-trigger-tokens.md) para enviar dados atuais quando os fluxos do botão forem executados.
* [Instale o aplicativo do Microsoft Flow para Android](https://aka.ms/flowmobiledocsandroid).
* [Instale o aplicativo do Microsoft Flow para iOS](https://aka.ms/flowmobiledocsios).

