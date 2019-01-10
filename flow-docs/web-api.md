# <a name="microsoft-flow-web-api"></a>API Web do Microsoft Flow

Agora todos os fluxos serão armazenados no Common Data Service (CDS) para Aplicativos e aproveite [a API Web avançada](https://docs.microsoft.com/dynamics365/customer-engagement/developer/webapi/perform-operations-web-api).

Este conteúdo aborda o gerenciamento de fluxos incluídos na guia **Soluções** no Microsoft Flow. Atualmente, fluxos sob **Meus fluxos** não são compatíveis com essas APIs.

## <a name="compose-http-requests"></a>Compor solicitações HTTP

Para começar a criação de solicitações, construa a URL primeiro. O formato para a URL base da API Web do Microsoft Flow é: `https://{Organization ID}.{Regional Subdomain}.dynamics.com/api/data/v9.1/`. Os dois parâmetros são:

- A **ID da organização** é um nome exclusivo para o ambiente que armazena seus fluxos. Você pode ver a ID da organização no seletor de ambiente na parte superior direita do Microsoft Flow. Observe que a **ID da organização** é diferente da **ID do ambiente** (que é o GUID que aparece na URL do fluxo).

     ![Seletor de ambiente](media/web-api/get-organization-id.png "Seletor de ambiente")

- O **Subdomínio Regional** depende do local do seu ambiente. Quando entra no Microsoft Flow, você pode ver a região do seu ambiente na URL da página da Web. Use esse nome de região para localizar o respectivo subdomínio na tabela a seguir:

     ![URL de fluxo](media/web-api/get-region-name.png "URL de fluxo")

     | Região         | Subdomínio   |
     | -------------- | ----------- |
     | Estados Unidos  | crm         |
     | América do Sul  | crm2        |
     | Canadá         | crm3        |
     | Europa         | crm4        |
     | Pacífico Asiático   | crm5        |
     | Austrália      | crm6        |
     | Japão          | crm7        |
     | Índia          | crm8        |
     | US Government  | crm9        |
     | Reino Unido | crm11       |

Também é possível programaticamente obter a lista de instâncias disponíveis para você por meio do método [Obter Instâncias](https://docs.microsoft.com/rest/api/admin.services.crm.dynamics.com/instances/getinstances) na API de gerenciamento Online.

Cada solicitação para a API Web deve ter os cabeçalhos `Accept` e `Content-type` definidos em `application/json`.

Por fim, preencha o cabeçalho `Authorization` com um token de Portador Azure AD. Você pode [aprender](https://docs.microsoft.com/dynamics365/customer-engagement/developer/authenticate-users) como adquirir um token de Portador Azure AD para o CDS para Aplicativos. Por exemplo, esta solicitação:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
```

A resposta contém a lista de fluxos de dentro desse ambiente:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#workflows",
    "value": [{
        "@odata.etag": "W/\"12116760\"",
        "category": 5,
        "statecode": 0,
        "workflowidunique": "00000000-0000-0000-0000-000000000001",
        "workflowid" : "00000000-0000-0000-0000-000000000002",
        "createdon": "2018-11-15T19:45:51Z",
        "_ownerid_value": "00000000-0000-0000-0000-000000000003",
        "modifiedon": "2018-11-15T19:45:51Z",
        "ismanaged": false,
        "name": "Sample flow",
        "_modifiedby_value": "00000000-0000-0000-0000-000000000003",
        "_createdby_value": "00000000-0000-0000-0000-000000000003",
        "type": 1,
        "description": "This flow updates some data in CDS for Apps.",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"source\":\"NotSpecified\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\",\"tier\":\"NotSpecified\"}},\"definition\":{...}},\"schemaVersion\":\"1.0.0.0\"}"
    }]
}
```

## <a name="list-flows"></a>Lista de fluxos

Como mostrado acima, você pode obter a lista de fluxos de trabalho chamando `GET` em `workflows`. Cada fluxo de trabalho tem várias propriedades, mas as mais relevantes são:

| Nome da propriedade     | Descrição                                              |
| ----------------- | -------------------------------------------------------- |
| categoria          | A categoria do fluxo. Os diferentes tipos são: 0 – CDS clássico para fluxos de trabalho de aplicativos, 1 – CDS clássico para caixas de diálogo de aplicativos, 2 – regras de negócios, 3 – CDS clássico para ações de aplicativos, 4 – fluxos de processo de negócios e 5 – fluxos automatizados, instantâneos ou agendados. |
| statecode         | O status do fluxo. O status pode ser **0** – desativado ou **1** – ativado.|
| workflowuniqueid  | O identificador exclusivo para esta instalação do fluxo. |
| workflowid        | O identificador exclusivo para um fluxo em todas as importações. |
| createdon         | A data em que o fluxo foi criado. |
| _ownerid_value    | O identificador exclusivo do usuário ou equipe proprietários do fluxo. Essa é uma ID da entidade systemusers no CDS para Aplicativos. |
| ModifiedOn        | A última vez que a tarefa foi atualizada. |
| ismanaged         | Indica se o fluxo foi instalado por meio de uma solução gerenciada. |
| Nome              | O nome de exibição que você deu ao fluxo. |
| _modifiedby_value | O último usuário que atualizou o fluxo. Essa é uma ID da entidade systemusers no CDS para Aplicativos. |
| _createdby_value  | O usuário que criou o fluxo. Essa é uma ID da entidade systemusers no CDS para Aplicativos. |
| tipo              | Indica se o fluxo é um fluxo de execução ou um modelo que pode ser usado para criar fluxos adicionais. 1 – fluxo, 2 – ativação ou 3 – modelo. |
| descrição       | A descrição do fluxo fornecida pelo usuário. |
| clientdata        | Uma cadeia de caracteres codificada JSON de um objeto que contém o connectionReferences e a definição do fluxo. |

Você também pode solicitar propriedades específicas, filtrar a lista de fluxos e muito mais, conforme descrito em [CDS para a documentação de aplicativos de API para consultar dados](https://docs.microsoft.com/dynamics365/customer-engagement/developer/webapi/query-data-web-api). Por exemplo, essa consulta retorna apenas os fluxos automatizados, instantâneos ou agendados que estão atualmente em:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows?$filter=category eq 5 and statecode eq 1
Accept: application/json
Authorization: Bearer ey...
```

## <a name="create-a-flow"></a>Crie um fluxo

Chame `POST` na coleção `workflows` para criar um fluxo. As propriedades necessárias para fluxos automatizados, instantâneos e agendados são: categoria, nome, tipo, primaryentity e clientdata. Use `none` para o primaryentity para esses tipos de fluxos.

Você também pode fornecer uma descrição e um statecode.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
        "category": 5,
        "statecode": 0,
        "name": "Sample flow name",
        "type": 1,
        "description": "This flow reads some data from CDS for Apps.",
        "primaryentity":"none",
        "clientdata": "{\"properties\":{\"connectionReferences\":{\"shared_commondataservice\":{\"connectionName\":\"shared-commondataser-00000000-0000-0000-0000-000000000004\",\"source\":\"Invoker\",\"id\":\"/providers/Microsoft.PowerApps/apis/shared_commondataservice\"}},\"definition\":{\"$schema\": \"https:\/\/schema.management.azure.com\/providers\/Microsoft.Logic\/schemas\/2016-06-01\/workflowdefinition.json#\",\"contentVersion\": \"1.0.0.0\",\"parameters\": {\"$connections\": {\"defaultValue\": {},\"type\": \"Object\"},\"$authentication\": {\"defaultValue\": {},\"type\": \"SecureObject\"}},\"triggers\": {\"Recurrence\": {\"recurrence\": {\"frequency\": \"Minute\",\"interval\": 1},\"type\": \"Recurrence\"}},\"actions\": {\"List_records\": {\"runAfter\": {},\"metadata\": {\"flowSystemMetadata\": {\"swaggerOperationId\": \"GetItems_V2\"}},\"type\": \"ApiConnection\",\"inputs\": {\"host\": {\"api\": {\"runtimeUrl\": \"https:\/\/firstrelease-001.azure-apim.net\/apim\/commondataservice\"},\"connection\": {\"name\": \"@parameters('$connections')['shared_commondataservice']['connectionId']\"}},\"method\": \"get\",\"path\": \"\/v2\/datasets\/@{encodeURIComponent(encodeURIComponent('default.cds'))}\/tables\/@{encodeURIComponent(encodeURIComponent('accounts'))}\/items\",\"queries\": {\"$top\": 1},\"authentication\": \"@parameters('$authentication')\"}}},\"outputs\": {}}},\"schemaVersion\":\"1.0.0.0\"}"
}
```

A seção mais importante é a `clientdata`, que contém o connectionReferences que o fluxo usa e a [definição](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language) do fluxo. Os connectionReferences são os mapeamentos para cada conexão que fluxo usa.

Há três propriedades:

| Nome da propriedade  | Descrição                                                 |
| -------------- | ----------------------------------------------------------- |
| connectionName | Identifica a conexão. Você pode ver o connectionName indo para a página **Conexões** e, em seguida, copiá-lo da URL da conexão. |
| fonte         | Tanto `Embedded` ou `Invoker`. `Invoker` só é válido para fluxos instantâneos (esses em que um usuário seleciona um botão para executar o fluxo) e indica que o usuário final fornecerá a conexão. Nesse caso, o connectionName só é usado no tempo de design. Se a conexão é `Embedded`, isso significa que sempre é usado o connectionName que você especifica. |
| id             | O identificador do conector. A ID sempre começa com `/providers/Microsoft.PowerApps/apis/` e, em seguida, tem o nome do conector, que você pode copiar da URL da conexão ou selecionando o conector da página **Conectores**. |

Depois de executar a solicitação `POST`, você receberá o cabeçalho `OData-EntityId`, que conterá o `workflowid` para seu novo fluxo.

## <a name="update-a-flow"></a>Atualize um fluxo

Você pode chamar `PATCH` no fluxo de trabalho para atualizar, ativar ou desativar um fluxo. Use a propriedade `workflowid` para fazer essas chamadas. Por exemplo, você pode atualizar a descrição e o proprietário do fluxo com a chamada a seguir:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "description" : "This flow will ensure consistency across systems.",
    "ownerid@odata.bind": "systemusers(00000000-0000-0000-0000-000000000005)",
}
```

> [!NOTE]
> A sintaxe para alterar o proprietário usa o formato `odata.bind`. Isso significa que, em vez de aplicar patch ao campo \_ownerid_value diretamente, você acrescenta `@odata.bind` ao nome da propriedade e, em seguida, encapsula a ID com `systemusers()`.

Em outro exemplo, você pode ativar um fluxo com esta chamada:

```http
PATCH https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "statecode" : 1
}
```

### <a name="delete-a-flow"></a>Excluir um fluxo

Excluir um fluxo com uma simples chamada `DELETE`:

```http
DELETE https://org00000000.crm0.dynamics.com/api/data/v9.1/workflows(00000000-0000-0000-0000-000000000002)
Accept: application/json
Authorization: Bearer ey...
```

> [!NOTE]
> Você não pode excluir um fluxo que está ativado. Você deve primeiro desativar o fluxo (veja antes **Atualização de um fluxo**) ou, caso contrário, você verá o erro: `Cannot delete an active workflow definition.`

## <a name="get-all-users-with-whom-a-flow-is-shared"></a>Obter todos os usuários com quem um fluxo é compartilhado

Listagem dos usuários com acesso usa uma *função* no CDS para Aplicativos. Essa função usa um único parâmetro de `Target`:

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/RetrieveSharedPrincipalsAndAccess(Target=@tid)?@tid={'@odata.id':'workflows(00000000-0000-0000-0000-000000000002)'}
Accept: application/json
Authorization: Bearer ey...
```

O parâmetro `Target` é uma cadeia de caracteres como JSON com uma única propriedade chamada `@odata.id`. Substitua a ID do fluxo de trabalho no exemplo acima. Isso retorna:

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.RetrieveSharedPrincipalsAndAccessResponse",
    "PrincipalAccesses": [
        {
            "AccessMask": "ReadAccess",
            "Principal": {
                "@odata.type": "#Microsoft.Dynamics.CRM.systemuser",
                "ownerid": "00000000-0000-0000-0000-000000000005"
            }
        }
    ]
}
```

## <a name="share-or-unshare-a-flow"></a>Compartilhar ou descompartilhar um fluxo

Você pode compartilhar um fluxo usando a ação `GrantAccess`.

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/GrantAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "PrincipalAccess": {
        "Principal": {
            "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
            "ownerid" : "00000000-0000-0000-0000-000000000005"
        },
        "AccessMask": "ReadAccess"
    }
}
```

O parâmetro `AccessMask` é um campo com os seguintes valores para diferentes níveis de permissão:

| Nome         | Descrição                                          |
| ------------ | ---------------------------------------------------- |
| Nenhum         | Sem acesso.                                           |
| ReadAccess   | O direito de ler o fluxo.                          |
| WriteAccess  | O direito de atualizar o fluxo.                        |
| DeleteAccess | O direito de excluir o fluxo.                        |
| ShareAccess  | O direito de compartilhar o fluxo.                         |
| AssignAccess | O direito de alterar o proprietário do fluxo.           |

Você pode combinar permissões com uma vírgula; por exemplo, fornecer a capacidade de ler e atualizar um fluxo, passando `ReadAccess,WriteAccess`.

Você pode *descompartilhar* um fluxo com a ação `RevokeAccess`. Veja um exemplo:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/RevokeAccess
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "Target" : {
        "@odata.type": "Microsoft.Dynamics.CRM.workflow",
        "workflowid" : "00000000-0000-0000-0000-000000000002"
    },
    "Revokee": {
        "@odata.type" : "Microsoft.Dynamics.CRM.systemuser",
        "ownerid" : "00000000-0000-0000-0000-000000000005"
    }
}
```

`RevokeAccess` Remove todas as permissões concedidas a `AccessMask`.

## <a name="export-flows"></a>Exportar fluxos

Use a ação `ExportSolution` para exportar fluxos para um arquivo .zip. Primeiro, adicione os fluxos que você deseja a uma [solução](https://flow.microsoft.com/blog/solutions-in-microsoft-flow/).

Depois que o fluxo está em uma solução, chame a ação a seguir:

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ExportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "SolutionName" : "Awesome solution 1",
    "Managed": false
}
```

