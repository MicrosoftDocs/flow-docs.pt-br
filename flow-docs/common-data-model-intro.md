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
ms.openlocfilehash: 60e076dadab17beb15ffaec289ec0a2937924668
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546959"
---
# <a name="create-a-flow-that-uses-the-common-data-service"></a>Criar um fluxo que usa o Common Data Service
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Melhore a eficiência operacional com uma exibição unificada de dados corporativos criando um fluxo que usa o [Common Data Service](https://powerapps.microsoft.com/tutorials/data-platform-intro/). Implante esse banco de dados de negócios seguro que compreende entidades comerciais padrão bem formadas (como vendas, compras, atendimento ao cliente e produtividade) em sua organização. Armazene dados organizacionais em uma ou mais [entidades personalizadas](https://powerapps.microsoft.com/tutorials/data-platform-create-entity/), que oferecem vários benefícios em relação a fontes de dados externas, como o Microsoft Excel e o Salesforce.

Por exemplo, aproveite o Common Data Service em Microsoft Flow dessas principais maneiras:

* Crie um fluxo para importar dados, exportar dados ou tomar medidas sobre os dados (como enviar uma notificação). Observe que essa abordagem não é um serviço de sincronização completo; Ele simplesmente permite que você mova dados para dentro ou para fora de acordo com a entidade.
  
    Para obter etapas detalhadas, consulte os procedimentos mais adiante neste tópico.
* Em vez de [criar um loop de aprovação por email](wait-for-approvals.md), crie um fluxo que armazene o estado de aprovação em uma entidade e crie um aplicativo personalizado no qual os usuários possam aprovar ou rejeitar itens.
  
    Para obter etapas detalhadas, consulte [criar um loop de aprovação com o Common Data Service](common-data-model-approve.md).

**Pré-requisitos**

* Inscreva-se para [Microsoft Flow](https://flow.microsoft.com) e [PowerApps](https://web.powerapps.com).
  
    Se você tiver problemas, verifique se [Microsoft Flow](sign-up-sign-in.md) e [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/) dão suporte ao tipo de conta que você tem e sua organização não bloqueou a inscrição.
* Se você não tiver usado o Common Data Service antes, abra a guia **entidades** de [powerapps.com](https://web.powerapps.com/#/entities)e, em seguida, clique ou toque em **criar meu banco de dados**.

## <a name="sign-in-to-your-environment"></a>Entre no seu ambiente
1. Abra o [portal de Microsoft Flow](https://flow.microsoft.com)e, em seguida, clique ou toque em **entrar** no canto superior direito.
   
    **Observação**: Talvez seja necessário abrir o menu superior esquerdo para mostrar o botão **entrar** .
   
    ![Entrar](./media/common-data-model-intro/signin-flow.png)
2. No menu superior direito, selecione o ambiente no qual você criou o banco de dados em powerapps.com.
   
    **Observação**: se você não selecionar o mesmo ambiente, você não verá suas entidades.
   
    ![Selecionar ambiente](./media/common-data-model-intro/select-environment.png)

## <a name="open-a-template"></a>Abrir um modelo
1. Na caixa **Pesquisar modelos** na parte superior da tela, digite ou cole **comum**e pressione Enter.
   
    ![Pesquisar modelos](./media/common-data-model-intro/template-search.png)
2. Na lista de modelos, clique ou toque no modelo que importa os dados da origem que você deseja para a entidade (ou *objeto*) que você deseja.
   
    Por exemplo, clique ou toque no modelo que copia as informações de contato do Dynamics 365 para a Common Data Service.
   
    ![Escolher um modelo](./media/common-data-model-intro/choose-template.png)
3. Clique ou toque em **usar este modelo**.
   
    ![Usar modelo](./media/common-data-model-intro/use-template.png)
4. Se você ainda não criou uma conexão de Microsoft Flow para o Dynamics 365, clique ou toque em **entrar**e, em seguida, forneça suas credenciais, se solicitado.
   
    ![Entrar no Dynamics 365](./media/common-data-model-intro/dynamics-signin.png)
5. Clique ou toque em **continuar**.
   
    ![Confirmar contas](./media/common-data-model-intro/confirm-accounts.png)

## <a name="build-your-flow"></a>Crie seu fluxo
1. No primeiro cartão, especifique o evento que irá disparar o fluxo.
   
    Por exemplo, você está criando um fluxo que irá copiar novos contatos de uma instância do Dynamics 365 para o Common Data Service. Em **quando um registro é criado**, especifique a instância clicando ou tocando na seta para baixo e, em seguida, clicando ou tocando em uma opção na lista que aparece.
   
    ![Especificar instância do Dynamics 365](./media/common-data-model-intro/specify-instance.png)
2. adicional Próximo à parte superior da tela, especifique um nome diferente para o fluxo que você está criando.
   
    **Observação**: se a janela do navegador não for maximizada, a interface do usuário poderá parecer um pouco diferente.
   
    ![Fluxo de nome](./media/common-data-model-intro/name-flow.png)
3. Clique ou toque em **criar fluxo**.
   
    **Observação**: se a janela do navegador não for maximizada, somente a marca de seleção poderá ser exibida.
   
    ![criar fluxo](./media/common-data-model-intro/create-flow.png)

Agora, sempre que esse objeto for criado no sistema de origem, ele será importado para o Common Data Service. Se você não encontrar um modelo que faça o que precisa, poderá [criar um fluxo do zero](get-started-logic-flow.md) que opere sobre o Common Data Service.

Você pode executar ações sobre alterações no banco de dados. Por exemplo, você pode enviar email de notificação sempre que os dados forem alterados.

