---
title: Criar um fluxo com o Dynamics 365 (online) | Microsoft Docs
description: Criar fluxos de trabalho úteis usando uma conexão do Dynamics 365 e Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: Mattp123
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/06/2017
ms.author: matp
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a138cef3761b188998766a60ceb84619ae5f0a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546907"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Criar um fluxo usando o Dynamics 365 (online)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Usando um conector do Dynamics 365, você pode criar fluxos que iniciam quando um evento ocorre no Dynamics 365 ou em algum outro serviço, que executa uma ação no Dynamics 365 ou em algum outro serviço. 

No Microsoft Flow, você pode configurar fluxos de trabalho automatizados entre seus aplicativos e serviços favoritos para sincronizar arquivos, obter notificações, coletar dados e muito mais. Para obter mais informações, consulte Introdução [ao Microsoft Flow](getting-started.md).

> [!IMPORTANT] 
> Para invocar um gatilho de fluxo, a entidade de Common Data Service usada com o fluxo deve ter **controle de alterações** habilitado. Mais informações: [habilitar o controle de alterações para controlar a sincronização de dados](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Criar um fluxo de um modelo
Você pode criar um fluxo usando um dos vários modelos disponíveis, como estes exemplos:

* Quando um objeto é criado no Dynamics 365, crie um item de lista no SharePoint.
* Criar registros de Lead do Dynamics 365 de uma tabela do Excel.
* Copie contas do Dynamics 365 para clientes no Dynamics 365 para operações.

Para criar um fluxo de um modelo, siga estas etapas.

1. Entre no site do [Microsoft Flow](https://flow.microsoft.com/).
2. Clique ou toque em **Serviços**e, em seguida, clique ou toque em **Dynamics 365**.
3. Vários modelos estão disponíveis. Para começar, selecione o modelo desejado.

## <a name="create-a-task-from-a-lead"></a>Criar uma tarefa de um cliente potencial
Se um modelo não estiver disponível para o que você precisa, crie um fluxo do zero. Este tutorial mostra como criar uma tarefa no Dynamics 365 sempre que um cliente potencial é criado no Dynamics 365.

1. Entre no site do [Microsoft Flow](https://flow.microsoft.com/).
2. Clique ou toque em **meus fluxos**e, em seguida, clique ou toque em **criar em branco**.
3. Na lista de gatilhos de fluxo, clique ou toque em **Dynamics 365-quando um registro é criado**.
4. Se solicitado, entre no Dynamics 365.
5. Em **nome da organização**, selecione a instância do Dynamics 365 onde você deseja que o fluxo escute.
6. Em **nome da entidade**, selecione a entidade que você deseja escutar, que atuará como um gatilho que inicia o fluxo.
   
     Para este passo a passos, selecione **leads**.
   
    ![Detalhes do fluxo](./media/connection-dynamics365/flow-details.png)
    > FUNDAMENTAL Para que o fluxo seja disparado na entidade do Dynamics 365, a definição de entidade deve ter **controle de alterações** habilitado. Consulte [habilitar o controle de alterações para controlar a sincronização de dados](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Clique ou toque em **nova etapa**e, em seguida, clique ou toque em **Adicionar uma ação**.
8. Clique ou toque em **Dynamics 365 – criar um novo registro**.
9. Em **nome da organização**, selecione a instância do Dynamics 365 na qual você deseja que o fluxo crie o registro. Observe que ele não precisa ser a mesma instância da qual o evento é disparado.
10. Em **nome da entidade**, selecione a entidade que criará um registro quando o evento ocorrer.
    
     Para este guia, selecione **tarefas**.
11. Uma caixa de **assunto** é exibida. Quando você clica ou toca nele, um painel de conteúdo dinâmico é exibido, onde você pode selecionar um desses campos.
    
    * **Sobrenome**. Se você selecionar esse campo, o último nome do cliente potencial será inserido no campo **assunto** da tarefa quando ele for criado.
    * **Tópico**. Se você selecionar esse campo, o campo de **tópico** do cliente potencial será inserido no campo **assunto** da tarefa quando ele for criado.
    
    Para este guia, selecione **tópico**.
    
    ![Adicionar tópico de fluxo](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Dica:** No painel de conteúdo dinâmico, clique ou toque em **Ver mais** para exibir mais campos associados à entidade. Por exemplo, você também pode preencher o campo de **assunto** da tarefa com o campo **nome da empresa**, **cliente**, **Descrição**ou **email** do cliente potencial.
    > 
    > 
12. Clique ou toque em **criar fluxo**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Criar uma tarefa do Wunderlist de uma tarefa do Dynamics 365
Este tutorial mostra como criar uma tarefa no [Wunderlist](https://www.wunderlist.com) sempre que uma tarefa é criada no Dynamics 365. O Wunderlist é um serviço baseado na Internet que você pode usar para criar listas de tarefas pendentes, adicionar lembretes ou controlar as alterações.

1. Entre no site do [Microsoft Flow](https://flow.microsoft.com/).
2. Clique ou toque em **meus fluxos**e, em seguida, clique ou toque em **criar em branco**.
3. Na lista de gatilhos de fluxo, clique ou toque em **Dynamics 365-quando um registro é criado**.
4. Em **nome da organização**, selecione a instância do Dynamics 365 onde você deseja que o fluxo escute.
5. Em **nome da entidade**, selecione a entidade que você deseja escutar, que atuará como um gatilho para iniciar o fluxo.
   
    Para este guia, selecione **tarefas**.
6. Clique ou toque em **nova etapa**e, em seguida, clique ou toque em **Adicionar uma ação**.
7. Digite *criar uma tarefa*e, em seguida, clique ou toque em **Wunderlist – criar uma tarefa**.
8. Em **ID da lista**, selecione **caixa de entrada**.
9. Em **título**, selecione **assunto** no painel de conteúdo dinâmico.
10. Clique ou toque em **criar fluxo**.  

## <a name="trigger-based-logic"></a>Lógica baseada em gatilho
Gatilhos como **quando um registro é criado**, **quando um registro é atualizado**e **quando um registro é excluído** iniciam o fluxo dentro de alguns minutos do evento que ocorre.  Em casos raros, o fluxo pode levar até 2 horas para ser disparado.

Quando o gatilho ocorre, o fluxo recebe uma notificação, mas o fluxo é executado em dados que existem no momento em que a ação é executada.  Por exemplo, se o fluxo disparar quando um novo registro for criado e você atualizar o registro duas vezes antes de executar o fluxo, o fluxo será executado apenas uma vez com os dados mais recentes.

## <a name="specify-advanced-options"></a>Especificar opções avançadas
Ao adicionar uma etapa a um fluxo, você pode clicar ou tocar em **Mostrar opções avançadas** para adicionar uma consulta de filtro ou ordenar por que controla como os dados são filtrados no fluxo.

Por exemplo, você pode usar uma consulta de filtro para recuperar somente contatos ativos e pode ordená-los por sobrenome. Para fazer isso, insira a consulta de filtro OData **StatusCode EQ 1** e selecione **Last Name** no painel de conteúdo dinâmico. Para obter mais informações sobre consultas de filtro e ordenar por, consulte [msdn: $Filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) e [msdn: $OrderBy](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Consulta de fluxo OrderBy](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Práticas recomendadas ao usar opções avançadas
Ao adicionar um valor a um campo, você deve corresponder ao tipo de campo, independentemente de digitar um valor ou selecionar um no painel de conteúdo dinâmico.

| Tipo de campo | Como usar | Onde encontrar | Nomes | Tipo de dados |
| --- | --- | --- | --- | --- |
| Campos de texto |Os campos de texto exigem uma única linha de texto ou conteúdo dinâmico que seja um campo de tipo de texto. Os exemplos incluem a **categoria** e os campos **de subcategoria** . |**Configurações** > **personalizações** > **Personalizar as entidades de > do sistema** > **campos** de > de **tarefas** |**Categorias** |**Linha única de texto** |
| Campos de inteiro |Alguns campos exigem conteúdo inteiro ou dinâmico que seja um campo de tipo inteiro. Os exemplos incluem **porcentagem concluída** e **duração**. |**Configurações** > **personalizações** > **Personalizar as entidades de > do sistema** > **campos** de > de **tarefas** |**PercentComplete** |**Número inteiro** |
| Campos de data |Alguns campos exigem uma data inserida no formato mm/dd/aaaa ou conteúdo dinâmico que seja um campo de tipo de data. Os exemplos **incluem criado em**, **data de início**, **início real**, **último em tempo de espera**, **fim real**e **data de conclusão**. |**Configurações** > **personalizações** > **Personalizar as entidades de > do sistema** > **campos** de > de **tarefas** |**criar** |**Data e hora** |
| Campos que exigem uma ID de registro e tipo de pesquisa |Alguns campos que fazem referência a outro registro de entidade exigem a ID do registro e o tipo de pesquisa. |**Configurações** > **personalizações** > **Personalizar as entidades de > do sistema** > **campos** de > de **conta** |**AccountId** |**Chave primária** |
|Conjunto de opções|Os campos de conjunto de opções exigem que um valor inteiro conhecido seja passado para esse tipo de campo.  Na área de personalização do Dynamics 365, uma exibição a opção define o backup do campo inteiro junto com seu respectivo rótulo.|Configurações > Personalização > personalizar as entidades de > do sistema > campos de > de conta | Método de contato preferencial| Número inteiro|

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Mais exemplos de campos que exigem uma ID de registro e um tipo de pesquisa
Expandindo na tabela anterior, veja mais exemplos de campos que não funcionam com valores selecionados na lista de conteúdo dinâmico. Em vez disso, esses campos exigem uma ID de registro e um tipo de pesquisa inseridos nos campos no PowerApps.

* **Proprietário** e **tipo de proprietário**.
  
  * O campo **proprietário** deve ser uma ID de registro de usuário ou de equipe válida.
  * O **tipo de proprietário** deve ser **systemusers** ou **Teams**.
* **Cliente** e **tipo de cliente**.
  
  * O campo **cliente** deve ser uma conta válida ou ID de registro de contato.
  * O **tipo de cliente** deve ser **contas** ou **contatos**.
* **Referente** a e **referente ao tipo**.
  
  * O campo **referente** deve ser uma ID de registro válida, como uma ID de registro de conta ou contato.
  * O **tipo referente** deve ser o tipo de pesquisa para o registro, como **contas** ou **contatos**.

Este exemplo adiciona um registro de conta que corresponde à ID do registro, adicionando-o ao campo **referente** da tarefa.

  ![Fluxo de registro e conta de tipo](./media/connection-dynamics365/flow-recordid-account.png)

Este exemplo também atribui a tarefa a um usuário específico com base na ID de registro do usuário.

  ![Fluxo recordId e tipo usuário](./media/connection-dynamics365/flow-recordid-user.png)

Para localizar a ID de um registro, consulte [localizar a ID de registro](#find-the-records-id) mais adiante neste tópico.

> **Importante:** Os campos não devem conter um valor se eles tiverem uma descrição de "somente para uso interno". Esses campos incluem **caminho atravessado**, **parâmetros adicionais**e **número de versão da regra de fuso horário.**
> 
> 

## <a name="find-the-records-id"></a>Localizar a ID do registro
1. No aplicativo Web do Dynamics 365, abra um registro, como um registro de conta.
2. Na barra de ferramentas ações, clique ou toque em **pop-Out**
   ![registro de popout](./media/connection-dynamics365/popout.png) (ou clique ou toque em **enviar um link por email** para copiar a URL completa para seu programa de email padrão).
   
    Na barra de endereços do navegador da Web, a URL contém a ID de registro entre os caracteres de codificação% 7B e% 7D.
   
   ![RecordId](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Tópicos relacionados
[Solução de problemas de um fluxo](fix-flow-failures.md)

[Fluxo na sua organização Q & A](organization-q-and-a.md)

[Perguntas frequentes](frequently-asked-questions.md)

