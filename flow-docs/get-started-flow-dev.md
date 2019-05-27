---
title: Criar conectores personalizados e inserir fluxos|Microsoft Docs
description: Crie um conector personalizado, compartilhe-o, insira um fluxo e faça muito mais.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: barathb
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 21f35216231193f40c1a723dda62bb3a2ad1be59
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460501"
---
# <a name="start-to-build-with-microsoft-flow"></a>Começar a criar com o Microsoft Flow

Aqui estão algumas das maneiras de estender o aplicativo com o Microsoft Flow:

* Crie e conecte-se com um conector personalizado.
* Compartilhe seu conector personalizado com todos os usuários do Microsoft Flow.
* Insira a experiência de fluxo dentro de um aplicativo.
* Destaque todos os conectores personalizados para que os usuários possam interagir com o Microsoft Flow da melhor maneira para eles.

## <a name="prerequisites"></a>Pré-requisitos

* Uma conta do [Microsoft Flow](https://flow.microsoft.com).

## <a name="create-a-custom-connector"></a>Criar um conector personalizado

Se você tiver um serviço Web com o qual deseja se conectar do Microsoft Flow, terá de criar primeiro um conector personalizado. Ao registrar um conector personalizado, você informa ao Microsoft Flow sobre as características do seu serviço Web, incluindo a autenticação necessária, os gatilhos e as ações a que ele dá suporte e os parâmetros e as saídas para cada uma dessas ações.

Siga este tutorial para saber como [Registrar e usar conectores personalizados](https://powerapps.microsoft.com/tutorials/register-custom-api/). Depois de registrar seu conector personalizado, você pode compartilhá-lo dentro de sua organização para teste.

## <a name="share-a-custom-connector-with-all-microsoft-flow-users"></a>Compartilhar um conector personalizado com todos os usuários do Microsoft Flow

Depois de testar completamente seu conector personalizado, inicie o [processo de revisão](https://flow.microsoft.com/blog/calling-all-saas-apps-now-you-can-build-your-own-connector-for-flow-and-logic-apps/) para que ele seja aprovado pela Microsoft, para compartilhar com todos os outros usuários do Microsoft Flow.

Veja o que será necessário para o processo de revisão:

* Um arquivo OpenAPI que representa sua API e informações de autenticação.
* Um ícone para o conector.
* Uma descrição do seu conector.
* Cerca de 10 ideias de como o seu conector pode beneficiar outros usuários por meio de modelos.

Depois de enviar essas informações, a Microsoft começa a avaliar a funcionalidade da API no Microsoft Flow e no Microsoft PowerApps.

## <a name="embed-the-flow-experience-into-your-website-or-app"></a>Inserir a experiência de fluxo no site ou aplicativo

Você pode [inserir](developer/embed-flow-dev.md) o Microsoft Flow no seu aplicativo para habilitar a integração profunda, em contexto, entre o aplicativo e todos os outros serviços aos quais o Microsoft Flow dá suporte. Por exemplo, você pode:

* Procurar todos os modelos relacionados ao serviço e permitir que usuários selecionem um modelo.
* Gerenciar os fluxos que os usuários relacionaram ao aplicativo.

## <a name="next-steps"></a>Próximas etapas

Saiba como [inserir](developer/embed-flow-dev.md) o Microsoft Flow em seu aplicativo.
