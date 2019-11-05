---
title: Notas de versão | Microsoft Docs
description: Problemas comuns e o que há de novo para as versões de Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/31/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6c414538c31aa17ed5ab6ba1498812576a8024ae
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548864"
---
# <a name="release-notes"></a>Notas de versão
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="top-questions"></a>Principais perguntas
1. Meu fluxo falhou. Como fazer corrigi-lo?
   
   1. Identifique a falha. Comece acessando o ícone de notificações na parte superior do portal da Web ou selecionando a guia **atividade** no aplicativo móvel. Você deve ver o fluxo ali e pode selecioná-lo.
   2. Agora você está examinando os detalhes do fluxo. Localize a etapa com o ícone de exclamação vermelha e você verá a mensagem de erro para o fluxo lá.
   3. Dependendo da mensagem de erro, você deve ser capaz de **Editar** o fluxo e corrigi-lo. [Leia mais sobre como corrigir falhas de fluxo comuns](fix-flow-failures.md).
2. Como fazer usar uma condição avançada ou uma expressão?
   
   * Leia sobre como [Adicionar condições](add-condition.md).
   * Se você quiser vários casos em um fluxo, selecione **Adicionar condição** de dentro de uma condição existente.
   * Crie uma expressão avançada referenciando [uma função em aplicativos lógicos](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Como funciona o licenciamento com o Office 365?
   
   * Se você for um usuário do Office 365, terá acesso completo por meio do Microsoft Flow para o plano do Office 365. Para obter mais informações, consulte os [planos de preços para Microsoft Flow](https://flow.microsoft.com/pricing/) .
   * Se você for um administrador, consulte informações sobre [Licenciamento para Microsoft Flow](organization-q-and-a.md), incluindo com o Office 365.

## <a name="known-issues"></a>Problemas conhecidos
1. As listas do SharePoint em meus sites e que não são do tipo *lista personalizada* não têm suporte. Para contornar esse problema, crie uma lista personalizada em um site padrão do SharePoint.
2. Os gatilhos de arquivo não serão acionados para arquivos que estão sendo adicionados dentro de pastas aninhadas dentro da pasta selecionada.

## <a name="whats-new"></a>O que há de novo

> [!IMPORTANT]
>
> **Anunciando as notas de versão**
>
> Está imaginando os recursos futuros e lançados recentemente no Microsoft Flow?
>[Exiba as notas de versão de outubro de 2018](https://docs.microsoft.com/business-applications-release-notes/October18/microsoft-flow/). Capturamos todos os detalhes, de ponta a ponta, de cima para baixo, que você pode usar para planejamento. Para obter mais detalhes, examine [cada versão semanal](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) com os recursos e aprimoramentos que ele contém.
>
> As notas de versão anteriores à versão de outubro de 2018 permanecerão aqui para referência futura, mas todas as novas versões só serão incluídas nos locais acima e não nesta página.

### <a name="release-2018-09-24"></a>Versão de 2018-09-24

- **Acesso de administrador a ajuda e suporte** -abra tíquetes de suporte para Microsoft Flow no centro de administração do plataforma Power e forneça detalhes adicionais sobre a falha do fluxo de trabalho.
- **Comunidade de fluxo reformulada** -encontrar o que você precisa simplesmente ficou mais fácil na Comunidade de fluxo.
- **Melhorias no Microsoft Teams Connector** – novos gatilhos para Microsoft Teams para que você possa executar um fluxo quando houver novas mensagens em um canal.
- **Mais ações do SharePoint** – há novas ações para mover arquivos e muito mais no conector do SharePoint.
- **Novos relatórios do admin Analytics** – análise ampla do ambiente e do locatário adicionados ao centro de administração da plataforma de aplicativos de negócios.
- **Integração de Power Query** – uma experiência de Power Query está sendo criada para permitir que os criadores criem mashups de dados de forma de SQL Server.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) sobre esta versão.

### <a name="release-2018-08-31"></a>Versão de 2018-08-31

- **Teste seu fluxo usando** dados de exemplo – use dados de exemplo de conectores para testar seu fluxo ao criá-lo de dentro do designer de Microsoft Flow. Ao testar seu fluxo com dados de exemplo, você confirma que o fluxo será executado conforme o esperado quando for implantado na produção.
- **Cinco novos conectores** – adicionamos quatro novos conectores de gerenciamento: powerapps para criadores de aplicativos, plataforma Power para administradores, PowerApps para administradores, Microsoft Flow para administradores e sincronização de dados de estudante da Microsoft.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/test-data-management-connectors/) sobre esta versão.

### <a name="release-2018-08-24"></a>Versão de 2018-08-24

- **Novos modelos de sincronização de calendário** – novos modelos de calendário que copiam eventos entre o Google Agenda e o Office 365 ou Outlook.com.
- **Suporte a vários valores para o SharePoint** -leitura e gravação para campos de vários valores no SharePoint que são tipos de pesquisa, de pessoa ou de seleção.
- **Enviar aprovações em nome de outros usuários em sua organização** – envie aprovações em nome de outros usuários em sua organização, por exemplo, a pessoa que carregou o arquivo na lista do SharePoint, em vez da pessoa que criou o fluxo.
- **Mais tipos de entrada de botão** -os botões têm dois novos tipos de entrada: número e sim/não.
- **Atualizações de conector** -um novo conector do netdocuments, aprimoramentos para conectores do Azure e muito mais.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-types-more/) sobre esta versão.

### <a name="release-2018-08-02"></a>Versão de 2018-08-02

O programa de visualização Microsoft Flow é a maneira de obter acesso antecipado às futuras funcionalidades e atualizações para Microsoft Flow. Para obter acesso antecipado aos recursos mais recentes, basta criar e, em seguida, usar um ambiente na região de visualização.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/flow-preview-program/) sobre esta versão.

### <a name="release-2018-07-23"></a>Versão de 2018-07-23

- **Criar e executar fluxos do Excel** – com o novo botão de **fluxo** (acessado na guia **dados** da faixa de bits), você pode criar e disparar automaçãos de Microsoft Flow nos dados da tabela no Excel. Automatize o processamento de dados ou a cópia/importação de dados.
- **Criar um fluxo de processo de negócios** – um fluxo de processo de negócios é um novo tipo de fluxo com monitoração de estado e interativo com base na Common Data Service. Use esses novos fluxos para definir um conjunto de estágios e etapas para as pessoas seguirem. Eles podem avançar e retroceder, conforme necessário.
- **Criar um fluxo para a Microsoft a fazer no Outlook Web App** -se alguém estiver \@mencionado no Outlook Web App, ele verá um atalho para criar um fluxo. Esse fluxo cria automaticamente tarefas para o \@pessoa mencionada no Microsoft to-from, com base no conteúdo do email.
- **Suporte à exibição do SharePoint** -o conector do SharePoint agora dá suporte à seleção de um modo de exibição do SharePoint específico em gatilhos e ações. Isso filtra as colunas apenas para os campos que estão na exibição selecionada.
- **Quatro novos conectores** -adicionados ao Azure IOT central-uma solução de SaaS (software como serviço) de IOT altamente escalonável – pesquisa 123, integração de design de LMS365 e ProjectWise.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) sobre esta versão.

### <a name="release-2018-06-29"></a>Versão de 2018-06-29

