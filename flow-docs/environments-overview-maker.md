---
title: Saiba mais sobre ambientes de Microsoft Flow | Microsoft Docs
description: Saiba como usar ambientes para isolar seus fluxos
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/27/2017
ms.author: sunayv
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8890e621d14fb0f2d00af4cdf767f05ddeab9f21
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547952"
---
# <a name="choosing-an-environment"></a>Escolhendo um ambiente
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este artigo apresenta Microsoft Flow **ambientes** nos quais você pode criar e isolar com segurança seus fluxos, gateways, conexões e outros recursos.

Você aprenderá sobre:

* Os recursos que os ambientes fornecem.
* Alternando entre ambientes.
* Como criar um fluxo no ambiente certo.

## <a name="environments-overview"></a>Visão geral dos ambientes

Ao criar um fluxo, você escolhe um ambiente para hospedar o fluxo e os recursos usados pelo fluxo. Você pode usar ambientes separados para cenários diferentes.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Aqui estão alguns cenários para usar ambientes

Cenário|Recomendação
-----|-----
Você deseja criar um fluxo que usa uma conexão com o Common Data Service da Microsoft.|Coloque seu fluxo e o Common Data Service no mesmo ambiente. Isso garante que todos os dados sejam isolados dentro desse ambiente (limite de isolamento).
Você está criando um fluxo para seu departamento de recursos humanos. Você deseja garantir que somente os usuários em seu departamento de recursos humanos tenham acesso ao fluxo.|Crie um ambiente e adicione apenas os usuários de RH a ele. Coloque o fluxo e quaisquer outros recursos que o fluxo usa nesse ambiente.
Há usuários na Europa que usam um fluxo para mostrar dados do SharePoint.|Crie um ambiente na Europa e, em seguida, crie seu fluxo e a conexão do SharePoint nele. Esse ambiente da Europa dá ao usuário Europeu o melhor desempenho, já que todos os recursos são locais para a Europa (localidade de dados).

Para criar ambientes, você deve ser um administrador de Microsoft Flow. Os administradores controlam quem tem acesso aos ambientes. Para obter detalhes sobre como você pode criar e gerenciar ambientes, consulte o tópico [administrar ambientes](environments-overview-admin.md) .

## <a name="switching-environments"></a>Alternando ambientes

Microsoft Flow torna fácil alternar entre ambientes. Ao mudar de ambiente, você verá apenas os itens que são criados nesse ambiente específico; Você não verá ou terá acesso a itens em qualquer outro ambiente.

Aqui está um exemplo.

Você criou um fluxo chamado *NewEmployee* no ambiente de *recursos humanos* . No [Microsoft Flow](https://flow.microsoft.com), você abre o ambiente de *vendas* . O fluxo *NewEmployee* não está listado. Para ver o fluxo do *NewEmployee* , abra o ambiente de *recursos humanos* . Lembre-se de que as mesmas regras se aplicam a quaisquer outros itens que você criou no ambiente, incluindo conexões, gateways, fluxos e muito mais.

Siga estas etapas para mudar de ambiente:

1. Entre [Microsoft Flow](https://flow.microsoft.com).
1. No canto superior direito, você verá uma imagem que representa seu perfil.

   ![imagem do perfil](./media/environments-overview-maker/default-environment.png)

1. Selecione a imagem. Uma lista suspensa exibe todos os ambientes disponíveis para você. O ambiente no qual você está conectado no momento está marcado:

   ![lista de imagens de ambientes](./media/environments-overview-maker/all-environments.png)
1. Para alternar para outro ambiente, selecione esse ambiente na lista:

   ![Selecione um ambiente para o qual alternar](./media/environments-overview-maker/select-europe.png)
1. Microsoft Flow muda para o novo ambiente.

## <a name="create-flows-in-the-right-environment"></a>Criar fluxos no ambiente certo

Antes de criar um fluxo, selecione o ambiente no qual você adicionará o fluxo e seus recursos.

> [!NOTE]
> Se você criar um fluxo no ambiente errado, terá que excluí-lo e, em seguida, criá-lo no ambiente correto.

Considere os seguintes fatores ao escolher um ambiente para hospedar seus fluxos:

* Você só pode criar gateways no ambiente padrão. Portanto, se você quiser usar um gateway para conectar seu fluxo a dados locais, será necessário usar o ambiente padrão.
* Os bancos de dados do Microsoft Common Data Service estão vinculados a um ambiente específico. Portanto, se você quiser criar um fluxo que usa o Common Data Service, deverá criar o fluxo no ambiente que hospeda o banco de dados.
* Você verá todos os ambientes nos quais é possível editar recursos. No entanto, você precisará pedir a um administrador para adicioná-lo como um criador a todos os ambientes nos quais deseja criar fluxos.

> [!NOTE]
> Você sempre poderá criar fluxos no ambiente padrão.

## <a name="next-steps"></a>Próximas etapas

* [Criar um fluxo de um modelo](get-started-logic-template.md)
* [Criar um fluxo](get-started-logic-flow.md)
* [Visão geral do ambiente para administradores](environments-overview-admin.md)
