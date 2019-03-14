---
title: Criar um fluxo automatizado com o Common Data Service para Aplicativos | Microsoft Docs
description: Criar fluxos de trabalho usando uma conexão do Common Data Service para Aplicativos e o Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: brandonsimons
manager: ryjones
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/06/2019
ms.author: brandonsimons
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f9a417f99b6ea4105a451b65f7ccabbf36922d78
ms.sourcegitcommit: 61f0eb1fdc54da02eb57dadf09899fa6f308b00d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57524487"
---
# <a name="create-an-automated-flow-by-using-common-data-service-for-apps"></a>Criar um fluxo automatizado usando o Common Data Service para Aplicativos

Com o conector do Common Data Service para Aplicativos, você pode criar fluxos que são iniciados por criar e atualizar eventos dentro de seu banco de dados do Common Data Service. Além disso, você pode executar criar, atualizar, recuperar e excluir ações em registros de dentro do banco de dados do Common Data Service para Aplicativos.

## <a name="initiate-a-flow-from-common-data-service-for-apps"></a>Iniciar um fluxo do Common Data Service para Aplicativos

Você pode usar qualquer um dos seguintes gatilhos para iniciar seu fluxo:

- Quando um registro é selecionado
- Quando um registro é criado
- Quando um registro é excluído
- Quando um registro é atualizado


> [!div class="mx-imgBorder"]
> ![Selecionar um gatilho](./media/cds-connector/Triggers.png)

Se o gatilho selecionado requer que um ambiente seja selecionado, você pode escolher `(Current)`, que sempre usa o banco de dados dentro do ambiente no qual o Microsoft Flow é executado. Se você quiser sempre disparar seu fluxo com base em um evento em um ambiente específico, selecione esse ambiente.

> [!div class="mx-imgBorder"]
> ![Escolher o ambiente](./media/cds-connector/Environments.png)

Você pode usar escopos para determinar se seu fluxo será executado se você criar um registro, se um registro for criado por um usuário dentro de sua unidade de negócios ou se um registro for criado por qualquer usuário em sua organização.

> [!div class="mx-imgBorder"]
> ![Escolher escopo](./media/cds-connector/Scopes.png)

|Escopo|Temporização do gatilho|
| --- | --- |
|Unidade de negócios|A ação é tomada em um registro pertencente à sua unidade de negócios|
|Organização|A ação é realizada por qualquer pessoa dentro da organização ou banco de dados|
|Divisões Primária e Secundárias|A ação é tomada em um registro pertencente à sua unidade de negócios ou a uma divisão secundária|
|Usuário|A ação é tomada em um registro pertencente a você|

Os gatilhos que são executados quando um registro é atualizado também podem usar atributos de filtragem. Isso garante que o fluxo seja executado somente quando todos os atributos definidos são atualizados.

> [!IMPORTANT]
> Use atributos de filtro para impedir que o seu fluxo execute desnecessariamente.

Esse fluxo dispara sempre que o nome ou sobrenome do contato pertencente ao usuário do fluxo é atualizado.

> [!div class="mx-imgBorder"]
> ![Atributos de filtro](./media/cds-connector/FilterAttributes.png)

## <a name="trigger-privileges"></a>Privilégios de gatilho

Para criar um fluxo que gatilhos com base em criar, atualizar ou excluir em um registro, o usuário precisa ter permissões de nível de usuário para criação, leitura, gravação e exclusão na entidade de Registro de Retorno de Chamada. Além disso, dependendo dos escopos definidos, o usuário talvez precise pelo menos desse nível de leitura na mesma entidade.  [Saiba mais](https://docs.microsoft.com/power-platform/admin/database-security) sobre a segurança do ambiente.

## <a name="write-data-into-common-data-service-for-apps"></a>Gravar dados no Common Data Service para Aplicativos

Use qualquer uma das seguintes ações para gravar dados no Common Data Service para Aplicativos:

- Criar um registro
- Atualizar um registro

Aqui está um exemplo de criação de uma tarefa de acompanhamento quando determinado usuário cria um registro de conta.  

> [!div class="mx-imgBorder"]
> ![Tarefa de acompanhamento](./media/cds-connector/Regarding.png)

## <a name="advanced-concepts"></a>Conceitos avançados

### <a name="write-data-into-customer-owner-and-regarding-fields"></a>Gravar dados no cliente, no proprietário e nos campos relacionados

Para gravar dados no cliente, no proprietário e nos campos relacionados, dois campos precisam ser populados.

| Categoria do campo | Configurações de exemplo |
| --- | --- |
| Relacionado | Relacionado = ID do registro (por exemplo, ID da conta) e Tipo Relacionado conforme selecionado na lista. |
| Cliente | Representa a ID do registro e o tipo de cliente conforme selecionado na lista. |
| Proprietário | Representa a ID da equipe ou do usuário do sistema, bem como o tipo do proprietário, conforme selecionado na lista. |

### <a name="enable-upsert-behavior"></a>Habilitar o comportamento de upsert

Você pode aproveitar o comando **atualizar um registro** para fornecer ações de upsert, o que atualiza o registro caso ele já exista ou, caso contrário, cria um registro. Para invocar o upsert, forneça a entidade e uma chave GUID. Se o registro com o tipo e a chave especificados existe, uma atualização ocorre. Caso contrário, é criado um registro com a chave especificada.

### <a name="trigger-behavior"></a>Comportamento de gatilho

Se você tiver um gatilho registrado na atualização de um registro, o fluxo será executado para cada atualização *confirmada* no registro fornecido. O serviço invoca seu fluxo de forma assíncrona e, com o conteúdo que ele captura no momento, a invocação ocorre.

> [!NOTE]
> Se você tiver duas atualizações que ocorrem dentro de segundos entre si, o fluxo poderá ser disparado mais de uma vez com o conteúdo mais recente com controle de versão.

Execuções de fluxo poderão se atrasar se houver uma lista de pendências de trabalhos do sistema em seu ambiente.  Se esse atraso ocorre, o fluxo é disparado quando o trabalho do sistema para invocar o fluxo é executado.
