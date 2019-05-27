---
ms.openlocfilehash: a4c1189e943d5e1f48507bd3e55b5f2d8fe52a8c
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460496"
---
Neste tópico, você verá como executar fluxos previamente agendados usando um gatilho chamado **Recorrência**.  Você criará um fluxo para a equipe de marketing da Contoso que recebe efetua pull de endereços de email do cliente de uma tabela do Excel no OneDrive. Você vai configurar o fluxo de forma que, uma vez por dia, novos endereços de email adicionados à planilha sejam então adicionados a uma lista de clientes do MailChimp. 

## <a name="create-a-scheduled-flow"></a>Criar um fluxo agendado
1. Abra o **Microsoft Flow**, selecione **Meus fluxos** e então selecione **Criar a partir do zero**. 
   
    ![](./media/learning-recurrence/flow-create-blank.png)
2. Selecione **Pesquisar centenas de conectores e gatilhos**.
3. Procure o serviço **Agenda**, selecione-o e, em seguida, selecione o gatilho **Agenda – Recorrência**.
   
    ![](./media/learning-recurrence/flow-recurrence-trigger.png)
4. Defina **Frequência** como **Dia** e **Intervalo** como **1**. Selecione **Nova etapa** e depois selecione **Adicionar uma ação**. 
   
    ![](./media/learning-recurrence/frequency-interval.png)
5. Procure o **Excel**, selecione o serviço do **Excel** e selecione a ação **Excel – Obter Linhas**. 
   
    ![](./media/learning-recurrence/excel-get-rows.png)
   
    **Observação**: Verifique se você selecionou **obter linhas**, e não **obter linha**. 
6. Selecione **Nome de arquivo** e navegue até o local do arquivo. Selecione **Nome da tabela** e selecione a tabela desejada na planilha. 
   
    ![](./media/learning-recurrence/excel-get-file.png)
7. Adicione uma nova ação. 
   
    ![](./media/learning-recurrence/new-step.png)
8. Procure o serviço **MailChimp**, então selecione a ação **MailChimp - Adicionar membro à lista**.
   
    ![](./media/learning-recurrence/select-mailchimp.png)
   
    **Observação:** O MailChimp é um *premium* conector. Dependendo de sua licença do Microsoft Flow, você precisará se inscrever em uma avaliação para usar esse conector.
9. Adicione os campos **Id da lista** e **Status** dos menus suspensos:
   
   * **Id da lista** – selecione sua lista de endereçamento do MailChimp
   * **Status** – selecione **Assinado** 
     
     ![](./media/learning-recurrence/mailchimp-id-status.png)
10. Em **Endereço de Email**, use o recurso de conteúdo dinâmico para adicionar o campo **ContactEmail**. 
    
     ![](./media/learning-recurrence/mailchimp-address.png)
    
     Observe que o fluxo cria automaticamente uma etapa adicional. O Flow detecta que você pretende definir uma ação que exija uma ação adicional. Sempre que o fluxo lê um novo endereço de email, também cria uma nova ação para cada linha. 
    
     ![](./media/learning-recurrence/mailchimp-for-each.png)
11. Use o conteúdo dinâmico para preencher os campos **Nome** e **Sobrenome**:
    
    * **Nome** – FirstName
    * **Sobrenome** – LastName
      
      ![](./media/learning-recurrence/mailchimp-names.png)

Agora esse fluxo será executado uma vez por dia e obterá novas linhas dessa tabela do Excel, obterá o endereço de email e o nome e os usará para preencher a lista de emails da Contoso no MailChimp, economizando seu tempo e seu dinheiro. 