- **Solicitação para o fluxo de aprovação interno do SharePoint** – quando você seleciona um arquivo ou item no SharePoint, você verá uma nova **solicitação para o fluxo de aprovação** . Esse fluxo não requer configuração nem configuração e envia uma solicitação de aprovação com um único clique.
- **Dois novos conectores** -adicionados o Cloud Connect Studio e o PoliteMail.
- **Melhorias de histórico e criação de página** – estamos atualizando a lista de histórico de execuções, incluindo tempos de execução exatos e a página criar, adicionamos um novo vídeo de explicação.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) sobre esta versão.

### <a name="release-2018-06-08"></a>Versão de 2018-06-08

- Os **cmdlets do PowerShell** -ambos os criadores de fluxo e administradores de locatários agora podem usar o PowerShell para gerenciar seus fluxos programaticamente.
- **Melhorias no bot de fluxo de equipes** – o bot de fluxo no Microsoft Teams pode executar botões de fluxo e descrever seus fluxos.
- **Três novos conectores** -suporte adicionado para marketo, ElasticOCR e DynamicSignal. 
- **Informações de compartilhamento adicionais** -adicionadas informações adicionais ao compartilhar ou executar fluxos compartilhados, para que você saiba exatamente quais permissões outras pessoas receberão.
- **Recorte automático de URLs do SharePoint** – quando você copia e cola uma URL do SharePoint no navegador, ele pode conter texto adicional além do site, esse texto será removido automaticamente para que você possa se conectar apenas ao site.
- **Documentação sobre solicitações GDPR** -criamos um guia e conjunto de ferramentas abrangentes para organizações empresariais para lidar com solicitações de direitos de entidade de dados.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) sobre esta versão.

### <a name="release-2018-05-21"></a>Versão de 2018-05-21

- **Flui "de propriedade de" listas do SharePoint e bibliotecas** – fluxos que funcionam com listas e bibliotecas do SharePoint podem ser compartilhados com essas listas ou bibliotecas. Portanto, em vez de serem compartilhados com indivíduos ou grupos, eles são compartilhados com todos que têm acesso à lista. À medida que os usuários são adicionados ou removidos da lista ou da biblioteca, sua associação é alterada automaticamente de acordo.
- **Análise de detalhes de erro** – um novo relatório inserido que fornece informações sobre todos os erros que ocorrem dentro de um fluxo.
- **Compartilhar fluxos com grupos do office 365** – você pode tornar um grupo moderno do Office 365 o proprietário de um fluxo e pode compartilhar fluxos de botão com grupos do Office 365 para que qualquer pessoa no grupo possa executar o fluxo.
- **Aprimoramentos do conector do SharePoint** – há dois novos recursos do conector do SharePoint: disparar fluxos quando itens ou arquivos forem excluídos e chamar qualquer ponto de extremidade http ao qual a API REST do SharePoint dê suporte.
- **Dois novos conectores** -suporte adicionado para Azure data Factory e MailParser

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) sobre esta versão.

### <a name="release-2018-05-01"></a>Versão de 2018-05-01

- **Rich Text em mensagens de aprovação** -use redução para formatar os detalhes de aprovação enviados.
- **Botões com entradas de seleção múltipla** – botões de fluxo de compilação que usam uma lista de seleção múltipla para coletar mais de um valor de uma só vez.
- **Trabalhar com fluxos maiores** – o aplicativo móvel Microsoft Flow agora dá suporte ao modo de exibição paisagem e o Web designer tem uma barra de rolagem horizontal.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) sobre esta versão.

### <a name="release-2018-04-12"></a>Versão de 2018-04-12

- **Retornar dados para o PowerApps de um fluxo** -criar fluxos que podem ser chamados de um aplicativo criado com o powerapps e retornar dados de volta para o aplicativo. Use o designer de fluxo visual do tipo "arrastar e soltar" para criar a lógica de que você precisa para seus aplicativos. 
- **Adicionar vários registros a entradas de matriz** – adicionou um construtor de lista no Microsoft Flow que pode ser usado para adicionar vários anexos a um email, por exemplo.
- **Fluxos de teste com dados de execução anteriores** – adicionou um novo botão de fluxo de teste ao designer que permite testar seu fluxo com dados de gatilho de execuções de fluxo anteriores.
- **Novos campos de fluxo de trabalho ()** – agora você pode acessar o nome do ambiente e o nome de exibição do fluxo com a expressão de fluxo de trabalho ().

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/return-data-to-powerapps/) sobre esta versão.

### <a name="release-2018-04-04"></a>Versão de 2018-04-04

- As **aprovações no Common Data Service** -aprovações modernas são criadas na versão mais recente do Common Data Service. Isso significa que você pode criar fluxos que lêem o status das aprovações que você envia ou recebe com o conector de Common Data Service.
- **Localizar erros em aplicar a cada** -salta diretamente para erros em loops na exibição de execução do fluxo, mesmo quando há centenas de itens no loop.
- **Reatribuir aprovações** -você pode atribuir qualquer aprovação que receber a outra pessoa em sua organização para delegar a aprovação a elas. 
- **Listas de salas** -o conector do Outlook para Office 365 adicionou ações para obter dados de sala em sua organização.
- **Ver detalhes de botões de fluxo** – quando você executa um fluxo que foi compartilhado com você, agora você pode ver todas as ações que o fluxo usa.
- **Região** do Reino Unido-os ambientes agora podem ser criados para armazenar seus dados no Reino Unido.
- **Dois novos conectores** -suporte adicionado para o AtBot admin e o marketing Content Hub.
- **Página de aterrissagem da nova documentação** -atualização da página de aterrissagem de documentação para ter o conteúdo agrupado por quem você é: um usuário iniciante, intermediário ou especialista. 

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) sobre esta versão.

### <a name="release-2018-03-13"></a>Versão de 2018-03-13

- **Histórico de aprovação** -Veja todas as solicitações de aprovação que você enviou, incluindo as respostas, os comentários que foram enviados e a hora exata em que ocorreram.
- **Quatro novos conectores** – adicionados ao Excel online (Business), ao Excel online (onedrive), ao Azure SQL data warehouse e à calculadora de impostos do Pitney Bowes.
- **Dicas de ferramenta de conteúdo dinâmico** -focalize o conteúdo dinâmico para ver onde ele veio dentro de ações e visualize as expressões sem abrir o editor de expressão completo.
- **Controle de simultaneidade** – habilite o controle de simultaneidade para que um determinado fluxo tenha apenas uma execução por vez.
- **Repetição exponencial** -um novo tipo de política de repetição que destaca as repetições exponencialmente ao longo do tempo.
- **Conformidade de acessibilidade** – lançamento de novos documentos de conformidade que descrevem como Microsoft Flow atendem aos padrões de acessibilidade.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/approval-history-accessibility/) sobre esta versão.

### <a name="release-2018-02-09"></a>Versão de 2018-02-09

- **Alta disponibilidade de gateway** -crie clusters altamente disponíveis de gateways de dados locais, para manter as conexões ativas quando as máquinas únicas ficarem inativas.
- **Aplicação aprimorada a cada** -com o processo plano 1 ou fluxo plano 2 de até 100.000 itens em uma única execução e 50 ações em paralelo em aplicar a cada loops. 

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) sobre esta versão.

### <a name="release-2018-01-29"></a>Versão de 2018-01-29

