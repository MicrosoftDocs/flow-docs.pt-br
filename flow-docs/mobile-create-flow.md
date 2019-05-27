---
title: Criar um fluxo usando o telefone | Microsoft Docs
description: Crie um fluxo de um modelo que, por exemplo, envia uma notificação por push quando você recebe uma mensagem de um endereço especificado
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
ms.openlocfilehash: f87320c61427957c02ff75675e4e15b938ac99f4
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64468793"
---
# <a name="create-a-flow-from-your-phone-by-using-microsoft-flow"></a>Crie um fluxo usando o telefone com o Microsoft Flow
Crie um fluxo através do seu telefone, usando um modelo que pode ser encontrado pesquisando em uma lista de serviços, navegando por categorias ou especificando palavras-chave. Siga as etapas deste tópico para criar um fluxo que envia uma notificação por push para o seu telefone, ao receber mensagens de seu gerente.

Se você não estiver familiarizado com o Microsoft Flow, [obtenha uma visão geral](getting-started.md).

## <a name="prerequisites"></a>Pré-requisitos
* Um [conta Microsoft Flow](sign-up-sign-in.md).
* O aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows) em um [dispositivo com suporte](getting-started.md#use-the-mobile-app). As imagens neste tópico refletem a versão do aplicativo para iPhone, mas a interface é semelhante em um dispositivo Android ou Windows Phone.
* Para usar o modelo demonstrado neste tópico, você também vai precisar de:
  
  * Credenciais do Office 365.
  * Notificações por push habilitadas em seu telefone.

## <a name="find-a-template"></a>Encontre um modelo
1. Abra o aplicativo móvel e, em seguida, toque em **Procurar** na parte inferior da tela.
   
    ![Ícone Procurar](./media/mobile-create-flow/browse-icon.png)
   
    Você pode encontrar um modelo de qualquer uma das seguintes maneiras:
   
   * Especifique uma palavra-chave na caixa de pesquisa na parte superior da tela.
   * Toque em uma opção na lista de serviços.
   * Role para baixo para mostrar uma variedade de categorias e, em seguida, toque em um modelo em qualquer categoria.
     
       ![Guia Procurar](./media/mobile-create-flow/browse-tab.png)
     
     Para este tutorial, você vai abrir o modelo que envia uma notificação por push ao receber mensagens de seu gerente.
2. Na lista de serviços, toque em **Ver todos**.
   
    ![Mostrar a lista de serviços](./media/mobile-create-flow/list-services.png)
3. Toque no ícone **Notificação por Push**.
   
    ![Notificações por push](./media/mobile-create-flow/push-notifications.png)
4. Na barra de pesquisa, digite **email** e, em seguida, toque no modelo para enviar uma notificação por push quando você receber uma mensagem de seu gerente.
   
    ![Escolha o modelo](./media/mobile-create-flow/choose-template.png)
5. Na tela que dá detalhes sobre o modelo que você selecionou, toque em **Usar este modelo**.
   
    ![Confirme o modelo](./media/mobile-create-flow/confirm-template.png)

## <a name="finish-the-flow"></a>Conclua o fluxo
1. Se solicitado, toque em **Entrar** e forneça suas credenciais para o Outlook do Office 365, usuários do Office 365 ou ambos.
   
    ![Entre no Office 365](./media/mobile-create-flow/office-signin.png)
   
    Você pode usar as mesmas conexões ao criar outros fluxos.
2. No canto superior direito, toque em **Avançar**.
   
    ![Toque em Avançar](./media/mobile-create-flow/next.png)
   
    A próxima tela mostra o evento de gatilho e todas as ações resultantes.
   
    ![Ações e eventos de gatilho](./media/mobile-create-flow/flow-structure.png)
   
    Para esse modelo, uma nova mensagem dispara o fluxo, que recupera as informações (incluindo o endereço do seu gerente) e envia uma notificação por push ao receber mensagens desse endereço. Alguns modelos exigem alguma personalização para funcionar corretamente, mas este modelo não.
3. (opcional) Na parte superior da tela, digite um nome diferente para o fluxo.
   
    ![Renomeie o fluxo](./media/mobile-create-flow/rename-flow.png)
4. No canto superior direito, toque em **Criar**.
   
    ![Criar fluxo](./media/mobile-create-flow/create-flow.png)
   
    O fluxo é criado e verificará se há mensagens de seu gerente até você pausar ou excluir o fluxo.

## <a name="next-steps"></a>Próximas etapas
* [Monitorar a atividade dos seus fluxos](mobile-monitor-activity.md).
* [Gerenciar seus fluxos](mobile-manage-flows.md).

