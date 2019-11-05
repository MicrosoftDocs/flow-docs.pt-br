---
title: Aprenda a gerenciar gateways de dados locais | Microsoft Docs
description: Exiba e instale um gateway de dados local no Microsoft Flow.
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
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3991e739178f86bbea3ae1b68b9d3337c42b4727
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547656"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Gerenciar um gateway de dados local no Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Instale e gerencie um gateway de dados local para integrar com segurança uma variedade de aplicativos baseados em nuvem com seus dados e aplicativos locais por meio de Microsoft Flow.

Com um gateway, você pode se conectar a dados locais por meio destas conexões:

* Apache Impala
* Conectores personalizados que você cria
* DB2
* Sistema de arquivos
* Http com o Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* Services
* SQL Server
* Teradata (versão prévia)

> [!IMPORTANT]
> Os gateways de dados do Microsoft SharePoint agora dão suporte ao tráfego HTTP e HTTPS.

## <a name="prerequisites"></a>Pré-requisitos

* O nome de usuário e a senha que você usou para [se inscrever](sign-up-sign-in.md) para Microsoft Flow.
* Permissões administrativas em um gateway.

  Você tem essas permissões por padrão para cada gateway que instalar. Além disso, um administrador de outro gateway pode lhe conceder essas permissões para esse gateway.
* Uma licença que dá suporte a gateways. Para obter mais informações, consulte a seção "conectividade" da [página de preços](https://flow.microsoft.com/pricing/).

> [!NOTE]
> Você pode criar um gateway e uma conexão local somente em seu [ambiente padrão](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Instalar um gateway

Para instalar um gateway, siga as etapas em [instalar um gateway de dados local](/data-integration/gateway/service-gateway-install). Instale o gateway no modo padrão porque o _Gateway de dados local (modo pessoal)_ está disponível apenas para Power bi.

## <a name="view-your-gateways"></a>Exibir seus gateways

No canto superior direito do [site Microsoft Flow](https://flow.microsoft.com), selecione o ícone de engrenagem e, em seguida, selecione **gateways**.

![Gateway em gerenciar][1]

> [!NOTE]
> Se você criou ou recebeu acesso a um gateway no PowerApps, esse gateway aparecerá na lista **meus gateways** em Microsoft Flow.

## <a name="cluster-your-gateways"></a>Clusterizar seus gateways

Você pode criar [clusters de alta disponibilidade de instalações de gateway de dados locais](/data-integration/gateway/service-gateway-high-availability-clusters) para evitar pontos únicos de falha ao acessar recursos de dados locais.

Por padrão, Microsoft Flow usa o gateway primário no cluster. Se o gateway primário não estiver disponível, o serviço alternará para o próximo gateway no cluster e assim por diante.

Depois de configurar um cluster de gateway, você pode permitir que o tráfego seja distribuído entre todos os gateways no cluster.

Siga estas etapas para distribuir o tráfego entre seus gateways:

1. Selecione **dados** na barra de navegação no lado esquerdo.
1. Selecione **gateways**.
1. Selecione qualquer um dos seus gateways.
1. Selecione **distribuir solicitações em todos os gateways ativos neste cluster**.
1. Selecione **aplicar** para salvar as alterações.

Para obter mais informações, consulte [entender gateways](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
