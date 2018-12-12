---
title: Trabalhar com fluxos de processo empresarial usando código | Microsoft Docs
description: Saiba como trabalhar programaticamente com fluxos de processo empresarial para criar processos empresariais mais eficientes e otimizados.
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
ms.openlocfilehash: 1283d9d0a8e7f2b9b0495400c5db1f624ef91954
ms.sourcegitcommit: a505b0aac796960d57fccee92eb18c6566ac9c35
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2018
ms.locfileid: "53006991"
---
# <a name="work-with-business-process-flows-using-code"></a>Trabalhar com fluxos de processo empresarial usando código

Um *fluxo do processo empresarial* permite que você crie processos mais eficientes e otimizados de vendas, serviço e outros processos empresariais. Ele cria uma visualização de seu processo empresarial colocando controles especiais na parte superior dos formulários de entidade. Os usuários são guiados por vários estágios de vendas, marketing ou processos de serviço em direção à conclusão. Cada processo dá suporte a vários estágios e etapas. Você pode adicionar ou remover etapas, alterar a ordem dos estágios ou adicionar novas entidades ao fluxo do processo empresarial.  
  
As instâncias de fluxo de processo empresarial diferentes podem ser executadas simultaneamente no mesmo registro de entidade. Os usuários podem alternar entre as instâncias de processos empresariais simultâneas e retomar seu trabalho em um estágio atual no processo. 

Este tópico fornece informações sobre como você pode trabalhar, por meio de programação, com fluxos de processo empresarial.

> [!NOTE]
> Você não precisa escrever código para trabalhar com fluxos de processo empresarial. Para obter informações sobre como usar a interface do usuário para criar e gerenciar fluxos de processo empresarial, consulte [Visão geral de fluxos de processo empresarial](../business-process-flows-overview.md)  

<a name="PrereqsBPF"></a>   
## <a name="prerequisites-for-business-process-flow"></a>Pré-requisitos para o fluxo de processo empresarial 

Entidades personalizadas e entidades que tenham formulários de interface do usuário atualizados podem participar no fluxo do processo empresarial. As entidades de interface do usuário atualizadas têm a propriedade <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsAIRUpdated> definida como `true`. 

Para habilitar uma entidade para o fluxo do processo empresarial, defina a propriedade <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBusinessProcessEnabled> para `true`.

> [!IMPORTANT]
>  Habilitar uma entidade para o fluxo do processo empresarial é um processo unidirecional. Não é possível revertê-lo.

   
<a name="DefineBPF"></a>   
## <a name="define-business-process-flow"></a>Definir fluxo do processo empresarial
  
Use o designer de fluxo do processo empresarial visual para definir um fluxo de processo empresarial. Mais informações: [Criar um fluxo de processo empresarial](../create-business-process-flow.md)

Por padrão, um registro de fluxo do processo empresarial é criado no estado `Draft`.  

Uma definição de fluxo de processo empresarial é armazenada na entidade <xref:Microsoft.Dynamics.CRM.workflow> e as informações de estágio para o fluxo do processo empresarial são armazenadas na entidade <xref:Microsoft.Dynamics.CRM.processstage>.
  
<a name="ActivateBPF"></a>   
## <a name="activate-business-process-flow"></a>Ativar fluxo do processo empresarial  
 Antes de usar o fluxo do processo, você precisará ativá-lo. Para ativá-lo, você deve ter o privilégio `prvActivateBusinessProcessFlow` para a entidade `Workflow`. Use a mensagem <xref:Microsoft.Xrm.Sdk.Messages.UpdateRequest> para definir o estado do registro da entidade `Workflow` para `Activated`. Mais informações: [Executar operações especializadas usando Update](/dynamics365/customer-engagement/developer/org-service/perform-specialized-operations-using-update) 

 > [!NOTE]
 > Você também pode usar o designer de fluxo do processo empresarial para ativar um fluxo de processo empresarial. 

