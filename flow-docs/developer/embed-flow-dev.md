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
ms.date: 05/09/2017
ms.author: barathb
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 738e566a9b064231a3bc2fe8bf7317df2bafbfef
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462799"
---
# <a name="integrate-microsoft-flow-with-websites-and-apps"></a>Integre o Microsoft Flow a sites e aplicativos
Insira o Microsoft Flow diretamente em seu aplicativo ou site para fornecer aos usuários uma maneira simples de automatizar suas tarefas profissionais ou pessoais.

Para criar fluxos, os usuários precisarão de um **Conta da Microsoft** ou uma conta corporativa ou de estudante no **Azure Active Directory**. O Microsoft Flow não dá suporte, por exemplo, a uma solução whitelabel que dão suporte a qualquer identidade que o sistema usa (a menos que já utilize Contas da Microsoft ou o AAD).

## <a name="prerequisites"></a>Pré-requisitos
* [Crie um conector personalizado](register-custom-api.md) que conecte seu serviço ao Microsoft Flow.
* [Crie e publique um ou mais modelos](../publish-a-template.md) que usem a API.

## <a name="show-templates-for-your-scenarios"></a>Mostrar modelos de cenários
Para iniciar, adicione este código para mostrar os modelos de fluxo diretamente no seu site:

```html
<iframe src="https://flow.microsoft.com/{locale}/widgets/templates/?q={search term}
&pagesize={number of templates}&destination={destination}"></iframe>
```

**Observação**: adicionamos uma quebra de linha para que o código possa ser exibido melhor na página.

| Parâmetro | Descrição |
| --- | --- |
| localidade |O código de região e o idioma de quatro letras para o modo de exibição do modelo. Por exemplo, `en-us` representa inglês americano e `de-de` representa o alemão. |
| termo de pesquisa |O termo de pesquisa para os modelos que você quer mostrar na exibição. Por exemplo, pesquise por `wunderlist` para mostrar modelos do Wunderlist. |
| número de modelos |O número de modelos que você quer mostrar na exibição. |
| destino |A página que é aberta quando os usuários clicam no modelo. Especifique `details` para mostrar os detalhes sobre o modelo ou especifique `new` para abrir o designer do Microsoft Flow. |
| parâmetros. {nome} |Contexto adicional para passar para o fluxo. |

Se o parâmetro de destino for `new`, o Microsoft Flow será aberto quando os usuários clicarem em um modelo e poderão criar um fluxo no designer. Se você quiser ter a experiência completa de trabalho de dentro do aplicativo, consulte a próxima seção.

### <a name="passing-additional-parameters-to-the-flow"></a>Passando parâmetros adicionais para o fluxo
Se o usuário estiver em determinado contexto em seu site ou aplicativo, passe esse contexto para o fluxo. Por exemplo, um usuário pode abrir um modelo para *Notificar quando um item é adicionado a uma lista* enquanto procura em determinada lista no Wunderlist. Seguindo essas etapas, você pode passar a ID da lista como um *parâmetro* ao fluxo:

1. Defina o parâmetro no modelo de fluxo antes de publicá-lo. Um parâmetro tem aparência `@{parameters('parameter_name')}`.
2. Passe o parâmetro no src iframe. Por exemplo, adicione `&parameters.listName={the name of the list}` se você tiver um parâmetro chamado **listName**.

### <a name="full-sample"></a>Exemplo completo
Para mostrar os quatro melhores modelos sobre o Wunderlist em alemão e iniciar o usuário com **myCoolList**:

```html
<iframe src="https://flow.microsoft.com/de-de/widgets/templates/?q=wunderlist
&pagesize=4&destination=details&parameters.listName=myCoolList"></iframe>
```

## <a name="embed-the-management-of-flows"></a>Inserir o gerenciamento de fluxos
Use o SDK de fluxo autenticado para permitir aos usuários criar e gerenciar fluxos diretamente de seu site ou aplicativo (em vez de navegar para o portal do Microsoft Flow). Você precisará subscrever o usuário na Conta da Microsoft ou do Azure Active Directory para usar o SDK autenticado.

> [!NOTE]
> Todos os usuários que usam o Microsoft Flow em seu aplicativo serão usuários do Microsoft Flow. Não é possível ocultar a identidade visual do Microsoft Flow.
> 
> 

### <a name="include-the-javascript-for-the-authenticated-sdk"></a>Incluir o JavaScript para o SDK autenticado
Inclua o SDK no código HTML, seguindo este exemplo. Você também pode baixar, minificar e empacotar o SDK com o produto.

```javascript
<script src="https://flow.microsoft.com/content/msflowsdk-1.1.js" async defer></script>
```

### <a name="create-a-container-to-contain-the-view"></a>Criar um contêiner para conter a exibição
Adicione um div HTML:

```html
<div id="flowDiv" class="flowContainer"></div>
```

É recomendável que o estilo desse contêiner apareça com as dimensões apropriadas em sua experiência:

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

Observe que o iframe não renderizará corretamente abaixo de 320 pixels de largura e não preencherá o conteúdo acima de 1.200 pixels de largura. Qualquer altura deve funcionar.

### <a name="authentication-against-the-sdk"></a>Autenticação no SDK
Para listar os fluxos que o usuário já criou e também para criar fluxos de modelos, forneça um authToken do AAD.

```javascript
<script>
    window.msFlowSdkLoaded = function() {
        var sdk = new MsFlowSdk({
            hostName:'https://flow.microsoft.com'
        });
        var widget = sdk.renderWidget('flows', {
            container: 'flowDiv',
            environmentId: '[environmentId]'    // find environment id from browser URL when you 
                                                // click on 'my flows'
                                                //ex: https://flow.microsoft.com/manage/environments/[environmentId]/flows
        });
        widget.callbacks.GET_ACCESS_TOKEN = function(requestParam, widgetDoneCallback)
       {
            var authCallback = function(token) {
                widgetDoneCallback(null, {
                    token: token // Get AAD access token from your backend system
                });
            };
        }
    }
</script>
```

Você pode encontrar o `environmentId` fazendo a seguinte chamada de API, que retorna a lista de ambientes na qual o usuário tem acesso:

```http
GET https://management.azure.com/providers/Microsoft.ProcessSimple/environments
?api-version=2016-11-01 
```

Isso retorna uma resposta JSON com a lista de ambientes, na qual você pode escolher qualquer ambiente. Você pode procurar o ambiente de usuário padrão, verificando a propriedade `properties.isDefault=true`.

Neste exemplo, `requestParam` é definido como:

```javascript
export interface IRpcRequestParam {
    callInfo: IRpcCallInfo,
    data?: any;
}
```

Em seguida, o `widgetDoneCallback` é uma função de retorno de chamada que precisa ser chamada uma vez que o host tem o token. Isso é feito porque a aquisição de token é provavelmente um processo assíncrono. Os parâmetros que precisam ser passados ao chamar essa função são `(errorResult: any, successResult: any)`. O successResult dependerá do tipo de retorno de chamada. Para `GetAccessToken` o tipo é:

```javascript
export interface IGetAccessTokenResult {
    token: string;
}
```