- **Fluxo dentro de equipes da Microsoft** – de equipes, você pode criar e gerenciar fluxos, examinar suas aprovações recebidas e enviadas e iniciar fluxos diretamente no aplicativo de área de trabalho de equipes ou no Teams.Microsoft.com- [saiba mais aqui](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Notificações de edição compartilhadas** – sempre que um fluxo que você possui for alterado por um colega de trabalho, você receberá uma notificação por email informando que você alterou o fluxo.
- **Novas expressões** – adicionadas dois novos conjuntos de expressões: uma para analisar URLs e outra para trabalhar com objetos JSON.
- **Três novos conectores** -esta semana há dois novos conectores do Plumsail: Plumsail SP e Plumsail Forms e um novo conector para kintone.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) sobre esta versão.

### <a name="release-2018-01-17"></a>Versão de 2018-01-17

- **Informações de perfil do office 365** – adicionamos novas ações ao conector de usuários do Office 365 que funcionam com perfis de usuário e fotos.
- **Acrescentar a variáveis de cadeia de caracteres** – você pode adicionar a cadeias de caracteres dentro de loops para criar tabelas ou outras listas.
- **Conector do Infobip** – o Infobip é um serviço que permite a comunicação de nível empresarial, incluindo chamadas de voz e disparo em SMS de entrada.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/o365-profile-infobip/) sobre esta versão.

### <a name="release-2017-12-20"></a>Versão de 2017-12-20

O Microsoft Flow Analytics agora está disponível em todas as regiões de Microsoft Flow, o que significa que você pode obter mais informações sobre a integridade dos fluxos em execução em seu ambiente.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) sobre esta versão.


### <a name="release-2017-12-14"></a>Versão de 2017-12-14

- **Aprimoramentos do conector do Outlook** – você pode salvar um email como um arquivo ". eml", responder a convites de calendário automaticamente e disparar fluxos quando for mencionado em um thread de email.
- **Melhorias de conexões** -Microsoft Flow memoriza as conexões usadas mais recentemente e mostra todos os conectores recém-adicionados.
- **Cinco novos conectores** – foram adicionadas instâncias de contêiner do Azure, Kusto do Azure, metatarefa, Microsoft a fazer e documentos de Plumsail.
- **Aprimoramentos de http** -a ação http agora dá suporte à codificação em partes.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/outlook-connector-more/) sobre esta versão.

### <a name="release-2017-12-05"></a>Versão de 2017-12-05

O painel de inicialização do Microsoft Flow agora está disponível em todas as regiões. Esse painel permite que você adicione valores a um fluxo ao executá-lo dentro de sua lista ou biblioteca de documentos do SharePoint.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) sobre esta versão.


### <a name="release-2017-11-28"></a>Versão de 2017-11-28

- **Metadados gerenciados** – ler dados de e gravar em colunas no SharePoint que usam os metadados gerenciados (também conhecido como. Tipo de taxonomia).
- **Anexar a matrizes** – adicione itens ao final das matrizes usando uma nova ação de variável acrescentar à matriz.
- **Tago** -um novo conector para o Tago, que fornece uma conexão fácil de dispositivos eletrônicos com dados externos para impulsionar decisões mais inteligentes usando a análise contextual.
- **iPhone x** – uma nova versão do aplicativo Microsoft Flow que usa a tela inteira no iPhone X e que tem uma melhoria na velocidade para carregamentos de imagem.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/managed-metadata-tago/) sobre esta versão.

### <a name="release-2017-11-09"></a>Versão de 2017-11-09

- **Integração do onedrive for Business** – [agora há um botão de fluxo dentro do onedrive for Business](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) que pode criar ou disparar fluxos em arquivos ou pastas selecionados.
- **Gatilhos de planejador** – iniciar fluxos quando uma nova tarefa for criada, quando uma tarefa for atribuída a você ou quando um for concluído.
- **Anexos do SharePoint** – trabalhar com anexos em itens de lista do SharePoint: listar, baixar, adicionar ou excluir anexos.
- **Conector de gerenciamento de fluxo** – crie fluxos que automatizam o gerenciamento de outros fluxos em seu ambiente (por exemplo, adicionar permissões a fluxos automaticamente).
- **Quatro novos conectores** -adicionados serviço de visão personalizada do Azure, D & B Optimizer, enadoc e Derdak SIGNL4. 
- **Mais ações de conector** -execute consultas SQL, obtenha gatilhos de email mais rápidos, use qualquer método com http com o Azure AD e muito mais.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) sobre esta versão.

### <a name="release-2017-11-02"></a>Versão de 2017-11-02

- **Log de auditoria** – eventos de auditoria de Microsoft Flow agora estão disponíveis no Office 365 centro de conformidade e segurança para todos os locatários.
- **Correções do widget de fluxo** – Corrigido um problema no aplicativo móvel do Flow que fazia com que os botões não carregassem no widget.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/security-and-compliance-center/) sobre esta versão.

### <a name="release-2017-10-19"></a>Versão de 2017-10-19

- **Aplicar aninhado a cada** -você pode adicionar aplicar a cada ação, filtrar e selecionar outro se aplicar a cada ação de contêiner.
- **Ações de data e hora** -novas ações para obter horas locais, adicionar, subtrair ou Formatar tempos.
- **Quatro novos conectores** -adicionados Content moderator, docParser, Microsoft Kaizala e Pitney Bowes data Validation.
- **Experiência de conexão aprimorada** -notificações no portal de Microsoft Flow quando uma conexão é quebrada e detalhes de conexão mais avançados.
- **Coleção em trânsito** – uma nova coleção de modelos para [trabalhadores em trânsito](https://flow.microsoft.com/collections/onthego/).
- **Entradas do botão de endereço de email** – colete os endereços de email dos usuários quando eles executam botões.
- **Entradas de botão de arquivo** – obtenha arquivos carregados, como fotos, de usuários quando eles executam botões.
- **Primeira execução e logon automático** -experiências de primeira execução aprimoradas no aplicativo móvel, incluindo a entrada automática.
- **Gatilhos mais rápidos do Microsoft Forms** -os formulários irão disparar fluxos muito mais rapidamente do que antes (anteriormente uma vez por hora).
- **Entradas de botão entre sessões** – os botões disparados em seu celular se lembrarão das entradas anteriores.
- **Feed de atividades móveis** -feed de atividades aprimorado para incluir resumos de execução mais detalhados e detalhes de solução de problemas.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/nested-apply-to-each/) sobre esta versão.

### <a name="release-2017-10-03"></a>Versão de 2017-10-03

- **Todos devem ser aprovados** -exigir uma solicitação de aprovação enviada a mais de uma pessoa para ter todos que receberam a solicitação para aprová-la.
- **Novas ações do onedrive for Business** – gere PDFs para arquivos armazenados no onedrive for Business e quatro outras novas ações.
- O **conector do Apache Impala** – Apache Impala (incubating) é o banco de dados analítico nativo de software livre para Apache Hadoop.
- **Adicionar descrições de fluxo** – dê suas descrições de fluxos para que você as Compartilhe para que seus colegas possam ver um resumo do fluxo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) sobre esta versão.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Versão de 2017-09-25 – atualização do Q3 para Microsoft Flow

