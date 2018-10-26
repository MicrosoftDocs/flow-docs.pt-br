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
ms.openlocfilehash: b25f63a3980d21e60b26a0783ac4bf5eb6030cd3
ms.sourcegitcommit: 282059c82bfcf5896d06043476c34641906e20e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2018
ms.locfileid: "49087898"
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



## <a name="view-your-gateways"></a>Exibir seus gateways

No canto superior direito do [site do Microsoft Flow](https://flow.microsoft.com), selecione o ícone de engrenagem e selecione **Gateways**.

![Gateway em gerenciamento][1]

> [!NOTE]
> Se você criou ou recebeu acesso a um gateway no PowerApps, esse gateway aparecerá na lista **Meus gateways** no Microsoft Flow.



## <a name="install-a-gateway"></a>Instalar um gateway

1. Faça download do [assistente de instalação do gateway](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).

1. Execute o assistente e forneça as mesmas credenciais com as quais você entrou no Microsoft Flow.

    Depois de registrar e configurar o gateway com êxito, ele aparecerá na lista **Gateways** no Microsoft Flow.

Para saber mais, consulte [Entender os gateways](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
