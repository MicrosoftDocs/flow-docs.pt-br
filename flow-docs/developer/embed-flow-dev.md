---
title: Integre Microsoft Flow com sites e aplicativos | Microsoft Docs
description: Insira as experiências de Microsoft Flow em seu site ou aplicativo.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: cf2f14826670cf221411fa2204ee9b2c5581222e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547722"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Integre Microsoft Flow com sites e aplicativos
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Insira Microsoft Flow em seu aplicativo ou site usando *widgets de fluxo* para dar aos usuários uma maneira simples de automatizar suas tarefas pessoais ou profissionais.

Os widgets de fluxo são iframes localizados em um documento de host. Este documento aponta para uma página no designer de Microsoft Flow. Esses widgets integram a funcionalidade de Microsoft Flow específica no aplicativo de terceiros.

Os widgets podem ser simples. Por exemplo, um widget que renderiza uma lista de modelos sem comunicação entre o host e o iframe. Os widgets também podem ser complexos. Por exemplo, um widget que provisiona um fluxo de um modelo e, em seguida, dispara o fluxo por meio da comunicação bidirecional entre o host e o widget.

## <a name="prerequisites"></a>Pré-requisitos

- Uma **conta da Microsoft** ou
- Uma conta corporativa ou de estudante

## <a name="use-the-unauthenticated-widget"></a>Usar o widget não autenticado
Para usar o widget modelos não autenticados, incorpore-o diretamente ao aplicativo host usando um iframe. Você não precisa do SDK do JS ou de um token de acesso. 

### <a name="show-templates-for-your-scenarios"></a>Mostrar modelos para seus cenários
Para começar, adicione este código para mostrar os modelos de Microsoft Flow em seu site:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}&category={category}"></iframe>
```

| Meter | Ndescrição |
| --- | --- |
| localidade |O idioma de quatro letras e o código de região para o modo de exibição de modelo. Por exemplo, `en-us` representa inglês americano e `de-de` representa alemão. |
| termo de pesquisa |O termo de pesquisa para os modelos que você deseja mostrar na exibição. Por exemplo, pesquise `wunderlist` para mostrar modelos para o Wunderlist. |
| número de modelos |O número de modelos que você deseja mostrar na exibição. |
| Destino |A página que é aberta quando os usuários selecionam o modelo. Insira `details` para mostrar os detalhes sobre o modelo ou insira `new` para abrir o designer de Microsoft Flow. |
| Categorias |Filtra para a categoria de modelo fornecida. | 
| parâmetro. nomes |Contexto adicional para passar para o fluxo. |


Se o parâmetro de destino for `new`, o designer de Microsoft Flow será aberto quando os usuários selecionarem um modelo. Os usuários podem, então, criar um fluxo no designer. Consulte a próxima seção se você quiser ter a experiência completa do widget.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Passando parâmetros adicionais para o modelo de fluxo

Se o usuário estiver em um contexto específico em seu site ou aplicativo, talvez você queira passar esse contexto para o fluxo. Por exemplo, um usuário pode abrir um modelo para *notificá-lo quando um item é adicionado a uma lista* ao examinar uma determinada lista no Wunderlist. Siga estas etapas para passar a ID da lista como um *parâmetro* para o fluxo:

1. Defina o parâmetro no modelo de fluxo antes de publicá-lo. Um parâmetro é semelhante A `@{parameters('parameter_name')}`.
1. Passe o parâmetro na cadeia de caracteres de consulta da src do iframe. Por exemplo, adicione `&parameters.listName={the name of the list}` se você tiver um parâmetro chamado **ListName**.

### <a name="full-sample"></a>Exemplo completo

Para mostrar os quatro principais modelos do Wunderlist em alemão e iniciar o usuário com **Mycoollist**, use este código:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Usar os widgets de fluxo autenticados

A tabela a seguir mostra a lista de Microsoft Flow widgets que dão suporte à experiência completa no widget usando o token de acesso de autenticação do usuário. Você precisará usar o JavaScript Software Developer Kit (SDK) do Microsoft Flow para inserir os widgets e fornecer o token de acesso do usuário necessário.

| Tipo de widget    | Recurso com suporte                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Fluxo          | Mostra uma lista de fluxos em uma guia para fluxos pessoais e compartilhados. Edite um fluxo existente ou crie um novo fluxo a partir de um modelo ou em branco. | 
| flowCreation   | Cria um fluxo de uma ID de modelo que o aplicativo host fornece.                                                                | 
| appmodel        | Dispara um fluxo de gatilhos manual ou híbrido que o aplicativo host fornece.                                                        | 
| approvalCenter | Insere solicitações de aprovação e aprovações enviadas.                                                                                        | 
| Modelo      | Mostra uma lista de modelos. O usuário escolhe um para criar um novo fluxo.                                                                         | 

Use o SDK do fluxo autenticado para permitir que os usuários criem e gerenciem fluxos diretamente do seu site ou aplicativo (em vez de navegar até Microsoft Flow). Você precisará conectar o usuário com sua conta da Microsoft ou Azure Active Directory para usar o SDK autenticado.

> [!NOTE]
> Não é possível ocultar a identidade visual Microsoft Flow quando você usa widgets.

## <a name="widget-architecture"></a>arquitetura do widget

Microsoft Flow widgets funcionam inserindo um iframe que faz referência a Microsoft Flow em um aplicativo host. O host fornece o token de acesso exigido pelo Widget de Microsoft Flow. O SDK do JS do Microsoft Flow permite que o aplicativo host inicialize e gerencie o ciclo de vida do widget.

![arquitetura do widget](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Detalhes do SDK do JS

A equipe de Microsoft Flow fornece o JS SDK para facilitar a integração de widgets de fluxo em aplicativos de terceiros. O SDK do Flow JS está disponível como um link público no serviço de fluxo e permite que o aplicativo host manipule eventos do widget e interaja com o aplicativo de fluxo enviando ações para o widget. Eventos e ações de widget são específicos do tipo de widget.

### <a name="widget-initialization"></a>Inicialização do widget

A referência do SDK do Flow JS precisa ser adicionada ao aplicativo host antes de inicializar o widget.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Crie uma instância do SDK do JS passando valores opcionais de nome de host e localidade em um objeto JSON.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US'
}); 
```

