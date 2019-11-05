---
title: Microsoft Flow solicitações de exclusão de entidade de dados GDPR | Microsoft Docs
description: Saiba como usar Microsoft Flow para responder a solicitações de exclusão de entidades de dados às GPDR.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 53e33d1c202b05854401573ca16040f17eb138c9
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548086"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Respondendo a solicitações de exclusão de entidade de dados GDPR para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O "direito de eliminação" pela remoção de dados pessoais dos dados de clientes de uma organização é uma proteção de chave no GDPR. A remoção de dados pessoais inclui a remoção de todos os dados pessoais e logs gerados pelo sistema, exceto informações do log de auditoria.

Microsoft Flow permite que os usuários criem fluxos de trabalho de automação que são uma parte crítica das operações diárias da sua organização. Quando um usuário sai da sua organização, um administrador precisa revisar manualmente e determinar se deseja ou não excluir determinados dados e recursos que o usuário criou. Há outros dados pessoais que são excluídos automaticamente sempre que a conta do usuário é excluída da Azure Active Directory.

A tabela a seguir mostra quais dados pessoais são excluídos automaticamente e quais dados exigem que um administrador examine e exclua manualmente:

|Requer revisão e exclusão manual|Excluído automaticamente quando o usuário é excluído da Azure Active Directory|
|------|------|
|Ambiente|Logs gerados pelo sistema|
|Permissões de ambiente * *|Histórico de execuções|
|Fluxo|Feed de atividades|
|Permissões de fluxo|Gateway |
|Detalhes do usuário|Permissões de gateway|
|Conexões||
|Permissões de conexão||
|Conector personalizado *||
|Permissões de conector personalizado||

\* Cada um desses recursos contém registros "criados por" e "modificados por" que incluem dados pessoais. Por motivos de segurança, esses registros são mantidos até que o recurso seja excluído.

