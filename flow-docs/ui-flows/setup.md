---
title: Configurar fluxos de interface do usuário em seu dispositivo | Microsoft Docs
description: Configurar fluxos de interface do usuário em seu dispositivo
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
ms.openlocfilehash: 9e5029189df9807ba727efbe377392f87ef20884
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589693"
---
# <a name="set-up-ui-flows"></a>Configurar fluxos da interface do usuário

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Para poder usar o dispositivo para criar fluxos de interface do usuário, você precisará garantir que ele atenda aos requisitos descritos aqui.

> [!TIP]
> Antes de criar um fluxo de interface do usuário, verifique a [lista de conectores](https://flow.microsoft.com/connectors/) para ver se o aplicativo que você deseja automatizar já tem um conector. Se tiver, considere criar um fluxo em vez de um fluxo de interface do usuário. Você também pode criar seu [próprio conector](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Pré-requisitos

- Um plano de energia [pago](https://flow.microsoft.com/pricing/) ou de [avaliação](https://flow.microsoft.com/manage/) automatizada.

- Uma conta corporativa ou de estudante para entrar na automatização de energia e no dispositivo Windows.

- Um dispositivo que executa o Windows 10, o Windows Server 2016 ou o Windows Server 2019.
- Um teclado dos EUA (QWERTY) anexado.

- A [próxima versão do Microsoft Edge ou do](https://www.microsoftedgeinsider.com) Google Chrome.

- Um [ambiente](https://docs.microsoft.com/power-platform/admin/environments-overview) com um [banco de dados Common Data Service](https://docs.microsoft.com/power-platform/admin/create-database).

> [!IMPORTANT]
> Os fluxos da interface do usuário estão sendo distribuídos em regiões. Se você não vir o recurso de visualização ou não puder criar novos fluxos de interface do usuário, tente novamente mais tarde.


## <a name="limitations"></a>Limitações

Os fluxos da interface do usuário (versão prévia) estão disponíveis em inglês.

Não há suporte para os seguintes:

-   Fluxos de interface do usuário de desktop

    -   Vários monitores
    -   Máquinas virtuais
    -   Clique duplo, focalizado com o mouse, entrada por toque/caneta
    -   Interações no Windows (explorador de arquivos, menu de inicialização, barra de tarefas, etc.)

-   Fluxos de interface do usuário da Web

    -   Clique com o botão direito
    -   As informações de sessão do usuário (por exemplo: cookies) não serão reutilizadas durante a reprodução. Você precisará editar o script para inserir informações de entrada quando exigido pelos sites.

Você encontrará limitações específicas do recurso incluídas na documentação de cada recurso.

## <a name="get-your-device-ready"></a>Prepare seu dispositivo

Instale os seguintes componentes para criar e executar fluxos de interface do usuário:

|  | **Nomes**                             | **Usos**  |                                                        
|---|--------------------------------------|----------------------------------------------------------------------|
|   | [O aplicativo de fluxos de interface do usuário](https://go.microsoft.com/fwlink/?linkid=2102613)                         | Registrar aplicativos do Windows na área de trabalho                                  |          |
|   | Extensão do navegador de fluxos de interface do usuário           | Registre e teste aplicativos do Windows para desktops. Registrar aplicativos Web. |                                                                                              |
|   | Unidade de disco                            | Testar e executar aplicativos do Windows para desktops                            |                                                                                              |
|   | [Selenium IDE](https://go.microsoft.com/fwlink/?linkid=2107665) | Gravar e reproduzir aplicativos Web                                 |  |
|   | [Gateway](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)                              | Usado para habilitar eventos, fluxos agendados ou fluxos de botão para se conectar, disparar seus fluxos de interface do usuário (em execução dentro de sua organização) e executá-los.              |  | 

## <a name="install-the-ui-flows-app"></a>Instalar o aplicativo de fluxos de interface do usuário

O instalador de fluxos de interface do usuário contém todos os componentes necessários para gravar, editar e testar fluxos de interface do usuário para área de trabalho. 

>[!IMPORTANT]
>O instalador de fluxos de interface do usuário instala o componente WebDriver e a extensão do navegador de fluxos de interface do usuário. Ambos são necessários para gravar, testar e executar fluxos de interface do usuário para área de trabalho.

Siga estas etapas para instalar o aplicativo de fluxos de interface do usuário:

1. [Baixe o instalador do aplicativo de fluxos de interface do usuário](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Abra o arquivo **Setup. Microsoft. Flow. UIflow. exe** . Esse arquivo provavelmente está na pasta **downloads** depois que você o baixou na etapa anterior.
1. Siga as instruções no instalador de **instalação de fluxos de interface do usuário (versão prévia)** para concluir a instalação.

## <a name="activate-the-ui-flows-browser-extension"></a>Ativar a extensão do navegador de fluxos de interface do usuário 

Depois que o instalador de fluxos da interface do usuário for concluído, você será solicitado por seu navegador para ativar a extensão.

- No Microsoft Edge (Chromium), selecione cada ícone de aviso no canto superior direito do navegador e, em seguida, selecione **habilitar extensão**.
-   No Google Chrome, selecione **habilitar extensão** quando solicitado.  


## <a name="install-selenium-ide"></a>Instalar o Selenium IDE

O IDE Selenium é uma ferramenta de software livre que permite que você registre e reproduza interações humanas em sites.

Com os fluxos da interface do usuário, você pode executar scripts do IDE do Selenium de energia automatizar e mantê-los armazenados com segurança (com governança de ti apropriada) em Common Data Service.

Siga estas etapas para instalar o Selenium IDE:

1. [Baixe e instale](https://go.microsoft.com/fwlink/?linkid=2107665) o IDE do Selenium para a próxima versão do Microsoft Edge ou do Google Chrome.

1. No Microsoft Edge (Chromium), selecione **permitir extensões de outras lojas**e, em seguida, selecione **Adicionar ao Chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Instalar o gateway de dados local

Você precisará do gateway para disparar o fluxo da interface do usuário de um [evento, agenda ou fluxo de botão.](../getting-started.md/#types-of-flows)

>[!TIP]
>O gateway não será necessário se você quiser apenas criar, editar e testar seus fluxos de interface do usuário em seu dispositivo.

[Instale o gateway de dados local](https://docs.microsoft.com/data-integration/gateway/service-gateway-install), se necessário.

## <a name="uninstall-ui-flows"></a>Desinstalar fluxos de interface do usuário

1. Abra o menu **iniciar** > **configurações** > **aplicativos**.
1. Pesquise **fluxos de interface do usuário (versão prévia)** e selecione-o.
1. Selecione **desinstalar**.

## <a name="next-steps"></a>Próximas etapas

- Aprenda a [criar fluxos de interface do usuário da área de trabalho](create-desktop.md).
- Aprenda a [criar fluxos de interface do usuário da Web](create-web.md).
- Saiba como executar [fluxos de interface do usuário](run-ui-flow.md).
- Aprenda a [gerenciar fluxos de interface do usuário](manage.md).
- Saiba mais sobre o [Gateway local](../gateway-reference.md/#use-a-gateway)

