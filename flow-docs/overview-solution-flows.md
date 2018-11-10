---
title: Visão geral de fluxos com reconhecimento de solução | Microsoft Docs
description: Conheça as vantagens de criar fluxos em soluções.
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
ms.openlocfilehash: 2515b64629436ccb96de497eaf928b83f281dc5f
ms.sourcegitcommit: b41b45f6fa29a22e9a9a4d3c726a2321b2ff3cbf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2018
ms.locfileid: "51025452"
---
# <a name="overview"></a>Visão geral

Quando você hospeda os fluxos em uma [solução](https://docs.microsoft.com/powerapps/maker/common-data-service/solutions-overview), eles se tornam portáteis. Dessa forma, fica mais fácil movê-los, bem como os respectivos componentes, de um ambiente para outro. Um caso de uso típico seria com um ISV (fornecedor independente de software) para desenvolver fluxos em um ambiente de área restrita e movê-los para um ambiente de teste. Após os testes, o ISV moveria os fluxos para um ambiente de produção, de modo que os clientes pudessem comprá-los. Esse processo é muito mais fácil quando você cria os fluxos em soluções e depois move as soluções e o respectivo conteúdo.

Os fluxos criados dentro de uma solução são chamados de fluxos com *reconhecimento de solução*. Você pode adicionar vários fluxos em uma única solução.

> [!NOTE] 
> No entanto, não é possível mover fluxos sem reconhecimento de solução para uma solução (fluxos não criados em uma solução).

## <a name="prerequisites"></a>Pré-requisitos

Para criar soluções e fluxos com reconhecimento de solução, é necessário ter os seguintes componentes:

- [Common Data Service for Apps 2.0](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
- Um ambiente com a versão 9.1.0.267 ou posterior.

  Para verificar a versão, vá para o [Centro de administração do Microsoft Flow](https://admin.flow.microsoft.com), selecione **Ambientes**, o ambiente no qual você tem interesse e a guia **Detalhes**.

## <a name="create-a-solution"></a>Criar uma solução

Para criar uma solução, faça o seguinte:

1. Entre no [Microsoft Flow](https://flow.microsoft.com).
1. Selecione **Soluções**, na barra de navegação.

   ![](./media/overview-solution-flows/select-solutions-from-left-nav.png)

1. Selecione **+ Nova solução**.

   ![](./media/overview-solution-flows/select-new-solution.png)

1. Forneça todas as informações necessárias para a nova solução, como **Nome para exibição**, **Fornecedor**, **Versão** e **Nome**. Convém também fornecer uma descrição para a solução.

   ![](./media/overview-solution-flows/new-solution.png)

1. Selecione **Salvar e Fechar**, no menu superior.

   ![](./media/overview-solution-flows/save-and-close-solution.png)

   A nova solução deverá ter a aparência da seguinte imagem:

   ![](./media/overview-solution-flows/new-solution-created.png)

   > [!TIP]
   > Selecione **Soluções** para atualizar a lista de soluções, caso a nova solução não esteja exibida.

## <a name="learn-more"></a>Saiba mais

- [Criar um fluxo em uma solução](./create-flow-solution.md)
- [Exportar uma solução](./export-flow-solution.md)
- [Importar uma solução](./import-flow-solution.md)
- [Editar um fluxo com reconhecimento de solução](./edit-solution-aware-flow.md)
- [Remover um fluxo com reconhecimento de solução](./remove-solution-aware-flow.md)
