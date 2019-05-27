---
title: Filtrar e copiar dados | Microsoft Docs
description: Aprenda a filtrar e copiar dados de uma fonte para um destino com o Microsoft Flow
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
ms.date: 09/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 702fd695a91fdf267f166d5162570b39505dbc91
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64465883"
---
# <a name="filter-and-copy-data-with-microsoft-flow"></a>Filtrar e copiar dados com o Microsoft Flow
Este passo a passo mostra como criar um fluxo que monitora uma origem para itens novos ou alterados e, em seguida, copia as alterações para um destino. Você pode criar um fluxo como este se seus usuários inserem dados em um local, mas sua equipe precisa deles em um local ou formato diferente.

Embora este passo a passo copie dados de uma [lista](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194) (a origem) do Microsoft SharePoint para uma tabela (destino) do [Banco de dados SQL do Azure](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview) , você pode copiar dados entre qualquer um dos mais de [150 serviços](https://flow.microsoft.com/connectors/) que aos quais o Microsoft Flow oferece suporte.

> [!IMPORTANT]
> As alterações feitas no destino não são copiadas para a fonte porque não há suporte para as sincronizações bidirecionais. Se você tentar configurar uma sincronização bidirecional, criará um loop infinito, onde as alterações são enviadas indefinidamente entre a origem e destino.
> 
> 

## <a name="prerequisites"></a>Pré-requisitos
* Acesso a uma fonte de dados e um destino. Este passo a passo não inclui etapas para criar a origem e o destino.
* acesso ao [Microsoft Flow](https://flow.microsoft.com).
* Um entendimento básico de como os dados estão armazenados.
* Familiaridade com os conceitos básicos de criação de fluxos. Você pode examinar como adicionar [ações, disparadores](multi-step-logic-flow.md#add-another-action) e [condições](add-condition.md). As etapas a seguir pressupõem que você sabe como executar essas ações.

> [!TIP]
> Cada nome de coluna na origem e no destino não precisa corresponder, mas você deve fornecer dados para todas as colunas *necessárias* ao inserir ou atualizar um item. O Microsoft Flow identifica os campos obrigatórios para você.
> 
> 

## <a name="quick-overview-of-the-steps"></a>Visão geral das etapas
Se você estiver familiarizado com o Microsoft Flow, utilize estas etapas rápidas para copiar dados de uma fonte de dados para outra:

1. Identificar a origem que será monitorada e o destino para o qual você copiará os dados alterados. Confirme que tem acesso a ambos.
2. Identifique pelo menos uma coluna que identifica exclusivamente itens na origem e no destino. No exemplo a seguir, usamos a coluna **Título**, mas você pode usar a coluna que desejar.
3. Configure um gatilho que monitora a origem para as alterações.
4. Pesquise o destino para determinar se existe um item alterado.
5. Use uma **Condição** com esta aparência:
   * Se o item novo ou alterado não existir no destino, crie-o.
   * Se o item novo ou alterado existir no destino, atualize-o.
6. Dispare seu fluxo e, em seguida, confirme que os itens novos ou alterados estão sendo copiados da origem para o destino.

> [!NOTE]
> Se você não tiver criado anteriormente uma conexão no SharePoint ou no Banco de Dados SQL do Azure, siga as instruções quando for solicitado a entrar.
> 
> 

Aqui estão as etapas detalhadas para criar o fluxo.

## <a name="monitor-the-source-for-changes"></a>Monitore a origem para obter as alterações
1. Entre no [Microsoft Flow](https://flow.microsoft.com), selecione **Meus fluxos** > **Criar de um modelo em branco**.
2. Procure por **SharePoint** > selecione o **SharePoint - Quando um item é criado ou modificado** dispara da lista de gatilhos.
3. Insira o **Endereço do Site** e, em seguida, selecione o **Nome da Lista** no cartão **Quando um item é criado ou modificado**.
   
    Selecione o **Endereço do Site** e o **Nome da Lista** para a lista do SharePoint que seu fluxo monitora para itens novos ou atualizados.
   
    ![configurar o gatilho do SharePoint](media/odata-filters/configure-sharepoint-trigger.png)

## <a name="search-the-destination-for-the-new-or-changed-item"></a>Pesquisar o destino para o item novo ou alterado
Usamos a ação **SQL Server - Obter linhas** para pesquisar o destino para o item novo ou alterado.

1. Selecione **Nova etapa** > **Adicionar uma ação**.
2. Procure por **Obter linhas**, selecione **SQL Server - Obter linhas** e, em seguida, selecione a tabela que você deseja monitorar na lista **Nome da Tabela**.
3. Selecione **Mostrar opções avançadas**.
4. Na caixa **Consulta de Filtro**, digite **Title eq '**, selecione o token **Title** na lista de conteúdo dinâmico e, em seguida, digite **'**.
   
    A etapa anterior pressupõe que você está correspondendo aos Títulos das linhas na origem e no destino.
   
    O cartão **Obter linhas** agora deve ser semelhante a esta imagem:
   
    ![tente obter o item do banco de dados de destino](media/odata-filters/configure-sql-get-rows-action.png)

## <a name="check-if-the-new-or-changed-item-was-found"></a>Verifique se o item novo ou alterado foi encontrado
Selecione **Nova etapa** > **Adicionar uma condição** para abrir o cartão **Condição**.

No cartão de condição:

1. Marque a caixa à esquerda.
   
    A lista **Adicionar conteúdo dinâmico a partir de aplicativos e conectores usados neste fluxo** é aberta.
2. Selecione **valor** na categoria **Obter linhas**.
   
   > [!TIP]
   > Confirme que você selecionou **valor** na categoria **Obter linhas**. Não selecione **valor** na categoria **Quando um item é criado ou modificado**.
   > 
   > 
3. Selecione **é igual a** na lista na caixa central.
4. Digite **0** (zero) na caixa à direita.
   
    O cartão **Condição** agora é semelhante a esta imagem:
   
    ![configurar uma condição](media/odata-filters/configure-condition.png)
5. Selecione **Editar no modo avançado**.
   
    Quando o modo avançado é aberto, você vê a expressão **\@equals(body('Get_rows')?['value'], 0)** na caixa. Edite esta expressão adicionando **length()** na função **body('Get_items')?['valor']**. A expressão inteira agora é exibida da seguinte maneira: **@equals(length(body('Get_rows')?['value']), 0)**
   
    O cartão **Condição** agora é semelhante a esta imagem:
   
    ![configurar uma condição](media/odata-filters/configure-condition-add-length.png)
   
   > [!TIP]
   > Adicionar a função **length()** permite que o fluxo verifique a lista **value** e determine se ela contém todos os itens.
   > 
   > 

Quando o fluxo "obtém" itens de destino, há dois resultados possíveis.

| Resultado | Próxima etapa |
| --- | --- |
| O item existe |[Atualizar o item](odata-filters.md#update-the-item-in-the-destination) |
| O item não existe |[Criar um novo item](odata-filters.md#create-the-item-in-the-destination) |

> [!NOTE]
> As imagens dos cartões **Inserir linha** e **Atualizar linha** mostradas a seguir podem ser diferentes da sua porque esses cartões mostram os nomes das colunas na tabela de Banco de dados SQL do Azure que estão sendo usados no fluxo.
> 
> 

## <a name="create-the-item-in-the-destination"></a>Criar o item no destino
Se o item não existe no destino, crie-o usando a ação **SQL Server - Inserir linha**.

Na ramificação **Se Sim** da **Condição**:

1. Selecione **Adicionar uma ação**, procure **inserir linha** e, em seguida, selecione **SQL Server - Inserir linha**.
   
    O cartão **Inserir linha** é aberto.
2. Na lista **Nome da tabela**, selecione a tabela na qual o novo item será inserido.
   
    O cartão **Inserir linha** expande e exibe todos os campos na tabela selecionada. Campos com um asterisco (*) são necessários e devem ser preenchidos para que a linha seja válida.
3. Selecione cada campo que você deseja preencher e insira os dados.
   
    Você pode inserir os dados manualmente, selecionar um ou mais tokens do **Conteúdo dinâmico**, ou inserir qualquer combinação de texto e tokens nos campos.
   
    O cartão **Inserir linha** agora é semelhante a esta imagem:
   
    ![configurar uma condição](media/odata-filters/insert-row.png)

## <a name="update-the-item-in-the-destination"></a>Atualizar o item no destino
Se o item existir no destino, atualize-o com as alterações.

1. Adicione a ação **SQL Server - Atualizar linha** para a ramificação **Se nenhum** da **Condição**.
2. Siga as etapas na seção [criar o item](odata-filters.md#create-the-item-in-the-destination) deste documento para preencher os campos da tabela.
   
    ![exibir ambientes](media/odata-filters/update-row.png)
3. Na parte superior da página, insira um nome para o fluxo na caixa **Nome do fluxo** e, em seguida, selecione **Criar fluxo** para salvá-lo.
   
    ![atribuir um nome ao fluxo](media/odata-filters/give-the-flow-a-name.png)

Agora, sempre que um item é alterado em sua lista (origem) do SharePoint, seu fluxo dispara e insere um novo item ou atualiza um item existente em seu Banco de Dados SQL do Azure (destino).

> [!NOTE]
> O fluxo não é disparado quando um item é excluído da fonte. Se esse for um cenário importante, considere adicionar uma coluna separada que indica quando um item não for mais necessário.
> 
> 

## <a name="learn-more"></a>Saiba mais
Use [operações de dados](data-operations.md) em seus fluxos.

