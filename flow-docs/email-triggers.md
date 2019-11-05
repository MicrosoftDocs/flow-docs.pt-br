---
title: Executar fluxos com base em Propriedades de email | Microsoft Docs
description: Inicie um fluxo com base em propriedades como o assunto, o endereço do remetente ou o endereço do destinatário de um email.
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
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b1dcb98d5bb99c9eaf2843ec75a8bdfaf03fa913
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544949"
---
# <a name="trigger-a-flow-based-on-email-properties"></a>Disparar um fluxo com base em Propriedades de email
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Use o gatilho **quando um novo email chega** para criar um fluxo que é executado quando uma ou mais das seguintes propriedades de email correspondem aos critérios que você fornece:

| Propriedade | Quando usar |
| --- | --- |
| Pasta |Dispare um fluxo sempre que os emails chegam em uma pasta específica. Essa propriedade pode ser útil se você tiver regras que roteiam emails para pastas diferentes. |
| Para |Dispare um fluxo com base no endereço para o qual um email foi enviado. Essa propriedade poderá ser útil se você receber emails que foram enviados a endereços de email diferentes na mesma caixa de entrada. |
| De |Dispare um fluxo com base no endereço de email do remetente. |
| Porta |Dispare um fluxo com base na importância com a qual os emails foram enviados. O email pode ser enviado com importância alta, normal ou baixa. |
| Tem anexo |Dispare um fluxo com base na presença de anexos em emails de entrada. |
| Filtro de assunto |Procure a presença de palavras específicas no assunto de um email. Em seguida, o fluxo executa *ações* baseadas nos resultados da pesquisa. |

> [!IMPORTANT]
> Cada [plano de Microsoft Flow](https://flow.microsoft.com/pricing/) inclui uma cota de execução. Sempre verifique as propriedades no gatilho do fluxo quando possível. Isso evita o uso de sua cota de execução desnecessariamente. Se você marcar uma propriedade em uma condição, cada execução contará em relação à cota de execução do plano, mesmo que a condição de filtro definida não seja atendida. 

Por exemplo, se você verificar o endereço *de* um email em uma condição, cada execução contará em relação à cota de execução do plano, mesmo que *não seja* o endereço que lhe interessa.
> 
> 

Nas orientações a seguir, verificamos todas as propriedades no gatilho **quando um novo email chega** . Saiba mais visitando as [perguntas de cobrança frequentes](billing-questions.md#what-counts-as-a-run) e a página de [preços](https://ms.flow.microsoft.com/pricing/) .

## <a name="prerequisites"></a>Pré-requisitos
* Uma conta com acesso a [Microsoft Flow](https://flow.microsoft.com)
* Uma conta do Outlook do Office 365
* O aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [Ios](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows)
* Conexões com o Office, o Outlook e o serviço de notificação por push

## <a name="trigger-a-flow-based-on-an-emails-subject"></a>Disparar um fluxo com base no assunto de um email
Neste tutorial, criamos um fluxo que envia uma notificação por push para seu celular se o assunto de um novo email tiver a palavra "loteria". Em seguida, o fluxo marca qualquer email como *lido*.

>[!NOTE]
>Embora este passo a passos envie uma notificação por push, você está livre para usar qualquer outra ação que atenda às suas necessidades de fluxo de trabalho. Por exemplo, você pode armazenar o conteúdo do email em outro repositório, como planilhas do Google ou um arquivo do Microsoft Excel armazenado no dropbox.

Ok, vamos começar:

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Na caixa **filtro de assunto** , insira o texto que seu fluxo usa para filtrar emails de entrada.
   
     Neste exemplo, estamos interessados em qualquer email que tenha a palavra "loteria" no assunto.
   
    ![opções avançadas](./media/email-triggers/email-triggers-subject-text.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Insira os detalhes da notificação móvel que você deseja receber ao receber um email que corresponda ao filtro de **assunto** especificado anteriormente.
   
    ![Detalhes da notificação](./media/email-triggers/email-triggers-4.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Dê um nome ao seu fluxo. Em seguida, salve-o selecionando **criar fluxo** na parte superior da página.
   
    ![salvar fluxo](./media/email-triggers/email-triggers-subject-notification.png)

Congratula! Agora você receberá uma notificação por push sempre que receber um email contendo a palavra "loteria" no assunto.

## <a name="trigger-a-flow-based-on-an-emails-sender"></a>Disparar um fluxo com base no remetente de um email
Neste tutorial, criamos um fluxo que envia uma notificação por push para seu celular se qualquer email novo chegar de um remetente específico (endereço de email). O fluxo também marca qualquer email como *lido*.

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-inbox-folder](includes/sign-in-use-blank-select-email-trigger-and-inbox-folder.md)]

1. Na caixa **de** , insira o endereço de email do remetente. 
   
     Seu fluxo executa uma ação em todos os emails enviados deste endereço.
   
    ![Propriedade de email](./media/email-triggers/email-triggers-from.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Insira os detalhes da notificação móvel que você gostaria de receber sempre que uma mensagem chegar do endereço de email que você inseriu anteriormente.
   
    ![Detalhes da notificação](./media/email-triggers/email-triggers-sender-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Dê um nome ao seu fluxo e salve-o selecionando **criar fluxo** na parte superior da página.
   
    ![salvar fluxo](./media/email-triggers/email-triggers-sender-5.png)

## <a name="trigger-a-flow-when-emails-arrive-in-a-specific-folder"></a>Disparar um fluxo quando os emails chegam em uma pasta específica
Se você tiver regras que roteiam email para pastas diferentes com base em determinadas propriedades, como o endereço, talvez você queira esse tipo de fluxo.

Vamos começar:

> [!NOTE]
> Se você ainda não tiver uma regra que roteia emails para uma pasta que não seja sua caixa de entrada, crie essa regra e confirme se ela funciona enviando um email de teste.
> 
> 

[!INCLUDE [sign-in-use-blank-select-email-trigger-and-specific-folder](includes/sign-in-use-blank-select-email-trigger-and-specific-folder.md)]

1. Selecione a pasta para a qual você está roteando emails específicos. Para exibir todas as pastas de email, primeiro selecione o ícone **Mostrar seletor** , que está localizado no lado direito da caixa **pasta** , no cartão **quando um novo email chega** .
   
    ![Selecionar pasta](./media/email-triggers/email-triggers-2.png)

    [!INCLUDE [add-mobile-notification-action](includes/add-mobile-notification-action.md)]

1. Insira os detalhes da notificação móvel que você gostaria de receber quando um email chega na pasta que você selecionou anteriormente. Se você ainda não fez isso, insira as credenciais para o serviço de notificações.
   
    ![Detalhes da notificação](./media/email-triggers/email-triggers-folder-notification.png)

    [!INCLUDE [add-mark-as-read-action](includes/add-mark-as-read-action.md)]

1. Dê um nome ao seu fluxo e salve-o selecionando **criar fluxo** na parte superior da página.
   
    ![salvar fluxo](./media/email-triggers/email-triggers-7.png)

Teste o fluxo enviando um email que é roteado para a pasta que você selecionou anteriormente neste passo a passos.

