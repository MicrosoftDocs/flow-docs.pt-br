---
title: Microsoft Flow para desenvolvedores corporativos, ISVs e parceiros | Microsoft Docs
description: Uma introdução ao desenvolvimento de soluções para Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: f26143533e84bc3ea8bc0784fef3c56eeb0551e1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547826"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Microsoft Flow para desenvolvedores corporativos, ISVs e parceiros
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Como desenvolvedor, você pode estender Microsoft Flow, permitindo soluções ainda mais poderosas para organizações e clientes.

## <a name="microsoft-flow-for-enterprise-developers"></a>Microsoft Flow para desenvolvedores corporativos

Como um desenvolvedor empresarial, Capacite sua organização para criar soluções avançadas adaptadas em Microsoft Flow:

- **Criar conectores personalizados**: desenvolva conectores personalizados para se conectar aos dados e serviços Web da sua organização por meio de Microsoft Flow. [Saiba Mais](https://docs.microsoft.com/connectors/custom-connectors/)

- **Build Azure Functions: crie**Azure Functions para estender aplicativos com lógica do lado do servidor Personalizada. [Saiba Mais](/azure/azure-functions/app-service-export-api-to-powerapps-and-flow)

- **Microsoft Flow de inserção**: Insira Microsoft Flow diretamente em suas experiências de site para criar soluções integradas, fluxos de trabalho identificando ou processos em que as pessoas em sua organização já fazem o seu funcionamento. [Saiba Mais](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>Microsoft Flow para ISVs e parceiros da Microsoft

Como parceiro da Microsoft ou ISV (fornecedor independente de software), acelere a adoção do cliente, ampliando seus produtos para se integrarem aos dados e processos de negócios dos seus clientes, além de adicionar e personalizar fluxos de trabalho para automatizar processos de negócios como parte do seu aplicativo. Depois de concluir as sete etapas abaixo, seu aplicativo terá a capacidade de aproveitar um mecanismo de fluxo de trabalho robusto em escala de nuvem que pode se conectar a mais de 200 serviços diferentes.

| Etapas | Etapa | Quando necessário? |
| --- | --- | --- |
| Desenvolver | 1. criar um conector personalizado para seus dados | Se você quiser expor seus próprios dados de ISV para o PowerApps ou Microsoft Flow |
| Desenvolver | 2. adicionar suporte para seu aplicativo para autenticar usuários com Azure Active Directory (Azure AD) | Se você quiser inserir a interface do usuário do Microsoft Flow ou a lista no Microsoft AppSource | 
| Desenvolver | 3. Insira a interface do usuário do Microsoft Flow em seu aplicativo usando o iframe baseado na Web | Se você quiser incluir a criação ou o gerenciamento de fluxo em seu aplicativo | 
| Desenvolver | 4. criar e publicar modelos de fluxo | Se você quiser criar previamente fluxos para seus clientes | 
| Desenvolver | 5. adicionar lógica do aplicativo para implantar fluxos programaticamente | Se você quiser implantar automaticamente seus fluxos pré-criados para seus clientes | 
| Distribuição | 6. conceder a seus clientes licenças para Microsoft Flow por meio do programa Microsoft Cloud provedor de soluções | Se seus clientes não tiverem licenças do Office 365 ou Dynamics 365 |
| Distribuição | 7. liste sua solução em Microsoft AppSource | Recomendado para aumentar a visibilidade da sua solução de ISV |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. conectando-se às suas APIs ou permitindo que os clientes se conectem às suas APIs

Como um ISV, geralmente você tem dados proprietários que deseja que os clientes acessem por meio de seus fluxos. Você pode expor o acesso a qualquer um dos seus dados por meio de um conector personalizado. [Saiba Mais](https://docs.microsoft.com/connectors/custom-connectors/)

Depois de criadas, há duas maneiras de disponibilizar o conector para seus clientes:
- O conector pode ser implantado no locatário do cliente por meio de APIs REST ou do PowerShell.
- Para disponibilizar publicamente o conector personalizado para todos os usuários, você pode enviar seu conector para certificação. [Saiba Mais](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. autenticação 

Para chamar as APIs REST e inserir a interface do usuário autenticada, seu aplicativo precisa usar o logon único federado do Azure AD para autenticar usuários finais e clientes. [Acesse aqui](https://identity.microsoft.com/) para obter informações sobre como habilitar o SSO Federado do AAD. Não há suporte para acesso não autenticado ou acesso com provedores de identidade diferentes do Azure AD. 

### <a name="3-embedding-ui-components"></a>3. incorporando componentes de interface do usuário

Insira Microsoft Flow em seu aplicativo para habilitar a integração profunda na contexto entre o aplicativo e todos os outros serviços aos quais Microsoft Flow dá suporte. [Saiba Mais](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. criar e publicar modelos de fluxo

Depois de ter um conector, você deve publicar modelos que demonstram como usar seu serviço. Esses modelos servirão como exemplos que os usuários podem usar para aprender e, em seguida, estender para seus próprios fluxos de trabalho exclusivos. [Saiba Mais](../publish-a-template.md)

### <a name="5-deployment"></a>5. implantação

Para conceder aos usuários finais acesso a fluxos que eles podem usar automaticamente, implante os fluxos no locatário do Azure AD do usuário. Use um pacote de implantação que você implanta usando nossas APIs REST ou o PowerShell. [Saiba Mais](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. licenciamento

Se os clientes já tiverem o Office 365 ou o Dynamics 365 e essas licenças estiverem associadas às identidades que os usuários fazem logon com o Azure AD, não haverá requisitos de licenciamento adicionais para você. No entanto, se os clientes não usam o Office 365 ou o Dynamics 365, você deve adquirir direitos de uso em seu nome para Microsoft Flow, para que eles sejam licenciados para aproveitar esses componentes inseridos em seu aplicativo.

Oferecemos o programa de [provedor de soluções Microsoft Cloud](https://partner.microsoft.com/cloud-solution-provider) para adquirir licenças em nome de seus clientes. Há dois planos de [preços](https://flow.microsoft.com/pricing/) diferentes disponíveis para Microsoft Flow, que devem ser verificados quanto aos detalhes do plano e do recurso.

### <a name="7-list-on-appsource"></a>7. List em AppSource

Depois de integrar Microsoft Flow ao seu aplicativo, você pode listá-lo em AppSource. Com o AppSource, você pode gerar novos clientes potenciais para sua empresa criando um aplicativo e publicando-o no AppSource para que novos clientes testem o drive. [Saiba Mais](dev-appsource-test-drive.md)
