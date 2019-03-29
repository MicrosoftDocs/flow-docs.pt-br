---
title: Integrar o Microsoft Flow a sites e aplicativos | Microsoft Docs
description: Insira as experiências do Microsoft Flow ao seu site ou aplicativo.
services: ''
suite: flow
documentationcenter: na
author: bbarath
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2019
ms.author: barathb
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 47d44b2c97275add492153d85138b7d11b554530
ms.sourcegitcommit: 3c7822c7207cfa51d0274e9647ef02e5ea1d999f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58321400"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Integre o Microsoft Flow a sites e aplicativos

Insira o Microsoft Flow em seu aplicativo ou site usando *widgets de fluxo* para oferecer aos seus usuários uma maneira simples de automatizar suas tarefas pessoais ou profissionais.

Os widgets de fluxo são iframes localizados em um documento de host. Este documento aponta para uma página no designer do Microsoft Flow. Esses widgets integram a funcionalidade específica do Microsoft Flow no aplicativo de terceiros.

Os widgets podem ser simples. Por exemplo, um widget que renderiza uma lista de modelos sem nenhuma comunicação entre o host e o iframe. Os widgets também podem ser complexos. Por exemplo, um widget que provisiona um fluxo de um modelo e, em seguida, dispara o fluxo por meio de uma comunicação bidirecional entre o host e o widget.

## <a name="prerequisites"></a>Pré-requisitos

- Uma **Conta Microsoft** ou
- Uma conta corporativa ou de estudante

## <a name="use-the-unauthenticated-widget"></a>Usar o widget não autenticado
Para usar o modelo não autenticado, insira-o diretamente no aplicativo host em um iframe. Não é necessário um SDK do JS ou um token de acesso. 

### <a name="show-templates-for-your-scenarios"></a>Mostrar modelos de cenários
Para iniciar, adicione este código para mostrar os modelos do Microsoft Flow em seu site:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

| Parâmetro | Descrição |
| --- | --- |
| localidade |O código de região e o idioma de quatro letras para o modo de exibição do modelo. Por exemplo, `en-us` representa inglês americano e `de-de` representa o alemão. |
| termo de pesquisa |O termo de pesquisa para os modelos que você quer mostrar na exibição. Por exemplo, pesquise por `wunderlist` para mostrar modelos do Wunderlist. |
| número de modelos |O número de modelos que você quer mostrar na exibição. |
| destino |A página que é aberta quando os usuários selecionam o modelo. Insira `details` para mostrar os detalhes sobre o modelo ou insira `new` para abrir o designer do Microsoft Flow. |
| parâmetros. {nome} |Contexto adicional para passar para o fluxo. |
| templateCategory | Filtros para a categoria de modelo fornecida                     | 

Se o parâmetro de destino for `new`, o designer do Microsoft Flow será aberto quando os usuários selecionarem um modelo. Os usuários podem criar um fluxo no designer. Confira a próxima seção se desejar ter a experiência completa do widget.

### <a name="passing-additional-parameters-to-the-flow-template"></a>Passando parâmetros adicionais para o modelo de fluxo

Se o usuário estiver em um contexto específico em seu site ou aplicativo, passe esse contexto para o fluxo. Por exemplo, um usuário pode abrir um modelo para *Notificar quando um item é adicionado a uma lista* enquanto procura em determinada lista no Wunderlist. Siga estas etapas para passar a ID da lista como um *parâmetro* ao fluxo:

1. Defina o parâmetro no modelo de fluxo antes de publicá-lo. Um parâmetro tem aparência `@{parameters('parameter_name')}`.
1. Passe o parâmetro no src iframe. Por exemplo, adicione `&parameters.listName={the name of the list}` se você tiver um parâmetro chamado **listName**.

### <a name="full-sample"></a>Exemplo completo

Para mostrar os quatro melhores modelos do Wunderlist em alemão e iniciar o usuário com **myCoolList**, use este código:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="use-the-authenticated-flow-widgets"></a>Usar os widgets de fluxo autenticados

A tabela a seguir mostra a lista de widgets do Microsoft Flow compatíveis com a experiência completa dentro do widget que usa o token de acesso de autenticação do usuário. Será necessário usar o SDK do JS (Kit do Desenvolvedor de Software do Javascript) do Microsoft Flow para inserir os widgets e fornecer o token de acesso de usuário necessário.

