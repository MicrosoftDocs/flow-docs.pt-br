---
title: Notas da versão | Microsoft Docs
description: Problemas comuns e novidades das versões do Microsoft Flow
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
ms.openlocfilehash: 392a869d6b25bb16ee02a6bb3373d6edcf81621b
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58353138"
---
# <a name="release-notes"></a>Notas de versão
## <a name="top-questions"></a>Principais perguntas
1. Meu fluxo falhou. Como corrijo isso?
   
   1. Identifique a falha. Comece indo para o ícone de notificações na parte superior do portal da Web ou selecionando a guia **Atividade** no aplicativo móvel. Você deve ver seu fluxo existe lá e pode selecioná-lo.
   2. Agora você vê os detalhes do fluxo. Localize a etapa com o ícone de ponto de exclamação vermelho e você verá a mensagem de erro para o fluxo.
   3. Dependendo da mensagem de erro, você deve ser capaz de **Editar** o fluxo e corrigi-lo. [Leia mais sobre como corrigir falhas comuns de fluxos](fix-flow-failures.md).
2. Como usar uma condição avançada ou uma expressão?
   
   * Leia sobre como [adicionar condições](add-condition.md).
   * Se você quiser vários casos em um fluxo, selecione **Adicionar condição** de dentro de uma condição existente.
   * Crie uma expressão avançada referenciando [uma função em Aplicativos Lógicos](https://docs.microsoft.com/rest/api/logic/definition-language).
3. Como funciona o licenciamento com o Office 365?
   
   * Se você for um usuário do Office 365, terá acesso completo através do plano Microsoft Flow do Office 365. Para obter mais informações, confira os [planos de preços do Microsoft Flow](https://flow.microsoft.com/pricing/) .
   * Se você for um administrador, confira as informações sobre o [licenciamento do Microsoft Flow](organization-q-and-a.md), inclusive com o Office 365.

## <a name="known-issues"></a>Problemas conhecidos
1. Não há suporte para as listas do SharePoint em Meus Sites e que não são do tipo *Lista Personalizada*. Para solucionar esse problema, crie uma lista personalizada em um site do SharePoint padrão.
2. Os gatilhos do arquivo não serão acionados para os arquivos sendo adicionados dentro das pastas aninhadas dentro da pasta selecionada.

## <a name="whats-new"></a>Novidades

> [!IMPORTANT]
>
> **Anunciamos as notas de versão**
>
> Gostaria de saber mais sobre os últimos recursos lançados e o que vem por aí no Microsoft Flow?
>[Veja as notas sobre a versão de outubro de 2018](https://docs.microsoft.com/business-applications-release-notes/October18/microsoft-flow/). Reunimos todos os detalhes, de ponta a ponta, que você pode usar para o planejamento. Para mais detalhes, analise [cada versão semanal](https://docs.microsoft.com/business-applications-release-notes/powerplatform/released-versions/flow) com os recursos e aprimoramentos que ela contém.
>
> As notas sobre a versão anteriores à versão de outubro de 2018 continuarão aqui para referência no futuro; contudo, todas as novas versões só serão incluídas nos locais acima, não nesta página.

### <a name="release-2018-09-24"></a>Versão de 24-09-2018

- **Acesso de administrador à ajuda e suporte** – abra tíquetes de suporte para o Microsoft Flow no centro de administração da plataforma Power e forneça detalhes adicionais sobre a falha no fluxo de trabalho.
- **Remodelagem da Comunidade do Flow** – encontrar o que você precisa ficou mais fácil na Comunidade do Flow.
- **Aprimoramentos do conector do Microsoft Teams** – novos gatilhos do Microsoft Teams para que você possa executar um fluxo quando houver novas mensagens em um canal.
- **Mais ações do SharePoint** – há novas ações para a movimentação de arquivos no conector do SharePoint.
- **Novos relatórios de análise de administrador** – análises do Ambiente e do Locatário adicionadas ao Centro de administração da Plataforma de Aplicativo de Negócios.
- **Integração com o Power Query** – uma experiência do Power Query está sendo criada e permitirá que os criadores definam mashups de dados do SQL Server.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/support-tickets-teams-sharepoint/) sobre esta versão.

### <a name="release-2018-08-31"></a>Versão 2018-08-31

- **Teste seu fluxo usando dados de exemplo** – use dados de exemplo de conectores para testar seu fluxo conforme ele é criado de dentro do designer do Microsoft Flow. Ao testar seu fluxo com os dados de exemplo, você confirma que o fluxo será executado conforme o esperado quando ele for implantado para produção.
- **Cinco novos conectores** – adicionamos quatro novos conectores de gerenciamento: o PowerApps para criadores de aplicativos, a plataforma Power para administradores, o PowerApps para administradores, o Microsoft Flow para administradores e o Microsoft School Data Sync.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/test-data-management-connectors/) sobre esta versão.

### <a name="release-2018-08-24"></a>Versão 2018-08-24

- **Novos modelos de sincronização de calendário** – novos modelos de calendário que copiam eventos entre o Google Agenda e o Office 365 ou o Outlook.com.
- **Suporte a vários valores para o SharePoint** – leia e grave em campos com vários valores no SharePoint que são dos tipos Escolha, Pessoa ou Pesquisa.
- **Envie aprovações em nome de outros usuários em sua organização** – envie aprovações em nome de outros usuários na sua organização, por exemplo, a pessoa que carregou o arquivo na lista do SharePoint, em vez da pessoa que criou o fluxo.
- **Mais tipos de entrada de botão** – os botões têm dois novos tipos de entrada: Número e Sim/Não.
- **Atualizações do conector** – um novo conector do NetDocuments, aprimoramentos aos conectores do Azure e muito mais.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-types-more/) sobre esta versão.

### <a name="release-2018-08-02"></a>Versão 2018-08-02

O programa de versão prévia do Microsoft Flow é a maneira de obter acesso antecipado a funcionalidades futuras e atualizações para o Microsoft Flow. Para obter acesso antecipado a funcionalidades mais recentes, basta criar e, em seguida, usar um ambiente na região de Versão prévia.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/flow-preview-program/) sobre esta versão.

### <a name="release-2018-07-23"></a>Versão de 23-07-2018

- **Criar e executar fluxos no Excel** – com o novo botão **Fluxo** (acessado na guia **Dados** na faixa de opções), você pode criar e disparar automações do Microsoft Flow nos dados da tabela no Excel. Automatize o processamento de dados ou a cópia/importação dos dados.
- **Criar um fluxo do processo empresarial** – um fluxo do processo empresarial é um novo tipo de fluxo interativo para pessoas, com estado, baseado no Common Data Service. Use esses novos fluxos para definir um conjunto de estágios e etapas para as pessoas seguirem. É possível mover-se para frente e para trás, conforme necessário.
- **Criar um fluxo para o Microsoft To-Do no Outlook Web App** – se alguém for \@mencionado no Outlook Web App, ele verá um atalho para criar um fluxo. Este fluxo cria automaticamente as tarefas para a pessoa \@mencionada no Microsoft To-Do, com base no conteúdo do email.
- **Suporte ao modo de exibição do SharePoint** – o conector do SharePoint agora suporta a seleção de um modo de exibição específico do SharePoint em gatilhos e ações. Isso filtra as colunas para apenas os campos que estão no modo de exibição selecionado.
- **Quatro novos conectores** – adicionado o Azure IoT Central – uma solução de software como serviço (SaaS) de IoT altamente escalonável – Survey 123, LMS365 e ProjectWise Design Integration.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/excel-bpf-todo-and-more/) sobre esta versão.

### <a name="release-2018-06-29"></a>Versão de 29-06-2018

