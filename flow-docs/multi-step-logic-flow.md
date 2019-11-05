---
title: Adicionar uma opção avançada e várias ações | Microsoft Docs
description: Expanda um fluxo para incluir uma opção avançada, como definir o email como prioridade alta e adicionar outra ação para o mesmo evento.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/20/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 668e69b1c8f1781cf5720443af8e48409f43d322
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548606"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Adicionar várias ações e opções avançadas a um fluxo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Personalize um fluxo adicionando uma ou mais opções avançadas e várias ações para o mesmo gatilho. Por exemplo, adicione uma opção avançada que envia uma mensagem de email como prioridade alta. Além de enviar email quando um item é adicionado a uma lista do SharePoint, crie um arquivo no Dropbox que contenha as mesmas informações.

## <a name="prerequisites"></a>Pré-requisitos
* [Criar um fluxo](get-started-logic-flow.md)

## <a name="add-another-action"></a>Adicionar outra ação
Neste procedimento, você adicionará uma ação no meio do fluxo. Esta ação salvará um arquivo em seu dropbox, arquivando o item na lista.

1. Em [Flow.Microsoft.com](https://flow.microsoft.com), selecione **meus fluxos** na barra de navegação superior.
2. Na lista de fluxos, selecione o fluxo que você deseja editar.
3. Selecione **nova etapa**e, em seguida, selecione **Adicionar uma ação**.
   
    ![Adição recolhida](./media/multi-step-logic-flow/add-action.png)
4. Na lista de possíveis ações, procure **criar arquivo**e, em seguida, selecione **Dropbox-criar arquivo**.
   
    ![Pesquisar criar arquivo](./media/multi-step-logic-flow/create-file-search.png)
5. Se solicitado, forneça suas credenciais do dropbox.
6. Selecione o ícone de pasta no lado direito da caixa **caminho da pasta** .
7. Localize e selecione a pasta na qual você deseja posicionar o novo arquivo.
   
    ![Pesquisar criar arquivo](./media/multi-step-logic-flow/create-file-folder.png)
8. Digite o nome do novo arquivo na caixa **nome do arquivo** . Lembre-se de acrescentar uma extensão, como ". txt", ao nome do arquivo. Aqui, vamos usar o **tweetid** no nome do arquivo para garantir a exclusividade dos arquivos. Talvez seja necessário selecionar **Ver mais** para localizar o token **tweetid** .
9. Adicione o texto que você deseja que o arquivo contenha digitando na caixa **conteúdo do arquivo** . Você também pode adicionar tokens à caixa **conteúdo do arquivo** .
   
    ![nome do arquivo e conteúdo](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Se você fornecer ao arquivo um nome que corresponda ao nome de um arquivo existente (na pasta selecionada), o arquivo existente será substituído.
   > 
   > 
10. Selecione **Atualizar fluxo**, que está localizado no menu na parte superior da tela.
11. Envie um tweet que contém a palavra-chave especificada.
    
     Em um minuto, um arquivo é criado em sua conta do dropbox.

## <a name="reorder-or-delete-an-action"></a>Reordenar ou excluir uma ação
* Para receber emails depois que o arquivo for criado no Dropbox, mova a ação do Dropbox arrastando sua barra de título para cima da ação de email. Libere a ação do Dropbox na seta entre o gatilho (**quando um novo tweet for Postado**) e a ação de email. (O cursor indica se a ação está posicionada corretamente.)
  
  > [!NOTE]
  > Você não pode mover uma etapa antes de outra se estiver usando qualquer saída dessa etapa.
  > 
  > 
  
    ![Excluir o menu](./media/multi-step-logic-flow/draggingaction.png)
* Para excluir uma ação, selecione as reticências (...) próximo à borda direita da barra de título para a ação que você deseja excluir, selecione **excluir**e, em seguida, selecione **OK**.
  
    ![Excluir o menu](./media/multi-step-logic-flow/deletemenu.png)
  
     **Observação:** Você não poderá excluir uma ação se estiver usando qualquer saída dela em qualquer lugar no fluxo. Primeiro, remova essas saídas dos campos e, em seguida, você pode excluir a ação.


## <a name="copy-and-paste-actions"></a>Copiar e colar ações

Se você quiser duplicar ações durante a criação de um fluxo, poderá copiá-las e colá-las. Por exemplo, se você estiver criando uma condição e quiser ações semelhantes no lado **se sim** e no lado **não** , em vez de criar as duas ações do zero, poderá criar a primeira ação em um lado e, em seguida, copiá-la para o outro lado.


### <a name="to-copy-an-action"></a>Para copiar uma ação
1. Selecione o menu de ação (o... na parte superior direita da ação).
1. Selecione **copiar para minha área de transferência**. 
1. Selecione a **nova etapa** onde você deseja que sua ação vá. 

     Observe a guia **minha área de transferência** que permite que você escolha entre todas as ações que você copiou.
1. Selecione o item que você deseja colar.

## <a name="add-advanced-options"></a>Adicionar opções avançadas
Comece com um fluxo que tenha uma ação **enviar um email** .

1. Selecione **Mostrar opções avançadas**, localizadas na parte inferior do cartão **enviar um email** .
   
     Em seguida, você verá as opções avançadas para enviar um email.
   
    ![Gatilhos do SharePoint](./media/multi-step-logic-flow/advanced.png)
2. Selecione **alta** na lista de **importância** e, em seguida, selecione **Ocultar opções avançadas** para ocultar as opções avançadas.
3. Selecione **Atualizar fluxo**, que está localizado no menu na parte superior da tela.
   
     Essa etapa salva as alterações.

