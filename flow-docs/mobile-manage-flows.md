---
title: Gerenciar fluxos usando o telefone | Microsoft Docs
description: Exiba uma lista dos seus fluxos, habilite ou desabilite-os e exiba evento(s), ação(ões) e histórico de execução de cada fluxo
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
ms.openlocfilehash: 4a35166ec57e81b957f7659e0e670e80bbf510ca
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64467697"
---
# <a name="manage-flows-in-microsoft-flow-from-your-phone"></a>Gerencie fluxos no Microsoft Flow usando seu telefone
Exiba uma lista de todos os fluxos que você criou e, para cada fluxo, exiba os eventos e ações, habilite ou desabilite-o e explore seu histórico de execução.

**Pré-requisitos**

* Instale o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows) em um [dispositivo com suporte](getting-started.md#use-the-mobile-app). As imagens neste tópico refletem a versão do aplicativo para iPhone, mas as imagens em Android e Windows Phone parecem semelhantes.
* Se você ainda não tiver um fluxo, crie um no [site do Microsoft Flow](https://flow.microsoft.com/). Para testes mais fáceis, use um que você mesmo pode disparar em vez de ter que aguardar um evento externo.

O fluxo neste tutorial é executado quando você receber o email de um endereço específico:

![Dispara o fluxo com o recebimento de uma mensagem de um endereço específico](./media/mobile-manage-flows/create-trigger.png)

Você pode configurar um fluxo desses, usando seu endereço de email pessoal para testar e usar um endereço diferente (por exemplo, o do seu gerente) quando o fluxo estiver pronto para o uso real.

Quando o fluxo é executado, ele envia uma notificação por push personalizada, com essa sintaxe, ao seu telefone:

![Enviar uma mensagem no Slack](./media/mobile-manage-flows/create-event.png)

**Observação**: Você também pode [monitorar a atividade de fluxo](mobile-monitor-activity.md) do aplicativo móvel.

## <a name="manage-a-flow"></a>Gerenciar um fluxo
1. Abra o aplicativo móvel e, em seguida, toque em **Meus fluxos** na parte inferior da tela para listar todos os seus fluxos.
   
    Cada entrada mostra o nome do fluxo, ícones para seus eventos e ações, quando ele foi executado mais recentemente e um ícone que indica se a execução mais recente foi bem-sucedida.
   
    ![Lista de fluxos](./media/mobile-manage-flows/flow-list.png)
2. Toque em um fluxo para mostrar as opções de gerenciamento.
   
    ![Opções para gerenciar um fluxo](./media/mobile-manage-flows/flow-details.png)
3. Tocar na alternância **Habilitar fluxo** para habilitar ou desabilitar o fluxo.
4. Toque em **Ver fluxo** para mostrar os eventos e as ações daquele fluxo, toque em cada evento ou em uma ação para expandi-la e, em seguida, toque em **Voltar**.
   
    ![Eventos e ações para um fluxo](./media/mobile-manage-flows/flow-event-action.png)
5. Toque em **Histórico de execução** para mostrar execuções bem-sucedidas do fluxo, falhas ou ambos.
   
    ![Lista de execuções](./media/mobile-manage-flows/history-mixed.png)
6. Toque em uma execução para mostrar se cada evento e a ação foi bem-sucedida e, nesse caso, quanto tempo (em segundos) a execução levou.
   
    ![Detalhes da execução](./media/mobile-manage-flows/flow-run.png)

