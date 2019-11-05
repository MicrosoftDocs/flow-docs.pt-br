---
title: Usar entradas e saídas em fluxos de interface do usuário da Web | Microsoft Docs
description: Use entradas e saídas em fluxos de interface do usuário da Web.
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
ms.openlocfilehash: f8506846f8081819ad42c70e820397bdc43536e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549336"
---
# <a name="use-inputs-and-outputs-in-web-ui-flows"></a>Usar entradas e saídas em fluxos de interface do usuário da Web

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs-for-a-web-ui-flow"></a>Definir entradas para um fluxo de interface do usuário da Web

As entradas de um fluxo de interface do usuário permitem passar informações de uma fonte externa, como um banco de dados ou outro fluxo de interface do usuário para o software herdado de destino que você automatizará.

Qualquer variável usada (leitura) antes da inicialização (geralmente feita por meio de comandos de **armazenamento** ) será tratada automaticamente como uma variável de entrada e será exibida no cartão **executar um fluxo de interface do usuário para a Web** .

Você pode usar variáveis por meio de interpolação de cadeia de caracteres, por exemplo, alterar o campo de destino do comando de clique para "ID =\${ElementID}". Ou altere o campo de valor do comando de tipo para "\${inputText}".

O comando, **definir o tamanho da janela** e o **tipo** de comando nas capturas de tela a seguir usam variáveis não inicializadas \${Width}, \${Height} e \${Search}. Essas variáveis se tornarão valores de entrada.

![Definir o tamanho e o tipo da janela](../media/inputs-outputs-web/f05cb445dad212aaf395b66ba969622c.png "Definir o tamanho e o tipo da janela")

Você pode usar variáveis diretamente em alguns comandos, por exemplo, os campos de destino/valor de um comando forEach são variáveis, não é necessário colocá-las com "\${}".

Consulte a referência de [comandos do Selenium](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/) para determinar quais comandos têm o nome da variável diretamente.

## <a name="define-outputs-for-a-web-ui-flow"></a>Definir saídas para um fluxo de interface do usuário da Web

Qualquer variável definida no script Selenium torna-se automaticamente um valor de saída. Use os seguintes comandos para declarar variáveis:

[Armazenadas](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store)

[Atributo de repositório](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-attribute)

[Armazenar JSON](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-json)

[Título da loja](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-title)

[valor de armazenamento](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-value)

[Identificador de janela de armazenamento](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-window-handle)

[Contagem de XPath de repositório](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#store-xpath-count)

[Executar script](https://www.seleniumhq.org/selenium-ide/docs/en/api/commands/#execute-script)(adicionar sintaxe "Return" para retornar o objeto que você deseja armazenar no final do script)

## <a name="next-steps"></a>Próximas etapas

- Saiba como [criar fluxos de interface do usuário da Web](create-web.md).
- Saiba como [disparar fluxos de interface do usuário](run-ui-flow.md).

