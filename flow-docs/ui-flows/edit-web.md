---
title: Saiba como editar fluxos de interface do usuário da Web | Microsoft Docs
description: Saiba como editar fluxos de interface do usuário da Web.
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 263f8634b2435217fba436e68ab7e744dd3b52b3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549566"
---
# <a name="edit-web-ui-flows"></a>Editar fluxos de interface do usuário da Web

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Fluxos de interface do usuário da Web automatizam sites em execução na [próxima versão do Microsoft Edge](https://www.microsoftedgeinsider.com/) ou Google Chrome. Depois de [criar um fluxo de interface do usuário da Web](create-web.md), talvez seja necessário editá-lo. Siga as etapas neste documento para aprender a editar seus fluxos de interface do usuário da Web.

## <a name="edit-in-selenium-ide"></a>Editar no IDE do Selenium

Use o IDE Selenium para editar os fluxos de interface do usuário da Web.

>[!NOTE]
>A edição no Selenium IDE destina-se a usuários avançados e desenvolvedores.

Você pode consultar os [comandos Selenium](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) para saber como editar o script.

O IDE Selenium sugere seletores diferentes e um padrão ao direcionar um elemento de interface do usuário. Você também pode definir um novo seletor se nenhum dos seletores propostos forem apropriados. Isso geralmente acontece quando a estrutura HTML do site é altamente dinâmica.

Aqui está um exemplo de seletores possíveis que o Selenium IDE identificou:

![Seletores possíveis](../media/edit-web/possible-selectors.png "Seletores possíveis")

## <a name="accessing-a-property-of-an-object-variable-or-item-of-an-array-variable"></a>Acessando uma propriedade de uma variável de objeto ou item de uma variável de matriz * *

Esse recurso avançado permite que você use sintaxe como \${foo. bar} para acessar a propriedade bar do objeto Foo. Você também pode gravar na propriedade bar de Foo usando foo. bar como a propriedade Value em um comando Store. Você também pode usar sintaxe como \${foo [0]} para acessar o item no índice 0 na matriz foo.

## <a name="next-steps"></a>Próximas etapas

- [Criar fluxos de interface do usuário da Web](create-web.md)
- [Executar fluxos da interface do usuário](run-ui-flow.md)
