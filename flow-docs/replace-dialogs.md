---
title: Substituir caixas de diálogo por fluxos de processos empresariais ou aplicativos de tela | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 498efb98a4c89ca6c2a01e345f5593beae4dbcca
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462991"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Substituir caixas de diálogo por fluxos de processos empresariais ou aplicativos de tela

As [caixas de diálogo estão preteridas](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated) e devem ser substituídas por fluxos de processos empresariais ou aplicativos de tela. Este tópico descreve diferentes recursos dessas opções, assim como situações em que um fluxo de processo empresarial ou aplicativo de tela inserido em um formulário orientado a modelos pode ser usado para substituir uma caixa de diálogo existente.

## <a name="feature-capability-comparison"></a>Comparação de funcionalidades de recurso

Esta tabela lista o conjunto de funcionalidades de caixa de diálogo e as funcionalidades equivalentes nos fluxos de processos empresariais e aplicativos de tela.


|Funcionalidade de caixa de diálogo  | Funcionalidade em fluxos de processos empresariais?  | Funcionalidade em aplicativos de tela?  |
|---------|---------|---------|
|Página     | Sim <br/> (estágio de processo empresarial)    | Sim <br/> (tela do aplicativo)        |
|Somente prompt   |  Não    |  Sim <br/> (rótulos)        |
|Prompt e resposta     |  Sim <br/> (somente atributos de entidade)    | Sim <br/> (rótulos e campos de entrada)    |
|Argumentos de entrada     |  Limitado <br/> (etapas no estágio do processo empresarial)    | Sim <br/> (parâmetros de cadeia de caracteres de consulta)     |
|Variáveis   |  Não     |  Sim       |
|Variáveis de consulta    |  Não     |  Sim     |
|Lógica de ramificação condicional    |  Sim     | Sim <br/>  (navegue até qualquer tela dentro do aplicativo)    |
|Reutilizar <br/> (iniciar como uma caixa de diálogo filho)   |  Não     | Sim <br/> (navegue até qualquer tela dentro do aplicativo, inicie um aplicativo diferente em uma nova janela)     |
|Executar fluxos de trabalho no início/fim    |   Sim      |  Não <br/> (use um fluxo, em vez disso)  |
|Executar fluxos de trabalho na entrada    | Sim    | Não <br/> (use um fluxo, em vez disso)   |
|Executar fluxos de trabalho na transição de página   |  Sim       | Não <br/> (use um fluxo, em vez disso)    |
|Começar a usar uma URL  |   Não      |  Sim     |
|Registro em log de sessão    |  Sim       |  Não     |
|Suporte ao SDK   |  Sim     |  Sim     |

### <a name="additional-capabilities-with-business-process-flows"></a>Outras funcionalidades com fluxos de processos empresariais
- Análise de processo (exibições, gráficos e tempo gasto em um estágio)
- Controles personalizados

### <a name="additional-capabilities-with-canvas-apps"></a>Outras funcionalidades com aplicativos de tela
- Análise do aplicativo (uso do aplicativo e desempenho)
- Composição da página de várias entidades
- Executar fluxos
- Conectores de dados (padrão e personalizados)
- Iniciar como um aplicativo autônomo
- Layout configurável

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Escolhendo entre um fluxo de processo empresarial ou um aplicativo de tela
Quando você escolhe sua substituição de caixa de diálogo, é importante considerar a experiência do usuário que você deseja entregar. Também tenha em mente que quase qualquer caixa de diálogo pode ser modelada usando um aplicativo de tela.

Os fluxos de processos empresariais são mais adequados para substituir caixas de diálogos que modelam processos que oferecem diretrizes entre um fluxo de trabalho abrangente que requer colaboração entre grupos de indivíduos e o contexto do aplicativo Dynamics 365. Por exemplo, revisão de cotação e roteamento. 

