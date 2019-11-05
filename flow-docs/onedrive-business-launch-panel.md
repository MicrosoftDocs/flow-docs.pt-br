---
title: Criar fluxos do painel de início do OneDrive for Business | Microsoft Docs
description: Crie fluxos do painel de início do OneDrive for Business.
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
ms.date: 08/25/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d7ed30741fcc85fea87f5be2d76a8150a0c42100
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548593"
---
# <a name="create-flows-from-the-onedrive-for-business-launch-panel"></a>Criar fluxos do painel de início do OneDrive for Business
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Semelhante ao painel de [inicialização de Microsoft Flow no SharePoint](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/), você pode executar fluxos em arquivos específicos no onedrive for Business. 

Esse recurso permite que a pessoa que executa o fluxo use suas próprias credenciais, o que é especialmente aplicável para fluxos que foram criados por um departamento de ti. 

Os usuários também podem obter prompts para entradas de tempo de execução como **Aprovador** ou **mensagem**, que podem ser do tipo texto, arquivo, email, booliano ou número.

Neste tutorial, criaremos um fluxo simples que usa um dos muitos [modelos do onedrive for Business](https://flow.microsoft.com/search/?q=OneDrive) para solicitar a aprovação de um arquivo pelo gerente do solicitante.

## <a name="create-a-flow-that-requests-manager-approval-for-a-file-in-onedrive-for-business"></a>Criar um fluxo que solicita aprovação do gerente para um arquivo no OneDrive for Business

1. Entre no OneDrive for Business.
1. Localize e selecione o arquivo no qual você deseja criar o fluxo.
1. Selecione o link **Mostrar ações** (três pontos).
1. Selecione **flow** > **criar um fluxo**.

     ![criar fluxo](./media/onedrive-launch-panel/create-flow.png) 

1. Selecione um dos modelos.

    Neste exemplo, selecione a **aprovação de solicitação do meu gerente para o modelo de arquivo selecionado** .

     >[!TIP]
     >Entre em qualquer conector que solicite que você entre.

1. Selecione **continuar**.
1. Faça as alterações desejadas no modelo e salve o fluxo com um nome que você se lembrará facilmente.

## <a name="run-the-flow"></a>Executar o fluxo

1. Entre no OneDrive for Business.
1. Localize e selecione o arquivo em que a aprovação do Gerenciador de solicitações.
1. Selecione o link **Mostrar ações** (três pontos).
1. Selecione **fluxo**. Você verá o fluxo que você criou anteriormente.
1. Selecione o fluxo que você criou anteriormente.

     ![Executar seu fluxo](./media/onedrive-launch-panel/run-flow.png)


>[!TIP]
>Embora este passo a passos mostre como criar um fluxo de um modelo, você também pode criar um fluxo de em branco para usar qualquer uma das centenas de conectores disponíveis no Microsoft Flow.

## <a name="learn-more"></a>Saiba Mais

- [Introdução ao Microsoft Flow](getting-started.md) 
- [Criar fluxos de várias etapas](multi-step-logic-flow.md)