`ExportSolution` retorna uma cadeia de caracteres codificada de base 64 na propriedade `ExportSoutionFile`.

```http
{
    "@odata.context": "https://org00000000.crm0.dynamics.com/api/data/v9.1/$metadata#Microsoft.Dynamics.CRM.ExportSolutionResponse",
    "ExportSolutionFile": "UEsDBBQAAgAI..."
}
```

Você pode, em seguida, salvar esse arquivo no controle de código-fonte e/ou usar qualquer gerenciamento de versão ou sistema de distribuição que você queira.

## <a name="import-flows"></a>Importe fluxos

Chame a ação `ImportSolution` para importar uma solução.

| Nome da propriedade                    | Descrição                               |
| -------------------------------- | ----------------------------------------- |
| OverwriteUnmanagedCustomizations | Se houver instâncias desses fluxos no CDS para Aplicativos, esse sinalizador precisa ser definido como `true` para importá-las. Caso contrário, elas não serão substituídas. |
| PublishWorkflows                 | Indica se CDS clássico para fluxos de trabalho de aplicativos será ativado durante a importação. Essa configuração não se aplica a outros tipos de fluxos. |
| ImportJobId                      | Fornece um GUID novo e exclusivo para acompanhar o trabalho de importação. |
| CustomizationFile                | Um arquivo zip codificado de base 64 que contém a solução. |

