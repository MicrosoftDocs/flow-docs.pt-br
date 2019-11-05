---
title: Microsoft Flow solicitações de exportação de entidade de dados GDPR | Microsoft Docs
description: Saiba como usar Microsoft Flow para responder a solicitações de exportação de entidade de dados às GPDR.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 15eff70b8996e5ea130142a1c01699906e199642
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548189"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Respondendo a solicitações de exportação de entidade de dados GDPR para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Como parte do nosso compromisso de fazer parceria com você em sua jornada com o Regulamento Geral sobre a Proteção de Dados (GDPR), desenvolvemos a documentação para ajudá-lo a se preparar. A documentação não apenas descreve o que estamos fazendo para se preparar para o GDPR, mas também compartilha exemplos de etapas que você pode adotar hoje com a Microsoft para dar suporte à conformidade com o GDPR ao usar o Microsoft Flow.

## <a name="manage-export-requests"></a>Gerenciar solicitações de exportação

O *direito de portabilidade de dados* permite que uma entidade de dados solicite uma cópia de seus dados pessoais em um formato eletrônico (que é um "formato estruturado, comumente usado, legível por computador e interoperável") que pode ser transmitido para outro controlador de dados.

O Microsoft Flow oferece as seguintes experiências para localizar ou exportar dados pessoais para um usuário específico:

