---
title: Criar um fluxo de aprovação que exige que todos aprovem | Microsoft Docs
description: Crie um fluxo de aprovação que exija que todos aprovem ou uma pessoa rejeite uma solicitação.
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
ms.date: 02/27/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 191792c356dc6b5e3a285a16050a306d4e6039f2
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545199"
---
# <a name="create-an-approval-flow-that-requires-everyone-to-approve"></a>Criar um fluxo de aprovação que exige que todos aprovem
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este tutorial mostra como criar um fluxo de trabalho de aprovação que exige que todos (todos os aprovadores atribuídos) concordem com a aprovação de uma solicitação de férias, mas qualquer Aprovador pode rejeitar toda a solicitação.

Esse tipo de fluxo de trabalho de aprovação é útil em uma organização que exige o gerente de uma pessoa e o gerente do gerente, para que ambos concordem com uma solicitação de férias para que ele seja aprovado. No entanto, qualquer gerente pode recusar a solicitação sem a entrada da outra pessoa.

> [!NOTE]
> Embora este tutorial destaque um cenário de aprovação de férias, você pode usar esse tipo de fluxo de aprovação em qualquer situação em que vários aprovadores sejam necessários para aprovar uma solicitação.
>
>

## <a name="prerequisites"></a>Pré-requisitos