- **Fluxo de solicitação de aprovação integrado no SharePoint** – ao selecionar um arquivo ou item no SharePoint, você verá um novo fluxo de **Solicitação de aprovação**. Este fluxo não requer nenhuma configuração ou instalação e envia uma solicitação de aprovação com um único clique.
- **Dois novos conectores** – adicionados o Cloud Connect Studio e PoliteMail.
- **Aprimoramentos no histórico e criar página** – estamos atualizando a lista Histórico de execuções para incluir os tempos exatos de execução, e o Criar página adicionando um novo vídeo passo a passo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/request-sign-off-four-connectors/) sobre esta versão.

### <a name="release-2018-06-08"></a>Versão de 08-06-2018

- **Cmdlets do PowerShell** – os criadores de fluxo e os administradores de locatários agora podem usar o PowerShell para gerenciar seus fluxos de forma programática.
- **Melhorias no bot do Flow no Teams** – o bot do Flow no Microsoft Teams pode executar botões de fluxo e descrever seus fluxos.
- **Três novos conectores** – adicionado suporte ao Marketo, ElasticOCR e DynamicSignal. 
- **Informações adicionais de compartilhamento** – adicionadas outras informações ao compartilhar ou executar fluxos compartilhados, para que você saiba exatamente quais permissões as outras pessoas receberão.
- **URLs do SharePoint de filtragem automática** – ao copiar e colar uma URL do SharePoint no navegador, ela pode conter texto adicional além do site, esse texto será removido automaticamente para que você possa se conectar apenas no site.
- **Documentação sobre solicitações de RGPD** – criamos um guia abrangente e um conjunto de ferramentas para organizações empresariais manusearem as solicitações de Direitos dos Titulares dos Dados.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/powershell-flow-bot-marketo/) sobre esta versão.

### <a name="release-2018-05-21"></a>Versão de 21-05-2018

- **Fluxos "pertencentes" a bibliotecas e listas do SharePoint** – os fluxos que funcionam com as listas e bibliotecas do SharePoint podem ser compartilhados com essas listas ou bibliotecas. Portanto, em vez de ser compartilhado com indivíduos ou grupos, eles são compartilhados com qualquer pessoa que tenha acesso à lista. Quando os usuários são adicionados ou removidos da lista ou da biblioteca, sua participação é alterada automaticamente de acordo com a ação executada.
- **Análise de detalhes do erro** – um novo relatório inserido que fornece informações sobre todos os erros que ocorrem dentro de um fluxo.
- **Compartilhar fluxos com grupos do Office 365** – você pode fazer com que um grupo moderno do Office 365 seja o proprietário de um fluxo e pode compartilhar fluxos de botão com os grupos do Office 365 para que qualquer pessoa no grupo possa executar o fluxo.
- **Melhorias do conector do SharePoint** – há duas novas funcionalidades do conector do SharePoint: disparar fluxos quando arquivos ou itens são excluídos e chamar um ponto de extremidade HTTP compatível com a API REST do SharePoint.
- **Dois novos conectores** – foi adicionado o suporte para o Azure Data Factory e o MailParser

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/share-with-sharepoint-office-365/) sobre esta versão.

### <a name="release-2018-05-01"></a>Versão 01-05-2018

- **Rich text em mensagens de aprovação** – use Markdown para formatar os detalhes da aprovação que você envia.
- **Botões com várias entradas de seleção** – crie botões de fluxo que usam uma lista de seleção múltipla para coletar mais de um valor por vez.
- **Trabalhar com fluxos maiores** – o aplicativo móvel Microsoft Flow agora dá suporte ao modo de exibição de paisagem e o designer da Web apresenta uma barra de rolagem horizontal.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/rich-approvals-text-and-multiselect/) sobre esta versão.

### <a name="release-2018-04-12"></a>Versão 2018-04-12

- **Retornar dados para o PowerApps de um fluxo** – Criar fluxos que podem ser chamados de um aplicativo criado com o PowerApps e retornar dados de volta para o aplicativo. Use o designer de fluxo visual do tipo “arrastar e soltar” para criar a lógica necessária para seus aplicativos. 
- **Adicionar vários registros a entradas de matriz** – Foi adicionado um construtor de lista no Microsoft Flow que pode ser usado para adicionar vários anexos a um email, por exemplo.
- **Testar os fluxos com os dados de execução anterior** – Foi adicionado um novo botão de fluxo de teste ao designer que permite que você teste seu fluxo com os dados de gatilho da execução de fluxo anterior.
- **Novos campos workflow()** – Agora você pode acessar o nome de ambiente e o nome de exibição do fluxo com a expressão workflow().

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/return-data-to-powerapps/) sobre esta versão.

### <a name="release-2018-04-04"></a>Versão 2018-04-04

- **Aprovações no Common Data Service** – as aprovações modernas são criadas na versão mais recente do Common Data Service. Isso significa que você pode criar fluxos que leem o status das aprovações enviadas ou recebidas com o conector do Common Data Service.
- **Localizar erros em aplicar a cada** – Saltar diretamente para erros em loops na exibição de execução de fluxo, mesmo quando houver centenas de itens no loop.
- **Reatribuir aprovações** – Você pode atribuir qualquer aprovação recebida a outra pessoa em sua organização para delegar a aprovação para essa pessoa. 
- **Listas de salas** – O conector do Outlook do Office 365 adicionou ações para obter dados de sala em sua organização.
- **Ver detalhes dos botões de fluxo** – Ao executar um fluxo que foi compartilhado com você, agora você pode ver todas as ações que o fluxo usa.
- **Região do Reino Unido** – Agora os ambientes podem ser criados para armazenar seus dados no Reino Unido.
- **Dois novos conectores** – Foi adicionado suporte para o AtBot Admin e o Marketing Content Hub.
- **Nova página de aterrissagem da documentação** – Foi atualizada a página de aterrissagem da documentação para ter conteúdo agrupado por você: usuário iniciante, intermediário ou especialista. 

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/approvals-in-cds-and-seven-updates/) sobre esta versão.

### <a name="release-2018-03-13"></a>Versão 2018-03-13

- **Histórico de aprovação** – Veja todas as solicitações de aprovação que você enviou, incluindo as respostas, os comentários enviados e a hora exata em que aconteceram.
- **Quatro novos conectores** – Foram adicionados o Excel Online (comercial), o Excel Online (OneDrive), o SQL Data Warehouse do Azure e a Calculadora de tributos Pitney Bowes.
- **Dicas de ferramenta de conteúdo dinâmico** – Focalize conteúdo dinâmico para ver de onde ele veio dentro de ações e visualize expressões sem abrir o editor de expressão completa.
- **Controle de simultaneidade** – Habilite o controle de simultaneidade para que determinado fluxo tenha apenas uma execução por vez.
- **Repetição exponencial** – Um novo tipo de política de repetição que aumenta os intervalos das repetições exponencialmente ao longo do tempo.
- **Conformidade de acessibilidade** – Foram liberados novos documentos de conformidade que descrevem como o Microsoft Flow atende aos padrões de acessibilidade.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/approval-history-accessibility/) sobre esta versão.

### <a name="release-2018-02-09"></a>Versão 2018-02-09

- **Alta disponibilidade do gateway** – criar clusters altamente disponíveis dos gateways de dados locais, para manter as conexões funcionando quando ocorrerem falhas em computadores únicos.
- **Aplicação aprimorada em cada** – com o processo do Plano 1 do Flow ou Plano 2 do Flow até 100.000 itens eu uma única execução e 50 ações em paralelo em loops de Aplicar em cada. 

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each/) sobre esta versão.

### <a name="release-2018-01-29"></a>Versão 2018-01-29

