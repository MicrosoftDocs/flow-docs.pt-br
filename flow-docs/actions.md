---
title: Usar ações | Microsoft Docs
description: Com as ações, você pode executar operações, como Criar, Atualizar, Excluir, Atribuir ou Executar ação. Internamente, uma ação cria uma mensagem personalizada
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cf5c0e488f1d01c514f509b9d2a8afae265cf487
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64455930"
---
# <a name="use-actions"></a>Usar ações

As ações abrem uma gama de possibilidades para compor a lógica de negócios. Com as ações, você pode executar operações, como Criar, Atualizar, Excluir, Atribuir ou Executar ação. Internamente, uma ação cria uma mensagem personalizada. Os desenvolvedores fazem referência a essas ações como "mensagens". Cada uma dessas mensagens é baseada em ações executadas em um registro de entidade. Se a meta de um processo é criar um registro, então o atualize e faça a atribuição. Há três etapas separadas. Cada etapa é definida pelas funcionalidades da entidade – não necessariamente o processo empresarial.  
  
As ações fornecem a capacidade de definir um único verbo (ou mensagem) que corresponde a uma operação que você precisa executar para a sua empresa. Essas novas mensagens são orientadas por um processo ou comportamento em vez do que pode ser feito com uma entidade. Essas mensagens podem correspondem aos verbos como Escalar, Converter, Agendar, Encaminhar ou Aprovar – tudo o que você precisa. A adição desses verbos ajuda a fornecer um vocabulário mais avançado para definir fluentemente seus processos empresariais. Você pode aplicar esse vocabulário mais rico por meio de clientes ou integrações em vez de precisar gravar a ação nos clientes. Isso também é facilitado porque você pode gerenciar e registrar o êxito ou a falha da ação inteira como uma única unidade.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Mensagens configuráveis  
 Depois que uma ação é definida e ativada, um desenvolvedor pode usar essa mensagem, como qualquer uma das outras mensagens fornecidas pela plataforma. No entanto, uma diferença significativa é que agora alguém que não é um desenvolvedor pode aplicar as alterações para o que deve ser feito quando essa mensagem é usada. Você pode configurar a ação para modificar as etapas à medida que seus processos empresariais mudam. Qualquer código personalizado que usa essa mensagem não precisa ser alterado desde que os argumentos do processo não sejam.  
  
 Plug-ins e processos de fluxo de trabalho continuam a fornecer funcionalidades semelhantes para a definição de automação. Os processos de fluxo de trabalho ainda fornecem a funcionalidade para um não desenvolvedor aplicar as alterações. Mas a diferença está em como os processos empresariais são compostos e como um desenvolvedor pode escrever seu código. Uma ação é uma mensagem que opera no mesmo nível que qualquer uma das mensagens fornecidas pela plataforma. Os desenvolvedores podem registrar os plug-ins para as ações.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Mensagens globais 
 
 Ao contrário dos fluxos de trabalho ou dos [plug-ins](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in) do Common Data Service, uma ação não precisa estar associada a uma entidade específica. Você pode definir as ações "globais" que podem ser chamadas por si próprias.

## <a name="next-steps"></a>Próximas etapas

[Criar uma ação personalizada](create-actions.md)  
  

