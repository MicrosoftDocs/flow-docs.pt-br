---
title: Visão geral do ambiente para Administradores | Microsoft Docs
description: Usar, criar e gerenciar ambientes no Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 43f6f36cc32ec40088bd9b4c61e2895a7de78589
ms.sourcegitcommit: 5b27ac91b56078e91f45f993f1967731d14af92b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2019
ms.locfileid: "65035044"
---
# <a name="using-environments-within-microsoft-flow"></a>Uso de ambientes no Microsoft Flow

## <a name="benefits"></a>Benefícios

Os ambientes fornecem os benefícios a seguir:

* **Localidade dos dados**: é possível criar ambientes em diferentes regiões e associá-los a essa localização geográfica. Quando você cria um fluxo em um ambiente, esse fluxo é roteado para todos os datacenters no local geográfico. Isso também fornece um benefício de desempenho.

    Se os usuários estiverem na Europa, crie e use o ambiente na região da Europa. Se os usuários estiverem nos Estados Unidos, crie e use o ambiente na região dos EUA. 

    > [!IMPORTANT]
    > Se você excluir o ambiente, todos os fluxos dentro desse ambiente também são excluídos. Isso se aplica a qualquer item que você criar no ambiente, incluindo conexões, gateways, PowerApps e muito mais.
* **Prevenção contra perda de dados**: como administrador, você não quer fluxos que recebam dados de uma localização interna (como uma lista do *OneDrive for Business* ou do SharePoint, que contém informações sobre salários) e postem esses dados publicamente (por exemplo, no *Twitter*). Use a prevenção de perda de dados para controlar quais serviços podem compartilhar dados em sua implantação do Microsoft Flow.

    Por exemplo, é possível adicionar serviços do *SharePoint* e do *OneDrive for Business* a uma política somente dados de negócios. Qualquer fluxo criado nesse ambiente pode usar serviços do *SharePoint* e do *OneDrive for Business*. No entanto, eles não poderão compartilhar dados com outros serviços que não estão incluídos na política somente de dados da empresa.

  > [!NOTE]
  > A prevenção de perda de dados está disponível com alguns SKUs de licença, incluindo a licença P2.

* **Limite de isolamento para todos os recursos**: todos os fluxos, gateways, conexões, conectores personalizados, entre outros, residem em um ambiente específico. Eles não existem em qualquer outro ambiente.
* **Common Data Service**: aqui estão suas opções, caso você pretenda criar um fluxo que insira dados em um serviço:

  * Inserir dados em um arquivo do Excel e armazenar o arquivo do Excel em uma conta de armazenamento de nuvem, como o OneDrive.
  * Crie um Banco de Dados SQL e armazene seus dados nele.
  * Use o Common Data Service para armazenar seus dados.

    Cada ambiente pode ter um máximo de um banco de dados para seus fluxos no Common Data Service. O acesso ao Common Data Service depende da licença que você compra; o Common Data Service não está incluído na Licença gratuita.

## <a name="limitations"></a>Limitações

Embora os ambientes ofereçam muitos benefícios, eles também apresentam novas limitações. O fato de os ambientes serem um limite de isolamento significa que nunca é possível ter recursos que fazem referência a recursos *entre* ambientes. Por exemplo, não é possível criar um conector personalizado em um ambiente e criar um fluxo que usa o conector personalizado em um ambiente diferente.

## <a name="use-the-default-environment"></a>Use o ambiente padrão

O ambiente **Padrão** é compartilhado por todos os usuários e qualquer usuário pode criar fluxos no ambiente **Padrão**.

> [!TIP]
> Se você for um Usuário de visualização, todos os fluxos existentes residirão no ambiente padrão. Um *Usuário de visualização* é alguém que utilizou o Microsoft Flow antes da liberação para Disponibilidade Geral (GA).

## <a name="the-admin-center"></a>O Centro de Administração

Os administradores usam o centro de administração para criar e gerenciar ambientes. Aqui estão as duas maneiras de abrir o centro de administração:

### <a name="option-1-select-settings"></a>Opção 1: selecione Configurações