| Tipo de widget    | Recurso com suporte                                                                                                                  | 
|----------------|------------------------------------------------------------------------------------------------------------------------------------| 
| Fluxos          | Mostra uma lista de fluxos em uma guia para fluxos pessoais e compartilhados. Edite um fluxo existente ou crie um fluxo com base em um modelo ou em branco. | 
| FlowCreation   | Cria um fluxo com base em uma ID de modelo fornecida pelo aplicativo host.                                                                | 
| Runtime        | Dispara um fluxo de gatilho híbrido ou manual fornecido pelo aplicativo host.                                                        | 
| ApprovalCenter | Insere solicitações de aprovação e aprovações enviadas.                                                                                        | 
| Modelos      | Mostra uma lista de modelos. O usuário escolhe uma para criar um novo fluxo.                                                                         | 

Use o SDK do Fluxo autenticado para permitir que os usuários criem e gerenciem fluxos diretamente do seu site ou do aplicativo (em vez de navegar até o Microsoft Flow). Será necessário conectar o usuário com sua Conta Microsoft ou com o Azure Active Directory para usar o SDK autenticado.

> [!NOTE]
> Não há como ocultar a identidade visual do Microsoft Flow ao usar widgets.

## <a name="widget-architecture"></a>Arquitetura do widget

Os widgets do Microsoft Flow funcionam por meio da inserção de um iframe que referencia o Microsoft Flow em um aplicativo host. O host fornece o token de acesso exigido pelo widget do Microsoft Flow. O SDK do JS do Microsoft Flow permite que o aplicativo host inicialize e gerencie o ciclo de vida do widget.

![arquitetura do widget](../media/embed-flow-dev/Architecture.png)

### <a name="js-sdk-details"></a>Detalhes do SDK do JS

A equipe do Microsoft Flow fornece o SDK do JS para facilitar a integração de widgets do Flow em aplicativos de terceiros. O SDK do JS do Fluxo está disponível como um link público no Serviço de fluxo e permite que o aplicativo host manipule eventos do widget e interaja com o aplicativo de Fluxo enviando ações para o widget. Eventos e ações do widget são específicos para o tipo de widget.

### <a name="widget-initialization"></a>Inicialização do widget

A referência do SDK do JS do Fluxo precisa ser adicionada ao aplicativo host antes de inicializar o widget.

```html
<script src="https://flow.microsoft.com/Content/msflowsdk-1.1.js"></script>
```

Crie uma instância de SDK do JS passando o hostName opcional e os valores de localidade em um objeto JSON.

```javascript
var sdk = new MsFlowSdk({
    hostName:'https://flow.microsoft.com',
    locale:'en-US',
}); 
```

| Nome     | Obrigatório/opcional | Descrição                                                    | 
|----------|-------------------|----------------------------------------------------------------| 
| `hostName` | Opcional          | Nome de host do Microsoft Flow, por exemplo, https://flow.microsoft.com        | 
| `locale`   | Opcional          | Localidade do cliente para o widget (o padrão é `en-Us` se não passado) | 


Após a criação da instância do SDK do JS, será possível inicializar e inserir um widget do Microsoft Flow em um elemento pai no aplicativo host. Para fazer isso, adicione um div HTML:

```html
<div id="flowDiv" class="flowContainer"></div>
```

Em seguida, inicialize o widget do Microsoft Flow com o método renderWidget() do SDK do JS. Forneça o tipo de widget e as configurações correspondentes.

```javascript
var widget = sdk.renderWidget('<widgettype>', {
        container: 'flow-div',
        flowsSettings: {},
        templatesSettings: {},
        approvalSettings: {},
        widgetStyleSettings: {},
});
```

Veja um estilo de exemplo para o contêiner que você pode modificar para corresponder às dimensões do aplicativo host.

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

| Parâmetro        | Obrigatório/opcional | Descrição                                                                                 | 
|------------------|-------------------|---------------------------------------------------------------------------------------------| 
| `container`        | Necessário          | ID de um elemento DIV na página do host em que o widget será inserido                      | 
| `environmentId`    | Opcional          | Os widgets precisam de uma ID de ambiente. Se você não fornecer uma ID, um ambiente padrão será usado. | 
| `flowsSettings`    | Opcional          | Objeto de configurações do Microsoft Flow                                                                        | 
| `templateSettings` | Opcional          | Objeto de configurações do modelo                                                                    | 
| `approvalSettings` | Opcional          | Objeto de configurações de aprovação                                                                    | 

