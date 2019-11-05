---
title: Visão geral de regiões para Microsoft Flow | Microsoft Docs
description: Visão geral com perguntas e respostas sobre regiões no Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 33c5a1c331d9874f6b794e8fd2ea92b541024ec6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548479"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Perguntas frequentes sobre regiões no Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Este documento fornece uma lista de perguntas frequentes sobre Microsoft Flow.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Como fazer descobrir onde meu fluxo está implantado?
O fluxo é implantado na [região](https://azure.microsoft.com/regions/) que hospeda o [ambiente](environments-overview-admin.md). Por exemplo, se o seu ambiente for criado na região da Europa, seu fluxo será implantado nos data centers da Europa.

Os administradores podem identificar a região se entrarem no centro de [Administração](https://admin.flow.microsoft.com)do Microsoft Flow. A guia **ambientes** lista todos os ambientes existentes e suas regiões.

![Exibir ambientes](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Quais regiões estão disponíveis?
* Estados Unidos
* Européia
* Centro
* Austrália
* Índia
* Japão
* Canadá
* América do Sul
* Reino Unido
* Governo dos EUA (GCC)
* França

## <a name="what-features-are-specific-to-a-given-region"></a>Quais recursos são específicos para uma determinada região?
Os ambientes podem ser criados em regiões diferentes e estão associados a esse local geográfico. Quando você cria um fluxo em um ambiente, esse fluxo é implantado em data centers nesse local geográfico. Isso se aplica a todos os itens que você criar nesse ambiente, incluindo o modelo de dados comum, fluxos, conexões, gateways, aplicativos e conectores personalizados.

Para obter um desempenho ideal, crie seu ambiente na região mais próxima de seus usuários. Por exemplo, se os usuários estiverem na Europa, crie seus ambientes na região da Europa. Se os usuários estiverem na Estados Unidos, crie seus ambientes na região Estados Unidos.

## <a name="gateways"></a>gateways
Os gateways são:

* Não está disponível na região da Índia.
* Com suporte apenas no ambiente padrão, não em ambientes personalizados.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>O está Microsoft Flow disponível em nuvens nacionais?
Ok. [Saiba mais](./us-govt.md).

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Quais endereços IP de saída são usados em cada região?
Consulte [limites e configuração](limits-and-config.md).

