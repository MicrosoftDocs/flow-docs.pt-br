---
title: Aperfeiçoar os fluxos de processo empresarial com ramificação com o PowerApps | Microsoft Docs
description: Saiba como usar ramificação em um fluxo de processo empresarial
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8911c828b216d8f65210b4c54603fd8838e848b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65054097"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Tutorial: Aprimorar os fluxos de processos empresariais com ramificação

Os fluxos de processo empresarial guiam você por vários estágios de vendas, marketing ou processos de serviço em direção à conclusão. Em casos simples, um fluxo de processo empresarial linear é uma boa opção. No entanto, em cenários mais complexos, você pode aprimorar um fluxo de processo empresarial com a ramificação. Se tiver as permissões de criação em fluxos de processo empresarial, você será capaz de criar um fluxo de processo empresarial com várias ramificações usando a lógica `If-Else`. A condição de ramificação pode ser formada por diversas expressões lógicas que usam uma combinação de operadores `AND` ou `OR`. A seleção de ramificação é feita automaticamente, em tempo real, com base nas regras definidas durante a definição de processo. Por exemplo, na venda de carros, você pode configurar um fluxo de processo empresarial único, que, após um estágio de qualificação comum, é dividido em duas ramificações separadas com base em uma regra (o cliente prefere um carro novo ou um carro usado, o orçamento está acima ou abaixo de US$ 20.000, e assim por diante ), uma ramificação para venda de novos carros e outra para venda de carros usados. Para mais informações sobre os fluxos de processo empresarial, consulte [Visão geral de fluxos de processo empresarial](business-process-flows-overview.md).  
  
 O diagrama a seguir mostra um fluxo de processo empresarial com ramificações.  
  
 ![Fluxograma mostrando as etapas no processo de vendas de carro](media/example-car-sales-flow-chart.png "Fluxograma mostrando as etapas no processo de vendas de carro")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>O que você precisa saber ao criar fluxos de processo empresarial com ramificações  
 Observe as seguintes informações quando você projeta o fluxo do processo empresarial com ramificações:  
  
-   Um processo pode se estender por um máximo de cinco entidades exclusivas.  
  
-   Você pode usar um máximo de 30 estágios por processo e um máximo de 30 etapas por estágio.  
  
-   Cada ramificação pode ter não mais que cinco níveis de profundidade.  
  
-   A regra de ramificação deve ser baseada nas etapas do estágio que o precede imediatamente.  
  
-   Você pode combinar várias condições em uma regra usando o operador `AND` ou `OR`, mas não os dois.  
  
-   Ao definir um fluxo de processo, você pode, opcionalmente, selecionar uma relação de entidade. Essa relação deve ser uma relação de entidade de 1:N (um para muitos).  
  
-   Mais de um processo ativo pode ser executado simultaneamente no mesmo registro de dados.  
  
-   Você pode reorganizar os blocos (Estágios, Etapas, Condições, etc.) no fluxo do processo usando “arrastar e soltar”.  
  
-   Ao mesclar ramificações, todas as ramificações pares devem ser mescladas em um único estágio. As ramificações pares devem ser mescladas em único estágio ou cada ramificação par deve encerrar o processo. Uma ramificação par não pode ser mesclada com outras e, ao mesmo tempo, encerrar o processo.  
  
> [!NOTE]
> - Uma entidade usada no processo pode ser revisitada várias vezes (vários loops de entidade fechados).  
> - Um processo pode voltar para o estágio anterior, independentemente de um tipo de entidade. Por exemplo, se o estágio ativo for **Entregar cotação** em um registro de cotação, os usuários do processo poderão mover o estágio ativo para o estágio **Propor** em um registro de oportunidade.  
>   
>   Em outro exemplo, suponha que um processo esteja atualmente no estágio **Apresentar Proposta** no fluxo do processo: **Qualificar Cliente Potencial** > **Identificar Necessidades** > **Criar Proposta** > **Apresentar Proposta** > **Fechar**. Se a proposta apresentada para o cliente exigir mais pesquisa para identificar as necessidades do cliente, os usuários poderão selecionar apenas o estágio **Identificar necessidades** do seu processo e escolher **Definir ativo**.  
  
<a name="CarSelling365"></a>   
## <a name="dynamics-365-customer-engagement-example-car-selling-process-flow-with-two-branches"></a>Exemplo do Dynamics 365 Customer Engagement: Fluxo de processo de venda de carro com duas ramificações
 
Vamos ver um exemplo de fluxo do processo empresarial com duas ramificações, para venda de carros novos e usados.  
  
 Primeiramente, vamos criar um novo processo chamado **Processo de vendas de carro**.  
  
