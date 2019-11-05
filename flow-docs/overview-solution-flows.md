---
title: Visão geral dos fluxos com reconhecimento de solução | Microsoft Docs
description: Conheça os benefícios da criação de fluxos em soluções.
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
ms.date: 11/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 19eb7d051c4d1438ec45305620e369b5499252a0
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548552"
---
# <a name="overview"></a>Sobre
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Quando você hospeda seus fluxos em uma [solução](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview), eles se tornam portáteis, tornando mais fácil movê-los e todos os seus componentes de um ambiente para outro. Um caso de uso típico é para um fornecedor de software independente (ISV) desenvolver fluxos em um ambiente de área restrita e, em seguida, mover esses fluxos para um ambiente de teste. Após o teste, o ISV moveria os fluxos para um ambiente de produção para clientes que compraram esses fluxos. Esse processo é muito mais fácil quando você cria seus fluxos em soluções e, em seguida, move as soluções e seu conteúdo.

Os fluxos criados dentro de uma solução são conhecidos como fluxos *com reconhecimento de solução* . Você pode adicionar vários fluxos em uma única solução.

> [!NOTE] 
> Não é possível mover fluxos sem reconhecimento de solução (fluxos não criados em uma solução) para uma solução.

## <a name="prerequisites"></a>Pré-requisitos

Você deve ter os seguintes componentes para criar soluções e fluxos com reconhecimento de solução:

- [Common Data Service](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Um ambiente com a versão 9.1.0.267 ou posterior.

  Para verificar sua versão, vá para [Microsoft Flow centro de administração](https://admin.flow.microsoft.com), selecione **ambientes**, selecione o ambiente no qual você está interessado e, em seguida, selecione a guia **detalhes** .

## <a name="create-a-solution"></a>Criar uma solução

Siga estas etapas para criar uma solução:

1. Entre no [Microsoft Flow](https://flow.microsoft.com).
1. Selecione **soluções** na barra de navegação.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Selecione **+ nova solução**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Forneça todas as informações necessárias para sua nova solução, incluindo o **nome de exibição**, o **Editor**, a **versão**e o **nome**. Também é uma boa ideia fornecer uma descrição de sua solução.

   ![](./media/overview-solution-flows/new-solution.png)

1. Selecione **salvar e fechar** no menu na parte superior.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   Sua nova solução pode aparecer como esta imagem:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Selecione **soluções** para atualizar a lista de soluções se sua nova solução não for exibida.

## <a name="learn-more"></a>Saiba Mais

- [Criar um fluxo em uma solução](./create-flow-solution.md)
- [Exportar uma solução](./export-flow-solution.md)
- [Importar uma solução](./import-flow-solution.md)
- [Editar um fluxo com reconhecimento de solução](./edit-solution-aware-flow.md)
- [Remover um fluxo com reconhecimento de solução](./remove-solution-aware-flow.md)
