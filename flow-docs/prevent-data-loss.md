---
title: Introdução às políticas de prevenção contra a perda de dados (DLP). | Microsoft Docs
description: Introdução a políticas de prevenção de perda de dados para o Microsoft Flow.
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
ms.date: 04/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: f019a6ca5856c0fb3c5360642b4f3fcb23594b16
ms.sourcegitcommit: 3f17d8a0765d66740bb181885a79fa9127fc2aab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2019
ms.locfileid: "64950497"
---
# <a name="data-loss-prevention-dlp-policies"></a>Políticas de DLP (prevenção de perda de dados)

Este documento apresenta políticas de prevenção contra perda de dados, que ajudam a proteger seus dados organizacionais de serem compartilhados com uma lista de conectores que você definir.

## <a name="whats-a-data-loss-prevention-policy"></a>O que é uma política de prevenção contra perda de dados?

Os dados de uma organização são fundamentais para o sucesso. Os dados precisam estar prontamente disponíveis para a tomada de decisões, mas precisam ser protegidos para que não sejam compartilhados com audiências que não devem ter acesso a eles. Para proteger esses dados, o Microsoft Flow fornece a capacidade de criar e impor políticas que definem com quais conectores de consumidor podem acessar e compartilhar dados de negócios. As políticas que definem como os dados podem ser compartilhados são chamadas de políticas de DLP (prevenção de perda de dados).

## <a name="why-create-a-dlp-policy"></a>Por que criar uma política de DLP?

Você cria a política DLP para definir claramente quais conectores de consumidor podem acessar e compartilhar seus dados de negócios. Por exemplo, uma organização que usa o Microsoft Flow pode não querer que seus dados de negócios no SharePoint sejam publicados automaticamente em seu feed do Twitter. Para evitar isso, crie uma política DLP que impeça que os dados do SharePoint sejam usados como a origem de tweets.

## <a name="benefits-of-a-dlp-policy"></a>Benefícios de uma política de DLP

* Garante que os dados sejam gerenciados de maneira uniforme em toda a organização.
* Impede que dados de negócios importantes sejam acidentalmente publicados em conectores como sites de mídia social.

## <a name="managing-dlp-policies"></a>Gerenciar políticas de DLP

### <a name="prerequisites-for-managing-dlp-policies"></a>Pré-requisitos para o gerenciamento de políticas DLP

* Permissões de administrador de ambiente ou administrador de locatário.

    É possível saber mais sobre permissões no [artigo de ambientes](environments-overview-admin.md).
* Uma [licença P2 do Microsoft Flow](billing-questions.md).

## <a name="create-a-dlp-policy"></a>Criar uma política de DLP

### <a name="prerequisites-for-creating-dlp-policies"></a>Pré-requisitos para a criação de políticas DLP

Para criar uma política DLP, você deve ter permissões para pelo menos um ambiente.

Siga estas etapas para criar uma política de DLP que impede que os dados no site do SharePoint de sua empresa sejam publicados no Twitter:

