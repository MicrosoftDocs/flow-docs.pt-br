---
title: Criar um fluxo automatizado com Common Data Service | Microsoft Docs
description: Criar fluxos de trabalho usando uma conexão Common Data Service e Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 110f3947cf7ece97bfd9b83ca6a12ee46d04b4d6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547129"
---
# <a name="create-an-automated-flow-by-using-common-data-service"></a>Criar um fluxo automatizado usando Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Com o conector de Common Data Service, você pode criar fluxos que são iniciados por criar e atualizar eventos em seu banco de dados Common Data Service. Além disso, você pode executar ações de criar, atualizar, recuperar e excluir em registros dentro do banco de dados Common Data Service.

## <a name="initiate-a-flow-from-common-data-service"></a>Iniciar um fluxo de Common Data Service

Você pode usar qualquer um dos seguintes gatilhos para iniciar o fluxo:

- Quando um registro é selecionado
- Quando um registro é criado
- Quando um registro é excluído
- Quando um registro é atualizado


> [!div class="mx-imgBorder"]
> ![selecionar um gatilho](./media/cds-connector/Triggers.png)

Se o gatilho selecionado exigir que um ambiente seja selecionado, você poderá escolher `(Current)`, que sempre usará o banco de dados dentro do ambiente no qual Microsoft Flow é executado. Se você quiser que o fluxo sempre seja disparado com base em um evento em um ambiente específico, selecione esse ambiente.

> [!div class="mx-imgBorder"]
> ![escolher ambiente](./media/cds-connector/Environments.png)

Você pode usar escopos para determinar se o fluxo será executado se você criar um novo registro, se um novo registro for criado por um usuário em sua unidade de negócios ou se um novo registro for criado por qualquer usuário em sua organização.

> [!div class="mx-imgBorder"]
> ![escolher o escopo](./media/cds-connector/Scopes.png)

|Com|Tempo de gatilho|
| --- | --- |
|Unidade de negócios|A ação é executada em um registro de propriedade de sua unidade de negócios|
|Organizações|A ação é tomada por qualquer pessoa dentro da organização ou do banco de dados|
|Pai: unidade de negócios filho|A ação é executada em um registro de propriedade de sua unidade de negócios ou de uma unidade de negócios filho|
|Usuário|A ação é executada em um registro de sua propriedade|

Os gatilhos que são executados quando um registro é atualizado também podem usar atributos de filtragem. Isso garante que o fluxo seja executado somente quando qualquer um dos atributos definidos for atualizado.

> [!IMPORTANT]
> Use atributos de filtro para impedir que o fluxo seja executado desnecessariamente.

Esse fluxo é disparado sempre que o nome ou sobrenome do contato que o usuário do fluxo possui é atualizado.

> [!div class="mx-imgBorder"]
> ![atributos de filtro](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Privilégios de gatilho

Para criar um fluxo que dispara com base em criar, atualizar ou excluir em um registro, o usuário precisa ter permissões de nível de usuário para criar, ler, gravar e excluir na entidade de registro de retorno de chamada. Além disso, dependendo dos escopos definidos, o usuário pode precisar de pelo menos esse nível de leitura na mesma entidade.  [Saiba mais](https://docs.microsoft.com/power-platform/admin/database-security) sobre a segurança do ambiente.

## <a name="write-data-into-common-data-service"></a>Gravar dados em Common Data Service

Use qualquer uma das seguintes ações para gravar dados em Common Data Service:

- Criar um novo registro
- Atualizar um registro

Aqui está um exemplo de criação de uma tarefa de acompanhamento quando o usuário determinado cria um novo registro de conta.  

> [!div class="mx-imgBorder"]
> ![tarefa de acompanhamento](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Conceitos avançados

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Gravar dados em campos de cliente, proprietário e relação

Para gravar dados em campos de cliente, proprietário e relação, dois campos devem ser preenchidos.

| Categoria de campo | configurações de exemplo |
| --- | --- |
| Cerne | Em relação a = ID do registro (por exemplo, ID da conta) e com relação ao tipo, conforme selecionado na lista. |
| Cliente | Representa a ID do registro e o tipo de cliente, conforme selecionado na lista. |
| Proprietário | Representa a ID do usuário do sistema ou da equipe e o tipo de proprietário conforme selecionado na lista. |

### <a name="enable-upsert-behavior"></a>Habilitar comportamento de Upsert

Você pode aproveitar o comando **atualizar um registro** para fornecer ações Upsert, que atualiza o registro, caso ele já exista, ou cria um novo registro. Para invocar Upsert, forneça a entidade e uma chave de GUID. Se o registro com o tipo e a chave especificados existir, ocorrerá uma atualização. Caso contrário, um registro com a chave especificada será criado.

### <a name="trigger-behavior"></a>Comportamento do gatilho

Se você tiver um gatilho registrado na atualização de um registro, o fluxo será executado para cada atualização *confirmada* para o registro fornecido. O serviço invoca o fluxo de forma assíncrona e com a carga que captura no momento em que a invocação ocorre.

> [!NOTE]
> Se você tiver duas atualizações que acontecem dentro de segundos uma da outra, o fluxo poderá ser disparado mais de uma vez com o conteúdo com controle de versão mais recente.

As execuções de fluxo podem ser atrasadas se houver uma pendência de trabalhos do sistema em seu ambiente.  Se esse atraso ocorrer, o fluxo será disparado quando o trabalho do sistema para invocar as execuções de fluxo.
