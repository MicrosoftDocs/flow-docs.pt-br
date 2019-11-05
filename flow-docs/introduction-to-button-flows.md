---
title: Saiba como automatizar e executar tarefas repetitivas com fluxos de botão | Microsoft Docs
description: Introdução aos fluxos de botão.
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
ms.date: 01/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 403c3d7cc116555ab26d5e4168587de5e5a6720f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547532"
---
# <a name="introducing-button-flows"></a>Introdução aos fluxos de botão
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-flows"></a>O que são fluxos de botão?
Há muitas tarefas repetitivas que todos nós desejamos que possamos executar com apenas um toque de um botão. Por exemplo, talvez seja necessário enviar rapidamente por email à sua equipe para lembrá-los de participar da sincronização diária da equipe, ou talvez você queira iniciar uma nova compilação do Visual Studio online da sua base de código depois de ter sido notificado de que não há mais check-ins planejados para o dia. Os fluxos de botão permitem que você realize essas e muitas outras tarefas simplesmente tocando em um botão em seu dispositivo móvel.

**Observação** Você pode criar fluxos de botão a partir do seu dispositivo móvel ou do portal do Flow.  
  ](./media/introduction-to-button-flows/buttons-montage.png) de imagem de visão geral ![  

## <a name="why-create-buttons"></a>Por que criar botões?
Crie botões para que você possa executar facilmente tarefas repetitivas de qualquer lugar, a qualquer momento por meio de seu dispositivo móvel. A execução de botões economiza tempo e, como as tarefas que eles executam são automatizadas, haverá menos erros do que se você os fez manualmente.  

## <a name="create-a-button"></a>Criar um botão
### <a name="prerequisites"></a>Pré-requisitos
* Acesso ao Flow. O administrador pode fornecer acesso.
* Uma conta com permissões para usar os conectores para criar seu botão. Por exemplo, você precisará de uma conta do Dropbox para criar um botão que acesse o dropbox.

### <a name="from-the-portal"></a>No portal
Neste passo a passo, vamos criar um botão que inicia uma compilação do Visual Studio online (VSO) e envia notificações para que você saiba quando o Build começa:  

1. Selecione a lista suspensa **mostrando** e escolha a categoria do **botão** . Isso filtra a lista de modelos somente àqueles que podem ser usados em fluxos de botão.  
   ](./media/introduction-to-button-flows/create-button-1.png) de imagem de visão geral ![   
2. Selecione **disparar um novo Build no** modelo do VSO na lista de modelos.  
   ](./media/introduction-to-button-flows/create-button-2.png) de imagem de visão geral ![  
3. Selecione o botão **usar este modelo** na página **disparar um novo Build no VSO** .   
   ](./media/introduction-to-button-flows/create-button-3.png) de imagem de visão geral ![  
4. Se você não estiver conectado, será solicitado a fazê-lo neste ponto:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-4.png)  
5. Depois de entrar no Flow, você será solicitado a entrar nos conectores usados no modelo selecionado. Neste exemplo, na etapa 2 acima, selecionamos o **gatilho um novo Build no modelo do VSO** , portanto, precisamos entrar no VSO (e em quaisquer outros conectores com os quais você está trabalhando), se você ainda não tiver entrado:  
   ](./media/introduction-to-button-flows/create-button-pre-req-1.png) de imagem de visão geral ![    
6. Selecione o botão **aceitar** se você concordar em autorizar o fluxo a acessar sua conta do VSO.  
   ](./media/introduction-to-button-flows/create-button-5.png)  de imagem de visão geral ![  
   **Observação** Você precisará autorizar cada conector de forma semelhante. O designer deve ser semelhante a este quando você estiver pronto para passar para a próxima etapa. Selecione o botão **continuar** para mover:  
   ](./media/introduction-to-button-flows/create-button-6.png) de imagem de visão geral ![   
7. Agora você está pronto para configurar as propriedades para a compilação que deseja iniciar:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-7.png)  
8. Selecione ou insira o **nome da conta**, o **nome do projeto**, a ID de **definição de compilação**, a **ramificação de origem** e, opcionalmente, os **parâmetros**, no novo cartão de **compilação da fila** :    
   ](./media/introduction-to-button-flows/create-button-8.png) de imagem de visão geral ![  
9. Em seguida, configure as propriedades da notificação por push no cartão **Enviar uma notificação por push** . Por padrão, essa notificação por push é configurada para enviar um link HTML para uma página da Web que exibe o status da compilação:  
   ](./media/introduction-to-button-flows/create-button-9.png) de imagem de visão geral ![  
10. Selecione o botão **criar fluxo** para salvar o fluxo de botão: ![imagem de visão geral](./media/introduction-to-button-flows/create-button-10.png)  
11. Você verá essa mensagem de êxito em alguns instantes:  
    ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-11.png)  

