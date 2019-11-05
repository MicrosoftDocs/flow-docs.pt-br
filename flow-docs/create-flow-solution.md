---
title: Saiba como criar fluxos com reconhecimento de solução | Microsoft Docs
description: Saiba como criar fluxos com reconhecimento de solução.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbd1ee543cfe5f54b61486eefbacbd5bb837f33
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546468"
---
# <a name="create-a-flow-in-a-solution"></a>Criar um fluxo em uma solução
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os fluxos criados em uma solução são conhecidos como fluxos *com reconhecimento de solução* . Siga estas etapas para criar um fluxo com reconhecimento de solução.

## <a name="prerequisites"></a>Pré-requisitos

Você precisa ter pelo menos uma solução para poder criar um fluxo com reconhecimento de solução.

## <a name="create-the-flow"></a>Criar o fluxo 

1. Entre no [Microsoft Flow](https://flow.microsoft.com).
1. Selecione **soluções** na barra de navegação.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Selecione a solução na qual você criará seu fluxo.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Selecione **+ novo**e, em seguida, selecione **fluxo**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Microsoft Flow é aberto.

1. Use os conectores e os gatilhos disponíveis para criar seu fluxo.

   Neste exemplo, criaremos um fluxo simples que envia uma notificação quando um email chega em sua caixa de entrada.
1. Pesquise e selecione **Office 365 Outlook**.
1. Selecione o gatilho **quando um novo email chega** .
1. Selecione **+ nova etapa**.
1. Selecione a ação **enviar-me uma notificação móvel** .
1. Adicione o token dinâmico da **entidade** ao campo de **texto** da caixa **enviar-me uma notificação móvel** .
1. Dê um nome ao seu fluxo e salve o fluxo.

   Seu fluxo deve ser semelhante a este:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Selecione **soluções** para ver seu fluxo na solução:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Saiba Mais

* [Criar uma solução](./overview-solution-flows.md)
* [Exportar uma solução](./export-flow-solution.md)
* [Importar uma solução](./import-flow-solution.md)
* [Editar um fluxo com reconhecimento de solução](./edit-solution-aware-flow.md)
* [Remover um fluxo com reconhecimento de solução](./remove-solution-aware-flow.md)