- **Flow dentro do Microsoft Teams** – no Teams, você pode criar e gerenciar fluxos, examinar suas aprovações recebidas e enviadas, e iniciar fluxos diretamente dentro do aplicativo de área de trabalho do Teams ou em teams.microsoft.com – [Saiba mais aqui](https://flow.microsoft.com/blog/microsoft-flow-in-microsoft-teams/).
- **Notificações de edição compartilhadas** – sempre que um fluxo de sua propriedade for alterado por um colega de trabalho, você receberá uma notificação por email informando quem alterou o fluxo.
- **Novas expressões** – adicionados dois novos conjuntos de expressões: um para analisar URLs e outro para trabalhar com objetos JSON.
- **Três novos conectores** – esta semana há dois novos conectores Plumsail: Plumsail SP e Plumsail Forms, e um novo conector para Kintone.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/shared-notifications-and-expressions/) sobre esta versão.

### <a name="release-2018-01-17"></a>Versão 2018-01-17

- **Informações de perfil do Office 365** – adicionamos novas ações ao conector de usuários do Office 365 que funcionam com perfis de usuário e fotos.
- **Acrescente a variáveis de cadeia de caracteres** – você pode adicionar a cadeias de caracteres dentro de loops para criar tabelas ou outras listas.
- **Conector Infobip** – Infobip é um serviço que permite a comunicação de nível empresarial, incluindo chamadas de voz e disparo de SMS de entrada.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/o365-profile-infobip/) sobre esta versão.

### <a name="release-2017-12-20"></a>Versão de 20-12-2017

O Microsoft Flow Analytics agora está disponível em todas as regiões do Microsoft Flow, o que significa que você consegue obter mais informações sobre a integridade dos fluxos sendo executados em seu ambiente.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-analytics/) sobre esta versão.


### <a name="release-2017-12-14"></a>Versão de 14-12-2017

- **Melhorias no conector do Outlook** – você pode salvar um email como um arquivo ".eml", responder a convites do calendário automaticamente e disparar fluxos quando for mencionado em um thread de emails.
- **Melhorias de conexões** – o Microsoft Flow lembra das suas conexões usadas mais recentemente e mostra todos os conectores novos adicionados.
- **Cinco novos conectores** – foram adicionados Instâncias de Contêiner do Azure, Azure Kusto, Metatask, Microsoft To-Do e Documentos do Plumsail.
- **Melhorias de HTTP**  – a ação de HTTP agora oferece suporte para codificação em bloco.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/outlook-connector-more/) sobre esta versão.

### <a name="release-2017-12-05"></a>Versão de 05-12-2017

Agora o Painel de Lançamento do Microsoft Flow está disponível em todas as regiões. Esse painel permite que você adicione valores a um fluxo ao executá-lo dentro da sua lista do SharePoint ou da biblioteca de documentos.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/introducing-flow-launch-panel-in-sharepoint-lists-and-libraries/) sobre esta versão.


### <a name="release-2017-11-28"></a>Versão de 28-11-2017

- **Metadados Gerenciados** – leia dados ou grave-os em colunas no SharePoint que usa o tipo de Metadados Gerenciados (também conhecido como Taxonomia).
- **Acrescentar a Matrizes** – adicione itens ao final de matrizes usando uma nova ação variável de Acrescentar à matriz.
- **Tago** – um novo conector ao Tago, que fornece fácil conexão de dispositivos eletrônicos com dados externos para levar a decisões mais inteligentes usando a análise contextual.
- **iPhone X** – uma nova versão do aplicativo Microsoft Flow, que usa a tela inteira no iPhone X e que apresenta melhoria de velocidade para carregamentos de imagem.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/managed-metadata-tago/) sobre esta versão.

### <a name="release-2017-11-09"></a>Versão de 09-11-2017

- **Integração do OneDrive para Empresas** – agora existe um [botão de fluxo dentro do OneDrive para Empresas](https://flow.microsoft.com/blog/microsoft-flow-integration-in-one-drive-for-business-and-new-connector-actions/) que pode criar ou disparar fluxos em arquivos ou pastas selecionados.
- **Gatilhos do Planner** – inicie os fluxos quando uma nova tarefa é criada, quando uma tarefa é atribuída a você ou quando uma tarefa é concluída.
- **Anexos do SharePoint** – trabalhe com anexos nos itens de lista do SharePoint: listar, baixar, adicionar ou excluir anexos.
- **Conector de gerenciamento de fluxo** – crie fluxos que automatizam o gerenciamento de outros fluxos em seu ambiente (por exemplo, adicionar permissões ao fluxo automaticamente).
- **Quatro novos conectores** – foram adicionados: Serviço de Visão Personalizada do Azure, D&B Optimizer, Enadoc e Derdak SIGNL4. 
- **Mais ações do conector** – execute consultas SQL, obtenha gatilhos de email mais rápidos, use qualquer método com HTTP com o Azure AD e muito mais.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/planner-triggers-connector-improvements/) sobre esta versão.

### <a name="release-2017-11-02"></a>Versão de 02-11-2017

- **Log de auditoria** – agora os eventos de auditoria do Microsoft Flow estão disponíveis no Centro Segurança e Conformidade do Office 365 para todos os locatários.
- **Correções no widget do Flow** – foi corrigido um problema no aplicativo móvel do Flow que fazia com que os botões não carregassem no widget.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/security-and-compliance-center/) sobre esta versão.

### <a name="release-2017-10-19"></a>Versão de 19-10-2017

- **Aplicação aninhada em cada** – é possível adicionar aplicação a cada ação, filtrar e selecionar outras aplicações a cada ação de contêiner.
- **Ações de data e hora** – novas ações para obtenção de horas locais, adição, subtração ou formatação de horas.
- **Quatro novos conectores** – foram adicionados: Content Moderator, Docparser, Microsoft Kaizala e validação de dados do Pitney Bowes.
- **Melhor experiência de conexão** – notificações no portal do Microsoft Flow quando uma conexão é interrompida, além de detalhes mais avançados de conexão.
- **Coleção em qualquer lugar** – uma nova coleção de modelo para [trabalhadores em qualquer lugar](https://flow.microsoft.com/collections/onthego/).
- **Entradas do botão Endereço de email** – coletar endereços de email dos usuários ao executarem botões.
- **Entradas do botão Arquivo** – obter arquivos carregados, como fotos, dos usuários ao executarem botões.
- **Primeira execução e entrada automática** – aprimorada as experiências de primeira execução no aplicativo móvel, incluindo a entrada automática.
- **Gatilhos mais rápidos do Microsoft Forms** – o Forms vai disparar gatilhos muito mais rapidamente do que antes (anteriormente era uma vez por hora).
- **Entradas de botão entre sessões** – botões disparados em seu telefone celular lembrarão entradas anteriores.
- **Feed de atividades móveis** – feed de atividade aprimorado para incluir resumos de execução mais detalhados e detalhes da solução de problemas.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/nested-apply-to-each/) sobre esta versão.

### <a name="release-2017-10-03"></a>Versão de 03-10-2017

- **Todos devem aprovar** – exige que uma solicitação de aprovação enviada para mais de uma pessoa seja aprovada por todos que a receberam.
- **Novas ações do OneDrive para Empresas** – gerar PDFs para arquivos armazenados no OneDrive para Empresas e quatro outras novas ações.
- **Conector do Apache Impala** – o Apache Impala (em encubação) é o banco de dados analítico nativo e de software livre do Apache Hadoop.
- **Adicionar descrições de fluxo** – dê descrições aos seus fluxos ao compartilhá-los para que seus colegas possam ver um resumo do que o fluxo faz.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/all-must-approve-and-onedrive/) sobre esta versão.

### <a name="release-2017-09-25---q3-update-for-microsoft-flow"></a>Versão de 25-09-2017 – Atualização do terceiro trimestre do Microsoft Flow

