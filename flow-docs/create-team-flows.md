---
title: Saiba como adicionar outros proprietários a um fluxo e criar fluxos de equipe | Microsoft Docs
description: Microsoft Flow torna fácil automatizar tarefas repetitivas. Você pode adicionar usuários ou grupos como proprietários e colaborar com eles para projetar e gerenciar fluxos.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2a986568a44f8329e55fc62aef4705207cdfc49
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547618"
---
# <a name="create-team-flows"></a>Criar fluxos de equipe
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Crie um fluxo de equipe adicionando outros em sua organização como proprietários. Todos os proprietários de um fluxo de equipe podem executar estas ações:

* Exiba o histórico do fluxo (ou seja, cada execução).
* Gerenciar as propriedades do fluxo (por exemplo, iniciar ou parar o fluxo, adicionar proprietários ou atualizar credenciais para uma conexão).
* Edite a definição do fluxo (por exemplo, adicionar ou remover uma ação ou condição).
* Adicionar e remover outros proprietários (mas não o criador do fluxo).
* Exclua o fluxo.

Se você for o criador ou o proprietário de um fluxo de equipe, você o encontrará listado na guia **fluxos da equipe** em [Microsoft Flow](https://flow.microsoft.com).

![guia fluxos da equipe](./media/create-team-flows/addowner5.png)

> [!NOTE]
> As conexões compartilhadas podem ser usadas **somente** no fluxo em que foram criadas.
> 
> 

Os proprietários podem usar os serviços em um fluxo, mas não podem modificar as credenciais de uma conexão criada por outro proprietário.

## <a name="prerequisites"></a>Pré-requisitos
Você deve ter um [plano de Microsoft Flow pago](https://flow.microsoft.com/pricing/) para criar um fluxo de equipe. Além disso, você deve ser o criador ou proprietário para adicionar/remover proprietários de um fluxo de equipe.

## <a name="create-a-team-flow"></a>Criar um fluxo de equipe
Siga estas etapas para criar um fluxo de equipe ou para adicionar mais proprietários a um fluxo de equipe.

1. Entre no [Microsoft Flow](https://flow.microsoft.com)e, em seguida, selecione **meus fluxos**.
2. Selecione o ícone de pessoas para o fluxo que você deseja modificar:
   
    ![ícone da equipe](./media/create-team-flows/addowner1.png)
3. Insira o nome, o endereço de email ou o nome do grupo para a pessoa ou grupo que você deseja adicionar como proprietário:
   
    ![Pesquisar o usuário](./media/create-team-flows/addowner2.png)
4. Na lista exibida, selecione o usuário a quem você deseja criar um proprietário:
   
    ![selecionar o usuário](./media/create-team-flows/addowner3.png)
   
     O usuário ou grupo que você selecionou se torna um proprietário do fluxo:
   
    ![novo proprietário](./media/create-team-flows/addowner4.png)
   
     Parabéns &mdash; seu fluxo de equipe foi criado!

## <a name="add-a-list-as-a-co-owner"></a>Adicionar uma lista como um coproprietário

Você pode adicionar listas do SharePoint como coproprietários a um fluxo para que todos que tenham acesso de edição à lista automaticamente obtenham acesso de edição ao fluxo. Depois que o fluxo é compartilhado, você pode simplesmente distribuir um link para ele.

> [!TIP]
> Use uma lista quando o fluxo estiver conectado ao SharePoint e use um grupo em outros casos.
>

## <a name="remove-an-owner"></a>Remover um proprietário

> [!IMPORTANT]
> Ao remover um proprietário cujas credenciais são usadas para acessar os serviços do Microsoft Flow, você deve atualizar as credenciais para essas conexões para que o fluxo continue a ser executado corretamente.
> 
> 

1. Selecione o ícone de pessoas para o fluxo que você deseja modificar:
   
    ![ícone selecionar pessoas](./media/create-team-flows/removeowner1.png)
2. Selecione o ícone de **exclusão** para o proprietário que você deseja remover:
   
    ![Selecione Excluir](./media/create-team-flows/removeowner2.png)
3. Na caixa de diálogo de confirmação, selecione **remover este proprietário**:
   
    ![confirmar remoção](./media/create-team-flows/removeowner3.png)
4. Parabéns &mdash; o usuário ou grupo que você removeu não está mais listado como proprietário do fluxo:
   
    ![usuário removido](./media/create-team-flows/removeowner4.png)


## <a name="update-connection-owner"></a>Atualizar proprietário da conexão

Talvez seja necessário alterar o proprietário de uma conexão em um fluxo se você remover o proprietário existente. Siga estas etapas para alternar o proprietário de um fluxo:

1. Selecione **dados** no painel do lado esquerdo.
1. Selecione **conexões**.
1. Pesquise a conexão que você deseja atualizar e, em seguida, selecione-a.
1. Selecione **...** (mais comandos) na conexão que você selecionou e selecione **alternar conta**.
1. Siga as etapas para usar uma conta diferente para a conexão.

## <a name="embedded-and-other-connections"></a>Conexões inseridas e outras

As conexões usadas em um fluxo se enquadram em duas categorias:

* &mdash; **inseridas** , essas conexões são usadas no fluxo.
* **Outras** &mdash; essas conexões foram definidas para um fluxo, mas não são usadas nela.

Se você parar de usar uma conexão em um fluxo, essa conexão aparecerá na lista **outras** conexões, onde permanecerá até que um proprietário a inclua no fluxo novamente.

Siga as etapas para [atualizar um proprietário de conexão](./create-team-flows.md#update-connection-owner) para fazer alterações em conexões inseridas.

A lista de conexões aparece sob a lista de proprietários nas propriedades de um fluxo:

![conexões inseridas](./media/create-team-flows/embeddedconnections.png)

