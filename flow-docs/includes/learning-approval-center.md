---
ms.openlocfilehash: 431bb579e19f89132f5ea0ca772a89ea17988de2
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463426"
---
Em um tópico anterior, você viu como capacitar um feed do Twitter com uma lista do SharePoint de um modo simples. Neste tópico, você aprenderá a criar um cenário mais amigável à sua empresa usando aprovações. Dessa forma, qualquer pessoa com acesso à lista do SharePoint poderá colabora com tweets, e a equipe de mídia social poderá aprovar ou rejeitar os tweets. A equipe mantém o controle da conta e do conteúdo distribuído aos clientes. 

## <a name="create-an-approval-request-flow"></a>Criar um fluxo de pedido de aprovação
1. Na home page do **Microsoft Flow**, selecione **Aprovações**, selecione **Criar fluxo de aprovação** e, em seguida, role para baixo e selecione o modelo **Postar itens de lista para o Twitter após a aprovação**. 
   
    ![Selecionar modelo](./media/learning-approval-center/create-approval.png)
2. Verifique suas credenciais de conta do **SharePoint**, **Aprovações** e **Twitter** e selecione **Continuar**. 
   
    ![Verificar as credenciais](./media/learning-approval-center/verify-credentials.png)

Por padrão, esse modelo começa um processo de aprovação sempre que um novo item é criado em uma lista específica e, se o item for aprovado, ele envia um tweet ao Twitter. Neste tópico, você modificará esse processo adicionando etapas que atualizam a lista do SharePoint com a resposta da aprovação, indicam se ela foi aprovada ou não e adicionam quaisquer comentários feitos pelo aprovador para o tweet proposto. 

1. Na lista do SharePoint **ContosoTweets** criada anteriormente, adicione duas colunas novas:
   
   1. Selecione o sinal de adição "**+**" e selecione **Sim/Não**
   2. Insira **ApprovalStatus** e selecione **Criar**
   3. Selecione o sinal de adição "**+**" e selecione **Linha única de texto**
   4. Insira **ApproverComments** e selecione **Salvar**
      
      ![Adicionar colunas](./media/learning-approval-center/new-columns.png)
2. De volta ao **Microsoft Flow**, na ação **Quando um novo item é criado**, insira os seguintes valores:
   
   * **Endereço do Site**: URL de sua equipe do SharePoint
   * **Lista o nome**: ContosoTweets
     
     ![Site e lista](./media/learning-approval-center/site-address.png)
3. Na ação **Iniciar uma aprovação**, selecione **Editar** para exibir todos os campos. 
   
    ![Editar campos](./media/learning-approval-center/edit-all-fields.png)
4. Em **Título**, insira **Novo tweet para** e selecione **Título** na lista de conteúdo dinâmico. 
   
    ![Título](./media/learning-approval-center/tweet-title.png)
5. Em **Atribuído a**, insira e selecione seu nome ou um nome de usuário de teste. 
   
    ![Atribuído a](./media/learning-approval-center/tweet-assigned-to.png)
6. Em **Detalhes**, remova os itens padrão e adicione **TweetContent**, **TweetDate** e **Criado por DisplayName** da lista de conteúdo dinâmico, conectada pelas palavras **em** e **por**. 
   
    ![Detalhes](./media/learning-approval-center/tweet-details.png)
7. Em **Link do Item**, copie e cole a URL da lista do SharePoint e, na **Descrição do Link do Item**, insira **Lista de Tweets da Contoso**. 
   
    ![Link do item](./media/learning-approval-center/tweet-item-link.png)
8. Na ação **Condição**, passe o mouse sobre a caixa **SE SIM**, selecione o sinal de adição "**+**" e selecione **Adicionar uma ação**. 
   
    ![Adicionar uma ação](./media/learning-approval-center/add-an-action.png)
9. Procure por **atualizar item**, selecione o conector **SharePoint** e selecione a ação **SharePoint – Atualizar item**.
   
    ![Atualizar item do SharePoint](./media/learning-approval-center/update-item.png)
10. Em **Endereço do Site** e **Nome da Lista**, insira a URL do site e a lista **ContosoTweets** novamente e, em **ID**, insira **ID**  na lista de conteúdo dinâmica. 
    
     ![Site, lista e ID](./media/learning-approval-center/address-list-id.png)
11. Selecione o campo **Título** e, na lista de conteúdo dinâmico, procure **Título**. Adicione o item **Título** na ação **Quando um novo item é criado**. 
    
     ![Novo título](./media/learning-approval-center/add-title.png)
12. Selecione **ApprovalStatus** e defina o valor como **Sim**, depois, selecione **ApproverComments** e defina o valor como **Comentários** na lista de conteúdo dinâmico. 
    
     ![Status e comentários](./media/learning-approval-center/approver-status.png)
13. Perto da parte inferior da caixa **SE NÃO, NÃO FAÇA NADA**, selecione **Adicionar uma ação**.
    
     ![Adicionar uma ação](./media/learning-approval-center/add-a-no-action.png)
14. Usando as mesmas etapas da configuração **SE SIM**, crie uma ação **SharePoint – Atualizar o item** e configure os campos com os mesmos valores, com exceção da configuração  **ApprovalStatus** como **Não**. 
    
     ![Status = não](./media/learning-approval-center/status-no.png)
15. Selecione a ação **Postar um tweet**, selecione **Editar** e defina **Texto do Tweet** como **TweetContent** da lista de conteúdo dinâmico.  Na parte superior da página, selecione **Criar fluxo** para salvar seu trabalho. 
    
     ![Postar e salvar](./media/learning-approval-center/post-tweet.png)

Essa é apenas uma maneira que o Microsoft Flow pode melhorar a produtividade de sua equipe. Sua equipe pode colaborar com ideias, notícias relevantes ou guia do produto, e ainda manter o controle sobre o que é publicado como tweet para os clientes.

Em nosso próximo tópico, veremos o que acontece quando um aprovador recebe um novo pedido para um tweet proposto. 

