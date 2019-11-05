---
title: Substituir fluxos de trabalho de Common Data Service clássicas por Microsoft Flow | Microsoft Docs
description: Descreve Microsoft Flow recursos e padrões recomendados para usar o Flow em vez de um fluxo de trabalho clássico.
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
ms.service: flow
ms.topic: article
ms.date: 08/27/2019
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3c824f726df991aba9aa1290eb117cf87113041a
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548520"
---
# <a name="replace-classic-common-data-service-workflows-with-flows"></a>Substituir fluxos de trabalho de Common Data Service clássicas por fluxos
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este tópico compara Microsoft Flow recursos com o fluxo de trabalho clássico.

Microsoft Flow tem vantagens significativas em relação ao modelo de fluxo de trabalho clássico; Você deve considerar o uso de Microsoft Flow para automatizar seus processos em vez de um fluxo de trabalho clássico. 

Crie fluxos em vez de fluxos de trabalho clássicos Common Data Service para criar novos processos de automação. Além disso, você deve revisar os processos de fluxo de trabalho clássicos existentes e considerar substituí-los por fluxos.

## <a name="feature-capability-comparison"></a>Comparação de capacidade de recurso

Esta tabela resume uma comparação entre Microsoft Flow e recursos de fluxos de trabalho clássicos. 

