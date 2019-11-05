---
title: Grupos de dados para Microsoft Flow | Microsoft Docs
description: Introdução aos grupos de dados para Microsoft PowerApps e Microsoft Flow.
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
ms.date: 10/26/2016
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 030e0563ce9adaa7c1c5c44f1446859e3152a398
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547436"
---
# <a name="learn-all-about-data-groups"></a>Saiba tudo sobre grupos de dados
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-is-a-data-group"></a>O que é um grupo de dados?
Os grupos de dados são uma maneira simples de categorizar serviços em uma [política de DLP (prevenção contra perda de dados)](prevent-data-loss.md). Os dois grupos de dados disponíveis são o grupo **somente dados de negócios** e o grupo **nenhum dado corporativo permitido** . As organizações são livres para determinar quais serviços são colocados em um determinado grupo de dados. Uma boa maneira de categorizar os serviços é colocá-los em grupos, com base no impacto para a organização. Por padrão, todos os serviços são colocados no grupo de dados **dados de negócios não permitidos** . Você gerencia os serviços em um grupo de dados quando cria ou modifica as propriedades de uma política DLP do centro de administração.

## <a name="how-data-is-shared-between-data-groups"></a>Como os dados são compartilhados entre grupos de dados
Os dados não podem ser compartilhados entre os serviços localizados em grupos diferentes. Por exemplo, se você coloca o SharePoint e o Salesforce no grupo **somente dados de negócios** e coloca o Facebook e o Twitter no grupo **nenhum dado corporativo permitido** , não é possível criar um fluxo que move dados entre o SharePoint e o Facebook. Embora os dados não possam ser compartilhados entre os serviços em grupos diferentes, você pode compartilhar dados entre os serviços dentro de um grupo específico. Então, voltando ao exemplo anterior, como o SharePoint e o Salesforce foram colocados no mesmo grupo de dados, os fluxos que os usuários finais criam podem compartilhar dados entre o SharePoint e o Salesforce. Da mesma forma, os usuários finais podem criar fluxos e PowerApps que compartilham dados entre o Facebook e o Twitter. O ponto principal é que os serviços em um grupo específico podem compartilhar dados, enquanto os serviços em grupos diferentes não podem compartilhar dados.  

Além disso, um grupo de dados deve ser designado como o grupo *padrão* . Inicialmente, o grupo **sem dados corporativos permitido** é o grupo *padrão* e todos os serviços estão no grupo de dados. Um administrador pode alterar o grupo de dados padrão para o grupo de dados **somente dados de negócios** . **Observação** todos os novos serviços adicionados ao fluxo serão colocados no grupo *padrão* designado. Por esse motivo, recomendamos que você mantenha os **dados de negócios permitidos** como o grupo padrão e adicione manualmente os serviços ao grupo **somente dados de negócios** depois que sua organização tiver avaliado o impacto de permitir que os dados corporativos sejam compartilhados com o novo serviço.

## <a name="add-services-to-a-data-group"></a>Adicionar serviços a um grupo de dados
Neste passo a passo, adicionaremos o SharePoint e o Salesforce ao grupo de dados **somente dados de negócios** de uma política de DLP (prevenção contra perda de dados). 

1. Selecione o link **+ Adicionar** localizado dentro da caixa de grupo **somente dados de negócios** de uma política DLP:    
   ![adicionar imagem](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Selecione SharePoint e Salesforce e, em seguida, selecione **Adicionar serviços** para adicionar ambos ao grupo somente dados de negócios:    
   ![adicionar imagem de serviços](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Selecione **salvar política** no menu na parte superior:  
   ![salvar](./media/introduction-to-data-groups/add-to-data-group-4.png) de política 
4. Observe que o SharePoint e o Salesforce agora estão no grupo somente dados de negócios:  
   ![grupo de dados corporativos atualizado](./media/introduction-to-data-groups/add-to-data-group-3.png)   

Neste passo a passo, você adicionou o SharePoint e o Salesforce ao grupo de dados **somente dados de negócios** de uma política de DLP. Se uma pessoa que faz parte do ambiente da política DLP criar um aplicativo que compartilha dados entre o SharePoint ou o Salesforce e qualquer serviço no grupo de dados **dados de negócios não permitidos** , o aplicativo não terá permissão para ser executado.

## <a name="remove-services-from-a-data-group"></a>Remover serviços de um grupo de dados
Como todos os serviços devem estar em um dos grupos de dados disponíveis, para remover um serviço de um grupo específico, basta adicionar o serviço a outro grupo e salvar a política.  

## <a name="change-the-default-data-group"></a>Alterar o grupo de dados padrão
Neste passo a passo, alteraremos o grupo de dados padrão do grupo de dados **dados de negócios não permitidos** para o grupo de dados **somente dados de negócios** .  

**Importante** todos os novos serviços adicionados ao Flow serão colocados no grupo *padrão* designado. Por esse motivo, recomendamos que você mantenha os **dados de negócios permitidos** como o grupo padrão e adicione manualmente os serviços ao grupo **somente dados de negócios** .

1. Selecione o **...** localizado no canto superior direito do grupo de dados que você deseja designar como o grupo de dados padrão:    
   ![alterar o grupo padrão](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Selecione **definir como grupo padrão**:  
   ![alterar o grupo padrão](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Selecione **salvar política** no menu na parte superior:  
   ![alterar o grupo padrão](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Observe que o grupo de dados agora é designado como o grupo de dados padrão:  
   ![alterar grupo padrão](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Próximas etapas
* [Saiba mais sobre as políticas de prevenção contra perda de dados (DLP)](prevent-data-loss.md)
* [Saiba mais sobre ambientes](environments-overview-admin.md)   

