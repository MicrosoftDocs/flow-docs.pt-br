---
title: Inscrição para P e R do Flow em sua organização | Microsoft Docs
description: Perguntas e respostas comuns sobre licenças, administração e usuários se inscrevendo no Flow em seu locatário do Office 365
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: erikre
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/05/2016
ms.author: stepsic
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 6e05c24aa00c29dff4ca07432277ca7b907ebbb0
ms.sourcegitcommit: e17963065b72ddaba7b2605908c62768acb8c16c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58327080"
---
# <a name="flow-in-your-organization-qa"></a>P e R sobre o Flow em sua organização
Este tópico descreve como os usuários em sua organização podem usar o Flow e como você pode controlar o serviço do Flow.

## <a name="signing-up-for-flow"></a>Inscrever-se no Flow
### <a name="what-is-microsoft-flow"></a>O que é Microsoft Flow?
O Microsoft Flow é um serviço de nuvem pública que ajuda pessoas e equipes a configurar fluxos de trabalho automatizados entre seus aplicativos favoritos e serviços para sincronizar, obter notificações, coletar dados e muito mais. 

### <a name="how-do-people-sign-up-for-flow"></a>Como as pessoas se inscrevem no Flow?
Há duas maneiras possíveis para as pessoas se inscreverem no Flow por meio do portal da Web:

