---
title: Executar fluxos de interface do usuário de outros fluxos | Microsoft Docs
description: Executar fluxos de interface do usuário de outros fluxos
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 275ef331d37ff83d8890b4b6ddd750dc038dd099
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589742"
---
# <a name="run-ui-flows"></a>Executar fluxos da interface do usuário

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Depois de criar e testar um fluxo de interface do usuário, você pode executá-lo de um evento, um agendamento ou um botão. Para tornar isso possível, adicione o fluxo da interface do usuário a um [fluxo automatizado](../get-started-logic-flow.md), um [fluxo de botão](../introduction-to-button-flows.md), um [fluxo agendado](../run-scheduled-tasks.md)ou um [fluxo de processo de negócios](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Pré-requisitos

- Você precisa do [Gateway de dados local](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) para que seu dispositivo tenha o fluxo da interface do usuário disparado pelo Power Automate.
   
   O gateway é uma conexão segura de nível empresarial entre a automatização de energia e o dispositivo (onde o fluxo de interface do usuário é executado). A automatização de energia usa o gateway para acessar seu dispositivo local para que ele possa disparar seus fluxos de interface do usuário de um evento, um agendamento ou um botão.
- Uma conta corporativa ou de estudante. 

   >[!IMPORTANT]
   >Você deve usar a mesma conta corporativa ou de estudante para configurar o gateway, para entrar no Power Automate e para fazer logon em seu dispositivo Windows.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Executar o fluxo da interface do usuário de um evento, um botão, um agendamento ou um fluxo de processo de negócios

Neste exemplo, usaremos um fluxo automatizado para disparar um fluxo de interface do usuário quando um novo email chegar.

1. Navegue até [Power Automate](https://flow.microsoft.com/).
1. Selecione **meus fluxos** na barra de navegação à esquerda.
1. Selecione **novo**e, em seguida, selecione **automatizado de em branco**.

   >[!TIP]
   >Você pode escolher qualquer outro tipo de fluxo para atender às suas necessidades.

1. Dê um nome ao seu fluxo na caixa **nome do fluxo** .
1. Pesquise "novo email" e, em seguida, selecione **quando um novo email chegar (v3)** na lista de gatilhos. 
    
   ![Selecionar um gatilho](../media/run-ui-flow/2d4ec17d239169a46905cef1829fa3a1.png "Selecionar um gatilho")

1. Selecione **criar**e, em seguida, selecione **nova etapa**.

1. Pesquise **fluxos de interface do usuário**e, em seguida, selecione **executar um fluxo de interface do usuário para área de trabalho** na lista de **ações**. 

   ![Ação de pesquisa](../media/run-ui-flow/search-action.png "Ação de pesquisa")

1. Forneça as informações do gateway e as credenciais do dispositivo. 

   Você precisará fazer isso uma vez por dispositivo:

    - **Nome da conexão**: escolha um nome para o dispositivo para o fluxo de conexão. Ele pode ser diferente do nome do gateway.
    - **Nome de usuário**: forneça a conta corporativa ou de estudante do seu dispositivo.
    - **Tipo de autenticação**: selecione Windows.
    - **Senha**: a senha da sua conta corporativa ou de estudante.
    - **Gateway**: selecione o gateway que você criou durante a instalação.

      ![Configurações de conexão](../media/run-ui-flow/connection-settings.png "Configurações de conexão")

      >[!TIP]
      >Se você não vir seu gateway, talvez seja necessário selecionar uma conexão diferente. Para fazer isso, selecione **...** no canto superior direito do cartão **executar um fluxo de interface do usuário para área de trabalho (versão prévia)** e, em seguida, selecione a conexão que você deseja usar em **minhas conexões**.

      ![Selecione uma nova conexão](../media/run-ui-flow/select-new-connection.png "Selecione uma nova conexão")

1. Selecione o fluxo de interface do usuário que você criou anteriormente.

   ![Selecionar fluxo de IU](../media/run-ui-flow/select-ui-flow.png "Selecionar fluxo de IU")

1. Selecione **salvar** para salvar o fluxo automatizado.

1. Teste seu fluxo enviando um email para dispará-lo. Você verá o fluxo da interface do usuário reproduzindo as etapas que você registrou. 

![Execução bem-sucedida que chama um fluxo de interface do usuário](../media/run-ui-flow/successful-run.png "Execução bem-sucedida que chama um fluxo de interface do usuário")

>[!TIP]
>Não interaja com seu dispositivo enquanto o fluxo é executado.

## <a name="use-inputs-and-outputs"></a>Usar entradas e saídas

Ao definir entradas e saídas em um fluxo de interface do usuário, você pode passar informações de e para essas entradas.

1. Ao adicionar um fluxo de interface do usuário a um fluxo, você pode ver a lista de entradas que foram definidas no fluxo da interface do usuário.

   ![Entradas de fluxo da interface do usuário](../media/run-ui-flow/inputs.png "Entradas de fluxo da interface do usuário")

1. Você pode preencher cada campo de entrada no fluxo da interface do usuário com valores de etapas anteriores no fluxo. Para fazer isso, selecione o campo de entrada e, em seguida, selecione uma entrada no seletor de token.


1. Você também pode usar saídas de seu fluxo de interface do usuário como entradas para ações que aparecem posteriormente no fluxo. Para fazer isso, selecione o campo de entrada e, em seguida, selecione uma entrada no seletor de token.

## <a name="limitations-and-known-issues"></a>Limitações e problemas conhecidos

- Não há suporte para clusters de gateway.
- Como não há suporte para teclados não-US (QWERTY) neste realease, a reprodução de uma etapa de entrada em que a sequência de chaves foi registrada de um teclado que não seja dos EUA (QWERTY) resultará em traços-chave em US (QWERTY).

## <a name="learn-more"></a>Saiba Mais

 - Instale o [Gateway de dados local](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - [Use a documentação do aplicativo de gateway de dados local](https://docs.microsoft.com/flow/gateway-manage) .
 - [Solucionar problemas](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) do gateway de dados local.
