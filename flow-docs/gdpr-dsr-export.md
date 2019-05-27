---
title: Solicitações de exportação de entidade de dados de GDPR do Microsoft Flow | Microsoft Docs
description: Saiba como usar o Microsoft Flow para responder às solicitações de exportação de entidade de dados de GPDR.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e0f9b8e5b345b4dbc226cff2f42850bb126c09b3
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461782"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Responder às solicitações de exportação de entidade de dados de GDPR do Microsoft Flow

Como parte do nosso comprometimento em firmar uma parceria com você em sua jornada rumo ao GDPR (Regulamento Geral sobre a Proteção de Dados), desenvolvemos uma documentação para ajudar em sua preparação. A documentação não apenas descreve o que estamos fazendo para nos prepararmos para o GDPR, mas também compartilha exemplos de etapas que você pode executar hoje com a Microsoft para estar em conformidade com o GDPR usando o Microsoft Flow.

## <a name="manage-export-requests"></a>Gerenciar solicitações de exportação

O *direito de portabilidade de dados* permite que uma entidade de dados solicite uma cópia de seus dados pessoais em formato eletrônico (que é um "formato estruturado, normalmente usado, legível por máquina e interoperável") que pode ser transmitido para outro controlador de dados.

O Microsoft Flow oferece as seguintes experiências para localizar ou exportar dados pessoais de um usuário específico:

