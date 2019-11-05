---
title: Crie fluxos com o Microsoft Visio | Microsoft Docs
description: Aproveite a experiência do Visio de sua organização para criar modelos comuns como um ponto de partida para criar fluxos.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/25/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 0ffe9fbf8c29682bbcb941dbb48f9986f3c7144d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548771"
---
# <a name="design-flows-in-microsoft-visio"></a>Fluxos de design no Microsoft Visio
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

O designer de Microsoft Flow é uma ferramenta avançada na qual você pode configurar cada detalhe da sua lógica. No entanto, às vezes você pode querer apenas esboçar sua lógica de fluxo antes de começar a criar seu fluxo. Para fazer isso, use o Microsoft Visio diretamente no Microsoft Flow.

>[!TIP]
> Muitos processos compartilham um modelo comum, mas têm pequenas variações em toda a organização. Você pode economizar tempo dentro de sua organização usando o Visio para criar um modelo de fluxo de trabalho mestre que outras pessoas irão ajustar com parâmetros especializados.

## <a name="prerequisites"></a>Pré-requisitos

- Uma conta de Microsoft Flow.
- O aplicativo da área de trabalho do Microsoft Visio (versão em inglês).
- Experiência no uso do Microsoft Visio.

## <a name="design-a-workflow-in-visio"></a>Criar um fluxo de trabalho no Visio

1. Entre [Microsoft Flow](https://flow.microsoft.com).
1. Selecione **modelos** no painel do lado esquerdo.

     ![Selecionar modelos no painel esquerdo](./media/visio-flows/templates-from-left-panel.png)

1. Selecione **Visio** na lista.

     ![Filtrar para modelos do Visio](./media/visio-flows/select-visio.png) 

1. Selecione o modelo de **diagrama BPMN de fluxo básico** na lista de modelos do **Visio** que o exibe.

     ![Selecionar um modelo do Visio](./media/visio-flows/visio-templates.png) 

     >[!IMPORTANT]
     >O Visio avisa que os arquivos da Internet podem danificar seu dispositivo. Se você estiver familiarizado, selecione **Sim** na mensagem de aviso.

     ![Observação de aviso sobre arquivos da Internet](./media/visio-flows/visio-warning.png)

1. O designer do Visio é iniciado.

     ![Exibição do designer do Visio](./media/visio-flows/visio-designer.png)


1. Use as formas básicas do BPMN para [criar seu fluxo de trabalho](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a).

   ![Formas básicas BPMN](./media/visio-flows/bpmn-basic-shapes.png)

## <a name="prepare-to-export-your-workflow-to-microsoft-flow"></a>Preparar para exportar seu fluxo de trabalho para Microsoft Flow

Siga estas etapas para preparar seu fluxo de trabalho para que você possa exportá-lo para Microsoft Flow.

1. Selecione a guia **processo** .
1. Selecione **preparar para exportar** do grupo de **Microsoft Flow** de ícones.

   ![Selecione o ícone preparar para exportar](./media/visio-flows/prepare-export-icon.png)
   
   O grupo **preparar para exportar** é aberto.

   ![Preparar grupo de exportação](./media/visio-flows/prepare-export-group.png)

1. Na guia **mapeamento de fluxo** do grupo **preparar para exportar** , mapeie seu diagrama BPMN para Microsoft Flow controles. 

1. Na guia **gatilhos e ações** do grupo **preparar para exportar** , mapeie seu diagrama BPMN para Microsoft Flow gatilhos e ações selecionando cada forma e, em seguida, selecionando um gatilho ou uma ação para representar essa forma em Microsoft Flow.

O fluxo de trabalho está pronto para ser exportado quando não há problemas restantes no controle **preparar para exportar** .

![Sem problemas](./media/visio-flows/prepare-export-no-issues.png) 

## <a name="export-your-workflow"></a>Exportar seu fluxo de trabalho
1. Selecione o botão **exportar para fluxo** para exportar seu diagrama de fluxo de trabalho para Microsoft Flow.
1. Nomeie seu fluxo e, em seguida, selecione o botão **criar fluxo** .
   
   ![Criar o fluxo](./media/visio-flows/export-create-flow.png)

1. Você deverá ver um relatório de êxito semelhante a este.

    ![Êxito](./media/visio-flows/export-create-flow-success.png)

Agora você pode executar ou fazer edições no seu fluxo por meio do designer de Microsoft Flow, assim como qualquer outro fluxo.

>[!TIP]
> Use os recursos de compartilhamento e comentários do Visio para colaborar com vários participantes e criar um fluxo de trabalho completo rapidamente.

## <a name="learn-more"></a>Saiba Mais

- [Introdução ao Microsoft Flow](getting-started.md) 
- [Criar fluxos de várias etapas](multi-step-logic-flow.md)
- [Criar um fluxo com o Microsoft Visio](https://support.office.com/article/design-a-microsoft-flow-in-visio-35f0c9a9-912b-486d-88f7-4fc68013ad1a)

     
