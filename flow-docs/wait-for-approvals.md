---
title: Aguardar a aprovação em um fluxo | Microsoft Docs
description: Os fluxos podem esperar que um evento externo ocorra, como um usuário aprovar ou rejeitar uma alteração, antes de executar uma ação, como o envio da notificação da decisão.
services: ''
suite: flow
documentationcenter: na
author: merwanhade
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2018
ms.author: merwanhade
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0cc750dd9601e7675cee148882c6aaee9250b92e
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64464814"
---
# <a name="wait-for-approval-in-microsoft-flow"></a>Aguardar a aprovação no Microsoft Flow

> [!VIDEO https://www.youtube.com/embed/W6oxcYRtW-8?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF]
>


Crie um fluxo que, se você criar um item no SharePoint, enviará um email de aprovação e notificará se o item foi aprovado ou rejeitado. Para acompanhar este tutorial de maneira exata, crie uma lista simples do SharePoint como uma ação de gatilho, mas você pode usar outra fonte de dados, como o Dropbox ou o OneDrive.

**Pré-requisitos**

* Crie uma lista simples do SharePoint chamada de **Rastreador de Projetos**, adicione uma coluna chamada **Título** e uma coluna de Pessoa ou Grupo chamada **Atribuído a**.

   ![Imagem da lista de Rastreador de projetos do SPO](./media/wait-for-approvals/project-tracker.png)

## <a name="add-an-event-to-trigger-the-flow"></a>Adicione um evento para disparar o fluxo

1. Entre no [Microsoft Flow](https://flow.microsoft.com), selecione **Meus fluxos** na barra de navegação superior e, em seguida, selecione **Criar do zero**.

1. Selecione a caixa **Pesquisar centenas de conectores e gatilhos**, digite **novo item** e, em seguida, navegue até **SharePoint – quando um item é criado**.

1. Se for solicitado, entre no SharePoint.
1. Em **Endereço do site**, insira a URL do site do SharePoint que contém a lista.

1. Em **Nome da lista**, selecione a lista criada anteriormente. Se você estiver acompanhando, o nome será **Rastreador de projetos**.

    ![Imagem do nome da lista do SPO](./media/wait-for-approvals/SPO-list-name.png)

## <a name="add-the-resulting-action"></a>Adicione a ação resultante

1. Selecione o botão **Nova etapa** e, em seguida, selecione **Adicionar uma ação.**

1. Na caixa **Pesquisar todos os conectores e ações**, digite ou cole **enviar email** e, sem guida, selecione **Office 365 Outlook – Enviar email com opções**.

1. Se solicitado, entre no Office 365 Outlook.

1. Selecione o campo **Para** e, em seguida, selecione o token **Atribuídos a Email**.

    O usuário na coluna **Atribuído a** recebe o email para aprovar ou rejeitar o item. Quando você criar um item para testar o fluxo, especificará a si mesmo nesse campo. Dessa forma, você não apenas aprova ou rejeita o item, mas também recebe o email de notificação.

    > [!NOTE]
    > É possível personalizar os campos **Assunto** e **Opções do usuário** para se adequar às suas necessidades.

    ![Imagem do campo enviar o email de aprovação para](./media/wait-for-approvals/send-approval-email-to.png)

## <a name="add-a-condition"></a>Adicionar uma condição

1. Selecione o botão **Nova etapa** e, em seguida, selecione **Adicionar uma condição**.

    ![Imagem de adicionar uma condição](./media/wait-for-approvals/add-a-condition.png)
1. Selecione a primeira caixa e, em seguida, selecione o token **SelectedOption**.
1. Selecione a última caixa e, em seguida, digite **Aprovar**.

    ![Imagem da placa de condição](./media/wait-for-approvals/condition-card-2.png)

1. Na área **Se sim**, selecione **Adicionar uma ação**.

1. Na caixa **Pesquisar todos os conectores e ações**, digite ou cole **enviar email** e, em seguida, selecione **Office 365 Outlook – Enviar um email**.

1. No campo **Para**, insira um destinatário como **Criado por Email**.

1. Na caixa **Assunto**, especifique um assunto.

    Por exemplo, selecione **Atribuído a DisplayName**, digite **Aprovou** com um espaço em cada lado e, em seguida, selecione **Título**.

1. Na caixa **Corpo**, especifique o corpo de email com algo como **Pronto para prosseguir com a próxima fase do projeto.**

    > [!NOTE]
    > A pessoa que criou o item na lista do SharePoint será notificada se o projeto foi aprovado ou rejeitado.

    ![Imagem de sim-enviar-email](./media/wait-for-approvals/if-yes-send-email-card-3.png)

1. Na área **Se não**, repita as cinco últimas etapas alterando o **Assunto** e **Corpo** para demonstrar que o projeto foi rejeitado.

     ![Imagem de não-enviar-email](./media/wait-for-approvals/no-send-email-2.png)

## <a name="finish-and-test-your-flow"></a>Concluir e testar seu fluxo

1. Nomeie seu fluxo e, em seguida, selecione **Criar fluxo**.

     ![Imagem de criar-fluxo](./media/wait-for-approvals/create-flow.png)
1. Crie um item na sua lista do SharePoint.

    Um email de aprovação é enviado para o destinatário especificado. Quando o destinatário seleciona **Aprovar** ou **Rejeitar** nesse email, você recebe um email que indica a resposta.

## <a name="learn-more"></a>Saiba mais

* [Passo a passo das aprovações modernas do aprovador único](modern-approvals.md)
* Crie [aprovações sequenciais](sequential-modern-approvals.md)
* Crie [aprovações paralelas](parallel-modern-approvals.md)
* Aprove [solicitações em qualquer lugar](mobile-approvals.md)