- **Integração mais profunda do SharePoint na primeira versão** – há um novo envio "pronto para ser" para fluxos de revisão e um painel de fluxo para coletar entradas quando você executa um fluxo para locatários de primeira versão.
- **Aplicativos do dynamics 365** – o Flow agora está integrado na interface do usuário para aplicativos do Dynamics 365, como o Dynamics 365 Sales e o atendimento ao cliente do Dynamics 365.
- **Centro de confiabilidade da Microsoft** -Microsoft Flow está listado na central de confiabilidade da Microsoft, mostrando certificações como HIPAA, ISO e SOC.
- **Análise de uso** -cada fluxo tem um painel de Power bi incorporado com análise de uso básico.
- **Log de auditoria na primeira versão** -todos os eventos de gerenciamento de fluxo são registrados no centro de conformidade e segurança do Office 365 para os locatários do primeiro lançamento.
- **Seis novos conectores** -adicionados o LinkedIn, grupos do Office 365, Skype for Business, Adobe Sign, Bizzy e Azure log Analytics coleta de dados.
- **Gatilhos SQL** -executam fluxos quando uma nova linha é adicionada ou uma linha é atualizada em uma tabela SQL.
- **Conectores personalizados** locais – os conectores personalizados agora podem usar o gateway de dados local para se conectar a pontos de extremidade internos em sua rede.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/q3-2017-update/) sobre esta versão.

### <a name="release-2017-09-21"></a>Versão de 2017-09-21

- **Baixar o histórico de fluxo** – Baixe o histórico de execução de um fluxo como um arquivo CSV para abrir no Excel.
- **Recorrência avançada** -crie agendamentos recorrentes para disparar seus fluxos, por exemplo, somente gatilhos em dias da semana.
- **IntelliSense** – ao digitar expressões, o IntelliSense fornecerá sugestões para parâmetros.
- **Quatro novos conectores** -adicionados conectores para os serviços http do Azure AD, Amazon Redshift, publicação da grade de eventos do Azure e FlowForma.
- **Compartilhando links** – uma nova ação para gerar links compartilháveis para arquivos do onedrive ou BLOBs de armazenamento do Azure.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/download-history-recurrence/) sobre esta versão.


### <a name="release-2017-08-25"></a>Versão de 2017-08-25
* **Propriedades do documento e muito mais para o SharePoint** - [ler e definir propriedades da biblioteca de documentos do SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/)e usar campos adicionais como links para o item do SharePoint.
* **Coleções de fluxo** – as coleções de fluxo são um conjunto de coleções de modelos organizadas por função ou por vertical.
* **Recompartilhamento de botão** – quando você compartilha botões com seus colegas de trabalho, eles podem compartilhá-los novamente com outras pessoas.
* **Coletar listas de botões** – defina os menus suspensos das opções para os usuários escolherem quando tocarem no botão.
* **Sete novos conectores** – Aweber, Azure log Analytics, tabelas do Azure, DocFusion365, grade de eventos do Azure, hubs de eventos do Azure e StaffHub. 
* **Melhorias na margem de atraso e no MySQL** -criar ou unir canais na margem de atraso e você pode gravar em bancos de dados MySQL.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-updates-seven-connectors/) sobre esta versão.

### <a name="release-2017-08-02"></a>Versão de 2017-08-02
* **Gravar nos campos pessoa, opção e pesquisa** – criar item e atualizar item do SharePoint [agora dão suporte à capacidade de](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) definir campos de pesquisa, de escolha e de pessoa.
* **Mais configurações de ação** – agora há mais controle sobre como os gatilhos e as ações são executados, incluindo a configuração de políticas de repetição e paginação.
* **Quatro novos conectores** – agora você pode usar o armazenamento de arquivos do Azure, formulários elásticos, Plivo e video indexer.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/four-connector-action-settings/) sobre esta versão.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Versão de 2017-07-27-atualização do Q2 para Microsoft Flow
* **Importar e exportar** – exportar e importar soluções de fluxo entre ambientes ou de teste para produção. 
* **Usar expressões em ações** – insira expressões em qualquer ação e Obtenha ajuda embutida com como usá-las.
* **Aumentar até os aplicativos lógicos do Azure** – Salve seus fluxos como recurso de aplicativo lógico do Azure que pode ser implantado por meio do Visual Studio ou do portal do Azure.
* **Visibilidade do administrador** -Baixe Microsoft Flow uso em seu locatário para entender exatamente onde e como os fluxos estão sendo usados.
* **Fluxos no dynamics 365** – use fluxos dentro do Dynamics 365 para operações & financeiro, Business Edition.
* **Encontre cenários com mais facilidade** – navegue tudo o que o conector pode fazer e, em seguida, use qualquer gatilho como um ponto de salto para a criação de fluxos.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/q2-2017-update/) sobre esta versão.

### <a name="release-2017-07-13"></a>Versão de 2017-07-13
* **Publicação de modelo aprimorada** – publique qualquer fluxo que você criar, juntamente com suas categorias, para a Galeria pública.
* **Obter eventos no seu calendário do Outlook** – uma nova ação para retornar todos os eventos entre duas vezes no seu calendário.
* **Nova funcionalidade móvel** -execute fluxos sob demanda e reenvie execuções com falha no aplicativo móvel.
* **Listas suspensas dinâmicas em conectores personalizados** – crie listas suspensas dinâmicas, disparadores de sondagem e teste seus conectores personalizados.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) sobre esta versão.

### <a name="release-2017-06-28"></a>Versão de 2017-06-28
* **Atualizar suas configurações de idioma** – você pode personalizar o idioma e a região que Microsoft Flow usa por meio do menu configurações.
* **Cinco novos conectores** -suporte adicionado para Adobe Creative Cloud, Bing Maps, pesquisa do Bing, JotForm e Freshservice.
* **Configurar tempos limite** -altere as ações de tempo demorado, como aprovações, são executadas antes de "Timeout" e o fluxo continua.
* **Incluir comentários no Outlook para aprovações** – quando você recebe uma solicitação de aprovação, pode fornecer comentários sem sair do Outlook.
* **Cores da marca do conector personalizado** -agora você pode inserir uma cor para os conectores personalizados que serão usados para os planos de fundo.
* **Salvar como para fluxos de equipe** – faça cópias de qualquer fluxo, incluindo fluxos de equipe
* **Excluir informações de fluxo** – ao excluir um fluxo, você verá a lista de todas as execuções pendentes para esse fluxo.
* **Filtragem na página conectores** – pesquise os conectores que você deseja na página conectores e filtre por tipo de conector.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/language-settings-3-connectors/) sobre esta versão.

### <a name="release-2017-06-19"></a>Versão de 2017-06-19
Agora você pode exibir o status de todas as solicitações de aprovação pendentes que você enviou. Além disso, você pode procurar e agir em todas as suas aprovações pendentes diretamente do seu dispositivo móvel.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) sobre esta versão.

### <a name="release-2017-06-15"></a>Versão de 2017-06-15
* **Conversão de conteúdo** – um novo conector que pode converter conteúdo HTML em texto sem formatação, útil para lidar com emails formatados em HTML.
* **Três novos conectores de banco de dados** -adicionado suporte somente leitura para MySQL, PostgreSQL e Teradata. Esses conectores se conectam por meio do gateway de dados local.
* **Três outros conectores** -Conecte-se a aplicativo Azure insights, Calendly e projetos de equipe.
* **Melhor visualização para tratamento de erros** – as etapas executadas após os erros agora são mostradas com setas pontilhadas vermelhas para que você possa identificá-las facilmente.
* **Painel de detalhes de execução** – quando um fluxo falha, agora há um novo painel à direita que contém algumas etapas úteis para corrigir o fluxo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/seven-connectors-and-html/) sobre esta versão.

