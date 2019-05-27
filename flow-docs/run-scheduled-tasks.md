---
title: Executar fluxos agendados | Microsoft Docs
description: Automatize tarefas repetitivas executando fluxos agendados, como diariamente ou a cada hora.
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
ms.date: 09/14/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: af18e8caae8e74bb12d274c6e5cb0d94a0e0471b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64468360"
---
# <a name="run-flows-on-a-schedule"></a>Execute fluxos agendados
Crie um fluxo que execute uma ou mais tarefas (como enviar um relatório por email):

* uma vez por dia, hora ou minuto
* em uma data especificada
* depois de um número de dias, horas ou minutos especificado

## <a name="create-a-recurring-flow"></a>Crie um fluxo recorrente
1. Entre no [Microsoft Flow](https://flow.microsoft.com), em seguida, selecione **Meus fluxos** na barra de navegação superior.
   
    ![Opção Meus fluxos](./media/run-scheduled-tasks/create-flow.png)
2. Selecione **Criar do zero**.
   
    ![Crie um fluxo do zero](./media/run-scheduled-tasks/create-from-blank.png)
3. Na caixa **Pesquisar todos os conectores e gatilhos**, digite **Recorrência**, em seguida, selecione **Agendamento - Recorrência**.
   
    ![Localizar o gatilho de recorrência](./media/run-scheduled-tasks/select-recurrence.png)
4. Na caixa de diálogo **Recorrência**, especifique a frequência na qual deseja executar o fluxo.
   
    Por exemplo, especifique **2** em **Intervalo** e **Semana** em **Frequência** se quiser que o fluxo seja executado a cada duas semanas.
   
    ![Especificar recorrência](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Especificar opções avançadas
1. Siga as etapas na seção anterior e selecione **Mostrar opções avançadas**.
   
    **Observação**: Essas opções mudam com base nos valores para os quais o **Intervalo** e a **Frequência** são definidos. Se a tela não coincidir com o gráfico a seguir, verifique se o **Intervalo** e a **Frequência** estão definidos para os mesmos valores que o gráfico mostra.
2. Selecione um **Fuso horário** para especificar se a **Hora de início** reflete um fuso horário local, Hora Universal Coordenada (UTC) etc.
3. Especifique uma **Hora de início** neste formato:
   <br>AAAA-MM-DDTHH:MM:SSZ
4. Se você especificou **Dia** em **Frequência**, especifique a hora do dia em que o fluxo deve ser executado.
5. Se você especificou **Semana** em **Frequência**, especifique o dia ou dias da semana em que o fluxo deve ser executado e a hora ou horas do dia em que o fluxo deve ser executado.
   
    Por exemplo, configure as opções conforme mostrado para iniciar um fluxo não antes do meio-dia (hora do Pacífico) na segunda-feira, 1º de janeiro de 2018, e executá-lo a cada duas semanas às terças-feiras às 17:30 (hora do Pacífico).
   
    ![Especificar opções avançadas](./media/run-scheduled-tasks/advanced-options.png)
6. Adicione a ação ou ações que você deseja que sejam feitas no fluxo, como descrito em [Criar um fluxo do zero](get-started-logic-flow.md).

## <a name="delay-a-flow"></a>Atrasar um fluxo
1. Entre no [Microsoft Flow](https://flow.microsoft.com), em seguida, selecione **Meus fluxos** na barra de navegação superior.
   
    ![Crie um fluxo do zero](./media/run-scheduled-tasks/create-flow.png)
2. Selecione **Criar do zero**.
   
    ![Crie um fluxo do zero](./media/run-scheduled-tasks/create-from-blank.png)
3. Especifique um evento, como descrito em [Criar um fluxo do zero](get-started-logic-flow.md).
4. Selecione **Nova Etapa** e depois selecione **Adicionar uma ação**.
   
    ![Opção para adicionar uma ação a um fluxo](./media/run-scheduled-tasks/add-action.png)
5. Na lista de ações, siga um destes procedimentos:
   
   * Selecione **Atrasar**, especifique uma **Contagem**e uma **Unidade** de tempo, como segundo, minuto ou hora.
   * Selecione **Atrasar até** e especifique uma data neste formato.<br>AAAA-MM-DDTHH:MM:SSZ
     
     ![Adicionar um atraso](./media/run-scheduled-tasks/add-delay.png)
     ![Especificar o atraso em unidades de tempo](./media/run-scheduled-tasks/delay.png)
     ![Especificar um atraso até](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Saiba mais

Saiba mais sobre as [opções avançadas](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) e como configurá-las.

