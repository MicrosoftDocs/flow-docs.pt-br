---
title: Práticas recomendadas para uso de atributos de entidade de fluxo de processo empresarial | MicrosoftDocs
description: Conheça as práticas recomendadas para uso de atributos de entidade de fluxo de processo empresarial.
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
ms.openlocfilehash: 950f03d78e708f00f28b68daf7c1012fae231c95
ms.sourcegitcommit: 2931edb777c1ed57e040670fc8a1c55252ac95b1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/25/2019
ms.locfileid: "64472962"
---
# <a name="best-practices-in-using-business-process-flow-attributes"></a>Práticas recomendadas para uso de atributos de entidade de fluxo de processo empresarial


Os atributos herdados relacionados ao processo nas entidades foi preterido. Aqui estão algumas práticas recomendadas para uso do atributo *Estágio Ativo* (activestageid), na entidade de fluxo do processo empresarial. 

## <a name="reporting-on-the-active-stage-of-a-business-process-flow"></a>Relatório sobre o estágio ativo de um fluxo de processo empresarial

Digamos que você gostaria de obter uma exibição do pipeline de vendas gerando um relatório em que o estágio **Processo de Vendas do Cliente Potencial até a Oportunidade** esteja ativo.

Anteriormente, para gerar relatórios sobre processos empresariais por estágio, era necessário definir um modo de exibição para cada entidade relacionada do fluxo de processo empresarial e, em seguida, gerar o relatório no campo *Estágio Ativo* (activestageid).

Com a substituição do campo *Estágio Ativo* (activestageid) nas entidades relacionadas, há duas maneiras de gerar relatórios nos fluxos de processo empresarial.

### <a name="option-1-views-and-charts-on-business-process-flow-entity-recommended"></a>Opção 1: modos de exibição e gráficos em entidades de fluxo de processo empresarial **(Recomendado)**

Nas versões 9.0 e posteriores, cada fluxo de processo empresarial cria a própria entidade do Common Data Service, geralmente com o mesmo nome do fluxo. Para gerar relatórios sobre o fluxo do processo empresarial, selecione a entidade do fluxo sobre o qual você deseja relatar e, em seguida, crie modos de exibição e gráficos, como fez anteriormente.

Em nosso exemplo, siga as etapas para acessar a entidade do **Processo de Vendas do Cliente Potencial até a Oportunidade**:
1. Vá para https://web.powerapps.com.
1. Selecione os **Dados**.
1. Selecione as **Entidades**.
1. Defina o filtro como **Todos**.
1. Procure e selecione a entidade do **Processo de Vendas do Cliente Potencial até a Oportunidade**.

   ![Entidade do Processo de Vendas do Cliente Potencial até a Oportunidade](media/best-practices-entity-attributes/lead-opportunity-process.png)

Aqui, você pode definir modos de exibição e gráficos, da mesma maneira que o faria em qualquer outra entidade.

![Detalhes da entidade do processo de tradução](media/best-practices-entity-attributes/lead-to-opportunity-sales-process-details.png)

A vantagem dessa abordagem é que você pode usar um único modo de exibição ou gráfico para gerar relatórios em fluxos de processos empresariais que abrangem várias entidades.

Além disso, como a entidade de fluxo de processo empresarial é igual a qualquer outra entidade personalizada no Common Data Service, você pode adicionar campos personalizados à entidade para rastrear as informações adicionais necessárias.

### <a name="option-2-copy-active-stage-to-a-related-entity"></a>Opção 2: copiar o estágio ativo para uma entidade relacionada

Como alternativa, para continuar gerando relatórios fora da entidade relacionada, crie um fluxo para copiar o campo *Estágio Ativo* (activestageid) da entidade do fluxo de processo empresarial em um campo personalizado, nas entidades relacionadas do Common Data Service.

Aqui estão algumas coisas que você deve levar em consideração ao usar esta abordagem:

1.  É possível ter mais de um fluxo de processo empresarial em execução em uma única entidade. Com esta abordagem, convém ter um campo personalizado que armazene o estágio ativo de cada fluxo de processo empresarial executado na entidade. Esta abordagem garante a integridade do relatório.

1.  Como o relatório é gerado na entidade relacionada, não é possível criar uma exibição de relatório única em fluxos de processos empresariais que abrangem várias entidades.

## <a name="using-the-active-stage-to-run-logic"></a>Como usar o estágio ativo para executar lógica

Aqui estão alguns casos em que talvez você queira executar uma lógica com base no estágio ativo:

### <a name="using-the-active-stage-to-run-client-side-logic"></a>Uso do estágio ativo para executar lógica do lado do cliente

Há várias coisas que talvez você queira fazer automaticamente quando usar o processo empresarial. Por exemplo:

-   Alterar o fluxo do processo empresarial ativo, com base em informações disponibilizadas recentemente no formulário ou no processo empresarial.

-   Mover o estágio ativo para o estágio anterior ou seguinte, com base nos valores que os usuários inseriram nas etapas ou nos campos do formulário.

-   Ocultar ou mostrar guias de formulário de acordo com o estágio selecionado.

-   Mostrar mensagens informativas e fazer cálculos com base nos fluxos de processos empresariais ativos, no estágio ativo ou selecionado, ou em eventos como mover o estágio ativo.

> [!TIP]
> Para cenários como estes, use o conjunto compatível das [APIs de cliente](https://docs.microsoft.com/dynamics365/customer-engagement/developer/clientapi/reference/formcontext-data-process) para fluxos de processos empresariais.
>

### <a name="using-the-active-stage-to-run-server-side-logic"></a>Uso do estágio ativo para executar lógica do lado do servidor

Pode haver casos em que a automação com base no fluxo do processo empresarial deve ser feita do lado do servidor. Por exemplo:

-   Enviar um email a um usuário, se o estágio **Qualificar** do **Processo de Vendas de Oportunidade** ficar ativo por mais de 15 dias.

-   Criar automaticamente um conjunto de atividades relevantes para o estágio ativo do **Processo de Vendas de Oportunidade**, sempre que houver alterações.

-   Concluir automaticamente o **Processo de Vendas de Oportunidade**, quando a atividade de telefonema para fechamento for concluída.

> [!TIP]
> Use os fluxos de trabalho clássicos do Common Data Service ou os fluxos que você definiu para o processo empresarial da entidade.
> 

Para criar um fluxo de trabalho clássico do Common Data Service que cria atividades para revisões de soluções internas, e para atender o cliente no estágio **Propor** do **Processo de Vendas de Oportunidade**:

1. Crie o fluxo de trabalho na entidade do **Processo de Vendas de Oportunidade** e defina-o para ser executado sempre que houver alterações no campo **Estágio Ativo** da entidade. 
1. Defina uma condição para verificar se o campo **Estágio Ativo** corresponde ao campo **Propor**. 
1. Crie um registro de compromisso e telefonema para a revisão interna da solução, e a chamada de cliente para revisar a solução, respectivamente.

   ![fechar acompanhamento de estágio](media/best-practices-entity-attributes/close-stage-followup.png)