* **Acesso ao site:** entre no [Centro de Administração do PowerApps](https://admin.powerapps.com/) ou no [Centro de Administração do Microsoft Flow](https://admin.flow.microsoft.com/).

* **Acesso ao PowerShell**:  [Cmdlets do PowerShell de administrador para](https://go.microsoft.com/fwlink/?linkid=871804).

|**Dados de cliente**|**Acesso ao site**|**Acesso ao PowerShell**|
|-----------------|------------------|-------------------|
|Logs gerados pelo sistema|[Portal de Confiança do Serviço Office 365](https://servicetrust.microsoft.com/)|
|Histórico de execuções|Microsoft Flow Maker Portal||
|Fluxos|Microsoft Flow Maker Portal||
|Permissões do Flow| Microsoft Flow Maker Portal e Centro de Administração do Microsoft Flow||
|Detalhes do usuário||Cmdlets de PowerApps|
|Conexões|Microsoft Flow Maker Portal|Cmdlets de PowerApps |
|Permissões de conexão|Microsoft Flow Maker Portal|Cmdlets de PowerApps |
|Conectores personalizados|Microsoft Flow Maker Portal|Cmdlets de PowerApps |
|Permissões do conector personalizado|Microsoft Flow Maker Portal|Cmdlets de PowerApps |
|Gateway|Microsoft Flow Maker Portal|Cmdlets do PowerShell do gateway de dados local|
|Permissões de gateway|Microsoft Flow Maker Portal|Cmdlets do PowerShell do gateway de dados local|

## <a name="export-a-flow"></a>Exportar um fluxo

Um usuário final ou administrador, que concedeu a si mesmo acesso se o fluxo, pode exportar o fluxo executando estas etapas:

1. Entre no [Microsoft Flow](https://flow.microsoft.com/).

1. Selecione o link **Meu fluxos** e, depois, selecione o fluxo para exportação.

1. Selecione **... Mais** e, em seguida, selecione **Exportar**.

    ![Exportar fluxo](./media/gdpr-dsr-export/export-flow.png)

1. Selecione o **Pacote (.zip)**.

Seu fluxo não estará disponível como um pacote compactado. Para saber mais, veja a postagem do blog sobre [como exportar e importar um fluxo](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exportar histórico de execução

O histórico de execução inclui uma lista com todas as execuções que ocorreram para um fluxo. Esses dados incluem o status do fluxo, a hora de início, a duração e os dados de entrada/saída para gatilhos e ações.

Um usuário final ou administrador que recebeu acesso ao fluxo por meio do Centro de Administração do Microsoft Flow, pode executar estas etapas para exportar esses dados:

1. Entre no [Microsoft Flow](https://flow.microsoft.com/).
1. Selecione o link **Meus fluxos** e, depois, selecione o fluxo para o qual você deseja exportar o histórico de execuções.
1. No painel **HISTÓRICO DE EXECUÇÕES**, selecione **Ver todas**.

    ![Histórico de execuções](./media/gdpr-dsr-export/run-history.png)

1. Selecione **Baixar CSV**.

    ![Baixar CSV](./media/gdpr-dsr-export/download-csv.png)

O histórico de execuções é baixado como um arquivo .csv para que você possa abri-lo no Microsoft Excel, ou em um editor de texto, e analisar com mais detalhes os resultados.

## <a name="export-a-users-activity-feed"></a>Exportar um feed de atividades do usuário

No [Microsoft Flow](https://flow.microsoft.com/), o feed de atividades mostra o histórico de atividades, falhas e notificações de um usuário. Qualquer usuário pode exibir o próprio feed de atividades executando estas etapas:

1. Entre no [Microsoft Flow](http://flow.microsoft.com/), selecione o ícone de sino no canto superior direito e selecione **Mostrar todas as atividades**.

    ![Mostrar feed de atividades](./media/gdpr-dsr-export/show-activity-feed.png)

1. Na tela **Atividade**, copie os resultados e cole-os em um editor de documentos, como o Microsoft Word.

    ![Mostrar feed de atividades](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exportar as conexões de um usuário

As conexões permitem que os fluxos se conectem a APIs, aplicativos SaaS e outros sistemas de terceiros. Execute estas etapas para exibir suas conexões:

1. Entre no [Microsoft Flow](http://flow.microsoft.com/), selecione o ícone de engrenagem no canto superior direito e selecione **Conexões**.

    ![Mostrar Conexões](./media/gdpr-dsr-export/show-connections.png)
1. Copie os resultados e cole-os em um editor de documentos, como o Microsoft Word.

Cmdlets do PowerShell de Administração do PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Exportar uma lista de permissões de conexão de um usuário

Um usuário pode exportar as atribuições de função de conexão de todas as conexões às quais tem acesso por meio da função Get-ConnectionRoleAssignment nos [cmdlets do PowerShell para PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Cmdlets do PowerShell de Administração do PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Exportar os conectores personalizados de um usuário

Conectores personalizados complementam os conectores originais e permitem a conectividade com outras APIs, SaaS e sistemas personalizados. Você pode transferir a propriedade de um conector personalizado ou excluí-lo.

Execute estas etapas para exportar uma lista de conectores de cliente:

1. Navegue até o [Microsoft Flow](https://flow.microsoft.com).
1. Selecione o ícone de **engrenagem** de configurações.
1. Selecione **Conectores Personalizados**.
1. Copie e cole a lista de conectores personalizados em um editor de texto, como o Microsoft Word.

    ![Exportar conectores personalizados](./media/gdpr-dsr-export/export-custom-connectors.png)

Além da experiência fornecida no Microsoft Flow, você pode usar a função Get-Connector dos [cmdlets do PowerShell para PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) para exportar todos os conectores personalizados.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Cmdlets do PowerShell de Administração do PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Exportar as permissões de conector personalizado de um usuário

Um usuário pode exportar todas as permissões de conector personalizado criadas por meio da função Get-ConnectorRoleAssignment nos [cmdlets do PowerShell para PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Cmdlets do PowerShell de Administração do PowerApps

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Exportar histórico de aprovações

O Histórico de Aprovações do Microsoft Flow captura um registro histórico de aprovações que foram recebidas ou enviadas para um usuário. Qualquer usuário pode exibir o próprio histórico de aprovação desta maneira:

1. Entrando no [Microsoft Flow](http://flow.microsoft.com/), selecionando **Aprovações** e, em seguida, selecionando **Histórico**.

    ![Exibir histórico de aprovações](./media/gdpr-dsr-export/view-approval-history.png)

1. Uma lista mostra as aprovações recebidas pelo usuário. Os usuários podem mostrar as aprovações que eles enviaram selecionando a seta para baixo ao lado de **Recebidas** e, em seguida, selecionando **Enviadas**.

    ![Exibir aprovações recebidas](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Exportar detalhes do usuário
Os detalhes do usuário fornecem uma ligação entre um usuário e um locatário específico. Um administrador pode exportar essas informações ao chamar o cmdlet **Get-AdminFlowUserDetails** e passar a ID de objeto para o usuário.

Cmdlets do PowerShell de Administração do PowerApps

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Exportar configurações do gateway
Para responder a solicitações de exportação de titular dos dados de gateways de dados locais clique [aqui](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

