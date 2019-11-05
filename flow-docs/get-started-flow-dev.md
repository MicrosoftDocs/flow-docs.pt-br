---
title: Criar conectores personalizados e inserir fluxos | Microsoft Docs
description: Crie um conector personalizado, compartilhe-o, insira um fluxo e faça muito mais.
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
ms.date: 11/22/2017
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 80b1d17944d780a1800c91458ee674f5f2afe188
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548259"
---
# <a name="start-to-build-with-microsoft-flow"></a>Comece a criar com Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Aqui estão algumas das maneiras pelas quais você pode estender seu aplicativo com Microsoft Flow:

* Crie e conecte-se a um conector personalizado.
* Compartilhe seu conector personalizado com todos os Microsoft Flow usuários.
* Incorpore a experiência de fluxo em um aplicativo.
* Realce todos os conectores personalizados para que os usuários possam interagir com Microsoft Flow da melhor maneira para eles.

## <a name="prerequisites"></a>Pré-requisitos

* Uma conta de [Microsoft Flow](https://flow.microsoft.com) .

## <a name="create-a-custom-connector"></a>Criar um conector personalizado

Se você tiver um serviço Web ao qual deseja se conectar Microsoft Flow, primeiro será necessário criar um conector personalizado. Ao registrar um conector personalizado, você ensina Microsoft Flow sobre as características do seu serviço Web, incluindo a autenticação necessária, os gatilhos e as ações que ele suporta, bem como os parâmetros e as saídas de cada uma dessas ações.

Siga este tutorial para aprender a [registrar e usar conectores personalizados](https://powerapps.microsoft.com/tutorials/register-custom-api/). Depois de registrar seu conector personalizado, você pode compartilhá-lo na sua organização para teste.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Compartilhar um conector personalizado com todos os Microsoft Flow usuários

Depois de testar completamente seu conector personalizado, inicie o [processo de revisão](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) para que ele seja aprovado pela Microsoft para compartilhamento com todos os outros Microsoft Flow usuários.

Veja o que você precisará para o processo de revisão:

* Um arquivo OpenAPI que representa sua API e qualquer informação de autenticação.
* Um ícone para o conector.
* Uma descrição do conector.
* Aproximadamente 10 ideias sobre como seu conector pode beneficiar outros usuários por meio de modelos.

Depois de enviar essas informações, a Microsoft começa a avaliar a funcionalidade da API em Microsoft Flow e Microsoft PowerApps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Inserir a experiência de fluxo em seu site ou aplicativo

Você pode [inserir](developer/embed-flow-dev.md) Microsoft Flow em seu aplicativo para habilitar a integração profunda, no contexto, entre seu aplicativo e todos os outros serviços aos quais Microsoft Flow dá suporte. Por exemplo, você pode:

* Procure todos os modelos relacionados ao seu serviço e permita que os usuários selecionem um modelo.
* Gerencie os fluxos que os usuários têm relacionados ao seu aplicativo.

## <a name="next-steps"></a>Próximas etapas

Saiba como [inserir](developer/embed-flow-dev.md) Microsoft Flow em seu aplicativo.