### <a name="access-tokens"></a>Tokens de acesso

Após a execução do `renderWidget()` do SDK do JS, o SDK do JS inicializará um iframe que aponta para a URL do widget do Microsoft Flow. Essa URL contém todas as configurações nos parâmetros da cadeia de caracteres de consulta. O aplicativo host precisa obter um token de acesso do Microsoft Flow para o usuário (token JWT do Azure Active Directory com o público-alvo https://service.flow.microsoft.com) antes que ele inicialize o widget. O widget gera um evento `GET_ACCESS_TOKEN` para solicitar um token de acesso do host. O host precisa manipular o evento e passar o token para o widget:

```javascript
widget.listen("GET_ACCESS_TOKEN", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
        token:  '<accesstokenFromHost>'
    });
});
```

O aplicativo host é responsável por manter o token e por passá-lo com uma data de expiração válida para o widget quando solicitado. Se o widget for aberto por períodos maiores, o host deverá verificar se o token expirou e atualizá-lo, se necessário, antes de passá-lo para o widget.

### <a name="detecting-if-the-widget-is-ready"></a>Detectando se o widget está pronto

Após a inicialização bem-sucedida, o widget gerará um evento para notificar que o widget está pronto. O host pode escutar o evento `WIDGET_READY` e executar qualquer código de host adicional.

```javascript
widget.listen("WIDGET_READY", function() {
    console.log("The flow widget is now ready.");
    // other host code on widget ready
});
 ```

## <a name="widget-settings"></a>Configurações do widget

### <a name="flowssettings"></a>FlowsSettings 

FlowsSettings pode ser usado para personalizar a funcionalidade do widget do Microsoft Flow.

```javascript
flowsSettings?: {
    createFromBlankTemplateId?: string;
    flowsFilter?: string;sc
    tab?: string;
};
 ```

| Parâmetro | Obrigatório/opcional | Descrição | 
|-----------|-------------------|-------------| 
| `createFromBlankTemplateId` | Necessário | Use a GUID do modelo quando o usuário selecionar o botão **Criar de um modelo em branco** no widget de Fluxo | 
| `flowsFilter` | Opcional | O widget do Microsoft Flow aplica o filtro fornecido ao listar fluxos. Por exemplo, mostre fluxos que referenciam um site específico do SharePoint. <br /> ```flowFilter: "operations/any(operation: operation/sharepoint.site eq 'https://microsoft.sharepoint.com/teams/ProcessSimple' )"   ``` |                 
| `tab` | Opcional | O padrão é a guia ativa a ser mostrada no widget do Microsoft Flow. <br /> Por exemplo, <br /> ```tab:'sharedFlows' ``` exibe a guia Equipe<br /> e ``` tab:'myFlows' ``` exibe a guia Meus fluxos. |   

### <a name="templatessettings"></a>TemplatesSettings 

Isso se aplica a todos os widgets que permitem que você crie fluxos com base em um modelo, incluindo widgets de Fluxos, FlowCreation e de Modelos.

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

| Parâmetro |Obrigatório/opcional | Descrição                                                                        
|-----------|-------------------|-----------------| 
|`defaultParams` | Opcional          | Os parâmetros de tempo de design a serem usados ao criar um fluxo com base em um modelo, por exemplo: <br /> ``` defaultParams: {'parameters.sharepoint.site': 'https://microsoft.sharepoint.com/teams/ProcessSimple', 'parameters.sharepoint.list': 'b3a5baa8-fe94-44ca-a6f0-270d9f821668'   } ```| 
| `destination` | Opcional          | Os valores válidos são “novo” ou “detalhes”. Quando definidos como “detalhes”, uma página de detalhes é mostrada ao criar um fluxo com base em um modelo.     |
| `pageSize` | Opcional          | Número de modelos a ser exibido. Tamanho padrão = 6 | 
| `searchTerm` | Opcional          | Exibir modelos que correspondem ao termo de pesquisa fornecido| 
| `templateCategory` | Opcional          | Exibir modelos em uma categoria específica| 
 
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
| Parâmetro | Obrigatório/opcional | Descrição | 
|------------|-------------------|--------------| 
| `hideLink`| Opcional | Quando definido como `true`, o widget oculta os links de aprovação recebida e enviada | 
| `autoNavigateToDetails`| Opcional | Quando definido como `true`, o widget abre automaticamente os detalhes de aprovação quando há somente uma aprovação | 
| `approvalsFilter`| Opcional | O widget de aprovação aplicará o filtro de aprovação especificado ao listar as aprovações, por exemplo:    O widget de aprovação aplicará o filtro de aprovação especificado ao listar as aprovações, por exemplo: <br/> ``` approvalsFilter: 'properties/itemlink eq \'https://microsoft.sharepoint.com/teams/ProcessSimple/_layouts/15/listform.aspx?PageType=4&ListId=737e30a6-5bc4-4e9c-bcdc-d34c5c57d938&ID=3&ContentTypeID=0x010010B708969A9C16408696FD23801531C6\'' ```  <br/> <br/>``` approvalsFilter: 'properties/itemlinkencoded eq \'{Your base64 encoded item link url} \'' ```|
| `tab`| Opcional | Guia ativa padrão a ser mostrada no widget de Fluxo. <br/> Valores válidos: “receivedApprovals”, “sentApprovals” | 
| `showSimpleEmptyPage`| Opcional | Mostra uma página vazia quando não há aprovações | 
| `hideInfoPaneCloseButton` | Opcional | Oculta o botão Fechar do painel de informações (ou o host já tem um botão Fechar) | 

<!-- why isn't this: hideInfoPaneCloseButton listed in the approvalCenterSettings? call since other optionals are there -->

## <a name="widget-events"></a>Eventos de widget

O widget do Microsoft Flow dá suporte a eventos que permitem que o host escute eventos de ciclo de vida do widget. O widget do Microsoft Flow dá suporte a dois tipos de eventos: eventos de notificação unidirecionais (por exemplo, Widget\_Ready) e eventos gerados do widget para efetuar fetch dos dados do host (Get\_Access\_Token). O host precisa usar o método widget.listen() para escutar eventos específicos gerados do widget.

### <a name="usage"></a>Uso

```javascript
widget.listen("<WIDGET_EVENT>", function() {
    console.log("The flow widget raised event");
});
```

### <a name="supported-events-by-widget-type"></a>Eventos com suporte pelo tipo de widget

| Evento de widget      | Detalhes                                                         | 
|-------------------|-----------------------------------------------------------------| 
| `WIDGET_READY`      | Widget carregado com sucesso                                      | 
| `WIDGET_RENDERED`   | Widget carregado e a renderização de interface do usuário está concluída                      | 
| `GET_ACCESS_TOKEN`  | Solicitação de widget para inserir token de acesso de usuário                      | 
| `GET_STRINGS`       | Permite que o host substitua um conjunto de cadeias de caracteres de interface do usuário mostrado no widget | 

### <a name="runtime-widget"></a>Widget de tempo de execução

| Evento de widget                    | Detalhes                                     | Dados                                              | 
|---------------------------------|---------------------------------------------|-----------| 
| `RUN_FLOW_STARTED`                | Disparados e a execução de fluxo foi iniciada      |           | 
| `RUN_FLOW_COMPLETED`              | Execução de fluxo disparada com êxito             |           | 
| `RUN_FLOW_DONE_BUTTON_CLICKED`    | O usuário selecionou o botão Concluído na execução de fluxo       |           | 
| `RUN_FLOW_CANCEL_BUTTON_CLICKED`  | O usuário selecionou o botão Cancelar na execução de fluxo     |           | 
| `FLOW_CREATION_SUCCEEDED`         | O fluxo foi criado com êxito           |`{ flowUrl: string, flowId: string, fromTemplate: string } `|
| `WIDGET_CLOSE`                    | Acionado quando o host deveria fechar o widget |       | 

### <a name="flow-creation-widget"></a>Widget de criação de fluxo

| Evento de widget             | Detalhes                                  | Dados  | 
|--------------------------|------------------------------------------|-------| 
| `FLOW_CREATION_FAILED`     | Falha na criação do fluxo                     |       | 
| `WIDGET_CLOSE`             | Acionado quando o host deveria fechar o widget  |       | 
| `TEMPLATE_LOAD_FAILED`     | Falha no carregamento do modelo              |       | 
| `FLOW_CREATION_SUCCEEDED`  | O fluxo foi criado com êxito        |` { flowUrl: string, flowId: string,fromTemplate?: string } `| 

### <a name="approval-widget"></a>Widget de aprovação

| Evento de widget                      | Detalhes                             | 
|-----------------------------------|-------------------------------------| 
| `RECEIVED_APPROVAL_STATUS_CHANGED`  | Status de aprovação recebida alterado  | 
| `SENT_APPROVAL_STATUS_CHANGED`      | Status de aprovação enviada alterado      | 

O evento **GET\_STRINGS** permite que você personalize o texto para alguns dos elementos de interface do usuário mostrados no widget. As cadeias de caracteres a seguir podem ser personalizadas:

| Chave da cadeia de caracteres                     | Usar no widget                                                                                                                  | 
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------| 
| `FLOW_CREATION_CREATE_BUTTON`    | Texto exibido no botão Criar fluxo no widget de criação de fluxo e de tempo de execução                                                | 
| `FLOW_CREATION_CUSTOM_FLOW_NAME` | O valor inicial a ser usado para o nome do fluxo no widget de criação de fluxo. Usado somente quando a configuração allowCustomFlowName está habilitada. | 
| `FLOW_CREATION_HEADER`           | Cabeçalho a ser usado ao criar um fluxo no widget de criação de fluxo e de tempo de execução                                                    | 
| `INVOKE_FLOW_HEADER`             | Cabeçalho a ser usado ao invocar um fluxo no widget de tempo de execução                                                                           | 
| `INVOKE_FLOW_RUN_FLOW_BUTTON`    | Texto exibido no botão usado para invocar/executar um fluxo no widget de tempo de execução                                                       | 

### <a name="example"></a>Exemplo

Chame `widgetDoneCallback` passando um objeto JSON com pares de chave-valor de chave de cadeia de caracteres e o texto para substituir o valor padrão.

```javascript
widget.listen("GET_STRINGS", function(requestParam, widgetDoneCallback) {
    widgetDoneCallback(null, {
         "FLOW_CREATION_HEADER": "<string override would go here>",
        "INVOKE_FLOW_RUN_FLOW_BUTTON":  "<string override would go here>"
    });
});
```

## <a name="widget-actions"></a>Ações de widget

O host usa ações de widget para enviar uma mensagem ou uma ação específica ao widget. O widget SDK do JS fornece o método `notify()` para enviar uma mensagem ou um conteúdo JSON para o widget. Cada ação do widget é compatível com uma assinatura de conteúdo específica.

### <a name="usage"></a>Uso

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

| Ação de widget                               | Detalhes                                                      | Interface de parâmetro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `triggerFlow`                                 | Dispara uma execução de fluxo                                          | `{ flowName: string, implicitData?: string } `| 
| `triggerFlowByTemplate`                       | Dispara uma execução de fluxo por modelo                              | `{ templateId: string, implicitData?: string, designTimeParameters?: Record<string, any> }` |
| `getTriggerSchema`                            | Obtém o esquema de gatilho para um fluxo                               | `{   flowName: string, }` | 
| `closeWidget`                                 | Cancela qualquer atividade pendente e gera um evento WIDGET_CLOSE |                      | 

### <a name="flow-creation-widget"></a>Widget de criação de fluxo

| Ação de widget                               | Detalhes                                                      | Interface de parâmetro  | 
|---------------------------------------------|--------------------------------------------------------------|----------------------| 
| `createFlowFromTemplate`                      | Cria um fluxo para o modelo selecionado                     | `{ templateName: string, designTimeParameters?: Record<string, any> }`| 
| `createFlowFromTemplateDefinition`            | Cria um fluxo para a definição de modelo selecionada          | `{ templateDefinition: string }` | 
| `closeWidget`                                 | Cancela qualquer atividade pendente e gera um evento WIDGET_CLOSE |                      | 

### <a name="approval-widget"></a>Widget de aprovação

| Ação de widget  | Detalhes                                           | Interface de parâmetro  | 
|----------------|---------------------------------------------------|----------------------| 
| `closeInfoPane`  | Fecha o painel de informações que exibe os detalhes da aprovação  | N/D                  | 

## <a name="configuring-your-client-application"></a>Configurando seu aplicativo cliente

Será necessário configurar seu aplicativo cliente com Escopos de serviço de fluxo (permissões delegadas). Se o aplicativo do AAD (Azure Active Directory) usado para integração de widget usar um fluxo de autorização de “concessão de código”, o aplicativo AAD precisará ser reconfigurado com permissões delegadas compatíveis com o Microsoft Flow. Isso oferece permissões delegadas que permitem ao aplicativo:

-   Gerenciar aprovações
-   Ler aprovações
-   Ler atividades
-   Gerenciar fluxos
-   Ler fluxos

Sigas estas etapas para selecionar uma ou mais permissões delegadas:

1.  Acesse https://portal.azure.com 
2.  Selecione **Azure Active Directory**.
3.  Selecione **Registros de aplicativo** em **Gerenciar**.
4.  Insira o aplicativo de terceiros a ser configurado para Escopos de serviço de fluxo.
5.  Selecione **Configurações**.
      ![arquitetura do widget](../media/embed-flow-dev/AAD-App-Settings.png)
6. Selecione **Permissões necessárias** em **Acesso à API**/
7. Selecione **Adicionar**.
8. Escolha **Selecionar uma API**.
      ![arquitetura do widget](../media/embed-flow-dev/AAD-App-Select-an-API.png)
9. Pesquise o **serviço do Microsoft Flow** e selecione-o. Observação: antes de poder ver o serviço do Microsoft Flow, seu locatário precisa ter pelo menos um usuário do AAD conectado ao portal do fluxo (<https://flow.microsoft.com>)
10. Escolha os escopos de fluxo necessários para seu aplicativo e, em seguida, selecione **Salvar**.
      ![arquitetura do widget](../media/embed-flow-dev/AAD-App-DelegatedPermissions.png)

Agora seu aplicativo obterá um token de Serviço de fluxo que contém as permissões delegadas na declaração \'scp' no token JWT.

## <a name="sample-application-embedding-flow-widgets"></a>Aplicativo de exemplo inserindo widgets de fluxo 

Um SPA (Aplicativo de Página Única) JavaScript de exemplo é fornecido na seção de recursos para você poder experimentar a inserção de widgets de fluxo em uma página de host. O uso do aplicativo de exemplo requer o registro de um aplicativo AAD com fluxo de concessão implícita habilitado.

### <a name="registering-an-aad-app"></a>Registrando um aplicativo AAD

1.  Entre no [portal do Azure](https://portal.azure.com/).
2.  No painel de navegação esquerdo, selecione **Azure Active Directory** e, em seguida, selecione **Registros de aplicativo** (Versão prévia) \> Novo registro.
3.  Quando a página **Registrar um aplicativo** for exibida, insira um nome para seu aplicativo.
4.  Em **Tipos de conta com suporte**, selecione **Contas** em qualquer diretório organizacional.
5.  Na seção **URL de redirecionamento**, selecione a plataforma da Web e defina o valor para a URL o aplicativo com base em seu servidor Web.  Configure esse valor como http://localhost:30662/ para executar o aplicativo de exemplo.
6.  Selecione **Registrar**.
7.  Na página **Visão geral** do aplicativo, anote o valor da ID do aplicativo (cliente).
8.  O exemplo requer que o [fluxo de concessão implícita](https://docs.microsoft.com/azure/active-directory/develop/v2-oauth2-implicit-grant-flow) esteja habilitado. No painel de navegação esquerdo do aplicativo registrado, selecione **Autenticação**.
9.  Em **Configurações avançadas**, em **Concessão implícita**, marque as caixas de seleção **Tokens de ID** e **Tokens de acesso**. Os tokens de ID e de acesso são necessários, pois o aplicativo precisa conectar os usuários e chamar a API do fluxo.
10. Selecione **Salvar**.

### <a name="running-the-sample"></a>Executando o exemplo
<!-- todo where should I download from? -->
<!-- todo is this a misspelling: applicaionConfig -->
1.  Baixe o exemplo e copie-o para uma pasta local em seu dispositivo.
2.  Abra o arquivo index.html na pasta FlowSDKSample e modifique o `applicaionConfig` para atualizar o `clientID` para a ID do aplicativo registrada anteriormente.
    ![arquitetura do widget](../media/embed-flow-dev/SampleApp-ApplicationConfig.png)
3.  O aplicativo de exemplo é configurado para usar os escopos de fluxo **Flows.Read.All** e **Flow.Manage.All.** É possível configurar escopos adicionais atualizando a propriedade **flowScopes** no objeto **applicationConfig**.
4.  Execute estes comandos para instalar a dependência e execute o aplicativo de exemplo:
    > \> npm install \> node server.js
5. Abra o navegador e, em seguida, insira http://localhost:30662
6. Selecione o botão **Entrar** para se autenticar no AAD e adquirir um token de acesso de fluxo.
7. A caixa de texto **Token de acesso** contém o token de acesso.
    ![arquitetura do widget](../media/embed-flow-dev/SampleApp-AccessToken.png)
8. Selecione **Carregar widget de fluxos** ou **Carregar widget de modelos** para inserir os widgets correspondentes.
    ![arquitetura do widget](../media/embed-flow-dev/SampleApp-TemplatesWidget.png)

[Link de download](https://procsi.blob.core.windows.net/docs/FlowWidgetSampleApp.zip) do aplicativo de exemplo.

## <a name="resources"></a>Recursos

### <a name="widget-test-pages"></a>Páginas de teste do widget

Descubra mais sobre a integração e as configurações do widget:

- Widget de modelos: <[https://flow.microsoft.com/en-us/test/templateswidget/](https://flow.microsoft.com/en-us/test/templateswidget/)>
- Widget FlowCreation: <[https://flow.microsoft.com/en-us/test/flowcreationwidget/](https://flow.microsoft.com/en-us/test/flowcreationwidget/)>
- Widget de tempo de execução: <[https://flow.microsoft.com/en-us/test/runtimewidget/](https://flow.microsoft.com/en-us/test/runtimewidget/)>
- Widget do centro de aprovações: <[https://flow.microsoft.com/en-us/test/approvalcenterwidget/](https://flow.microsoft.com/en-us/test/approvalcenterwidget/)>
- Widget de fluxos: <[https://flow.microsoft.com/en-us/test/managewidget/](https://flow.microsoft.com/en-us/test/managewidget/)>

### <a name="supported-widget-locales"></a>Localidades de widget com suporte

Se a localidade inicializada não estiver listada, o padrão do fluxo será a localidade com suporte mais próxima.

| Localidade     | Idioma                   | 
|------------|----------------------------| 
| bg-bg      | Búlgaro (Bulgária)       | 
| ca-es      | Catalão (Espanha)            | 
| cs-cz      | Tcheco (República Tcheca)     | 
| da-dk      | Dinamarquês (Dinamarca)           | 
| de-de      | Alemão (Alemanha)           | 
| el-gr      | Grego (Grécia)             | 
| en-Us      | Inglês (Estados Unidos)    | 
| es-es      | Espanhol (Castelhano)        | 
| et-ee      | Estoniano (Estônia)         | 
| eu-es      | Basco (Espanha)             | 
| fi-fi      | Finlandês (Finlândia)          | 
| fr-fr      | Francês (França)            | 
| gl-es      | Galego (Espanha)           | 
| hi-HU      | Húngaro (Hungria)        | 
| hi-in      | Hindi (Índia)              | 
| hr-hr      | Croata (Croácia)         | 
| id-Id      | Indonésio (Indonésia)     | 
| it-It      | Italiano (Itália)            | 
| jp-Jp      | Japonês (Japão)           | 
| kk-kz      | Cazaque (Cazaquistão)        | 
| ko-kr      | Coreano (Coreia do Sul)             | 
| lt-LT      | Lituano (Lituânia)     | 
| lv-lv      | Letão (Letônia)           | 
| ms-my      | Malaio (Malásia)           | 
| nb-no      | Norueguês (Bokmål)         | 
| nl-nl      | Holandês (Países Baixos)        | 
| pl-pl      | Polonês (Polônia)            | 
| pt-br      | Português (Brasil)        | 
| pt-pt      | Português (Portugal)      | 
| ro-ro      | Romeno (Romênia)         | 
| ru-ru      | Russo (Rússia)           | 
| sk-sk      | Eslovaco (Eslováquia)          | 
| sl-si      | Esloveno (Eslovênia)       | 
| sr-cyrl-rs | Sérvio (Cirílico, Sérvia) | 
| sr-latn-rs | Sérvio (Latino, Sérvia)    | 
| sv-se      | Sueco (Suécia)           | 
| th-th      | Tailandês (Tailândia)            | 
| tr-tr      | Turco (Turquia)           | 
| uk-ua      | Ucraniano (Ucrânia)        | 
| vi-vn      | Vietnamita (Vietnã)      |
