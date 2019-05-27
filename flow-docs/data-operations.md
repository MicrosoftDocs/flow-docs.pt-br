---
title: Entender as operações de dados | Microsoft Docs
description: Saiba como realizar operações, como criar uma tabela HTML, uma tabela CSV, compor, unir, selecionar e filtrar uma matriz com o Microsoft Flow.
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
ms.openlocfilehash: c28fa7feb743db4616199246d6d517e2e1f6aff9
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64457881"
---
# <a name="use-data-operations-with-microsoft-flow"></a>Usar as operações de dados com o Microsoft Flow
Neste passo a passo, conheça algumas das operações de dados populares do Microsoft Flow, como compor, unir, selecionar, filtrar uma matriz, criar uma tabela e analisar o JSON, disponíveis para manipular os dados ao criar fluxos.

## <a name="prerequisites"></a>Pré-requisitos
* Acesso ao Microsoft Flow.
* Uma ferramenta, como o [PostMan](https://www.getpostman.com/postman), para enviar solicitações HTTP POST com uma matriz JSON para o fluxo.

## <a name="use-the-compose-action"></a>Usar a ação de composição
Use a ação (de composição) **Operações de Dados - Compor** para não precisar inserir dados idênticos várias vezes durante a criação de um fluxo. Por exemplo, se você precisar inserir uma matriz de dígitos: ````[0,1,2,3,4,5,6,7,8,9]```` várias vezes enquanto cria o fluxo, poderá usar a ação de composição para salvar a matriz assim:

1. Pesquise **Compor** e, em seguida, selecione a ação (de composição) **Operações de Dados - Compor**.
   
    ![pesquisar e selecionar a ação de composição](./media/data-operations/search-select-compose.png)
2. Insira a matriz na caixa **Entradas** que você deseja referenciar depois:
   
    ![configurar a ação de composição](./media/data-operations/add-array-compose.png)

> [!TIP]
> Para facilitar a referência posterior, renomeie o cartão **Compor** clicando no texto "Compor" na barra de título do cartão **Compor**.
> 
> 

Quando você precisar acessar o conteúdo da ação de composição, faça isso via token **Saída** na lista **Adicionar conteúdo dinâmico a partir de aplicativos e conectores usados neste fluxo** seguindo estas etapas:

1. Adicione uma ação, como **Operações de Dados – Unir**.
2. Selecione o controle ao qual você gostaria de adicionar o conteúdo salvo na ação de composição.
   
    A lista **Adicionar conteúdo dinâmico a partir de aplicativos e conectores usados neste fluxo** é aberta.
3. Em **Adicionar conteúdo dinâmico a partir de aplicativos e conectores usados neste fluxo**, selecione o token **Saída** que está na categoria **Compor** da guia **Conteúdo dinâmico**.
   
    ![usar a saída da ação de composição](./media/data-operations/use-compose-output.png)

## <a name="use-the-join-action"></a>Usar a ação de união
Use a ação (União) **Operações de Dados - Unir** para delimitar uma matriz com um separador de sua escolha. Por exemplo, suponha que seu fluxo receba uma solicitação da Web que inclua a seguinte matriz de endereços de email: ````["d@example.com", "k@example.com", "dal@example.com"]````. No entanto, o programa de email requer que os endereços sejam uma única cadeia de caracteres separada por pontos e vírgulas. Para fazer isso, use a ação (união) **Operações de Dados - Unir** para alterar o delimitador de vírgula para um ponto e vírgula ";" seguindo estas etapas:

1. Adicione uma nova ação, pesquise **Unir** e, em seguida, selecione a ação (união) **Operações de Dados - Unir**.
   
    ![pesquisar e selecionar a ação de união](./media/data-operations/search-select-join.png)
2. Insira a matriz na caixa **De** e insira o novo delimitador que você deseja usar na caixa **Unir com**.
   
    Aqui, usei o ponto e vírgula (;) como o novo delimitador.
   
    ![configurar a ação de união](./media/data-operations/add-array-join.png)
3. Salve seu fluxo e execute-o.
4. Após a execução do fluxo, a saída da ação **Operações de Dados – Unir** será:
   
    ![saída da união](./media/data-operations/join-output.png)

## <a name="use-the-select-action"></a>Usar a ação de seleção
Use a ação (seleção) **Operações de Dados – Selecionar** para transformar a forma dos objetos em uma matriz. Por exemplo, você pode adicionar, remover ou renomear os elementos de cada objeto em uma matriz.

> [!NOTE]
> Embora você possa adicionar ou remover os elementos usando a ação de seleção, não pode alterar o número de objetos na matriz.
> 
> 

Por exemplo, será possível usar a ação de seleção se os dados inserirem seu fluxo via solicitação da Web neste formato:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

e você gostaria de remodelar os dados de entrada renomeando "primeiro" como "Nome", "último" como "Sobrenome" e adicionar um novo membro denominado "NomedeFamília" que combina o "primeiro" e o "último" (separados por um espaço):

````[ { "FirstName": "Deon", "FamilyName": "Herb", "FullName": "Deon Herb" }, { "FirstName": "K", "FamilyName": "Herb", "FullName": "K Herb" } ]````.

Para fazer isso:

1. Adicione a ação (solicitar) **Solicitação/Resposta – Resposta** ao fluxo.
2. Selecione **Usar o conteúdo de exemplo para gerar o esquema** no cartão **Solicitar**.
3. Na caixa exibida, cole um exemplo de sua matriz dos dados de origem e, em seguida, selecione o botão **Concluído**.
4. Adicione a ação (seleção) **Operações de Dados – Selecionar** e configure-a como a imagem a seguir.
   
    ![configurar a ação de seleção](./media/data-operations/select-card.png)
   
   > [!TIP]
   > A saída da ação de seleção é uma matriz que contém os objetos recém-modelados. Em seguida, você poderá usar essa matriz em qualquer outra ação, como **Compor**, analisada anteriormente.
   > 
   > 

## <a name="use-the-filter-array-action"></a>Usar a ação de filtro da matriz
Use a ação (filtro da matriz) **Operações de Dados - Filtrar matriz** para reduzir o número de objetos em uma matriz a um subconjunto que corresponda aos critérios fornecidos.

> [!NOTE]
> O filtro da matriz não pode ser usado para alterar a forma dos objetos em uma matriz. Além disso, o texto no qual você filtra diferencia as letras maiúsculas e minúsculas.
> 
> 

Por exemplo, você pode usar o filtro da matriz nesta matriz:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

para criar uma nova matriz que contenha apenas os objetos nos quais *primeiro* está definido como "Deon".

Vamos fazer isso.

1. Localize e adicione a ação (filtro da matriz) **Operações de Dados - Filtrar matriz** ao fluxo.
2. Configure a ação de filtro da matriz como a seguinte imagem.
   
    ![configurar a ação de filtro da matriz](./media/data-operations/add-configure-filter-array.png)
3. Salve e execute seu fluxo.
   
    Você pode usar [PostMan](https://www.getpostman.com/postman) para gerar uma solicitação da Web que envia uma matriz JSON para o fluxo.
4. Quando o fluxo é executado, supondo que a entrada JSON se pareça com essa matriz:
   
    ````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````,
   
    a saída se parece com essa matriz (observe que somente os objetos nos quais *primeiro* está definido como "Deon" são incluídos na saída da ação):
   
    ````[ { "first": "Deon", "last": "Herb" } ]````

## <a name="use-the-create-csv-table-action"></a>Usar a ação de criação da tabela csv
Use a ação (criação da tabela csv) **Operações de Dados – Criar tabela CSV** para alterar a entrada da matriz do JSON para uma tabela com valores separados por vírgula (CSV). Opcionalmente, você pode manter os cabeçalhos visíveis na saída CSV. Por exemplo, é possível converter a seguinte matriz em uma tabela CSV usando a ação **Criar tabela CSV**:

````[ { "first": "Deon", "last": "Herb" }, { "first": "K", "last": "Herb" } ]````

1. Localize, adicione e configure a ação **Operações de Dados – Criar tabela CSV** para parecer com a imagem a seguir.
   
    ![configurar a ação de criação da tabela csv](./media/data-operations/create-csv-table.png)
   
    Observação: O **corpo** token nesta imagem vem de uma **de solicitação / resposta – resposta** ação, no entanto, você pode obter a entrada para o **criar tabela CSV** ação da saída de qualquer ação anterior no fluxo ou você poderá inseri-lo diretamente para o **de** caixa.
2. Salve e execute seu fluxo.
   
    Quando o fluxo é executado, a saída **Criar tabela CSV** se parece com essa imagem:
   
    ![criar saída da tabela csv](./media/data-operations/create-csv-table-output.png)

## <a name="use-the-create-html-table-action"></a>usar a ação de criação da tabela csv
Use **Operações de Dados - Criar tabela HTML** para alterar uma entrada da matriz JSON para uma tabela HTML. Opcionalmente, você pode manter os cabeçalhos visíveis na saída HTML.

Para fazer isso, siga as etapas na [seção de criação da tabela csv](#use-the-create-csv-table-action) para obter um exemplo detalhado. Use a ação **Operações de Dados - Criar tabela HTML**, em vez da ação **Operações de Dados – Criar tabela CSV**.

> [!TIP]
> Se você planeja enviar a tabela HTML por email, lembre de selecionar "IsHtml" na ação de email.
> 
> 

