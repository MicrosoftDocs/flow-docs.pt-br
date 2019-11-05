---
title: Criar um fluxo a partir de um modelo | Microsoft Docs
description: Crie um fluxo de qualquer um dos vários modelos internos.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/07/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 874a942c4422fb402bc564609aff6ea06449ef78
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548245"
---
# <a name="create-a-flow-from-a-template-in-microsoft-flow"></a>Criar um fluxo de um modelo no Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Crie um fluxo de um dos muitos modelos internos que podem, por exemplo, enviar uma mensagem de margem de atraso quando seu gerente enviar um email no Office 365.

**Observação:** [crie um fluxo do zero](get-started-logic-flow.md) se você já tiver um processo em mente e não conseguir encontrar um modelo para ele.

**Pré-requisitos**

* Uma conta no [Flow.Microsoft.com](https://flow.microsoft.com)
* Uma conta de margem de atraso
* Credenciais do Office 365

## <a name="choose-a-template"></a>Escolher um modelo
<iframe width="560" height="315" src="https://www.youtube.com/embed/ZJK8cYdjAic?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Em [Flow.Microsoft.com](https://flow.microsoft.com), selecione **modelos** na barra de navegação superior.
2. Na barra de pesquisa, digite **margem de atraso**e, em seguida, selecione o ícone de pesquisa.
3. Você verá apenas os modelos relacionados à margem de atraso, portanto, agora você pode selecionar **Enviar uma mensagem na margem de atraso quando meu gerente me enviar emails**.
   
    ![Nova opção na barra de navegação à esquerda](./media/get-started-logic-template/select-template.png)
4. Confirme se este modelo fará o que você deseja e, em seguida, selecione **usar este modelo**.
5. Se você não tiver entrado no Office ou na margem de atraso, selecione **entrar** e siga os prompts.
   
    ![Lista de conexões que o modelo requer](./media/get-started-logic-template/confirm-connections.png)
6. Depois de confirmar suas conexões, selecione **continuar**.
   
    Seu fluxo é exibido, mostrando cada ação com uma barra de título laranja.
   
    ![Eventos e ações padrão do modelo](./media/get-started-logic-template/template-default.png)

## <a name="customize-your-flow"></a>Personalizar seu fluxo
1. Selecione a barra de título de um evento para expandi-lo e, em seguida, personalize-o (por exemplo, especificando um filtro no email que lhe interessa).
2. As ações que exigem entrada do você serão expandidas automaticamente.
   
    Por exemplo, a ação **postar mensagem** é expandida porque você precisa inserir um canal, como o *nome de usuário do\@* . Você também pode personalizar o conteúdo da mensagem. Por padrão, a mensagem conterá apenas o assunto, mas você pode incluir outras informações.
   
    ![Especificar o canal para a margem de atraso](./media/get-started-logic-template/specify-keyword.png)
3. Próximo à parte superior da tela, especifique um nome para o fluxo e, em seguida, selecione **criar fluxo**.
4. Por fim, se você estiver satisfeito com o fluxo, selecione **concluído**.
   
    ![Botão concluído](./media/get-started-logic-template/done.png)

Agora, quando o seu gerente enviar um email, você receberá uma mensagem de margem de atraso que contém as informações que você especificou.

## <a name="next-steps"></a>Próximas etapas
* [Assista ao seu fluxo em ação](see-a-flow-run.md)
* [Publicar seu próprio modelo](publish-a-template.md)
* [Usar um modelo para o Common Data Service](common-data-model-intro.md)
* Comece a usar os [fluxos de equipe](create-team-flows.md) e convide outras pessoas para colaborar com você para criar fluxos.

