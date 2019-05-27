---
title: Automatizar as tarefas criando um fluxo | Microsoft Docs
description: Crie um fluxo que execute automaticamente uma ou mais ações, como enviar email, quando ocorrerem eventos como alguém adicionar uma linha a uma lista do SharePoint.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/28/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4ea24ed12ab12d2d52502477cdb7a4a9eb822076
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64992601"
---
# <a name="create-a-flow-in-microsoft-flow"></a>Criar um fluxo no Microsoft Flow

> [!VIDEO https://www.youtube.com/embed/Gt3CMhLAQqE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]

Crie um fluxo que executa uma ou mais tarefas automaticamente depois dela ser disparada por um evento. Por exemplo, crie um fluxo que o notifique por email quando alguém envia um tweet contendo uma palavra-chave especificada. Neste exemplo, o envio do tweet é o evento e o envio do email é a ação.

## <a name="prerequisites"></a>Pré-requisitos

* Uma conta em [flow.microsoft.com](https://flow.microsoft.com)
* Uma conta do Twitter
* Credenciais do Office 365

## <a name="specify-an-event-to-start-the-flow"></a>Especificar um evento para iniciar o fluxo

Primeiro, você precisará selecionar qual evento, ou *gatilho*, inicia o fluxo.

1. Em [flow.microsoft.com](https://flow.microsoft.com), selecione **Meus fluxos** na barra de navegação superior e, em seguida, selecione **Criar do zero**.

    ![Opção Fluxos na barra de navegação à esquerda](./media/get-started-logic-flow/create-logic-flow.png)
1. Selecione a caixa **Pesquisar centenas de conectores e gatilhos** na parte inferior da tela, insira **Twitter** na caixa que diz **Pesquisar todos os conectores e gatilhos** e, em seguida, selecione **Twitter – Quando um novo tweet é postado**.

    ![Evento do Twitter](./media/get-started-logic-flow/twitter-search.png)

1. Se você ainda não conectou sua conta do Twitter ao Microsoft Flow, selecione **Entrar no Twitter** e, em seguida, forneça suas credenciais.

1. Na caixa **Texto de consulta** digite a palavra-chave que você deseja encontrar.

    ![Palavra-chave do Twitter](./media/get-started-logic-flow/twitter-keyword.png)

## <a name="specify-an-action"></a>Especificar uma ação

1. Selecione **Nova Etapa** e depois selecione **Adicionar uma ação**.

    ![Adicionar ação](./media/get-started-logic-flow/add-action-icon.png)

1. Na caixa que mostra **Pesquisar todos os conectores e ações**, digite ou cole **enviar email**, em seguida, selecione **Outlook do Office 365 - Enviar um email**.

    ![Lista de ações](./media/get-started-logic-flow/send-email.png)

1. Se solicitado, selecione o botão de entrada e, em seguida, forneça suas credenciais.

1. No formulário que aparece, digite ou cole o endereço de email na caixa **Para** e selecione seu nome na lista de contatos que é exibida.

    ![Mensagem de email em branco](./media/get-started-logic-flow/blank-email.png)
1. Na caixa **Assunto** , digite ou cole **Novo tweet de:** e, em seguida, digite um espaço.

    ![Linha do assunto com espaço reservado](./media/get-started-logic-flow/message-token.png)
1. Na lista de tokens, selecione o token **Publicado por** para adicionar um espaço reservado.

    ![Adicionar parâmetro](./media/get-started-logic-flow/add-parameter.png)
1. Selecione a caixa **Corpo** e, em seguida, selecione o token **Texto do tweet** para adicionar um espaço reservado para ele.
1. (opcional) Adicione mais tokens, outro conteúdo, ou ambos, ao corpo do email.
1. Próximo à parte superior da tela, especifique um nome para o fluxo e, em seguida, selecione **Criar fluxo**.

    ![Selecione o botão de Criar fluxo](./media/get-started-logic-flow/create-button.png)
1. Selecione **Concluído** para atualizar a lista de fluxos.

     ![Selecionar o botão Concluído](./media/get-started-logic-flow/done-button.png)
1. Envie um tweet com a palavra-chave indicada ou aguarde até que outra pessoa poste esse tweet.

     Dentro de um minuto após o tweet ser postado, uma mensagem de email notifica sobre o novo tweet.

> [!TIP]
> Use a ação **Enviar email (V2)** para formatar o email com personalização de fonte, cor e realce, uso de negrito, itálico e sublinhado, para criar listas, links e muito mais.

![Edição avançada de email](media/get-started-logic-flow/email-rich-text.png)

## <a name="manage-a-flow"></a>Gerenciar um fluxo

1. Em [flow.microsoft.com](https://flow.microsoft.com), selecione **Meus fluxos** na barra de navegação superior.
1. Na lista de fluxos, siga um destes procedimentos:

   * Para pausar um fluxo, defina sua alternância como **Desligada**.

       ![Pausar fluxo](./media/get-started-logic-flow/pause-flow.png)
   * Para retomar um fluxo, defina sua alternância como **Ligada**.

       ![Retomar fluxo](./media/get-started-logic-flow/resume-flow.png)
   * Para editar um fluxo, selecione o ícone de lápis que corresponde ao fluxo que você deseja editar.

       ![Selecionar fluxo](./media/get-started-logic-flow/select-flow.png)
   * Para excluir um fluxo, selecione o ícone **...**, selecione **Excluir**, em seguida, selecione **Excluir** na caixa de mensagem que aparece.

       ![Ícone Excluir](./media/get-started-logic-flow/delete-icon.png)
   * Para exibir o histórico de execuções de um fluxo, selecione o fluxo na página **Meus fluxos** e exiba o histórico na seção **HISTÓRICO DE EXECUÇÕES** da página aberta.

       ![histórico de fluxos](./media/get-started-logic-flow/run-history.png)

     Selecione uma execução de fluxo na lista de execuções para acessar as entradas e saídas de cada etapa.

> [!NOTE]
> É possível ter até 50 fluxos na conta. Se você já tiver 50, exclua um antes de criar outro.
>
>

## <a name="next-steps"></a>Próximas etapas

* [Adicionar etapas](multi-step-logic-flow.md), como diferentes maneiras de ser notificado, ao seu fluxo.
* [Execute tarefas em uma agenda](run-scheduled-tasks.md) quando você quiser que uma ação ocorra diariamente, em determinada data, ou após determinado número de minutos.
* [Adicionar um fluxo a um aplicativo](https://powerapps.microsoft.com/tutorials/using-logic-flows/) para permitir que seu aplicativo inicie lógica na nuvem.
* [Comece a usar os fluxos de equipe](create-team-flows.md) e convide outras pessoas para colaborar com a criação de fluxos.