1. Entre no [centro de administração do Microsoft Flow](https://admin.flow.microsoft.com) (centro de administração).

1. Selecione a guia Políticas de Dados e, em seguida, selecione o link **Nova política**:

    ![Entrar](./media/prevent-data-loss/create-policy-1.png)
1. Selecione a guia **Grupos de dados**.

1. Insira o nome da política DLP como *Acesso Seguro aos Dados da Contoso* no rótulo **Nome da Política de Dados** na parte superior da página:

    ![Entrar](./media/prevent-data-loss/create-policy-2.png)

1. Selecione o [ambiente](environments-overview-admin.md) na guia **Ambientes**.

    > [!NOTE]
    > Como administrador de ambiente, é possível criar políticas que se aplicam apenas a um único ambiente. Como administrador de locatário, é possível criar políticas que se aplicam a qualquer combinação de ambientes:
    >
    >

    ![Selecionar um ambiente](./media/prevent-data-loss/create-policy-3.png)

1. Selecione a guia **Grupos de dados**:

    ![selecionar grupos de dados](./media/prevent-data-loss/create-policy-4.png)

1. Selecione o link **Adicionar** localizado dentro da caixa de grupo **Somente dados de negócios**:

    ![Selecionar adicionar](./media/prevent-data-loss/create-policy-5.png)

1. Selecione os conectores **SharePoint** e **Salesforce** na página **Adicionar conectores**:

   ![selecionar conectores](./media/prevent-data-loss/create-policy-6.png)

1. Selecione o botão **Adicionar conectores** para adicionar os conectores que podem compartilhar dados de negócios.

1. Selecione **Salvar política** no canto superior direito da tela.

1. Após alguns instantes, a nova política de DLP será exibida na lista de políticas de prevenção de perda de dados:

    ![Lista de DLP](./media/prevent-data-loss/create-policy-9.png)

1. **Opcional** envie um email ou outras comunicações à sua equipe, avisando que uma nova política de DLP está disponível agora.

Parabéns, agora você criou uma política DLP que permite que o aplicativo compartilhe dados entre o SharePoint e o Salesforce e bloqueia o compartilhamento de dados com outros serviços.

> [!NOTE]
> Adicionar um serviço a um grupo de dados automaticamente removerá este serviço do outro grupo de dados. Por exemplo, se atualmente o Twitter estiver localizado no grupo de dados **somente dados de negócios** e você não quiser permitir que os dados de negócios sejam compartilhados com o Twitter, basta adicionar o serviço do Twitter ao grupo de **dados de negócios não permitidos**. Isso removerá o Twitter do grupo de dados somente dados de negócios.
>
>

## <a name="data-sharing-violations"></a>Violações de compartilhamento de dados

Supondo que você criou a política DLP descrita acima, quando um usuário cria um fluxo que compartilha dados entre o Salesforce (que está no grupo de dados **somente dados de negócios**) e Twitter (que está no grupo de dados **dados de negócios não permitidos**), o usuário é informado de que o fluxo está **suspenso** devido a um conflito com a política de prevenção contra perda de dados criada por você.

![criar fluxo](./media/prevent-data-loss/10.png)

Se os usuários entrarem em contato com você sobre fluxos suspensos, veja alguns itens a considerar:

1. Neste exemplo, se houver um motivo comercial válido para compartilhar dados de negócios entre o SharePoint e o Twitter, será possível editar a política DLP.

1. Peça ao usuário para editar o fluxo de acordo com a política DLP.

1. Peça ao usuário para deixar o fluxo no estado suspenso até que seja feita uma decisão sobre o compartilhamento de dados entre essas duas entidades.

## <a name="find-a-dlp-policy"></a>Localizar uma política de DLP

### <a name="admins"></a>Administradores.

Os administradores podem usar o recurso de pesquisa do Centro de administração para localizar políticas de DLP específicas.

> [!NOTE]
> Os administradores devem publicar todas as políticas DLP para que os usuários da organização estejam cientes das políticas antes da criação de fluxos.
>
>

### <a name="makers"></a>Criadores

Se você não tem permissões de administrador e deseja saber mais sobre as políticas de DLP em sua organização, contate o administrador. Também é possível saber mais no [artigo de ambientes de fabricante](environments-overview-maker.md)

> [!NOTE]
> Somente administradores podem editar ou excluir políticas DLP.
>
>

## <a name="edit-a-dlp-policy"></a>Editar uma política de DLP

1. Inicie o [Centro de administração](https://admin.flow.microsoft.com).

1. No Centro de administração iniciado, selecione o link **Políticas de dados** no lado esquerdo.

    ![selecionar políticas de dados](./media/prevent-data-loss/2.png)

1. Pesquise a lista de políticas DLP existentes e selecione o botão editar ao lado da política que você pretende editar.

1. Faça as alterações necessárias na política. Você pode modificar o ambiente ou os serviços nos grupos de dados, por exemplo.

1. Selecione **Salvar Política** para salvar as alterações.

> [!NOTE]
> As políticas DLP criadas por administradores de locatários podem ser exibidas por administradores de ambiente, mas não podem ser editadas por administradores de ambiente.
>
>

## <a name="delete-a-dlp-policy"></a>Excluir uma política de DLP

1. Inicie o [Centro de administração](https://admin.flow.microsoft.com).

1. Selecione a guia **Políticas de Dados** no lado esquerdo.

    ![selecionar guia de políticas de dados](./media/prevent-data-loss/2.png)

1. Pesquise a lista de políticas DLP existentes e, em seguida, selecione o botão excluir ao lado de política que você pretende excluir:

    ![Selecionar o botão excluir](./media/prevent-data-loss/3-delete.png)

1. Confirme que você realmente deseja excluir a política selecionando o botão **Excluir**:

    ![confirme que você realmente deseja excluir a política](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>Permissões de política de DLP

Apenas os administradores de locatários e de ambiente podem criar e modificar políticas de DLP. Saiba mais sobre permissões no artigo [ambientes](environments-overview-admin.md).


## <a name="custom-and-http-connectors"></a>Conectores personalizados e conectores HTTP

Conectores personalizados e conectores HTTP devem ser adicionados às políticas DLP por meio do PowerShell ou de um modelo do Microsoft Flow.

> [!TIP]
> Não é possível fazer downgrade da versão do esquema 2018-11-01. Não é possível remover o suporte a HTTP de uma política. Se você tentar remover o suporte a HTTP, a política DLP poderá ser corrompida. Além disso, quando uma política DLP é atualizada para dar suporte a conectores HTTP, os fluxos atuais que usam essas funcionalidades HTTP podem ser desativados.

Aqui estão os conectores HTTP que podem ser adicionados a uma política:

- HTTP (e HTTP + Swagger)
- HTTP Webhook
- Solicitação HTTP

## <a name="add-connectors-custom-and-http-connectors-with-templates"></a>Adicionar conectores personalizados e conectores HTTP com modelos

Para adicionar um conector personalizado a uma política usando uma [modelo](https://flow.microsoft.com/galleries/public/templates/ae9683086770420e902c043e5ed4b363/), insira o nome da política, o grupo ao qual adicionará o conector, mais o nome, a ID e o tipo do conector. Execute o fluxo uma vez para adicionar o conector personalizado à política e ao grupo fornecidos.

Para adicionar os conectores HTTP a uma política existente por meio do [modelo](https://flow.microsoft.com/galleries/public/templates/834eb1366aa54335a5f979014a9e0477/), insira o nome da política à qual você deseja adicioná-los e, em seguida, execute o fluxo.

## <a name="add-custom-and-http-connectors-with-powershell"></a>Adicionar conectores personalizados e conectores HTTP com o PowerShell

Para adicionar suporte para conectores personalizados e/ou conectores HTTP a uma política usando o PowerShell, [baixe](https://docs.microsoft.com/powerapps/administrator/powerapps-powershell) e importe os scripts mais recentes do PowerShell do PowerApps e, em seguida, use os seguintes cmdlets:  ‘New-AdminDlpPolicy’, ‘Set-AdminDlpPolicy’, ‘Add-CustomConnectorToPolicy’ e ‘Remove-CustomConnectorFromPolicy’ para modificar a política. Use o cmdlet ‘Get-Help -detailed’ como referência.


> [!IMPORTANT]
> Use a versão do esquema 2018-11-01 ao criar ou atualizar uma política DLP a fim de incluir os conectores HTTP. A adição de suporte a HTTP usando o modelo ou o PowerShell afetará apenas a política especificada. Novas políticas criadas no Centro de administração não incluem os conectores HTTP.



## <a name="next-steps"></a>Próximas etapas

* [Saiba mais sobre os ambientes](environments-overview-admin.md)
* [Saiba mais sobre o Microsoft Flow](getting-started.md)
* [Saiba mais sobre o centro de administração](admin-center-introduction.md)
* [Saiba mais sobre integração de dados](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
