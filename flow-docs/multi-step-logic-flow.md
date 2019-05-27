---
title: Adicionar uma opção avançada e várias ações | Microsoft Docs
description: Expanda um fluxo para incluir uma opção avançada, como a configuração de um email como alta prioridade e adicionar outra ação para o mesmo evento.
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
ms.openlocfilehash: 9dd2aed8b8cdb1f0a8e673c5466291f60baaf41d
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64466485"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Adicione várias ações e opções avançadas a um fluxo
Personalize um fluxo, adicionando um ou mais opções avançadas e várias ações com o mesmo gatilho. Por exemplo, adicione uma opção avançada que envia uma mensagem de email como prioridade alta. Quando um item é adicionado a uma lista do SharePoint, além de enviar um email, crie um arquivo no Dropbox que contém as mesmas informações.

## <a name="prerequisites"></a>Pré-requisitos
* [Criar um fluxo](get-started-logic-flow.md)

## <a name="add-another-action"></a>Adicione outra ação
Neste procedimento, você adicionará uma ação no meio do fluxo. Esta ação salvará um arquivo no seu Dropbox, arquivando o item na lista.

1. Em [flow.microsoft.com](https://flow.microsoft.com), selecione **Meus fluxos** na barra de navegação superior.
2. Na lista de fluxos, selecione o fluxo que quer editar.
3. Selecione **Nova etapa** e **Adicionar uma ação**.
   
    ![Adicionar recolhido](./media/multi-step-logic-flow/add-action.png)
4. Na lista de possíveis ações, pesquise por **Criar arquivo** e, em seguida, selecione em **Dropbox – criar arquivo**.
   
    ![pesquisar criar arquivo](./media/multi-step-logic-flow/create-file-search.png)
5. Se solicitado, forneça suas credenciais do Dropbox.
6. Selecione o ícone de pasta no lado direito da caixa de **Caminho de pasta**.
7. Localize e selecione a pasta na qual você deseja colocar o novo arquivo.
   
    ![pesquisar criar arquivo](./media/multi-step-logic-flow/create-file-folder.png)
8. Insira o nome do novo arquivo na caixa **Nome de arquivo**. Certifique-se de acrescentar uma extensão, como ".txt", ao nome do arquivo. Aqui, vamos usar o **TweetId** no nome do arquivo para garantir que os arquivos são exclusivos. Pode ter que selecionar **Ver mais** para encontrar o token **TweetId**.
9. Adicione o texto que você deseja que o arquivo contenha ao digitá-lo na caixa de **Conteúdo do arquivo**. Também pode adicionar tokens na caixa **Conteúdo do arquivo**.
   
    ![nome e conteúdos do arquivo](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Se você der ao arquivo um nome que corresponda ao nome de um arquivo existente (na pasta selecionada), o arquivo existente será substituído.
   > 
   > 
10. Selecione **Atualizar fluxo**, que está localizado no menu da parte superior da tela.
11. Envie um tweet que contém a palavra-chave especificada.
    
     Dentro de um minuto, um arquivo é criado na sua conta do Dropbox.

## <a name="reorder-or-delete-an-action"></a>Reordenar ou excluir uma ação
* Para receber o email depois que o arquivo é criado no Dropbox, mova a ação do Dropbox, arrastando-a e soltando sua barra de título. Libere a ação do Dropbox sobre a seta entre o gatilho (**Quando é colocado um novo tweet**) e a ação de email. (O cursor indica se a ação está posicionada corretamente.)
  
  > [!NOTE]
  > Não será possível mover uma etapa antes da outra se você estiver usando qualquer saída dessa etapa.
  > 
  > 
  
    ![Exclua o menu](./media/multi-step-logic-flow/draggingaction.png)
* Para excluir uma ação, selecione as reticências (...) próximo a borda direita da barra de título da ação que você deseja excluir, selecione **Excluir** e, em seguida, selecione **OK**.
  
    ![Exclua o menu](./media/multi-step-logic-flow/deletemenu.png)
  
     **Observação:** Você não pode excluir uma ação se você estiver usando qualquer saída dela em qualquer lugar no fluxo. Primeiro, remova essas saídas dos campos e, em seguida, você pode excluir a ação.

## <a name="add-advanced-options"></a>Adicionar opções avançadas
Inicie um fluxo que contém uma ação **Enviar email**.

1. Selecione **Mostrar opções avançadas**, que está localizado na parte inferior do cartão **Enviar um email**.
   
     Em seguida, você verá as opções avançadas para enviar um email.
   
    ![Gatilhos do SharePoint](./media/multi-step-logic-flow/advanced.png)
2. Selecione **Alta** da lista de **Importância** e, em seguida, selecione **Ocultar opções avançadas** para ocultar as opções avançadas.
3. Selecione **Atualizar fluxo**, que está localizado no menu da parte superior da tela.
   
     Esta etapa salva as alterações.