### <a name="release-2017-06-04"></a>Versão de 2017-06-04
* **GA para Windows Phone** - [o aplicativo móvel Microsoft Flow foi lançado para a disponibilidade geral para Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Emails em falhas de fluxo** – seja notificado por email quando houver um fluxo com falha. Esses emails de falha serão enviados apenas uma vez por semana e poderão ser ativados ou desativados pelo usuário.
* **Selecionar ação para tabelas** – use a nova ação selecionar para alterar o conjunto de colunas que serão incluídas em tabelas.
* **Microsoft Forms Connector** -o Microsoft Forms é uma nova parte do Office 365 Education, que permite que professores e alunos criem testes personalizados de maneira rápida e fácil, pesquisas, questionários, registros e muito mais.
* **Plano do office 365 Enterprise K1** – PowerApps e Microsoft Flow agora estão incluídos no plano do Office 365 Enterprise K1 com determinadas cotas.
* Os **cabeçalhos HTTP são mais fáceis** , assim como a ação Select, você pode fornecer um nome de cabeçalho e um valor de cabeçalho simplesmente preenchendo as caixas de texto na ação.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) sobre esta versão.

### <a name="release-2017-05-23"></a>Versão de 2017-05-23
* **Microsoft Teams connector** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) é um espaço de trabalho baseado em chat no Office 365 que reúne pessoas, conversas e conteúdo – juntamente com as ferramentas de que as equipes precisam, para que possam colaborar facilmente para obter mais.
* **Widgets em widgets Ios e Android** -Microsoft Flow são atalhos de botão que fornecem uma maneira mais fácil e rápida para o botão disparar diretamente da tela inicial.
* **Criar etapas de "tratamento de erro"** -defina uma ou mais etapas a serem executadas depois que uma ação falhar. Por exemplo, receba uma notificação imediatamente se o fluxo falhar ao criar um registro no Dynamics 365.
* **Variáveis Integer e float** – inicializar e incrementar ou decrementar contadores dentro de uma execução de fluxo para contar quantas vezes um determinado conjunto de lógica é executado.
* **Página de detalhes do fluxo** – quando você seleciona um fluxo em sua lista **meus fluxos** , você verá uma página com detalhes sobre esse fluxo, como quem tem acesso e o histórico de execução.
* **Cotas de execução de fluxo para administradores** – os administradores agora podem monitorar o uso de execução de fluxo em uma organização em relação à cota de execução da empresa comum e obter uma divisão de cota para entender quais licenças contribuem para sua cota.
* **Aprimoramentos do gatilho de solicitação HTTP** – use métodos http diferentes e adicione segmentos de caminho para o gatilho de solicitação.
* **Dois conectores de parceiro** -Microsoft Flow agora podem se conectar ao Parserr, um serviço de análise de email e formulários de cognito, um serviço de formulários online.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/error-handling/) sobre esta versão.

### <a name="release-2017-05-12"></a>Versão de 2017-05-12
* **Integração das bibliotecas de documentos do SharePoint** – você pode selecionar qualquer arquivo em uma biblioteca de documentos e disparar um fluxo, por exemplo, para enviá-lo ao seu gerente para aprovação [e muito mais](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Conector do Microsoft Planner** -o Microsoft Planner permite que você reúna facilmente equipes, tarefas, documentos e conversas para obter melhores resultados.
* **Exibição do administrador de licenças** – os administradores podem ver todas as licenças Microsoft Flow e PowerApps (avaliação e pagas) no centro de administração do Microsoft Flow.
* **Plano de comunidade do powerapps** -o plano de comunidade do powerapps é um plano gratuito para indivíduos que exploram, aprendem e criam habilidades para o PowerApps, Microsoft Flow e Common Data Service.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/planner-community-and-licenses/) sobre esta versão.

### <a name="release-2017-05-09"></a>Versão de 2017-05-09
* **Conector do AD do Azure** – há um novo conector para executar ações de administrador do Microsoft Flow, incluindo a criação de usuários ou a adição deles a grupos.
* **Aprimoramentos do Outlook do Office 365** – os fluxos agora podem ser disparados por caixas de correio compartilhadas e enviar emails para uma caixa de correio compartilhada. Eles também podem definir ou ler respostas automáticas.
* **Disponível no Canadá** -agora você pode criar seus fluxos no Canadá.
* **Criar WebHooks de API personalizada** -os desenvolvedores de conector personalizado agora podem adicionar gatilhos a suas APIs personalizadas com WebHooks.
* **Gerenciar proprietários de fluxo no centro de administração** -os administradores de ambiente podem gerenciar os proprietários de fluxo no centro de administração Microsoft Flow.
* **Referência de documentação do conector** -agora temos uma [referência completa do conector em docs.Microsoft.com](https://docs.microsoft.com/Connectors/).
* **Dois serviços de parceiros** -dois novos serviços de parceiros foram lançados: Nexmo e Paylocity.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/canada-mailboxes-aad) sobre esta versão.

### <a name="release-2017-04-27"></a>Versão de 2017-04-27
* Criar **fluxos com etapas paralelas** – criar fluxos com execução paralela: ou seja, você pode ter duas ou mais etapas executadas exatamente ao mesmo tempo.
* **Cinco novos serviços com suporte** -cinco novos serviços: aprovações, email de benchmark, CRM de cápsula, LiveChat e Gerenciador de clientes do Outlook.
* **Monitorar repetições para ações** -Microsoft Flow tentará novamente quando houver falhas com os serviços. Agora, veja quantas tentativas automáticas ocorreram e os detalhes do que aconteceu.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/parallel-actions/) sobre esta versão.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Versão de 2017-04-17-atualização de Q1 para Microsoft Flow
* **Experiências de aprovação modernas** -crie fluxos de trabalho em que os aprovadores podem aprovar com segurança de dentro do Microsoft Flow aplicativo móvel ou o centro de aprovações unificadas no site do Microsoft Flow.
* **Disponibilidade geral de fluxos de equipe** -várias pessoas podem possuir e gerenciar um fluxo junto com fluxos de equipe, que agora estão disponíveis para o público em geral.
* **Conectores de Build para Microsoft Flow** -qualquer pessoa pode enviar seu próprio conector de Microsoft Flow gratuitamente para o restante do mundo usar.
* **Um designer de "dieta"** -para determinados modelos, uma nova versão do designer apresenta apenas os campos que são necessários para criar um fluxo, o que simplifica a experiência.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/q1-2017-update/) sobre esta versão.

### <a name="release-2017-04-11"></a>Versão de 2017-04-11
* **Novas ações para criar tabelas e listas** – nova criação de tabela HTML, criar uma tabela CSV e ações de junção que podem processar listas de itens (em vez de aplicar somente a aplicação anterior).
* **Inserir etapas em qualquer lugar** – agora você pode inserir uma nova etapa em qualquer lugar no fluxo de trabalho sem a necessidade de arrastar e soltar.
* **Quatro novos serviços** – o Flow agora dá suporte a agendamento de 10 a 8, Act!, Inoreader e o API da pesquisa Visual computacional. Com o API da Pesquisa Visual Computacional você pode processar imagens para obter o conteúdo do texto (conhecido como OCR) ou marcar imagens automaticamente com base em seu conteúdo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) sobre esta versão.

