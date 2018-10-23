---
title: Use expressões com condições. | Microsoft Docs
description: Uso de expressões avançadas, como "e", "ou", "vazio", "menos" e "maior" com as condições do Microsoft Flow.
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
ms.date: 08/01/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 81aa718837fa14615459f3688a282c25cb99bab6
ms.sourcegitcommit: dc188618c36583b20af3e838d72bd7b020575d7d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2018
ms.locfileid: "48874427"
---
# <a name="use-expressions-in-conditions-to-check-multiple-values"></a>Usar funções nas condições para verificar diversos valores
Neste passo a passo, você aprenderá a usar expressões e **Condições** para comparar diversos valores no **modo Avançado**.

Ao criar um fluxo, use o cartão [ **Condição**](add-condition.md#add-a-condition) no modo básico para comparar rapidamente um único valor com outro. No entanto, há vezes em que você precisará comparar diversos valores. Por exemplo, talvez você queira verificar o valor de algumas colunas em uma planilha ou tabela do banco de dados.

É possível usar qualquer combinação das seguintes expressões lógicas em suas condições.

Expressão|Descrição|Exemplo
--------|-----------|-------
|[and](#use-the-and-expression)|Obtém dois argumentos e retorna true se ambos os valores são verdadeiros.<br><b>Observação</b>: ambos os argumentos devem ser boolianos.|Essa expressão retorna false: <br>and(greater(1,10),equals(0,0))
|[or](#use-the-or-expression)|Obtém dois argumentos e retorna true se qualquer um dos valores é verdadeiro. <br><b>Observação</b>: ambos os argumentos devem ser boolianos.|Essa expressão retorna true:<br>or(greater(1,10),equals(0,0))
|equals|Retorna true se os dois valores são iguais.|Por exemplo, se o parameter1 for algumValor, a função retornará true:<br>equals(parameters('parameter1'), 'someValue')
|[less](#use-the-less-expression)|Obtém dois argumentos e retorna true se o primeiro argumento é menor que o segundo argumento. <br><b>Observação</b>: os tipos suportados são: inteiro, flutuante e cadeia de caracteres.|Essa expressão retorna true:<br>less(10,100)
|lessOrEquals|Obtém dois argumentos e retorna true se o primeiro argumento é menor que ou igual ao segundo argumento. <br><b>Observação</b>: os tipos suportados são: inteiro, flutuante e cadeia de caracteres.|Essa expressão retorna true:<br>lessOrEquals(10,10)
|[greater](#use-the-greater-expression)|Obtém dois argumentos e retorna true se o primeiro argumento é maior que o segundo. <br><b>Observação</b>: os tipos suportados são: inteiro, flutuante e cadeia de caracteres.|Essa expressão retorna false:<br>greater(10,10)
|greaterOrEquals|Obtém dois argumentos e retorna true se o primeiro argumento é maior que ou igual ao segundo argumento. <br><b>Observação</b>: os tipos suportados são: inteiro, flutuante e cadeia de caracteres.|Essa expressão retorna false:<br>greaterOrEquals(10,100)
|[empty](#use-the-empty-expression)|Retorna true se a matriz, cadeia de caracteres ou objeto estiver vazio.|Essa expressão retorna true:<br>empty('')
|not|Retorna o oposto de um valor booliano. |Essa expressão retorna true:<br>not(contains('200 Success','Fail'))
|if|Retorna um valor específico se a expressão resulta em true ou false.|Essa expressão retorna "yes":<br>if(equals(1, 1), 'yes', 'no')

## <a name="prerequisites"></a>Pré-requisitos
* Acesso ao Microsoft Flow.
* Mais adiante neste passo a passo, apresentaremos uma planilha com as tabelas descritas. Salve a planilha em um local como o Dropbox ou o Microsoft OneDrive para que o Microsoft Flow possa acessá-la.
* Outlook do Microsoft Office 365 (enquanto usamos o Outlook do Office 365, você pode usar qualquer serviço de email com suporte em seus fluxos.)

## <a name="use-the-or-expression"></a>Usar a expressão or
Às vezes, o fluxo de trabalho precisa executar uma ação se o valor de um item for o valorA **ou** o valorB. Por exemplo, você pode acompanhar o status das tarefas em uma tabela da planilha. Suponha que a tabela possua uma coluna denominada *Status* e os possíveis valores na coluna *Status* sejam:

* **concluído**
* **bloqueado**
* **desnecessário**
* **não iniciado**

Veja um exemplo da provável aparência da planilha:

![planilha de exemplo](./media/use-expressions-in-conditions/spreadsheet-table.png)

Dada a planilha anterior, você deseja usar o Microsoft Flow para remover todas as linhas com uma coluna *Status* definida como *concluído* ou *desnecessário*.

Vamos criar o fluxo.

### <a name="start-with-a-blank-flow"></a>Iniciar com um fluxo em branco
1. Entre no [Microsoft Flow](https://flow.microsoft.com).

    ![entrar](includes/media/modern-approvals/sign-in.png)
2. Selecione a guia **Meus fluxos**.

    ![selecione meus fluxos](includes/media/modern-approvals/select-my-flows.png)
3. Selecione **Criar do zero**.

    ![criar do zero](includes/media/modern-approvals/blank-template.png)

### <a name="add-a-trigger-to-your-flow"></a>Adicionar um gatilho ao fluxo
1. Procure **Agendamento** e, em seguida, escolha o gatilho **Agendamento - Recorrência**

    ![agendar o gatilho](includes/media/schedule-trigger/schedule-trigger.png)
2. Defina o agendamento para ser executado uma vez por dia.

    ![definir o agendamento](includes/media/schedule-trigger/set-schedule.png)

### <a name="select-the-spreadsheet-and-get-all-rows"></a>Selecionar a planilha e obter todas as linhas
1. Selecione **Nova etapa** > **Adicionar uma ação**.

    ![nova etapa](includes/media/new-step/action.png)
2. Procure as **linhas** e, em seguida, selecione **Excel - Obter linhas**.

    Observação: selecione a ação "obter linhas" que corresponde à planilha que você está usando. Por exemplo, se você estiver usando as Planilhas do Google, selecione **Planilhas do Google - Obter linhas**.

    ![obter Linhas](includes/media/new-step/get-excel-rows.png)
3. Selecione o ícone de pasta na caixa **Nome do arquivo**, navegue e escolha a planilha que contém seus dados.

    ![selecionar planilha](includes/media/new-step/select-spreadsheet.png)
4. Escolha a tabela que contém seus dados na lista **Nome da tabela**.

    ![selecionar tabela](includes/media/new-step/select-table.png)

### <a name="check-the-status-column-of-each-row"></a>Verificar a coluna de status de cada linha
1. Selecione **Nova etapa** > **Mais** > **Adicionar um aplicar a cada**.

    ![selecionar tabela](includes/media/new-step/apply-to-each.png)
2. Adicione o token **Valor** à caixa **Selecionar uma saída nas etapas anteriores**.

    ![selecionar tabela](includes/media/apply-to-each/add-value-token.png)
3. Selecione **Adicionar uma condição** > **Editar no modo avançado**.
4. Adicione a expressão **or** a seguir. A expressão **or** verifica o valor de cada linha na tabela (uma linha é conhecida como item quando acessada em uma expressão). Se o valor da coluna **status** for *concluído* **ou** *desnecessário*, a expressão **or** será avaliada como "true".

    A expressão **or** aparece como mostrado aqui:

    ````@or(equals(item()?['status'], 'unnecessary'), equals(item()?['status'], 'completed'))````

    O cartão **Condição** é semelhante a esta imagem:

    ![imagem da expressão or](./media/use-expressions-in-conditions/or-expression.png)

### <a name="delete-matching-rows-from-the-spreadsheet"></a>Excluir linhas correspondentes da planilha
1. Selecione **Adicionar uma ação** na ramificação da condição **SE SIM, NÃO FAÇA NADA**.
2. Pesquise **Excluir linha** e, em seguida, selecione **Excel - Excluir linha**.

    ![excluir a imagem da linha](includes/media/new-step/select-delete-excel-row.png)
3. Na caixa **Nome do arquivo**, pesquise e escolha o arquivo da planilha que contém os dados que você deseja excluir.
4. Na lista **Nome da tabela**, selecione a tabela que contém seus dados.
5. Coloque o token **Id da linha** na caixa **Id da linha**.

    ![arquivo da planilha](includes/media/new-step/delete-excel-row.png)

### <a name="name-the-flow-and-save-it"></a>Nomear e salvar o fluxo
1. Nomeie seu fluxo e selecione o botão **Criar fluxo**.

    ![salvar seu fluxo](./media/use-expressions-in-conditions/name-and-save.png)

### <a name="run-the-flow-with-the-or-expression"></a>Executar o fluxo com a expressão or
O fluxo é executado depois que você salvá-lo. Se você criou a planilha mostrada anteriormente neste passo a passo, ela terá essa aparência após a execução ser concluída:

![a expressão or termina](./media/use-expressions-in-conditions/spreadsheet-table-after-or-expression-runs.png)

Observe que todos os dados das linhas que tinham "concluído" ou "desnecessário" na coluna Status foram excluídos.

## <a name="use-the-and-expression"></a>Usar a expressão and
Suponha que você tenha uma tabela da planilha com duas colunas. Os nomes das colunas são Status e Atribuído. Suponha também que você queira excluir todas as linhas se o valor da coluna Status for "bloqueado" e o valor da coluna Atribuído for "John Wonder".  Para realizar essa tarefa, siga todas as etapas anteriores neste passo a passo. No entanto, quando você editar o cartão **Condição** no modo avançado, use a expressão **and** mostrada aqui:

````@and(equals(item()?['Status'], 'blocked'), equals(item()?['Assigned'], 'John Wonder'))````

O cartão **Condição** é semelhante a esta imagem:

![imagem da expressão and](./media/use-expressions-in-conditions/and-expression.png)

### <a name="run-the-flow-with-the-and-expression"></a>Executar o fluxo com a expressão and
Se você tiver acompanhado o processo, a planilha será semelhante a esta imagem:

![antes de and ser executada](./media/use-expressions-in-conditions/spreadsheet-table-before-and-expression-runs.png)

Depois do fluxo ser executado, a planilha será semelhante a esta imagem:

![após and ser executada](./media/use-expressions-in-conditions/spreadsheet-table-after-and-expression-runs.png)

## <a name="use-the-empty-expression"></a>Usar a expressão empty
Observe que agora, há várias linhas vazias na planilha. Para removê-las, use a expressão **empty** para identificar todas as linhas sem texto nas colunas Atribuído e Status.

Para realizar essa tarefa, siga todas as etapas listadas na seção **Usar a função and** anteriormente neste passo a passo. No entanto, quando você editar o cartão **Condição** no modo avançado, use a função empty da seguinte maneira:

````@and(empty(item()?['Status']), empty(item()?['Assigned']))````

O cartão **Condição** é semelhante a esta imagem:

![imagem da expressão empty](./media/use-expressions-in-conditions/empty-expression.png)

Depois do fluxo ser executado, a planilha será semelhante a esta imagem:

![após empty ser executada](./media/use-expressions-in-conditions/spreadsheet-table-after-empty-expression-runs.png)

Observe que as linhas extras foram removidas da tabela.

## <a name="use-the-greater-expression"></a>Usar a expressão greater
Imagine que você tenha comprado ingressos para um jogo de baseball para seus colegas de trabalho e está usando uma planilha para garantir que será reembolsado por cada pessoa. Você pode criar rapidamente um fluxo que envia um email diário para cada pessoa que não pagou o valor total.

Use a expressão **greater** para identificar os funcionários que não pagaram o valor total. Em seguida, você pode enviar automaticamente um email de lembrete amigável para aqueles que não pagaram o total.

Veja uma exibição da planilha:

![exibição da planilha](./media/use-expressions-in-conditions/tickets-spreadsheet-table.png)

Veja a implementação da expressão **greater** que identifica todas as pessoas que pagaram menos que a quantidade devida:

````@greater(item()?['Due'], item()?['Paid'])````

## <a name="use-the-less-expression"></a>Usar a expressão less
Imagine que você tenha comprado ingressos para um jogo de baseball para seus colegas de trabalho e está usando uma planilha para garantir que será reembolsado por cada pessoa na data que todos acordaram. Você pode criar um fluxo que envia um email de lembrete para cada pessoa que não pagou o valor total, caso a data atual seja menor que um dia antes da data de vencimento.

Use a expressão **and** junto com a expressão **less**, uma vez que há duas condições sendo validadas:


|          Condição a validar          | expressão a usar |                    Exemplo                     |
|-----------------------------------------|-------------------|------------------------------------------------|
|   O valor total devido foi pago?    |      greater      |   @greater(item()?['Due'], item()?['Paid'])    |
| A data devida é menor que um dia? |       less        | @less(item()?['DueDate'], addDays(utcNow(),1)) |

## <a name="combine-the-greater-and-less-expressions-in-an-and-expression"></a>Combinar as expressões greater e less em uma expressão and
Use a expressão **greater** para identificar os funcionários que pagaram menos que o valor total devido e use a expressão **less** para determinar se a data de vencimento é menor que um dia antes da data atual. Então, você poderá usar a ação **Enviar um email** para enviar um email de lembrete amigável para aqueles que não pagaram tudo e cuja data de vencimento é menor que um dia.

Veja uma exibição da tabela da planilha:

![exibição da planilha](./media/use-expressions-in-conditions/spreadsheet-table-due-date.png)

Veja a implementação da expressão **and** que identifica todas as pessoas que pagaram menos que o valor devido e se a data de vencimento é menor que um dia antes da data atual:

````@and(greater(item()?['Due'], item()?['Paid']), less(item()?['dueDate'], addDays(utcNow(),1)))````

## <a name="learn-more"></a>Saiba mais
Saiba mais sobre outras [expressões](https://docs.microsoft.com/azure/logic-apps/logic-apps-workflow-definition-language#functions)