- **Integração mais profunda do SharePoint na primeira versão** – há um novo envio “na caixa” para fluxos de revisão e um painel do Flow para coletar entradas ao executar um fluxo para locatários da primeira versão.
- **Dynamics 365 para Compromisso com o Cliente** – agora o Flow está integrado à interface de usuário do Dynamics 365 para Compromisso com o Cliente.
- **Central de Confiabilidade da Microsoft** – o Microsoft Flow está listado na Central de Confiabilidade da Microsoft, mostrando certificações como HIPAA, ISO e SOC.
- **Análise de uso** – cada fluxo tem um painel inserido do Power BI com análise de uso básico.
- **Log de auditoria na primeira versão** – todos os eventos de gerenciamento de fluxo são registrados no Centro de Conformidade e Segurança do Office 365 para locatários da primeira versão.
- **Seis novos conectores** – foram adicionados: LinkedIn, Grupos do Office 365, Skype for Business, Adobe Sign, Bizzy e Coleta de dados Azure Log Analytics.
- **Gatilhos do SQL** – execute fluxos quando uma nova linha for adicionada ou for atualizada em uma tabela do SQL.
- **Conectores locais personalizados** – agora conectores personalizados podem usar o gateway de dados local para se conectarem aos pontos de extremidade internos da sua rede.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/q3-2017-update/) sobre esta versão.

### <a name="release-2017-09-21"></a>Versão de 21-09-2017

- **Baixar o histórico do Flow** – baixe o histórico de execução de um fluxo como arquivo CSV para abrir no Excel.
- **Recorrência avançada** – compile agendas recorrentes para disparar os fluxos, por exemplo: disparar somente em dias da semana.
- **IntelliSense** – ao digitar expressões, o IntelliSense fornecerá sugestões para parâmetros.
- **Quatro novos conectores** – foram adicionados conectores para serviços HTTP do Azure AD, Amazon Redshift, Publicação da Grade de Eventos do Azure e FlowForma.
- **Compartilhando links** – uma nova ação para gerar links compartilháveis para arquivos do OneDrive ou Azure Storage Blob.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/download-history-recurrence/) sobre esta versão.


### <a name="release-2017-08-25"></a>Versão de 25-08-2017
* **Propriedades do documento e mais para o SharePoint** - [Leia e defina as propriedades da biblioteca de documentos do SharePoint](https://flow.microsoft.com/blog/support-for-sharepoint-document-library-properties/) e use os campos adicionais como links para o item do SharePoint.
* **Coleções de fluxo** - as coleções de fluxo são um conjunto de coleções de modelo organizadas por função ou na vertical.
* **Novo compartilhamento de botão** - quando você compartilha botões com seus colegas de trabalho, eles podem compartilhá-lhos novamente com outras pessoas também.
* **Coletar listas de botões** - defina listas suspensas de opções para os usuários escolherem quando tocarem no botão.
* **Sete conectores novos** - AWeber, Azure Log Analytics, Tabelas do Azure, DocFusion365, Grade de Eventos do Azure, Hubs de Eventos do Azure e StaffHub. 
* **Melhorias no Slack e MySQL** - crie ou adicione canais no Slack e você poderá gravar nos bancos de dados MySQL.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-updates-seven-connectors/) sobre esta versão.

### <a name="release-2017-08-02"></a>Versão 02-08-2017
* Os **campos de gravação da Pessoa, Escolha e Pesquisa** - Criar item e Atualizar item do SharePoint[agora dão suporte à capacidade de](https://flow.microsoft.com/blog/setting-sharepoint-s-person-choice-and-lookup-fields/) definir os campos Pessoa, Escolha e Pesquisa.
* **Mais configurações de ação** - Agora, há mais controle sobre como os gatilhos e ações são executados, incluindo como configurar as políticas de repetição e a paginação.
* **Quatro novos conectores** -Agora, você pode usar o Armazenamento de Arquivos do Azure, Formulários Elásticos, Plivo e Video Indexer.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/four-connector-action-settings/) sobre esta versão.

### <a name="release-2017-07-27---q2-update-for-microsoft-flow"></a>Versão de 27-07-2017 - Atualização Q2 do Microsoft Flow
* **Importar e exportar** -Exporte e importe soluções de fluxo nos ambientes ou no teste para produção. 
* **Usar expressões em ações** - Insira expressões em qualquer ação e obtenha ajuda em linha com o modo de usá-las.
* **Desenvolver para Aplicativos Lógicos do Azure** - Salve seus fluxos como um recurso do Aplicativo Lógico do Azure que pode ser implantado com o Visual Studio ou o portal do Azure.
* **Visibilidade do administrador** -Baixe o uso do Microsoft Flow no seu locatário para entender exatamente onde e como os fluxos estão sendo usados.
* **Fluxos no Dynamics 365** -Use fluxos dentro do 365 Dynamics para Operations & Financials, Business Edition.
* **Localizar os cenários mais facilmente** - Procure tudo o que esse conector pode fazer e use qualquer gatilho como um ponto de partida para criar fluxos.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/q2-2017-update/) sobre esta versão.

### <a name="release-2017-07-13"></a>Versão 13-07-2017
* **Melhor publicação do modelo** - Publique qualquer fluxo criado, junto com suas categorias, na galeria pública.
* **Obter eventos no Calendário do Outlook** - Uma nova ação para retornar todos os eventos entre duas datas no calendário.
* **Nova funcionalidade móvel** - Execute os fluxos sob demanda e reenvie as execuções com falha no aplicativo móvel.
* **Menus suspensos dinâmicos nos Conectores personalizados** - Crie menus suspensos dinâmicos, gatilhos de sondagem e teste seus conectores personalizados.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/publishing-and-custom-connectors/) sobre esta versão.

### <a name="release-2017-06-28"></a>Versão 28-06-2017
* **Atualize suas configurações de idioma** - Você pode personalizar o Idioma e a Região que o Microsoft Flow usa por meio do menu Configurações.
* **Cinco novos conectores** - Suporte adicionado para Adobe Creative Cloud, Bing Maps, Bing Search, JotForm e Freshservice.
* **Defina os tempos limite** - Altere as ações de longa duração de tempo, como as aprovações, executadas antes de "expirar" e o fluxo continuar.
* **Incluir comentários no Outlook para aprovações** - Quando você receber uma solicitação de aprovação, poderá fornecer comentários sem sair do Outlook.
* **Cores de marca do conector personalizado** -Agora você pode inserir uma cor para os Conectores Personalizado que serão usados para os planos de fundo.
* **Salvar como para fluxos de equipe** - Faça cópias de qualquer fluxo, incluindo fluxos de Equipe
* **Excluir informações de fluxo** - Ao excluir um fluxo, será exibida a lista de todas as execuções pendentes para esse fluxo.
* **Filtragem na página de Conectores** -Pesquise os conectores desejados na página de Conectores e filtre por tipo de conector.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/language-settings-3-connectors/) sobre esta versão.

### <a name="release-2017-06-19"></a>Versão 19-06-2017
Agora você pode exibir o status de todas as solicitações de aprovação pendente que você enviou. Além disso, você pode procurar e agir em todas as suas aprovações pendentes diretamente em seu dispositivo móvel.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/sent-requests-flow-mobile/) sobre esta versão.

### <a name="release-2017-06-15"></a>Versão 15-06-2017
* **Conversão de conteúdo** - Um novo conector que pode converter o conteúdo HTML em texto sem formatação, útil para lidar com emails HTML formatados.
* **Três novos conectores de banco de dados** -Foi adicionado suporte somente leitura para MySQL, PostgreSQL e Teradata. Esses conectores se conectam por meio do gateway de dados local.
* **Três outros conectores** - Conecte-se ao Azure Application Insights, Calendly e Projetos de Equipe.
* **Melhor visualização para tratamento de erros** - As etapas executadas após os erros agora são exibidas com as setas vermelhas pontilhadas para que você possa identificá-las facilmente.
* **Executar o painel de detalhes** - Agora, quando um fluxo falha, há um novo painel à direita que contém algumas etapas úteis para saber como corrigir seu fluxo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/seven-connectors-and-html/) sobre esta versão.

