---
ms.openlocfilehash: d48ba29d932bc3d9b0d631b4646eb68d89134271
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035149"
---
Neste tópico, você aprenderá a **criar um fluxo de botão** para a Contoso Flooring Company. 

Os fluxos de botão podem ser usados para **enviar email** para uma equipe e **alertá-los de tarefas** a serem executadas. A **Propriedade** dos fluxos **pode ser atribuída a um** trabalhador ou **compartilhada por vários** membros de uma equipe.  

1. Primeiro, vá para o [site do Microsoft Flow](https://ms.flow.microsoft.com) e entre.
2. Após entrar, selecione **Meus fluxos** e **Criar a partir do zero**.
   
    ![Criar de um modelo em branco](./media/learning-create-button-flow/2-create-from-blank.png)
   
    A primeira coisa que você precisará é de um gatilho. O fluxo de botão é uma boa opção. 
3. Se ele não existir em sua lista, selecione **Pesquisar centenas de conectores e gatilhos** na parte inferior da página e digite **botão**, e ele será exibido para você. 
4. Selecione **Botão de fluxo para dispositivos móveis**.
   
    ![Botão de pesquisa](./media/learning-create-button-flow/3-button-flow.png) 
5. Selecione **Botão de fluxo para dispositivos móveis - Disparar manualmente um fluxo**.
   
    ![Selecione o gatilho manual](./media/learning-create-button-flow/4-press-it.png)
6. Na tela de entrada, selecione **Adicionar texto de entrada**,
   
    ![Adicionar entrada](./media/learning-create-button-flow/5-add-input.png)
7. Digite **Contoso Flooring** na primeira caixa de texto e **Email de entrega do depósito** na segunda caixa de texto.
   
    ![Adicionar entrada](./media/learning-create-button-flow/6-text-for-flow.png)
8. Selecione **Nova etapa**. 
   
    ![Texto de entrada](./media/learning-create-button-flow/7-input-description.png)
9. Selecione **Adicionar uma ação**. 
   
    ![Adicionar ação](./media/learning-create-button-flow/8-add-an-action.png)
10. Selecione o conector do **Outlook do Office 365**. Se ele não estiver lá, pesquise por **outlook**.
    
     ![Pesquisar por Outlook](./media/learning-create-button-flow/9-search-outlook.png)
11. Selecione **Outlook do Office 365 - Enviar um email**.
    
     ![Enviar email](./media/learning-create-button-flow/10-send-email.png)
    
     Quando o botão for pressionado, um email será enviado para toda a equipe Contoso Warehouse, independentemente de onde eles estejam, informando que a entrega foi recebida.
12. Expanda os campos e personalize o email para funcionar com Flooring Contoso.
    
    1. No campo **Para**, digite um endereço de email válido em sua organização.
    2. No campo **Assunto**, digite **Entrega Recebida**. 
    3. À direita, observe uma caixa **Conteúdo dinâmico** a ser exibida. Para mostrar, na linha de assunto, a data e hora exatas em que o botão foi pressionado, selecione **Data** e **Carimbo de data/hora**. 
       
        ![Data/hora do email](./media/learning-create-button-flow/11-email-date-time.png)
13. Agora, insira um simples **Corpo** para o email informando algo como **Equipe do depósito, venha para o compartimento de descarregamento porque a entrega foi recebida hoje**.
14. Selecione **Criar fluxo** para salvar o fluxo.
    
     ![Criar fluxo](./media/learning-create-button-flow/12-create-flow.png)

## <a name="create-a-team-flow"></a>Criar um fluxo de equipe
Você pode usar esse fluxo de botão como um exemplo de como criar um fluxo de equipe. E se o criador desse fluxo estiver ausente por estar doente? E se essa pessoa sair da empresa? Você deve certificar-se de que este fluxo continua em execução. Para fazer isso, adicione os coproprietários.

1. Selecione o **ícone de equipe** em seu fluxo para adicionar um coproprietário.
   
    ![Criar fluxo de equipe](./media/learning-create-button-flow/13-create-team-flow.png) 
2. Introduza nomes, endereços de email ou grupos de usuários para adicionar coproprietários.
   
    ![Adicionar coproprietários](./media/learning-create-button-flow/14-add-co-owners.png)
3. Para remover os coproprietários, selecione a Lixeira à direita do nome.
   
    ![Remover coproprietários](./media/learning-create-button-flow/15-remove-co-owners.png)
4. Selecione **Remover esse proprietário** para concluir a remoção.
   
    ![Remover coproprietários](./media/learning-create-button-flow/16-agree-to-remove.png)

## <a name="summary"></a>Resumo
Nesta lição, você viu como **criar um fluxo de botão**. 

Em poucos minutos, o fluxo forneceu a um funcionário do depósito a capacidade de **alertar a equipe** sobre a **chegada de uma entrega**, de modo que eles não tenham que ficar por perto esperando, desperdiçando um tempo valioso que eles poderiam gastar em outras tarefas. 

Em seguida, o funcionário compartilhou esse botão com a equipe, para que os colegas pudessem acionar o mesmo fluxo, caso ele não estivesse por perto.

## <a name="next-lesson"></a>Próxima lição
Confira a próxima lição para conferir como criar um fluxo que usa **notificações por push**.

