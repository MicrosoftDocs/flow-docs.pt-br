---
title: Saiba como automatizar e executar as tarefas repetitivas com os fluxos de botão | Microsoft Docs
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
ms.openlocfilehash: cbcbce51bb950ef9154f356ce44a651f25ce55bd
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64464147"
---
# <a name="introducing-button-flows"></a>Introdução a fluxos de botão
## <a name="what-are-button-flows"></a>O que são fluxos de botão?
Há muitas tarefas repetitivas que todos gostaríamos de poder executar com apenas o toque de um botão. Por exemplo, talvez você precise enviar rapidamente um email à sua equipe para lembrá-los de participar da sincronização diária de equipe ou talvez queira iniciar uma nova compilação do Visual Studio Online de sua base de código após ser notificado de que não há mais check-ins planejados para o dia. Os fluxos de botão permitem realizar essas e muitas outras tarefas simplesmente tocando em um botão no dispositivo móvel.

**Observação** você pode criar fluxos de botão por meio de seu dispositivo móvel ou no portal do Flow.  
  ![Imagem de visão geral](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Por que criar botões?
Crie botões para que você possa facilmente executar tarefas repetitivas em qualquer lugar e a qualquer momento por meio de seu dispositivo móvel. Executar botões economiza tempo e, como as tarefas que eles executam são automatizadas, haverá menos erros do que se você as realizasse manualmente-los.  

## <a name="create-a-button"></a>Criar um botão
### <a name="prerequisites"></a>Pré-requisitos
* Acesso ao Flow. O administrador pode lhe fornecer acesso.
* Uma conta com permissões para usar os conectores para criar o botão. Por exemplo, você precisará de uma conta do Dropbox para criar um botão que acessa o Dropbox.

### <a name="from-the-portal"></a>Por meio do portal
Neste passo a passo, vamos criar um botão que inicia uma compilação do VSO (Visual Studio Online) e envia notificações para que você saiba quando a compilação é iniciada:  

1. Selecione a lista suspensa **Mostrando** e escolha a categoria **Botão**. Isso filtra a lista de modelos para apenas aqueles que podem ser usados em fluxos de botão.  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-1.png)   
2. Selecione o modelo **Disparar uma nova compilação no VSO** na lista de modelos.  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-2.png)  
3. Selecione o botão **Usar este modelo** na página **Disparar uma nova compilação no VSO**.   
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-3.png)  
4. Se não estiver conectado, você será solicitado a fazê-lo nesse ponto:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-4.png)  
5. Depois que tiver entrado no fluxo, você será solicitado a entrar nos conectores usados no modelo que selecionou. Neste exemplo, na etapa 2 acima, selecionamos o modelo **Disparar uma nova compilação no VSO**. Portanto, precisamos entrar no VSO (e em todos os outros conectores com os quais você está trabalhando), caso isso ainda não tenha sido feito:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Selecione o botão **Aceitar** se você concordar em autorizar o Flow a acessar sua conta do VSO.  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-5.png)   
   **Observação** você precisará autorizar cada conector da mesma forma. O designer deverá ter essa aparência quando você estiver pronto para passar para a próxima etapa. Selecione o botão **Continuar** para continuar:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-6.png)   
7. Agora você está pronto para configurar as propriedades para a compilação que deseja iniciar:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-7.png)  
8. Selecione ou insira o **Nome da conta**, **Nome do projeto**, **Id de definição de compilação**, **Ramificação de origem** e, opcionalmente, **Parâmetros**, no cartão **Enfileirar uma nova compilação**:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-8.png)  
9. Em seguida, configure as propriedades de notificação por push no cartão **Enviar uma notificação por push**. Por padrão, essa notificação por push é configurada para enviar um link HTML a uma página da Web que exibe o status da compilação:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-9.png)  
10. Selecione o **criar fluxo** botão para salvar seu fluxo de botão: ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-10.png)  
11. Você verá essa mensagem de êxito em poucos instantes:  
    ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-11.png)  