Como alternativa, os aplicativos de tela podem ser usados para substituir as caixas de diálogo que modelam tarefas prescritivas como um script de chamada para prospecção de clientes potenciais ou para simplificar a experiência do usuário para outras tarefas, como atualizar uma oportunidade. Observe que esses cenários podem até se beneficiar de um aplicativo de tela autônomo. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Substituição da caixa de diálogo usando um cenário de fluxo de processo empresarial
Imagine que você tenha uma caixa de diálogo que, ao longo de uma série de páginas, solicita informações importantes do usuário, gera uma cotação e envia um email para os revisores aceitarem ou rejeitarem a cotação antes de enviá-la por email para o cliente. Esse tipo de processo é modelado com mais eficácia usando um fluxo de processo empresarial. 

Para substituir a caixa de diálogo, comece identificando os principais estágios no processo. Eles podem incluir um estágio *Preparar conteúdo* para garantir que todos os produtos estão listados e os descontos estão aplicados, um estágio *Gerar cotação* para criar a cotação e examiná-la quanto a precisão do formato, um estágio *Revisão primária* para enviar a cotação para revisão e aprovação, um estágio *Revisão secundária* para revisar a cotação sob determinadas circunstâncias e, por fim, um estágio *Entregar cotação* para enviá-la ao cliente.

Em seguida, identifique as principais etapas que os usuários devem seguir no processo. Por exemplo, o estágio *Preparar conteúdo* pode conter uma etapa simples verdadeira ou falsa para que o usuário verifique novamente os produtos a serem cotados, uma etapa de pesquisa obrigatória para selecionar uma lista de preços e uma etapa numérica para inserir um desconto antes de passar para o próximo estágio. O estágio *Gerar cotação* pode ter uma [etapa de ação](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) para criar uma cotação com base em todas as informações capturadas anteriormente no estágio *Preparar conteúdo* e seu registro do Dynamics 365 relacionado. Os estágios *Revisão primária* e *Revisão secundária* podem ter várias etapas verdadeiras ou falsas para orientar a revisão da cotação, juntamente com uma etapa obrigatória para capturar o status de aprovação e garantir que o processo só possa ser movido para o próximo estágio após a aprovação ser recebida. Configure a [segurança de nível de campo](/customer-engagement/admin/field-level-security) nessa etapa para certificar-se de que apenas os revisores autorizados possam fornecer aprovação sobre a cotação.  Além disso, é possível adicionar um fluxo de trabalho aos estágios *Revisão primária* e *Revisão secundária*, tal que, ao entrar, uma notificação por email é enviada a todos os revisores. 

Finalmente, configure seus estágios e etapas de fluxo de processo empresarial, juntamente com a lógica condicional para orientar o fluxo de processo. Para esse exemplo, adicione um [branch condicional](enhance-business-process-flows-branching.md) após o estágio *Revisão primária*, tal que, se uma etapa indicar a necessidade de um segundo nível de revisão, o próximo estágio no processo será o estágio *Revisão secundária*, senão, será o estágio *Entregar cotação*.

Para disponibilizar esse fluxo de processo empresarial para usuários, garanta que os usuários certos têm privilégios para o fluxo de processo empresarial e, em seguida, ative-os.