| Nomes     | Obrigatório/opcional | Ndescrição                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Adicional          | Microsoft Flow nome do host, por exemplo, https://flow.microsoft.com        | 
| `locale`   | Adicional          | Localidade do cliente para o widget (o padrão é `en-Us` se não for especificado) | 


Depois que a instância do SDK do JS for criada, você poderá inicializar e inserir um widget de Microsoft Flow em um elemento pai no aplicativo host. Para fazer isso, adicione um div HTML:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Em seguida, inicialize o widget Microsoft Flow com o método de `renderWidget()` do SDK JS. Certifique-se de fornecer o tipo de widget e as configurações correspondentes.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flowDiv',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {}
});
```

Aqui está um estilo de exemplo para o contêiner que você pode modificar para corresponder às dimensões do aplicativo host.

```html
<head>
    <style>
        .flowContainer iframe {
            width: 400px;
            height: 1000px;
            border: none;
            overflow: hidden;
    }
    </style>
</head>
```

Estes são os parâmetros para `renderWidget()`: 

| Meter        | Obrigatório/opcional | Ndescrição                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Necessário          | ID de um elemento DIV na página host onde o widget será inserido.                   | 
| `environmentId`    | Adicional          | Os widgets precisam de uma ID de ambiente. Se você não fornecer uma ID, um ambiente padrão será usado. | 
| `flowsSettings`    | Adicional          | Objeto de configurações de Microsoft Flow                                                                        | 
| `templateSettings` | Adicional          | Objeto de configurações de modelo                                                                    | 
| `approvalSettings` | Adicional          | Objeto de configurações de aprovação                                                                    | 

### <a name="access-tokens"></a>Tokens de acesso

Depois que o SDK do JS `renderWidget()` é executado, o SDK do JS Inicializa um iframe que aponta para a URL do widget Microsoft Flow. Essa URL contém todas as configurações nos parâmetros de cadeia de caracteres de consulta. O aplicativo host precisa obter um token de acesso Microsoft Flow para o usuário (Azure Active Directory token JWT com o público https://service.flow.microsoft.com) antes de inicializar o widget. O widget gera um evento `GET_ACCESS_TOKEN` para solicitar um token de acesso do host. O host precisa manipular o evento e passar o token para o widget:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

O aplicativo host é responsável por manter o token e passá-lo com uma data de expiração válida para o widget quando solicitado. Se o widget estiver aberto por períodos mais longos, o host deverá verificar se o token expirou e atualizar o token, se necessário, antes de passá-lo para o widget.

### <a name="detecting-if-the-widget-is-ready"></a>Detectando se o widget está pronto

Após a inicialização bem-sucedida, o widget gera um evento para notificar que o widget está pronto. O host pode escutar o evento de `WIDGET_READY` e executar qualquer código de host adicional.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Configurações do widget

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings pode ser usado para personalizar a funcionalidade do widget Microsoft Flow.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Meter | Obrigatório/opcional | Ndescrição | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Necessário | Use o GUID do modelo quando o usuário selecionar o botão **criar de branco** no widget de fluxo | 
| `flowsFilter` | Adicional | O widget Microsoft Flow aplica o filtro fornecido ao listar fluxos. Por exemplo, mostre fluxos que fazem referência a um site específico do SharePoint. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Adicional | O padrão é a guia ativa a ser mostrada no widget Microsoft Flow. <br /> Por exemplo, <br /> ```tab:'sharedFlows' ``` exibe a guia equipe<br /> e ``` tab:'myFlows' ``` exibe a guia Meus fluxos. |   

### <a name="templatessettings"></a>TemplatesSettings 

Isso se aplica a todos os widgets que permitem que você crie fluxos de um modelo, incluindo os widgets fluxos, FlowCreation e modelos.

```javascript
templatesSettings?: {
    defaultParams?: any;
    destination?: string;
    pageSize?: number;
    searchTerm?: string;
    templateCategory?: string;
    useServerSideProvisioning?: boolean;
    enableDietDesigner?: boolean;
};
 ```

| Meter |Obrigatório/opcional | Ndescrição                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Adicional          | Parâmetros de tempo de design a serem usados ao criar um fluxo de um modelo, por exemplo: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Adicional          | Os valores válidos são ' New ' ou ' details '. Quando definido como ' Detalhes ', uma página de detalhes é mostrada durante a criação de um fluxo de um modelo.     |
| `pageSize` | Adicional          | Número de modelos a serem exibidos. Tamanho padrão = 6 | 
| `searchTerm` | Adicional          | Exibir modelos que correspondem ao termo de pesquisa fornecido| 
| `templateCategory` | Adicional          | Exibir modelos em uma categoria específica| 
 
### <a name="approvalcentersettings"></a>ApprovalCenterSettings

Aplica-se a widgets ApprovalCenter.

 ```javascript
 approvalCenterSettings?: {
    approvalsFilter?: string;
    tab?: string;but
    autoNavigateToDetails?: boolean;
    showSimpleEmptyPage? boolean;
    hideLink?: boolean
};
 ```
| Meter | Obrigatório/opcional | Ndescrição | 
|------------|-------------------|--------------| 
| `hideLink`| Adicional | Quando definido como `true`, o widget oculta os links de aprovação recebidos e enviados | 
| `autoNavigateToDetails`| Adicional | Quando definido como `true`, o widget abre automaticamente os detalhes de aprovação quando há apenas uma aprovação | 
| `approvalsFilter`| Adicional | O widget de aprovação aplicará o filtro de aprovação especificado ao listar as aprovações, por exemplo: o widget de aprovação aplicará o filtro de aprovação especificado ao listar as aprovações, por exemplo: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Adicional | Guia ativa padrão para mostrar no widget de fluxo. <br/> Valores válidos: ' receivedApprovals ', ' sentApprovals ' | 
| `showSimpleEmptyPage`| Adicional | Mostra uma página vazia quando não há aprovações | 
| `hideInfoPaneCloseButton` | Adicional | Oculta o botão de fechamento informações-painel (ou o host já tem um botão fechar) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Eventos de widget

O widget Microsoft Flow dá suporte a eventos que permitem que o host Ouça eventos do ciclo de vida do widget. O widget de Microsoft Flow dá suporte a dois tipos de eventos: eventos de notificação unidirecional (por exemplo, widget\_pronto) e eventos gerados do widget para buscar dados do host (obter\_token de\_de acesso). O host precisa usar o método widget. Listen () para escutar eventos específicos gerados do widget.

### <a name="usage"></a>Usos

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Eventos com suporte por tipo de widget

| Evento do widget      | Ver                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Widget carregado com êxito                                      | 
| `WIDGET_RENDERED`   | O widget foi carregado e a renderização da interface do usuário foi concluída                      | 
| `GET_ACCESS_TOKEN`  | Solicitação de widget para inserir token de acesso de usuário                      | 
| `GET_STRINGS`       | Permite que o host substitua um conjunto de cadeias de caracteres da interface do usuário mostrado no widget | 

### <a name="runtime-widget"></a>Widget de tempo de execução

| Evento do widget                    | Ver                                     | Dado                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Acionado e a execução do fluxo foi iniciada      |           | 
| `RUN_FLOW_COMPLETED`              | Execução de fluxo disparada com êxito             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | Botão selecionado pelo usuário na execução do fluxo       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | Botão Cancelar selecionado pelo usuário na execução do fluxo     |           | 
| `FLOW_CREATION_SUCCEEDED`         | O fluxo foi criado com êxito           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Acionado quando o host deve fechar o widget |       | 

### <a name="flow-creation-widget"></a>Widget de criação de fluxo

| Evento do widget             | Ver                                  | Dado  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Falha na criação do fluxo                     |       | 
| `WIDGET_CLOSE`             | Acionado quando o host deve fechar o widget  |       | 
| `TEMPLATE_LOAD_FAILED`     | Falha ao carregar o modelo              |       | 
| `FLOW_CREATION_SUCCEEDED`  | O fluxo foi criado com êxito        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget de aprovação

| Evento do widget                      | Ver                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Status de aprovação recebido alterado  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Status de aprovação enviado alterado      | 

O evento **GET\_Strings** permite que você personalize o texto de alguns dos elementos da interface do usuário mostrados no widget. As seguintes cadeias de caracteres podem ser personalizadas:

| Chave de cadeia de caracteres                     | Usar no widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Texto exibido no botão criar fluxo no widget criação de fluxo e tempo de execução                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | O valor inicial a ser usado para o nome do fluxo no widget de criação de fluxo. Usado somente quando a configuração allowCustomFlowName está habilitada. | 
| `FLOW_CREATION_HEADER`           | Cabeçalho a ser usado ao criar um fluxo no widget criação de fluxo e tempo de execução                                                    | 
| `INVOKE_FLOW_HEADER`             | Cabeçalho a ser usado ao invocar um fluxo no widget de tempo de execução                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Texto exibido no botão usado para invocar/executar um fluxo no widget de tempo de execução                                                       | 

### <a name="example"></a>Exemplo

Chame `widgetDoneCallback` passando um objeto JSON com pares de chave-valor de texto e chave de cadeia de caracteres para substituir o valor padrão.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Ações do widget

O host usa ações do widget para enviar uma ação ou mensagem específica para o widget. O SDK do widget JS fornece o método `notify()` para enviar uma mensagem ou uma carga JSON para o widget. Cada ação de widget dá suporte a uma assinatura de carga específica.

### <a name="usage"></a>Usos

```javascript
widget.notify('<WIDGET_ACTION>', parameterMatchingParameterInterface)
    .then(result => console.log(result))
    .catch(error => console.log(error))
 ```

### <a name="example"></a>Exemplo 

Invocar um fluxo enviando o comando a seguir para um widget de tempo de execução 

```javascript
widget.notify('triggerFlow', { flowName: flowName, implicitData:implicitData });  
 ```

### <a name="runtime-widget"></a>Widget de tempo de execução

| Ação do widget                               | Ver                                                      | Interface de parâmetro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Dispara uma execução de fluxo                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Dispara uma execução de fluxo por modelo                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Obtém o esquema de gatilho para um fluxo                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Cancela qualquer atividade pendente e gera um evento WIDGET_CLOSE |                      | 

### <a name="flow-creation-widget"></a>Widget de criação de fluxo

| Ação do widget                               | Ver                                                      | Interface de parâmetro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Cria um fluxo para o modelo selecionado                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Cria um fluxo para a definição de modelo selecionada          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Cancela qualquer atividade pendente e gera um evento WIDGET_CLOSE |                      | 

### <a name="approval-widget"></a>Widget de aprovação

| Ação do widget  | Ver                                           | Interface de parâmetro  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Fecha o painel informações exibindo detalhes de aprovação  | N/A                  | 

## <a name="configuring-your-client-application"></a>Configurando seu aplicativo cliente

Você precisará configurar seu aplicativo cliente com escopos de serviço de fluxo (permissões delegadas). Se o aplicativo Azure Active Directory (AAD) usado para a integração do widget usar um fluxo de autorização ' concessão de código ', o aplicativo AAD precisará ser pré-configurado com permissões delegadas com suporte Microsoft Flow. Isso fornece permissões delegadas que permitem ao aplicativo:

-   Gerenciar aprovações
-   Aprovações de leitura
-   Ler atividades
-   Gerenciar fluxos
-   Fluxos de leitura

Siga estas etapas para selecionar uma ou mais permissões delegadas:

1.  Ir para https://portal.azure.com 
2.  Selecione **Azure Active Directory**.
3.  Selecione **registros de aplicativo** em **gerenciar**.
4.  Insira o aplicativo de terceiros a ser configurado para escopos de serviço de fluxo.
5.  Selecione **configurações**.
      ![a arquitetura do widget](../media/embed-flow-dev/AAD-App-Settings.png)
6. Selecione **as permissões necessárias** em **acesso à API**/
7. Selecione **Adicionar**.
8. Escolha **selecionar uma API**.
      ![a arquitetura do widget](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Procure **Microsoft Flow serviço** e selecione-o. Observação: antes de poder ver Microsoft Flow serviço, seu locatário precisa ter pelo menos um usuário do AAD conectado ao portal do Flow (<https://flow.microsoft.com>)
10. Escolha os escopos de fluxo necessários para seu aplicativo e, em seguida, selecione **salvar**.
      ![a arquitetura do widget](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Agora, seu aplicativo obterá um token de serviço de fluxo que contém permissões delegadas na declaração de \'SCP no token JWT.

## <a name="sample-application-embedding-flow-widgets"></a>Widgets de fluxo de incorporação de aplicativo de exemplo 

Um SPA (aplicativo de página única) de JavaScript de exemplo é fornecido na seção de recursos para que você possa experimentar com widgets de fluxo de incorporação em uma página de host. O uso do aplicativo de exemplo requer o registro de um aplicativo do AAD com o fluxo de concessão implícito habilitado.

### <a name="registering-an-aad-app"></a>Registrando um aplicativo do AAD

1.  Entre no [portal do Azure](https://portal.azure.com/).
2.  No painel de navegação esquerdo, selecione **Azure Active Directory**e, em seguida, selecione **registros de aplicativo** (versão prévia) \> novo registro.
3.  Quando a página **registrar um aplicativo** for exibida, insira um nome para seu aplicativo.
4.  Em **tipos de conta com suporte**, selecione **contas** em qualquer diretório organizacional.
5.  Na seção **URL de redirecionamento** , selecione a plataforma da Web e defina o valor para o aplicativo\'s URL com base em seu servidor Web.  Configure esse valor para http://localhost:30662/ para executar o aplicativo de exemplo.
6.  Selecione **registrar**.
7.  Na página **visão geral** do aplicativo, observe o valor da ID do aplicativo (cliente).
8.  O exemplo requer que o [fluxo de concessão implícita](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) esteja habilitado. No painel de navegação à esquerda do aplicativo registrado, selecione **autenticação**.
9.  Em **Configurações avançadas**, em **concessão implícita**, habilite as caixas de seleção **tokens de ID** e **tokens de acesso** . Tokens de ID e tokens de acesso são necessários, pois esse aplicativo precisa conectar usuários e API de fluxo de chamadas.
10. Selecione **salvar**.

### <a name="running-the-sample"></a>Executando o exemplo
<!-- todo where should I download from? -->
1.  Baixe o exemplo e copie-o para uma pasta local em seu dispositivo.
2.  Abra o arquivo index. html na pasta FlowSDKSample e modifique o `applicationConfig` para atualizar o `clientID` para a ID do aplicativo que você registrou anteriormente.
    ![a arquitetura do widget](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  O aplicativo de exemplo está configurado para usar fluxos de escopos de fluxo **. Read. All** e **Flow. Manage. All.** Você pode configurar escopos adicionais atualizando a propriedade **flowScopes** no objeto **applicationConfig** .
4.  Execute estes comandos para instalar a dependência e executar o aplicativo de exemplo:
    > \> NPM instalar \> node Server. js
5. Abra o navegador e, em seguida, insira http://localhost:30662
6. Selecione o botão **entrar** para autenticar no AAD e adquirir um token de acesso de fluxo.
7. A caixa de texto **token de acesso** contém o token de acesso.
    ![a arquitetura do widget](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Selecione o **widget carregar fluxos** ou o **widget modelos de carregamento** para inserir os widgets correspondentes.
    ![a arquitetura do widget](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

Link de [Download](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip)do aplicativo de exemplo.

## <a name="resources"></a>Os

### <a name="widget-test-pages"></a>Páginas de teste de widget

Saiba mais sobre as configurações e a integração do widget:

- Widget de modelos: <[https://flow.microsoft.com/test/templateswidget/](https://flow.microsoft.com/test/templateswidget/)>
- Widget FlowCreation: <[https://flow.microsoft.com/test/flowcreationwidget/](https://flow.microsoft.com/test/flowcreationwidget/)>
- Widget de tempo de execução: <[https://flow.microsoft.com/test/runtimewidget/](https://flow.microsoft.com/test/runtimewidget/)>
- Widget do centro de aprovações: <[https://flow.microsoft.com/test/approvalcenterwidget/](https://flow.microsoft.com/test/approvalcenterwidget/)>
- Widget de fluxos: <[https://flow.microsoft.com/test/managewidget/](https://flow.microsoft.com/test/managewidget/)>

### <a name="supported-widget-locales"></a>Localidades de widget com suporte

Se a localidade inicializada não estiver listada, o Flow usará como padrão a localidade com suporte mais próxima.

| localidade     | idioma                   | 
|------------|----------------------------| 
| bg-BG      | Búlgaro (Bulgária)       | 
| CA-es      | Catalão (Espanha)            | 
| Cs-cz      | Tcheco (República Tcheca)     | 
| da-DK      | Dinamarquês (Dinamarca)           | 
| De-de      | Alemão (Alemanha)           | 
| El-gr      | Grego (Grécia)             | 
| en-US      | Inglês (Estados Unidos)    | 
| Es-es      | Espanhol (castelhano)        | 
| et-EE      | Estoniano (Estônia)         | 
| UE-es      | Basco (Espanha)             | 
| Fi-Fi      | Finlandês (Finlândia)          | 
| Fr-fr      | Francês (França)            | 
| GL-es      | Galego (Espanha)           | 
| Hi-HU      | Húngaro (Hungria)        | 
| Hi-in      | Híndi (Índia)              | 
| HR-HR      | Croata (Croácia)         | 
| ID-ID      | Indonésio (Indonésia)     | 
| ti-ti      | Italiano (Itália)            | 
| JP-JP      | Japonês (Japão)           | 
| kk-kz      | Cazaque (Cazaquistão)        | 
| Ko-KR      | Coreano (Coreia)             | 
| lt-LT      | Lituano (Lituânia)     | 
| LV-LV      | Letão (Letônia)           | 
| MS-My      | Malaio (Malásia)           | 
| NB-não      | Norueguês (bokmål)         | 
| NL-NL      | Holandês (Países Baixos)        | 
| Pl-pl      | Polonês (Polônia)            | 
| Pt-br      | Português (Brasil)        | 
| pt-pt      | Português (Portugal)      | 
| ro-ro      | Romeno (Romênia)         | 
| Ru-ru      | Russo (Rússia)           | 
| SK-SK      | Eslovaco (Eslováquia)          | 
| SL-si      | Esloveno (Eslovênia)       | 
| Sr-Cyrl-RS | Sérvio (cirílico, Sérvia) | 
| Sr-Latn-RS | Sérvio (latino, Sérvia)    | 
| Va-se      | Sueco (Suécia)           | 
| th-ésimo      | Tailandês (Tailândia)            | 
| TR-TR      | Turco (Turquia)           | 
| ru-UA      | Ucraniano (Ucrânia)        | 
| vi-vn      | Vietnamita (Vietnã)      |
