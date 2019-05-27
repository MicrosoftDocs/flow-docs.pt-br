---
title: Saiba como conectar seus dados usando conexões e gateways de dados locais | Microsoft Docs
description: Adicionar ou gerenciar conexões com o SharePoint, SQL Server, OneDrive for Business, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google unidade e muito mais
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
ms.openlocfilehash: bdfa1072bca2afc7c608a4dbf68b8f598dff89f1
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456820"
---
# <a name="manage-connections-in-microsoft-flow"></a>Gerenciar conexões no Microsoft Flow
Se você criar uma conexão no Microsoft Flow, poderá acessar facilmente seus dados durante a criação de um fluxo. O Microsoft Flow inclui conexões usadas normalmente, incluindo o SharePoint, SQL Server, Office 365, OneDrive for Business, Salesforce, Excel, Dropbox, Twitter e muito mais. As conexões são compartilhadas com o PowerApps, assim, quando você cria uma conexão em um produto, ela aparece no outro.

Por exemplo, use uma conexão para executar estas tarefas:

* Atualizar uma lista do SharePoint.
* Obter dados de um arquivo do Excel em sua conta do OneDrive for Business ou Dropbox.
* Enviar email no Office 365.
* Enviar um tweet.

Crie uma conexão em vários cenários, como estes:

* Criar um [fluxo de um modelo](get-started-logic-template.md)
* Criar um [fluxo de espaço em branco](get-started-logic-flow.md) ou atualizar um fluxo existente
* Criar uma conexão diretamente no [site do Microsoft Flow][1]

Este tópico mostra como gerenciar conexões no [site do Microsoft Flow][1].

## <a name="add-a-connection"></a>Adicionar uma conexão
1. No [site do Microsoft Flow][1], entre com sua conta corporativa ou da organização.
2. No canto superior direito, selecione o ícone de engrenagem e selecione **Conexões**.
   
    ![Selecione conexões](./media/add-manage-connections/connections-menu.png)
3. Selecione **Criar conexão**.
4. Na lista de **Conexões disponíveis**, selecione a conexão que você quer configurar, como a do SharePoint.
5. Selecione o botão **Criar conexão** e insira suas credenciais para configurar a conexão.

Após a configuração da conexão, ela é relacionada em **Minhas conexões**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Conectar-se aos dados por meio de um gateway de dados local
No momento deste texto, o SQL Server e o SharePoint oferecem suporte ao gateway de dados local. Para criar uma conexão que usa um gateway:

1. Siga as etapas anteriores deste tópico para adicionar uma conexão.
2. Na lista de **Conexões disponíveis**, selecione **SQL Server** e, em seguida, marque a caixa de seleção **Conectar por meio do gateway de dados local**.
   
    ![Selecionar gateway](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Os gateways de dados do Microsoft SharePoint oferecem suporte a tráfego HTTP, mas não ao tráfego HTTPS.
   > 
   > 
3. Forneça as credenciais de conexão e selecione o gateway que você quer usar.
   
    Para obter mais informações, consulte [Gerenciar gateways](gateway-manage.md) e [Entender os gateways](gateway-reference.md).
   
    Após a configuração da conexão, ela é relacionada em **Minhas conexões**.

## <a name="delete-a-connection"></a>Excluir uma conexão
1. Acesse a página **Minhas conexões** e selecione o ícone de lixeira para a conexão que você quer excluir.
   
    ![Excluir conexão](./media/add-manage-connections/delete-connection.png)
2. Selecione **OK** para confirmar a exclusão da conexão.
   
    ![Confirmar exclusão](./media/add-manage-connections/delete-confirmation.png)

Quando você exclui uma conexão, ela é removida do PowerApps e do Microsoft Flow.

## <a name="update-a-connection"></a>Atualizar uma conexão
Atualize uma conexão que não está funcionando devido a alguma alteração nos detalhes ou senha de sua conta.

1. Na página **Minhas conexões**, selecione o link **Verificar senha** para a conexão que você deseja atualizar.
   
    ![Verificar senha](./media/add-manage-connections/verify-password.png)
2. Quando solicitado, atualize a conexão com novas credenciais.

Ao atualizar uma conexão, ela será atualizada no PowerApps e no Microsoft Flow.

## <a name="troubleshoot-a-connection"></a>Solucionar problemas de uma conexão
Dependendo das políticas de sua organização, talvez seja necessário usar a mesma conta para entrar no Microsoft Flow e criar uma conexão com o SharePoint, Office 365 ou OneDrive for Business.

Por exemplo, você pode entrar no Microsoft Flow com  *yourname@outlook.com*, mas ser bloqueado ao tentar se conectar ao SharePoint com *yourname@contoso.com*. Em vez disso, entre no Microsoft Flow com *yourname@contoso.com* e você poderá se conectar ao SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
