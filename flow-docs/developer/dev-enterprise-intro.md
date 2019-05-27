---
title: Microsoft Flow para desenvolvedores corporativos, ISVs e parceiros | Microsoft Docs
description: Uma introdução ao desenvolvimento de soluções para o Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: mblythe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: f510d387b594bb11306f8bc2530573b775e5f08e
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64455872"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Microsoft Flow para desenvolvedores corporativos, ISVs e parceiros

Como desenvolvedor, você pode estender o Microsoft Flow, permitindo soluções ainda mais poderosas para organizações e clientes.

## <a name="microsoft-flow-for-enterprise-developers"></a>Microsoft Flow para desenvolvedores corporativos

Como um desenvolvedor corporativo, capacite sua organização para criar soluções robustas personalizadas no Microsoft Flow:

- **Criar conectores personalizados**: Desenvolva conectores personalizados para se conectar a dados da sua organização e serviços Web por meio do Microsoft Flow. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/)

- **Criar Azure Functions**: Colocar Azure Functions para estender aplicativos com lógica personalizada do lado do servidor. [Saiba mais](https://docs.microsoft.com/azure/azure-functions/functions-flow-scenario)

- **Incorporar Microsoft Flow**: Incorpore o Microsoft Flow diretamente às suas experiências de site para criar soluções integradas, identificando os fluxos de trabalho ou processos em que as pessoas na sua organização já realizam seu trabalho. [Saiba mais](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>Microsoft Flow para ISVs e parceiros Microsoft

Como um parceiro da Microsoft ou um ISV (Fornecedor Independente de Software), acelere a adoção do cliente ao ampliar o alcance de seus produtos para integrá-los aos dados e aos processos comerciais dos seus clientes, bem como ao adicionar e personalizar os fluxos de trabalho para automatizar os processos comerciais como parte do seu aplicativo. Depois de concluir as sete etapas abaixo, seu aplicativo terá a capacidade de aproveitar um mecanismo de fluxo de trabalho em escala de nuvem e robusto, que pode se conectar a mais de 200 serviços diferentes.

| Fase | Etapa | Quando é necessária? |
| --- | --- | --- |
| Desenvolvimento | 1. Criar um conector personalizado para os seus dados | Se você quiser expor seus próprios dados de ISV para o PowerApps ou para o Microsoft Flow |
| Desenvolvimento | 2. Adicionar suporte ao seu aplicativo para autenticar usuários com o Azure AD (Azure Active Directory) | Se você quiser inserir a interface do usuário do Microsoft Flow ou a lista no Microsoft AppSource | 
| Desenvolvimento | 3. Inserir a interface do usuário do Microsoft Flow em seu aplicativo usando nosso iframe baseado na Web | Se você quiser incluir a criação ou o gerenciamento de fluxo em seu aplicativo | 
| Desenvolvimento | 4. Criar e publicar modelos de fluxo | Se você quiser pré-criar fluxos para seus clientes | 
| Desenvolvimento | 5. Adicionar lógica de aplicativo para implantar fluxos de modo programático | Se você quiser implantar automaticamente os fluxos pré-criados para seus clientes | 
| Distribuição | 6. Conceder licenças do Microsoft Flow para seus clientes por meio do programa Provedor de Soluções de Nuvem da Microsoft | Se seus clientes não tiverem licenças do Office 365 ou do Dynamics 365 |
| Distribuição | 7. Listar suas soluções no Microsoft AppSource | Recomendado para aumentar a visibilidade da sua solução de ISV |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. Conectar-se às suas APIs OU permitir que os clientes se conectem às suas APIs

Como um ISV, você geralmente têm dados proprietários que deseja que os clientes acessem por meio de seus fluxos. Você pode expor o acesso a qualquer um dos seus dados através de um conector personalizado. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/)

Depois de criado, há duas maneiras de disponibilizar o conector para seus clientes:
- O conector pode ser implantado no locatário do cliente por meio da APIs REST ou do PowerShell.
- Para tornar o conector personalizado disponível publicamente para todos os usuários, você poderá enviar seu conector de certificação. [Saiba mais](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. Autenticação 

Para chamar as APIs REST e inserir a interface do usuário autenticada, seu aplicativo deve usar o logon único federado do Azure AD para autenticar os usuários finais e os clientes. [Clique aqui](https://identity.microsoft.com/) para obter informações sobre como habilitar o SSO federado para o AAD. Não oferecemos suporte para acesso não autenticado ou para acesso com provedores de identidade diferentes do Azure AD. 

### <a name="3-embedding-ui-components"></a>3. Incorporar componentes de interface do usuário

Insira o Microsoft Flow de dentro do seu aplicativo para habilitar a integração profunda, em contexto, entre o aplicativo e todos os outros serviços aos quais o Microsoft Flow dá suporte. [Saiba mais](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. Criar e publicar modelos de fluxo

Quando você tiver um conector, deve publicar modelos que demonstram como usar o serviço. Esses modelos servirão como exemplos que os usuários podem usar para aprender e, em seguida, estender a seus próprios fluxos de trabalho exclusivos. [Saiba mais](../publish-a-template.md)

### <a name="5-deployment"></a>5. Implantação

Para conceder aos usuários finais acesso aos fluxos que eles podem usar automaticamente, implante os fluxos no locatário do Azure AD do usuário. Utilize um pacote de implantação que você implanta usando nossas APIs REST ou o PowerShell. [Saiba mais](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. Licenciamento

Se os clientes já tiverem o Office 365 ou o Dynamics 365 e essas licenças estiverem associadas às identidades que os usuários utilizam para fazer logon com o Azure AD, não haverá nenhum requisito de licenciamento adicional para você. No entanto, se os clientes não usarem o Office 365 ou o Dynamics 365, você deverá adquirir direitos de uso em nome deles para o Microsoft Flow, de modo que eles sejam licenciados para aproveitarem esses componentes inseridos em seu aplicativo.

Oferecemos o programa [Provedor de Soluções de Nuvem da Microsoft](https://partner.microsoft.com/cloud-solution-provider) para adquirir licenças em nome de seus clientes. Há duas [propostas de preços](https://flow.microsoft.com/pricing/) diferentes disponíveis para o Microsoft Flow, que você pode verificar para obter os detalhes sobre os planos e os recursos.

### <a name="7-list-on-appsource"></a>7. Listar no AppSource

Depois que tiver integrado o Microsoft Flow em seu aplicativo, você poderá listá-lo no AppSource. Com o AppSource, você pode gerar novos clientes potenciais para a sua empresa ao criar um aplicativo e publicá-lo no AppSource para os novos clientes testarem. [Saiba mais](dev-appsource-test-drive.md)
