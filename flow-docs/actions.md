---
title: Usar ações | MicrosoftDocs
description: Com as ações, você pode executar operações, como criar, atualizar, excluir, atribuir ou executar ação. Internamente, uma ação cria uma mensagem personalizada
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: eb4fa4040611241dd2bd81706736738ad6774d38
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544598"
---
# <a name="use-actions"></a>Ações de uso
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

As ações abrem uma variedade de possibilidades para compor a lógica de negócios. Com as ações, você pode executar operações, como criar, atualizar, excluir, atribuir ou executar ação. Internamente, uma ação cria uma mensagem personalizada. Os desenvolvedores se referem a essas ações como "mensagens". Cada uma dessas mensagens é baseada em ações executadas em um registro de entidade. Se a meta de um processo for criar um registro, atualizá-lo e, em seguida, atribuí-lo, haverá três etapas separadas. Cada etapa é definida pelos recursos da entidade – não necessariamente seu processo comercial.  
  
As ações fornecem a capacidade de definir um único verbo (ou mensagem) que corresponda a uma operação que você precisa executar para sua empresa. Essas novas mensagens são orientadas por um processo ou comportamento em vez do que pode ser feito com uma entidade. Essas mensagens podem corresponder a verbos como escalonar, converter, agendar, rotear ou aprovar – o que for necessário. A adição desses verbos ajuda a fornecer um vocabulário mais rico para você definir de forma fluente seus processos de negócios. Você pode aplicar esse vocabulário mais rico de clientes ou integrações em vez de ter que escrever a ação dentro dos clientes. Isso também facilita a tarefa, pois você pode gerenciar e registrar o êxito ou a falha de toda a ação como uma única unidade.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Mensagens configuráveis  
 Depois que uma ação é definida e ativada, um desenvolvedor pode usar essa mensagem como qualquer uma das outras mensagens fornecidas pela plataforma. No entanto, uma diferença significativa é que agora alguém que não é um desenvolvedor pode aplicar alterações no que deve ser feito quando essa mensagem é usada. Você pode configurar a ação para modificar as etapas conforme os processos de negócios mudam. Qualquer código personalizado que usa essa mensagem não precisa ser alterado, desde que os argumentos do processo não sejam alterados.  
  
 Os processos de fluxo de trabalho e os plug-ins continuam a fornecer recursos semelhantes para definir a automação. Os processos de fluxo de trabalho ainda fornecem a capacidade de um não desenvolvedor aplicar alterações. Mas a diferença está em como os processos de negócios são compostos e como um desenvolvedor pode escrever seu código. Uma ação é uma mensagem que opera no mesmo nível que qualquer uma das mensagens fornecidas pela plataforma. Os desenvolvedores podem registrar plug-ins para ações.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Mensagens globais 
 
 Ao contrário dos fluxos de trabalho ou [plug-ins](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in)de Common Data Service, uma ação não precisa ser associada a uma entidade específica. Você pode definir ações "globais" que podem ser chamadas por conta própria.

## <a name="next-steps"></a>Próximas etapas

[Criar uma ação personalizada](create-actions.md)  
  

