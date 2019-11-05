---
title: Trabalhar com fluxos de processos de negócios usando código | MicrosoftDocs
description: Saiba como trabalhar programaticamente com fluxos de processos empresariais para criar processos de negócios mais eficientes e simplificados.
ms.custom: ''
ms.date: 07/09/2018
ms.reviewer: ''
ms.service: flow
ms.topic: article
ms.assetid: 67d8cf80-9f77-4804-97a1-cf9f61417e83
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 5ce11084cb9a430899fd0a4b672e009c0dc22d25
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547741"
---
# <a name="work-with-business-process-flows-using-code"></a>Trabalhar com fluxos de processos de negócios usando código
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Um *fluxo de processo de negócios* permite que você crie processos de negócios, serviços e outras vendas mais eficientes e simplificados. Ele cria uma visualização de seu processo de negócios, colocando controles especiais na parte superior dos formulários de entidade. Os usuários são guiados por meio de vários estágios de vendas, marketing ou processos de serviço para a conclusão. Cada processo dá suporte a vários estágios e etapas. Você pode adicionar ou remover etapas, alterar a ordem dos estágios ou adicionar novas entidades ao fluxo do processo de negócios.  
  
Diferentes instâncias de fluxo de processo de negócios podem ser executadas simultaneamente no mesmo registro de entidade. Os usuários podem alternar entre instâncias de processos de negócios simultâneas e retomar seu trabalho em um estágio atual no processo. 

Este tópico fornece informações sobre como você pode trabalhar programaticamente com fluxos de processo de negócios.

> [!NOTE]
> Você não precisa escrever código para trabalhar com fluxos de processo de negócios. Para obter informações sobre como usar a interface do usuário para criar e gerenciar fluxos de processos comerciais, consulte [visão geral de fluxos de processos de negócios](../business-process-flows-overview.md)  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Pré-requisitos para o fluxo de processos de negócios 

Entidades personalizadas e entidades que atualizaram formulários de interface do usuário podem participar do fluxo do processo de negócios. As entidades de interface do usuário atualizadas têm a propriedade <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> definida como `true`. 

Para habilitar uma entidade para o fluxo do processo de negócios, defina a propriedade <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> como `true`.

> [!IMPORTANT]
>  Habilitar uma entidade para fluxo de processo empresarial é um processo unidirecional. Você não pode revertê-lo.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Definir o fluxo do processo de negócios
  
Use o Visual Business Process Flow designer para definir um fluxo de processo de negócios. Mais informações: [criar um fluxo de processo de negócios](../create-business-process-flow.md)

Por padrão, um registro de fluxo do processo de negócios é criado no estado `Draft`.  

