---
title: Automatizar tarefas criando um fluxo | Microsoft Docs
description: Crie um fluxo que executa automaticamente uma ou mais ações, como enviar email, quando ocorrem eventos como alguém adicionando uma linha a uma lista do SharePoint.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/04/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 494a5f978b7792fa971a53cfda85addd9b78f929
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548303"
---
# <a name="create-a-flow-in-microsoft-flow"></a>Criar um fluxo no Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Crie um fluxo que executa uma ou mais tarefas automaticamente depois que ele é disparado por um evento. Por exemplo, crie um fluxo que o notifique por email quando alguém envia um tweet que contém uma palavra-chave que você especifica. Neste exemplo, o envio de um tweet é o evento, e o envio de email é a ação.

## <a name="prerequisites"></a>Pré-requisitos

* Uma conta no [Flow.Microsoft.com](https://flow.microsoft.com)
* Uma conta do Twitter
* Credenciais do Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Especificar um evento para iniciar o fluxo

Primeiro, você precisará selecionar qual evento, ou *gatilho*, inicia o fluxo.

1. Em [Flow.Microsoft.com](https://flow.microsoft.com), selecione **meus fluxos** na barra de navegação superior e, em seguida, selecione **criar em branco**.

    ![Opção de fluxos na barra de navegação à esquerda](./media/get-started-logic-flow/create-logic-flow.png)
1. Selecione a caixa **Pesquisar centenas de conectores e gatilhos** na parte inferior da tela, insira **Twitter** na caixa que diz **Pesquisar todos os conectores e gatilhos**e, em seguida, selecione **Twitter – quando um novo tweet é Postado**.

    ![Evento do Twitter](./media/get-started-logic-flow/twitter-search.png)

1. Se você ainda não conectou sua conta do Twitter ao Microsoft Flow, selecione **entrar no Twitter**e forneça suas credenciais.

1. Na caixa de **texto Pesquisar** , digite a palavra-chave que você deseja localizar.

    ![Palavra-chave do Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Especificar uma ação

1. Selecione **nova etapa**e, em seguida, selecione **Adicionar uma ação**.

    ![Adicionar ação](./media/get-started-logic-flow/add-action-icon.png)

1. Na caixa que mostra **Pesquisar todos os conectores e ações**, digite ou cole **Enviar email**e, em seguida, selecione **Office 365 Outlook-enviar um email**.

    ![Lista de ações](./media/get-started-logic-flow/send-email.png)

1. Se solicitado, selecione o botão entrar e forneça suas credenciais.

1. No formulário exibido, digite ou Cole seu endereço de email na caixa **para** e selecione seu nome na lista de contatos exibida.

    ![Mensagem de email em branco](./media/get-started-logic-flow/blank-email.png)
1. Na caixa **assunto** , digite ou cole **novo tweet de:** , em seguida, digite um espaço.

    ![Linha de assunto com espaço reservado](./media/get-started-logic-flow/message-token.png)
1. Na lista de tokens, selecione o token **tweeted by** para adicionar um espaço reservado para ele.

    ![Adicionar parâmetro](./media/get-started-logic-flow/add-parameter.png)
1. Selecione a caixa **corpo** e, em seguida, selecione o token **texto do tweet** para adicionar um espaço reservado para ele.
1. adicional Adicione mais tokens, outro conteúdo ou ambos ao corpo do email.
1. Próximo à parte superior da tela, nomeie o fluxo e, em seguida, selecione **criar fluxo**.

    ![Selecione o botão criar fluxo](./media/get-started-logic-flow/create-button.png)
1. Selecione **concluído** para atualizar a lista de fluxos.

     ![Selecione o botão concluído](./media/get-started-logic-flow/done-button.png)
1. Envie um tweet com a palavra-chave que você indicou ou aguarde até que outra pessoa poste esse tweet.

     Em um minuto depois que o tweet é Postado, uma mensagem de email o notifica sobre o novo tweet.

> [!TIP]
> Use a ação **Enviar email (v2)** para formatar o email no qual você personaliza a fonte, usar negrito, itálico ou sublinhado, personalizar a cor e o realce e criar listas ou links e muito mais.

![Email de edição avançada](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Gerenciar um fluxo

1. Em [Flow.Microsoft.com](https://flow.microsoft.com), selecione **meus fluxos** na barra de navegação superior.
1. Na lista de fluxos, siga um destes procedimentos:

   * Para pausar um fluxo, defina sua alternância como **desativado**.

       ![Pausar fluxo](./media/get-started-logic-flow/pause-flow.png)
   * Para retomar um fluxo, defina sua alternância como **ativado**.

       ![Continuar fluxo](./media/get-started-logic-flow/resume-flow.png)
   * Para editar um fluxo, selecione o ícone de lápis que corresponde ao fluxo que você deseja editar.

       ![Selecionar fluxo](./media/get-started-logic-flow/select-flow.png)
   * Para excluir um fluxo, selecione o ícone **...** , selecione **excluir**e, em seguida, selecione **excluir** na caixa de mensagem exibida.

       ![Ícone excluir](./media/get-started-logic-flow/delete-icon.png)
   * Para exibir o histórico de execuções de um fluxo, selecione o fluxo na página **meus fluxos** e, em seguida, exiba o histórico na seção **histórico de execuções** da página que é aberta.

       ![Histórico de execuções](./media/get-started-logic-flow/run-history.png)

     Selecione uma execução de fluxo na lista de execuções para ver as entradas e saídas de cada etapa.

> [!NOTE]
> Você pode ter até 600 fluxos em sua conta. Se você já tiver 600 fluxos, exclua um antes de criar outro fluxo.
>
>

## <a name="next-steps"></a>Próximas etapas

* [Adicione etapas](multi-step-logic-flow.md), como diferentes maneiras de serem notificadas, ao seu fluxo.
* [Executar tarefas em uma agenda](run-scheduled-tasks.md), quando você quiser que uma ação ocorra diariamente, em uma determinada data ou após um determinado número de minutos.
* [Adicione um fluxo a um aplicativo](https://powerapps.microsoft.com/tutorials/using-logic-flows/) para permitir que seu aplicativo inicie a lógica na nuvem.
* Comece a usar os [fluxos de equipe](create-team-flows.md) e convide outras pessoas para colaborar com você para criar fluxos.