### <a name="release-2017-06-04"></a>Versão 04-06-2017
* **GA para Windows Phone** - [O aplicativo móvel Microsoft Flow foi lançado para Disponibilidade Geral para Windows Phone](https://flow.microsoft.com/blog/announcing-flow-windows-phone-app/).
* **Emails em falhas de fluxo** - Receba notificações por email quando tiver falha em um fluxo. Esses emails de falha serão enviados apenas uma vez por semana e podem ser ativados ou desativados pelo usuário.
* **Selecionar a ação das tabelas** - Use a nova ação Selecionar para alterar o conjunto de colunas que serão incluídas nas tabelas.
* **Conector do Microsoft Forms** - O Microsoft Forms é uma nova parte do Office 365 Education que permite aos professores e alunos criarem testes personalizados rapidamente e facilmente, além de pesquisas, questionários, registros e muito mais.
* **Plano K1 do Office 365 Enterprise** - O PowerApps e o Microsoft Flow agora estão incluídos com o plano K1 do Office 365 Enterprise com determinadas cotas.
* **Os cabeçalhos HTTP são mais fáceis** - Tal como a ação Selecionar, você pode fornecer um nome de cabeçalho e um valor de cabeçalho preenchendo apenas as caixas de texto na ação.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/microsoft-forms-tables-flow-failures/) sobre esta versão.

### <a name="release-2017-05-23"></a>Versão 23-05-2017
* **Conector do Microsoft Teams** - [Microsoft Teams](https://flow.microsoft.com/blog/introducing-the-microsoft-teams-connector-for-flow/) é um workspace com base no bate-papo no Office 365 que une pessoas, conversas e conteúdo – juntamente com as ferramentas que as equipes necessitam, para que eles possam facilmente colaborar para atingir mais.
* **Widgets em iOS e Android** -Os widgets Microsoft Flow são atalhos do botão que fornecem uma maneira mais fácil e rápida para acionar o botão diretamente da sua tela inicial.
* **Criar etapas de "tratamento de erro"** - Definir uma ou mais etapas para executar após a falha de uma ação. Por exemplo, receber uma notificação imediatamente se seu fluxo não pode criar um registro no Dynamics 365.
* **Variáveis de inteiro e flutuantes** - Inicializar e incrementar ou decrementar contadores dentro de uma execução de fluxo para contar quantas vezes um determinado conjunto de lógica é executado.
* **Página de detalhes do fluxo** - Ao selecionar um fluxo em sua lista **Meus fluxos**, você verá uma página com detalhes sobre esse fluxo, como quem tem acesso e o histórico de execução.
* **Cotas de execução de fluxo para administradores** - Os administradores agora podem monitorar o uso de execução de fluxo em toda a organização em relação à cota de execução comum da empresa e obter uma análise de cota para entender quais licenças contribuem com sua cota.
* **Aprimoramentos de gatilho de solicitação HTTP** - Use métodos diferentes de HTTP e adicione segmentos de caminho para o disparador de Solicitação.
* **Conectores de dois parceiros** - O Microsoft Flow agora pode se conectar ao Parserr, um serviço de análise de email e formulários Cognito, um serviço de formulários on-line.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/error-handling/) sobre esta versão.

### <a name="release-2017-05-12"></a>Versão 12-05-2017
* **Integração de Bibliotecas de Documentos do SharePoint** - Você pode selecionar qualquer arquivo em uma biblioteca de documentos e reproduzir um fluxo, por exemplo, para enviá-lo ao seu gerente para aprovação, [e muito mais](https://flow.microsoft.com/blog/flow-in-spo-document-libraries/).
* **Conector do Microsoft Planner** - O Microsoft Planner permite que você facilmente reúna equipes, tarefas, documentos e conversas para obter resultados melhores.
* **Exibição do administrador de licenças** - Os administradores podem ver todas as licenças do Microsoft Flow e PowerApps (avaliação e pagas) no Microsoft Flow Admin Center.
* **Plano de Comunidade do PowerApps** - A Comunidade do PowerApps é um plano gratuito para que as pessoas possam explorar, aprender e desenvolver habilidades para PowerApps, Microsoft Flow e Serviço de Dados Comum.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/planner-community-and-licenses/) sobre esta versão.

### <a name="release-2017-05-09"></a>Versão 09-05-2017
* **Conector do Azure AD** -Há um novo conector para executar as ações do administrador do Microsoft Flow, inclusive criar usuários ou adicioná-los a grupos.
* **Aprimoramentos do Office 365 Outlook** -os fluxos agora podem ser acionados por Caixas de Correio Compartilhadas e enviar email a uma Caixa de Correio Compartilhada. Eles também podem definir ou ler respostas automáticas.
* **Disponível no Canadá** -Agora você pode criar seus fluxos no Canadá.
* **Criar webhooks de API personalizada** - Desenvolvedores de conectores personalizados agora podem adicionar gatilhos a suas APIs personalizadas com webhooks.
* **Gerenciar proprietários de fluxo no Centro de administração** - Os administradores de ambiente podem gerenciar proprietários de fluxo no Centro de administração do Microsoft Flow.
* **Referência de documentação do conector** -Agora temos uma [referência completa do conector em docs.microsoft.com](https://docs.microsoft.com/Connectors/).
* **Dois serviços de parceiro** – Dois novos serviços de parceiro lançados: Nexmo e Paylocity.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/canada-mailboxes-aad) sobre esta versão.

### <a name="release-2017-04-27"></a>Versão 27-04-2017
* **Criar fluxos com etapas paralelas** - Criar fluxos com execução paralela: ou seja, você pode ter duas ou mais etapas que são executadas exatamente ao mesmo tempo.
* **Cinco novos serviços com suporte** – cinco novos serviços: Aprovações, Email de Parâmetro de Comparação, CRM de Cápsula, LiveChat e Gerenciador de Clientes do Outlook.
* **Monitorar tentativas para ações** - O Microsoft Flow tentará novamente quando houver falhas com os serviços. Agora, confira os detalhes do que aconteceu e quantas tentativas automáticas ocorreram.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/parallel-actions/) sobre esta versão.

### <a name="release-2017-04-17---q1-update-for-microsoft-flow"></a>Versão 17-04-2017 - Atualização Q1 do Microsoft Flow
* **Experiências de aprovação modernas** - Crie fluxos de trabalho onde os aprovadores podem aprovar com segurança de dentro do aplicativo móvel do Microsoft Flow ou do centro de aprovações unificadas no site do Microsoft Flow.
* **Disponibilidade geral de fluxos de equipe** - Várias pessoas podem possuir e gerenciar um fluxo com fluxos de equipe, que agora estão disponíveis.
* **Criar conectores para o Microsoft Flow** - Qualquer pessoa pode enviar seu próprio conector do Microsoft Flow gratuitamente para o resto do mundo usar.
* **Um designer leve** - Para alguns modelos, uma nova versão do designer apresenta apenas os campos que são necessários para criar um fluxo, o que simplifica a experiência.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/q1-2017-update/) sobre esta versão.

### <a name="release-2017-04-11"></a>Versão 04-11-2017
* **Novas ações para criar tabelas e listas** - Nova tabela Criar HTML, Criar Tabela de CSV e Ações de junção que podem processar listas de itens (em vez dos anteriores Aplicar para cada somente).
* **Inserir etapas em qualquer lugar** - Agora você pode inserir uma nova etapa em qualquer lugar no fluxo de trabalho sem a necessidade de arrastar e soltar.
* **Quatro novos serviços** - O Flow agora oferece suporte ao Agendamento de 10 a 8, Act!, Inoreader e a API da Pesquisa Visual Computacional. Com a API da Pesquisa Visual Computacional você pode processar imagens para obter o conteúdo de texto (conhecido como OCR) ou marcar automaticamente imagens com base em seu conteúdo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/html-tables-csvs-computer-vision/) sobre esta versão.

