---
title: Gateway de dados local | Microsoft Docs
description: Este artigo é uma visão geral do gateway de dados local para Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8349361b7ee543c19635dc5899726d69adaa917a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544651"
---
# <a name="what-is-an-on-premises-data-gateway"></a>O que é um gateway de dados local?
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O gateway de dados local atua como uma ponte para fornecer transferência de dados rápida e segura entre dados locais (dados que não estão na nuvem) e vários serviços de nuvem da Microsoft. Esses serviços de nuvem incluem Power BI, PowerApps, Microsoft Flow, Azure Analysis Services e aplicativos lógicos do Azure. Usando um gateway, as organizações podem manter os bancos de dados e outras fontes em suas redes locais, mas, com segurança, usam os dados locais nos serviços de nuvem.

## <a name="how-the-gateway-works"></a>Como funciona o gateway

![Visão geral do gateway](media/gateway-reference/on-premises-data-gateway.png)

Para obter mais informações sobre como funciona o gateway, consulte [arquitetura do gateway de dados local](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Tipos de gateways

Há dois tipos diferentes de gateways, cada um para um cenário diferente:

- O **Gateway de dados local** permite que vários usuários se conectem a várias fontes de dados locais. Você pode usar um gateway de dados local com todos os serviços com suporte, com uma única instalação de gateway. Esse gateway é bem adequado para cenários complexos com várias pessoas acessando várias fontes de dados.

- O **Gateway de dados local (modo pessoal)** permite que um usuário se conecte a fontes e não possa ser compartilhado com outras pessoas. Um gateway de dados local (modo pessoal) pode ser usado somente com Power BI. Esse gateway é adequado para cenários em que você é a única pessoa que cria relatórios e não precisa compartilhar nenhuma fonte de dados com outras pessoas.

## <a name="use-a-gateway"></a>Usar um gateway

Há quatro etapas principais para usar um gateway.

1. [Baixe e instale o gateway](/data-integration/gateway/service-gateway-install) em um computador local.
2. [Configure](/data-integration/gateway/service-gateway-app) o gateway com base em seu firewall e outros requisitos de rede.
3. [Adicione administradores de gateway](/data-integration/gateway/service-gateway-manage) que também podem gerenciar e administrar outros requisitos de rede.
4. [Solucionar problemas](/data-integration/gateway/service-gateway-tshoot) do gateway em caso de erros.

## <a name="next-steps"></a>Próximas etapas

- [Instalar o gateway de dados local](/data-integration/gateway/service-gateway-install)
