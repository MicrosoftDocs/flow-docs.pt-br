---
title: O aplicativo móvel do Microsoft Flow já tem suporte para o gerenciamento de aplicativo móvel do Microsoft Intune. | Microsoft Docs
description: O aplicativo móvel do Microsoft Flow já tem suporte para o gerenciamento de aplicativo móvel do Microsoft Intune.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 7cc2b37eb27ed0e2107eeaada02afb072d9a0098
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65060481"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Aplicativo móvel do Microsoft Flow com suporte para o Microsoft Intune

O aplicativo móvel do Microsoft Flow para iOS e Android tem suporte para o MAM (gerenciamento de aplicativo móvel) do Microsoft Intune sem registro de dispositivo. Os administradores de TI podem usar o MAM para criar e impor políticas de dados móveis, a fim de proteger os dados organizacionais.

## <a name="why-intune-support-is-important"></a>Saiba porque o suporte do Intune é importante

As organizações visam obter mais controle sobre os dados que residem nos dispositivos móveis dos funcionários. Elas podem querer restringir a maneira pela qual esses dados são movidos para os dispositivos e garantir que eles sejam removidos, caso os funcionários deixem a organização.

## <a name="what-is-microsoft-application-management-mam"></a>O que é o MAM (Gerenciamento de Aplicativo Móvel) da Microsoft

O MAM permite às organizações criar políticas que controlem como os aplicativos são usados no locatário. Isso inclui a imposição de criptografia de dados do aplicativo, a limitação da capacidade de copiar ou extrair dados apenas de aplicativos aprovados ou a imposição de PIN em dispositivos.

### <a name="prerequisites"></a>Pré-requisitos

- Uma [política de proteção do aplicativo](https://docs.microsoft.com/intune/app-protection-policies) do Intune.
- Um grupo do Microsoft Azure AD (Azure Active Directory).
- O Portal da Empresa. A principal vantagem de usar o MAM é que não é necessário registrar os dispositivos no Intune MAM. Tudo o que é necessário é o Portal da Empresa, que está disponível na App Store e na Google Play Store.
- A versão 2.31.0 do aplicativo móvel do Microsoft Flow para iOS, Android ou Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Criar uma política de proteção do aplicativo, atribuir aplicativos à política, definir configurações e adicionar usuários a um grupo do Microsoft Azure AD

Para gerenciar o aplicativo móvel do Microsoft Flow, é necessário:

1. Criar uma política de proteção do aplicativo.
1. Atribuir o aplicativo móvel do Microsoft Flow à política de proteção do aplicativo.
1. Atribuir as configurações da política. Por exemplo, você pode atribuir a política a fim de exigir um PIN para acessar o dispositivo móvel que executa o aplicativo móvel do Microsoft Flow.
1. Aplicar a política de proteção do aplicativo a um grupo específico do Microsoft Azure AD.
1. Adicionar todos os usuários aos quais a política de proteção do aplicativo se aplica ao grupo do Microsoft Azure AD.

Siga essas etapas para criar uma [política de proteção do aplicativo](https://docs.microsoft.com/intune/app-protection-policies) que exija aos usuários inserir um PIN para acessar o aplicativo móvel do Microsoft Flow. 


## <a name="test-the-app-protection-policy"></a>Testar a política de proteção do aplicativo

Depois de criar a política de proteção do aplicativo e atribuir usuários ao grupo do Microsoft Azure AD, é hora de usar o aplicativo móvel do Microsoft Flow e verificar se a política funciona.

Para verificar se a política funciona, faça o seguinte:

1. Instale o aplicativo móvel do Microsoft Flow em um dispositivo cuja plataforma corresponda a uma das plataformas que você definiu na política de proteção do aplicativo.
1. Entre no aplicativo móvel com uma conta que esteja no grupo do Microsoft Azure AD, que restrinja o uso do aplicativo móvel aos usuários que tenham um PIN.

Em seguida, você será solicitado a:
1. Instalar o Portal da Empresa.
1. Definir o PIN, caso ainda não tenha um PIN que atenda aos critérios da política de proteção do aplicativo.


## <a name="learn-more"></a>Saiba mais

Saiba como criar uma [política de proteção do aplicativo](https://docs.microsoft.com/intune/app-protection-policies).

