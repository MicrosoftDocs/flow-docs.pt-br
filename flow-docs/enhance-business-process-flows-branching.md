---
title: Aprimore os fluxos de processos de negócios com a ramificação com o PowerApps | MicrosoftDocs
description: Saiba como usar a ramificação em um fluxo de processo de negócios
ms.custom: ''
ms.date: 06/27/2018
ms.tgt_pltfrm: ''
ms.topic: article
ms.service: flow
author: MSFTMAN
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: Deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a03cefcb3e808bb7900b79b05e6c2b3f8ef7f5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544774"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Tutorial: melhorar os fluxos de processos empresariais com a ramificação
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Os fluxos de processos de negócios orientam você por vários estágios de vendas, marketing ou processos de serviço para a conclusão. Em casos simples, um fluxo de processo comercial linear é uma boa opção. No entanto, em cenários mais complexos, você pode aprimorar um fluxo de processo de negócios com ramificação. Se você tiver as permissões criar nos fluxos do processo comercial, poderá criar um fluxo de processo empresarial com várias ramificações usando a lógica de `If-Else`. A condição de ramificação pode ser formada por várias expressões lógicas que usam uma combinação de operadores de `AND` ou `OR`. A seleção de ramificação é feita automaticamente, em tempo real, com base nas regras definidas durante a definição do processo. Por exemplo, em venda de carros, você pode configurar um fluxo de processo de negócios único, que depois que um estágio de qualificação comum se divide em duas ramificações separadas com base em uma regra (o cliente prefere um novo carro ou carro de propriedade), é seu orçamento acima ou abaixo de $20000 e assim por diante. ), uma ramificação, para vender novos carros e outra ramificação, para vender carros de propriedade. Para obter mais informações sobre fluxos de processo de negócios, consulte [visão geral de fluxos de processos de negócios](business-process-flows-overview.md).  
  
 O diagrama a seguir mostra um fluxo de processo de negócios com branches.  
  
 ![Fluxograma mostrando as etapas no processo de vendas do carro](media/example-car-sales-flow-chart.png "Fluxograma mostrando as etapas no processo de vendas do carro")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>O que você precisa saber ao projetar fluxos de processo de negócios com branches  
 Tome nota das seguintes informações ao projetar o fluxo do processo de negócios com as ramificações:  
  
-   Um processo pode abranger no máximo 5 entidades exclusivas.  
  
-   Você pode usar um máximo de 30 estágios por processo e um máximo de 30 etapas por etapa.  
  
-   Cada ramificação não pode ter mais de 5 níveis de profundidade.  
  
-   A regra de ramificação deve ser baseada nas etapas no estágio que a precede imediatamente.  
  
-   Você pode combinar várias condições em uma regra usando o operador de `AND` ou o operador de `OR`, mas não ambos os operadores.  
  
-   Ao definir um fluxo de processo, você pode opcionalmente selecionar uma relação de entidade. Essa relação deve ser uma relação de entidade 1: N (um-para-muitos).  
  
-   Mais de um processo ativo pode ser executado simultaneamente no mesmo registro de dados.  
  
-   Você pode reorganizar blocos (estágios, etapas, condições, etc.) no fluxo do processo usando arrastar e soltar.  
  
-   Ao mesclar branches, todos os branches pares devem ser mesclados em um único estágio. As ramificações de pares devem ser mescladas em um único estágio ou cada ramificação do par deve encerrar o processo. Uma ramificação par não pode mesclar com outras ramificações e, ao mesmo tempo, encerrar o processo.  
  
> [!NOTE]
> - Uma entidade usada no processo pode ser revisitada várias vezes (vários loops de entidade fechados).  
> - Um processo pode voltar para o estágio anterior, independentemente de um tipo de entidade. Por exemplo, se o estágio ativo for **entregar uma cotação** em um registro de cotação, os usuários do processo poderão mover o estágio ativo de volta para o estágio de **proposta** em um registro de oportunidade.  
>   
>   Em outro exemplo, suponha que um processo esteja atualmente no estágio **presente da proposta** em seu fluxo de processo: **qualificar Lead** > **identificar necessidades** > **criar** proposta > **presente proposta** >  **Fechar**. Se a proposta apresentada ao cliente exigir mais pesquisa para identificar as necessidades do cliente, os usuários poderão simplesmente selecionar o estágio **identificar necessidades** do processo e escolher **definir ativo**.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Exemplo: fluxo de processo de venda de carro com duas ramificações
 
Vejamos o exemplo do fluxo do processo empresarial com duas ramificações, para venda de carros novos e de propriedade.  
  
 Primeiro, vamos criar um novo processo chamado **carro Sales Process**.  
  
1.  [Abra o Gerenciador de soluções](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) e, no painel de navegação à esquerda, selecione **processos**.  
  
2.  Selecione **novo** para criar um novo processo.  
  
3.  Especifique a **categoria** como **fluxo de processo de negócios** e para a **entidade** primária, escolha **cliente potencial**.  
  
4.  Adicione o primeiro estágio ao processo chamado **qualificar** e adicione as etapas **intervalo de tempo de compra** e preferência de **carro**.  
  
