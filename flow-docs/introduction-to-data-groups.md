---
title: Grupos de dados para Microsoft Flow | Microsoft Docs
description: Introdução aos Grupos de dados para o Microsoft PowerApps e Microsoft Flow.
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
ms.openlocfilehash: ba064461c34ce73faa712964791643ef67fca089
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461526"
---
# <a name="learn-all-about-data-groups"></a>Saiba tudo sobre os grupos de dados
## <a name="what-is-a-data-group"></a>O que é um grupo de dados?
Os grupos de dados são uma maneira simples de categorizar os serviços em uma [política de prevenção de perda de dados (DLP)](prevent-data-loss.md). Os dois grupos de dados disponíveis são os grupos **Somente dados de negócios** e **Dados de negócios não permitidos**. As organizações são livres para determinar quais serviços são colocados em um grupo de dados específico. Uma boa forma de categorizar os serviços é colocá-los em grupos, com base no impacto na organização. Por padrão, todos os serviços são colocados no grupo de dados **Dados de negócios não permitidos**. Você gerencia os serviços em um grupo de dados ao criar ou modificar as propriedades de uma política DLP no centro de administração.

## <a name="how-data-is-shared-between-data-groups"></a>Como os dados são compartilhados entre os grupos de dados
Os dados não podem ser compartilhados entre os serviços localizados em grupos diferentes. Por exemplo, se você colocar o SharePoint e o Salesforce no grupo **Somente dados de negócios** e colocar o Facebook e o Twitter no grupo **Dados de negócios não permitidos**, não poderá criar um fluxo que move os dados entre o SharePoint e o Facebook. Enquanto os dados não possam ser compartilhados entre os serviços em grupos diferentes, você pode compartilhar os dados entre os serviços dentro de um grupo específico. Então, voltando ao exemplo anterior, como o SharePoint e o Salesforce foram colocados no mesmo grupo de dados, os fluxos que seus usuários finais criam podem compartilhar dados entre o SharePoint e o Salesforce. Da mesma forma, os usuários finais podem criar fluxos e PowerApps que compartilham dados entre o Facebook e o Twitter. O ponto principal é que os serviços em um grupo específico podem compartilhar dados, enquanto os serviços em grupos diferentes não podem.  

Além disso, um grupo de dados deve ser designado como o grupo *padrão*. Inicialmente, o grupo **Dados de negócios não permitidos** é o grupo *padrão* e todos os serviços estão no grupo de dados. Um administrador pode alterar o grupo de dados padrão para o grupo de dados **somente dados de negócios**. **Observação** quaisquer novos serviços adicionados ao fluxo serão colocados no grupo *padrão* designado. Por esse motivo, recomendamos que você mantenha o grupo **Dados de negócios não permitidos** como o grupo padrão e adicione manualmente os serviços ao grupo **Somente dados de negócios** depois que sua organização tiver avaliado o impacto de permitir que os dados de negócios sejam compartilhados com o novo serviço.

## <a name="add-services-to-a-data-group"></a>Adicionar serviços a um grupo de dados
Neste passo a passo, iremos adicionar o SharePoint e o Salesforce ao grupo de dados **somente dados de negócios** de uma política de prevenção de perda de dados (DLP). 

1. Selecione o link **+ Adicionar** localizado na caixa do grupo **Somente dados de negócios** de uma política DLP:    
   ![Adicionar imagem](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Selecione o SharePoint e o Salesforce, então, **Adicionar serviços** para adicionar ambos ao grupo Somente dados de negócios:    
   ![Adicionar imagem dos serviços](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Selecione **Salvar Política** no menu na parte superior:  
   ![Salvar política](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Observe que o SharePoint e o Salesforce estão agora no grupo Somente dados de negócios:  
   ![grupo dos dados de negócios atualizado](./media/introduction-to-data-groups/add-to-data-group-3.png)   

Neste passo a passo, adicionamos o SharePoint e o Salesforce ao grupo de dados **somente dados de negócios** de uma política DLP. Se uma pessoa que faz parte do ambiente da política DLP criar um aplicativo que compartilha dados entre o SharePoint ou o Salesforce e qualquer serviço no grupo de dados **Dados de negócios não permitidos**, o aplicativo não poderá ser executado.

## <a name="remove-services-from-a-data-group"></a>Remover os serviços de um grupo de dados
Como todos os serviços devem estar em um dos grupos de dados disponíveis, para remover um serviço de um grupo específico, basta adicionar o serviço a outro grupo e salvar a política.  

## <a name="change-the-default-data-group"></a>Alterar o grupo de dados padrão
Neste passo a passo, iremos alterar o grupo de dados padrão do grupo de dados **dados de negócios não permitidos** para o grupo de dados **somente dados de negócios**.  

**Importante** quaisquer novos serviços adicionados ao fluxo serão colocados no grupo *padrão* designado. Por esse motivo, recomendamos que você mantenha o grupo **Dados de negócios não permitidos** como o grupo padrão e adicione manualmente os serviços ao grupo **Somente dados de negócios**.

1. Selecione os **...** localizados no canto superior direito do grupo de dados que você deseja designar como o grupo de dados padrão:    
   ![alterar o grupo padrão](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Selecione **Definir como grupo padrão**:  
   ![alterar o grupo padrão](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Selecione **Salvar Política** no menu na parte superior:  
   ![alterar o grupo padrão](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Observe que o grupo de dados agora é designado como o grupo de dados padrão:  
   ![alterar o grupo padrão](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Próximas etapas
* [Saiba mais sobre as políticas de prevenção de perda de dados (DLP)](prevent-data-loss.md)
* [Saiba mais sobre os ambientes](environments-overview-admin.md)   