1. Entre em [flow.microsoft.com](https://flow.microsoft.com).
1. Selecione a engrenagem Configurações e escolha **Centro de Administração** na lista:

   ![Configurações e o Portal do Administrador](./media/environments-overview-admin/settings.png)
1. O centro de administrador é exibido.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Opção 2: abra admin.flow.microsoft.com

Vá até [admin.flow.microsoft.com](https://admin.flow.microsoft.com) e entre com sua conta de trabalho.

## <a name="create-an-environment"></a>Criar um ambiente

1. No [Centro de administração do Microsoft Flow](https://admin.flow.microsoft.com), selecione **Ambientes**. Todos os ambientes existentes estarão visíveis: ![Ambientes](./media/environments-overview-admin/environments-list.png)
2. Selecione **Novo ambiente** e forneça as informações necessárias:


   |     Propriedade     |                                                 Descrição                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Nome do Ambiente |              Insira o nome do seu ambiente, como `Human Resources`, ou `Europe flows`.              |
   |      Região      | Escolha o local para hospedar seu ambiente. Para obter o melhor desempenho, use uma região mais próxima de seus usuários. |
   | Tipo de ambiente |                  Escolha um tipo de ambiente com base em sua licença: Produção ou Avaliação.                   |

     ![configurações do ambiente](./media/environments-overview-admin/new-environment-dialog.png)
3. Clique em **Criar ambiente**.
4. Agora você tem uma opção para **Criar banco de dados** ou **Ignorar**.
5. Se você escolher **Criar banco de dados**, será necessário selecionar uma **Moeda** e **Idioma** para o banco de dados. Além disso, também é possível optar por ter aplicativos de amostra e dados implantados.

   ![definições de configuração do banco de dados](./media/environments-overview-admin/create-database-dialog2.png)


Agora é possível adicionar usuários ao ambiente.

## <a name="manage-your-existing-environments"></a>Gerencie os ambientes existentes

1. No [Centro de administração do Microsoft Flow](https://admin.flow.microsoft.com), selecione **Ambientes**:

   ![item de menu de ambientes](./media/environments-overview-admin/select-environments.png)
1. Selecione um ambiente para abrir suas propriedades.
1. Use a guia **Detalhes** para visualizar informações adicionais sobre um ambiente, incluindo quem criou o ambiente, sua localização geográfica e mais:

   ![guia detalhes](./media/environments-overview-admin/open-environment.png)
1. Selecione **Segurança**.

    Se você não selecionou **Criar banco de dados** nas etapas anteriores, em **Funções de ambiente**, há duas opções: **Administrador de Ambiente** e **Criador de Ambiente**:

    ![as funções do administrador](./media/environments-overview-admin/environment-roles.png)

    Um **Criador** pode criar novos recursos como fluxos, conexões de dados e gateways em um ambiente.

   > [!NOTE]
   > Um usuário não precisa ser um **Criador** para *editar* recursos em um ambiente. Cada Criador determina quem pode editar os respectivos recursos, concedendo permissões a usuários que não sejam criadores de ambiente.
   > 
   > 

    Um **Administrador** pode criar políticas de prevenção de perda e executar outras tarefas administrativas, como criar ambientes, adicionar usuários a ambientes e atribuir privilégios de administrador/criador.

   1. Selecione a função **Criador de Ambiente** e selecione **Usuários**: ![função de criador](./media/environments-overview-admin/add-environment-maker.png)
   1. Insira um nome, endereço de email ou grupo de usuários que você deseja fornecer à função do **Criador**.
   1. Selecione **Salvar**.

1. Em **segurança**, selecione **Funções de Usuário**:

    ![funções de usuário](./media/environments-overview-admin/security-user-roles.png)

    Todas as funções existentes são listadas, inclusive as opções para editar ou excluir a função.

    Selecione **Nova função** para criar uma nova função.
1. Em **Segurança**, selecione **Conjuntos de Permissões**:

    ![conjunto de permissão](./media/environments-overview-admin/security-permission-set.png)

    Você verá todos os conjuntos de permissões e opções existentes para editar ou excluir funções.

    Selecione **Novo conjunto de permissões** para criar um novo conjunto de permissões.
1. Se você optou por **Criar banco de dados** para armazenar seus dados, esse banco de dados faz parte do Common Data Service. Ao clicar na guia **Segurança**, você será solicitado a navegar até o **Centro de gerenciamento de instância do Dynamics 365**, no qual a segurança baseada em função pode ser aplicada.
![configurações de segurança do Dynamics](./media/environments-overview-admin/Security-Link-D365.png)

1. Selecione o usuário na lista de usuários no ambiente/instância.
  ![configurações de segurança do Dynamics](./media/environments-overview-admin/D365-Select-User.png)

1. Atribua a função ao usuário.

   ![atribuir função ao usuário](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Os usuários ou grupos atribuídos a essas funções de ambiente não recebem automaticamente acesso ao banco de dados do ambiente (se existir) e devem receber acesso separadamente por um proprietário do banco de dados. 
>
>

### <a name="database-security"></a>Segurança do banco de dados
A capacidade de criar e modificar um esquema de banco de dados e de se conectar aos dados armazenados em um banco de dados que é provisionado em seu ambiente é controlada pelas funções de usuário e pelos conjuntos de permissões do banco de dados. É possível gerenciar as funções de usuário e os conjuntos de permissões do banco de dados do seu ambiente na seção **Funções de usuário** e **Conjuntos de permissões** da guia **Segurança**. 

   ![atribuir função ao usuário](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="can-i-move-a-flow-between-environments"></a>Posso mover um fluxo entre ambientes?

Sim, os fluxos podem ser exportados de um ambiente e importados para outro ambiente.

### <a name="which-license-includes-the-common-data-service"></a>Qual licença inclui o Common Data Service?

Somente o Plano 2 do Microsoft PowerApps inclui direitos para criar bancos de dados com o Common Data Service. No entanto, todos os planos pagos (planos 1 e 2 do Microsoft Flow e planos 1 e 2 do Microsoft PowerApps) tem os direitos para usar o Common Data Service.

Escolha o plano certo para você visitando a página de [preço do Microsoft Flow](https://flow.microsoft.com/pricing/).

Confira respostas a perguntas frequentes sobre cobrança no documento [Perguntas para cobrança](billing-questions.md).

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>O Common Data Service pode ser usado fora de um ambiente?

Não. O Common Data Service requer um ambiente. [Leia mais](common-data-model-intro.md) sobre ele.

### <a name="what-regions-include-microsoft-flow"></a>Quais regiões estão incluídas no Microsoft Flow?

O Microsoft Flow dá suporte à maioria das regiões compatíveis com o Office 365, confira mais detalhes [na visão geral das regiões](regions-overview.md).

### <a name="whats-needed-to-create-my-own-custom-environment"></a>O que é necessário para meu próprio ambiente personalizado?

Todos os usuários com a licença do Microsoft Flow Plan 2 podem criar seus próprios ambientes. Todos os usuários do Microsoft Flow podem usar os ambientes criados pelos administradores do Plano 2, mas não podem criar seus próprios ambientes.
