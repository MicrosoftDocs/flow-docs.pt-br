---
title: Microsoft Flow aplicativo móvel agora dá suporte ao gerenciamento de aplicativos móveis do Microsoft Intune. | Microsoft Docs
description: Microsoft Flow aplicativo móvel agora dá suporte ao gerenciamento de aplicativos móveis do Microsoft Intune.
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
ms.openlocfilehash: d5709d7f98c3f4cc1dcf7d0da8fc5c9501adb84c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547385"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Microsoft Flow aplicativo móvel dá suporte a Microsoft Intune
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O aplicativo móvel Microsoft Flow para iOS e Android dá suporte ao MAM (gerenciamento de aplicativo móvel) do Intune sem registro de dispositivo. O uso do MAM permite que os administradores de ti criem e imponham políticas de dados móveis para proteger dados organizacionais.

## <a name="why-intune-support-is-important"></a>Por que o suporte do Intune é importante

As organizações estão procurando mais controle sobre os dados que residem em dispositivos móveis de funcionários. As organizações podem querer restringir a forma como os dados são movidos para o dispositivo e garantir que os dados sejam removidos, caso o funcionário saia da organização.

## <a name="what-is-microsoft-application-management-mam"></a>O que é o MAM (Microsoft Application Management)

O MAM permite que as organizações criem políticas que regem como os aplicativos são usados dentro de um locatário. Isso inclui a imposição da criptografia de dados de aplicativo, limitando a capacidade de copiar ou extrair dados para apenas aplicativos aprovados ou impor um PIN em um dispositivo.

### <a name="prerequisites"></a>Pré-requisitos

- Uma [política de proteção de aplicativo](https://docs.microsoft.com/intune/app-protection-policies)do Intune.
- Um grupo Azure Active Directory (Azure AD).
- Portal da Empresa. Um dos principais benefícios do uso do MAM é que os dispositivos não precisam ser registrados no MAM do Intune. Tudo o que é necessário é o Portal da Empresa, que está disponível na loja de aplicativos e na loja de Google Play.
- Versão 2.31.0 do aplicativo móvel Microsoft Flow para iOS, Android ou Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Criar uma política de proteção de aplicativo, atribuir aplicativos à política, definir configurações e adicionar usuários a um grupo do Azure AD

Para que o aplicativo móvel Microsoft Flow seja gerenciado, você deve:

1. Criar uma política de proteção de aplicativo.
1. Atribua o aplicativo móvel Microsoft Flow à política de proteção do aplicativo.
1. Atribua as configurações de política. Por exemplo, você pode atribuir a política para exigir um PIN para acessar o dispositivo móvel que executa o aplicativo Microsoft Flow Mobile.
1. Aplique a política de proteção de aplicativo a um grupo específico do Azure AD.
1. Adicione todos os usuários aos quais a política de proteção de aplicativo se aplica ao grupo do Azure AD.

Siga estas etapas para criar uma [política de proteção de aplicativo](https://docs.microsoft.com/intune/app-protection-policies) que exige Microsoft Flow usuários de aplicativo móvel insiram um PIN antes de poderem acessar o aplicativo. 


## <a name="test-the-app-protection-policy"></a>Testar a política de proteção do aplicativo

Depois de criar a política de proteção de aplicativo e os usuários atribuídos ao grupo do Azure AD, é hora de usar o Microsoft Flow aplicativo móvel e confirmar se a política funciona.

Para confirmar se a política funciona, siga estas etapas:

1. Instale o aplicativo móvel Microsoft Flow em um dispositivo cuja plataforma corresponda a uma das plataformas que você definiu na política de proteção do aplicativo.
1. Entre no aplicativo móvel com uma conta que está no grupo do Azure AD que restringe o uso do aplicativo móvel a usuários que têm um PIN.

Em seguida, você será solicitado a:
1. Instale o Portal da Empresa.
1. Defina seu PIN se você ainda não tiver um PIN que atenda aos critérios da política de proteção de aplicativo.


## <a name="learn-more"></a>Saiba Mais

Aprenda a criar uma [política de proteção de aplicativo](https://docs.microsoft.com/intune/app-protection-policies).

