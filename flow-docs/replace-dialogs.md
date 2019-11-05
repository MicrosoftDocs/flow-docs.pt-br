---
title: Substituir caixas de diálogo por fluxos de processo de negócios ou aplicativos de tela | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a7e8bac3c33fa5bb8cfb0501b981af65115036ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548805"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Substituir caixas de diálogo por fluxos de processo de negócios ou aplicativos de tela
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

As [caixas de diálogo são preteridas](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated)e devem ser substituídas por aplicativos de tela ou fluxos de processo de negócios. Este tópico descreve os diferentes recursos dessas opções, bem como situações em que um aplicativo de tela ou de fluxo de processo empresarial inserido em um formulário controlado por modelos pode ser usado para substituir uma caixa de diálogo existente.

## <a name="feature-capability-comparison"></a>Comparação de capacidade de recurso

Esta tabela lista o conjunto de recursos de caixa de diálogo e os recursos equivalentes nos fluxos de processo de negócios e aplicativos de tela.


|Funcionalidade de diálogo  | O recurso nos fluxos de processos empresariais?  | Funcionalidade em aplicativos de tela?  |
|---------|---------|---------|
|Web     | Ok <br/> (estágio do processo de negócios)    | Ok <br/> (tela do aplicativo)        |
|Somente prompt   |  Não    |  Ok <br/> las        |
|Prompt e resposta     |  Ok <br/> (somente atributos de entidade)    | Ok <br/> (rótulos e campos de entrada)    |
|Argumentos de entrada     |  Certo <br/> (etapas no estágio do processo comercial)    | Ok <br/> (parâmetros de cadeia de caracteres de consulta)     |
|As   |  Não     |  Ok       |
|Variáveis de consulta    |  Não     |  Ok     |
|Lógica de ramificação condicional    |  Ok     | Ok <br/>  (navegar para qualquer tela no aplicativo)    |
|Posterior <br/> (iniciar como uma caixa de diálogo filho)   |  Não     | Ok <br/> (navegue até qualquer tela no aplicativo, inicie um aplicativo diferente em uma nova janela)     |
|Executar fluxos de trabalho no início/fim    |   Ok      |  Não <br/> (em vez disso, use um fluxo)  |
|Executar fluxos de trabalho na entrada    | Ok    | Não <br/> (em vez disso, use um fluxo)   |
|Executar fluxos de trabalho na transição de página   |  Ok       | Não <br/> (em vez disso, use um fluxo)    |
|Começar a usar uma URL  |   Não      |  Ok     |
|Log de sessão    |  Ok       |  Não     |
|Suporte a SDK   |  Ok     |  Ok     |

### <a name="additional-capabilities-with-business-process-flows"></a>Recursos adicionais com fluxos de processo de negócios
- Análise de processo (exibições, gráficos e tempo gasto em um estágio)
- Controles personalizados

### <a name="additional-capabilities-with-canvas-apps"></a>Recursos adicionais com aplicativos de tela
- Análise de aplicativo (uso do aplicativo & desempenho)
- Composição de página de várias entidades
- Fluxos de execução
- Conectores de dados (padrão e personalizado)
- Iniciar como um aplicativo autônomo
- Layout configurável

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Escolhendo entre um aplicativo de tela ou fluxo de processo de negócios
Quando você escolhe a substituição da caixa de diálogo, é importante considerar a experiência do usuário que deseja entregar. Lembre-se também de que quase qualquer caixa de diálogo pode ser modelada usando um aplicativo de tela.

Os fluxos de processos de negócios são mais adequados para substituir caixas de diálogo que modelam processos que fornecem orientação em um workstream abrangente que exige a colaboração entre grupos de indivíduos e o contexto de aplicativo do Dynamics 365. Por exemplo, revisão e roteamento de cotação. 

