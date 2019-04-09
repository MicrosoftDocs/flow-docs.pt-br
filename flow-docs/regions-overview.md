---
title: Visão geral das regiões no Microsoft Flow | Microsoft Docs
description: Visão geral de perguntas e respostas sobre regiões no Microsoft Flow
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
ms.openlocfilehash: dce9fa4bb838f931acdcd95710d82d15bdc7dd24
ms.sourcegitcommit: 17bb4525b881ab2095bdfa4a573a186f6b7b1fd6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2019
ms.locfileid: "58913091"
---
# <a name="faq-for-regions-in-microsoft-flow"></a>Perguntas Frequentes sobre regiões no Microsoft Flow
Este documento fornece uma lista de perguntas frequentes sobre o Microsoft Flow.

## <a name="how-do-i-find-out-where-my-flow-is-deployed"></a>Como posso descobrir onde o meu fluxo está implantado?
O fluxo é implantado na [região](https://azure.microsoft.com/regions/) que hospeda o [ambiente](environments-overview-admin.md). Por exemplo, se seu ambiente for criado na região da Europa, o seu fluxo é implantado nos data centers da Europa.

Os administradores podem identificar a região se eles entrarem no [centro de administração](https://admin.flow.microsoft.com) do Microsoft Flow. A guia **Ambientes** lista todos os ambientes e regiões existentes.

![exibir ambientes](media/regions-overview/environments-list.png)

## <a name="what-regions-are-available"></a>Quais regiões estão disponíveis?
* Estados Unidos
* Europa
* Ásia
* Austrália
* Índia
* Japão
* Canadá
* América do Sul
* Reino Unido
* (GCC) do Governo dos EUA

## <a name="what-features-are-specific-to-a-given-region"></a>Quais recursos são específicos a uma determinada região?
Os ambientes podem ser criados em diferentes regiões e são associados a esse local geográfico. Quando você cria um fluxo em um ambiente, esse fluxo é implantado em datacenters neste local geográfico. Isso se aplica a qualquer item que você criar no ambiente, incluindo o modelo de dados comuns, fluxos, conexões, gateways, aplicativos e conectores personalizados.

Para obter um melhor desempenho, crie seu ambiente na região mais próxima de seus usuários. Por exemplo, se os usuários estiverem na Europa, crie seus ambientes na região da Europa. Se os usuários estiverem nos Estados Unidos, crie seus ambientes na região dos Estados Unidos.

## <a name="gateways"></a>Gateways
Os gateways são:

* Não está disponível na região Índia.
* Suportado apenas nos ambientes padrão, não nos ambientes personalizados.

## <a name="is-microsoft-flow-available-in-national-clouds"></a>O Microsoft Flow está disponível em nuvens nacionais?
Não, o Microsoft Flow não está disponível nas nuvens nacionais. O suporte para as nuvens nacionais está planejado para 2018.

## <a name="what-outbound-ip-addresses-are-used-in-each-region"></a>Quais endereços IP de saída são usados em cada região?
Veja [Limites e configuração](limits-and-config.md).

