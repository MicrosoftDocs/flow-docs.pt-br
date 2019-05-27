---
title: Iniciar os fluxos com botões Flic | Microsoft Docs
description: Inicie facilmente os fluxos de botão com botões físicos Flic da Shortcut Labs.
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
ms.openlocfilehash: bbcb6c8950e8ac5959880727604e0355b3150c6f
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64455635"
---
# <a name="run-your-flows-by-pressing-a-flic-smart-button-preview"></a>Executar seu fluxos pressionando um botão inteligente Flic (Visualização)
Dispare seus fluxos pressionando um botão físico, conhecido como Flic, da Shortcut Labs. Por exemplo, pressione um Flic para controlar o horário de trabalho, bloquear seu calendário, contar os visitantes em um evento ou salvar as localizações geográficas.

> [!IMPORTANT]
> Configure todas as propriedades do Flic usando o aplicativo móvel do Flic para [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) antes de criar seu fluxo.
> 
> 

## <a name="prerequisites"></a>Pré-requisitos
Para usar os Flics com o Microsoft Flow, você deve ter:

* acesso ao [Microsoft Flow](https://flow.microsoft.com).
* baixado o aplicativo móvel [Android](https://play.google.com/store/apps/details?id=io.flic.app) ou [iOS](https://itunes.apple.com/us/app/flic-app/id977593793?ls=1&mt=8) do Flic e usado-o para emparelhar um ou mais Flics.

## <a name="configure-flic-properties"></a>Configurar as propriedades do Flic
Use o aplicativo móvel do Flic programar os eventos do Flic. Os eventos são:

* clique (pressionar rapidamente)
* dois cliques (pressionar rapidamente duas vezes)
* segurar (pressionar por mais tempo)

Esta captura de tela mostra um exemplo de como pode ser o processo de configuração do Flic:

![configurar os Flics](./media/flic-button-flows/configure-flic-actions.png)

Depois de ter vinculado um evento Flic ao Microsoft Flow, você poderá selecionar esse Flic como um gatilho para seus fluxos. Você selecionará os gatilhos posteriormente neste passo a passo.

## <a name="create-a-flow-thats-triggered-by-a-flic"></a>Criar um fluxo que é disparado por um Flic
Neste passo a passo, usamos um Flic para executar um fluxo que registra o tempo que um consultor passa com cada cliente. O consultor pressiona o Flic uma vez na chegada e pressiona-o novamente, um pouco antes da partida do cliente. Cada Flic pressionado inicia uma execução do fluxo ao qual ele está conectado. O fluxo salva a hora atual nas planilhas do Google e envia uma notificação por email. O email contém detalhes sobre a execução do fluxo.

Observação: Certifique-se de que você já usou o aplicativo móvel do Flic para emparelhar e configurar pelo menos um **clique em** ação para disparar o Microsoft Flow. Nessa tela, eu configurei a ação de **clique** para disparar o Microsoft Flow. Posteriormente neste passo a passo, iremos configurar nosso fluxo para disparar quando o Flic for pressionado uma vez (clicado).

   ![configuração do flic](./media/flic-button-flows/flic-configured-for-flow.png)

Vamos começar criando nosso fluxo.

### <a name="start-with-a-template"></a>Começar com um modelo
1. Entre no [Microsoft Flow](https://flow.microsoft.com).
   
    ![entrar](./media/flic-button-flows/sign-into-flow.png)
2. Digite **flic** na caixa de pesquisa e selecione o ícone de pesquisa.
   
    ![pesquisar flic](./media/flic-button-flows/search-flic.png)
3. Selecione o modelo **Controlar suas horas de trabalho com o botão inteligente Flic**.
   
    ![selecionar modelo](./media/flic-button-flows/flic-templates.png)

### <a name="create-a-spreadsheet-in-google-sheets"></a>Criar uma planilha nas Planilhas do Google
1. Revise os detalhes do modelo e observe que esse modelo requer uma planilha nas Planilhas do Google.
   
   ![revisar os detalhes do modelo](./media/flic-button-flows/flic-template-details.png)
2. Nas Planilhas do Google, crie uma planilha que contenha uma folha com colunas denominadas **TipoClique** e **CarimboHora**.
   
      Dica: Você nomeia as colunas nas planilhas do Google digitando o nome da coluna na parte superior da coluna. Assim, sua planilha deverá parecer com esta captura de tela:
   
   ![Planilhas do Google](./media/flic-button-flows/flic-google-sheet.png)
   
   Observação: Você usará esta planilha posteriormente neste passo a passo.

### <a name="add-the-flic-trigger-to-your-flow"></a>Adicionar o gatilho do Flic ao seu fluxo
1. Entre nos serviços do modelo e selecione **Continuar**.
   
     **Continuar** será habilitado depois de você entrar nos serviços necessários para o modelo.
   
    ![fornecer credenciais](./media/flic-button-flows/flic-template-services-sign-in.png)
2. Digite **flic** na caixa de pesquisa e selecione o gatilho **Flic - Quando um Flic é pressionado**.
   
    ![pesquisar gatilho do flic](./media/flic-button-flows/flic-search-trigger.png)
3. Selecione o Flic que você deseja usar na lista **botão Flic** no cartão **Flic - Quando um Flic é pressionado**.
4. Selecione **clique** na lista **Eventos** para indicar que você deseja disparar o fluxo quando o Flic for pressionado uma vez.
   
    ![selecionar ação do flic](./media/flic-button-flows/select-flic.png)
   
   Opcionalmente, você pode selecionar **qualquer** para indicar que cada evento do Flic (clicar, clicar duas vezes ou segurar) dispara o fluxo.
   
   **Dois cliques** indica que o fluxo dispara quando o Flic é pressionado rapidamente duas vezes. **Segurar** indica que um pressionamento longo no Flic dispara o fluxo.
   
   Você pode criar outros fluxos e dispará-los usando os outros eventos na lista **Eventos**. Por exemplo, você pode usar o evento **Dois cliques** para registrar o momento no qual você deixa um cliente.

### <a name="configure-the-sheet"></a>configurar a planilha
   No cartão **Inserir linha**:

1. Selecione a planilha que você criou anteriormente na lista **Arquivo**.
2. Selecione a planilha na lista **Planilha**.
   
   Observação: Duas caixas adicionais aparecerão na **Inserir linha** depois de selecionar a planilha de cartão. Essas caixas representam as duas colunas na planilha criada anteriormente.
3. Marque a caixa **TipoClique** e selecione o token **Tipo do clique**.
4. Marque a caixa **CarimboHora** e selecione o token **Hora do clique**.
   
    ![configurar dados das Planilhas do Google](./media/flic-button-flows/flick-insert-row-card.png)

### <a name="confirm-the-email-settings-are-correct"></a>Confirmar se as configurações de email estão corretas
1. Confirme se o cartão **Enviar uma notificação por email** se parece com esta captura de tela.
   
    ![confirmar notificação por email](./media/flic-button-flows/email-settings.png)

### <a name="save-your-flow-and-test-it"></a>Salvar seu fluxo e testá-lo
1. Nomeie seu fluxo e salve-o.
   
    ![salvar seu fluxo](./media/flic-button-flows/save.png)

Se você acompanhou até aqui, pressionar o Flic uma vez irá disparar o fluxo. Então, o fluxo registra o tipo de clique e a hora atual na planilha, em seguida, envia um email para você.

1. Pressione o Flic uma vez.
2. Abra a planilha nas Planilhas do Google. Você deverá ver as colunas **TipoClique** e **CarimboHora** preenchidas com o "clique" e a hora, respectivamente.
   
    ![ver resultados da execução](./media/flic-button-flows/flic-google-sheet-after-run.png)
3. Você também pode ver os resultados da execução no site do Microsoft Flow ou no aplicativo móvel do Microsoft Flow. Aqui está uma captura de tela de minha execução de teste.
   
    ![salvar seu fluxo](./media/flic-button-flows/flic-test-run-results-portal.png)
4. O corpo do email de notificação recebido da execução do fluxo tem esta aparência.
   
    ![salvar seu fluxo](./media/flic-button-flows/flic-email-body.png)

Para ter um crédito extra, considere estender o fluxo para registrar automaticamente sua localização (latitude e longitude) quando o Flic for pressionado.

## <a name="more-information"></a>Mais informações
* [Compartilhe os fluxos do botão](share-buttons.md)
* Aprenda a usar os [tokens de gatilho do botão](introduction-to-button-trigger-tokens.md) para enviar dados atuais quando os fluxos do botão forem executados.
* Instale o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows).