<a name="BPFEntity"></a>   
## <a name="business-process-flow-entity"></a>Entidade de fluxo de processo empresarial 
 Depois de ativar uma definição de fluxo de processo empresarial alterando o estado o registro de entidade `Workflow` correspondente ou usando o designer de fluxo do processo empresarial, uma entidade personalizada com o seguinte nome é criada automaticamente para armazenar as instâncias de fluxo de processo empresarial: "*\<activesolutionprefix>*_*\<uniquename>*", em que o nome exclusivo é derivado do nome que você especificar.  
  
 Por exemplo, se você especificou "Meu BPF personalizado" como o nome da definição de fluxo de processo empresarial e estiver usando o editor padrão (novo) para sua solução ativa, o nome da entidade personalizada criada para armazenar as instâncias de processo será "new_mycustombpf".  
  
 Se o valor de `uniquename` não estiver disponível para uma definição de fluxo do processo empresarial, por exemplo, se o fluxo do processo empresarial tiver sido importado como parte da solução de uma versão anterior, o nome padrão da entidade personalizada será "`\<activesolutionprefix>_bpf_<GUID_BPF_Definition>`:  
  
> [!IMPORTANT]
>  Os registros de fluxo de processo empresarial de amostra usam entidades do sistema para armazenar os registros de instância do fluxo de processo empresarial correspondentes.  
>   
>  No entanto, quaisquer novas definições de fluxo de processo empresarial que você criar usarão entidades personalizadas para armazenar seus registros de instância, conforme explicado anteriormente. 

Você pode recuperar o nome da sua entidade de fluxo do processo empresarial usando qualquer uma das seguintes maneiras:

- **Usando a interface do usuário**: use a interface do usuário de personalização para navegar até a entidade de fluxo do processo empresarial:

    ![](media/bpf-entity-name.png)
- **Usando a API Web**: use a seguinte solicitação:

    **Solicitar**

    ```
    GET [Organization URI]/api/data/v9.0/workflows?$filter=name eq 'My Custom BPF'&$select=uniquename HTTP/1.1
    ```

    **Resposta**
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
- **Usando o serviço da organização**: use o exemplo de código a seguir:

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
> A propriedade <xref:Microsoft.Xrm.Sdk.Metadata.EntityMetadata.IsBPFEntity> é `true` para as entidades do fluxo do processo empresarial. Você pode recuperar todas as entidades do fluxo do processo empresarial em sua instância executando a seguinte solicitação de API Web:
> ```http
> GET [Organization URI]/api/data/v9.0/EntityDefinitions?$select=SchemaName,LogicalName,DisplayName&$filter=IsBPFEntity eq true HTTP/1.1
> ```

<a name="BPFSecurity"></a>   
## <a name="manage-security-for-business-process-flows"></a>Gerenciar a segurança dos fluxos dos processos empresariais

A entidade personalizada que é criada automaticamente na ativação de um fluxo do processo empresarial para armazenar as instâncias dele segue o modelo de segurança padrão como qualquer outra entidade personalizada no Customer Engagement. Isso implica que os privilégios concedidos nessas entidades definem as permissões de tempo de execução dos usuários dos fluxos dos processos empresariais.

A entidade personalizada do fluxo do processo empresarial tem um escopo da organização. Os privilégios regulares para criar, recuperar, atualizar e excluir nessa entidade definem a permissão do usuário com base em suas funções atribuídas. Por padrão, quando a entidade personalizada do fluxo do processo empresarial é criada, somente as funções de segurança **administrador do sistema** e **personalizador do sistema** recebem acesso a ela. Para outras funções de segurança, você precisa conceder as permissões explicitamente para a nova entidade do fluxo do processo empresarial (por exemplo, **Meu BPF personalizado**), conforme o necessário.

![](media/bpf-privileges.png)

<a name="ManageBPF"></a>   
## <a name="create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances"></a>Criar, recuperar, atualizar e excluir registros de entidade do fluxo do processo empresarial (instâncias de processo)  
 A entidade personalizada que é criada automaticamente na ativação de uma definição de fluxo do processo empresarial armazena todas as instâncias de processo dessa definição. A entidade personalizada permite a criação e o gerenciamento programáticos padrão de registros (instâncias de processo) usando a API Web e o ponto de extremidade do CRM 2011.

