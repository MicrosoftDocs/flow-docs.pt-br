---
title: Práticas recomendadas para usar atributos de entidade do fluxo de processo de negócios | MicrosoftDocs
description: Conheça as práticas recomendadas para usar atributos de entidade do fluxo de processo de negócios.
ms.custom: ''
ms.date: 04/23/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Business Process Flows
helpviewer_keywords:
- flow
- process flow
- business process flow
- process
- workflow
author: msftman
ms.author: deonhe
manager: kvivek
ms.openlocfilehash: b46eac7317db8f5b63ebcd7b8b1fe8c79109bc11
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545275"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Práticas recomendadas no uso de atributos de fluxo de processo de negócios
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]


Os atributos herdados relacionados ao processo em entidades são preteridos. Aqui estão algumas práticas recomendadas para usar o atributo de *estágio ativo* (activestageid) na entidade de fluxo do processo de negócios. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Relatórios sobre o estágio ativo de um fluxo de processo de negócios

Digamos que você queira obter uma exibição do pipeline de vendas relatando no estágio ativo que o processo de vendas do **cliente potencial para a oportunidade** está.

Anteriormente, para relatar processos de negócios por etapa, é possível definir uma exibição em cada entidade relacionada do fluxo do processo de negócios e, em seguida, reportar o campo *estágio ativo* (activestageid).

Com a substituição do campo *estágio ativo* (activestageid) em entidades relacionadas, há duas maneiras de relatar fluxos de processos empresariais.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Opção 1: exibições e gráficos na entidade de fluxo do processo de negócios **(recomendado)**

Nas versões 9,0 e superiores, cada fluxo de processo de negócios cria sua própria entidade Common Data Service, geralmente com o mesmo nome que o fluxo do processo comercial. Para relatar o fluxo do processo de negócios, selecione a entidade para o fluxo do processo de negócios que você deseja relatar e, em seguida, crie exibições e gráficos, da mesma forma que antes.

Em nosso exemplo, siga estas etapas para ir para a entidade do **processo de vendas do cliente potencial para a oportunidade** :
1. Vá para https://web.powerapps.com.
1. Selecione os **dados**.
1. Selecione as **entidades**.
1. Defina o filtro como **todos**.
1. Pesquise e selecione a entidade processo de **vendas de cliente potencial para oportunidade** .

   ![entidade do processo de vendas de cliente potencial para oportunidade](media/best-practices-entity-attributes/lead-opportunity-process.png)

Aqui, você pode definir exibições e gráficos da mesma forma como faria em qualquer outra entidade.

![detalhes da entidade processo de tradução](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

Uma vantagem dessa abordagem é que você pode usar um único modo de exibição ou gráfico para relatar fluxos de processo de negócios que abrangem várias entidades.

Além disso, como a entidade de fluxo do processo de negócios não é diferente de qualquer outra entidade personalizada no Common Data Service, você pode adicionar campos personalizados à entidade para acompanhar quaisquer informações adicionais necessárias.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Opção 2: copiar o estágio ativo para uma entidade relacionada

Como alternativa, para continuar relatando a entidade relacionada, crie um fluxo para copiar o campo de *estágio ativo* (activestageid) da entidade de fluxo do processo de negócios para um campo personalizado nas entidades de Common Data Service relacionadas.

Aqui estão algumas coisas para ter em mente quando você usa essa abordagem:

1.  É possível ter mais de um fluxo de processo de negócios em execução em uma única entidade. Com essa abordagem, é melhor ter um campo personalizado que armazene o estágio ativo para cada fluxo de processo de negócios executado na entidade. Essa abordagem garante a integridade do relatório.

1.  Como a geração de relatórios é controlada da entidade relacionada, não é possível criar uma única exibição que relate os fluxos de processos empresariais que abrangem várias entidades.

## <a name="using-the-active-stage-to-run-logic"></a>Usando o estágio ativo para executar a lógica

Aqui estão alguns casos em que você pode querer executar a lógica com base no estágio ativo:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Usando o estágio ativo para executar a lógica do lado do cliente

Conforme você usa o processo de negócios, há muitas coisas que você pode querer fazer automaticamente. Por exemplo:

-   Altere o fluxo do processo comercial ativo com base em informações recentemente disponíveis sobre o fluxo do processo de negócios ou formulário.

-   Mova o estágio ativo para o estágio seguinte ou anterior, com base nos valores inseridos pelos usuários para etapas ou campos de formulário.

-   Ocultar ou mostrar guias de formulário e campos com base no estágio selecionado.

-   Mostrar mensagens informativas e executar o calulations com base nos fluxos de processos de negócios ativos, no estágio ativo ou selecionado, ou em eventos como mover o estágio ativo.

> [!TIP]
> Para cenários como esses, use o conjunto de [APIs de cliente](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) com suporte para fluxos de processo de negócios.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Usando o estágio ativo para executar a lógica do lado do servidor

Pode haver casos em que a automação baseada no fluxo do processo de negócios precisa ser feita no lado do servidor. Por exemplo:

-   Envie um email para um usuário se a **qualificação** do estágio do **processo de vendas da oportunidade** estiver ativa por mais de 15 dias.

-   Crie automaticamente um conjunto de atividades relevantes para o estágio ativo do **processo de vendas da oportunidade** sempre que ele for alterado.

-   Conclua automaticamente o **processo de vendas da oportunidade** quando a atividade de chamada telefônica para fechamento for concluída.

> [!TIP]
> Use fluxos de trabalho do Common Data Service clássico ou fluxos que você define na entidade para o fluxo do processo empresarial.
> 

Para criar um fluxo de trabalho de Common Data Service clássico que cria atividades para análises de soluções internas e para acompanhar o cliente no estágio de **proposta** do **processo de vendas da oportunidade**:

1. Crie-o na entidade **processo de vendas da oportunidade** e defina-o para ser executado sempre que o campo **estágio ativo** da entidade for alterado. 
1. Defina uma condição para verificar se o campo **ativo de estágio** é igual a **propor**. 
1. Crie um registro de telefonema e telefonema para a revisão interna da solução e a chamada do cliente para examinar a solução, respectivamente.

   ![fechar acompanhamento do estágio](media/best-practices-entity-attributes/close-stage-followup.png)
