---
title: Gerenciar fluxos do seu telefone | Microsoft Docs
description: Exibir uma lista de seus fluxos, habilitá-los ou desabilitá-los e exibir o histórico de eventos/s, ações/s e a execução de cada fluxo
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
ms.openlocfilehash: 6f452f52d654d6f03a3262de8888c68cb2480704
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548631"
---
# <a name="manage-flows-in-microsoft-flow-from-your-phone"></a>Gerenciar fluxos em Microsoft Flow do seu telefone
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Exiba uma lista de todos os fluxos que você criou e, para cada fluxo, exiba seus eventos e ações, habilite ou desabilite-o e explore seu histórico de execução.

**Pré-requisitos**

* Instale o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [Ios](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows) em um [dispositivo com suporte](getting-started.md#use-the-mobile-app). Os gráficos neste tópico refletem a versão do aplicativo para iPhone, mas os elementos gráficos no Android e Windows Phone parecem semelhantes.
* Se você ainda não tiver um fluxo, crie um no [site para Microsoft Flow](https://flow.microsoft.com/). Para um teste mais fácil, use um que possa ser disparado em vez de aguardar um evento externo.

O fluxo neste tutorial é executado quando você recebe o email de um endereço específico:

![Disparar fluxo no recebimento de email de endereço específico](./media/mobile-manage-flows/create-trigger.png)

Você pode configurar um fluxo desse tipo com seu endereço de email pessoal para teste e um endereço diferente (por exemplo, o seu gerente) quando o fluxo estiver pronto para uso real.

Quando o fluxo é executado, ele envia uma notificação por push personalizada, com essa sintaxe, ao seu telefone:

![Enviar mensagem para a margem de atraso](./media/mobile-manage-flows/create-event.png)

**Observação**: você também pode [monitorar a atividade de fluxo](mobile-monitor-activity.md) do aplicativo móvel.

## <a name="manage-a-flow"></a>Gerenciar um fluxo
1. Abra o aplicativo móvel e, em seguida, toque em **meus fluxos** na parte inferior da tela para listar todos os seus fluxos.
   
    Cada entrada mostra o nome do fluxo, os ícones para seus eventos e ações, a hora em que ele foi executado mais recentemente e um ícone que indica se a execução mais recente foi bem-sucedida.
   
    ![Lista de fluxos](./media/mobile-manage-flows/flow-list.png)
2. Toque em um fluxo para mostrar opções para gerenciá-lo.
   
    ![Opções para gerenciar um fluxo](./media/mobile-manage-flows/flow-details.png)
3. Toque na alternância **habilitar fluxo** para habilitar ou desabilitar o fluxo.
4. Toque em **Ver fluxo** para mostrar os eventos e as ações desse fluxo, toque em cada evento ou em uma ação para expandi-lo e, em seguida, toque em **voltar**.
   
    ![Eventos e ações para um fluxo](./media/mobile-manage-flows/flow-event-action.png)
5. Toque em **histórico de execução** para mostrar os êxitos do fluxo, falhas ou ambos.
   
    ![Lista de execuções](./media/mobile-manage-flows/history-mixed.png)
6. Toque em uma execução para mostrar se cada evento e ação teve êxito e, se for, quanto tempo (em segundos) demorou.
   
    ![Detalhes da execução](./media/mobile-manage-flows/flow-run.png)

