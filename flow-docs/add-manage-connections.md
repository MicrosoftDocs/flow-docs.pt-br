---
title: Aprenda a se conectar aos seus dados usando conexões e gateways de dados locais | Microsoft Docs
description: Adicionar ou gerenciar conexões com o SharePoint, SQL Server, OneDrive for Business, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive e muito mais
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 1de8602cc573e800d721b6b70222df49cf1577e3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544768"
---
# <a name="manage-connections-in-microsoft-flow"></a>Gerenciar conexões no Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Se você criar uma conexão no Microsoft Flow, poderá acessar seus dados facilmente ao criar um fluxo. Microsoft Flow inclui conexões comumente usadas, incluindo SharePoint, SQL Server, Office 365, OneDrive for Business, Salesforce, Excel, Dropbox, Twitter e muito mais. As conexões são compartilhadas com o PowerApps, portanto, quando você cria uma conexão em um produto, a conexão aparece no outro.

Por exemplo, você pode usar uma conexão para executar estas tarefas:

* Atualize uma lista do SharePoint.
* Obtenha dados de um arquivo do Excel em sua conta do OneDrive for Business ou do dropbox.
* Enviar email no Office 365.
* Envie um tweet.

Você pode criar uma conexão em vários cenários, como estes:

* Criando um [fluxo de um modelo](get-started-logic-template.md)
* Criando um [fluxo de em branco](get-started-logic-flow.md) ou atualizando um fluxo existente
* Criando uma conexão no [site Microsoft Flow][1] diretamente

Este tópico mostra como gerenciar conexões no [site Microsoft Flow][1].

## <a name="add-a-connection"></a>Adicionar uma conexão
1. No [site Microsoft Flow][1], entre com sua conta corporativa ou de organização.
2. Próximo ao canto superior direito, selecione o ícone de engrenagem e, em seguida, selecione **conexões**.
   
    ![Selecionar conexões](./media/add-manage-connections/connections-menu.png)
3. Selecione **criar conexão**.
4. Na lista de **conexões disponíveis**, selecione a conexão que você deseja configurar, como o SharePoint.
5. Selecione o botão **criar conexão** e, em seguida, insira suas credenciais para configurar a conexão.

Quando a conexão é configurada, ela é listada em **minhas conexões**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Conectar-se aos seus dados por meio de um gateway de dados local
No momento da redação deste artigo, SQL Server e SharePoint Server dão suporte ao gateway de dados local. Para criar uma conexão que usa um gateway:

1. Siga as etapas anteriores neste tópico para adicionar uma conexão.
2. Na lista de **conexões disponíveis**, selecione **SQL Server**e, em seguida, marque a caixa de seleção **conectar via gateway de dados local** .
   
    ![Selecionar gateway](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Os gateways de dados do Microsoft SharePoint dão suporte ao tráfego HTTP, mas não ao tráfego HTTPS.
   > 
   > 
3. Forneça as credenciais da conexão e selecione o gateway que você deseja usar.
   
    Para obter mais informações, consulte [gerenciar gateways](gateway-manage.md) e [entender gateways](gateway-reference.md).
   
    Quando a conexão é configurada, ela é listada em **minhas conexões**.

## <a name="delete-a-connection"></a>Excluir uma conexão
1. Vá para a página **minhas conexões** e selecione o ícone de lixeira para a conexão que você deseja excluir.
   
    ![Excluir conexão](./media/add-manage-connections/delete-connection.png)
2. Selecione **OK** para confirmar que você gostaria de excluir a conexão.
   
    ![Confirmar exclusão](./media/add-manage-connections/delete-confirmation.png)

Quando você exclui uma conexão, ela é removida do PowerApps e do Microsoft Flow.

## <a name="update-a-connection"></a>Atualizar uma conexão
Você pode atualizar uma conexão que não está funcionando porque os detalhes da sua conta ou sua senha foram alterados.

1. Na página **minhas conexões** , selecione o link **verificar senha** para a conexão que você deseja atualizar.
   
    ![Verificar senha](./media/add-manage-connections/verify-password.png)
2. Quando solicitado, atualize sua conexão com novas credenciais.

Quando você atualiza uma conexão, ela é atualizada para o PowerApps e o Microsoft Flow.

## <a name="troubleshoot-a-connection"></a>Solucionar problemas de conexão
Dependendo das políticas da sua organização, talvez seja necessário usar a mesma conta para entrar no Microsoft Flow e criar uma conexão com o SharePoint, Office 365 ou OneDrive for Business.

Por exemplo, você pode entrar no Microsoft Flow com *yourname@outlook.com* mas ser bloqueado quando tentar se conectar ao SharePoint com o *yourname@contoso.com* . Em vez disso, você pode entrar no Microsoft Flow com *yourname@contoso.com* e você poderá se conectar ao SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
