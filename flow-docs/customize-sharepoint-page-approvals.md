---
title: Gerenciar aprovações de página do SharePoint com Microsoft Flow | Microsoft Docs
description: Saiba como gerenciar as aprovações de páginas do SharePoint com o Microsoft Flow..
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
ms.openlocfilehash: 1b328b604f9b199c2303dde3a0aa00898f188ada
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547644"
---
# <a name="manage-sharepoint-page-approvals-with-microsoft-flow"></a>Gerenciar aprovações de página do SharePoint com Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os administradores de site do SharePoint podem usar Microsoft Flow para exigir que páginas novas ou atualizadas do site sejam aprovadas antes de serem publicadas.

Neste artigo, você aprenderá a configurar seu site do SharePoint para usar um fluxo para exigir alterações no site a serem aprovadas antes de ficarem ativas.

## <a name="configure-sharepoint-for-page-approvals"></a>Configurar o SharePoint para aprovações de página

### <a name="prerequisites"></a>Pré-requisitos 

Você deve ser um administrador de site do SharePoint para executar as atividades neste artigo.

1. Entre no SharePoint como um administrador de site.
1. Selecione **páginas** na barra de navegação.

    ![Selecionar fluxo de aprovação de página](media/customize-sharepoint-page-approvals/pages.png)

1. Selecione **fluxo** e, em seguida, selecione **Configurar fluxo de aprovação de página**.
    
    ![Selecionar fluxo de aprovação de página](media/customize-sharepoint-page-approvals/select-page-approval-flow.png)

1. Forneça um **nome de fluxo**, pelo menos um nome na caixa **aprovadores** e, em seguida, selecione **criar**.
    
    ![Selecionar fluxo de aprovação de página](media/customize-sharepoint-page-approvals/flow-name-approvers-create.png)

Isso é tudo! Agora, cada vez que uma página é adicionada ou modificada, uma solicitação de aprovação vai para os **aprovadores** listados no fluxo.

O fluxo de aprovação de página é assim como qualquer outro fluxo, portanto, está listado na guia **meus fluxos** .

![Selecionar fluxo de aprovação de página](media/customize-sharepoint-page-approvals/page-approval-flow-success.png)

## <a name="submit-a-page-for-approval"></a>Enviar uma página para aprovação

Agora que você criou um fluxo de aprovação de página, qualquer pessoa que adicionar ou alterar uma página precisará fazer o seguinte:

 - Faça uma alteração no site (adicione uma nova página, por exemplo) e, em seguida, salve a alteração.

     ![Enviar página para aprovação](media/customize-sharepoint-page-approvals/create-new-page.png)
     
 - Aguarde até que alguém aprove a alteração.
    
    ![Enviar página para aprovação](media/customize-sharepoint-page-approvals/wait-for-approval.png)
    
## <a name="approve-a-page"></a>Aprovar uma página

Os aprovadores recebem um email sempre que houver uma solicitação de aprovação de página. Eles podem aprovar as solicitações diretamente no email (se o cliente de email oferecer suporte a mensagens acionáveis) ou abrir a página do email a ser revisado e, em seguida, aprovar a página no SharePoint.

## <a name="customize-page-approval-flows"></a>Personalizar fluxos de aprovação de página

Como as aprovações de página usam Microsoft Flow nos bastidores, o fluxo de aprovação de página está disponível para proprietários de sites para modificar e adicionar qualquer lógica de negócios personalizada no fluxo. Para modificar o fluxo, o proprietário do site pode selecionar **fluxos** e, em seguida, selecionar **os fluxos** na biblioteca de páginas para localizar o fluxo de aprovação de página.

## <a name="learn-more"></a>Saiba Mais

- [Fluxo de aprovação de página](https://support.office.com/article/page-approval-flow-a8b2e689-d4a1-4639-8028-333c0ece30d9)
- [Configurar a aprovação da página](https://support.office.com/article/configure-page-approval-14ce6976-a0a7-427b-b4ab-d28d344a5222)