1.  [Abra o gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e, em seguida, no painel de navegação esquerdo, selecione **Processos**.  
  
2.  Selecione **Novo** para criar um novo processo.  
  
3.  Especifique a **Categoria** como **Fluxo de processo empresarial** e, para a **Entidade** principal, escolha **Cliente potencial**.  
  
4.  Adicione o primeiro estágio ao processo de chamado **Qualificar** e adicione as etapas **Período de tempo de compra** e **Preferência de carro**.  
  
5.  Após o estágio **Qualificar** comum, dividimos o processo em duas ramificações separadas, usando o bloco **Condição**.  
  
    1.  Configure o bloco de condição com regras que atendam seus requisitos de negócios  
  
    2.  Para adicionar a primeira ramificação a um estágio, adicione um bloco Estágio no caminho "Sim" do bloco de condição  
  
    3.  Para adicionar a segundo ramificação que é executada quando a condição não for atendida, adicione outro bloco Estágio no caminho "Não" do bloco de condição  
  
> [!TIP]
>  Você pode adicionar outra condição no caminho "não" de um bloco de condição existente para criar ramificações mais complexas.  
  
 ![Imagem mostrando o estágio Qualificar criado](media/example-car-sales-qualify-stage.JPG "Imagem mostrando o estágio Qualificar criado")  
  
 Se **Preferência de carro** = **Novo**, o processo é ramificado para o estágio **Venda de carro novo**. Caso contrário, ele salta para o estágio **Venda de carro usado**, na segunda ramificação, conforme mostrado abaixo.  
  
 ![Imagem mostrando o estágio de venda de carro novo](media/example-car-sales-new-stage-1.JPG "Imagem mostrando o estágio de venda de carro novo")  
  
 ![Estágio&#45;de venda de carro usado](media/example-car-sales-pre-owned-stage.JPG "Estágio de venda de carro usado")  
  
 Depois de concluir todas as etapas no estágio **Venda de carro novo** ou **Venda de carro usado**, o processo retorna para o fluxo principal, com o estágio **Entregar cotação**.  
  
 ![Estágio Entregar cotação](media/example-car-sales-deliver-quote-stage.JPG "Estágio Entregar cotação")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Evitar a divulgação de informações confidenciais  
 Considere um fluxo de processo empresarial com ramificações para processar uma solicitação de empréstimo em um banco, conforme mostrado abaixo. As entidades personalizadas usadas nos estágios são mostradas entre parênteses.  
  
 ![Fluxograma mostrando as etapas em um processo de exemplo para evitar a divulgação de informações confidenciais](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Fluxograma mostrando as etapas em um processo de exemplo para evitar a divulgação de informações confidenciais")  
  
 Nesse cenário, a responsável pelo empréstimo bancário precisa acessar o registro de solicitação, mas ela não deve ter nenhuma visibilidade sobre a investigação da solicitação. À primeira vista, parece que podemos facilmente fazer isso atribuindo à responsável pelo empréstimo uma função de segurança que não especifica nenhum acesso à entidade de investigação. Mas, vamos examinar o exemplo mais detalhadamente e ver se isso é realmente verdadeiro.  
  
 Digamos que um cliente coloca na solicitação de empréstimo mais de US$ 60.000 para o banco. A responsável pelo empréstimo examina a solicitação no primeiro estágio. Se a regra de ramificação que verifica se o valor devido ao banco excederá US$ 50.000 for atendida, o próximo estágio do processo será investigar se a solicitação é fraudulenta. Se for determinado de que é realmente um caso de fraude, o processo prosseguirá para ações legais contra o solicitante. A responsável pelo empréstimo não deve ter visibilidade sobre os dois estágios investigativos porque ela não tem acesso à entidade de investigação.  
  
 No entanto, se a responsável pelo empréstimo abrir o registro de solicitação, qualquer pessoa poderá ver todo o processo de ponta a ponta. Ela terá a capacidade de ver o estágio de investigação de fraude e também de identificar o resultado da investigação por ter sido capaz de ver o estágio de ações legais no processo. Além disso, ela poderá visualizar as etapas nos estágios de investigação escolhendo o estágio. Ela não terá permissão para ver os dados ou o status de conclusão da etapa, mas poderá identificar as possíveis ações que foram executadas em relação ao emissor da solicitação, durante os estágios de investigação e ação legal.  
  
 Nesse fluxo de processo, a responsável pelo empréstimo será capaz de ver os estágios de investigação de fraude e ações legais, que constitui uma divulgação imprópria de informações confidenciais. É recomendável prestar atenção especial às informações que podem ser divulgadas devido à ramificação. Em nosso exemplo, divida o processo em dois processos separados, um para o processamento da solicitação e outro para a investigação de fraudes, para evitar a divulgação de informações confidenciais. O processo para a responsável pelo empréstimo terá esta aparência:  
  
 ![Fluxograma mostrando as etapas adicionais em um processo para evitar a divulgação de informações confidenciais](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Fluxograma mostrando as etapas adicionais em um processo para evitar a divulgação de informações confidenciais")  
  
 O processo para a investigação será independente e incluirá os seguintes estágios:  
  
 ![Fluxograma mostrando as etapas para um processo de investigação para casos de divulgação de informações confidenciais](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Fluxograma mostrando as etapas para um processo de investigação para casos de divulgação de informações confidenciais")  
  
 Você precisará fornecer um fluxo de trabalho para sincronizar a decisão de aprovar/negar do registro de investigação no registro da solicitação.  
  
### <a name="next-steps"></a>Próximas etapas  
 [Criar um fluxo de processo empresarial](create-business-process-flow.md)   
 [Criar lógica de negócios personalizada com processos](guide-staff-through-common-tasks-processes.md)   
 
