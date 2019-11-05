---
title: Entender as operações de dados | Microsoft Docs
description: Aprenda a executar operações, como criar tabela HTML, criar tabela CSV, compor, unir, selecionar e filtrar matriz com Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/02/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 87d805fb7de5ee9688e9e89c201be00fda8fb319
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547781"
---
# <a name="use-data-operations-with-microsoft-flow"></a>Usar operações de dados com o Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Neste tutorial, você aprende sobre algumas das operações de dados populares do Microsoft Flow, como compor, unir, selecionar, filtrar matriz, criar tabela e analisar JSON que estão disponíveis para manipular dados quando você cria fluxos.

## <a name="prerequisites"></a>Pré-requisitos
* Acesso a Microsoft Flow.
* Uma ferramenta como o [postmaster](https://www.getpostman.com/postman) para enviar solicitações HTTP post com uma matriz JSON para seu fluxo.

## <a name="use-the-compose-action"></a>Usar a ação de composição
Use a ação **Data Operations-compor** (compor) para evitar a inserção de dados idênticos várias vezes quando você estiver criando um fluxo. Por exemplo, se você precisar inserir uma matriz de dígitos: ````[0,1,2,3,4,5,6,7,8,9]```` várias vezes enquanto cria o fluxo, você pode usar a ação compor para salvar a matriz desta forma:

1. Pesquise **redigir**e selecione a ação operações de **dados-compor** (compor).
   
    ![Pesquisar e selecionar a ação de composição](./media/data-operations/search-select-compose.png)
2. Insira a matriz na caixa **entradas** que você deseja referenciar mais tarde:
   
    ![configurar a ação de composição](./media/data-operations/add-array-compose.png)

> [!TIP]
> Para uma referência mais fácil posteriormente, renomeie o cartão **compor** clicando no texto "compor" na barra de título do cartão de **composição** .
> 
> 

Quando você precisar acessar o conteúdo da ação compor, faça isso por meio do token de **saída** na lista **adicionar conteúdo dinâmico dos aplicativos e conectores usados neste fluxo** seguindo estas etapas:

1. Adicione uma ação como **operações de dados – ingressar**.
2. Selecione o controle ao qual você deseja adicionar o conteúdo que você salvou na ação de composição.
   
    O **adicionar conteúdo dinâmico dos aplicativos e conectores usados nesse fluxo** é aberto.
3. Em **adicionar conteúdo dinâmico dos aplicativos e conectores usados neste fluxo**, selecione o token de **saída** que está na categoria **compor** da guia **conteúdo dinâmico** .
   
    ![usar saída da ação de composição](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>Usar a ação de junção
Use a ação **operações de dados – junção** (junção) para delimitar uma matriz com um separador de sua escolha. Por exemplo, suponha que o fluxo receba uma solicitação da Web que inclua a seguinte matriz de endereços de email: ````["d@example.com", "k@example.com", "dal@example.com"]````. No entanto, seu programa de email exige que os endereços sejam uma única cadeia de caracteres separada com ponto e vírgula. Para fazer isso, use a ação **operações de dados – junção** (junção) para alterar o delimitador de vírgula para um ponto-e-vírgula ";" seguindo estas etapas:

1. Adicione uma nova ação, procure **ingressar**e, em seguida, selecione **operações de dados – ingressar** (ingressar).
   
    ![Pesquisar e selecionar a ação de junção](./media/data-operations/search-select-join.png)
2. Insira a matriz na caixa **de** e, em seguida, insira o novo delimitador que você deseja usar na caixa **ingressar com** .
   
    Aqui, usei o ponto-e-vírgula (;) como o novo delimitador.
   
    ![configurar a ação de junção](./media/data-operations/add-array-join.png)
3. Salve seu fluxo e, em seguida, execute-o.
4. Após a execução do fluxo, a saída da ação **operações de dados – junção** será:
   
    ![saída de junção](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Usar a ação selecionar
Use as **operações de dados – selecione** (selecionar) para transformar a forma dos objetos em uma matriz. Por exemplo, você pode adicionar, remover ou renomear elementos em cada objeto em uma matriz.

> [!NOTE]
> Embora você possa adicionar ou remover elementos usando a ação selecionar, não é possível alterar o número de objetos na matriz.
> 
> 

Por exemplo, você pode usar a ação selecionar se os dados entrarem no fluxo por meio de uma solicitação da Web neste formato:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

e você gostaria de remodelar os dados de entrada renomeando "First" para "FirstName", "Last" para "LastName" e adicionando um novo membro chamado "familyName" que combina "First" e "Last" (separados por um espaço):

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Para fazer isso:

1. Adicione a ação **solicitação/resposta – resposta** (solicitação) ao seu fluxo.
2. Selecione **usar o conteúdo de exemplo para gerar o esquema** a partir do cartão de **solicitação** .
3. Na caixa exibida, Cole uma amostra da matriz de dados de origem e, em seguida, selecione o botão **concluído** .
4. Adicione a ação **operações de dados – selecione** (selecionar) e, em seguida, configure-a como a imagem a seguir.
   
    ![configurar a ação Select](./media/data-operations/select-card.png)
   
   > [!TIP]
   > A saída da ação SELECT é uma matriz que contém os objetos recentemente moldados. Você pode usar essa matriz em qualquer outra ação, como **Compose**, discutida anteriormente.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Usar a ação filtrar matriz
Use **operações de dados – filtrar matriz** (matriz de filtro) para reduzir o número de objetos em uma matriz para um subconjunto que corresponda aos critérios fornecidos.

> [!NOTE]
> A matriz de filtro não pode ser usada para alterar a forma dos objetos em uma matriz. Além disso, o texto no qual você filtra diferencia maiúsculas de minúsculas.
> 
> 

Por exemplo, você pode usar a matriz de filtro nesta matriz:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

para criar uma nova matriz que contém somente objetos nos quais *First* está definido como "Deon".

Vamos fazer isso.

1. Localize e adicione a ação **Data Operations-Filter array** (Filter array) ao seu fluxo.
2. Configure a ação filtrar matriz como a imagem a seguir.
   
    ![Configurar ação de filtragem de matriz](./media/data-operations/add-configure-filter-array.png)
3. Salve e, em seguida, execute o fluxo.
   
    Você pode usar o [postmaster](https://www.getpostman.com/postman) para gerar uma solicitação da Web que envia uma matriz JSON para seu fluxo.
4. Quando o fluxo é executado, supondo que a entrada JSON seja semelhante a esta matriz:
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    a saída é semelhante a esta matriz (Observe que somente os objetos nos quais *primeiro* está definido como "Deon" são incluídos na saída da ação):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Usar a ação criar tabela CSV
Use a **tabela operações de dados – Create CSV** (criar tabela CSV) para alterar a entrada de uma matriz JSON em uma tabela de valores separados por vírgulas (CSV). Opcionalmente, você pode manter os cabeçalhos visíveis na saída CSV. Por exemplo, você pode converter a seguinte matriz em uma tabela CSV usando a ação **criar tabela CSV** :

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Localize, adicione e configure a ação **operações de dados – criar tabela CSV** para se parecer com a imagem a seguir.
   
    ![Configurar ação de criar tabela CSV](./media/data-operations/create-csv-table.png)
   
    Observação: o token de **corpo** nessa imagem é proveniente de uma ação de **solicitação/resposta – resposta** , no entanto, você pode obter a entrada para a ação **criar tabela CSV** da saída de qualquer ação anterior em seu fluxo ou pode inseri-la diretamente no Caixa **de** .
2. Salve e, em seguida, execute o fluxo.
   
    Quando o fluxo é executado, a saída **criar tabela CSV** é semelhante a esta imagem:
   
    ![criar saída de tabela CSV](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>Usar a ação criar tabela HTML
Usar **operações de dados – criar tabela HTML** para alterar uma entrada de matriz JSON em uma tabela HTML. Opcionalmente, você pode manter os cabeçalhos visíveis na saída HTML.

Para fazer isso, siga as etapas na [seção criar tabela CSV](#use-the-create-csv-table-action) para obter um exemplo detalhado. Certifique-se de usar a ação **operações de dados – criar tabela HTML** , em vez da ação **operações de dados – criar tabela CSV** .

> [!TIP]
> Se você planeja enviar a tabela HTML por email, lembre-se de selecionar "IsHtml" na ação de email.
> 
> 

