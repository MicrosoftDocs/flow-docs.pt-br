---
title: Aprenda a criar fluxos de interface do usuário da área de trabalho | Microsoft Docs
description: Aprenda a criar fluxos de interface do usuário de área de trabalho para aplicativos do Windows.
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
ms.openlocfilehash: e03b23387f5c3837b9b3f7e9ce023f8c31ce79a3
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589792"
---
# <a name="create-and-test-desktop-ui-flows"></a>Criar e testar fluxos de interface do usuário da área de trabalho

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]


Crie fluxos de interface do usuário da área de trabalho para automatizar aplicativos do Windows desktop. 

Consulte os [problemas conhecidos](create-desktop.md#known-issues-and-solutions) mais adiante neste tópico para saber mais sobre os problemas que você pode encontrar, soluções alternativas para esses problemas e cenários que não têm suporte nesta versão de visualização.


> [!TIP]
> Você pode automatizar outros aplicativos da área de trabalho do Windows seguindo um padrão semelhante.

## <a name="create-a-desktop-ui-flow"></a>Criar um fluxo de interface do usuário de área de trabalho

Nas etapas a seguir, demonstraremos como automatizar o aplicativo de calculadora para somar dois números e, em seguida, armazenar o resultado para uso posterior. 

1. Verifique se o [dispositivo está pronto](setup.md) para criar fluxos de interface do usuário. <!--Todo: link to the prereqs section-->

1. Use a [versão Chromium do Microsoft Edge ou do](https://www.microsoftedgeinsider.com) Google Chrome para abrir a [automatização de energia](https://flow.microsoft.com)e entre com uma conta de email corporativa ou de estudante.

1. Selecione **meus fluxos** > **fluxos de interface do usuário (visualização)**  > **novos**.

   ![Criar novo fluxo de interface do usuário](../media/create-windows-ui-flow/create-new.png "Criar novo fluxo de interface do usuário")

1. Escolha **aplicativo da área de trabalho** e, em seguida, selecione **Avançar**.

   ![Selecionar área de trabalho](../media/create-windows-ui-flow/select-desktop.png "Selecionar área de trabalho") 

1. Insira um nome para o fluxo da interface do usuário no campo **nome do fluxo** e, em seguida, selecione **Avançar**.

   ![Selecionar área de trabalho](../media/create-windows-ui-flow/give-a-name.png "Selecionar área de trabalho") 

1. Selecione **Avançar** na parte inferior para ignorar a tela de **entradas de configuração** opcional, já que não estamos usando entradas neste guia.

1. Selecione o cartão de **aplicativo de registro** para expandi-lo.

   ![Selecionar o aplicativo de registro](../media/create-windows-ui-flow/select-record-app.png "Selecionar o aplicativo de registro")

1. Selecione **Iniciar gravador**.

   ![Selecione Iniciar gravador](../media/create-windows-ui-flow/select-launch-recorder.png "Selecione Iniciar gravador")

   O controle de gravador é exibido na parte superior da tela.

   ![O gravador-controle](../media/create-windows-ui-flow/recorder-control.png "O gravador-controle")

1. Inicie o aplicativo de calculadora.

     >[!TIP]
     >À medida que o mouse focaliza os controles no aplicativo, você observará que um contorno azul realça cada controle. Sempre aguarde o realce azul antes de selecionar um controle.
     >
     >Se o realce azul não for exibido em volta do elemento, talvez ele não seja gravado corretamente.

1. Selecione **registro** no controle do gravador.
1. Selecione o primeiro número, selecione **+** , selecione o segundo número e, em seguida, selecione **=** .

    ![O aplicativo de calculadora](../media/create-windows-ui-flow/app-to-record.png "O aplicativo de calculadora")

1. Selecione **concluído** no controle de gravador depois de concluir as ações que deseja registrar.

1. Feche o aplicativo que você registrou.

1. Selecione o cartão que começa com "executar script de <app name>" para exibir capturas de tela das etapas gravadas.

     >[!TIP]
     >Selecione **...**  > **excluir** para remover as etapas adicionais que talvez você queira remover.

    ![Mostrar etapas gravadas](../media/create-windows-ui-flow/show-recorded-steps.png "Mostrar etapas gravadas")

1. Selecione **Avançar**. 

1. Selecione **Avançar** para ignorar a etapa opcional **Configurar saídas** , uma vez que não estamos usando saídas neste guia.

## <a name="test-your-ui-flow"></a>Testar o fluxo da interface do usuário

É sempre uma ótima ideia testar o fluxo da interface do usuário. Para fazer isso, selecione o botão **testar agora** e, em seguida, Assista à execução do fluxo da interface do usuário.
    
 >[!IMPORTANT]
 >Para obter melhores resultados, não interaja com seu dispositivo durante a reprodução.

1. Selecione **salvar e sair** para salvar o fluxo e sair do recurso de fluxos da interface do usuário.


## <a name="known-issues-and-solutions"></a>Problemas e soluções conhecidos

- Abra e maximize os aplicativos *que você deseja registrar antes de* começar a gravar.

- Talvez você queira adicionar uma ação [ **fechar** ](edit-desktop.md#add-a-manual-action) no final do fluxo da interface do usuário porque os fluxos da interface do usuário iniciam uma nova instância dos aplicativos com cada teste ou execução.

- Selecione **...**  > **excluir** no cartão de ações gravadas para remover as ações desnecessárias/duplicadas. Ações duplicadas podem ser criadas dependendo do tipo e da velocidade de gravação. 

- Os cliques à direita podem não ser reproduzidos corretamente. Nesse caso, durante a gravação, clique em esquerda para concentrar os fluxos da interface do usuário no elemento de interface de destino e clique com o botão direito do mouse.

- Se a interface do usuário não flui mais registros ou reproduza aplicativos do Windows após a instalação de uma nova versão, desinstale a versão anterior e instale uma nova versão.


### <a name="unsupported-application-types"></a>Tipos de aplicativos sem suporte

-   Interações no Windows (explorador de arquivos, menu de inicialização, barra de tarefas, etc.).

-   Navegadores da Web (Chrome, IE, Edge, Edge Chromium, Firefox, Mozilla, etc.).
    Em vez disso, consulte [criar um fluxo de interface do usuário da Web](edit-web.md) para automatizar sites.

-   Aplicativos Java.

-   Clique em aplicativos.

-   Aplicativos com uma exibição da Web, como aplicativos do tipo de aplicativo.

-   Microsoft Office 2016 e anteriores. 

-   Microsoft Office Online.

### <a name="unsupported-configurations"></a>Configurações sem suporte

-   Várias telas.

-   Gravação por meio de um cliente de máquina virtual (Área de Trabalho Remota, Citrix, etc.), com o aplicativo de fluxos de interface do usuário em execução no dispositivo host ou na máquina virtual. Não há suporte para nenhum.

-   Várias instâncias de um aplicativo em que os títulos da janela principal são idênticos.

-   Janelas de aplicativos com títulos idênticos, por exemplo, o Microsoft Outlook com várias janelas de mensagens **sem título (HTML)** novas e ativas ao mesmo tempo.

-   A gravação simultânea de sessões em um determinado dispositivo.

-   Sessões de reprodução simultâneas em um determinado dispositivo. No caso de execuções de fluxo de interface do usuário simultâneas, a primeira tem precedência e as subsequentes falham até que a primeira seja concluída.

-   Reprodução em um dispositivo com um layout de teclado diferente do dispositivo no qual ele foi registrado.

-   A gravação em uma sessão do dispositivo ou do Windows enquanto o navegador com Microsoft Flow está em um dispositivo ou sessão do Windows diferente.

### <a name="unsupported-action-types-and-behaviors"></a>Comportamentos e tipos de ação sem suporte

As seguintes ações não serão gravadas:

-   Clique duas vezes em.

-   Movimentação do mouse.

-   Mouse em foco.

-   Clique e arraste.

-   Entrada por toque ou caneta.

-   Abra o aplicativo antes da gravação.

-   Aplicativo fechado antes do início da reprodução.

## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Comportamentos não confiáveis e soluções alternativas para Microsoft Office (Desktop)
- Fixe a faixa de bits antes de começar a reprodução para evitar problemas que possam ocorrer se a faixa de bits estiver definida para ocultar automaticamente durante a reprodução.
- Não selecione itens clicando e arrastando. Por exemplo, não use Shift-clique para selecionar células no Microsoft Excel e não selecione texto no Microsoft Word ou no Microsoft PowerPoint arrastando o mouse.
- Alguns elementos podem não funcionar corretamente em fluxos de interface do usuário (versão prévia) para aplicativos do Microsoft Word e da área de trabalho do Microsoft PowerPoint. Por exemplo, as opções no menu arquivo, como a partir de em branco, ou ao clicar com o botão direito do mouse em controles como adicionar um parágrafo no Microsoft Word ou alterar o layout dos slides no Microsoft PowerPoint, podem não funcionar.

## <a name="next-steps"></a>Próximas etapas

- Saiba como [disparar o fluxo de interface do usuário](run-ui-flow.md) que você acabou de criar.

- Se você quiser fazer mais com os fluxos da interface do usuário, você também poderá experimentar fluxos de interface do usuário com parâmetros [de entrada e saída](inputs-outputs-web.md) .