### <a name="release-2017-04-03"></a>Versão 03-04-2017
* **Versão Beta do Windows Phone** - O programa beta do Aplicativo do Windows Phone está disponível para obter uma visualização do aplicativo em seu Windows Phone. [Leia mais](https://flow.microsoft.com/blog/windows-phone-app-beta-is-now-available/).
* **PDF Muhimbi** - Agora você pode converter arquivos do Microsoft Word para PDF, adicionar marcas d'água, mesclar documentos e muito mais com o PDF Muhimbi. [Leia mais](https://flow.microsoft.com/blog/convert-files-using-muhimbi/).
* **Disparar fluxos de botões físicos** – anunciamos parcerias com dois dos principais produtos no espaço de botão físico: Flic by Shortcut Labs e Bttn by The Button Corporation. [Leia mais](https://flow.microsoft.com/blog/physical-buttons/)

### <a name="release-2017-03-22"></a>Versão 22-03-2017
* **Faça uma cópia do seu fluxo** - Agora você pode fazer uma cópia do seu fluxo para trabalhar em versões de rascunho ou duplicar um fluxo que você criou anteriormente.
* **Dois novos serviços** - Adicionando suporte para Toodledo - gerencie sua lista de tarefas criando e atualizando tarefas e Zendesk, que fornece um serviço de cliente e suporte à plataforma de emissão de tíquetes.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/make-a-copy/) sobre esta versão.

### <a name="release-2017-03-15"></a>Versão 15-03-2017
* **Compartilhar botões com colegas de trabalho** - agora você pode compartilhar botões de fluxo com outras pessoas, tornando mais fácil para qualquer usuário empresarial executar tarefas rápidas.
* **Disparar botões na tela inicial** - atalhos para os botões de fluxo das telas iniciais e de bloqueio de dispositivos móveis torna mais rápido do que nunca disparar um fluxo.
* **Fluxos de equipe no aplicativo Microsoft Flow** - agora você pode ver os fluxos que têm outros proprietários no aplicativo Microsoft Flow para iOS ou Android.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-sharing/) sobre esta versão.

### <a name="release-2017-03-10"></a>Versão 10-03-2017
* **Experiência melhorada de conector personalizado** - Agora você pode usar uma coleção Postman para criar um conector personalizado, editar, adicionar e testar ações.
* **Dois novos serviços** - notificações do PowerApps adicionadas e suporte do PivotalTracker.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/new-updates-custom-api/) sobre esta versão.

### <a name="release-2017-02-27"></a>Versão 27-02-2017
* **Disparar os botões de fluxo** – agora você pode disparar botões de fluxo diretamente do Microsoft Flow. Ao examinar sua lista de fluxos, selecione o menu "…" e escolha o comando Executar agora.
* **Cinco novos serviços** - suporte adicionado do Oracle Database, Intercom, FreshBooks, LeanKit e WebMerge.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/trigger-flow-buttons-web/) sobre esta versão.

### <a name="release-2017-02-21"></a>Versão 21-02-2017
* **Exibir fluxos de ambiente** - os administradores de ambiente agora podem exibir a lista completa de todos os fluxos dentro de um determinado ambiente, bem como habilitar, desabilitar ou excluir fluxos.
* **Dois novos serviços** - suporte adicionado à Automação do Azure e Basecamp 2.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sobre esta versão.

### <a name="release-2017-02-16"></a>Versão 16-02- 2017
* **Cinco novos serviços** - suporte adicionado ao Azure Data Lake, Bitbucket (um serviço de hospedagem baseado na Web para projetos que usam o controle de revisão GIT), Eventbrite, Infusionsoft e Pipedrive.
* **Autenticação HTTP personalizada** - no designer do fluxo agora é possível usar a autenticação com pontos de extremidade HTTP personalizados.
* **Analisar mensagens JSON** - você pode analisar dados JSON do gatilho de Solicitação HTTP ou que é retornado da ação HTTP.
* **Filtragem da Execução de fluxo** - filtragem aprimorada para execuções de fluxo, com opções mais específicas, incluindo ver os Fluxos em execução ou Execuções canceladas.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/managing-flow-resources-in-the-admin-center/) sobre esta versão.

### <a name="release-2017-02-06"></a>Versão 06-02-2017
* **Fluxos de equipe** - os fluxos de equipe possibilitam que várias pessoas possuam e gerenciem um fluxo juntas e, se alguém sair de uma organização, os fluxos criados podem continuar sendo executados.
* **Compartilhamento de conectores personalizados** - os conectores personalizados, como fluxos de equipe, podem ser compartilhados e gerenciados coletivamente dentro de uma organização.
* **Suporte do Gmail e LUIS** - conecte-se ao Serviço Inteligente do Entendimento de Linguagem dos Serviços Cognitivos do Azure e do Gmail.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/team-flows/) sobre esta versão.

### <a name="release-2017-01-30"></a>Versão 30-01-2017
* **Entradas do botão de fluxo** - os botões de fluxo podem agora receber entradas de usuário em tempo de execução. Assim, os autores de fluxo podem definir informações que são passadas quando o botão é tocado.
* **Tarefas do Outlook e HelloSign** - o serviço de Tarefas do Outlook permite que você gerencie tarefas e o HelloSign permite assinaturas eletrônicas seguras.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-user-inputs/) sobre esta versão.

### <a name="release-2017-01-23"></a>Versão 23-01-2017
* **Pesquisar por serviço** - procure pelo serviço ao adicionar um gatilho ou ação para ver todas as ações de cada serviço.
* **Alternar caso** - adicione Blocos de alternância para ter várias ramificações da lógica paralela.
* **Mais ações de email** - nova funcionalidade nos serviços do Office 365 Outlook e Outlook.com para trabalhar com emails sinalizados.
* **Cinco novos serviços** - conecte aos Sistemas de Arquivo Local e de Rede, Faixa do serviço de pagamento, IBM Informix, IBM DB2 e UserVoice.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/search-by-service/) sobre esta versão.

### <a name="release-2017-01-14"></a>Versão 2017-01-14
* **Reenviar execuções** - se um fluxo falhou e você deseja tentar corrigi-lo e executá-lo novamente, poderá reenviar a execução com falha.
* **Cancelar execuções** - quando um fluxo ficar travado, agora você poderá cancelar explicitamente a execução.
* **Dois novos serviços** - suporte adicionado para GoToTraining e GoToWebinar.
* **Links móveis** - agora você pode compartilhar modelos diretamente do aplicativo móvel e adicionamos um link de download rápido para os aplicativos na parte superior do site.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/managing-runs/) sobre esta versão.

### <a name="release-2016-12-29"></a>Versão 2016-12-29
Agora, o Microsoft Flow suporta o DocuSign para lidar com as assinaturas digitais e o Gerenciamento de Transações Digitais, o SurveyMonkey para as pesquisas baseadas na Web e o aplicativo de anotações do OneNote (apenas para as contas de negócios).

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/final-2016-services/) sobre esta versão.

### <a name="release-2016-12-20"></a>Versão 2016-12-20
* **Executar agora** - agora, você pode disparar um gatilho recorrente sob demanda - por exemplo, se tiver um relatório agendado todos os dias, mas precisar executar o relatório **agora** também.
* **Seis novos serviços** - crie fluxos que conectam à Previsão do Tempo MSN, Medium, Contatos do Google, Buffer, Harvest e TypeForm.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/run-now-and-six-more-services/) sobre esta versão.

