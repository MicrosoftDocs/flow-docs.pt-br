---
title: Executar fluxos em um agendamento | Microsoft Docs
description: Automatize tarefas recorrentes executando fluxos em um agendamento, como todos os dias ou a cada hora.
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
ms.openlocfilehash: b737f416c927e7d7d8a7ea28ec81e268aa59b51d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548839"
---
# <a name="run-flows-on-a-schedule"></a>Executar fluxos em uma agenda
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Crie um fluxo que executa uma ou mais tarefas (como enviar um relatório no email):

* uma vez por dia, uma hora ou um minuto
* em uma data que você especificar
* após um número de dias, horas ou minutos que você especificar

## <a name="create-a-recurring-flow"></a>Criar um fluxo recorrente
1. Entre no [Microsoft Flow](https://flow.microsoft.com)e, em seguida, selecione **meus fluxos** na barra de navegação superior.
   
    ![Opção Meus fluxos](./media/run-scheduled-tasks/create-flow.png)
2. Selecione **criar em branco**.
   
    ![Criar um fluxo de branco](./media/run-scheduled-tasks/create-from-blank.png)
3. Na caixa **Pesquisar todos os conectores e gatilhos** , digite **recorrência**e selecione **agenda-recorrência**.
   
    ![Localizar gatilho de recorrência](./media/run-scheduled-tasks/select-recurrence.png)
4. Na caixa de diálogo **recorrência** , especifique com que frequência você deseja que o fluxo seja executado.
   
    Por exemplo, especifique **2** em **intervalo** e **semana** em **frequência** se você quiser que o fluxo seja executado a cada duas semanas.
   
    ![Especificar recorrência](./media/run-scheduled-tasks/specify-recurrence.png)

## <a name="specify-advanced-options"></a>Especificar opções avançadas
1. Siga as etapas na seção anterior e, em seguida, selecione **Mostrar opções avançadas**.
   
    **Observação**: essas opções são alteradas com base nos valores para os quais o **intervalo** e a **frequência** são definidos. Se a tela não corresponder ao gráfico abaixo, verifique se o **intervalo** e a **frequência** estão definidos com os mesmos valores mostrados pelo gráfico.
2. Selecione um **fuso horário** para especificar se a **hora de início** reflete um fuso horário local, UTC (horário coordenado universal) etc.
3. Especifique uma **hora de início** neste formato:
   <br>AAAA-MM-DDTHH: MM: SSZ
4. Se você especificou **dia** em **frequência**, especifique a hora do dia em que o fluxo deve ser executado.
5. Se você especificou **semana** em **frequência**, especifique o dia ou os dias da semana em que o fluxo deve ser executado e a hora ou as horas do dia em que o fluxo deve ser executado.
   
    Por exemplo, configure as opções conforme mostrado para iniciar um fluxo não antes do meio-dia (hora do Pacífico) na segunda-feira, 1º de janeiro de 2018 e execute-o a cada duas semanas às terças-feiras às 30P (hora do Pacífico).
   
    ![Especificar opções avançadas](./media/run-scheduled-tasks/advanced-options.png)
6. Adicione a ação ou ações que você deseja que o fluxo execute, como descrito [em criar um fluxo do zero](get-started-logic-flow.md) .

## <a name="delay-a-flow"></a>Atrasar um fluxo
1. Entre no [Microsoft Flow](https://flow.microsoft.com)e, em seguida, selecione **meus fluxos** na barra de navegação superior.
   
    ![Criar um fluxo de branco](./media/run-scheduled-tasks/create-flow.png)
2. Selecione **criar em branco**.
   
    ![Criar um fluxo de branco](./media/run-scheduled-tasks/create-from-blank.png)
3. Especifique um evento como [criar um fluxo do zero](get-started-logic-flow.md) descreve.
4. Selecione **nova etapa**e, em seguida, selecione **Adicionar uma ação**.
   
    ![Opção para adicionar uma ação a um fluxo](./media/run-scheduled-tasks/add-action.png)
5. Na lista de ações, siga um destes procedimentos:
   
   * Selecione **atraso**, especifique uma **contagem**e especifique uma **unidade** de tempo, como segundo, minuto ou hora.
   * Selecione **atrasar até**e, em seguida, especifique uma data neste formato.<br>AAAA-MM-DDTHH: MM: SSZ
     
     ![adicionar um atraso](./media/run-scheduled-tasks/add-delay.png)
     ![especificar o atraso em unidades de tempo](./media/run-scheduled-tasks/delay.png)
     ![especifique o atraso até](./media/run-scheduled-tasks/delay-until.png)

## <a name="learn-more"></a>Saiba Mais

Saiba mais sobre as [Opções avançadas](https://docs.microsoft.com/azure/connectors/connectors-native-recurrence) e como configurá-las.

