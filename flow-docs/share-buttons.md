---
title: Compartilhe seus botões com outras pessoas. | Microsoft Docs
description: Compartilhe seus botões com outras pessoas para que possam usar os botões e economizar tempo.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 77b46d10ec3856054dcc8e1734b327bac9a01596
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64465707"
---
# <a name="share-button-flows-in-microsoft-flow"></a>Compartilhar fluxos de botão no Microsoft Flow
No aplicativo móvel do Microsoft Flow, você pode compartilhar [fluxos de botão](introduction-to-button-flows.md) (botões) com outros usuários ou grupos em sua organização. Quando você compartilha um botão, a pessoa ou grupo com quem você compartilha pode executar seu botão, da mesma maneira que executam seus próprios botões. Você também pode [compartilhar um link](share-buttons.md#re-share-a-button) para botões que outra pessoa compartilhou com você. Você pode [parar de compartilhar](share-buttons.md#stop-sharing-a-button) seus botões a qualquer momento.

> As capturas de tela usadas neste documento foram executadas em um dispositivo Android. Se você estiver usando um iPhone, as imagens podem parecer diferentes, mas a funcionalidade é a mesmo.
> 
> 

Siga [essas etapas](share-buttons.md#use-shared-buttons) para usar um botão que alguém compartilhou com você.

## <a name="prerequisites"></a>Pré-requisitos
Para compartilhar botões, você precisará de:

* Uma conta com acesso ao [Microsoft Flow](https://flow.microsoft.com).
* Um fluxo para compartilhar.
* Um dispositivo móvel com o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows).
* Um grupo ou usuário em sua organização com os quais compartilhar seu botão.

## <a name="share-a-button"></a>Compartilhar um botão
Você pode compartilhar um botão na guia **Botões** do aplicativo móvel do Microsoft Flow.

1. Toque no ícone pequeno ao lado do botão que você deseja compartilhar.
   
    ![compartilhar botão](./media/share-buttons/share-button-flows-buttons-tab.png)
2. Toque em **Convidar outras pessoas** na página **Usuários do botão**.
   
    ![compartilhar botão](./media/share-buttons/share-button-flows-button-users.png)
3. Procure e selecione o grupo ou a pessoa com quem você gostaria de compartilhar o botão.
   
    ![compartilhar botão](./media/share-buttons/share-button-flows-invite-others-select.png)
4. Toque em **ENVIAR** na página **Convidar outras pessoas**.
   
    ![compartilhar botão](./media/share-buttons/share-button-flows-invite-others-send.png)
5. Toque em **CONCLUIR** na página que indica o botão compartilhando a operação concluída com êxito.
   
    ![compartilhar botão](./media/share-buttons/share-button-flows-invite-others-done.png)

## <a name="require-users-to-use-their-own-connections"></a>Exigir que os usuários usem suas próprias conexões
> [!NOTE]
> Quando você compartilha um botão, pode permitir que as pessoas com quem compartilhou o botão usem todas as conexões usadas pelo botão. Você também pode exigir que eles usem suas próprias conexões. Se você permitir que outras pessoas usem suas conexões, elas não poderão acessar as credenciais em sua conexão ou reutilizá-las em qualquer outro fluxo.
> 
> 

Siga estas etapas para exigir que as pessoas com quem você compartilhou os botões para usar suas próprias conexões.

1. Selecione **GERENCIAR CONEXÕES** na tela exibida imediatamente depois que você compartilha um botão.
2. Selecione **EDITAR** no botão que você deseja gerenciar.
3. Selecione **Fornecido pelo usuário** ou seu endereço de email.
   
    Sua escolha indica as conexões de quem devem ser usadas no botão compartilhado.
   
    ![compartilhar botão](./media/share-buttons/share-button-select-connection-provided-by-user.png)
   
    Você pode exibir ou alterar sua opção a qualquer momento. Para fazer isso, selecione a guia **Fluxos** > o fluxo que você compartilhou > **Usuários e conexões** > a guia **CONEXÕES** > **EDITAR** no botão que você deseja gerenciar.
   
    ![compartilhar botão](./media/share-buttons/share-button-flows-conn-provided-by-user.png)

## <a name="view-the-list-of-button-users"></a>Exibir a lista de usuários de botão
Você pode exibir todos os grupos ou usuários com o qual um botão é compartilhado seguindo estas etapas na guia **Botões**:

1. Toque no ícone pequeno ao lado do botão no qual você está interessado.
2. Na página **Usuários de botão**, exiba todos os grupos ou usuários com o qual o botão é compartilhado.
   
    ![exibir usuários de botão](./media/share-buttons/share-button-flows-button-users-list.png)

## <a name="stop-sharing-a-button"></a>Interromper o compartilhamento de um botão
Você pode interromper o compartilhamento de um botão seguindo estas etapas na guia **Botões**:

1. Toque no ícone pequeno ao lado do botão que você não deseja mais compartilhar.
2. Na página **Usuários de botão**, toque no usuário ou grupo com o qual você deseja interromper o compartilhamento do botão.
   
    ![interromper o compartilhamento de um botão](./media/share-buttons/share-button-flows-remove-user-list.png)
3. Toque em **Remover usuário** quando a página do usuário for exibida.
   
    ![interromper o compartilhamento de um botão](./media/share-buttons/share-button-flows-remove-user.png)
4. Aguarde a conclusão da operação de remoção. Observe que a lista **Usuários de botão** atualiza e o usuário ou grupo que você removeu não está mais listado.
   
    ![interromper o compartilhamento de um botão](./media/share-buttons/share-button-flows-remove-user-result.png)

## <a name="monitor-the-run-history"></a>Monitorar o histórico de execução
Todos os históricos de execução, incluindo as execuções iniciadas por uma pessoa com a qual um botão foi compartilhado, serão exibidos somente na guia **Atividade** do aplicativo móvel do Microsoft Flow do criador do botão.

## <a name="use-shared-buttons"></a>Use os botões compartilhados
Antes de executar um botão que alguém tenha compartilhado com você, adicione-o à sua guia **Botões** na página **Adicionar botões**.

1. Toque em **GET MORE** (ou na faixa **Novos botões estão disponíveis** se ela aparecer) na guia **Botões**.
   
    ![novos botões compartilhados comigo](./media/share-buttons/share-button-flows-banner.png)
2. Toque no botão que você deseja usar.
   
    O botão tocado será adicionado imediatamente à guia **Botões** do aplicativo do Microsoft Flow. Você pode usar o fluxo da guia **Botões**, assim como qualquer outro botão que está listado.
   
    ![novos botões compartilhados comigo](./media/share-buttons/share-button-flows-buttons-shared-with-me.png)

## <a name="re-share-a-button"></a>Compartilhar um botão novamente
Você pode compartilhar um link para um botão que foi compartilhado com você.

1. Selecione **...** ao lado do botão que você deseja compartilhar.
2. Selecione **link do botão Compartilhar**.
   
    ![link do botão compartilhar novamente](./media/share-buttons/re-share-button.png)
3. Selecione o aplicativo que você gostaria de usar para compartilhar o botão e então acompanhe as etapas para enviar o botão para a pessoa com a qual você deseja compartilhar.

## <a name="stop-using-a-shared-button"></a>Parar de usar um botão compartilhado
Se você não quiser usar um botão que foi compartilhado com você, remova-o da guia **Botões** executando as seguintes etapas:

1. Na guia **Botões**, toque em **...** ao lado do botão que você não deseja mais usar.
   
    ![remover botão](./media/share-buttons/share-button-flows-added-shared-button.png)
2. Toque em **Remover** no menu que é exibido.

É só isso. O botão não aparecerá mais na guia **Botões** do aplicativo Microsoft Flow.

> [!NOTE]
> Depois de remover um botão compartilhado, adicione-o novamente selecionando **GET MORE** na guia **Botões**.
> 
> 