Parabéns, você criou um fluxo de botão! Agora você pode executar esse fluxo de botão a qualquer momento e em qualquer lugar, por meio da guia **Botões** no aplicativo Flow. Basta pressionar o "botão" e ele será executado! O aplicativo móvel Microsoft Flow está disponível para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>Em seu dispositivo móvel
**Observação**: Embora este passo a passo exiba as telas de um dispositivo Android, as telas e experiência em um dispositivo iOS são semelhantes.

No aplicativo Flow:

1. Selecione a guia **Procurar** e role até a categoria **Botão**.  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Selecione o link **Ver todos**. Isso exibe todos os modelos de botão prontos para usar.     
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Selecione o modelo **Enviar um email para lembrar sua equipe de ingressar em uma reunião**    
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Selecione o link **USAR ESTE MODELO** na parte inferior da página.    
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Você precisará entrar em todos os serviços que este modelo usa:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Selecione o link **Avançar** após entrar em todos os serviços.      
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Selecione o link **Criar**. Aqui você também pode analisar o fluxo e fazer as alterações necessárias para personalizar o email, por exemplo.        
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Após alguns instantes, o fluxo de botão é criado. Selecione **VER MEU FLUXO**:   
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Exibir todos os seus fluxos na guia **Meus fluxos**  
   ![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Parabéns, você criou um fluxo de botão! Agora você pode executar esse fluxo de botão a qualquer momento e em qualquer lugar, por meio da guia **Botões** no aplicativo Flow. Basta pressionar o "botão" e ele será executado! O aplicativo Flow está disponível atualmente em dispositivos móveis Android e iOS.  

![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Disparar um fluxo de botão
Agora que você criou um fluxo de botão, é hora de executá-lo. Como você só pode executar fluxos de botão no aplicativo Flow, verifique se instalou o Flow em seu dispositivo móvel Android ou iOS.  

1. Agora, inicie o aplicativo de fluxo, toque na guia **Botões** localizada na parte inferior da página e toque no *botão* que representa o fluxo de botão que você deseja disparar:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Confira o progresso enquanto o fluxo é executado:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Por fim, a página é atualizada, indicando que o fluxo de botão foi concluído:  
   ![Imagem de visão geral](./media/introduction-to-button-flows/trigger-button-3.png)   

Essas são todas as etapas para executar um fluxo. 

Agora você deve receber a notificação por push, indicando que o email foi enviado.  

## <a name="monitor-your-button-flow-runs"></a>Monitorar as execuções de fluxo de botão
Você pode monitorar fluxos de botão na guia **Atividade** do aplicativo Flow:   
![Imagem de visão geral](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Observação**: Toque em qualquer atividade para analisar os resultados da execução para saber mais sobre a execução.  

![Imagem de visão geral](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Gerenciar fluxos de botão
Você tem controle total de seus fluxos de botão para que possa habilitar/desabilitar, editar ou excluir um botão, a qualquer momento e em qualquer lugar. No aplicativo móvel ou no portal do fluxo, selecione **Meus fluxos** para começar a gerenciar seus fluxos.    

Na guia **Meus fluxos** do aplicativo Flow:

1. Selecione o fluxo que você deseja gerenciar:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Você pode usar qualquer uma dessas opções, com base no que deseja fazer:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Toque em **Excluir fluxo** para excluir um fluxo.  

**Observação** todo o histórico de execução é excluído quando você exclui um fluxo:   
![Imagem de visão geral](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Toque em **Atualizar** após concluir a edição de um fluxo de botão para salvar as alterações:   
   ![Imagem de visão geral](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Toque em **Histórico de execução** para ver os resultados de todas as execuções de um fluxo de botão específico:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Se você desabilitar um fluxo, ele não estará mais disponível na guia **Botões**:    
   ![Imagem de visão geral](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Próximas etapas
* [Compartilhe os fluxos do botão](share-buttons.md)
* Aprenda a usar os [tokens de gatilho de botão](introduction-to-button-trigger-tokens.md) para enviar dados em tempo real quando os fluxos de botão são executados.
* Instale o aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows).

