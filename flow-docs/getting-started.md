---
title: Introdução | Microsoft Docs
description: Maneiras rápidas de começar a automatizar seu trabalho e sua vida com o Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: hero-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f667401774e49505009cd416f6975ff38683a5c7
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035206"
---
# <a name="get-started-with-microsoft-flow"></a>Introdução ao Microsoft Flow #

<iframe width="560" height="315" src="https://www.youtube.com/embed/iMteXfAvDSE?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

Bem-vindo! O Microsoft Flow é um serviço com o qual você pode criar fluxos de trabalho automatizados entre seus aplicativos e serviços favoritos para sincronizar arquivos, obter notificações, coletar dados e muito mais.

Os principais tipos de fluxos são [automatizado](get-started-logic-flow.md), [botão](introduction-to-button-flows.md), [agendado](run-scheduled-tasks.md) e [processo empresarial](business-process-flows-overview.md).

Se você é um personalizador do Dynamics 365 Customer Engagement, talvez já esteja familiarizado com os processos clássicos do Common Data Service que incluem, [fluxos de trabalho](configure-workflow-steps.md), [ações](create-actions.md), [fluxos de tarefas móveis](create-mobile-task-flow.md) e [caixas de diálogo](use-cds-for-apps-dialogs.md).

A primeira etapa consiste em [inscrever-se](sign-up-sign-in.md). Mas, se você já tem uma conta do Microsoft Flow, [entre](https://flow.microsoft.com/signin) usando um tablet, computador desktop ou telefone.

## <a name="check-out-the-start-page"></a>Confira a página inicial ##

[Na página inicial ](https://flow.microsoft.com) do Microsoft Flow, é possível [explorar um conjunto variado de modelos](https://flow.microsoft.com/templates) e conhecer os principais recursos do programa. É possível obter uma ideia do que é possível e como o Microsoft Flow pode ajudar sua empresa e sua vida.

Com o Microsoft Flow, é possível:

- Pesquisar modelos e serviços facilmente.

    ![Página inicial do Flow 1](./media/getting-started/flowhome1.png)

- Escolher entre os serviços mais populares.

    ![Página inicial do Flow 2](./media/getting-started/flowhome2.png)

- Exibir uma visão geral de cada fluxo.

    ![Página inicial do Flow 3](./media/getting-started/flowhome3.png)

Cada modelo é elaborado para uma finalidade específica. Por exemplo, o programa oferece modelos destinados a enviar uma mensagem de texto para você quando seu chefe envia emails, adicionar clientes potenciais do Twitter ao Dynamics 365 ou fazer backup de arquivos. Esses modelos representam apenas a ponta do iceberg. Eles servem para inspirá-lo a criar fluxos personalizados, especialmente para os processos de que você precisa.

## <a name="create-your-first-flow"></a>Criar seu primeiro fluxo ##

1. Selecione um modelo que seja útil para você. Veja a seguir o exemplo de modelo simples, [**Obter lembretes diários por Email**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/).

    ![modelo de lembrete diário](./media/getting-started/template-details.png)

1. Selecione **Continuar**.

    ![Criar conexão](./media/getting-started/create-connection.png)

1. Insira os endereços de email para os quais você enviará o lembrete diário. Em seguida, insira a mensagem de lembrete. Por fim, selecione **Criar fluxo** e verifique se o fluxo está funcionando conforme o esperado.

    ![Forneça credenciais para a conexão](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > É possível explorar as condições que disparam o fluxo e as ações que resultam desses eventos. Brinque com as configurações para personalizar o fluxo. Você pode inclusive adicionar ou excluir ações.

1. Selecione **Concluído**.

[Siga este tutorial](get-started-logic-template.md) para saber mais sobre como criar fluxos usando modelos.

## <a name="get-creative"></a>Seja criativo ##

Agora que você já criou o primeiro fluxo com um modelo, use as mais de [150 fontes de dados](https://flow.microsoft.com/connectors/) com suporte do Microsoft Flow para [criar fluxos personalizados do zero](get-started-logic-flow.md).

![Criar um fluxo](./media/getting-started/build-a-flow.png)

Quando cria um fluxo do zero, você pode controlar o fluxo de trabalho inteiro. Aqui estão algumas ideias para ajudá-lo a começar:

- [Fluxos com várias etapas](multi-step-logic-flow.md).
- [Executar tarefas em uma agenda](run-scheduled-tasks.md).
- [Criar um fluxo de aprovação](wait-for-approvals.md).
- [Assistir a um fluxo em ação](see-a-flow-run.md).
- [Publicar um modelo](publish-a-template.md).
- [Criar fluxos usando um modelo do Microsoft Teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Inspecionar o código

Não é necessário ser um desenvolvedor para criar fluxos, no entanto, o Microsoft Flow fornece o recurso **Inspecionar código**, com o qual as pessoas podem analisar detalhadamente o código que é gerado para todas as ações e gatilhos em um fluxo. A inspeção no código pode proporcionar uma compreensão clara dos dados que estão em uso por gatilhos e ações. Siga estas etapas para inspecionar o código que é gerado para os fluxos, de dentro do designer do Microsoft Flow: 

1. Selecione o item de menu **...**, no canto superior direito de qualquer **ação** ou **gatilho**. 
1. Selecione **Código de espiada**.

    ![Inspecionar código](media/getting-started/peek-code.png)

1. Veja a representação JSON completa dos gatilhos e das ações. Ela inclui todas as entradas, como o texto que você insere diretamente, e as expressões usadas. Você pode selecionar expressões aqui e colá-las no editor de expressão de **Conteúdo Dinâmico**. Com isso, você também tem uma maneira de verificar os dados que devem estar presentes no fluxo.

    ![Inspecionar código](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Localizar os fluxos com facilidade

Quando sua imaginação começar a *fluir*, certamente você criará vários fluxos. Não se preocupe, pois é fácil encontrar os fluxos. Basta usar a caixa de pesquisa na tela **Meus fluxos**, **Fluxos de equipe**, **Conexões** ou **Soluções** para exibir somente os fluxos que correspondem aos termos de pesquisa inseridos.

![Filtrar ou pesquisar fluxos](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> O filtro de pesquisa localiza apenas os fluxos que foram carregados na página. Caso não encontre um determinado fluxo, experimente selecionar **Carregar mais**, na parte inferior da página.

## <a name="get-notifications-when-somethings-wrong"></a>Receber notificações quando algo está errado

Use o centro de notificações do Microsoft Flow, localizado no canto superior direito do designer, para ver rapidamente uma lista dos fluxos que falharam recentemente. O centro de notificações exibe um número que indica a quantidade de fluxos que falharam recentemente.

Nesse local, você pode navegar até a página **Atividade** do Microsoft Flow para ver todos os fluxos executados, que enviaram notificações ou que falharam recentemente.

![Centro de notificações](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Usar o aplicativo móvel ##

Baixe o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows). Com este aplicativo, é possível [monitorar a atividade do fluxo](mobile-monitor-activity.md), [gerenciar os fluxos](mobile-manage-flows.md) e [criar fluxos usando modelos](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Estamos aqui para ajudar ##

Estamos entusiasmados em ver o que você pode fazer com o Microsoft Flow e queremos garantir que você tenha uma ótima experiência. Confira nossos tutoriais de [aprendizagem interativa](https://flow.microsoft.com/guided-learning/) e [participe da nossa comunidade](http://go.microsoft.com/fwlink/?LinkID=787467) para fazer perguntas e compartilhar ideias. [Entre em contato com o suporte](http://go.microsoft.com/fwlink/?LinkID=787479) se tiver algum problema.
