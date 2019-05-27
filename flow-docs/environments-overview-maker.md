---
title: Saiba mais sobre os ambientes do Microsoft Flow| Microsoft Docs
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
ms.openlocfilehash: 0e6b410f75f28ba13357878a5cda178bc66b69ff
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460857"
---
# <a name="choosing-an-environment"></a>Escolhendo um ambiente

Este artigo o apresenta aos **ambientes** do Microsoft Flow, nos quais é possível criar e isolar com segurança seus fluxos, gateways, conexões e outros recursos.

Você saberá mais sobre:

* Os recursos que os ambientes fornecem.
* Alternância entre ambientes.
* Como criar um fluxo no ambiente certo.

## <a name="environments-overview"></a>Visão geral de ambientes

Ao criar um fluxo, você escolhe em qual ambiente hospedá-lo e os recursos usados por esse fluxo. Você pode usar ambientes separados para cenários diferentes.

## <a name="here-are-a-few-scenarios-for-using-environments"></a>Aqui estão alguns cenários de uso de ambientes

Cenário|Recomendação
-----|-----
Você deseja criar um fluxo que use uma conexão com Common Data Service da Microsoft.|Coloque seu fluxo e o Common Data Service no mesmo ambiente. Isso garante que todos os dados estejam isolados dentro desse ambiente (limite de isolamento).
Você está criando um fluxo para seu departamento de Recursos Humanos. Você deseja garantir que somente usuários no departamento de Recursos Humanos tenham acesso ao fluxo.|Crie um ambiente e adicione apenas os usuários de RH a ele. Coloque o fluxo e quaisquer outros recursos usados por ele nesse ambiente.
Na Europa, há usuários que utilizam um fluxo para mostrar dados do SharePoint.|Crie um ambiente na Europa, depois crie seu fluxo e a conexão do SharePoint nele. Esse ambiente da Europa oferece o melhor desempenho aos usuários europeus, já que todos os recursos são locais para a Europa (localidade dos dados).

Para criar ambientes, você deve ser um administrador do Microsoft Flow. Administradores controlam quem tem acesso aos ambientes. Para obter detalhes sobre como criar e gerenciar ambientes, consulte o tópico [administrar ambientes](environments-overview-admin.md).

## <a name="switching-environments"></a>Alternância de ambientes

O Microsoft Flow facilita a alternância entre ambientes. Ao alternar ambientes, você vê apenas os itens que são criados nesse ambiente específico e não vê nem tem acesso aos itens em nenhum outro ambiente.

Veja um exemplo.

Você criou um fluxo chamado *NewEmployee* no ambiente *Recursos Humanos*. Em [Microsoft Flow](https://flow.microsoft.com), você abre o ambiente de *Vendas*. O fluxo *NewEmployee* não está listado. Para ver o fluxo *NewEmployee* fluxo, abra o ambiente *Recursos Humanos*. Lembre-se de que as mesmas regras se aplicam a quaisquer outros itens criados por você no ambiente, incluindo conexões, gateways, fluxos e muito mais.

Siga estas etapas para alternar os ambientes:

1. Entre no [Microsoft Flow](https://flow.microsoft.com).
1. No canto superior direito, você verá uma imagem que representa o seu perfil.

   ![Imagem de perfil](./media/environments-overview-maker/default-environment.png)

1. Selecione a imagem. Uma lista suspensa exibe todos os ambientes disponíveis para você. O ambiente no qual você está conectado no momento é verificado:

   ![lista da imagem de ambientes](./media/environments-overview-maker/all-environments.png)
1. Para alternar para outro ambiente, selecione o ambiente na lista:

   ![selecione um ambiente para o qual alternar](./media/environments-overview-maker/select-europe.png)
1. O Microsoft Flow alterna para o novo ambiente.

## <a name="create-flows-in-the-right-environment"></a>Criar fluxos no ambiente certo

Antes de criar um fluxo, selecione o ambiente no qual você adicionará o fluxo e seus recursos.

> [!NOTE]
> Caso crie um fluxo no ambiente errado, será preciso excluí-lo e depois criá-lo no ambiente correto.

Considere os seguintes fatores ao escolher um ambiente no qual hospedar seus fluxos:

* Você só pode criar gateways no ambiente padrão. Então, se deseja usar um gateway para conectar seu fluxo a dados locais, você precisará usar o ambiente padrão.
* Bancos de dados do Common Data Service da Microsoft são associados a um ambiente específico. Portanto, se deseja criar um fluxo que use o Common Data Service, você deve criar o fluxo no ambiente que hospeda o banco de dados.
* Você verá todos os ambientes nos quais é possível editar recursos. No entanto, será preciso solicitar que um administrador adicione você como um criador em todos os ambientes nos quais você deseja criar fluxos.

> [!NOTE]
> Você sempre poderá criar fluxos no ambiente padrão.

## <a name="next-steps"></a>Próximas etapas

* [Criar um fluxo a partir de um modelo](get-started-logic-template.md)
* [Criar um fluxo](get-started-logic-flow.md)
* [Visão geral do ambiente para Administradores](environments-overview-admin.md)