Como alternativa, os aplicativos de tela podem ser usados para substituir caixas de diálogo que modelam tarefas prescritivas, como um script de chamada para clientes potenciais potenciais ou para simplificar a experiência do usuário para outras tarefas, como a atualização de uma oportunidade. Observe que esses cenários podem até mesmo se beneficiar de ter um aplicativo de tela autônomo. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Substituição da caixa de diálogo usando cenário de fluxo de processo de negócios
Imagine que você tenha uma caixa de diálogo que, em uma série de páginas, solicite informações importantes do usuário, gere uma cotação, envie um email para os revisores para aceitar ou rejeitar a cotação, antes de enviá-la por email para o cliente. Esse tipo de processo é modelado com mais eficiência usando um fluxo de processo de negócios. 

Para substituir a caixa de diálogo, você começa identificando os estágios principais do processo. Eles podem incluir um estágio de *preparação de conteúdo* para garantir que todos os produtos sejam listados e os descontos sejam aplicados, um estágio *gerar cotação* para criar a cotação e examiná-lo quanto à precisão do formato, um estágio de *revisão principal* para o qual enviar a cotação revisão e aprovação, um estágio de *revisão secundário* para examinar a cotação em determinadas circunstâncias e, finalmente, um estágio *entregar cotação* para enviar a cotação ao cliente.

Em seguida, identifique as principais etapas que os usuários devem seguir no processo. Por exemplo, o estágio de *preparação de conteúdo* pode conter uma simples etapa verdadeiro ou falso para que o usuário Verifique os produtos entre aspas, uma etapa de pesquisa obrigatória para selecionar uma lista de preços e uma etapa numérica para inserir um desconto antes de passar para o próximo estágio. O estágio *gerar cotação* pode ter uma [etapa de ação](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) para criar uma cotação com base em todas as informações previamente capturadas no estágio *preparar conteúdo* e seu registro do Dynamics 365 relacionado. Os estágios de análise *primária* e de *revisão secundária* podem ter várias etapas verdadeiro ou falso para guiar a revisão da cotação, juntamente com uma etapa necessária para capturar o status de aprovação e garantir que o processo só possa ser movido para o próximo estágio quando a aprovação for recepção. Configure a [segurança em nível de campo](/customer-engagement/admin/field-level-security) nesta etapa para garantir que apenas os revisores autorizados possam fornecer aprovação na cotação.  Além disso, é possível adicionar um fluxo de trabalho aos estágios *principal de revisão* e de *revisão secundária* , de modo que, ao inserir, uma notificação por email seja enviada a todos os revisores. 

Por fim, configure as etapas e os estágios do fluxo do processo de negócios, juntamente com a lógica condicional para guiar o fluxo do processo. Para este exemplo, você pode adicionar uma [ramificação condicional](enhance-business-process-flows-branching.md) após o estágio de *revisão principal* , de modo que, se uma etapa indicar a necessidade de um segundo nível de revisão, o próximo estágio no processo será o estágio de *análise secundário* , caso contrário, será o  *Estágio entregar cotação* .

Para disponibilizar esse fluxo de processo comercial para os usuários, verifique se os usuários certos têm privilégios para o fluxo do processo de negócios e, em seguida, ative-o.

