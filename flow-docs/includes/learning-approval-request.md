---
ms.openlocfilehash: bb5f08b2606b889a19de0167ef2825cd3428d069
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463395"
---
Em um tópico anterior, você viu como criar um processo de aprovação em torno de tweets armazenados em uma lista do SharePoint.  Neste tópico, você verá a aparência da experiência de quando um aprovador recebe uma nova solicitação de aprovação. 

## <a name="create-and-process-a-request"></a>Criar e processar uma solicitação
Primeiro, precisamos adicionar um item à lista do SharePoint e, em seguida, podemos processar uma solicitação de aprovação para aquele item.

1. Abra a lista do SharePoint **ContosoTweets**, configurada em um tópico anterior.  Selecione **Novo** para criar um novo tweet. 
   
    ![Lista do SharePoint](./media/learning-approval-request/sharepoint-list-home.png)
2. Adicione os seguintes valores aos campos e selecione **Salvar**.
   
   * **Título** – Promoções
   * **TweetContent** – confira a nova linha da Contoso Flooring #ohsocontoso
   * **TweetDate** – Data de hoje
     
     ![Novo item do SharePoint](./media/learning-approval-request/sharepoint-new-tweet.png)
3. Em **Microsoft Flow**, selecione **Meus Fluxos**. 
4. Selecione o fluxo **Postar itens de lista no Twitter após a aprovação** configurado no tópico anterior, então selecione o fluxo em execução em **HISTÓRICO DE EXECUÇÃO**.
   
    ![Histórico de execuções](./media/learning-approval-request/run-history.png)
5. Selecione o gatilho **Quando um novo item é criado**. Verifique se as informações do item de lista que você acabou de criar são exibidas.
   
    ![Gatilho de fluxo](./media/learning-approval-request/approval-flow.png)
6. No **Outlook**, abra o email de aprovação automatizado na caixa de entrada e então selecione **Aprovar**. 
   
    ![Solicitação do Outlook](./media/learning-approval-request/outlook-mail.png)
7. No **Centro de Aprovação**, exiba os detalhes da solicitação, adicione um comentário e selecione **Confirmar**. 
   
    ![Centro de aprovação](./media/learning-approval-request/approval-center.png)
8. No **SharePoint**, atualize a lista **ContosoTweets** e verifique se **ApprovalStatus** é **Sim** e se o comentário que você inseriu é exibido. 
   
    ![Lista de atualização do SharePoint](./media/learning-approval-request/sharepoint-list-approved.png)

Neste tópico, você viu a experiência do ponto de vista do aprovador - desde o recebimento de um email de solicitação de aprovação até o processamento da solicitação no Centro de Aprovação.