> [!IMPORTANT]
> A mudança para outra instância de processo de um registro de entidade apenas é permitida por meio da interface do usuário (cliente) ou de forma programática usando as informações disponíveis nesta seção. Não é mais possível usar a mensagem `SetProcess` (<xref href="Microsoft.Dynamics.CRM.SetProcess?text=SetProcess Action" /> ou <xref:Microsoft.Crm.Sdk.Messages.SetProcessRequest>) para mudar de processo de forma programática (definir outro fluxo do processo empresarial como a instância de processo ativa) no registro da entidade de destino. 

 Vamos considerar o seguinte exemplo contendo um fluxo do processo empresarial entre entidades, "Meu BPF personalizado", com três estágios: S1:Account, S2:Account e S3:Contact. 

 ![](media/sample-bpf.png)
 
### <a name="retrieve-all-the-records-instances-for-a-business-process-flow-entity"></a>Recuperar todos os registros (instâncias) de uma entidade do fluxo do processo empresarial
 Se o nome da entidade do fluxo do processo empresarial for "new_mycustombpf", use a seguinte consulta para recuperar todos os registros (instâncias de processo) dessa entidade:  
  
```http
GET [Organization URI]/api/data/v9.0/new_mycustombpfs HTTP/1.1 
```

Neste ponto, você não poderá obter todas as instâncias em sua resposta, pois não há nenhuma. Execute esta solicitação depois de criar uma instância de sua definição de fluxo de processo empresarial neste tópico.