Uma definição de fluxo de processo de negócios é armazenada na entidade <xref:Microsoft.Dynamics.CRM.workflow> e as informações de estágio para o fluxo do processo comercial são armazenadas na entidade <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Ativar o fluxo do processo de negócios  
 Antes de poder usar o fluxo do processo, você precisa ativá-lo. Para ativá-lo, você deve ter o privilégio de `prvActivateBusinessProcessFlow` para a entidade `Workflow`. Use a mensagem <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> para definir o estado do registro de entidade `Workflow` como `Activated`. Mais informações: [executar operações especializadas usando a atualização](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > Você também pode usar o designer de fluxo de processo de negócios para ativar um fluxo de processo de negócios. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entidade de fluxo do processo de negócios 
 Depois de ativar uma definição de fluxo de processo de negócios alterando o estado do registro de entidade `Workflow` correspondente ou usando o designer de fluxo de processo de negócios, uma entidade personalizada com o seguinte nome é criada automaticamente para armazenar os negócios ativados instâncias de fluxo de processo: " *\<activesolutionprefix >* _ *\<UniqueName >* ", em que o UniqueName é derivado do nome que você especificar.  
  
 Por exemplo, se você tiver especificado "meu BPF personalizado" como o nome da definição de fluxo de processo empresarial e estiver usando o Publicador padrão (novo) para sua solução ativa, o nome da entidade personalizada criada para armazenar instâncias de processo será "new_mycustombpf".  
  
 Se o valor de `uniquename` não estiver disponível para uma definição de fluxo de processo de negócios, por exemplo, se o fluxo do processo comercial foi importado como parte da solução de uma versão anterior, o nome padrão da entidade personalizada será "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`:  
  
> [!IMPORTANT]
>  Os registros de fluxo do processo de negócios de exemplo usam entidades do sistema para armazenar os registros correspondentes da instância do fluxo de processos de negócios.  
>   
>  No entanto, quaisquer novas definições de fluxo de processo de negócios criadas usarão entidades personalizadas para armazenar seus registros de instância, conforme explicado anteriormente. 

Você pode recuperar o nome da sua entidade de fluxo de processo de negócios usando qualquer uma das seguintes maneiras:

- **Usando a interface do usuário**: Use a interface do usuário de personalização para navegar até sua entidade de fluxo do processo de negócios:

    ![](media/bpf-entity-name.png)
- **Usando a API Web**: Use a seguinte solicitação:

    **Quest**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Responde**
    ```
    {  
    "@odata.context":"[Organization URI]/api/data/v9.0/$metadata#workflows(uniquename)",
    "value":[  
         {  
             "@odata.etag":"W/\"1084677\"",
             "uniquename":"new_mycustombpf",
             "workflowid":"2669927e-8ad6-4f95-8a9a-f1008af6956f"
         }
      ]
    }
    ```
- **Usando o serviço da organização**: Use o exemplo de código a seguir:

    ```c#
    QueryExpression query = new QueryExpression
    {
        EntityName = "workflow",
        ColumnSet = new ColumnSet("uniquename"),
        Criteria = new FilterExpression
        {
            Conditions =
            {
                new ConditionExpression
                {
                    AttributeName = "name",
                    Operator = ConditionOperator.Equal,
                    Values = { "My Custom BPF" }
                }
            }
        }
    };
    Workflow Bpf = (Workflow)_serviceProxy.RetrieveMultiple(query).Entities[0]; 
    ```
> [!NOTE]
> A propriedade <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> é `true` para entidades de fluxo de processo de negócios. Você pode recuperar todas as entidades de fluxo do processo de negócios em sua instância executando a seguinte solicitação de API Web:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Gerenciar a segurança para fluxos de processos de negócios

A entidade personalizada criada automaticamente na ativação de um fluxo de processo de negócios para armazenar instâncias de fluxo de processo de negócios segue o modelo de segurança padrão para qualquer outra entidade personalizada no Common Data Service. Isso implica que os privilégios concedidos nessas entidades definem as permissões de tempo de execução para os fluxos de processo de negócios para os usuários.

A entidade personalizada do fluxo do processo de negócios tem o escopo da organização. Os privilégios regular criar, recuperar, atualizar e excluir nessa entidade definem a permissão que os usuários teriam com base em suas funções atribuídas. Por padrão, quando a entidade personalizada de fluxo do processo de negócios é criada, somente as funções de segurança **administrador do sistema** e personalizador do **sistema** recebem acesso a ela e você deve conceder permissões explicitamente à nova entidade de fluxo de processo comercial (para exemplo, **meu BPF personalizado**) para outras funções de segurança, conforme necessário.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Criar, recuperar, atualizar e excluir registros de entidade de fluxo de processo de negócios (instâncias de processo)  
 A entidade personalizada criada automaticamente na ativação de uma definição de fluxo de processo de negócios armazena todas as instâncias de processo para a definição de fluxo do processo de negócios. A entidade personalizada dá suporte à criação programática padrão e ao gerenciamento de registros (instâncias de processo) usando a API da Web e o ponto de extremidade do CRM 2011.

> [!IMPORTANT]
> A alternância para outra instância de processo para um registro de entidade só tem suporte por meio da interface do usuário (cliente) ou programaticamente usando as informações disponíveis nesta seção. Você não pode mais usar a mensagem de `SetProcess` (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> ou <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) para alternar processos programaticamente (definir outro fluxo de processo empresarial como a instância de processo ativa) para o registro de entidade de destino. 

 Vamos considerar o exemplo a seguir em que temos um fluxo de processo empresarial de entidade cruzada, "meu BPF personalizado", com 3 estágios: S1: account, S2: Account e S3: contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Recuperar todos os registros (instâncias) de uma entidade de fluxo de processo de negócios
 Se o nome da sua entidade de fluxo de processo de negócios for "new_mycustombpf", use a seguinte consulta para recuperar todos os registros (instâncias de processo) para sua entidade de fluxo de processo de negócios:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

Neste ponto, você não poderá obter nenhuma instância em sua resposta, pois não há nenhuma. Execute essa solicitação depois de criar uma instância de sua definição de fluxo de processo de negócios posteriormente neste tópico.

> [!NOTE]
> Para saber como recuperar o nome da sua entidade de fluxo de processo de negócios, consulte a seção anterior, [entidade de fluxo de processo de negócios](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Criar um registro de entidade do fluxo de processo de negócios (instância do processo) 

Crie um registro de entidade de fluxo de processo de negócios (instância de processo) programaticamente se você quiser alternar para outro fluxo de processo de negócios para um registro de entidade sem usar a interface do usuário. 

Para criar um registro de entidade de fluxo de processo de negócios, você precisa especificar os seguintes valores: 
- Associe o registro de entidade do fluxo do processo de negócios a um registro de entidade principal definindo a propriedade de navegação de valor único usando a anotação `@odata.bind`. Para descobrir o nome da propriedade de navegação que aponta para o registro de entidade principal para sua definição de fluxo de processo de negócios, use o [documento CSDL $Metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Associe o registro de entidade do fluxo do processo de negócios a um estágio válido especificado na definição de fluxo do processo de negócios definindo a propriedade de navegação de valor único usando a anotação `@odata.bind`. Para descobrir o nome da propriedade de navegação (normalmente `activestageid`) que aponta para o registro de estágio para sua definição de fluxo de processo de negócios, use o [documento CSDL $Metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    Além disso, você pode recuperar informações sobre todos os estágios de uma definição de fluxo de processo de negócios usando a seguinte solicitação de API Web, supondo que a ID da definição de fluxo do processo de negócios seja 2669927e-8ad6-4f95-8a9a-f1008af6956f:

    **Quest**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Responde**

    ```http
    {
        "@odata.context": "[Organization URI]/api/data/v9.0/$metadata#processstages(stagename)",
        "value": [
            {
                "@odata.etag": "W/\"858240\"",
                "stagename": "S1",
                "processstageid": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b"
            },
            {
                "@odata.etag": "W/\"858239\"",
                "stagename": "S3",
                "processstageid": "a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a"
            },
            {
                "@odata.etag": "W/\"858238\"",
                "stagename": "S2",
                "processstageid": "19a11fc0-3398-4214-8522-cb2a97f66e4b"
            }
        ]
    }
    ```

Em seguida, use a seguinte solicitação para criar uma instância de sua definição de fluxo do processo de negócios para um registro de conta (ID = a176be9e-9a68-e711-80e7-00155d41e206) e o estágio ativo definido como o primeiro estágio da instância do processo, S1 (ID = 9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**Quest**

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(a176be9e-9a68-e711-80e7-00155d41e206)",
    "activestageid@odata.bind": "/processstages(9a9185f5-b75b-4bbb-9c2b-a6626683b99b)"    
}
```

**Responde**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Observe que, se você quiser criar uma instância de sua definição de fluxo de processo de negócios com o estágio ativo definido como um estágio ***diferente*** do primeiro estágio, você também deverá fornecer `traversedpath` em sua solicitação. O caminho percorrido é a cadeia de caracteres delimitada por vírgulas de IDs de estágio do processo que representam os estágios visitados da instância do fluxo do processo de negócios. A solicitação a seguir cria uma instância para um registro de conta (ID = 679b2464-71B5-e711-80f5-00155d513100) e o estágio ativo definido como o segundo estágio, S2 (ID = 19a11fc0-3398-4214-8522-cb2a97f66e4b).

```http
POST [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
Content-Type: application/json; charset=utf-8 
OData-MaxVersion: 4.0 
OData-Version: 4.0 
Accept: application/json 

{
    "bpf_accountid@odata.bind": "/accounts(679b2464-71b5-e711-80f5-00155d513100)",
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"   
}
```

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Atualizar um registro de entidade do fluxo de processo de negócios (instância do processo)

Você pode atualizar uma instância de processo para mover para o estágio seguinte ou anterior, abandonar uma instância de processo, reativar uma instância de processo ou concluir uma instância de processo. 

#### <a name="stage-navigation"></a>Navegação do estágio

Para navegar até um estágio diferente, você precisa atualizar um registro de instância de processo para alterar sua ID de estágio ativa e atualizar adequadamente o caminho atravessado. Observe que você deve mover para o estágio seguinte ou anterior durante a atualização de uma instância de fluxo de processo de negócios.

Para executar a navegação do estágio, você precisará da ID da instância do fluxo do processo de negócios que deseja atualizar. Para recuperar todas as instâncias do fluxo do processo de negócios, consulte [recuperar todos os registros (instâncias) para uma entidade de fluxo do processo de negócios](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) anteriormente.

Supondo que a ID da instância do processo que você deseja atualizar seja dc2ab599-306d-e811-80ff-00155d513100, use a seguinte solicitação para atualizar o estágio ativo de S1 para S2:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
Content-Type: application/json
OData-MaxVersion: 4.0
OData-Version: 4.0

{
    "activestageid@odata.bind": "/processstages(19a11fc0-3398-4214-8522-cb2a97f66e4b)",
    "traversedpath": "9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b"
}
```

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Alterar o estado de uma instância de processo: abortar, reativar ou concluir 

Uma instância de processo pode ter um dos seguintes Estados: **ativa**, **concluída**ou **anulada**. O estado é determinado pelos seguintes atributos no registro da instância do processo:

- **stateCode**: exibe o status da instância do processo.

    |valor|Chamada|
    |-----|-----|
    |0    |Activo|
    |uma    |Inativo|

- **StatusCode**: exibe informações sobre o status da instância do processo.

    |valor|Chamada|
    |-----|-----|
    |uma    |Activo|
    |2    |Finaliza|
    |Beta    |Anulada|

Portanto, para **anular** uma instância de processo, use a seguinte solicitação defina o `statecode` e `statuscode` valores adequadamente:

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{ 
    "statecode" : "1", 
    "statuscode": "3" 
}
```
 
> [!NOTE]
> Você pode anular uma instância de processo em qualquer estágio.

Da mesma forma, para reativar uma instância de processo, substitua os valores `statecode` e `statuscode` no código acima por **0** e **1** , respectivamente.

Por fim, para definir um status de instância de processo como **concluído**, o que só é possível no último estágio de uma instância de processo, substitua os valores `statecode` e `statuscode` no código acima por **0** e **2** , respectivamente.

#### <a name="cross-entity-navigation"></a>Navegação entre entidades

Para navegação entre entidades neste exemplo, você deve definir o estágio ativo da instância do processo para o último estágio, S3 (ID = a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), atualizar o caminho atravessado de acordo e definir um registro de contato como o registro de entidade principal, de acordo com o a definição de fluxo do processo de negócios.

```http
PATCH [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1   
Content-Type: application/json   
OData-MaxVersion: 4.0   
OData-Version: 4.0 
  
{
    "activestageid@odata.bind": "/processstages(a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a)",
    "traversedpath":"9a9185f5-b75b-4bbb-9c2b-a6626683b99b,19a11fc0-3398-4214-8522-cb2a97f66e4b,a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a",
    "bpf_contactid@odata.bind": "/contacts(0e3f10b0-da33-e811-80fc-00155d513100)"
}
``` 

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Excluir um registro de entidade do fluxo de processo de negócios (instância do processo)

Use a seguinte solicitação de API Web:

**Quest**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Responde**

Se o registro existir, você receberá uma resposta normal com o status 204 para indicar que a exclusão foi bem-sucedida. Se a entidade não for encontrada, você receberá uma resposta com o status 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Usar mensagens RetrieveProcessInstances e RetrieveActivePath

Use a mensagem de `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) para recuperar todas as instâncias de fluxo do processo de negócios para um registro de entidade entre todas as definições de processo de negócios. As instâncias de fluxo do processo de negócios retornadas para uma entidade são ordenadas com base no atributo `modifiedon` para a instância. Por exemplo, a instância de fluxo de processo de negócios modificada mais recentemente será o *primeiro* registro na coleção retornada. A instância de fluxo de processos de negócios modificada mais recentemente é aquela que está ativa na interface do usuário para um registro de entidade.  
  
Cada registro de instância de fluxo de processo de negócios retornado para um registro de entidade como resultado do uso da mensagem `RetrieveProcessInstances` armazena a ID do estágio ativo no atributo `processstageid` que pode ser usado para localizar o estágio ativo e, em seguida, mover para o estágio anterior ou próximo. Para fazer isso, primeiro você precisa localizar o caminho ativo de uma instância de fluxo de processo de negócios e os estágios disponíveis na instância do fluxo de processo usando a mensagem de `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Depois de ter o estágio ativo e as informações de caminho ativo para uma instância de fluxo de processo de negócios, você pode usar as informações para mover para um estágio anterior ou próximo no caminho ativo. A navegação progressiva de estágios deve ser feita em sequência, ou seja, você só deve avançar para o próximo estágio no caminho ativo.   
  
 Para obter o exemplo completo que o código demonstra o uso desses dois métodos e a navegação de estágio usando o [serviço da organização](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), consulte [exemplo: trabalhar com fluxos de processo de negócios](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Aplicar o fluxo do processo de negócios ao criar um registro de entidade

Esta seção fornece informações sobre o comportamento padrão para aplicar fluxos de processos comerciais automaticamente a novos registros de entidade criados em Common Data Service e como você pode substituí-lo para aplicar um fluxo de processo de negócios de sua escolha para novos registros de entidade.

Por padrão, para uma entidade que tem vários fluxos de processo de negócios definidos para ele, o sistema aplica um fluxo de processo de negócios ao novo registro de entidade usando a seguinte lógica de várias etapas:
1. Identifique todos os fluxos de processos de negócios aplicáveis ao novo registro de entidade com base no atributo **Workflow. PrimaryEntity** dos registros de definição de fluxo do processo de negócios.
2. Identifique as definições de fluxo do processo de negócios às quais o usuário atual tem acesso. Para obter informações sobre como o acesso a um fluxo de processo de negócios é determinado e gerenciado, consulte [gerenciar a segurança para fluxos de processo de negócios](#BPFSecurity) anteriormente neste tópico.<br/>  
3. Todas as definições de fluxo de processo de negócios no sistema estão sujeitas a uma ordem global por entidade. A ordem do fluxo do processo de negócios é armazenada no atributo **Workflow. ProcessOrder** . As definições de fluxo do processo de negócios para uma entidade são classificadas com base nessa ordem e a que com o valor de ordem mínimo é selecionada.
4. Por fim, se o registro de entidade for criado a partir de um aplicativo de negócios (módulo de aplicativo), mais um nível de filtragem será aplicado para escolher o fluxo do processo de negócios a ser aplicado automaticamente ao novo registro de entidade. Ao trabalhar em um aplicativo, os usuários podem acessar somente entidades relevantes, fluxos de processos comerciais, exibições e formulários aos quais eles têm acesso em virtude das funções de segurança atribuídas ao aplicativo de negócios. 
    - Se o aplicativo de negócios não contiver nenhum fluxo de processo de negócios, o fluxo do processo de negócios será aplicado conforme explicado até a etapa 3.
    - Se o aplicativo de negócios tiver um ou mais fluxos de processo de negócios, somente os fluxos de processo de negócios presentes no aplicativo seriam aplicáveis. Nesse caso, quando o usuário está trabalhando em um contexto de aplicativo de negócios, a lista de fluxos de processo de negócios da etapa 3 é filtrada ainda mais para aqueles que fazem parte do aplicativo de negócios que estão presentes dentro do módulo de aplicativo e são classificados com base na ordem de processo. 
    - Se nenhum fluxo de processo comercial estiver disponível em um aplicativo de negócios para a entidade ou com o qual o usuário tem acesso, nenhum fluxo de processo comercial será aplicado ao novo registro de entidade.

Você pode substituir a lógica padrão dos fluxos do processo de negócios sendo aplicada automaticamente a novos registros de entidade. Para fazer isso, defina o atributo **ProcessId** da entidade como um dos seguintes valores ao criar um novo registro de entidade:
- Defina como **GUID. Empty** para ignorar a configuração de um fluxo de processo comercial para novos registros de entidade. Talvez você queira fazer isso se estiver criando registros de entidade em massa, mas não quiser que o fluxo do processo de negócios seja aplicado a eles.
- Defina-o como uma entidade de fluxo de processo de negócios específica (como uma referência de entidade). Nesse caso, o sistema aplicará o fluxo do processo comercial especificado em vez da lógica padrão.

Se você não definir um valor para o atributo **ProcessId** durante a criação de um novo registro de entidade, o sistema aplicará a lógica padrão conforme explicado anteriormente.

> [!NOTE]
> Substituir a lógica padrão dos fluxos do processo de negócios sendo aplicado automaticamente a novos registros de entidade tem suporte apenas por meio de programação. Você não pode fazer isso usando a interface do usuário.

## <a name="legacy-process-related-attributes-in-entities"></a>Atributos relacionados ao processo herdado em entidades

Os atributos herdados relacionados ao processo (como **ProcessId**, **stageid**e **TraversedPath**) em entidades habilitadas para fluxos de processo comercial já estão preteridos. Manipular esses atributos relacionados ao processo herdado para registros de entidade de destino não garante a consistência do estado de fluxo do processo de negócios e ***não*** é um cenário com suporte. A maneira recomendada é usar os atributos da entidade de fluxo do processo de negócios, conforme explicado anteriormente na seção [criar, recuperar, atualizar e excluir registros de entidade do fluxo de processo de negócios (instâncias de processo)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances)

A única exceção a isso é modificar programaticamente o atributo **ProcessId** ao criar um registro de entidade para substituir o aplicativo padrão do fluxo do processo de negócios para o novo registro, conforme explicado na seção anterior: [aplicar negócios fluxo do processo ao criar um registro de entidade](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Suporte à programação no lado do cliente para fluxos de processo de negócios  
 Há um objeto do lado do cliente que você pode usar para interagir com fluxos de processo de negócios em seus scripts de formulário. Os fluxos de processos de negócios acionam eventos do lado do cliente sempre que um processo é aplicado a um registro, o estágio é alterado ou seu status é alterado para `Active`, `Finished`ou `Aborted`. Mais informações: [formContext. Data. Process (referência de API de cliente)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de processos, estágios e etapas  
 Por entidade, o valor padrão para o número máximo de fluxos de processo de negócios ativados é 10. Você pode especificar um valor diferente usando o atributo `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. No entanto, se o valor for maior que 10, você poderá ver uma diminuição no desempenho do sistema ao alternar processos ou abrir um registro que tenha um fluxo de processo comercial atribuído. Isso pode ser especialmente perceptível se os processos abrangerem várias entidades.  
  
 As configurações a seguir não são personalizáveis:  
  
-   O número máximo de estágios por entidade no processo é 30.  
  
-   O número máximo de etapas em cada estágio é 30.  
  
-   O número máximo de entidades que podem participar do fluxo do processo é 5.  