### <a name="release-2017-04-03"></a>Versão de 2017-04-03
* **Windows Phone beta** -o programa beta do aplicativo Windows Phone está disponível para obter uma visualização do aplicativo em seu Windows Phone. [Leia mais](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **MUHIMBI PDF** – agora você pode converter arquivos do Microsoft Word em PDF, adicionar marcas-d ' água, mesclar documentos e muito mais com o MUHIMBI PDF. [Leia mais](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Disparar fluxos de botões físicos** – anunciando parcerias com dois dos principais produtos no espaço de botão físico: flic por laboratórios de atalho e BTTN pela The Button Corporation. [Leia mais](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Versão de 2017-03-22
* **Fazer uma cópia do seu fluxo** – agora você pode fazer uma cópia do seu fluxo para trabalhar em versões de rascunho ou duplicar um fluxo que você criou no passado.
* **Dois novos serviços** -adicionando suporte para Toodledo-Gerencie sua lista de tarefas criando e atualizando, e zendesk, que fornece um serviço de cliente e suporte à plataforma de tíquetes.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/make-a-copy/) sobre esta versão.

### <a name="release-2017-03-15"></a>Versão de 2017-03-15
* **Compartilhar botões com colegas de trabalho** – agora você pode compartilhar botões de fluxo com outras pessoas, facilitando a realização de tarefas rápidas por qualquer usuário comercial.
* **Os botões de gatilho da tela inicial** -atalhos para os botões de fluxo das telas início e bloqueio de dispositivos móveis tornam mais rápido do que nunca disparar um fluxo.
* **Fluxos de equipe no aplicativo Microsoft Flow** – agora você pode ver os fluxos que têm outros proprietários no aplicativo Microsoft Flow para Ios ou Android.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-sharing/) sobre esta versão.

### <a name="release-2017-03-10"></a>Versão de 2017-03-10
* **Melhor experiência de conector personalizado** : agora você pode usar uma coleção de postmaster para criar um conector personalizado e editar, adicionar e testar ações.
* **Dois novos serviços** -foram adicionadas notificações do PowerApps e suporte PivotalTracker.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/new-updates-custom-api/) sobre esta versão.

### <a name="release-2017-02-27"></a>Versão de 2017-02-27
* **Disparar seus botões de fluxo** – agora você pode disparar botões de fluxo diretamente de Microsoft Flow. Ao examinar sua lista de fluxos, basta selecionar o botão "..." e escolha o comando executar agora.
* **Cinco novos serviços** -adicionados Oracle Database, intercomunicador, FreshBooks, LeanKit e suporte webmerge.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) sobre esta versão.

### <a name="release-2017-02-21"></a>Versão de 2017-02-21
* **Exibir fluxos de ambiente** -os administradores de ambiente agora podem exibir a lista completa de todos os fluxos dentro de um determinado ambiente, bem como habilitar, desabilitar ou excluir fluxos.
* **Dois novos serviços** -foram adicionados suporte à automação do Azure e ao Basecamp 2.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sobre esta versão.

### <a name="release-2017-02-16"></a>Versão de 2017-02-16
* **Cinco novos serviços** -suporte adicionado para Azure data Lake, bitbucket (um serviço de hospedagem baseado na Web para projetos que usam o controle de revisão git), Eventbrite, Infusionsoft e Pipedrive.
* **Autenticação HTTP personalizada** -no designer de fluxo, agora é possível usar a autenticação com pontos de extremidade HTTP personalizados.
* **Analisar mensagens JSON** – você pode analisar dados JSON do gatilho de solicitação HTTP ou que é retornado da ação http.
* **Filtragem de execução de fluxo** -filtragem aprimorada para execuções de fluxo, com opções mais específicas, incluindo ver fluxos em execução ou canceladas execuções.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sobre esta versão.

### <a name="release-2017-02-06"></a>Versão de 2017-02-06
* **Fluxos de equipe** -os fluxos de equipe possibilitam que várias pessoas tenham e gerenciem um fluxo juntos e, se alguém sair de uma organização, os fluxos criados poderão continuar a ser executados.
* **Compartilhamento de conectores personalizados** – conectores personalizados, como fluxos de equipe, podem ser compartilhados e gerenciados coletivamente dentro de uma organização.
* **Suporte ao gmail e ao Luis** – Conecte-se ao gmail e aos serviços cognitivas do Azure ' reconhecimento vocal serviço inteligente.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/team-flows/) sobre esta versão.

### <a name="release-2017-01-30"></a>Versão de 2017-01-30
* **Entradas do botão de fluxo** – os botões de fluxo agora podem receber entradas de usuário em tempo de execução, portanto, os autores de fluxo podem definir informações que são passadas quando o botão é tocado.
* **Tarefas do Outlook e HelloSign** -o serviço de tarefas do Outlook permite gerenciar tarefas e o HelloSign permite assinaturas eletrônicas seguras.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-user-inputs/) sobre esta versão.

### <a name="release-2017-01-23"></a>Versão de 2017-01-23
* **Pesquisar por serviço** – navegue pelo serviço ao adicionar um gatilho ou uma ação para ver todas as ações de cada serviço.
* **Alternar maiúsculas/minúsculas** -adicionar blocos de alternância para ter várias ramificações de lógica paralela.
* **Mais ações de email** – nova funcionalidade nos serviços de Outlook.com e Outlook do Office 365 para trabalhar com emails sinalizados.
* **Cinco novos serviços** – Conecte-se a sistemas de arquivos locais ou de rede, a faixa de serviço de pagamento, IBM Informix, IBM DB2 e UserVoice.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/search-by-service/) sobre esta versão.

### <a name="release-2017-01-14"></a>Versão de 2017-01-14
* **Reenviar execuções** -se um fluxo falhou e você deseja tentar corrigi-lo e executá-lo novamente, você pode reenviar a execução com falha.
* **Cancelar execuções** -quando um fluxo fica preso, agora você pode cancelar explicitamente a execução.
* **Dois novos serviços** -suporte adicionado para GoToTraining e GoToWebinar.
* **Links móveis** -você pode compartilhar modelos diretamente do aplicativo móvel e adicionamos um link de download rápido para os aplicativos na parte superior do site.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/managing-runs/) sobre esta versão.

### <a name="release-2016-12-29"></a>Versão de 2016-12-29
Microsoft Flow agora dá suporte a DocuSign, para lidar com assinaturas digitais e gerenciamento de transações digitais; SurveyMonkey, para pesquisas baseadas na Web; e o aplicativo de anotações do OneNote (somente contas de negócios).

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/final-2016-services/) sobre esta versão.

### <a name="release-2016-12-20"></a>Versão de 2016-12-20
* **Executar agora** -agora você pode disparar um gatilho recorrente sob demanda – por exemplo, se você tiver um relatório agendado todos os dias, mas precisar que o relatório seja executado **agora** também.
* **Seis novos serviços** -crie fluxos que se conectam ao MSN Weather, médio, contatos do Google, buffer, coleta e TypeForm.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/run-now-and-six-more-services/) sobre esta versão.

### <a name="release-2016-12-14"></a>Versão de 2016-12-14
Agora você pode aproveitar informações valiosas ao disparar um fluxo de botão, como de onde o botão foi disparado, por quem, em que hora e muito mais.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-trigger-tokens/) sobre esta versão.