5.  Após o estágio comum de **qualificação** , dividimos o processo em duas ramificações separadas, usando o bloco **condição** .  
  
    1.  Configurar o bloco de condição com regras que atendam às suas necessidades de negócios  
  
    2.  Para adicionar o primeiro Branch para um estágio, adicione um bloco de estágio no caminho "Sim" do bloco de condição  
  
    3.  Para adicionar a segunda ramificação que é executada quando a condição não é satisfeita, adicione outro bloco de estágio no caminho "não" do bloco de condição  
  
> [!TIP]
>  Você pode adicionar outra condição no caminho "não" de um bloco de condição existente para criar uma ramificação mais complexa.  
  
 ![Imagem mostrando o estágio de qualificação criado](media/example-car-sales-qualify-stage.JPG "Imagem mostrando o estágio de qualificação criado")  
  
 Se a **preferência de carro** = **nova**, o processo se ramifica para o novo estágio de **vendas do carro** , caso contrário, ele salta para o estágio de vendas de **carros de propriedade** , na segunda ramificação, conforme mostrado abaixo.  
  
 ![Imagem mostrando o novo estágio de venda do carro](media/example-car-sales-new-stage-1.JPG "Imagem mostrando o novo estágio de venda do carro")  
  
 ![Estágio&#45;de vendas de carro de propriedade](media/example-car-sales-pre-owned-stage.JPG "Estágio de vendas de carro de propriedade")  
  
 Depois de concluir todas as etapas no **novo** estágio de vendas do carro ou no estágio de **vendas do carro de propriedade** , o processo retorna ao fluxo principal, com o estágio **entregar citação** .  
  
 ![Estágio entregar cotação](media/example-car-sales-deliver-quote-stage.JPG "Estágio entregar cotação")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Impedir a divulgação de informações  
 Considere um fluxo de processos de negócios com ramificações para processar uma solicitação de empréstimo em um banco, conforme mostrado abaixo. As entidades personalizadas usadas nos estágios são mostradas entre parênteses.  
  
 ![Fluxograma mostrando as etapas em um processo de exemplo para impedir a divulgação de informações](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Fluxograma mostrando as etapas em um processo de exemplo para impedir a divulgação de informações")  
  
 Nesse cenário, o responsável pelo empréstimo bancário precisa acessar o registro da solicitação, mas o responsável pelo empréstimo não deve ter nenhuma visibilidade da investigação da solicitação. À primeira vista, parece que podemos fazer isso facilmente atribuindo ao responsável pelo empréstimo uma função de segurança que não especifica nenhum acesso à entidade de investigação. Mas vamos examinar o exemplo mais detalhadamente e ver se isso é realmente verdadeiro.  
  
 Digamos que um cliente coloque a solicitação de empréstimo por mais de $60000 para o banco. O responsável pelo empréstimo revisa a solicitação no primeiro estágio. Se a regra de ramificação que verifica se o valor devido ao banco excederá $50000 é satisfeita, o próximo estágio do processo é investigar se a solicitação é fraudulenta. Se for determinado que esse é realmente um caso de fraude, o processo passará para realizar uma ação legal no solicitante. O responsável pelo empréstimo não deve ter visibilidade dos dois estágios investigativos, pois o responsável não tem acesso à entidade de investigação.  
  
 No entanto, se o analista de empréstimos abrir o registro de solicitação, tudo poderá ver todo o processo de ponta a ponta. O diretor de empréstimos não será capaz de ver o estágio de investigação de fraude, mas também poderá identificar o resultado da investigação, tendo conseguido ver o estágio de ação legal no processo. Além disso, o responsável poderá visualizar as etapas nos estágios investigativos escolhendo o estágio. Embora o analista de empréstimos não consiga ver os dados ou o status de conclusão da etapa, ela poderá identificar as ações em potencial que foram tomadas em relação ao emissor da solicitação durante os estágios de investigação e ação legal.  
  
 Nesse fluxo de processo, o analista de empréstimos poderá ver os estágios de investigação de fraude e ação legal, que constitui uma divulgação inadequada de informações. É recomendável prestar atenção especial às informações que podem se tornar divulgadas devido à ramificação. Em nosso exemplo, divida o processo em dois processos separados, um para o processamento de solicitação e outro para a investigação de fraude, para evitar a divulgação de informações. O processo para o responsável pelo empréstimo terá a seguinte aparência:  
  
 ![Fluxograma mostrando etapas adicionais no processo para impedir a divulgação de informações](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Fluxograma mostrando etapas adicionais no processo para impedir a divulgação de informações")  
  
 O processo para a investigação será independente e incluirá os seguintes estágios:  
  
 ![Fluxograma mostrando as etapas para um processo de investigação para casos de divulgação de informações](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Fluxograma mostrando as etapas para um processo de investigação para casos de divulgação de informações")  
  
 Você precisará fornecer um fluxo de trabalho para sincronizar a decisão aprovar/negar do registro de investigação para o registro de solicitação.  
  
### <a name="next-steps"></a>Próximas etapas  
 [Criar um  de fluxo de processo de negócios](create-business-process-flow.md)  
 [Criar lógica de negócios personalizada com processos](guide-staff-through-common-tasks-processes.md)   
 
