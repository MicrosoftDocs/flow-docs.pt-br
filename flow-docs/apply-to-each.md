---
title: Use para aplicar em cada ação e percorrer uma matriz de itens. | Microsoft Docs
description: Use o Microsoft Flow para percorrer uma matriz de itens para verificar várias condições e tomar ações com base nessas condições.
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
ms.date: 03/16/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 914fe6d84bb63e1f3e184794d34fbfd58ad30963
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64459884"
---
# <a name="use-the-apply-to-each-action-in-microsoft-flow-to-process-a-list-of-items-periodically"></a>Use para aplicar em cada ação no Microsoft Flow e processar uma lista de itens periodicamente
Vários gatilhos podem iniciar imediatamente um fluxo com base em um evento, como quando um novo email chega na caixa de entrada. Os gatilhos são ótimos, mas, às vezes, você deseja executar um fluxo que consulta uma fonte de dados em uma agenda predefinida, tomando certas ações com base nas propriedades dos itens na fonte de dados. Para fazer isso, o fluxo pode ser iniciado em uma agenda (por exemplo, uma vez por dia) e usar uma ação de loop como **Aplicar em cada** para processar uma lista de itens. Por exemplo, você pode usar **Aplicar em cada** para atualizar os registros em um banco de dados ou uma lista de itens no Microsoft SharePoint.

Neste passo a passo, criaremos um fluxo que é executado a cada 15 minutos e faz o seguinte:

1. obtém as últimas 10 mensagens não lidas em sua caixa de entrada do Outlook do Office 365.
2. verifica cada uma das 10 mensagens para confirmar se qualquer uma tem as palavras **reunir agora** no assunto.
3. verifica se o email é do seu chefe ou foi enviado com alta prioridade.
4. envia uma notificação por push e marca como lido qualquer email com as palavras **reunir agora** no assunto, e se é do seu chefe ou foi enviada com alta prioridade.

Este diagrama mostra os detalhes do fluxo que criaremos neste passo a passo:

![visão geral do fluxo sendo criado](./media/apply-to-each/foreach-flow-visio.png)

## <a name="prerequisites"></a>Pré-requisitos
Aqui estão os requisitos para executar com êxito as etapas neste passo a passo:

* uma conta registrada para usar o [Microsoft Flow](https://flow.microsoft.com).
* uma conta do Outlook do Office 365.
* O aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows).
* conexões com o Outlook do Office 365 e o serviço de notificação por push.