#### <a name="option-1"></a>Opção 1
Qualquer pessoa pode se inscrever acessando [flow.microsoft.com](https://flow.microsoft.com), selecionando **Inscrever-se gratuitamente** e, em seguida, concluindo o processo de inscrição no Flow por meio de [admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free) ou [signup.live.com](https://signup.live.com).

#### <a name="option-2"></a>Opção 2
Para se inscrever, os usuários podem acessar [flow.microsoft.com](https://flow.microsoft.com), escolher **Entrar**, entrar com a conta corporativa, de estudante ou pessoal e aceitar os termos de uso do Flow.    

Quando um usuário em sua organização se inscreve no Flow com a Opção 2, uma licença do Microsoft Flow Gratuito será automaticamente atribuída a ele.

[Inscrever-se no Flow](sign-up-sign-in.md) inclui mais detalhes.

### <a name="what-is-the-microsoft-flow-free-plan"></a>O que é o plano gratuito do Microsoft Flow?

O plano gratuito do Microsoft Flow é usado somente para fins de rastreamento. Habilitá-lo ou desabilitá-lo não afeta a capacidade dos usuários de criar fluxos. Se você desabilitar o plano gratuito do Microsoft Flow, ele será habilitado novamente quando um usuário fizer logon. Esse é o comportamento esperado.

### <a name="can-i-block-another-person-from-signing-up-for-flow"></a>Posso impedir uma pessoa de se inscrever no Flow?
Como o Microsoft Flow é um serviço de nuvem pública, todos podem se inscrever e usá-lo para automatizar suas tarefas diárias. Para usar o Microsoft Flow, não há requisitos para que os usuários tenham ou usem uma conta do Office 365. Por isso, não há atualmente um mecanismo para impedir que uma pessoa use o Flow (como todas as pessoas no mundo podem fazer, independentemente do endereço de email).

No entanto, se uma pessoa se inscrever no Microsoft Flow e você optar por não lhe oferecer suporte dentro de sua organização, ela não poderá, em hipótese alguma, incorrer em custos para sua empresa. Quando uma pessoa se inscreve no Microsoft Flow, a relação é entre essa pessoa e a Microsoft, que é como muitos outros serviços de nuvem da Microsoft, como o Bing, Wunderlist, OneDrive ou Outlook.com. O uso de uma pessoa do Microsoft Flow não implica que o serviço é fornecido por sua organização.

Finalmente, se sua empresa quiser restringir o uso de dados exclusivamente organizacionais no Microsoft Flow, pode usar políticas de prevenção contra perda de dados (DLP) para fazer isso.

### <a name="how-can-people-gain-access-to-the-paid-features-of-microsoft-flow"></a>Como as pessoas podem obter acesso aos recursos pagos do Microsoft Flow?
As pessoas podem obter acesso aos recursos pagos do Microsoft Flow de três maneiras diferentes:

1. Elas podem se inscrever individualmente em uma avaliação gratuita de 90 dias do Flow Plano 1 ou do Flow Plano 2
2. Você pode atribuir uma licença do Flow a essas pessoas no portal de administração do Office 365.
3. O usuário foi atribuído a planos do Office 365 e do Dynamics 365 que inclui acesso ao serviço do Flow. Confira a [Página de preços do Flow](https://flow.microsoft.com/pricing/) para obter a lista de planos do Office 365 e do Dynamics 365 que incluem os recursos do Flow.

### <a name="can-i-block-another-person-from-using-the-paid-features-of-flow"></a>Posso impedir que uma pessoa use os recursos pagos do Flow?
Qualquer pessoa pode experimentar gratuitamente os recursos pagos do Microsoft Flow por 90 dias. No entanto, você pode gerenciar totalmente a atribuição das licenças perpétuas pagas dentro de sua organização por meio do portal de administração do Office 365.

Tal como acontece com as ofertas gratuitas, se uma pessoa optar por se inscrever na avaliação, essa é uma relação direta entre a pessoa e a Microsoft, que não é necessariamente endossada pela sua empresa.

## <a name="administration-of-flow"></a>Administração do Flow
### <a name="why-has-the-flow-icon-appeared-in-the-office-365-app-launcher"></a>Por que o ícone do Flow foi exibido no iniciador de aplicativos do Office 365?
Conforme anunciado em agosto, o Microsoft Flow agora é uma parte fundamental do pacote do Office 365. Três meses após este anúncio, o Microsoft Flow foi habilitado como um serviço, parte de todos os serviços de SKUs do Office 365 existentes. Como agora usuários de todo o mundo já podem usar o Microsoft Flow, ele será exibido no iniciador de aplicativos de todas as pessoas.

Confira a seção a seguir se quiser remover o bloco do Flow do iniciador de aplicativos por padrão.

### <a name="how-do-i-remove-microsoft-flow-from-the-app-launcher-for-my-organization"></a>Como remover o Microsoft Flow do iniciador de aplicativos para minha organização?
Se um usuário tiver sido atribuído a uma licença do Flow Plano 1 ou do Flow Plano 2, siga as seguintes etapas para remover a licença do Flow para esse usuário e isso removerá o ícone do Flow do iniciador de aplicativos:

1. Acesse o [Portal de Administração do Office 365](https://portal.microsoftonline.com/).
2. Na barra de navegação à esquerda, selecione **Usuários** e, em seguida, selecione **Usuários Ativos**.
3. Localize o usuário do qual você deseja remover a licença e, em seguida, marque o nome da pessoa.
4. No painel de detalhes do usuário, na seção **Licenças de produtos**, selecione **Editar**.
5. Localize a licença chamada **Microsoft Flow Plano 1** ou **Microsoft Flow Plano 2**, defina a alternância como **Desabilitado** e, em seguida, selecione **Salvar**.
   
   ![](./media/organization-q-and-a/remove-license.png)

Se um usuário tiver acesso ao Flow através da licença do plano do Office 365 e do Dynamics 365, é possível desabilitar o acesso aos recursos adicionais incluídos neste plano executando as seguintes etapas:

1. Acesse o [Portal de Administração do Office 365](https://portal.microsoftonline.com/).
2. Na barra de navegação à esquerda, selecione **Usuários** e, em seguida, selecione **Usuários Ativos**.
3. Localize o usuário do qual deseja remover o acesso e, em seguida, marque o nome da pessoa.
4. No painel de detalhes do usuário, na seção **Licenças de produtos**, selecione **Editar**.
5. Expanda a licença do usuário do Office 365 ou do Dynamics 365, desabilite o acesso ao serviço chamado **Flow para Office 365** ou **Flow para Dynamics 365** e, em seguida, selecione **Salvar**.
   
   ![](./media/organization-q-and-a/remove-service-plan.png)

Também é possível remover licenças em massa com o PowerShell. Confira [Remover licenças de contas de usuário com o Office 365 PowerShell](https://technet.microsoft.com/library/dn771774.aspx) para obter um exemplo detalhado.   Por fim, em [Desabilitar o acesso a serviços com o Office 365 PowerShell](https://technet.microsoft.com/library/dn771769.aspx), você tem acesso a ainda mais orientações sobre a remoção em massa dos serviços contidos em uma licença.

Remover a licença ou o serviço do Flow de um usuário da organização resultará na remoção do ícone do Flow nos seguintes locais para o usuário:

1. [Office.com](https://office.com)
   
   ![](./media/organization-q-and-a/office-home.png)
2. Iniciador de Aplicativos do Office 365
   
   ![](./media/organization-q-and-a/office-waffle.png)

Observe que isso removerá apenas o bloco do Flow por padrão. O usuário ainda poderá usar o Microsoft Flow individualmente.

### <a name="why-did-10000-licenses-for-microsoft-flow-show-up-in-my-office-365-tenant"></a>Por que 10.000 licenças do Microsoft Flow foram exibidas em meu locatário do Office 365?
Qualquer pessoa pode experimentar o plano do Microsoft Flow 1 ou 2 por 90 dias e essas licenças de avaliação representam a capacidade disponível para novos usuários do Flow em seu locatário. Não há qualquer custo para essas licenças. Especificamente, há duas razões possíveis por ser exibida uma capacidade de 10.000 licenças (avaliação) do Flow no portal de administração do Office 365:

1. Se pelo menos um usuário em seu locatário tiver participado em uma visualização pública do Flow ocorrida de abril de 2016 a outubro de 2016. Dessa forma, você verá 10.000 licenças rotuladas como "Microsoft PowerApps e Fluxos de lógica"
   
    ![](./media/organization-q-and-a/licenses2.png)
2. Se pelo menos um usuário em seu locatário tiver se inscrito em uma avaliação do Flow Plano 2 através de uma inscrição de avaliação **Opção 1** descrita na seção [Como os usuários se inscrevem no PowerApps](#how-do-people-sign-up-for-flow). Dessa forma, você verá 10.000 licenças rotuladas como "Microsoft PowerApps e Flow"
   
    ![](./media/organization-q-and-a/licenses1.png)

Você pode optar por atribuir licenças adicionais aos usuários através do portal de administração do Office 365, mas observe que essas são licenças de avaliação do Microsoft Flow Plano 2 e expirarão em 90 dias após terem sido atribuídas a um usuário.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>É grátis? Serei cobrado por essas licenças?
Nenhum usuário poderá implicar custos para sua organização sem seu consentimento expresso, portanto, licenças gratuitas e de avaliação podem acarretar encargos para sua organização. Além disso, os usuários também não utilizam cotas, como cotas de execução.

### <a name="i-removed-the-microsoft-flow-free-license-and-users-can-still-access-flow"></a>Removi a licença do Microsoft Flow Gratuito, mas os usuários ainda conseguem acessar o Flow?
A licença do Microsoft Flow Gratuito está incluída apenas para fins de acompanhamento. Conforme abordado na primeira seção, não é possível evitar que outra pessoa use o Microsoft Flow para fins individuais. Assim, a presença de uma licença do Microsoft Flow Gratuito, na verdade não concede ou remove qualquer recurso.

### <a name="why-cant-i-see-all-flow-licenses-in-the-office-365-admin-portal"></a>Por que não consigo ver todas as licenças do Flow no portal de Administração do Office 365?
Os usuários podem usar o Microsoft Flow individualmente ou como parte de sua organização. As licenças no nível da organização sempre estarão visíveis no portal do Office 365. No entanto, se um usuário se inscrever em uma avaliação como um indivíduo, então, não será gerenciado por seu administrador do Office 365 nem aparecerá no portal.

### <a name="how-does-an-individual-find-out-what-plan-they-are-on"></a>Como um indivíduo descobre em qual plano ele está?
Qualquer pessoa pode ver o plano que tem visitando a página de preços de Fluxo em [https://flow.microsoft.com/pricing](https://flow.microsoft.com/pricing). O plano ou a versão de avaliação atual será mostrada aqui.

### <a name="will-microsoft-flow-sign-up-impact-the-identities-in-my-organization"></a>Inscrever-se no Microsoft Flow afetará as identidades em minha organização?
Se sua organização já tiver um ambiente do Office 365 existente e todos os usuários na organização tiverem contas do Office 365, o gerenciamento de identidades não será alterado.

Se sua organização já tiver um ambiente existente do Office 365, mas nem todos os usuários em sua organização tiverem contas do Office 365, poderemos criar um usuário no locatário e atribuir licenças com base no endereço de email corporativo ou de estudante do usuário. Isso significa que o número de usuários que você está gerenciando a qualquer momento específico aumentará à medida que os usuários em sua organização se inscreverem no serviço.

Se sua organização não tiver um ambiente do Office 365 conectado ao domínio de email, não haverá alteração na forma de gerenciar identidades. Os usuários serão adicionados a um novo diretório de usuários somente na nuvem, e você terá a opção de assumir como administrador do locatário e gerenciá-los.

### <a name="a-new-tenant-was-created-by-microsoft-flow-how-do-i-manage-this"></a>Um novo locatário foi criado pelo Microsoft Flow. Como faço para gerenciar isso?
Se um novo locatário tiver sido criado pelo Microsoft Flow, você poderá solicitá-lo e gerenciá-lo usando as seguintes etapas:

1. Ingresse no locatário inscrevendo-se no Flow com um domínio de endereço de email que corresponda ao domínio de locatário que você deseja gerenciar. Por exemplo, se a Microsoft tiver criado o locatário contoso.com, ingresse com um endereço de email que termine com @contoso.com.
2. Solicite o controle de administração verificando a propriedade do domínio: quando estiver no locatário, você poderá se autopromover à função de administrador verificando a propriedade do domínio. Para fazer isso, siga estas etapas:    
   
   1. Acesse [https://admin.microsoft.com](https://admin.microsoft.com/Start?sku=flow_free).
   2. Selecione o ícone do iniciador de aplicativos no canto superior esquerdo e escolha Administrador.
   3. Leia as instruções na página **Tornar-se o administrador** e escolha **Sim, quero ser o administrador**.  
      
       **OBSERVAÇÃO**: se essa opção não for exibida, um administrador do Office 365 já está em vigor.

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Se eu tiver vários domínios, poderei controlar o locatário do Office 365 ao qual os usuários são adicionados?
Se você não fizer nada, um locatário será criado para cada domínio de email de usuário e subdomínio.

Se você desejar que todos os usuários estejam no mesmo locatário independentemente de suas extensões de endereço de email:  

* Crie um locatário de destino antecipadamente ou use um locatário existente. Adicione todos os domínios e subdomínios existentes que deseja consolidar neste locatário. Em seguida, todos os usuários com endereços de email que terminam com esses domínios e subdomínios ingressam automaticamente no locatário de destino ao se inscreverem.

**IMPORTANTE**: não há um mecanismo automatizado com suporte para mover os usuários entre locatários depois que eles são criados. Para saber mais sobre a adição de domínios para um único locatário do Office 365, confira [Adicionar os usuários e o domínio ao Office 365](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-ffdb2216-330d-4d73-832b-3e31bcb5b2a7).

### <a name="how-can-i-restrict-my-users-ability-to-access-my-organizations-business-data"></a>Como posso restringir a capacidade de meus usuários de acessar dados de negócios da minha organização?
O Microsoft Flow permite que você crie zonas de dados para dados comerciais e não comerciais, conforme mostrado abaixo. Depois que essas políticas de prevenção contra perda de dados forem implementadas, os usuários serão impedidos de criar ou executar o Flow que combina dados comerciais e não comerciais. Para obter mais detalhes, confira [Políticas de prevenção contra perda de dados (DLP)](prevent-data-loss.md).

  ![](./media/organization-q-and-a/data-loss-prevention-policy.png)

