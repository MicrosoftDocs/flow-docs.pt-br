---
title: Introdução | Microsoft Docs
description: Maneiras rápidas de começar a automatizar seu trabalho e sua vida com a automatização de energia
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: conceptual
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/31/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 54d1478f34743b6059692b927da8baf2c49a35a7
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589845"
---
# <a name="get-started-with-power-automate"></a>Introdução à automatização de energia

[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

<br>
<iframe width="1129" height="635" src="https://www.youtube.com/embed/hCuxuUaGC6Y" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Inicial! A automatização de energia é um serviço que ajuda a criar fluxos de trabalho automatizados entre seus aplicativos e serviços favoritos para sincronizar arquivos, obter notificações, coletar dados e muito mais.

Os principais tipos de fluxo são fluxos [automatizados](get-started-logic-flow.md), de [botões](introduction-to-button-flows.md), [agendados](run-scheduled-tasks.md)e de [processos comerciais](business-process-flows-overview.md) .

## <a name="types-of-flows"></a>Tipos de fluxos

A automatização de energia é um dos três pilares da plataforma de energia. Ele fornece uma plataforma de código baixo para fluxo de trabalho e automação de processo. Aqui está uma lista dos diferentes tipos de fluxos:

| **Tipo de fluxo**                                                                       | **Caso de uso**                                                                                  | **Alvo**                                                                             |
|-------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|
| [Fluxos automatizados](get-started-logic-flow.md)                 | Crie um fluxo que executa uma ou mais tarefas automaticamente depois que ele é disparado por um evento. | [Conectores](https://docs.microsoft.com/connectors/) para serviços de nuvem ou locais. |
| [Fluxos de botão](introduction-to-button-flows.md)              | Execute tarefas repetitivas de qualquer lugar, a qualquer momento, por meio de seu dispositivo móvel.                        |                                                                                        |
| [Fluxos agendados](run-scheduled-tasks.md)                    | Crie um fluxo que executa uma ou mais tarefas em uma agenda.             |                                                                                        |
| [Fluxos de processos de negócios](business-process-flows-overview.md) | Defina um conjunto de etapas para que as pessoas sigam para levá-las a um resultado desejado.                 | Processos humanos                                                                        |
| [Fluxos da interface do usuário (visualização)](ui-flows/overview.md)                                                | Registre e automatize a reprodução de etapas manuais no software herdado.                    | Aplicativos Web e de área de trabalho que não têm APIs disponíveis para automação.    |

Você pode criar e gerenciar todos os fluxos da guia **meus fluxos** na automatização de energia.

Se você for um usuário do Dynamics 365, também poderá estar familiarizado com os processos de Common Data Service clássicos que incluem, [fluxos de trabalho](configure-workflow-steps.md), [ações](create-actions.md), [fluxos de tarefas móveis](create-mobile-task-flow.md)e [caixas de diálogo](use-cds-for-apps-dialogs.md).

A primeira etapa é [inscrever-](sign-up-sign-in.md)se ou, se você já tiver uma conta com energia automatizada, [entrar](https://flow.microsoft.com/signin) no Tablet, computador desktop ou até mesmo em seu telefone.

## <a name="check-out-the-start-page"></a>Confira a página inicial ##

[Na página inicial](https://flow.microsoft.com) da energia automatizada, você pode [explorar um conjunto diversificado de modelos](https://flow.microsoft.com/templates) e saber mais sobre os principais recursos da automatização de energia. Você pode ter uma noção rápida do que é possível e como a automatização da energia pode ajudar sua empresa e sua vida.

Com a automatização de energia, você pode:

- Pesquise facilmente modelos e serviços.

    ![Página inicial do fluxo 1](./media/getting-started/flowhome1.png)

- Escolha entre os serviços mais populares.

    ![Página inicial do fluxo 2](./media/getting-started/flowhome2.png)

- Consulte uma visão geral de cada fluxo.

    ![Página inicial do fluxo 3](./media/getting-started/flowhome3.png)

Cada modelo é projetado para uma finalidade específica. Por exemplo, há modelos para enviar uma mensagem de texto quando seu chefe envia emails para você, adicionando leads do Twitter ao Dynamics 365 ou fazendo backup de seus arquivos. Esses modelos são apenas a ponta do iceberg. Eles destinam-se a inspirar você a criar fluxos personalizados para os processos exatos de que precisa.

## <a name="create-your-first-flow"></a>Criar seu primeiro fluxo ##

1. Selecione um modelo que seja útil para você. Um modelo simples é [**obter lembretes diários no email**](https://flow.microsoft.com/galleries/public/templates/45a3399aa29345308f08b6db0a9c85b9/):

    ![modelo de lembrete diário](./media/getting-started/template-details.png)

1. Selecione **continuar**.

    ![Criar conexão](./media/getting-started/create-connection.png)

1. Insira os endereços de email para os quais o lembrete diário será enviado. Em seguida, insira a mensagem de lembrete. Por fim, selecione **criar fluxo**e verifique se o fluxo está sendo executado conforme o esperado.

    ![Fornecer credenciais para a conexão](./media/getting-started/configure-email-details.png)

    > [!NOTE]
    > Você pode explorar as condições que disparam o fluxo e a ação que resulta desse evento. Experimente com as configurações para tornar o fluxo seu próprio. Você pode até mesmo adicionar ou excluir ações.

1. Selecione **concluído**.

[Siga este tutorial](get-started-logic-template.md) para saber mais sobre como criar fluxos a partir de modelos.

## <a name="get-creative"></a>Obtenha o criativo ##

Agora que você criou seu primeiro fluxo a partir de um modelo, use qualquer uma das mais de [150 fontes de dados](https://flow.microsoft.com/connectors/) que a energia automatizada oferece suporte para [criar seus próprios fluxos do zero](get-started-logic-flow.md).

![Criando um fluxo](./media/getting-started/build-a-flow.png)

Ao criar um fluxo do zero, você controla todo o fluxo de trabalho. Aqui estão algumas ideias para começar:

- [Flui com várias etapas](multi-step-logic-flow.md).
- [Executar tarefas em um agendamento](run-scheduled-tasks.md).
- [Crie um fluxo de aprovação](wait-for-approvals.md).
- [Assista a um fluxo em ação](see-a-flow-run.md).
- [Publicar um modelo](publish-a-template.md).
- [Crie fluxos de um modelo do Microsoft Teams](https://flow.microsoft.com/connectors/shared_teams/microsoft-teams/).


## <a name="peek-at-the-code"></a>Espiar o código

Você não precisa ser um desenvolvedor para criar fluxos, no entanto, a automatização de energia fornece um recurso de **inspecionar código** que permite que qualquer pessoa examine mais atentamente o código gerado para todas as ações e gatilhos em um fluxo. A inspeção do código pode lhe dar uma compreensão mais clara dos dados que estão sendo usados por gatilhos e ações. Siga estas etapas para inspecionar o código que é gerado para seus fluxos de dentro do designer de energia automatizada: 

1. Selecione o item de menu **...** no canto superior direito de qualquer **ação** ou **gatilho**. 
1. Selecione **código de inspeção**.

    ![Inspecionar código](media/getting-started/peek-code.png)

1. Observe a representação JSON completa das ações e dos gatilhos. Isso inclui todas as entradas, como o texto inserido diretamente e as expressões usadas. Você pode selecionar expressões aqui e, em seguida, colá-las no editor de expressão de **conteúdo dinâmico** . Isso também pode fornecer uma maneira de verificar os dados esperados estão presentes no fluxo.

    ![Inspecionar código](media/getting-started/peek-code-details.png)
   

## <a name="find-your-flows-easily"></a>Encontre seus fluxos facilmente

Quando os sucos criativos começam a *fluir*, você pode criar vários fluxos. Não se preocupe, encontrar seus fluxos é fácil. basta usar a caixa de pesquisa na tela **meus fluxos**, **fluxos de equipe**, **conexões**ou **soluções** para exibir apenas os fluxos que correspondem aos termos de pesquisa que você inserir.

![Filtrar ou Pesquisar fluxos](media/getting-started/filter-search-box.png)
 
> [!NOTE]
> O filtro de pesquisa localiza apenas os fluxos que foram carregados na página. Se você não encontrar seu fluxo, tente selecionar **carregar mais** na parte inferior da página.

## <a name="get-notifications-when-somethings-wrong"></a>Obter notificações quando algo estiver errado

Use o centro de notificação de automatização de energia (localizado no canto superior direito do designer) para ver rapidamente uma lista de fluxos que falharam recentemente. A central de notificações exibe um número que indica o número de fluxos que falharam recentemente.

No centro de notificações, você pode navegar até a página **atividade** da energia automatizada para ver todos os fluxos que foram executados recentemente, enviar notificações ou falha.

![Centro de notificações](media/getting-started/notification-center.png)

## <a name="use-the-mobile-app"></a>Usar o aplicativo móvel ##

Baixe o aplicativo móvel de energia automatizada para [Android](https://aka.ms/flowmobiledocsandroid), [Ios](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows). Com esse aplicativo, você pode [monitorar a atividade de fluxo](mobile-monitor-activity.md), [gerenciar seus fluxos](mobile-manage-flows.md) e [criar fluxos a partir de modelos](mobile-create-flow.md).

## <a name="were-here-to-help"></a>Estamos aqui para ajudar ##

Estamos empolgados para ver o que você faz com a automatização de energia e queremos garantir que você tenha uma ótima experiência. Lembre-se de conferir nossos tutoriais de [aprendizado guiado](https://flow.microsoft.com/guided-learning/) e [participar de nossa comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) para fazer perguntas e compartilhar suas ideias. [Contate o suporte](https://go.microsoft.com/fwlink/?LinkID=787479) se você encontrar algum problema.
