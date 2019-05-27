---
ms.openlocfilehash: d45bf5974c24a8258f3f4e51e1e4c89b9c74fba7
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460335"
---
Para este fluxo, você compilará uma lista do **SharePoint** na qual a equipe de Marketing da **Contoso Flooring** armazena suas **postagens do Twitter** e as datas da postagem. A partir daí, você criará um fluxo que postará os tweets de conteúdo automaticamente. 

## <a name="connect-microsoft-flow-services"></a>Conectar os serviços do Microsoft Flow
Neste tópico, você usará os serviços do **SharePoint** e do **Twitter**. Se você estiver usando um serviço novo para você, primeiro será necessário conectar-se ao novo serviço. 

1. No Microsoft Flow, selecione o **ícone de engrenagem** e, depois, **Conexões**,
   
    ![Obter conexão](./media/learning-push-notifications/2-get-connection.png) 
2. Selecione **+ Criar conexão**.
   
    ![Criar conexão](./media/learning-push-notifications/3-create-connection.png) 
3. Role a lista para baixo, localize Twitter e selecione **+**.
   
    ![Clique no sinal de adição](./media/learning-push-notifications/4-click-plus.png)
4. Para autorizar uma conta do Twitter, insira seu nome de usuário, ou email, e a senha e, em seguida, selecione **Autorizar aplicativo**.
   
    ![Criar um ID e senha](./media/learning-push-notifications/5-create-id-pswd.png)
5. Para verificar suas conexões, selecione o **ícone de engrenagem** e **Conexões**.
   
    ![Minhas Conexões](./media/learning-push-notifications/6-my-connections.png)
   
    Você deve ver sua nova conexão do Twitter e qualquer outra conexão criada. 
   
    ![Conectar-se ao Twitter](./media/learning-push-notifications/7-twitter-connection.png)

## <a name="build-a-sharepoint-list"></a>Compilar uma lista do SharePoint
A primeira coisa que você precisa fazer é criar uma nova lista do SharePoint Online para Contoso Flooring. 

1. No SharePoint Online, selecione **Novo** e, em seguida, **Lista**.
   
    ![Criar nova lista](./media/learning-push-notifications/1-new-list.png)
2. Dê à lista o nome **Contoso Tweets**. 
3. Desmarque a caixa de seleção **Mostrar na navegação do site** e selecione **Criar**.
   
    ![Criar lista](./media/learning-push-notifications/2-name-create-list.png)
   
    Quando você seleciona **Criar**, o SharePoint leva você até a nova lista.
4. Por padrão, a lista contém uma única coluna - **Título**. Adicione outra coluna e denomine-a **Conteúdo do Tweet**. As coisas que você dirá em seu tweets aparecerão aqui. 
   
   1. Selecione o sinal de adição e depois **Mais...**
      
       ![Criar lista](./media/learning-push-notifications/3-add-more-column-types.png)
   2. Selecione **Várias linhas de texto** e, em seguida, selecione **OK**.
      
       ![Criar lista](./media/learning-push-notifications/4-add-column.png)
5. Adicione uma coluna para a data e hora do tweet e dê a ela o nome **Data do Tweet**.
   
   1. Assim como você fez com **Conteúdo do Tweet** acima, selecione o sinal de adição e selecione **Mais...**
      
       ![Coluna de data e hora](./media/learning-push-notifications/5-date-time-col.png)
   2. Role para baixo até **Formato de Data e Hora**. Selecione **Data e Hora**, para que ambas sejam incluídas.
      
       ![Data e hora](./media/learning-push-notifications/6-date-time-must-do.png)
   3. Selecione **OK**. Você verá a lista **Contoso Tweets** em seu site do SharePoint e poderá adicionar novos itens à lista.

## <a name="build-the-flow"></a>Criar o fluxo
A lista foi criada, agora você pode criar o fluxo.

### <a name="choose-a-trigger"></a>Escolher um acionador
1. No Microsoft Flow, acesse **Meus Fluxos**, depois, selecione **Criar de um modelo em branco**.
   
    ![Criar de um modelo em branco](./media/learning-push-notifications/8-create-from-blank.png)
2. Selecione **Quando um item é criado**.
   
    ![Adicionar gatilho](./media/learning-push-notifications/9-add-trigger.png)
   
    Queremos que nosso gatilho seja acionado quando uma nova linha é adicionada ao conteúdo do tweet.
3. Selecione seu site do SharePoint, depois, selecione a lista que você configurou anteriormente, **Contoso Tweets**.
   
    ![Novo item criado](./media/learning-push-notifications/11-set-trigger.png)

Ok, isso basta para o gatilho.

### <a name="add-an-action-to-delay-posting"></a>Adicionar uma ação para atrasar a postagem
1. Selecione **+ Nova etapa** e depois selecione **Adicionar uma ação**. 
   
    ![Adicionar etapa e ação](./media/learning-push-notifications/12-add-step-and-action.png)
2. No serviço **Agenda**, selecione **Atrasar até**. 
   
    ![Atrasar até](./media/learning-push-notifications/13-delay-until-schedule.png)  
3. Defina o valor do atraso.
   
   1. Clique ou toque no campo **Carimbo de data/hora**. 
   2. Quando a caixa de conteúdo dinâmica abrir, role para baixo até a parte inferior, e você vê as três colunas da lista do SharePoint: **Título**, **data do Tweet**, e **conteúdo do Tweet**.
   3. Selecione **Data do Tweet**. 
      
       ![Atrasar até o carimbo de data/hora](./media/learning-push-notifications/14-delay-until-timestamp.png)
      
       Agora, quando alguém adicionar algo à sua lista do SharePoint, qualquer ação será atrasada até a data e a hora definidas na coluna **Data do Tweet**.
      
       ![Carimbo de data/hora dinâmico](./media/learning-push-notifications/15-dynamic-timestamp.png)

### <a name="add-an-action-to-post-a-tweet"></a>Adicionar uma ação para postar um Tweet
Agora, você adicionará outra ação para execução do fluxo na data e hora especificadas na coluna **Data do Tweet**.

1. Selecione **+ Nova etapa**, **Adicionar uma ação** e, em seguida, procure por **Twitter**.
   
    ![Adicionar tweet](./media/learning-push-notifications/16-add-tweet.png) 
2. Escolha a ação **Twitter - Postar um tweet**.
   
    ![Postar um tweet](./media/learning-push-notifications/17-post-tweet.png) 
3. Clique ou toque no campo **Texto do Tweet** e, na caixa de conteúdo dinâmico, selecione **Conteúdo do Tweet**. Aqui está a sequência que você criou. 
   
    ![Conteúdo de data do Tweet](./media/learning-push-notifications/18-tweet-date-content.png)
4. Selecione **Criar fluxo...**
   
    ![Criar fluxo](./media/learning-push-notifications/19-tiny-create.png) 
5. Selecione **Concluído**.
   
    ![Clique em concluído](./media/learning-push-notifications/19-click-done.png)
   
    Agora, o fluxo está concluído.
   
    ![O fluxo está concluído](./media/learning-push-notifications/20-flow-is-done.png)
   
    Quando um novo item for criado na lista do SharePoint, o fluxo atrasará a postagem até a data previamente configurada. Quando essa data chegar, o fluxo será publicado no Twitter com o texto da coluna **Conteúdo do Tweet** na lista.

## <a name="next-lesson"></a>Próxima lição
Na próxima lição, você aprenderá como **Executar fluxos em uma agenda** usando um gatilho chamado **Recorrência**.