Para obter mais informações sobre como criar um fluxo de processo de negócios, consulte [tutorial: criar um fluxo de processo de negócios para padronizar processos](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Substituição da caixa de diálogo usando o cenário do aplicativo de tela

Suponha que você tenha uma caixa de diálogo, que segue um script de chamada que orienta os representantes de vendas por meio dos clientes potenciais de chamada a frio. Esse processo pode ser facilmente capturado usando um aplicativo de tela.

Comece com a conexão às fontes de dados que você precisará para ler e gravar dados. Neste exemplo, uma [conexão com o Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) é usada para informações de cliente potencial, conta e contato.

Comece identificando o número de telas necessárias. Para este exemplo, você pode optar por ter cinco telas. 
-   Tela 1. Para selecionar um cliente potencial de uma lista a ser chamada.
-   Tela 2. Para introduções, verificação de disponibilidade de uma conversa e agendamento de um retorno de chamada em uma data posterior. 
-   Tela 3. Para determinar BANT (orçamento, autoridade, necessidade e linha do tempo). 
-   Tela 4. Para capturar próximas etapas e agendar chamadas de acompanhamento. 
-   Tela 5. Agradecemos o Lead pelo seu tempo no final da chamada.

Em seguida, compile cada tela. Na primeira tela, [crie uma galeria](/powerapps/maker/canvas-apps/customize-layout-sharepoint) de leads que precisam ser chamados. No segundo, use rótulos para o título da tela e forneça o script de chamada, enquanto usa controles como botões de opção para capturar se é um bom momento para a pessoa falar. Se for, use a lógica condicional para habilitar um botão para navegar para a próxima tela e, se não, revelar um script na mesma tela para tentar agendar uma chamada de volta com o cliente. Da mesma forma, defina o script de chamada nas telas subsequentes.

Por fim, [defina a navegação entre as telas](/powerapps/maker/canvas-apps/functions/function-navigate). Neste exemplo, além de navegar pelas telas sequencialmente, talvez você queira navegar pelo usuário da segunda tela até a última tela (o final do script, agradecendo o Lead por seu tempo) se o cliente potencial não estiver interessado em ter uma conversa.

Para disponibilizar esse aplicativo para os usuários, publique o aplicativo. Considere como esse cenário pode ser transformado por meio da disponibilidade de um aplicativo autônomo que fornece scripts de chamada e dá suporte à entrada rápida de dados.

Imagine que você deseja inserir essa experiência em vendas do Dynamics 365. Para fazer isso, comece com a criação de um iframe em um formulário de vendas do Dynamics 365. Em seguida, navegue até a seção **aplicativos** no menu do PowerApps, selecione o aplicativo que você acabou de publicar, copie o link da Web na guia **detalhes** e cole-o como a URL para o iframe. 

Dando um passo adiante, suponha que você queira que esse aplicativo esteja disponível no formulário principal do Lead e esteja no contexto do cliente potencial para que o aplicativo não exija que o usuário selecione um cliente potencial na primeira tela. Para passar informações relevantes para o aplicativo, basta modificar a URL do iframe para acrescentar uma cadeia de caracteres de consulta que contém essas informações, como IDs de conta ou cliente potencial, usando JavaScript que é executado em um determinado evento, como na carga do formulário. Em seguida, atualize o aplicativo para remover a primeira tela (para seleção de Lead) e, em vez disso, acesse os valores passados para o aplicativo por meio da cadeia de caracteres de consulta usando a [função param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>FAQ de substituição da caixa de diálogo

As dependências em aplicativos de tela são rastreadas? 
- As dependências em aplicativos de tela são controladas da mesma forma que as dependências nos aplicativos Dynamics 365.

Posso iniciar um aplicativo de tela como um pop-up de um botão na barra de comandos?
- Ok. Para fazer isso, basta definir a URL de destino para o seu aplicativo de tela, obtido na seção **detalhes** do aplicativo, conforme descrito anteriormente.

Os fluxos de trabalho podem ser chamados de um aplicativo de tela?
- Não há suporte para isso. É recomendável usar um fluxo em vez disso. Mais informações: [introdução aos fluxos de botão com entrada do usuário](button-flow-with-user-input-tokens.md)

Posso converter caixas de diálogo para aplicativos de tela ou fluxos de processos de negócios automaticamente?
- Não há maneira automatizada de converter caixas de diálogo para fluxos de processo de negócios ou aplicativos de tela.


## <a name="see-also"></a>Consulte também
[Tutorial: criar um fluxo de processo comercial para padronizar processos](create-business-process-flow.md) </br>
[O que são aplicativos de tela no PowerApps?](/powerapps/maker/canvas-apps/getting-started)


