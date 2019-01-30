---
title: Criar um fluxo com o Dynamics 365 (online) | Microsoft Docs
description: Crie fluxos de trabalho úteis usando uma conexão do Dynamics 365 e o Microsoft Flow
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
ms.openlocfilehash: e5abf1dd6f1f1d1dd6853aa552460694aebddd61
ms.sourcegitcommit: 31b578972f00e6ab2e50ea0b674142199b3b7a35
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54905645"
---
# <a name="create-a-flow-by-using-dynamics-365-online"></a>Criar um fluxo usando o Dynamics 365 (online)
Com um conector do Dynamics 365, crie fluxos iniciados quando ocorre um evento no Dynamics 365, ou em algum outro serviço, que, em seguida, executa uma ação no Dynamics 365, ou em algum outro serviço. 

No Microsoft Flow é possível configurar fluxos de trabalho automatizados entre seus aplicativos e serviços favoritos a fim de sincronizar arquivos, obter notificações, coletar dados e muito mais. Para saber mais, confira [Introdução ao Microsoft Flow](getting-started.md).

> [!IMPORTANT] 
> Para invocar um gatilho de fluxo, a entidade de engajamento de cliente do Dynamics 365 usada com o fluxo deve estar com o **Controle de Alterações** habilitado. Mais informações: [Habilitar o Controle de Alterações para controlar a sincronização de dados](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) 

## <a name="create-a-flow-from-a-template"></a>Criar um fluxo de um modelo
Crie um fluxo usando um dos vários modelos disponíveis, como nestes exemplos:

* Quando um objeto é criado no Dynamics 365, um item de lista também é criado no SharePoint.
* Crie registros de lead do Dynamics 365 a partir de uma tabela do Excel.
* Copie contas do Dynamics 365 para os clientes no Dynamics 365 for Operations.

Para criar um fluxo de um modelo, execute estas etapas.