### <a name="release-2016-12-14"></a>Versão 2016-12-14
Agora, você pode aproveitar informações valiosas ao disparar um fluxo de botão, como de onde qual botão foi disparado, por quem, a hora e muito mais.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/button-trigger-tokens/) sobre esta versão.

### <a name="release-2016-12-06"></a>Versão 2016-12-06
* **Introdução ao Aprendizado Guiado** - comece com uma coleção sequenciada de cursos que combina vídeos com documentação para ajudá-lo a compreender os vastos e poderosos recursos do Microsoft Flow.
* **Dois novos serviços** - os fluxos já podem usar o Freshdesk, uma solução de suporte ao cliente, e o GoToMeeting, uma ferramenta de reuniões online.
* **Suporte a HTTP Webhook** - um fluxo agora pode ser um ponto de extremidade para webhooks que se registrarão e cancelarão o registro automaticamente.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/guided-learning-and-two-services/) sobre esta versão.

### <a name="release-2016-11-23"></a>Versão 2016-11-23
* **Suporte de alerta do Power BI no Flow** - torna informações em ação ao disparar fluxos a partir de alertas de dados do Power BI.
* **Aprimoramentos dos aplicativos móveis** - foi adicionada a capacidade de criar fluxos a partir do zero, além da experiência já existente de criação a partir de modelos. Também melhoramos o desempenho da visualização das execuções do fluxo.
* **Oito novos serviços** – Agora é possível se conectar ao Azure Resource Manager, ao Azure Queues, ao Chatter, ao Disqus, ao Azure Cosmos DB, à API de Detecção Facial dos Serviços Cognitivos, ao HipChat e ao Wordpress.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/power-bi-and-eight-other-services/) sobre esta versão.

### <a name="release-2016-11-15"></a>Versão 2016-11-15
* **Programa de Parceiro do Microsoft Flow** - o Microsoft Flow agora tem um programa de parceiro certificado para fazer conexões e aproveitar os diversos talentos da empresa e a experiência com o Microsoft Flow em todo o mundo.
* **Seis novos serviços** – também estamos lançando seis serviços esta semana: Asana, Campfire, EasyRedmine, JIRA, Redmine e Vimeo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/partner-program-six-new-services/) sobre esta versão.

### <a name="release-2016-10-31---general-availability"></a>Versão de 31-10-2016 - Disponibilidade Geral
* **Preços e licenciamento** - agora disponível nos planos Gratuito e pagos, bem como incluída no Office 365 e no Dynamics 365.
* **Centro de Administração do Microsoft Flow** - empresarial com o novo Centro de Administração. No Centro de Administração, você pode gerenciar os ambientes dentro da organização.
* **Políticas de prevenção de perda de dados** - os administradores podem criar políticas de prevenção de perda de dados para controlar o fluxo de dados entre os serviços.
* **Disponibilidade do Android** -aplicativo de telefone Microsoft Flow agora está disponível para iOS e Android. O aplicativo permite que você obtenha notificações, monitore a atividade e inicie os fluxos com o toque de um botão.
* **Novas experiências do designer** - agora você pode pesquisar o conteúdo dinâmico transmitido passo a passo, tornando muito mais rápido fazer referência aos dados desejados.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/announcing-ga/) sobre esta versão.

### <a name="release-2016-10-26"></a>Versão de 26-10-2016
* **Fluxos do botão** - há inúmeras operações que gostaríamos de disparar a qualquer momento e em qualquer lugar. Agora, com os Fluxos do Botão, você pode fazer isso com apenas um clique do botão no dispositivo móvel.
* **Apresentando os ambientes** - os ambientes são espaços distintos para armazenar e gerenciar os fluxos de sua organização. Os ambientes são localizados geograficamente, o que significa que os fluxos, aplicativos e dados de negócios que residem em um ambiente estarão na região onde está o ambiente.
* **Seis novos serviços** -Adicionando suporte para Bit.ly, Análise de Texto dos Serviços Cognitivos, Dynamics NAV, Dynamics 365 Financeiro, Instapaper e Pinterest.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/environments-for-makers/) sobre esta versão.

### <a name="release-2016-10-16"></a>Versão 2016-10-16
* **Os conectores personalizados oferecem suporte a mais tipos de autenticação**: os conectores personalizados agora oferecem suporte à autenticação da Chave de API e podem autenticar qualquer serviço que oferece suporte à especificação completa do OAuth 2.0.
* **Três novos serviços com suporte**: adicionamos suporte para Basecamp 3, Blogger e PagerDuty.
* **Melhorias para Designer**: melhor desempenho, você pode atualizar e reparar as conexões à direita do menu “...” para cada ação e adicionamos uma nova etapa chamada Terminar, que você pode usar para finalizar a execução de um fluxo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/early-october-updates/) sobre esta versão.

### <a name="release-2016-09-25"></a>Versão 2016-09-25
Criação de fluxo agora disponível em seus telefones móveis. Navegue por nossa galeria de modelos avançados e nossa lista de serviços ou selecione uma categoria de modelo para analisar. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/mobile-creation/) sobre esta versão.

### <a name="release-2016-09-22"></a>Versão 2016-09-22
* **Seletor de Pessoas do Microsoft Graph**: um novo seletor de pessoas do Microsoft Graph é integrado diretamente à interface do usuário do Microsoft Flow para ajudá-lo a escolher o contato ou endereço de email corretos.
* **Suporte do Microsoft Dynamics AX**: de dentro dos seus fluxos, agora é possível executar ações em seus dados de operações do Dynamics AX Online, desde a criação de novos registros até consulta de dados.
* **Dois novos serviços de parceiros**: agora, use appFigures ou Insightly de seus fluxos.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/more-september-updates/) sobre esta versão.

### <a name="release-2016-09-14"></a>Versão 2016-09-14
* **Inserindo em seu site ou aplicativo**: os desenvolvedores agora podem inserir o Microsoft Flow diretamente em seus aplicativos ou sites para conceder aos usuários uma maneira simples de automatizar suas tarefas profissionais ou pessoais.
* **Usar um fluxo como um ponto de extremidade HTTP**: agora é possível usar um fluxo em si, como uma API HTTP. Há um gatilho chamado Solicitação dentro de fluxo e você pode optar por responder à solicitação de entrada, adicionando um cartão de Resposta.
* **Suporte Todoist** – Todoist oferece perspectiva sobre todos seus projetos, no trabalho e em casa.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/extend-web-site-application/) sobre esta versão.

### <a name="release-2016-09-01"></a>Versão 2016-09-01
Microsoft Flow agora disponível para todos: abrimos inicialmente a visualização somente para endereços fornecidos por seu trabalho ou escola, como aqueles usados com o Office 365 Business ou Office 365 Enterprise. Hoje, estamos anunciando que a visualização está oficialmente disponível, com uso gratuito para todos os usuários, independentemente do email que tiver. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/available-for-everyone/) sobre esta versão.

### <a name="release-2016-08-31"></a>Versão 2016-08-31
* **Condicionais aninhadas**: agora você pode adicionar uma segundo (ou terceira etc.) condição dentro de outra.
* **Aplicar a cada**: uma aplicação para cada loop torna possível controlar a lista que se repete.
* **Do-until**: um loop do-until permite que você repita uma etapa até que uma determinada condição seja atendida.
* **Filtrar matrizes**: há uma única etapa de filtro nativo que pode garantir que cada item da lista coincida com alguma expressão que você definir.
* **Compor variáveis de cadeia de caracteres**: agora você pode criar uma variável de cadeia de caracteres.
* **Escopos**: escopos são uma maneira simples de agrupar duas ou mais ações.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/build-advanced-flows/) sobre esta versão.

