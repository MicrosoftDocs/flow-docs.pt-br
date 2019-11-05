---
title: Iniciar fluxos com botões Flic | Microsoft Docs
description: Inicie facilmente fluxos de botão com botões físicos do Flic por laboratórios de atalho.
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
ms.date: 05/19/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e6430f78ad2eccecc5af7f6606bb56e1a7eb4599
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544798"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Execute seus fluxos pressionando um botão inteligente flic (visualização)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Dispare seus fluxos pressionando um botão físico, conhecido como Flic, dos laboratórios de atalho. Por exemplo, pressione um flic para controlar suas horas de trabalho, bloquear seu calendário, contar visitantes em um evento ou salvar locais geográficos.

> [!IMPORTANT]
> Configure todas as propriedades Flic usando o aplicativo móvel do Flic para [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [Ios](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) antes de criar o fluxo.
> 
> 

## <a name="prerequisites"></a>Pré-requisitos
Para usar o os flics com Microsoft Flow, você deve ter:

* Acesso a [Microsoft Flow](https://flow.microsoft.com).
* Aplicativo móvel [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [Ios](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) do Flic baixado e usou-o para emparelhar um ou mais os flics.

## <a name="configure-flic-properties"></a>Configurar propriedades de Flic
Use o aplicativo móvel do Flic para programar os eventos do flic. Os eventos são:

* clique em (uma prensa rápida)
* Clique duas vezes (duas prensas rápidas)
* Espera (uma prensa longa)

Esta captura de tela mostra um exemplo de como o processo de configuração do Flic pode ser semelhante a:

![configurar o os flics](./media/flic-button-flows/configure-flic-actions.png)

Depois de vincular um evento Flic a Microsoft Flow, você poderá selecionar esse Flic como um gatilho para seus fluxos. Você seleciona os gatilhos mais adiante neste guia.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Criar um fluxo que é disparado por um flic
Neste tutorial, usamos um flic para executar um fluxo que registra o tempo que um consultor gasta em cada cliente. O consultor pressionará o Flic uma vez na chegada e, em seguida, o pressionará novamente, logo antes da partida do cliente. Cada prensa do Flic inicia uma execução do fluxo ao qual está conectada. O fluxo salva a hora atual nas planilhas do Google e, em seguida, envia uma notificação por email. O email contém detalhes sobre a execução do fluxo.

Observação: Certifique-se de que você usou o aplicativo móvel Flic para emparelhar e configure pelo menos uma ação de **clique** para disparar Microsoft Flow. Nesta captura de tela, configurei a ação de **clique** para disparar Microsoft Flow. Mais adiante neste tutorial, configuramos nosso fluxo para disparar quando o Flic é pressionado uma vez (clicado).

   ![configuração do Flic](./media/flic-button-flows/flic-configured-for-flow.png)

Vamos começar a criar nosso fluxo.

### <a name="start-with-a-template"></a>Iniciar com um modelo
1. Entre [Microsoft Flow](https://flow.microsoft.com).
   
    ![Entrar](./media/flic-button-flows/sign-into-flow.png)
2. Insira **Flic** na caixa de pesquisa e, em seguida, selecione o ícone de pesquisa.
   
    ![Pesquisar Flic](./media/flic-button-flows/search-flic.png)
3. Selecione o modelo **controlar suas horas de trabalho com o botão inteligente Flic** .
   
    ![Selecionar modelo](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Criar uma planilha no Google Sheets
1. Examine os detalhes do modelo e observe que este modelo requer uma planilha no Google sheets.
   
   ![examinar detalhes do modelo](./media/flic-button-flows/flic-template-details.png)
2. No Google sheets, crie uma planilha que contenha uma planilha com colunas nomeadas **clicktype** e **timestamp**.
   
      Dica: você nomeia colunas nas planilhas do Google inserindo o nome da coluna na parte superior da coluna. Portanto, sua planilha deve aparecer como esta captura de tela:
   
   ![Planilha do Google](./media/flic-button-flows/flic-google-sheet.png)
   
   Observação: você usará esta planilha mais adiante neste guia.

### <a name="add-the-flic-trigger-to-your-flow"></a>Adicionar o gatilho Flic ao seu fluxo
1. Entre nos serviços do modelo e selecione **continuar**.
   
     **Continue** é habilitado depois que você entra em todos os serviços necessários para o modelo.
   
    ![fornecer credenciais](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Insira **Flic** na caixa de pesquisa e, em seguida, selecione o gatilho **Flic-quando um flic é pressionado** .
   
    ![Pesquisar o gatilho Flic](./media/flic-button-flows/flic-search-trigger.png)
3. Selecione o Flic que você deseja usar na lista de **botões Flic** no cartão **Flic-quando um flic é pressionado** .
4. Selecione **clique** na lista **eventos** para indicar que você deseja disparar o fluxo quando o Flic for pressionado uma vez.
   
    ![Selecione a ação Flic](./media/flic-button-flows/select-flic.png)
   
   Opcionalmente, você pode selecionar **qualquer** para indicar que cada evento flic (clicar, clicar duas vezes ou manter) dispara o fluxo.
   
   **Clicar duas** vezes indica que o fluxo é disparado quando o Flic é rapidamente pressionado duas vezes. **Hold** indica que uma prensa longa no Flic dispara o fluxo.
   
   Você está livre para criar outros fluxos e dispará-los usando os outros eventos na lista de **eventos** . Por exemplo, você pode usar o evento de **clique duplo** para registrar o tempo que você sai de um cliente.

### <a name="configure-the-sheet"></a>Configurar a planilha
   No cartão **Inserir linha** :

1. Selecione a planilha que você criou anteriormente na lista de **arquivos** .
2. Selecione a planilha na lista **planilha** .
   
   Observação: duas caixas adicionais são exibidas no cartão **Inserir linha** depois que você seleciona a planilha. Essas caixas representam as duas colunas na planilha que você criou anteriormente.
3. Selecione a caixa **clicktype** e, em seguida, selecione o token de **tipo de clique** .
4. Selecione a caixa **timestamp** e, em seguida, selecione o token **tempo de clique** .
   
    ![configurar dados de planilhas do Google](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Confirme se as configurações de email estão corretas
1. Confirme se o cartão **enviar um email para mim** é semelhante a esta captura de tela.
   
    ![confirmar notificação por email](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Salve seu fluxo e teste-o
1. Dê um nome ao seu fluxo e, em seguida, salve-o.
   
    ![salvar seu fluxo](./media/flic-button-flows/save.png)

Se você seguiu, pressionar o Flic uma vez dispara o fluxo. Em seguida, o fluxo registra o tipo de clique e a hora atual na planilha e, em seguida, envia um email para você.

1. Pressione seu Flic uma vez.
2. Abra sua planilha no Google sheets. Você deve ver as colunas **clicktype** e **timestamp** populadas com o "clique" e a hora, respectivamente.
   
    ![consulte executar resultados](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. Você também pode ver os resultados da execução no site Microsoft Flow ou no aplicativo móvel Microsoft Flow. Aqui está uma captura de tela da minha execução de teste.
   
    ![salvar seu fluxo](./media/flic-button-flows/flic-test-run-results-portal.png)
4. Veja o que o corpo do email de notificação que recebi da execução do fluxo é semelhante.
   
    ![salvar seu fluxo](./media/flic-button-flows/flic-email-body.png)

Para obter crédito extra, considere estender o fluxo para registrar automaticamente seu local (Latitude e longitude) quando o Flic for pressionado.

## <a name="more-information"></a>Mais informações
* [Compartilhar fluxos de botão](share-buttons.md).
* Aprenda a usar [tokens de gatilho de botão](introduction-to-button-trigger-tokens.md) para enviar dados atuais quando os fluxos de botão são executados.
* Instale o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [Ios](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).

