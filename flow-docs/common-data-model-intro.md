---
title: Common Data Service | Microsoft Docs
description: Crie um fluxo para importar dados, exportar dados ou criar aprovações com o Common Data Service.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b2cf6c52a2cbaf06fc638fe8fc898689e6d523c4
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64459917"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Crie um fluxo que utiliza o Common Data Service
Melhore a eficiência operacional com uma exibição unificada de dados de negócios com a criação de fluxo que usa o [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Implante esse banco de dados de negócios seguro que inclui entidades de negócios padrão bem formadas (como Vendas, Compras, Atendimento ao cliente e Produtividade) em sua organização. Armazene dados organizacionais em uma ou mais [entidades personalizadas](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), que oferecem várias vantagens sobre fontes de dados externas, como o Microsoft Excel e Salesforce.

Por exemplo, aproveite o Common Data Service no Microsoft Flow das seguintes principais maneiras:

* Crie um fluxo para importar dados, exportar dados ou agir sobre os dados (como enviar uma notificação). Observe que essa abordagem não é um serviço de sincronização completo; ele simplesmente permite mover dados por entidade.
  
    Para obter etapas detalhadas, consulte os procedimentos mais adiante neste tópico.
* Em vez de [criar um loop de aprovação por meio de email](wait-for-approvals.md), crie um fluxo que armazene estado de aprovação em uma entidade e compile um aplicativo personalizado no qual os usuários podem aprovar ou rejeitar itens.
  
    Para obter etapas detalhadas, consulte [Criar um loop de aprovação com o Common Data Service](common-data-model-approve.md).

**Pré-requisitos**

* Inscreva-se no [Microsoft Flow](https://flow.microsoft.com) e [PowerApps](https://web.powerapps.com).
  
    Se você tiver problemas, verifique se o [Microsoft Flow](sign-up-sign-in.md) e [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) dão suporte ao tipo de conta que você tem e se sua organização não bloqueou a inscrição.
* Se você não tiver usado o Common Data Service antes, abra a guia **Entidades** guia de [powerapps.com](https://web.powerapps.com/#/entities) e clique ou toque em **Criar meu banco de dados**.

## <a name="sign-in-to-your-environment"></a>Entre no seu Ambiente
1. Abra o [portal do Microsoft Flow](https://flow.microsoft.com) e clique ou toque em **Entrar** no canto superior direito.
   
    **Observação**: talvez seja necessário abrir o menu do canto superior esquerdo para mostrar o botão **Entrar**.
   
    ![Entrar](./media/common-data-model-intro/signin-flow.png)
2. No menu superior direito, selecione o ambiente que você criou o banco de dados em powerapps.com.
   
    **Observação**: se você não selecionar o mesmo ambiente, você não verá suas entidades.
   
    ![Selecionar um ambiente](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Abrir um modelo
1. Na caixa **Pesquisar modelos**, na parte superior da tela, digite ou cole **comum** e pressione Enter.
   
    ![Pesquisar modelos](./media/common-data-model-intro/template-search.png)
2. Na lista de modelos, clique ou toque no modelo que importa os dados da origem que você quer para a entidade (ou *objeto*) que você quer.
   
    Por exemplo, clique ou toque no modelo que copia informações de contato do Dynamics 365 para o Common Data Service.
   
    ![Escolher um modelo](./media/common-data-model-intro/choose-template.png)
3. Clique ou toque em **Usar este modelo**.
   
    ![Usar modelo](./media/common-data-model-intro/use-template.png)
4. Se você ainda não criou uma conexão do Microsoft Flow com o Dynamics 365, clique ou toque em **Entrar** e, em seguida, forneça suas credenciais, se solicitado.
   
    ![Entrar no Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Clique ou toque em **Continuar**.
   
    ![Confirmar contas](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Compilar fluxo
1. No primeiro cartão, especifique o evento que disparará o fluxo.
   
    Por exemplo, você está criando um fluxo que copiará novos contatos de uma instância do Dynamics 365 para o Common Data Service. Em **quando um registro é criado**, especifique a instância clicando ou tocando na seta para baixo e, em seguida, clicando ou tocando em uma opção na lista que aparece.
   
    ![Especificar a instância do Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. (opcional) Próximo ao topo da tela, especifique um nome diferente para o fluxo que você está criando.
   
    **Observação**: Se a janela do navegador não estiver maximizada, a interface do usuário pode parecer um pouco diferente.
   
    ![Nomear fluxo](./media/common-data-model-intro/name-flow.png)
3. Clique ou toque em **Criar fluxo**.
   
    **Observação**: Se a janela do navegador não estiver maximizada, apenas a marca de seleção poderá aparecer.
   
    ![Criar fluxo](./media/common-data-model-intro/create-flow.png)

Agora, sempre que o objeto é criado no sistema de origem, ele será importado para o Common Data Service. Se você não encontrar um modelo que faz o que precisa, será possível [compila um fluxo do zero](get-started-logic-flow.md) que opere sobre o Common Data Service.

Você pode executar ações sobre as alterações no banco de dados. Por exemplo, você pode enviar email de notificação sempre que dados forem alterados.