\* * Para ambientes que incluem um banco de dados Common Data Service, as permissões de ambiente (por exemplo, quais usuários são atribuídos ao criador do ambiente e às funções de administrador) são armazenados como registros no banco de dados Common Data Service. Consulte [executando o DSRs em relação aos dados do cliente Common Data Service](https://go.microsoft.com/fwlink/?linkid=872251), para obter orientação sobre como responder a DSRs para usuários que usam o Common Data Service.

Para os dados e recursos que exigem revisão manual, o Microsoft Flow oferece as seguintes experiências para localizar ou alterar dados pessoais para um usuário específico:

* **Acesso ao site:** entre no [centro de administração do PowerApps](https://admin.powerapps.com/)ou no [centro de administração do Microsoft Flow](https://admin.flow.microsoft.com/)

* **Acesso ao PowerShell:**  [cmdlets do PowerShell de administrador do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) 

Aqui está a divisão das experiências disponíveis para que um administrador exclua cada tipo de dados pessoais em cada um dos tipos de recursos:

|Recursos que contêm dados pessoais|Acesso ao site|Acesso ao PowerShell|Exclusão automatizada|
|-----|----|----|----|
|Logs gerados pelo sistema|[Portal de confiança do serviço do Office 365](https://servicetrust.microsoft.com/)|||
|Ambiente|Centro de administração do Microsoft Flow|Cmdlets do PowerApps||
|Permissões de ambiente *|Centro de administração do Microsoft Flow|Cmdlets do PowerApps||
|Histórico de execuções||| Excluído por meio da política de retenção de 28 dias|
|Feed de atividades |||Excluído por meio da política de retenção de 28 dias|
|Trabalhos do usuário|| ||
|Fluxo|Portal do Microsoft Flow Maker * *|||
|Permissões de fluxo|Portal do Microsoft Flow Maker|||
|Detalhes do usuário||Cmdlets do PowerApps||
|Conexões|Portal do Microsoft Flow Maker| ||
|Permissões de conexão|Portal do Microsoft Flow Maker| ||
|Conector personalizado|Portal do Microsoft Flow Maker| ||
|Permissões de conector personalizado|Portal do Microsoft Flow Maker| ||
|Histórico de aprovação|Portal do Microsoft PowerApps Maker *|||

\* Com a introdução do Common Data Service, se um banco de dados for criado dentro do ambiente, as permissões de ambiente e as permissões de aplicativo controladas por modelos serão armazenadas como registros dentro da instância de banco de dados Common Data Service. Consulte [executando o DSRs em relação aos dados do cliente Common Data Service](https://go.microsoft.com/fwlink/?linkid=872251), para obter orientação sobre como responder a DSRs para usuários que usam o Common Data Service.

\*\* um administrador só poderá acessar esses recursos no portal do Microsoft Flow Maker se o administrador tiver recebido acesso do centro de administração do Microsoft Flow.

## <a name="manage-delete-requests"></a>Gerenciar solicitações de exclusão

As etapas a seguir descrevem como as funções administrativas existem para atender a solicitações de exclusão para GDPR. Essas etapas devem ser executadas na ordem descrita abaixo.

> [!IMPORTANT]
> Para evitar a corrupção de dados, siga estas etapas na ordem.
>
>

## <a name="list-and-re-assign-flows"></a>Listar e reatribuir fluxos

Essas etapas copiam os fluxos existentes para um usuário que está departendo. Se você atribuir uma nova propriedade às cópias, esses fluxos poderão continuar a oferecer suporte aos processos de negócios existentes. A cópia desses fluxos é importante para excluir ligações de identificador pessoal para o usuário de desparting e novas conexões devem ser estabelecidas para que o fluxo se conecte com outras APIs e aplicativos SaaS.

1. Entre no [centro de administração do Microsoft Flow](https://admin.flow.microsoft.com/)e selecione o ambiente que contém os fluxos que o usuário excluído possui.

    ![Exibir ambientes](./media/gdpr-dsr-delete/view-environments.png)

1. Selecione **recursos**, > **fluxos**e, em seguida, selecione o título para o fluxo que você deseja reatribuir.

    ![Exibir fluxos](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Selecione **gerenciar compartilhamento**.

    ![Gerenciar compartilhamento](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. No painel de **compartilhamento** que aparece próximo à borda direita, adicione você mesmo como um proprietário e, em seguida, selecione **salvar**.

    ![Fluxo de compartilhamento](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Entre [Microsoft Flow](https://flow.microsoft.com/), selecione **meus fluxos**e, em seguida, selecione **fluxos de equipe**.

1. Selecione as reticências **(...)** para o fluxo que você deseja copiar e, em seguida, selecione **salvar como**.

    ![Fluxo salvar como](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configure as conexões conforme necessário e, em seguida, selecione **continuar**.

1. Forneça um novo nome e, em seguida, selecione **salvar**.

    ![Criar cópia do fluxo](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Essa nova versão do fluxo aparece em **meus fluxos**, onde você pode compartilhá-lo com usuários adicionais, se desejar.

    ![Fluxos de equipe](./media/gdpr-dsr-delete/team-flows.png)

1. Exclua o fluxo original selecionando as reticências **(...)** para ele, selecionando **excluir**e, em seguida, selecione **excluir** novamente quando solicitado. Esta etapa também removerá os identificadores pessoais subjacentes incluídos nas dependências do sistema entre o usuário e o Microsoft Flow.

    ![Excluir confirmação de fluxo](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Habilite a cópia do fluxo, abrindo **meus fluxos** e, em seguida, ativando o **controle de alternância.**

    ![Habilitar fluxo](./media/gdpr-dsr-delete/toggle-on.png)

1. A cópia agora executa a mesma lógica de fluxo de trabalho que a versão original.

## <a name="delete-approval-history-from-microsoft-flow"></a>Excluir Histórico de aprovação de Microsoft Flow

 Os dados de aprovação para Microsoft Flow são armazenados na versão atual ou anterior do Common Data Service. Em uma aprovação, as informações pessoais existem na forma de atribuições de aprovação e comentários incluídos em uma resposta de aprovação. Os administradores podem acessar esses dados seguindo estas etapas:

1. Entre no [PowerApps](https://web.powerapps.com/).

1. Selecione **dados**e, em seguida, selecione **entidades**.

1. Selecione as reticências **(...)** para a entidade **aprovação de fluxo** e, em seguida, abra os dados no Microsoft Excel.

1. No Microsoft Excel, pesquise, filtre e exclua os dados de aprovação conforme necessário.

Consulte [executando o DSRs em relação aos dados do cliente Common Data Service](https://go.microsoft.com/fwlink/?linkid=872251), para obter diretrizes adicionais sobre como responder a DSRs para usuários que usam o Common Data Service.


## <a name="delete-connections-created-by-a-user"></a>Excluir conexões criadas por um usuário

As conexões são usadas em conjunto com conectores para estabelecer conectividade com outras APIs e sistemas SaaS.  As conexões incluem referências ao usuário que as criou e, como resultado, podem ser excluídas para remover todas as referências ao usuário.

Cmdlets do PowerShell do PowerApps Maker

Um usuário pode excluir todas as suas conexões usando a função remove-Connection dos [cmdlets do PowerShell do PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

Cmdlets do PowerShell de administrador do PowerApps

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>Excluir as permissões do usuário para conexões compartilhadas

Cmdlets do PowerShell do PowerApps Maker

Um usuário pode excluir todas as atribuições de função de conexão para conexões compartilhadas, remova a função ConnectionRoleAssignment nos [cmdlets do PowerShell do PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

Cmdlets do PowerShell de administrador do PowerApps

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> As atribuições de função do proprietário não podem ser excluídas sem excluir o recurso de conexão.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Excluir conectores personalizados criados pelo usuário

Os conectores personalizados complementam os conectores existentes prontos para uso e permitem a conectividade com outras APIs, SaaS e sistemas de desenvolvimento personalizado. Os conectores personalizados incluem referências ao usuário que os criou e, como resultado, podem ser excluídos para remover todas as referências ao usuário.

Cmdlets do PowerShell do PowerApps Maker

Um usuário pode excluir todos os conectores personalizados da função remove-Connector nos [cmdlets do PowerShell do PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Cmdlets do PowerShell de administrador do PowerApps
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Excluir as permissões do usuário para conectores personalizados compartilhados

Cmdlets do PowerShell do PowerApps Maker

Um usuário pode excluir todas as atribuições de função de conector para o conector personalizado compartilhado com a função remove-ConnectorRoleAssignment nos [cmdlets do PowerShell do PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

Cmdlets do PowerShell de administrador do PowerApps
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> As atribuições de função do proprietário não podem ser excluídas sem excluir o recurso de conexão.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Excluir ou reatribuir todos os ambientes criados pelo usuário

Como administrador, você tem duas decisões a serem tomadas ao processar uma solicitação de exclusão de DSR para um usuário para cada um dos ambientes que foram criados pelo usuário:

1. Se você determinar que o ambiente não está sendo usado por mais ninguém em sua organização, você poderá optar por excluir o ambiente
1. Se você determinar que o ambiente ainda é necessário, poderá optar por não excluir o ambiente e adicionar a si mesmo (ou a outro usuário em sua organização) como um administrador de ambiente.
> [!IMPORTANT]
> A exclusão de um ambiente excluirá permanentemente todos os recursos no ambiente, incluindo todos os aplicativos, fluxos, conexões, etc., portanto, examine o conteúdo de um ambiente antes da exclusão.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Conceder acesso a ambientes de um usuário no centro de administração Microsoft Flow

Um administrador pode conceder acesso de administrador a um ambiente criado por um usuário específico do [centro de administração Microsoft Flow](https://admin.flow.microsoft.com/). Para obter mais informações sobre como administrar ambientes, navegue até [usando ambientes dentro de Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Excluir as permissões do usuário para todos os outros ambientes

Os usuários podem receber permissões (como administrador do ambiente, criador do ambiente, etc.) em um ambiente, que é armazenado no serviço de Microsoft Flow como uma "atribuição de função".

Com a introdução do Common Data Service, se um banco de dados for criado dentro do ambiente, essas "atribuições de função" serão armazenadas como registros dentro da instância do banco de dados Common Data Service.

Para obter mais informações sobre como remover a permissão de um usuário em um ambiente, navegue até [usando ambientes dentro de Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-gateway-settings"></a>Excluir configurações de gateway

Responder a solicitações de exclusão de entidades de dados para gateways de dados locais pode ser encontrado [aqui](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Excluir detalhes do usuário

Os detalhes do usuário fornecem uma ligação entre um usuário e um locatário específico. Antes de executar esse comando, verifique se todos os fluxos deste usuário foram atribuídos novamente e/ou excluídos. Depois de concluído, um administrador pode excluir detalhes do usuário chamando o cmdlet **Remove-AdminFlowUserDetails** e passando a ID de objeto para o usuário.

Cmdlets do PowerShell de administrador do PowerApps
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Se um usuário ainda possuir fluxos individuais ou de equipe, esse comando retornará um erro. Para resolver, exclua todos os fluxos restantes ou fluxos de equipe para este usuário e execute o comando novamente.
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>Excluir o usuário do Azure Active Directory

Depois que as etapas acima forem concluídas, a etapa final será excluir a conta do usuário para Azure Active Directory seguindo as etapas descritas na documentação da solicitação de entidade de dados do Azure GDPR que podem ser encontradas no [portal de confiança do serviço do Office 365](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="delete-the-user-from-unmanaged-tenant"></a>Excluir o usuário do locatário não gerenciado

Caso você seja membro de um locatário não gerenciado, precisará executar uma ação de fechamento de **conta** do [portal de privacidade corporativo e de estudante](https://go.microsoft.com/fwlink/?linkid=873123).

Para determinar se você é um usuário de um locatário gerenciado ou não gerenciado, execute as seguintes ações:

1. Abra a seguinte URL em um navegador, substituindo seu endereço de email na URL:[https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Se você for um membro de um **locatário não gerenciado** , verá um `"IsViral": true` na resposta.

    {

     "Logon": "foobar@unmanagedcontoso.com",

    "Nome_do_domínio": "unmanagedcontoso.com",

    "Isviral": **true**,
    
    }

1. Caso contrário, você pertence a um locatário gerenciado.