1. Entre no [site do Microsoft Flow](https://flow.microsoft.com/).
2. Clique ou toque **Serviços** e depois clique ou toque em **Dynamics 365**.
3. Há vários modelos disponíveis. Para começar, selecione o modelo que você deseja.

## <a name="create-a-task-from-a-lead"></a>Criar uma tarefa a partir de um lead
Se não houver um modelo disponível para sua necessidade, crie um fluxo do zero. Este passo a passo mostra como criar uma tarefa no Dynamics 365 sempre que um lead for criado no Dynamics 365.

1. Entre no [site do Microsoft Flow](https://flow.microsoft.com/).
2. Clique ou toque em **Meus fluxos**e depois clique ou toque em **Criar de um modelo em branco**.
3. Na lista de gatilhos de fluxo, clique ou toque em **Dynamics 365 - Quando um registro for criado**.
4. Se receber uma solicitação, entre no Dynamics 365.
5. Em **Nome da Organização**, selecione a instância do Dynamics 365 na qual você quer que o fluxo escute.
6. Em **Nome da Entidade**, selecione a entidade que você deseja ouvir, que agirá como um gatilho que inicia o fluxo.
   
     Para este passo a passo, selecione **Leads**.
   
    ![Detalhes do fluxo](./media/connection-dynamics365/flow-details.png)
    > [IMPORTANTE] Para o fluxo ser disparado na entidade do Dynamics 365, a definição da entidade precisa estar com o **Controle de Alterações** habilitado. Consulte [Habilitar o Controle de Alterações para controlar a sincronização de dados](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization)
    
7. Clique ou toque em **Nova etapa** e, em seguida, clique ou toque **Adicionar uma ação**.
8. Clique ou toque em **Dynamics 365 – Criar um novo registro**.
9. Em **Nome da Organização**, selecione a instância do Dynamics 365 na qual você quer que o fluxo crie o registro. Observe que não precisa ser a mesma instância a partir da qual o evento é disparado.
10. Em **Nome da Entidade**, selecione a entidade que criará um registro quando o evento ocorrer.
    
     Para este passo a passo, selecione **Tarefas**.
11. Uma caixa **Assunto** é exibida. Quando você clica ou toca nela, um painel de conteúdo dinâmico é exibido no qual você pode selecionar um destes campos.
    
    * **Sobrenome**. Se você selecionar esse campo, o sobrenome do lead será inserido no campo **Assunto** da tarefa após a criação.
    * **Tópico** Se você selecionar esse campo, o campo **Tópico** do lead será inserido no campo **Assunto** da tarefa após a criação.
    
    Para este passo a passo, selecione **Tópico**.
    
    ![Tópico de adição de fluxo](./media/connection-dynamics365/flow-addtopic.png)
    
    > **Dica:** no painel de conteúdo dinâmico, clique ou toque em **Ver mais** para exibir mais campos associados à entidade. Por exemplo, preencha também o campo **Assunto** da tarefa com o campo **Nome da Empresa**, **Cliente**, **Descrição** ou **Email** do lead.
    > 
    > 
12. Clique ou toque em **Criar fluxo**.

## <a name="create-a-wunderlist-task-from-a-dynamics-365-task"></a>Criar uma tarefa de Wunderlist a partir de uma tarefa de Dynamics 365
Este passo a passo mostra como criar uma tarefa no [Wunderlist](https://www.wunderlist.com) sempre que uma tarefa for criada no Dynamics 365. Wunderlist é um serviço baseado na Internet que pode ser usado para criar listas de tarefas, adicionar lembretes ou controlar incumbências.

1. Entre no [site do Microsoft Flow](https://flow.microsoft.com/).
2. Clique ou toque em **Meus fluxos**e depois clique ou toque em **Criar de um modelo em branco**.
3. Na lista de gatilhos de fluxo, clique ou toque em **Dynamics 365 - Quando um registro for criado**.
4. Em **Nome da Organização**, selecione a instância do Dynamics 365 na qual você quer que o fluxo escute.
5. Em **Nome da Entidade**, selecione a entidade que você deseja ouvir, que agirá como um gatilho que inicia o fluxo.
   
    Para este passo a passo, selecione **Tarefas**.
6. Clique ou toque em **Nova etapa** e, em seguida, clique ou toque **Adicionar uma ação**.
7. Digite *criar uma tarefa* e depois clique ou toque em **Wunderlist – Criar uma tarefa**.
8. Em **ID da Lista**, selecione **caixa de entrada**.
9. Em **Título**, selecione **Assunto** no painel de conteúdo dinâmico.
10. Clique ou toque em **Criar fluxo**.  

## <a name="trigger-based-logic"></a>Lógica baseada em gatilho
Gatilhos como **Quando um registro é criado**, **Quando um registro é atualizado** e **Quando um registro é excluído** iniciam o fluxo em alguns minutos depois que o evento ocorre.  Em casos raros, o fluxo pode levar até 2 horas para ser disparado.

Quando o gatilho ocorre, o fluxo recebe uma notificação, mas o fluxo é executado nos dados que existem no momento em que a ação é executada.  Por exemplo, se o fluxo é disparado quando um novo registro é criado e você atualiza o registro duas vezes antes da execução do fluxo, o fluxo é executado apenas uma vez com os dados mais recentes.

## <a name="specify-advanced-options"></a>Especificar opções avançadas
Quando você adiciona uma etapa a um fluxo, clique ou toque em **Mostrar opções avançadas** para adicionar um filtro ou uma consulta de ordenar por que controla como os dados são filtrados no fluxo.

Por exemplo, use uma consulta de filtro para recuperar somente os contatos ativos, e organize-os por sobrenome. Para fazer isso, insira a consulta de filtro OData **statuscode eq 1** e selecione **Sobrenome** no painel de conteúdo dinâmico. Para saber mais sobre como filtrar e classificar por consultas, consulte [MSDN: $filter](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_1) e [MSDN: $orderby](https://msdn.microsoft.com/library/gg309461.aspx#Anchor_2).

  ![Consulta organizar por fluxo](./media/connection-dynamics365/flow-orderby-query.png)

### <a name="best-practices-when-using-advanced-options"></a>Práticas recomendadas ao usar as opções avançadas
Ao adicionar um valor a um campo, é necessário corresponder ao tipo de campo, mesmo se você digitar um valor ou selecionar um no painel de conteúdo dinâmico.

| Tipo de campo | Como usar | Onde encontrar | Nome | Tipo de dados |
| --- | --- | --- | --- | --- |
| Campos de texto |Os campos de texto exigem uma única linha de texto ou conteúdo dinâmico que seja um campo do tipo texto. Os exemplos incluem os campos **Categoria** e **Subcategoria**. |**Configurações** > **Personalizações** > **Personalizar o Sistema** > **Entidades** > **Tarefa** > **Campos** |**categoria** |**Linha Única de Texto** |
| Campos de número inteiro |Alguns campos exigem números inteiros ou um conteúdo dinâmico que seja um campo do tipo número inteiro. Os exemplos incluem **Porcentagem Concluída** e **Duração**. |**Configurações** > **Personalizações** > **Personalizar o Sistema** > **Entidades** > **Tarefa** > **Campos** |**percentcomplete** |**Número Inteiro** |
| Campos de data |Alguns campos exigem uma data inserida no formato dd/mm/aaaa, ou um conteúdo dinâmico que seja um campo do tipo data. Os exemplos incluem **Criado em**, **Data Inicial**, **Início Real**, **Último Suspensão**, **Término Real** e **Data de Vencimento**. |**Configurações** > **Personalizações** > **Personalizar o Sistema** > **Entidades** > **Tarefa** > **Campos** |**createdon** |**Data e Hora** |
| Campos que exigem uma ID de registro e tipo de pesquisa |Alguns campos que fazem referência a outro registro de entidade exigem a ID do registro e o tipo de pesquisa. |**Configurações** > **Personalizações** > **Personalizar o Sistema** > **Entidades** > **Conta** > **Campos** |**accountid** |**Chave Primária** |

### <a name="more-examples-of-fields-that-require-both-a-record-id-and-lookup-type"></a>Mais exemplos de campos que exigem uma ID de registro e tipo de pesquisa
Expandindo a tabela anterior, veja mais exemplos de campos que não funcionam com valores selecionados na lista de conteúdo dinâmico. Em vez disso, esses campos exigem uma ID de registro e tipo de pesquisa inseridos nos campos no PowerApps.

* **Proprietário** e **Tipo de Proprietário**.
  
  * O campo **Proprietário** deve ser uma ID válida de registro de usuário ou de equipe.
  * O **Tipo de Proprietário** deve ser **systemusers** ou **equipes**.
* **Cliente** e **Tipo de Cliente**.
  
  * O campo **Cliente** deve ser uma conta válida ou ID de registro do contato.
  * O **Tipo de Cliente** deve ser **contas** ou **contatos**.
* **Referente** e **Tipo Referente**.
  
  * O campo **Referente** deve ser uma ID de registro válida, como uma ID de registro de conta ou contato.
  * O **Tipo Referente** deve ser o tipo de pesquisa para o registro, como **contas** ou **contatos**.

Esse exemplo adiciona um registro de conta que corresponde à ID do registro, adicionando-o ao campo **Referente** da tarefa.

  ![ID de registro e tipo de conta do fluxo](./media/connection-dynamics365/flow-recordid-account.png)

Esse exemplo também atribui a tarefa a um usuário específico com base na ID de registro do usuário.

  ![ID de registro e tipo de usuário do fluxo](./media/connection-dynamics365/flow-recordid-user.png)

Para localizar a ID de um registro, consulte [Encontrar a ID do registro](#find-the-records-id) mais adiante neste tópico.

> **Importante:** os campos não deverão conter um valor se tiverem uma descrição "Somente para uso interno". Esses campos incluem **Caminho percorrido**, **Parâmetros Adicionais** e **Número de versão da regra de fuso horário.**
> 
> 

## <a name="find-the-records-id"></a>Encontrar a ID do registro
1. No aplicativo Web do Dynamics 365, abra um registro, como um registro de conta.
2. Na barra de ferramentas de ações, clique ou toque em **Pop-Out**
   ![registro de pop-out](./media/connection-dynamics365/popout.png) (ou clique ou toque em **ENVIAR UM LINK POR EMAIL** para copiar a URL completa para seu programa de email padrão).
   
    Na barra de endereços do navegador da Web, a URL contém a ID do registro entre os caracteres de codificação %7b e %7d.
   
   ![ID do registro](./media/connection-dynamics365/recordid.png)

## <a name="related-topics"></a>Tópicos relacionados
[Solução de problemas de um fluxo](fix-flow-failures.md)

[P e R sobre o Flow em sua organização](organization-q-and-a.md)

[Perguntas frequentes](frequently-asked-questions.md)

