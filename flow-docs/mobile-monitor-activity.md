---
title: Monitorar a atividade usando seu telefone | Microsoft Docs
description: Veja quantas vezes cada fluxo foi bem-sucedido ou falhou, quando ocorreu cada execução e quanto tempo demorou
services: ''
suite: flow
documentationcenter: na
author: adiregev
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/11/2016
ms.author: adiregev
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3ba49aff12118d79d41a7b76f7c8a0f7e3f1d01b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64467921"
---
# <a name="monitor-activity-in-microsoft-flow-from-your-phone"></a>Monitore a atividade do Microsoft Flow usando seu telefone
Exiba um resumo de quantas vezes cada fluxo foi bem-sucedido ou falhou hoje, ontem e em dias anteriores. Explore os detalhes sobre cada execução, tais como quando foi executado, quanto tempo cada etapa levou e, se falhou, o motivo.

**Pré-requisitos**

<iframe width="560" height="315" src="https://www.youtube.com/embed/vZuYZ64K3tI?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

* Instale o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows) em um [dispositivo com suporte](getting-started.md#use-the-mobile-app). As imagens neste tópico refletem a versão do aplicativo para iPhone, mas a interface os gráficos em Android e Windows Phone são semelhantes.
* Se você ainda não tiver um fluxo, crie um no [site do Microsoft Flow](https://flow.microsoft.com/). Para testes mais fáceis, use um que você mesmo pode disparar em vez de ter que aguardar um evento externo.

O fluxo neste tutorial é executado quando você receber o email de um endereço específico:

![Dispara o fluxo com o recebimento de uma mensagem de um endereço específico](./media/mobile-monitor-activity/create-trigger.png)

Você pode configurar um fluxo desses, usando seu endereço de email pessoal para testar e usar um endereço diferente (por exemplo, o do seu gerente) quando o fluxo estiver pronto para o uso real.

Quando o fluxo é executado, ele envia uma notificação por push personalizada, com essa sintaxe, ao seu telefone:

![Enviar notificação por push](./media/mobile-monitor-activity/create-event.png)

**Observação:** Você também pode [gerenciar seus fluxos](mobile-manage-flows.md) do aplicativo móvel.

## <a name="display-a-summary-of-activity"></a>Exibir um resumo de atividades
<iframe width="560" height="315" src="https://www.youtube.com/embed/nVCGJamOw6s?list=PL8nfc9haGeb55I9wL9QnWyHp3ctU2_ThF" frameborder="0" allowfullscreen></iframe>

1. Se seu fluxo ainda não foi executado, dispare uma execução para gerar dados.
   
    Pode levar algum tempo para que os dados sejam exibidos no aplicativo.
2. Abra o aplicativo móvel, que mostra a guia **Atividade** por padrão.
   
    Essa guia organiza dados por dia, com dados atuais na parte superior.
   
    ![Atividade organizada por dia](./media/mobile-monitor-activity/activity-day2.png)
   
    Cada entrada mostra o nome de um fluxo com ícones que correspondem aos seus eventos e ações de gatilho.
   
    ![Nome e ícones de cada fluxo](./media/mobile-monitor-activity/activity-flow-name.png)
   
    Se pelo menos uma execução de um fluxo foi bem-sucedida em um dia, uma entrada mostra o número de execuções bem-sucedidas e a hora mais recente em que isso ocorreu. Uma entrada diferente mostra informações semelhantes se um fluxo falhou.
   
    ![Resumo de execuções bem-sucedidas ou falhas](./media/mobile-monitor-activity/activity-summary.png)
   
    Se um fluxo de enviar uma notificação por push, o texto da notificação mais recente aparecerá na parte inferior da entrada de execuções bem-sucedidas.
   
    ![Exemplo de notificação por push](./media/mobile-monitor-activity/activity-notification.png)
3. Se várias notificações de push foram enviadas em um dia, passe o dedo para a esquerda sobre a notificação para exibir notificações de até três execuções anteriores. Se mais de quatro notificações forem enviadas em um dia, passe o dedo para a esquerda até o **Ver mais** aparecer e, em seguida, toque para exibir uma lista de todas as notificações.
   
    ![Exemplo de notificação por push](./media/mobile-monitor-activity/activity-notification-list.png)
4. Toque em **Voltar** para retornar para o resumo de atividades.
5. Para filtrar o resumo de atividades, toque no ícone no canto superior direito.
   
    Você pode mostrar todas as entradas, somente as entradas de falhas ou apenas as entradas que incluem notificações por push.
   
    ![Mostrar todas as execuções, somente falhas ou apenas as notificações](./media/mobile-monitor-activity/activity-filter.png)

## <a name="show-details-of-a-run"></a>Mostrar detalhes de uma execução
1. No resumo de atividades, toque em uma entrada para mostrar os detalhes da execução mais recente.
   
     Cada evento e ação aparece com um ícone que indica se o evento ou a ação foi bem-sucedida ou falhou. Se foi bem-sucedida, também será exibido quanto tempo levou (em segundos).
   
    ![Detalhes de uma execução](./media/mobile-monitor-activity/activity-icons.png)
2. Na parte inferior da tela, toque em **Ver execuções anteriores** para listar todas as execuções do fluxo e, em seguida, toque em uma execução para mostrar seus detalhes.
   
    ![Histórico de execuções bem-sucedidas / falha](./media/mobile-monitor-activity/history-mixed.png)