Para obter mais informações sobre como criar um fluxo de processo de negócios, consulte [Tutorial: Criar um fluxo de processo empresarial para padronizar processos](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Substituição da caixa de diálogo usando o cenário de aplicativo de tela

Suponha que você tem uma caixa de diálogo, que segue um script de chamada que orienta os representantes de vendas por clientes potenciais de telemarketing. Esse processo pode ser facilmente capturado usando um aplicativo de tela.

Comece conectando-se às fontes de dados de que você precisará para ler e gravar dados. Neste exemplo, uma [conexão com o Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) é usada para obter informações do cliente potencial, da conta e do contato.

Comece identificando o número de telas necessárias. Neste exemplo, você pode decidir ter cinco telas. 
-   Tela 1. Para selecionar um cliente potencial em uma lista para chamar.
-   Tela 2. Para introduções, verificando a disponibilidade de uma conversa e o agendamento de um retorno de chamada posteriormente. 
-   Tela 3. Para determinar BANT (orçamento, autoridade, necessidade e linha do tempo). 
-   Tela 4. Para capturar as próximas etapas e agendar chamadas de acompanhamento. 
-   Tela 5. Agradecer o cliente potencial pelo tempo ao fim da chamada.

Em seguida, crie cada tela. Na primeira tela, [crie uma galeria](/powerapps/maker/canvas-apps/customize-layout-sharepoint) de clientes potenciais que precisam ser chamados. Na segunda, use rótulos para dar um título à tela e forneça o script de chamada, usando controles como botões de opção para capturar se é um bom momento para a pessoa falar. Se for, use a lógica condicional para habilitar um botão para navegar até a próxima tela; se não for, revele um script na mesma tela para tentar agendar um retorno de chamada com o cliente. Da mesma forma, defina seus scripts de chamada entre as telas subsequentes.

Por fim, [defina navegação entre telas](/powerapps/maker/canvas-apps/functions/function-navigate). Nesse exemplo, além de navegar por telas em sequência, talvez você queria que o usuário navegue da segunda tela até a última (o fim do script que agradece o cliente potencial pelo tempo) se o cliente potencial não estiver interessado em ter uma conversa.

Para disponibilizar esse aplicativo a usuários, publique o aplicativo. Considere como esse cenário pode ser transformado por meio da disponibilidade de um aplicativo autônomo que fornece scripts de chamada e dá suporte à entrada rápida de dados.

Imagine que você deseje inserir essa experiência no Dynamics 365 for Sales. Para fazer isso, comece criando um iframe em um formulário do Dynamics 365 for Sales. Em seguida, navegue até a seção **Aplicativos** no menu do PowerApps, selecione o aplicativo recém-publicado, copie o link da Web na guia **Detalhes** e cole-o como a URL do iframe. 

Indo além, suponha que você deseje que esse aplicativo fique disponível dentro do principal formulário do cliente potencial e esteja no contexto do lead para que o usuário não precise selecionar um cliente potencial na primeira tela. Para passar informações relevantes para o aplicativo, basta modificar a URL do iframe para acrescentar uma cadeia de caracteres de consulta que contém essas informações, como Ids do cliente potencial ou da conta, que usam o JavaScript executado em um determinado evento, como no carregamento do formulário. Em seguida, atualize o aplicativo para remover a primeira tela (para seleção de clientes potenciais) e, em vez disso, acesse os valores passados para o aplicativo por meio da cadeia de caracteres de consulta usando a [Função param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>Perguntas frequentes sobre substituição de caixa de diálogo

As dependências de aplicativos de tela são rastreadas? 
- As dependências de aplicativos de tela são rastreadas da mesma maneira que as dependências na participação do cliente do Dynamics 365.

Posso iniciar um aplicativo de tela como uma pop-up de um botão na barra de comandos?
- Sim. Para fazer isso, basta definir a URL de destino como a do seu aplicativo de tela, obtida da seção **Detalhes** do aplicativo, conforme descrito anteriormente.

Os fluxos de trabalho podem ser chamados de um aplicativo de tela?
- Não há suporte para isso. Em vez disso, recomenda-se usar um fluxo. Mais informações: [Introdução aos fluxos de botão com a entrada do usuário](button-flow-with-user-input-tokens.md)

Posso converter automaticamente as caixas de diálogo em fluxos de processos empresariais ou aplicativos de tela?
- Não há uma maneira automatizada de converter caixas de diálogo em fluxos de processos empresariais ou aplicativos de tela.


## <a name="see-also"></a>Consulte também
[Tutorial: Criar um fluxo de processo empresarial para padronizar processos](create-business-process-flow.md) </br>
[O que são aplicativos de tela no PowerApps?](/powerapps/maker/canvas-apps/getting-started)


