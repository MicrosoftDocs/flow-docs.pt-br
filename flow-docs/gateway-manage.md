---
title: Saiba como gerenciar os gateways de dados locais | Microsoft Docs
description: Exibir e instalar um gateway de dados local no Microsoft Flow
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
ms.date: 02/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b8b14f720736a60b04cbd9ae23dec5c0524ff03c
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65054061"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Gerenciar um gateway de dados locais no Microsoft Flow

Instale e gerencie um gateway de dados local para integrar com segurança uma variedade de aplicativos baseados em nuvem com dados e aplicativos locais por meio do Microsoft Flow.

Com um gateway, você pode conectar aos dados locais através dessas conexões:

* Apache Impala
* Conectores personalizados criados por você
* DB2
* Sistema de arquivos
* HTTP com Microsoft Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (Versão prévia)

> [!IMPORTANT]
> Agora, os gateways de dados do Microsoft SharePoint suportam os tráfegos HTTP e HTTPS.

## <a name="prerequisites"></a>Pré-requisitos

* O nome de usuário e senha usados para se [inscrever](sign-up-sign-in.md) no Microsoft Flow.
* Permissões administrativas em um gateway.

  Você tem essas permissões por padrão para cada gateway que instalar. Além disso, um administrador de outro gateway pode conceder essas permissões para esse gateway.
* Uma licença que oferece suporte a gateways. Para obter mais informações, confira a seção “Conectividade” da [página de preços](https://flow.microsoft.com/pricing/).

> [!NOTE]
> Crie um gateway e uma conexão local em seu [ambiente padrão](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Instalar um gateway

1. Faça download do [assistente de instalação do gateway](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).

1. Execute o assistente e forneça as mesmas credenciais com as quais você entrou no Microsoft Flow.

    Depois de registrar e configurar o gateway com êxito, ele aparecerá na lista **Gateways** no Microsoft Flow.

## <a name="view-your-gateways"></a>Exibir seus gateways

No canto superior direito do [site do Microsoft Flow](https://flow.microsoft.com), selecione o ícone de engrenagem e selecione **Gateways**.

![Gateway em gerenciamento][1]

> [!NOTE]
> Se você criou ou recebeu acesso a um gateway no PowerApps, esse gateway aparecerá na lista **Meus gateways** no Microsoft Flow.


## <a name="cluster-your-gateways"></a>Agrupar os gateways

Você pode criar *clusters de alta disponibilidade de instalações do gateway de dados local* para evitar pontos únicos de falha, ao acessar recursos de dados locais. 

Por padrão, o Microsoft Flow usa o gateway principal do cluster. Se o gateway principal não estiver disponível, o serviço alternará para o gateway seguinte do cluster, e assim por diante.

Depois de configurar um cluster de gateway, você pode permitir que o tráfego seja distribuído por todos os gateways do cluster. 

Para distribuir o tráfego entre os gateways, faça o seguinte:

1. Selecione **Dados** na barra de navegação à esquerda.
1. Selecione **Gateways**.
1. Selecione o gateway desejado.
1. Selecione **Distribua solicitações em todos os gateways ativos neste cluster**.
1. Selecione **Aplicar** para salvar as alterações.


Para saber mais, consulte [Entender os gateways](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