## <a name="create-a-flow"></a>Crie um fluxo
1. Entre no [Microsoft Flow](https://flow.microsoft.com):
2. Selecione a guia **Meus fluxos**, em seguida, crie um fluxo em branco:
   
    ![criar do zero](./media/apply-to-each/foreach-1.png)
3. Insira "agendar" na caixa de pesquisa para procurar todos os serviços e gatilhos relacionados ao agendamento.
4. Selecione o gatilho **Schedule - Recurrence** para indicar que seu fluxo será executado em uma agenda que você fornecerá em seguida:
   
    ![ação de recorrência de agendamento](./media/apply-to-each/foreach-2.png)
5. Defina a agenda para executar a cada 15 minutos:
   
    ![a agenda é executada](./media/apply-to-each/foreach-3.png)
6. Selecione **+ Nova etapa**, **Adicionar uma ação**, em seguida, digite **outlook** na caixa de pesquisa para procurar todas as ações relacionadas ao Microsoft Outlook.
7. Selecione a ação **Outlook do Office 365 - Obter emails**:
   
    ![selecionar a ação para obter emails](./media/apply-to-each/foreach-4.png)
8. Isso abrirá o cartão **Obter emails**. Configure o cartão **Obter emails** para selecionar os 10 principais emails não lidos na pasta da Caixa de entrada. Não inclua os anexos porque eles não serão usados no fluxo:
   
    ![configurar cartão de email](./media/apply-to-each/foreach-5.png)
   
   > [!NOTE]
   > Até agora, você criou um fluxo simples que obtém alguns emails na caixa de entrada. Esses emails serão retornados em uma matriz; a ação **Aplicar em a cada** requer uma matriz, portanto, é exatamente isso o que é necessário.
   > 
   > 

## <a name="add-actions-and-conditions"></a>Adicionar ações e condições
1. Selecione **+ Nova etapa**, **Mais**, então, a ação**Adicionar e aplicar em cada**:
   
    ![selecione e aplicar em cada](./media/apply-to-each/foreach-6.png)
2. Insira o token **Corpo** na caixa **Selecionar uma saída nas etapas anteriores** no cartão **Aplicar em cada**. Isso extrairá o corpo dos emails a serem usados na ação **Aplicar em cada**:
   
    ![adicionar token do corpo](./media/apply-to-each/foreach-7.png)
3. Selecione **Adicionar uma condição**:
   
    ![adicionar condição](./media/apply-to-each/foreach-8.png)
4. Configure o cartão **Condição** para procurar o assunto de cada email com as palavras "reunir agora":
   
   * Insira o token **Assunto** na caixa **Nome do Objeto**.
   * Selecione **contém** na lista **Relação**.
   * Digite **reunir agora** na caixa **Valor**.
     
     ![configurar condição](./media/apply-to-each/foreach-subject-condition.png)
5. Selecione **Mais**, em seguida, selecione **Adicionar uma condição** no desvio **SE SIM, NÃO FAÇA NADA**. Isso abrirá o cartão **Condição 2**. Configure o cartão como assim:
   
   * Insira o token **Importância** na caixa **Nome do Objeto**.
   * Selecione **igual a** na lista **Relação**.
   * Digite **Alta** na caixa **Valor**.
     
     ![adicionar condição](./media/apply-to-each/foreach-importance-condition.png)
6. Selecione **Adicionar uma ação** na seção **SE SIM, NÃO FAÇA NADA**. Isso abrirá o cartão **Escolher uma ação**, onde você definirá o que deve acontecer caso o critério da pesquisa (o email **reunir agora** foi enviado com alta prioridade) seja verdadeiro:
   
    ![adicionar ação](./media/apply-to-each/foreach-9.png)
7. Procure a **notificação**, em seguida, selecione a ação **Notificações - Enviar para mim uma notificação móvel**:
   
    ![pesquisar e selecionar notificação](./media/apply-to-each/foreach-10.png)
8. No cartão **Enviar para mim uma notificação móvel**, forneça os detalhes da notificação por push que será enviada caso o assunto de um email contenha "reunir agora", em seguida, selecione **Adicionar uma ação**:
   
    ![configurar notificação](./media/apply-to-each/foreach-11.png)
9. Digite **lido** como o termo da pesquisa e selecione a ação **Outlook do Office 365 - Marcar como lido**. Isso marcará cada email como lido depois da notificação por push ser enviada:
   
    ![adicionar marca como ação de email lido](./media/apply-to-each/foreach-12.png)
10. Adicione o token **Id da Mensagem** à caixa **Id da Mensagem** do cartão **Marcar como lido**. Talvez seja necessário selecionar **Ver mais** para encontrar o token **Id da Mensagem**. Isso indica a Id da mensagem que será marcada como lida:
    
     ![adicionar id da mensagem](./media/apply-to-each/foreach-13.png)
11. Voltando para o cartão **Condição 2** no desvio **SE NÃO, NÃO FAÇA NADA**:
    
    * Selecione **Adicionar uma ação**, em seguida, digite **obter gerenciador** na caixa de pesquisa.
    * Selecione a ação **Usuários do Office 365 - Obter gerenciador** na lista de resultados da pesquisa.
    * Insira seu endereço de mail *completo* na caixa **Usuário** do cartão **Obter gerenciador**.
      
      ![adicionar e configurar a ação para obter gerenciador](./media/apply-to-each/foreach-get-manager.png)
12. Selecione **Mais**, em seguida, selecione **Adicionar uma condição** no desvio **SE NÃO**. Isso abrirá o cartão **Condição 3**. Configure o cartão para verificar se o endereço de email do remetente do email (token De) é o mesmo endereço de email do seu chefe (token Email):
    
    * Insira o token **De** na caixa **Nome do Objeto**.
    * Selecione **contém** na lista **Relação**.
    * Digite o token **Email** na caixa **Valor**.
      
      ![configurar condição da pesquisa](./media/apply-to-each/foreach-condition3-card.png)
13. Selecione **Adicionar uma ação** na seção **SE SIM, NÃO FAÇA NADA** do cartão **Condição 3**. Isso abrirá o cartão **SE SIM**, onde você definirá o que deve acontecer caso a condição da pesquisa (o email foi enviado de seu chefe) seja verdadeira:
    
     ![configurar condição](./media/apply-to-each/foreah-condition3-add-action.png)
14. Procure a **notificação**, em seguida, selecione a ação **Notificações - Enviar para mim uma notificação móvel**:
    
     ![procurar a ação de notificação](./media/apply-to-each/foreach-10.png)
15. No cartão **Enviar para mim uma notificação móvel 2**, forneça os detalhes da notificação por push que será enviada caso o email seja de seu chefe, então, selecione **Adicionar uma ação**:
    
     ![configurar cartão de notificação](./media/apply-to-each/foreach-boss-notification.png)
16. Adicione a ação **Outlook do Office 365 - Marcar como lido**. Isso marcará cada email como lido depois da notificação por push ser enviada:
    
     ![adicionar marca como ação de email lido](./media/apply-to-each/foreach-12.png)
17. Adicione o token **Id da Mensagem** ao cartão **Marcar como lido 2**. Talvez seja necessário selecionar **Ver mais** para encontrar o token **Id da Mensagem**. Isso indica a Id da mensagem que será marcada como lida:
    
     ![configurar marca como ação de email lido](./media/apply-to-each/foreach-mark-as-read2.png)
18. Nomeie seu fluxo, depois, crie-o:
    
     ![nomear seu fluxo e salvá-lo](./media/apply-to-each/foreach-14.png)

Se você acompanhou, seu fluxo deverá ser semelhante a este diagrama:

![visão geral do fluxo criado](./media/apply-to-each/foreach-flow-finished.png)

## <a name="run-the-flow"></a>Executar o fluxo
1. Envie para si mesmo um email de alta prioridade que inclua **reunir agora** no assunto (ou faça com que alguém em sua organização envie tal email).
2. Confirme se o email está em sua caixa de entrada e aparece como não lido.
3. Entre no Microsoft Flow, selecione **Meus fluxos**, em seguida, selecione **Executar agora**:
   
    ![executar agora](./media/apply-to-each/foreach-run-1.png)
4. Selecione **Executar fluxo** para confirmar que você realmente deseja executar o fluxo:
   
    ![confirmar execução](./media/apply-to-each/foreach-run-2.png)
5. Após alguns momentos, você deverá ver os resultados da execução bem-sucedida:
   
    ![resultados da execução](./media/apply-to-each/foreach-run-3.png)

## <a name="view-results-of-the-run"></a>Exibir resultados da execução
Agora que você executou o fluxo com êxito, deverá receber a notificação por push em seu dispositivo móvel.

1. Abra o aplicativo Microsoft Flow em seu dispositivo móvel e selecione a guia **Atividade**. Você verá a notificação por push sobre a reunião:
   
    ![selecione a guia atividade](./media/apply-to-each/foreach-notification-1.png)
2. Para ver todo o conteúdo da notificação, você terá que selecioná-la. Você verá a notificação completa, semelhante a isto:
   
    ![detalhes da notificação](./media/apply-to-each/foreach-notification-2.png)
   
   > [!NOTE]
   > Se você não receber a notificação por push, confirme se o dispositivo móvel tem uma conexão de dados ativa.
   > 
   > 