### <a name="release-2016-08-27"></a>Versão 2016-08-27
* **Comentários sobre etapas**: comentários facilitam anotar cada ação individual com observações, para que você se lembre facilmente do fluxo precisa
* **Suporte do Smartsheet**: esta semana adicionamos o suporte para se conectar ao Smartsheet. O Smartsheet é um serviço que facilita a colaboração em planilhas na nuvem.
* **Aprimoramentos da interface do usuário ao criar fluxos**: tornamos o nome sempre disponível e movemos o botão Salvar para a parte superior da página, facilitando o acesso.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/add-comments-smartsheet/) sobre esta versão.

### <a name="release-2016-08-18"></a>Versão 2016-08-18
Agora você pode visualizar a nova experiência moderna de listas do SharePoint Online, que inclui a integração com o Microsoft Flow. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/microsoft-flow-integration-with-sharepoint-modern-lists-preview/) sobre esta versão.

### <a name="release-2016-08-13"></a>Versão 2016-08-13
* **Visual Studio Team Services**: com o Flow, agora é possível conectar o VSTS a uma ampla variedade de serviços, como O365 Email, Slack, Trello e Wunderlist.
* **Aprimoramentos no SharePoint**: as listas do SharePoint dão suporte a uma variedade de tipos de dados de objetos simples, como linhas únicas de texto, data e hora para objetos complexos, como Pessoa ou Grupo, Pesquisa e Escolha.
* **Testar Conexões do O365 Outlook**: sempre que você criar uma nova conexão do O365 Outlook, agora a testaremos para verificar se você está pronto para usá-la.
* **Controle Booliano**: também adicionamos um controle booliano para esclarecer quais valores boolianos devem ser inseridos nos campos de entrada, como Há Anexos no gatilho Quando um novo email chegar.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/visual-studio-team-services-enhancements-to-sharepoint-and-o365-outlook-and-boolean-control/) sobre esta versão.

### <a name="release-2016-08-08"></a>Versão 2016-08-08
Visualização pública do Common Data Service da Microsoft integrado ao Microsoft Flow. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/flow-and-common-data-model/) sobre esta versão.

### <a name="release-2016-08-05"></a>Versão 2016-08-05
* **SharePoint Local**: assim como no SharePoint Online, é possível criar fluxos em torno de suas listas e bibliotecas de documentos do SharePoint local, ao usar modelos predefinidos ou ao criá-los do zero.
* **Informações-bolhas no designer**: para elaborar recursos de cada gatilho e ação, adicionamos informações-bolhas acima de cada etapa do seu fluxo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/sharepoint-on-premises-and-info-bubbles-2/) sobre esta versão.

### <a name="release-2016-07-15"></a>Versão 2016-07-15
* **Quatro novos serviços adicionados**: conecte-se ao Calendário Google, Google Tarefas, YouTube e SparkPost.
* **Renomeie suas ações**: agora é possível distinguir essas diferentes ações ao renomeá-las.
* **Atraso para diferentes períodos de tempo**: agora é possível selecionar qualquer número de Segundos, Minutos, Horas ou Dias.
* **Navegador de pasta mais fácil de usar**: simplificamos o navegador de pasta. Agora, a seleção à esquerda escolherá a pasta e a seleção à direita abrirá a pasta para que você escolha as subpastas.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/new-google-services-rename-more/) sobre esta versão.

### <a name="release-2016-07-08"></a>Versão 2016-07-08
Conectividade local para o Microsoft Flow usando o gateway de dados local. Isso permite estabelecer conexões seguras para o SQL Server e integrá-los com seus fluxos. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/on-premises-data-gateway/) sobre esta versão.

### <a name="release-2016-07-02"></a>Versão 2016-07-02
* **Suporte das Planilhas Google**: no passado, tivemos a capacidade de usar o Excel, bem como o Google Drive, mas esta semana estamos adicionando suporte nativo a Planilhas Google.
* **Inicie mais rápido com modelos**: também fizemos algumas otimizações na forma de iniciar com modelos. Agora, você pode selecionar as contas que você deseja usar para um modelo direto embutido na página do modelo.
* **Nenhuma autorização expira no SharePoint e no Office 365**: agora, o Microsoft Flow renovará automaticamente seu acesso aos serviços baseados no Azure Active Directory, para que todos seus fluxos continuem funcionando em alterações de senha.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/more-june-updates/) sobre esta versão.

### <a name="release-2016-06-20"></a>Versão 2016-06-20
* **Apresentando o novo aplicativo móvel para Microsoft Flow**: hoje, estamos orgulhosos em apresentar outra grande parte da nossa oferta: um aplicativo móvel agora está disponível para download no iOS (em breve também no Android) que fornece a capacidade de gerenciar, controlar e explorar seus fluxos de trabalho automatizados a qualquer momento e em qualquer lugar.  
* **Logon único** – implementamos logon único que permite que você autentique-se ao Microsoft Flow com outros serviços da Microsoft, como o Office 365.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/welcome-to-flow-now-more-mobile/) sobre esta versão.

### <a name="release-2016-06-18"></a>Versão 2016-06-18
* **Novo serviço de email**: agora é possível enviar emails diretamente do Microsoft Flow, sem precisar se conectar às suas contas de email pessoais ou de trabalho dentro do Microsoft Flow.
* **Notificações no portal**: agora você verá as Notificações na parte superior do portal sempre que algo estiver errado com seus fluxos.
* **Todas as atividades no portal**: agora você pode ver atividade em todos os seus fluxos ao clicar na nova guia Atividade no site do fluxo.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/mail-and-all-activity/) sobre esta versão.

### <a name="release-2016-05-27"></a>Versão 2016-05-27
* **Procurar modelos por serviço** – agora há uma maneira de ver todos os serviços aos quais oferecemos suporte (sem precisar fazer logon). Nesta página, você pode ver uma descrição de cada um dos serviços e conferir os modelos que temos para este serviço.
* **Criar e usar seus conectores personalizados** - Da mesma forma que você pode criar conectores personalizados no PowerApps, também pode se conectar às suas próprias APIs direto em flow.microsoft.com:
* **Teste o fluxo antes de concluir**: sempre que salvar um fluxo, agora é possível ver os resultados da execução do fluxo direto na página, caso execute a ação inicial.

[Leia mais e faça perguntas](https://flow.microsoft.com/blog/may-updates-to-microsoft-flow/) sobre esta versão.

### <a name="release-2016-05-07"></a>Versão 2016-05-07
Dois novos serviços adicionados: Microsoft Project Online e Mandrill por Mailchimp. [Leia mais e faça perguntas](https://flow.microsoft.com/blog/announcing-microsoft-flow-webinars/) sobre esta versão.

### <a name="release-2016-04-27---public-preview"></a>Versão de 27-04-2016 - Visualização Pública
Se você usou fluxos lógicos como parte do [Microsoft PowerApps](https://powerapps.microsoft.com), a versão de visualização do Microsoft Flow oferece vários recursos novos:

* Agora você pode navegar em uma galeria com dezenas de modelos e classificar por popularidade, nome ou data de publicação.
* Você pode [publicar seus próprios modelos](publish-a-template.md) na galeria depois de personalizar um fluxo.
* Você pode ver o histórico de cada verificação e execução do seu fluxo.
* Quando você salva um fluxo, você pode [vê-lo em ação imediatamente](see-a-flow-run.md) apenas executando a ação de gatilho.
* Temos um [nova comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) para você falar sobre o Flow ou [enviar suas ideias](https://go.microsoft.com/fwlink/?LinkID=787474).

## <a name="next-steps"></a>Próximas etapas
Se você tiver problemas não abordados nessas notas de versão ou nas [perguntas frequentes](frequently-asked-questions.md), por favor, [participe da nossa comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) para fazer perguntas ou [entre em contato com o suporte](http://go.microsoft.com/fwlink/?LinkID=787479).