### <a name="release-2016-12-06"></a>Versão de 2016-12-06
* **Introdução ao aprendizado guiado** -introdução a uma coleção sequenciada de cursos que emparelham vídeos com a documentação para ajudá-lo a compreender os recursos abrangentes e poderosos do Microsoft Flow.
* **Dois novos serviços** – os fluxos agora podem usar o Freshdesk, uma solução de suporte ao cliente e o GoToMeeting, uma ferramenta de reunião online.
* **Suporte a webhook http** -um fluxo agora pode ser um ponto de extremidade para WebHooks que serão automaticamente registrados e cancelar o registro.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/guided-learning-and-two-services/) sobre esta versão.

### <a name="release-2016-11-23"></a>Versão de 2016-11-23
* **Power bi suporte a alertas no Flow** -transforme informações em ação disparando fluxos de Power bi alertas de dados.
* **Aprimoramentos de aplicativos móveis** -foi adicionada a capacidade de criar fluxos de em branco, além da experiência já existente de criação a partir de modelos. Também melhoramos o desempenho ao exibir execuções de fluxo.
* **Oito novos serviços** – agora você pode se conectar a Azure Resource Manager, filas do Azure, informativo, Disqus, Azure Cosmos DB, serviços cognitivas API de detecção facial, HipChat e WordPress.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) sobre esta versão.

### <a name="release-2016-11-15"></a>Versão de 2016-11-15
* **Microsoft Flow programa de parceiro** – Microsoft Flow agora tem um programa de parceria certificado para fazer conexões e aproveitar os talentos e a experiência de uma empresa diferente com Microsoft Flow em todo o mundo.
* **Seis novos serviços** – também estamos lançando seis serviços desta semana: asana, Campfire, EASYREDMINE, JIRA, redmín e Vimeo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/partner-program-six-new-services/) sobre esta versão.

### <a name="release-2016-10-31---general-availability"></a>Versão 2016-10-31-disponibilidade geral
* **Preços e licenciamento** – agora disponíveis em planos gratuitos e pagos, bem como incluídos no Office 365 e no Dynamics 365.
* **Microsoft Flow centro de administração** – pronto para empresas com o novo centro de administração. No centro de administração, você pode gerenciar os ambientes dentro da organização.
* **Políticas de prevenção de perda de dados** – os administradores podem criar políticas de prevenção contra perda de dados para controlar o fluxo de dados entre serviços.
* **Disponibilidade do Android** -o aplicativo de telefone Microsoft Flow agora está disponível para IOS e Android. O aplicativo permite que você obtenha notificações, monitore a atividade e inicie fluxos com o toque de um botão.
* **Novas experiências de designer** – agora você pode pesquisar o conteúdo dinâmico passado de etapa para etapa, tornando muito mais rápido fazer referência aos dados que você deseja.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/announcing-ga/) sobre esta versão.

### <a name="release-2016-10-26"></a>Versão de 2016-10-26
* **Fluxos de botão** – há inúmeras operações que desejamos disparar a qualquer momento e em qualquer lugar. Agora, com fluxos de botão, você pode fazer isso com apenas um clique de um botão, do seu dispositivo móvel.
* **Anunciando ambientes** – os ambientes são espaços distintos para armazenar e gerenciar os fluxos da sua organização. Os ambientes são geograficamente localizados, o que significa que os fluxos, os aplicativos e os dados de negócios que residem em um ambiente estarão na região em que o ambiente está localizado.
* **Seis novos serviços** -adicionando suporte para bit.ly, serviços cognitivas análise de texto, Dynamics NAV, Dynamics 365 para finanças, Instapaper e Pinterest.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/environments-for-makers/) sobre esta versão.

### <a name="release-2016-10-16"></a>Versão de 2016-10-16
* **Conectores personalizados dão suporte a mais tipos de autenticação** – os conectores personalizados agora dão suporte à autenticação de chave de API e podem se autenticar em qualquer serviço que ofereça suporte à especificação OAuth 2,0 completa.
* **Três novos serviços com suporte** – Adicionamos suporte para Basecamp 3, Blogger e PagerDuty.
* **Aprimoramentos do designer** -melhor desempenho, agora você pode atualizar e reparar suas conexões diretamente do "..." para cada ação e adicionamos uma nova etapa chamada Terminate que você pode usar para encerrar a execução de um fluxo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/early-october-updates/) sobre esta versão.

### <a name="release-2016-09-25"></a>Versão de 2016-09-25
Criação de fluxo agora disponível nos telefones celulares. Navegue pela nossa galeria de modelos avançados, navegue pela nossa lista de serviços ou selecione uma categoria de modelo para analisar. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/mobile-creation/) sobre esta versão.

### <a name="release-2016-09-22"></a>Versão de 2016-09-22
* **Microsoft Graph seletor de pessoas** – um novo seletor de pessoas Microsoft Graph é integrado diretamente à interface do usuário do Microsoft Flow para ajudá-lo a escolher o contato correto ou o endereço de email.
* **Suporte do Microsoft Dynamics AX** -de dentro de seus fluxos, agora você pode tomar medidas sobre seus dados de operações do Dynamics AX online, desde a criação de novos registros até a consulta de dados.
* **Dois novos serviços de parceiros** – agora usam appFigures ou insightly de seus fluxos.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/more-september-updates/) sobre esta versão.

### <a name="release-2016-09-14"></a>Versão de 2016-09-14
* **Inserindo em seu site ou aplicativo** -os desenvolvedores agora podem inserir Microsoft Flow diretamente em seus aplicativos ou sites para dar aos usuários uma maneira simples de automatizar suas tarefas pessoais ou profissionais.
* **Usar um fluxo como um ponto de extremidade http** – agora você pode usar um fluxo em si como uma API http. Há um gatilho chamado solicitação dentro do fluxo e você pode optar por responder à solicitação de entrada adicionando um cartão de resposta.
* **Suporte** do Todoist – todo fornece uma perspectiva sobre todos os seus projetos, no trabalho e em casa.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/extend-web-site-application/) sobre esta versão.

### <a name="release-2016-09-01"></a>Versão de 2016-09-01
Microsoft Flow agora disponível para todos – inicialmente, abrimos a visualização para apenas endereços de email fornecidos pelo seu trabalho ou escola, como aqueles usados com o Office 365 Business ou o Office 365 Enterprise. Hoje, estamos anunciando que a versão prévia está oficialmente disponível, livre para uso, para todos os usuários, independentemente do email que você possa ter. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/available-for-everyone/) sobre esta versão.

### <a name="release-2016-08-31"></a>Versão de 2016-08-31
* **Condicionais aninhadas** – agora você pode adicionar uma segunda condição (ou terceira, etc...) dentro de outra.
* **Aplicar a cada** -um se aplicar a cada loop torna possível controlar a lista que você repete.
* O **loop do-until-a** do-until permite repetir uma etapa até que uma determinada condição seja atendida.
* **Filtrar matrizes** – há uma única etapa de filtro nativo que pode garantir que cada item da lista corresponda a alguma expressão que você definir.
* **Compor variáveis de cadeia de caracteres** – agora você pode compor uma variável de cadeia de caracteres.
* **Escopos** -escopos são uma maneira simples de agrupar duas ou mais ações.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/build-advanced-flows/) sobre esta versão.