*Estamos continuamente adicionando novos recursos para Microsoft Flow, de modo que ele esteja em par e ainda melhor do que os recursos de fluxo de trabalho clássicos. Atualizaremos as informações desta tabela à medida que Microsoft Flow Obtém recursos; Volte a verificar com frequência! Para obter informações sobre recursos de fluxo futuros que ajudarão você a substituir o fluxo de trabalho clássico pelo Flow, consulte [novidades e planos planejados para Microsoft Flow](https://docs.microsoft.com/business-applications-release-notes/April19/microsoft-flow/planned-features) nas notas de versão de abril de 2019!*

<table>
<tr>
<th colspan="2">Recursos</th>
<th>Microsoft Flow</th>
<th>Fluxo de trabalho clássico</th>
</tr>
<tr>
<td rowspan="5">Mode</td>
<td>Ramificação condicional</td>
<td>Ok</td>
<td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Loop
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Não
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Condições de espera em campos
                    
                </td>
                <td>
                    
   Não
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Ramificação paralela
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Não
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Conectores prontos para uso para sistemas externos (gatilho e execução de ações em serviços externos)
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Não
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Composição
                    
                </td>
                <td>
                    
   Conteúdo dinâmico
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Acesso à pré-imagem de dados de evento
                    
                </td>
                <td>
                    
   Não
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar fluxos de trabalho filho
                    
                </td>
                <td>
                    
   Não
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar Common Data Service ações (incluindo as personalizadas)
                    
                </td>
                <td>
                    
   Não
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar atividades de fluxo de trabalho personalizadas
                    
                </td>
                <td>
                    
   Não
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Agrupar etapas para executar em uma transação
                    
                </td>
                <td>
                    
   Sim (conjuntos de alterações)
                    
                </td>
                <td>
                    
   Não
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Fluxos de trabalho de aprovação
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Não
                    
                </td>
            </tr>
            <tr>
                <td rowspan="7">
                    
   Chão
                    
                </td>
                <td>
                    
   Disparar em alterações de campo
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Disparar condicionalmente em valores de campo (por exemplo, em uma determinada data em um campo de data)
                    
                </td>
                <td>
                    
   Não
                    
                </td>
                <td>
                    
   Não
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Disparar em vários eventos de entidade de Common Data Service
                    
                </td>
                <td>
                    
   Não
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar sob demanda
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
       de escopos de execução como<br/>
   (por exemplo, organização, unidade de negócios, usuário)
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar em uma agenda
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Não
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar de forma síncrona (em tempo real)
                    
                </td>
                <td>
                    
   Não
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td rowspan="2">
                    
   Cliques
                    
                </td>
                <td>
                    
   Auditoria
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Executar análise
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Não
                    
                </td>
            </tr>
            <tr>
                <td rowspan="3">
                    
   Criação e portabilidade
                    
                </td>
                <td>
                    
   Suporte da solução
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
            </tr>
            <tr>
                <td>
                    
   Designer moderno
                    
                </td>
                <td>
                    
   Ok
                    
                </td>
                <td>
                    
   Não
                    
                </td>
            </tr>
            <tr>
<td>Criação assistida de ia</td>
<td>Ok</td>
<td>Não</td>
</tr>
</table>

## <a name="example-scenario-replace-workflow-with-a-flow"></a>Cenário de exemplo: substituir o fluxo de trabalho por um fluxo

Imagine um cenário de vendas em que você reuniu uma cotação para um cliente e agora precisa solicitar aprovação de sua equipe de gerenciamento antes de enviar a cotação para o cliente. Com os fluxos de trabalho clássicos, isso não seria fácil e a maioria das soluções para isso requer que um desenvolvedor grave atividades de fluxo de trabalho personalizadas para recuperar itens de linha de cotação.

Com os fluxos, isso é mais fácil de criar, conforme demonstrado no Walkthrough, mais tarde, que aborda alguns dos recursos de Microsoft Flow para dar suporte ao cenário. Isso inclui:

-   Criando um fluxo que é executado sob demanda

-   Obtendo uma lista de registros relacionados a uma entidade Common Data Service

-   Loop em uma lista de registros

-   Enviando solicitações de aprovação

Para permitir que o vendedor de vendas dispare a solicitação de aprovação sob demanda:

1. Entre no [Microsoft Flow](https://flow.microsoft.com/) e crie um fluxo em uma solução. Mais informações: [criar um fluxo em uma solução](create-flow-solution.md). 

1. Na lista de gatilhos, selecione **Common Data Service (ambiente atual) – quando um registro é selecionado** e selecione **aspas** como a entidade. Esse gatilho permite que um fluxo seja executado sob demanda em um registro ou lista de registros.

1. Com o gatilho configurado, adicione ações a serem executadas em nosso fluxo. Isso fornecerá ao aprovador os detalhes de Resumo de que eles precisam para identificar os itens e valores entre aspas. Comece adicionando o **Common Data Service (ambiente atual) –** ação de registros de lista. Como queremos obter itens de linha individuais de uma cotação, defina a entidade para **linhas de cotação**. Para garantir que listamos apenas os itens de linha de cotação que pertencem à cotação para a qual o fluxo foi disparado, especificaremos um critério de filtro de estilo OData. No campo **consulta de filtro** , digite *\_quoteid_value EQ* e selecione *aspas* na lista de valores dinâmicos que aparecem.

    ![Definir seu fluxo](media/define-flow-1.png "Definir seu fluxo")

1. Como desejamos resumir itens de linha de cotação para a aprovação, adicione a ação **inicializar variável** . Defina o campo **nome** como *Resumo da linha da cotação* e o **tipo** como cadeia de caracteres (na lista suspensa) e deixe o campo **valor** vazio.

1. Adicione a ação **acrescentar à variável de cadeia de caracteres** e selecione a variável de Resumo de linha de *cotação* criada anteriormente. No campo **valor** , selecione *quantidade, nome, preço por unidade, valor estendido e valor manual* na lista de valores dinâmicos. O designer de Microsoft Flow identifica que esses valores são de uma lista de itens de linha de cotação e adiciona essa ação em um loop **aplicar a cada** para garantir que as informações de cada item de linha sejam adicionadas a esse Resumo.

    ![Definir seu fluxo](media/define-flow-2.png "Definir seu fluxo")

1. Para solicitar aprovação no resumo da cotação que criamos, adicione a **aprovação – iniciar e aguardar uma ação de aprovação** . Selecione um tipo de aprovação (por exemplo, aprovar/rejeitar – primeiro para responder), dê um **título** à solicitação de aprovação (por exemplo, o nome da cotação para a qual a aprovação está sendo solicitada, selecionada na lista de valores dinâmicos), insira o endereço de email para o pessoa que precisa revisar e aprovar a cotação no campo **atribuído a** . No campo detalhes, adicione a variável de *Resumo da linha de cotação* , juntamente com outras informações que podem ser relevantes usando o seletor de valor dinâmico (por exemplo, valor total).

1. Para determinar o que acontece quando uma aprovação é aceita ou rejeitada, adicione a ação de **condição** . Selecione *resultado* na lista de valores dinâmicos do primeiro campo na condição, *contenha* do menu suspenso no segundo campo e digite *Accept* no terceiro campo da condição. Por fim, adicione ações com base no resultado da aprovação (por exemplo, enviar um email de notificação).

    ![Definir seu fluxo](media/define-flow-3.png "Definir seu fluxo")

Agora temos a estrutura de aprovação criada para que o aprovador tenha todas as informações necessárias para tomar uma decisão sobre as próximas etapas. Aqui está o fluxo de exemplo completo sob demanda para solicitar aprovação:

![Estrutura de fluxo de aprovação](media/approval-flow-structure.png "Estrutura de fluxo de aprovação")

Quando você executa esse fluxo em sua cotação, ele resume os itens de linha de cotação para essa cotação e envia uma solicitação de aprovação que o aprovador pode responder de Microsoft Flow ou o email acionável que recebe. Veja abaixo um exemplo da exibição:

![Fluxo em ação](media/flow-in-action.png "Fluxo em ação")

## <a name="recommended-patterns"></a>Padrões recomendados


-   **Fluxos de trabalho com lógica condicional else-if complexa**  
    
    Em vez de usar condições, é recomendável usar a [ação switch](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-switch-statement#add-switch-statement) .

-   **Fluxos de trabalho que são executados do plug-in/código**  
    
    É recomendável recriar o fluxo para começar com gatilhos.

    -   Use Common Data Service gatilhos para executar fluxos com base em eventos.

    -   Para executar fluxos com base em eventos em um serviço externo, utilize mais de 260 conectores prontos para uso.

    -   Para cenários em que um conector de que você precisa não está disponível pronta para uso, crie facilmente seu próprio conector personalizado [Aprenda a criar conectores personalizados](https://docs.microsoft.com/connectors/custom-connectors/define-blank).

    -   Por fim, se houver cenários em que você não pode disparar o fluxo usando Common Data Service Connector, um dos conectores prontos para uso ou criar um conector personalizado, aproveite o [gatilho quando um pedido http é recebido](https://docs.microsoft.com/azure/connectors/connectors-native-reqres#use-the-http-request-trigger) para invocar o fluxo

-   **Fluxos de trabalho que são executados recursivamente**  
    
    Use o loop do [-until](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#until-loop) ou [aplicar a cada](https://docs.microsoft.com/azure/logic-apps/logic-apps-control-flow-loops#foreach-loop) em fluxos em vez disso

-   **Fluxos de trabalho que precisam de uma lista de registros**  
    
    Use a ação **listar registros** . Ao usar essa ação, defina os critérios de filtragem de registros usando a sintaxe do OData para otimizar a ação, minimizando o número de registros que você deseja recuperar.

-   **Fluxos de trabalho que estão em suspensão para serem executados em um agendamento**  
    
    Use o gatilho de **recorrência** para executar a lógica de negócios em intervalos periódicos.

-   **Fluxos de trabalho para os quais as execuções foram gerenciadas para garantir que as atividades fossem executadas em uma única transação**  
    
    [Use a [ação do conjunto de alterações](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/automated-flows-support-change-sets-common-data-service) para garantir que todas as ações dentro dela sejam executadas como uma única unidade atômica, na qual todas elas tenham êxito ou falhem como um grupo. Se qualquer uma das ações em um conjunto de alterações falhar, as alterações feitas por operações concluídas serão revertidas.

-   **Monitorar execuções de fluxo de trabalho para falhas**  
    
    Em Microsoft Flow, use a **configuração executar-após** em uma ação para configurá-la para ser executada quando a ação anterior falhar. Por exemplo, envie um Microsoft Flow notificação móvel quando a ação **atualizar um registro** falhar ou atingir o tempo limite.

## <a name="faqs"></a>FAQs


-   **Tenho uma licença do Dynamics 365. Posso usar Microsoft Flow?**

    Todos os usuários do Dynamics 365 têm o direito de usar Microsoft Flow. Examine nossas informações de licenciamento: <https://flow.microsoft.com/pricing/>

-   **Com que frequência meus fluxos podem ser disparados?**

    -   Fluxos do Dynamics 365 (ou Common Data Service) são executados quase em tempo real após o gatilho porque usam WebHooks (sem necessidade de sondagem)

    -   Assim como acontece com o acesso direto à API, há restrições/limites no sistema, totalmente documentados aqui: <https://docs.microsoft.com/flow/limits-and-config>

    -   Especificamente, há um limite de 100 mil ações por 5 minutos, por fluxo, e um único loop em um fluxo não pode processar mais de 100 mil itens ao mesmo tempo

    -   Máximo de 6 GB de taxa de transferência por 5 minutos

-   **Por quanto tempo um único fluxo pode ser executado?**  
    
    Uma execução de fluxo único atinge o tempo limite após 30 dias.

-   **Como fazer mover meus fluxos entre ambientes?**  
    
    Assim como os fluxos de trabalho clássicos, você pode criar fluxos em soluções para dar suporte ao ciclo de vida completo do aplicativo para processos.

-   **As dependências Microsoft Flow são controladas no Common Data Service?**  
    
    Semelhante a outros componentes em uma solução, todas as dependências para fluxos em soluções são controladas no Common Data Service.

-   **E quanto aos fluxos de trabalho síncronos?** 
 
    Você deve reavaliar a necessidade de fluxos de trabalho síncronos para identificar se o objetivo ou partes do fluxo de trabalho podem ser criados usando um fluxo. Em particular, vemos de nossa telemetria que os fluxos de trabalho síncronos são um colaborador significativo da experiência geral de desempenho ruim do usuário final. Para muitos usos, embora seja preferível dividir essas ações como assíncronas para que o usuário possa continuar com sua atividade enquanto Microsoft Flow continua a garantir a conclusão da ação.

-   **Usando Microsoft Flow, meus dados permanecerão dentro da região (ou seja, a mesma região que o meu ambiente do Dynamics 365 ou Common Data Service)?**  
    
    Sim, Microsoft Flow sempre usa a mesma região que Common Data Service.

-   **É necessário fazer alterações de proxy/firewall?**  
    
    Consulte a [referência de configuração de endereço IP](limits-and-config.md#ip-address-configuration) para determinar se você precisa fazer alterações de proxy/firewall.
