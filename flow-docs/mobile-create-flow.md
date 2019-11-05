---
title: Criar um fluxo do seu telefone | Microsoft Docs
description: Crie um fluxo de um modelo que, por exemplo, envie uma notificação por push ao receber emails de um endereço que você especificar
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/18/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 095b3a7f6565afff0a944bb08aee8f3a06ea114b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549054"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Criar um fluxo do seu telefone usando Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Crie um fluxo do seu telefone usando um modelo, que você pode encontrar pesquisando em uma lista de serviços, categorias de navegação ou especificando palavras-chave. Siga as etapas neste tópico para criar um fluxo que envia uma notificação por push ao seu telefone quando você recebe o email de seu gerente.

Se você não estiver familiarizado com Microsoft Flow, [obtenha uma visão geral](getting-started.md).

## <a name="prerequisites"></a>Pré-requisitos
* Uma [conta para Microsoft Flow](sign-up-sign-in.md).
* O aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [Ios](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows) em um [dispositivo com suporte](getting-started.md#use-the-mobile-app). Os gráficos neste tópico refletem a versão do aplicativo para iPhone, mas a interface em um dispositivo Android ou Windows Phone é semelhante.
* Para usar o modelo demonstrado neste tópico, você também precisará de:
  
  * Credenciais do Office 365.
  * Notificações por push habilitadas em seu telefone.

## <a name="find-a-template"></a>Localizar um modelo
1. Abra o aplicativo móvel e, em seguida, toque em **procurar** na parte inferior da tela.
   
    ![Ícone procurar](./media/mobile-create-flow/browse-icon.png)
   
    Você pode encontrar um modelo de qualquer uma destas maneiras:
   
   * Especifique uma palavra-chave na caixa de pesquisa na parte superior da tela.
   * Toque em uma opção na lista de serviços.
   * Role para baixo para mostrar uma variedade de categorias e, em seguida, toque em um modelo em qualquer categoria.
     
       ![Guia procurar](./media/mobile-create-flow/browse-tab.png)
     
     Para este tutorial, você abrirá o modelo que envia uma notificação por push quando você recebe o email de seu gerente.
2. Na lista de serviços, toque em **ver tudo**.
   
    ![Mostrar lista de serviços](./media/mobile-create-flow/list-services.png)
3. Toque no ícone para **notificação por push**.
   
    ![Notificações por push](./media/mobile-create-flow/push-notifications.png)
4. Na barra de pesquisa, digite **email**e, em seguida, toque no modelo para enviar uma notificação por push quando você receber uma mensagem do seu gerente.
   
    ![Escolher modelo](./media/mobile-create-flow/choose-template.png)
5. Na tela que fornece detalhes sobre o modelo que você selecionou, toque em **usar este modelo**.
   
    ![Confirmar modelo](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Concluir o fluxo
1. Se solicitado, toque **em entrar**e forneça suas credenciais para o Office 365 Outlook, os usuários do Office 365 ou ambos.
   
    ![Entrar no Office 365](./media/mobile-create-flow/office-signin.png)
   
    Você pode usar as mesmas conexões ao criar outros fluxos.
2. No canto superior direito, toque em **Avançar**.
   
    ![Toque em avançar](./media/mobile-create-flow/next.png)
   
    A próxima tela mostra o evento de gatilho e todas as ações resultantes.
   
    ![Eventos de gatilho e ações](./media/mobile-create-flow/flow-structure.png)
   
    Para esse modelo, novos emails disparam o fluxo, que recupera suas informações (incluindo o endereço do gerente) e envia uma notificação por push quando você recebe mensagens desse endereço. Alguns modelos exigem alguma personalização para funcionar corretamente, mas esse modelo não.
3. adicional Próximo à parte superior da tela, digite um nome diferente para o fluxo.
   
    ![Renomear fluxo](./media/mobile-create-flow/rename-flow.png)
4. No canto superior direito, toque em **criar**.
   
    ![criar fluxo](./media/mobile-create-flow/create-flow.png)
   
    Seu fluxo é criado e verificará se há mensagens do seu gerente até você pausar ou excluir o fluxo.

## <a name="next-steps"></a>Próximas etapas
* [Monitore sua atividade de fluxo](mobile-monitor-activity.md).
* [Gerencie seus fluxos](mobile-manage-flows.md).