```http
POST https://org00000000.crm0.dynamics.com/api/data/v9.1/ImportSolution
Accept: application/json
Authorization: Bearer ey...
Content-type: application/json
{
    "OverwriteUnmanagedCustomizations": false,
    "PublishWorkflows" : true,
    "ImportJobId" : "00000000-0000-0000-0000-000000000006",
    "CustomizationFile" : "UEsDBBQAAgAI..."
}
```

Como importar é uma operação de longa execução, a resposta para a ação de ImportSolution será um `204 No content`. Para acompanhar o progresso, chame um `GET` no objeto `importjobs`, fornecendo ao `ImportJobId` que você incluiu na ação `ImportSolution` original.

```http
GET https://org00000000.crm0.dynamics.com/api/data/v9.1/importjobs(00000000-0000-0000-0000-000000000006)
Accept: application/json
Authorization: Bearer ey...
```

Essa chamada retorna o status da operação de importação, incluindo `progress` (a porcentagem de conclusão), `startedon`, e `completedon` (se a importação foi concluída).

Depois que a importação for concluída com êxito, você precisará configurar as conexões para o fluxo, já que os `connectionNames` provavelmente serão diferentes no ambiente de destino (se as conexões realmente existirem). Se você estiver configurando novas conexões no ambiente de destino, o proprietário dos fluxos deverá criá-los no designer do Microsoft Flow. Se as conexões já estão definidas no novo ambiente, você pode `PATCH` o `clientData` do fluxo com os nomes das conexões.