### <a name="release-2016-08-27"></a>Versão de 2016-08-27
* **Comentários sobre etapas** -comentários facilitam a anotação de cada ação individual com anotações para que você possa se lembrar facilmente do que o fluxo precisa
* **Suporte do SmartSheet** – esta semana Adicionamos suporte para conexão com o SmartSheet. O SmartSheet é um serviço que torna mais fácil colaborar em planilhas na nuvem.
* **Refinamentos da interface do usuário ao criar fluxos** – fizemos o nome do fluxo no front-and-Center e Movei o botão Salvar para a parte superior da página para facilitar o acesso.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/add-comments-smartsheet/) sobre esta versão.

### <a name="release-2016-08-18"></a>Versão de 2016-08-18
Agora você pode visualizar a nova experiência de listas modernas do SharePoint Online que inclui a integração de Microsoft Flow. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) sobre esta versão.

### <a name="release-2016-08-13"></a>Versão de 2016-08-13
* **Visual Studio Team Services** -com o Flow, agora você pode conectar o VSTS a uma ampla variedade de serviços, como email do O365, margem de atraso, Trello e Wunderlist.
* **Aprimoramentos no SharePoint** – as listas do SharePoint dão suporte a uma variedade de tipos de dados de objetos simples, como linhas únicas de texto e data e hora, para objetos complexos, como pessoa ou grupo, pesquisa e escolha.
* **Testar conexões do O365 Outlook** – sempre que você criar uma nova conexão do o365 Outlook, agora vamos testá-la para verificar se você está pronto para usá-la.
* **Controle booliano** – também adicionamos um controle booliano para esclarecer quais valores você deve inserir para campos de entrada boolianos, como o tem anexos no gatilho quando um novo email chega.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) sobre esta versão.

### <a name="release-2016-08-08"></a>Versão de 2016-08-08
Visualização pública do Microsoft Common Data Service integrado no Microsoft Flow. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/flow-and-common-data-model/) sobre esta versão.

### <a name="release-2016-08-05"></a>Versão de 2016-08-05
* **SharePoint local** – assim como acontece com o SharePoint Online, você pode criar fluxos em suas listas locais do SharePoint e bibliotecas de documentos usando modelos predefinidos ou compilando-os do zero.
* **Info-Bubbles no designer** -para elaborar os recursos de cada gatilho e ação, adicionamos informações-bolhas acima de cada etapa do fluxo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) sobre esta versão.

### <a name="release-2016-07-15"></a>Versão de 2016-07-15
* **Quatro novos serviços adicionados** -Conecte-se ao Google Agenda, Google Tasks, YouTube e SparkPost.
* **Renomear suas ações** -agora, você pode contar com essas diferentes ações separadas renomeando-as.
* **Atraso para períodos diferentes de tempo** – agora você pode selecionar qualquer número de segundos, minutos, horas ou dias.
* **Navegador de pastas mais fácil de usar** -simplificamos o navegador de pastas. agora, a seleção à esquerda escolherá essa pasta e, à direita, será aberta a pasta para que você possa escolher as subpastas dentro.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/new-google-services-rename-more/) sobre esta versão.

### <a name="release-2016-07-08"></a>Versão de 2016-07-08
Conectividade local para Microsoft Flow usando o gateway de dados local. Isso permite que você estabeleça conexões seguras para SQL Server e integre-as com seus fluxos. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/on-premises-data-gateway/) sobre esta versão.

### <a name="release-2016-07-02"></a>Versão de 2016-07-02
* **Suporte do Google Sheets** – no passado, tivemos a capacidade de usar o Excel, bem como o Google Drive, mas esta semana estamos adicionando suporte nativo a planilhas do Google.
* Comece **mais rapidamente a partir de modelos** – também fizemos algumas otimizações para a maneira como você pode iniciar a partir de modelos. Agora, você pode selecionar as contas que deseja usar para um modelo de linha embutido na página do modelo.
* **Nenhuma autorização expirando para o SharePoint e o Office 365** -agora, Microsoft Flow irá renovar automaticamente o acesso a serviços baseados em Azure Active Directory, de modo que todos os fluxos continuarão funcionando nas alterações de senha.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/more-june-updates/) sobre esta versão.

### <a name="release-2016-06-20"></a>Versão de 2016-06-20
* **Apresentando o novo aplicativo móvel para Microsoft Flow** -hoje, temos o prazer de introduzir outra parte importante da nossa oferta: um aplicativo móvel agora disponível para download no IOS (em breve também no Android) que oferece a você o poder de gerenciar, controlar e explorar seu fluxos de trabalho automatizados a qualquer momento e em qualquer lugar.  
* **Logon único** – implementamos o logon único que permite que você se autentique em Microsoft Flow com outros serviços da Microsoft, como o Office 365.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) sobre esta versão.

### <a name="release-2016-06-18"></a>Versão de 2016-06-18
* **Novo serviço de email** -agora você pode enviar emails diretamente do Microsoft Flow, sem precisar se conectar às suas contas de email pessoais ou corporativas dentro do Microsoft Flow.
* **Notificações no portal** – agora, você verá notificações na parte superior do portal sempre que algo for quebrado com seus fluxos.
* **Todas as atividades no portal** – agora você pode ver a atividade em todos os seus fluxos clicando na guia nova atividade no site do Flow.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/mail-and-all-activity/) sobre esta versão.

### <a name="release-2016-05-27"></a>Versão de 2016-05-27
* **Procurar modelos por serviço** – há agora uma maneira de ver todos os serviços aos quais damos suporte (sem precisar fazer logon). Nessa página, você pode ver uma descrição de cada um dos serviços e conferir os modelos que temos para esse serviço.
* **Criar e usar seus conectores personalizados** – assim como você pode criar conectores personalizados no PowerApps, você também pode se conectar às suas próprias APIs diretamente em Flow.Microsoft.com:
* **Testar seus fluxos antes de concluir** – sempre que salvar um fluxo, agora você pode ver os resultados da execução do fluxo ao vivo na página, se você executar a ação inicial.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) sobre esta versão.

### <a name="release-2016-05-07"></a>Versão de 2016-05-07
Adicionados dois novos serviços: Microsoft Project online e Mandrill by MailChimp. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) sobre esta versão.

### <a name="release-2016-04-27---public-preview"></a>Versão 2016-04-27 – visualização pública
Se você usou fluxos lógicos como parte do [Microsoft PowerApps](https://powerapps.microsoft.com), a versão de visualização Microsoft Flow oferece vários recursos novos:

* Agora você pode navegar por uma galeria de dezenas de modelos e classificar por popularidade, nome ou data de publicação.
* Você pode [publicar seus próprios modelos](publish-a-template.md) na Galeria depois de personalizar um fluxo.
* Você pode ver o histórico de cada verificação e execução do seu fluxo.
* Ao salvar um fluxo, você pode [vê-lo em ação imediatamente](see-a-flow-run.md) executando apenas a ação de gatilho.
* Temos uma [nova comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) para que você discuta o fluxo ou [Envie suas ideias](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Próximas etapas
Se você tiver problemas que ainda não foram abordados nestas notas de versão ou nas [perguntas frequentes](frequently-asked-questions.md), junte-se à [nossa comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) para fazer perguntas ou [contate o suporte](https://go.microsoft.com/fwlink/?LinkID=787479).

