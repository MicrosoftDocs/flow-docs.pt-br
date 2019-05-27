---
title: Criar um fluxo de um modelo | Microsoft Docs
description: Crie um fluxo de qualquer um dos vários modelos internos.
services: ''
suite: flow
documentationcenter: na
author: aftowen
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
ms.author: anneta
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 52aae570f65eaae537f548e686f437592eb5ef03
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461273"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Criar um fluxo de um modelo no Microsoft Flow
Crie um fluxo de um dos muitos modelos internos que podem, por exemplo, enviar uma mensagem de Slack quando seu gerente lhe envia um email no Office 365.

**Observação:** [Criar um fluxo do zero](get-started-logic-flow.md) se você já tiver um processo em mente e não é possível localizar um modelo para ele.

**Pré-requisitos**

* Uma conta em [flow.microsoft.com](https://flow.microsoft.com)
* Uma conta de Slack
* Credenciais do Office 365

## <a name="choose-a-template"></a>Escolher um modelo
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Em [flow.microsoft.com](https://flow.microsoft.com), selecione **Modelos** na barra de navegação superior.
2. Na barra de pesquisa, digite **Slack**, e, em seguida, selecione o ícone de pesquisa.
3. Você verá apenas os modelos relacionados ao Slack, para que possa selecionar agora **Enviar uma mensagem com Slack quando meu gerente me enviar emails**.
   
    ![Opção Nova na barra de navegação à esquerda](./media/get-started-logic-template/select-template.png)
4. Confirme se esse modelo fará o que deseja e, em seguida, selecione **Usar este modelo**.
5. Se você não tiver entrado no Office ou Slack, selecione **Entrar** e, em seguida, siga os prompts.
   
    ![Lista de conexões que o modelo requer](./media/get-started-logic-template/confirm-connections.png)
6. Depois de confirmar suas conexões, selecione **Continuar**.
   
    O fluxo é exibido, mostrando cada ação com uma barra de título laranja.
   
    ![Eventos e ações padrão do modelo](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Personalizar o fluxo
1. Selecione a barra de título de um evento para expandi-lo e personalize-o (por exemplo, especificando um filtro no email que lhe interessa).
2. Ações que exigem entradas de você serão automaticamente expandidas.
   
    Por exemplo, a ação **Publicar mensagem** é expandida porque você precisa inserir um canal, como o *\@username*. Você também pode personalizar o conteúdo da mensagem. Por padrão, a mensagem conterá apenas o assunto, mas você pode incluir outras informações.
   
    ![Especificar canal para Slack](./media/get-started-logic-template/specify-keyword.png)
3. Na parte inferior da tela, especifique um nome para o fluxo e, em seguida, selecione **Criar Fluxo**.
4. Por fim, se você estiver satisfeito com o fluxo, selecione **Concluído**.
   
    ![Botão Concluído](./media/get-started-logic-template/done.png)

Agora, quando seu gerente lhe enviar um email, você receberá uma mensagem de Slack contendo as informações que você especificou.

## <a name="next-steps"></a>Próximas etapas
* [Assista a seu fluxo em ação](see-a-flow-run.md)
* [Publicar seu próprio modelo](publish-a-template.md)
* [Usar um modelo para o Common Data Service](common-data-model-intro.md)
* [Comece a usar os fluxos de equipe](create-team-flows.md) e convide outras pessoas para colaborar com a criação de fluxos.

