---
title: Aprenda a criar fluxos de interface do usuário para sites | Microsoft Docs
description: Aprenda a automatizar aplicativos Web com fluxos de interface do usuário.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 010b6632a60f2c81c138fa98d850df79be814f68
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589875"
---
# <a name="create-and-test-your-web-ui-flows"></a>Criar e testar seus fluxos de interface do usuário da Web

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Siga estas etapas para criar um fluxo de interface do usuário da Web simples:

## <a name="create-a-web-ui-flow"></a>Criar um fluxo de interface do usuário da Web

1. Abra a [próxima versão do Microsoft Edge ou do](https://www.microsoftedgeinsider.com/) Google Chrome e, em seguida, navegue até [Power Automate](https://flow.microsoft.com/).

1. Entre com sua conta corporativa ou de estudante se necessário.

1. Selecione **meus fluxos** > **fluxos de interface do usuário (visualização)**  > **novos**.

   ![Criar novo fluxo de interface do usuário](../media/create-windows-ui-flow/create-new.png "Criar novo fluxo de interface do usuário")

1. Selecione o **aplicativo Web** > **Avançar**
    
   ![Selecionar aplicativo Web](../media/create-web-ui-flow/select-web-app.png "Selecionar aplicativo Web")

1. Insira um nome para o fluxo da interface do usuário no campo **nome do fluxo** .

1. Insira a URL do site que você deseja automatizar no campo **URL base** e, em seguida, selecione **Iniciar gravador**.

   ![Dê um nome e uma URL](../media/create-web-ui-flow/give-a-name.png "Dê um nome e uma URL") 

   O IDE do Selenium é iniciado.

   >[!TIP] 
   >Dica: você pode registrar ações em vários sites HTTP ou HTTPS na mesma guia.  

1. No Selenium IDE, selecione o botão de **REC** vermelho no lado superior direito da tela para iniciar o gravador.

   A URL que você escolheu na etapa anterior é aberta.

   ![Selecionar REC](../media/create-web-ui-flow/select-rec.png "Selecionar REC")

1.  Execute as ações que você deseja registrar no site. 
    
    >[!TIP]
    >Na parte inferior direita, você pode ver o status da gravação.

    ![Status da gravação](../media/create-web-ui-flow/recording-status.png "Status da gravação")

1.  Quando terminar de gravar, selecione o botão vermelho **Stop** no canto superior direito do IDE do Selenium.

    ![Botão parar](../media/create-web-ui-flow/stop-button.png "Botão parar" )

1. Selecione o botão **Executar teste atual** no canto superior esquerdo da tela para ver o fluxo da interface do usuário que você acabou de criar executar.

    ![Executar teste atual](../media/create-web-ui-flow/run-test.png "Executar teste atual")

   >[!TIP]
   >Você pode definir o tempo de espera entre as etapas para reduzir a reprodução local para teste. Essa configuração é apenas para fins de teste e não tem impacto quando o fluxo da interface do usuário é implantado.  
  
1. Selecione o botão **salvar projeto** no canto superior direito do IDE do Selenium. Isso fecha e, em seguida, carrega o projeto.

Agora que você criou um fluxo de interface do usuário da Web, use-o em seus outros fluxos.

## <a name="limitations-and-known-issues-for-web-ui-flows"></a>Limitações e problemas conhecidos para fluxos de interface do usuário da Web

>[!WARNING]
>**As senhas no IDE Selenium são armazenadas em texto sem formatação.**  


**A interface do usuário não flui mais registros nem reproduz aplicativos do Windows após a instalação de uma nova versão.**

Você precisa desinstalar a versão anterior antes de instalar uma nova.

Para isso, abra o menu Iniciar, vá para **configurações** > **aplicativos**, pesquise **fluxos da interface do usuário** na lista de aplicativos > **fluxos da interface do usuário (versão prévia)** e, em seguida, selecione "Desinstalar". O assistente vai orientá-lo durante o processo.

**Perfil de usuário temporário para reprodução**

As gravações do Selenium IDE são feitas com o perfil do usuário atual, mas a reprodução é feita usando um perfil de usuário temporário. Isso significa que sites que precisam de autenticação podem não solicitar credenciais durante uma sessão de gravação, mas as etapas de autenticação serão necessárias durante a reprodução. 

Para resolver isso, o usuário precisa editar manualmente o script para inserir os comandos necessários para o processo de logon.

**Outras limitações**

-   Gravando aplicativos de área de trabalho durante uma sessão de gravação na Web. Se você precisar automatizar aplicativos Web e de área de trabalho, poderá criar fluxos de interface do usuário separados para cada tipo e, em seguida, combiná-los em um fluxo.

-   Não há suporte para a autenticação multifator (MFA), use um locatário que não exija MFA.

-   Não há suporte para esses comandos Selenium IDE: Execute, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, Debugger, ClickAt, DoubleClickAt, Echo, mouseout, MouseUpAt e MouseDownAt.

-   Não há suporte para o clique com o botão direito. 

-   Entrada de fluxo de interface do usuário Web adicional é gerada quando você usa comandos foreach. Para contornar esse problema, insira qualquer valor nos campos extras. Ele não afeta a reprodução.

-   Se o arquivo. Side contiver vários projetos de teste, somente o primeiro que foi criado será executado. 

     >[!TIP]
     >Observe que o Selenium IDE ordena os testes por nome, não por data de criação, portanto, o primeiro teste criado pode não ser o primeiro na lista.

-   A reprodução diretamente no Selenium IDE pode não se comportar conforme o esperado. No entanto, a reprodução em tempo de execução por meio da infraestrutura de fluxo da interface do usuário se comporta corretamente.

## <a name="next-steps"></a>Próximas etapas

- Saiba como [executar fluxos de interface do usuário](run-ui-flow.md).

- Se você quiser fazer mais com os fluxos da interface do usuário, você também poderá experimentar fluxos de interface do usuário com parâmetros [de entrada e saída](inputs-outputs-web.md) .