Parabéns, você criou um fluxo de botão! Agora você pode executar esse fluxo de botão a qualquer momento, em qualquer lugar, na guia **botões** do aplicativo de fluxo. Basta pressionar o "botão" e ele será executado! O aplicativo móvel Microsoft Flow está disponível para [Android](https://aka.ms/flowmobiledocsandroid), [Ios](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Do seu dispositivo móvel
**Observação**: embora esse passo a passo exiba telas de um dispositivo Android, as telas e a experiência em um dispositivo IOS são semelhantes.

No aplicativo de fluxo:

1. Selecione a guia **procurar** e role até a categoria do **botão** .  
   ](./media/introduction-to-button-flows/create-button-from-mobile-1.png) de imagem de visão geral ![  
2. Selecione o link **ver tudo** . Isso exibe todos os modelos de botão prontos para uso.     
   ](./media/introduction-to-button-flows/create-button-from-mobile-2.png) de imagem de visão geral ![  
3. Selecione **enviar um email para lembrar sua equipe para ingressar em um** modelo de reunião    
   ](./media/introduction-to-button-flows/create-button-from-mobile-3.png) de imagem de visão geral ![  
4. Selecione o link **usar este modelo** , na parte inferior da página.    
   ](./media/introduction-to-button-flows/create-button-from-mobile-4.png) de imagem de visão geral ![  
5. Você precisará entrar em todos os serviços que este modelo usa:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Selecione o link a **seguir** depois de entrar em todos os serviços.      
   ](./media/introduction-to-button-flows/create-button-from-mobile-6.png) de imagem de visão geral ![  
7. Selecione o link **criar** . Aqui você também pode examinar o fluxo e fazer as alterações necessárias para personalizar o email, por exemplo.        
   ](./media/introduction-to-button-flows/create-button-from-mobile-7.png) de imagem de visão geral ![  
8. Após alguns instantes, o fluxo do botão é criado. Selecione **ver meu fluxo**:   
   ](./media/introduction-to-button-flows/create-button-from-mobile-8.png) de imagem de visão geral ![  
9. Exibir todos os seus fluxos na guia **meus fluxos**  
   ](./media/introduction-to-button-flows/create-button-from-mobile-9.png) de imagem de visão geral ![  

Parabéns, você criou um fluxo de botão! Agora você pode executar esse fluxo de botão a qualquer momento, em qualquer lugar, na guia **botões** do aplicativo de fluxo. Basta pressionar o "botão" e ele será executado! O aplicativo de fluxo está disponível atualmente em dispositivos móveis Android e iOS.  

![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Disparar um fluxo de botão
Agora que você criou um fluxo de botão, é hora de executá-lo. Como você só pode executar fluxos de botão do aplicativo de fluxo, certifique-se de que você instalou o Flow em seu dispositivo móvel Android ou iOS.  

1. Agora, inicie o aplicativo de fluxo, toque na guia **botões** que está localizada na parte inferior da página e toque no *botão* que representa o fluxo de botão que você deseja disparar:  
   ](./media/introduction-to-button-flows/trigger-button-1.png) de imagem de visão geral ![   
2. Consulte o progresso enquanto o fluxo é executado:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Por fim, a página é atualizada, indicando que o fluxo de botão foi concluído:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/trigger-button-3.png)   

Isso é tudo o que é para executar um fluxo. 

Agora você deve receber a notificação por push, indicando que o email foi enviado.  

## <a name="monitor-your-button-flow-runs"></a>Monitorar as execuções de fluxo de botão
Você pode monitorar fluxos de botão da guia **atividade** do aplicativo de fluxo:   
](./media/introduction-to-button-flows/create-button-from-mobile-13.png) de imagem de visão geral ![  

**Observação**: toque em qualquer atividade para analisar os resultados da execução para saber mais sobre a execução.  

![Imagem de visão geral](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Gerenciar fluxos de botão
Você tem controle total de seus fluxos de botão para que você possa habilitar/desabilitar, editar ou excluir um botão a qualquer momento e em qualquer lugar. No aplicativo móvel ou no portal do Flow, selecione **meus fluxos** para começar a gerenciar seus fluxos.    

Na guia **meus fluxos** do aplicativo de fluxo:

1. Selecione o fluxo que você deseja gerenciar:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Você pode tocar em qualquer uma dessas opções, com base no que você gostaria de realizar:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Toque em **excluir fluxo** para excluir um fluxo.  

**Observação** Todo o histórico de execução é excluído quando você exclui um fluxo:   
](./media/introduction-to-button-flows/manage-flow-2.png) de imagem de visão geral ![   

1. Toque em **Atualizar** depois de terminar de editar um fluxo de botão, para salvar suas alterações:   
   ](./media/introduction-to-button-flows/manage-flow-3.png) de imagem de visão geral ![   
2. Toque em **histórico de execução** para ver os resultados de todas as execuções de um fluxo de botão específico:    
   ](./media/introduction-to-button-flows/manage-flow-4.png) de imagem de visão geral ![  
3. Se você desabilitar um fluxo, ele não estará mais disponível na guia **botões** :    
   ](./media/introduction-to-button-flows/manage-flow-5.png) de imagem de visão geral ![  

## <a name="next-steps"></a>Próximas etapas
* [Compartilhar fluxos de botão](share-buttons.md).
* Aprenda a usar [tokens de gatilho de botão](introduction-to-button-trigger-tokens.md) para enviar dados em tempo real quando os fluxos de botão são executados.
* Instale o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [Ios](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).