* **Acesso ao site:** entre no [centro de administração do PowerApps](https://admin.powerapps.com/)ou no [centro de administração do Microsoft Flow](https://admin.flow.microsoft.com/).

* **Acesso ao PowerShell:**  [cmdlets do PowerShell de administrador do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

|**Dados do cliente**|**Acesso ao site**|**Acesso ao PowerShell**|
|-----------------|------------------|-------------------|
|Logs gerados pelo sistema|[Portal de confiança do serviço do Office 365](https://servicetrust.microsoft.com/)|
|Histórico de execuções|Portal do Microsoft Flow Maker||
|Fluxo|Portal do Microsoft Flow Maker||
|Permissões de fluxo| Portal do Microsoft Flow Maker e centro de administração do Microsoft Flow||
|Detalhes do usuário||Cmdlets do PowerApps|
|Conexões|Portal do Microsoft Flow Maker|Cmdlets do PowerApps |
|Permissões de conexão|Portal do Microsoft Flow Maker|Cmdlets do PowerApps |
|Conectores personalizados|Portal do Microsoft Flow Maker|Cmdlets do PowerApps |
|Permissões de conector personalizado|Portal do Microsoft Flow Maker|Cmdlets do PowerApps |
|Gateway|Portal do Microsoft Flow Maker|Cmdlets do PowerShell do gateway de dados local|
|Permissões de gateway|Portal do Microsoft Flow Maker|Cmdlets do PowerShell do gateway de dados local|

## <a name="export-a-flow"></a>Exportar um fluxo

Um usuário final ou um administrador que concedeu a si mesmo acesso ao fluxo, pode exportar o fluxo seguindo estas etapas:

1. Entre [Microsoft Flow](https://flow.microsoft.com/).

1. Selecione o link **meus fluxos** e, em seguida, selecione o fluxo a ser exportado.

1. Selecionar **... Mais**e, em seguida, selecione **Exportar**.

    ![Fluxo de exportação](./media/gdpr-dsr-export/export-flow.png)

1. Selecione **pacote (. zip)** .

Seu fluxo agora estará disponível como um pacote compactado. Para obter mais informações, consulte a postagem no blog sobre [como exportar e importar um fluxo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportar histórico de execução

O histórico de execuções inclui uma lista de todas as execuções que ocorreram para um fluxo. Esses dados incluem o status do fluxo, a hora de início, a duração e os dados de entrada/saída para gatilhos e ações.

Um usuário final ou um administrador, que recebeu acesso ao fluxo por meio do centro de administração Microsoft Flow, pode seguir estas etapas para exportar esses dados:

1. Entre [Microsoft Flow](https://flow.microsoft.com/).
1. Selecione o link **meus fluxos** e, em seguida, selecione o fluxo para o qual você deseja exportar o histórico de execução.
1. No painel **histórico de execuções** , selecione **ver tudo**.

    ![Histórico de execuções](./media/gdpr-dsr-export/run-history.png)

1. Selecione **baixar CSV**.

    ![Baixar CSV](./media/gdpr-dsr-export/download-csv.png)

O histórico de execuções é baixado como um arquivo. csv para que você possa abri-lo no Microsoft Excel ou em um editor de texto e analisar ainda mais os resultados.

## <a name="export-a-users-activity-feed"></a>Exportar o feed de atividades de um usuário

No [Microsoft Flow](https://flow.microsoft.com/), o feed de atividades mostra o histórico de atividades, falhas e notificações de um usuário. Qualquer usuário pode exibir seu feed de atividades seguindo estas etapas:

1. Entre [Microsoft Flow](https://flow.microsoft.com/), selecione o ícone de sino próximo ao canto superior direito e, em seguida, selecione **Mostrar todas as atividades**.

    ![Mostrar feed de atividade](./media/gdpr-dsr-export/show-activity-feed.png)

1. Na tela **atividade** , copie os resultados e cole-os em um editor de documentos, como o Microsoft Word.

    ![Mostrar feed de atividade](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportar as conexões de um usuário

As conexões permitem que os fluxos se conectem a APIs, aplicativos SaaS e outros sistemas de terceiros. Siga estas etapas para exibir suas conexões:

1. Entre [Microsoft Flow](https://flow.microsoft.com/), selecione o ícone de engrenagem próximo ao canto superior direito e, em seguida, selecione **conexões**.

    ![Mostrar conexões](./media/gdpr-dsr-export/show-connections.png)
1. Copie os resultados e cole-os em um editor de documentos, como o Microsoft Word.

Cmdlets do PowerShell de administrador do PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Exportar uma lista de permissões de conexão de um usuário

Um usuário pode exportar as atribuições de função de conexão para todas as conexões às quais elas têm acesso por meio da função Get-ConnectionRoleAssignment no [cmdlets do PowerShell do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Cmdlets do PowerShell de administrador do PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Exportar os conectores personalizados de um usuário

Os conectores personalizados complementam os conectores prontos para uso e permitem a conectividade com outras APIs, SaaS e sistemas personalizados desenvolvidos. Você pode transferir a propriedade de um conector personalizado ou excluí-la.

Siga estas etapas para exportar uma lista de conectores de clientes:

1. Navegue até [Microsoft Flow](https://flow.microsoft.com).
1. Selecione o ícone de **engrenagem** configurações.
1. Selecione **conectores personalizados**.
1. Copie e cole a lista de conectores personalizados em um editor de texto como o Microsoft Word.

    ![Exportar conectores personalizados](./media/gdpr-dsr-export/export-custom-connectors.png)

Além da experiência fornecida no Microsoft Flow, você pode usar a função Get-Connector dos [cmdlets do PowerShell do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) para exportar todos os conectores personalizados.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Cmdlets do PowerShell de administrador do PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Exportar permissões de conector personalizado de um usuário

Um usuário pode exportar todas as permissões de conector personalizadas criadas por meio da função Get-ConnectorRoleAssignment no [cmdlets do PowerShell do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Cmdlets do PowerShell de administrador do PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Exportar histórico de aprovação

O histórico de Microsoft Flow aprovações captura um registro histórico de aprovações que foram recebidas ou enviadas para um usuário. Qualquer usuário pode exibir seu histórico de aprovação:

1. Entrar [Microsoft Flow](https://flow.microsoft.com/), selecionar **aprovações**e, em seguida, selecionar **histórico**.

    ![Exibir histórico de aprovação](./media/gdpr-dsr-export/view-approval-history.png)

1. Uma lista mostra as aprovações que o usuário recebeu. Os usuários podem mostrar as aprovações que eles enviaram selecionando a seta para baixo ao lado de **recebido** e, em seguida, selecionando **enviado**.

    ![Exibir aprovações recebidas](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Exportar detalhes do usuário
Os detalhes do usuário fornecem uma ligação entre um usuário e um locatário específico. Um administrador pode exportar essas informações chamando o cmdlet **Get-AdminFlowUserDetails** e passando a ID de objeto para o usuário.

Cmdlets do PowerShell de administrador do PowerApps

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Exportar configurações de gateway
Responder a solicitações de exportação de entidade de dados para gateways de dados locais pode ser encontrado [aqui](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