> [!NOTE]
> Para saber como recuperar o nome da sua entidade de fluxo do processo empresarial, consulte a seção anterior, [Entidade de fluxo de processo empresarial](#business-process-flow-entity).
  
### <a name="create-a-business-process-flow-entity-record-process-instance"></a>Criar um registro de entidade de fluxo de processo empresarial (instância de processo) 

Crie um registro de entidade de fluxo de processo empresarial (instância de processo) por meio de programação se quiser alternar para outro fluxo de processo empresarial para um registro de entidade sem usar a interface do usuário. 

Para criar um registro de entidade de fluxo de processo empresarial, você precisará especificar os seguintes valores: 
- Associar o registro de entidade de fluxo de processo empresarial a um registro de entidade principal definindo a propriedade de navegação de valor único usando a anotação `@odata.bind`. Para descobrir o nome da propriedade de navegação que aponta para o registro de entidade principal para sua definição de fluxo de processo empresarial, use o [documento CSDL $metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document). 
- Associar o registro de entidade de fluxo de processo empresarial a estágio válido especificado na definição do fluxo de processo empresarial definindo a propriedade de navegação de valor único usando a anotação `@odata.bind`. Para descobrir o nome da propriedade de navegação (normalmente, `activestageid`) que aponta para o registro de estágio para sua definição de fluxo de processo empresarial, use o [documento CSDL $metadata](/dynamics365/customer-engagement/developer/webapi/web-api-types-operations.md#csdl-metadata-document).

    Além disso, você pode recuperar informações sobre todos os estágios para uma definição de fluxo do processo empresarial usando a seguinte solicitação da API Web, supondo que a ID da sua definição de fluxo de processo empresarial seja 2669927e-8ad6-4f95-8a9a-f1008af6956f:

    **Solicitar**

    ```http
    GET [Organization URI]/api/data/v9.0/processstages?$select=stagename&$filter=processid/workflowid eq 2669927e-8ad6-4f95-8a9a-f1008af6956f HTTP/1.1
    ```

    **Resposta**

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

Em seguida, use a seguinte solicitação para criar uma instância de sua definição de fluxo de processo empresarial para um registro de conta (ID=a176be9e-9a68-e711-80e7-00155d41e206) e o estágio ativo definido como o primeiro estágio da instância do processo, S1 (ID=9a9185f5-b75b-4bbb-9c2b-a6626683b99b):

**Solicitar**

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

**Resposta**

```http
HTTP/1.1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.0/new_mycustombpfs(cc3f721b-026e-e811-80ff-00155d513100)
```

Observe que, se você quiser criar uma instância de sua definição de fluxo de processo empresarial com estágio ativo definido como um estágio ***diferente*** do primeiro, você também deverá fornecer `traversedpath` na sua solicitação. O caminho percorrido é a cadeia de caracteres delimitada por vírgulas de IDs de estágio do processo que representam estágios visitados da instância de fluxo do processo empresarial. A solicitação a seguir cria uma instância de um registro de conta (ID=679b2464-71b5-e711-80f5-00155d513100) e estágio ativo definido como o segundo estágio, S2 (ID=19a11fc0-3398-4214-8522-cb2a97f66e4b).

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

### <a name="update-a-business-process-flow-entity-record-process-instance"></a>Atualizar um registro de entidade de fluxo de processo empresarial (instância de processo)

Você pode atualizar uma instância de processo para mover para o estágio seguinte ou anterior, abandonar uma instância de processo, reativar uma instância de processo ou concluir uma instância de processo. 

#### <a name="stage-navigation"></a>Navegação de estágio

Para navegar até um estágio diferente, você precisa atualizar um registro de instância de processo para alterar sua ID de estágio ativo e atualizar adequadamente o caminho percorrido. Observe que você só deve mover para o estágio anterior ou seguinte ao atualizar uma instância de fluxo de processo empresarial.

Para executar a navegação de estágio, você precisará da ID da instância de fluxo do processo empresarial que você deseja atualizar. Para recuperar todas as instâncias do seu fluxo de processo empresarial, consulte [Recuperar todos os registros (instâncias) para uma entidade de fluxo de processo empresarial](#retrieve-all-the-records-instances-for-a-business-process-flow-entity) mencionado anteriormente.

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

#### <a name="change-the-state-of-a-process-instance-abort-reactivate-or-finish"></a>Altere o estado de uma instância de processo: Anular, Reativar ou Concluir 

Uma instância de processo pode estar em um dos seguintes estados: **Ativa**, **Concluída** ou **Anulada**. O estado é determinado pelos seguintes atributos no registro de instância do processo:

- **statecode**: exibe o status da instância de processo.

    |Valor|Rótulo|
    |-----|-----|
    |0    |Ativo|
    |1    |Inativo|

- **statuscode**: exibe informações sobre o status da instância de processo.

    |Valor|Rótulo|
    |-----|-----|
    |1    |Ativo|
    |2    |Concluído|
    |3    |Anulado|

Portanto, para **Anular** uma instância de processo, use a seguinte solicitação e defina os valores `statecode` e `statuscode` adequadamente:

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

Da mesma forma, para reativar uma instância de processo, substitua os valores `statecode` e `statuscode` no código acima com **0** e **1**, respectivamente.

Por fim, para definir um status da instância de processo como **Concluído**, que é possível apenas no último estágio de uma instância de processo, substitua os valores `statecode` e `statuscode` no código acima por **0** e **2**, respectivamente.

#### <a name="cross-entity-navigation"></a>Navegação entre entidades

Para a navegação entre entidades neste exemplo, você deve definir o estágio ativo da instância do processo para o último estágio, S3 (ID=a107e2fd-7543-4c1a-b6b4-b8060ecb1a1a), atualizar o caminho percorrido adequadamente e definir um registro de contato como o registro de entidade principal de acordo a definição de fluxo do processo empresarial.

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

### <a name="delete-a-business-process-flow-entity-record-process-instance"></a>Excluir um registro de entidade de fluxo de processo empresarial (instância de processo)

Use a seguinte solicitação de API Web:

**Solicitar**

```http
DELETE [Organization URI]/api/data/v9.0/new_mycustombpfs(dc2ab599-306d-e811-80ff-00155d513100) HTTP/1.1
```  

**Resposta**

Se o registro existir, você obterá uma resposta normal com status 204 para indicar que a exclusão foi bem-sucedida. Se a entidade não for encontrada, você obterá uma resposta com o status 404.

## <a name="use-retrieveprocessinstances-and-retrieveactivepath-messages"></a>Use as mensagens RetrieveProcessInstances e RetrieveActivePath

Use a mensagem `RetrieveProcessInstances` (<xref href="Microsoft.Dynamics.CRM.RetrieveProcessInstances?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveProcessInstancesRequest>) para recuperar todas as instâncias de fluxo de processo empresarial para um registro de entidade em todas as definições de processo empresarial. As instâncias de fluxo de processo empresarial retornadas para uma entidade são ordenadas com base no atributo `modifiedon` para a instância. Por exemplo, a instância de fluxo de processo empresarial mais recentemente modificada será o *primeiro* registro na coleção retornada. A instância de fluxo de processo empresarial mais recentemente modificada é aquela que está ativa na interface do usuário para um registro de entidade.  
  
Cada registro de instância de fluxo de processo empresarial retornado para um registro de entidade como resultado do uso da mensagem `RetrieveProcessInstances` armazena a ID do estágio no atributo `processstageid` que pode ser usado para localizar o estágio ativo e, em seguida, mover para o estágio seguinte ou anterior. Para fazer isso, você primeiro precisa localizar o caminho ativo de uma instância de fluxo de processo empresarial e os estágios disponíveis na instância de fluxo de processo usando a mensagem `RetrieveActivePath` (<xref href="Microsoft.Dynamics.CRM.RetrieveActivePath?text=RetrieveActivePath Function" /> ou <xref:Microsoft.Crm.Sdk.Messages.RetrieveActivePathRequest>).   
  
 Depois de ter o estágio ativo e as informações de caminho ativo para uma instância de fluxo de processo empresarial, você pode usar as informações para mover para um estágio anterior ou seguinte no caminho ativo. A navegação progressiva dos estágios deve ser feita em sequência, ou seja, você deve apenas passar para o próximo estágio no caminho ativo.   
  
 Para obter o exemplo completo do código que demonstra o uso desses dois métodos e a navegação de estágio usando o [serviço da organização](/dynamics365/customer-engagement/developer/org-service/use-organization-service-read-write-data-metadata), confira [Exemplo: Trabalhar com fluxos dos processos empresariais](sample-work-business-process-flows.md). 

<a name="ApplyBPF"></a>   
## <a name="apply-business-process-flow-while-creating-an-entity-record"></a>Aplicar o fluxo do processo empresarial durante a criação de um registro de entidade

Esta seção fornece informações sobre o comportamento padrão para a aplicação de fluxos de processo empresarial automaticamente a novos registros de entidade criados na participação do cliente e como isso pode ser substituído para aplicar um fluxo de processo empresarial de sua escolha para novos registros de entidade.

Por padrão, para uma entidade que tem vários fluxos de processo empresarial definidos para ela, o sistema aplica um fluxo de processo empresarial para o novo registro de entidade usando a lógica de várias etapas a seguir:
1. Identificar todos os fluxos de processo empresarial aplicáveis para o novo registro de entidade com base no atributo **Workflow.PrimaryEntity** dos registros de definição de fluxo do processo empresarial.
2. Identifique as definições de fluxo de processo empresarial as quais o usuário atual tem acesso. Para obter informações sobre como o acesso a um fluxo de processo empresarial é determinado e gerenciado, consulte [Gerenciar a segurança para fluxos de processo empresarial](#BPFSecurity) anteriormente neste tópico.<br/>  
3. Todas as definições de fluxo de processo empresarial no sistema estão sujeitas a uma ordem global por entidade. A ordem do fluxo de processo empresarial é armazenada no atributo **Workflow.ProcessOrder**. As definições de fluxo do processo empresarial para uma entidade são classificadas com base nessa ordem, e a que tiver o menor valor de ordem é escolhida.
4. Por fim, se o registro de entidade é criado de um aplicativo de negócios (módulo de aplicativo), mais um nível de filtragem é aplicado para escolher o fluxo do processo empresarial que será aplicado automaticamente ao novo registro de entidade. Ao trabalhar em um aplicativo, os usuários podem acessar apenas entidades relevantes, fluxos de processo empresarial, exibições e formulários aos quais eles tenham acesso em virtude de funções de segurança atribuídas ao aplicativo de negócios. 
    - Se o aplicativo de negócios não contiver qualquer fluxo de processo empresarial, então o fluxo do processo empresarial será aplicado conforme explicado até a etapa 3.
    - Se o aplicativo de negócios tiver um ou mais fluxos de processo empresarial, então apenas os fluxos de processo empresarial presentes no aplicativo serão aplicáveis. Nesse caso, quando o usuário está trabalhando em um contexto de aplicativo de negócios, a lista de fluxos de processo empresarial da etapa 3 é filtrada para aqueles que fazem parte do aplicativo de negócios e que estão presentes dentro do módulo de aplicativo e são classificados com base na ordem do processo. 
    - Se nenhum fluxo de processo empresarial estiver disponível em um aplicativo de negócios para a entidade ou um que o usuário tenha acesso, então nenhum fluxo de processo empresarial será aplicado para o novo registro de entidade.

Você pode substituir a lógica padrão de fluxos de processo empresarial sendo aplicados automaticamente para novos registros de entidade. Para fazer isso, defina o atributo **ProcessId** da entidade para um dos valores a seguir ao criar um novo registro de entidade:
- Defina **Guid.Empty** para ignorar a configuração de um fluxo de processo empresarial para novos registros de entidade. Você talvez queira fazer isso se você criar registros de entidade em massa, mas não quiser que o fluxo do processo empresarial seja aplicado a eles.
- Defina-o para uma entidade de fluxo de processo empresarial específica (como uma referência de entidade). Nesse caso, o sistema aplicará o fluxo do processo empresarial especificado em vez da lógica padrão.

Se você não definir um valor para o atributo **ProcessId** ao criar um novo registro de entidade, o sistema aplicará a lógica padrão conforme explicado anteriormente.

> [!NOTE]
> A substituição da lógica padrão de fluxos de processo empresarial sendo aplicados automaticamente a novos registros de entidade tem suporte apenas por meio de programação. Você não pode fazer isso usando a interface do usuário.

## <a name="legacy-process-related-attributes-in-entities"></a>Atributos herdados relacionados ao processo nas entidades

Os atributos herdados relacionados ao processo (como **ProcessId**, **StageId** e **TraversedPath**) em entidades habilitadas para os fluxos do processo empresarial já foram preteridos. Manipular esses atributos herdados relacionados ao processo para registros de entidade de destino não garante a consistência do estado de fluxo do processo empresarial e ***não*** é um cenário com suporte. A maneira recomendada é usar os atributos da entidade de fluxo de processo empresarial, conforme explicado anteriormente na seção [Criar, recuperar, atualizar e excluir registros de entidade do fluxo de processo empresarial (instâncias do processo)](#create-retrieve-update-and-delete-business-process-flow-entity-records-process-instances)

A única exceção é modificar de forma programática o atributo **ProcessId** durante a criação de um registro de entidade para substituir o aplicativo padrão do fluxo do processo empresarial no novo registro, conforme explicado na seção anterior: [Aplicar o fluxo do processo empresarial durante a criação de um registro de entidade](#ApplyBPF).

<a name="BKMK_clientSideScript"></a>   
## <a name="client-side-programmability-support-for-business-process-flows"></a>Suporte do lado do cliente por meio de programação para fluxos de processo empresarial  
 Há um objeto do lado do cliente que você pode usar para interagir com os fluxos de processo empresarial em seus scripts de formulário. Os fluxos de processo empresarial disparam eventos do lado do cliente sempre que um processo também é aplicado a um registro, o estágio é alterado ou seu status é alterado para `Active`, `Finished` ou `Aborted`. Mais informações: [formContext.data.process (referência de API do cliente)](/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process.md)  
  
<a name="BKMK_MaxSettings"></a>   
## <a name="maximum-number-of-processes-stages-and-steps"></a>Número máximo de processos, estágios e etapas  
 Por entidade, o valor padrão para o número máximo de fluxos de processo empresarial ativado é 10. Você pode especificar um valor diferente usando o atributo `Organization.MaximumActiveBusinessProcessFlowsAllowedPerEntity`. No entanto, se o valor for maior que 10, você poderá ver uma diminuição no desempenho do sistema quando alternar entre processos ou abrir um registro que tenha um fluxo de processo empresarial atribuído. Isso pode ser particularmente perceptível se os processos abrangem várias entidades.  
  
 As configurações a seguir não são personalizáveis:  
  
-   O número máximo de estágios por entidade no processo é 30.  
  
-   O número máximo de etapas em cada estágio é 30.  
  
-   O número máximo de entidades que podem participar no fluxo de processo é 5.  