* Acesso a [Microsoft Flow](https://flow.microsoft.com), Microsoft Office 365 do Outlook e Microsoft Office usuários do 365.
* Uma [lista](https://support.office.com/article/SharePoint-lists-I-An-introduction-f11cd5fe-bc87-4f9e-9bfe-bbd87a22a194)do SharePoint.

    Este passo a passos pressupõe que você criou uma lista do SharePoint que é usada para solicitar férias. Consulte a explicação sobre [aprovações paralelas](parallel-modern-approvals.md) para obter um exemplo detalhado que detalha a aparência da sua lista do SharePoint.
* Familiaridade com as noções básicas de criação de fluxos.

    Você pode examinar como adicionar [ações, gatilhos](multi-step-logic-flow.md#add-another-action)e [condições](add-condition.md). As etapas a seguir pressupõem que você saiba como executar essas ações.

> [!NOTE]
> Embora possamos usar o SharePoint e o Office 365 Outlook neste passo a passos, você pode usar outros serviços, como zendesk, Salesforce, Gmail ou qualquer um dos mais de [200 serviços](https://flow.microsoft.com/connectors/) aos quais Microsoft Flow dá suporte.
>
>

## <a name="create-the-flow"></a>Criar o fluxo

> [!NOTE]
> Se você não tiver criado uma conexão com o SharePoint ou com o Office 365 anteriormente, siga as instruções quando for solicitado a entrar.
>
>

Este tutorial usa tokens. Para exibir a lista de tokens, toque ou clique em qualquer controle de entrada e, em seguida, procure o token na lista de **conteúdo dinâmico** que é aberta.

Entre no [Microsoft Flow](https://flow.microsoft.com)e, em seguida, execute as etapas a seguir para criar seu fluxo.

1. Selecione **meus fluxos** > **criar em branco**, no canto superior direito da tela.
1. Adicione o gatilho **SharePoint-quando um item é criado ou modificado** .
1. Insira o **endereço do site** para o site do SharePoint que hospeda sua lista de solicitações de férias e selecione o **nome da lista**de lista.
1. Adicione a ação **usuários do Office 365 – obter o Gerenciador v2** , selecione a caixa **usuário (UPN)** e, em seguida, adicione o token **criado por email** a ele.

    O token **criado por email** está localizado na categoria **quando um item é criado ou modificado** na lista de **conteúdo dinâmico** . Esse token fornece acesso dinâmico aos dados sobre o gerente para a pessoa que criou o item no SharePoint.

1. Adicione outros **usuários do Office 365 – obter a ação do Gerenciador v2** e, em seguida, adicione o token de **email** à caixa **usuário (UPN)** .

    O token de **email** está localizado na categoria **obter gerenciador v2 2** da lista de **conteúdo dinâmico** . Esse token fornece acesso dinâmico ao endereço de email para o gerente do gerente.

    Você também pode renomear o cartão **Get Manager V2 2** para algo significativo como "ignorar Gerenciador de nível".
1. Adicione a ação **iniciar uma aprovação** e, em seguida, selecione **todos da lista atribuída** na lista **tipo de aprovação** .

   > [!IMPORTANT]
   > Se qualquer aprovador rejeitar, a solicitação de aprovação será considerada rejeitada para todos os aprovadores.
   >
   >
1. Use a tabela a seguir como um guia para concluir o cartão **iniciar uma aprovação** .

   | campo | Ndescrição |
   | --- | --- |
   |  Tipo de aprovação |Use **qualquer pessoa da lista atribuída** para indicar que qualquer um dos aprovadores pode aprovar ou rejeitar a solicitação. </p>Use **todos da lista atribuída** para indicar que uma solicitação só será aprovada se todos concordar e a solicitação for negada se uma única pessoa a rejeitar. |
   |  título |O título da solicitação de aprovação. |
   |  Atribuído a |Os endereços de email dos aprovadores. |
   |  Ver |Todas as informações adicionais que você deseja enviar aos aprovadores listados no campo **atribuído a** . |
   |  Link do item |Uma URL para o item de aprovação. Neste exemplo, esse é um link para o item no SharePoint. |
   |  Descrição do link do item |Uma descrição de texto para o **link do item**. |

   > [!TIP]
   > A ação **iniciar uma aprovação** fornece vários tokens, incluindo **resposta** e **Resumo da resposta**. Use esses tokens em seu fluxo para fornecer relatórios avançados dos resultados de uma execução de um fluxo de solicitação de aprovação.
   >
   >

    O cartão **iniciar uma aprovação** é um modelo para a solicitação de aprovação enviada aos aprovadores. Configure-o de uma maneira útil para sua organização. Aqui está um exemplo.

    ![iniciar uma aprovação](media/all-assigned-must-approve/start-an-approval-card.png)

1. Adicionar a ação **Outlook do Office 365-enviar um email** e, em seguida, configurá-lo para enviar um email com os resultados da solicitação.

    Veja um exemplo de como seria a aparência do cartão **enviar um email** .

    ![enviar um email](media/all-assigned-must-approve/send-an-email-card.png)

> [!NOTE]
> Qualquer ação que segue a ação **iniciar uma aprovação** é executada com base na sua seleção na lista **tipo de aprovação** no cartão **iniciar uma aprovação** . A tabela a seguir lista o comportamento com base na sua seleção.
>
>

| Tipo de aprovação | Comportamento |
| --- | --- |
| Qualquer pessoa da lista atribuída |As ações que seguem a ação **iniciar uma aprovação** são executadas depois que qualquer um dos aprovadores decidir. |
| Todos da lista atribuída |Ações que seguem a ação **iniciar uma aprovação** são executadas depois que um Aprovador recusa ou todos aprova a solicitação. |

Na parte superior da tela, insira um nome para o fluxo na caixa **nome do fluxo** e, em seguida, selecione **criar fluxo** para salvá-lo.

Parabéns, seu fluxo está concluído! Se você seguiu, seu fluxo é semelhante a esta imagem.

![imagem de fluxo geral](media/all-assigned-must-approve/overall-flow.png)

Agora, sempre que um item for adicionado à sua lista do SharePoint ou se um item for alterado, seu fluxo disparará e enviará solicitações de aprovação para todos os aprovadores listados na caixa **atribuído a** do cartão **iniciar uma aprovação** . Seu fluxo envia solicitações de aprovação por meio do aplicativo móvel Microsoft Flow e por email. A pessoa que cria o item no SharePoint Obtém um email que resume os resultados, indicando claramente se a solicitação foi aprovada ou rejeitada.

Aqui está um exemplo da solicitação de aprovação que é enviada para cada aprovador.

![solicitação de aprovação](media/all-assigned-must-approve/approval-request.png)

Aqui está um exemplo de como pode ser uma resposta e um resumo de resposta após o fluxo ser executado.

![tokens de resposta](media/all-assigned-must-approve/response-output.png)

## <a name="learn-more-about-approvals"></a>Saiba mais sobre aprovações

* [Aprovações modernas de aprovador único](modern-approvals.md)
* [Aprovações modernas sequenciais](sequential-modern-approvals.md)
* [Aprovações modernas paralelas](parallel-modern-approvals.md)
* [Aprovações e o Microsoft Common Data Service](common-data-model-approve.md)
* [Aprovar solicitações em qualquer lugar](mobile-approvals.md)
