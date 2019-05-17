---
title: Gerenciar aprovações da página do SharePoint com o Microsoft Flow | Microsoft Docs
description: Saiba como gerenciar aprovações da página do SharePoint com o Microsoft Flow.
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
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: d5e01a3d2e13cc48107e19e0e2bbea3821437273
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65061332"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Gerenciar aprovações da página do SharePoint com o Microsoft Flow

Os administradores de sites do SharePoint podem usar o Microsoft Flow a fim de solicitar que as páginas novas ou atualizadas dos sites sejam aprovadas, antes de publicá-las.

Veja neste artigo como configurar seu site do SharePoint para usar um fluxo, a fim de solicitar que as alterações sejam aprovadas, antes de publicá-las.

## <a name="configure-sharepoint-for-page-approvals"></a>Configurar o SharePoint para aprovações de páginas

### <a name="prerequisites"></a>Pré-requisitos 

É necessário ser um administrador de site do SharePoint para realizar as atividades descritas neste artigo.

1. Entre no SharePoint como administrador de site.
1. Selecione **Páginas** na barra de navegação.

    ![Selecionar fluxo de aprovação de página](media/customize-sharepoint-page-approvals/pages.png)

1. Selecione **Fluxo** e, em seguida, escolha **Configurar fluxo de aprovação de página**.
    
    ![Selecionar fluxo de aprovação de página](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Atribua um **nome ao fluxo**, insira pelo menos um nome na caixa **Aprovadores** e selecione **Criar**.
    
    ![Selecionar fluxo de aprovação de página](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Pronto! Agora, sempre que uma página for adicionada ou modificada, nosso sistema enviará uma solicitação de aprovação para os **Aprovadores** indicados no fluxo.

O fluxo de aprovação de página é igual a qualquer outro fluxo e está relacionado na guia **Meus fluxos**.

![Selecionar fluxo de aprovação de página](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Enviar uma página para aprovação

Depois de criar um fluxo de aprovação de página, todas as pessoas que adicionarem ou alterarem uma página deverão fazer o seguinte:

 - Fazer alterações ao site (por exemplo, adicionar uma nova página) e salvá-las.

     ![Enviar página para aprovação](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Aguarde a aprovação das alterações.
    
    ![Enviar página para aprovação](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Aprovar uma página

Os aprovadores recebem um email, sempre que há uma solicitação de aprovação da página. Eles podem aprovar as solicitações diretamente no email (se o respectivo cliente de email tiver suporte para mensagens acionáveis) ou abrir a página no email para revisar e aprová-la no SharePoint.

## <a name="customize-page-approval-flows"></a>Personalizar fluxos de aprovação de página

Como as aprovações de página usam o Microsoft Flow nos bastidores, o fluxo de aprovação de página está disponível para que os proprietários de sites possam modificar e adicionar lógicas de negócios personalizadas no fluxo. Para modificar o fluxo, o proprietário do site pode selecionar **Fluxos** e, em seguida, escolher **Ver seus fluxos**, na biblioteca de páginas, para encontrar o fluxo de aprovação de página.

## <a name="learn-more"></a>Saiba mais

- [Fluxo de aprovação de página](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configurar aprovação de página](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
