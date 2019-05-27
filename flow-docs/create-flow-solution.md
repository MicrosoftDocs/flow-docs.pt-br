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
ms.openlocfilehash: cbc6e3a8ffe50eb7ad27e80eba044957647a1da3
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456574"
---
# <a name="create-a-flow-in-a-solution"></a>Criar um fluxo em uma solução

Os fluxos criados em uma solução são chamados de fluxos com *reconhecimento de solução*. Para criar um fluxo com reconhecimento de solução, faça o seguinte:

## <a name="prerequisites"></a>Pré-requisitos

É necessário ter pelo menos uma solução para poder criar um fluxo com reconhecimento de solução.

## <a name="create-the-flow"></a>Criar o fluxo 

1. Entre no [Microsoft Flow](https://flow.microsoft.com).
1. Selecione **Soluções**, na barra de navegação.

   ![](./media/create-flow-solution/select-solutions-from-left-nav.png)

1. Selecione a solução na qual você criará o fluxo.

   ![](./media/create-flow-solution/new-solution-created.png)

1. Selecione **+ Novo** e **Fluxo**.

   ![](./media/create-flow-solution/select-new-flow.png)

   Isso abrirá o Microsoft Flow.

1. Use os conectores e gatilhos disponíveis para criar o fluxo.

   Neste exemplo, vamos criar um fluxo simples que envia uma notificação quando chega um email na Caixa de Entrada.
1. Procure o **Office 365 Outlook** e selecione-o.
1. Selecione o gatilho **Quando um novo email é recebido**.
1. Selecione **+ Nova etapa**.
1. Selecione a ação **Envie-me uma notificação por celular**.
1. Adicione o token dinâmico **Assunto** ao campo **Texto** da caixa **Envie-me uma notificação por celular**.
1. Atribua um nome e salve o fluxo.

   O fluxo deve ter a seguinte aparência:

   ![](./media/create-flow-solution/new-email-notification-flow.png)
   
1. Selecione **Soluções** para ver o fluxo na solução:

   ![](./media/create-flow-solution/new-flow-inside-solution.png)

## <a name="learn-more"></a>Saiba mais

* [Criar uma solução](./overview-solution-flows.md)
* [Exportar uma solução](./export-flow-solution.md)
* [Importar uma solução](./import-flow-solution.md)
* [Editar um fluxo com reconhecimento de solução](./edit-solution-aware-flow.md)
* [Remover um fluxo com reconhecimento de solução](./remove-solution-aware-flow.md)
