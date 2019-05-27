---
title: Saiba como automatizar as tarefas repetitivas com os fluxos de botão que aceitam a entrada do usuário | Microsoft Docs
description: O Microsoft Flow facilita a automatização de tarefas repetitivas. Seus fluxos ainda podem levar à entrada do usuário ao executar uma tarefa repetitiva.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 5c1aed64ad5ac8fc1cced9290b376cb54f97e65a
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64992287"
---
# <a name="introducing-button-flows-with-user-input"></a>Introdução aos fluxos de botão com a entrada do usuário
Crie um fluxo de botão para executar tarefas de rotina com um simples toque em um botão. Personalize seu fluxo permitindo que o usuário forneça detalhes específicos que serão usados quando o fluxo for executado. Este tópico ajuda você a criar um fluxo de botão que recebe entrada do usuário e a executar o fluxo de botão, destacando como fornecer a entrada do usuário.

Crie um fluxo de botão no site do Microsoft Flow ou no aplicativo móvel do Microsoft Flow. Para este tópico, você usará o site.

### <a name="prerequisites"></a>Pré-requisitos
* Uma conta no site do Microsoft Flow.

## <a name="open-the-template"></a>Abrir o modelo
1. Entre no [site do Microsoft Flow](https://flow.microsoft.com), insira **Visual Studio** na caixa de pesquisa e clique ou toque no ícone de pesquisa para localizar todos os modelos relacionados ao Visual Studio:
   
    ![](./media/button-flow-with-user-input-tokens/1.png)  
2. Selecione o modelo **Abrir um Bug de Prioridade 2 no Visual Studio**:
   
    ![](./media/button-flow-with-user-input-tokens/2.png)  
3. Selecione o botão **Usar este modelo**:
   
    ![](./media/button-flow-with-user-input-tokens/3.png)  
   
    Esse modelo usa o Visual Studio Team Services (VSTS) e os serviços de notificação por push. Você precisará entrar nesses serviços se não tiver uma conexão com algum deles. O botão **Entrar** será exibido somente se você precisar entrar em um serviço.
4. Depois de entrar em todos os serviços necessários, selecione o botão **Continuar**:
   
    ![](./media/button-flow-with-user-input-tokens/4.png)  
5. (opcional) Altere o nome do fluxo digitando um nome de sua escolha na caixa na parte superior do portal:
   
    ![](./media/button-flow-with-user-input-tokens/5.png)

## <a name="customize-the-user-input"></a>Personalizar a entrada do usuário
1. No cartão do gatilho, selecione **Editar**:
   
    ![](./media/button-flow-with-user-input-tokens/6.png)  
2. Selecione o ícone **+** para expandir a página de modo que você possa adicionar campos de entrada personalizados:
   
    ![](./media/button-flow-with-user-input-tokens/7.png)
3. Insira o **Título da entrada** e a **Descrição da entrada** de cada campo personalizado que você deseja disponibilizar quando alguém executar seu fluxo.  
   
    Nesse exemplo, você criará dois campos de entrada personalizados (**Etapas de reprodução de bugs** e **Gravidade do bug**) para que qualquer pessoa que use esse fluxo possa inserir as etapas de reprodução do bug e avaliar a gravidade do bug:  
   
    ![](./media/button-flow-with-user-input-tokens/8.png)

## <a name="customize-the-bug"></a>Personalizar o bug
1. Toque na barra de título do cartão **Criar um novo item de trabalho**:
   
    ![](./media/button-flow-with-user-input-tokens/9.png)  
2. Faça as seleções apropriadas ao seu ambiente do VSTS e selecione **Editar**:
   
    Por exemplo, conecte-se a myinstance.visualstudio.com digitando **myinstance**.
   
    ![](./media/button-flow-with-user-input-tokens/10.png)  
3. Selecione **Mostrar opções avançadas** para revelar os outros campos desse cartão:
   
    ![](./media/button-flow-with-user-input-tokens/11.png)  
4. Coloque o cursor antes do token **Título do bug** e insira "Gravidade:" no campo de texto **Título**.
5. Com o cursor parado no campo de texto de título, selecione o token **Gravidade do bug** e, em seguida, digite " -- ".  
6. No campo de texto **Descrição**, coloque o cursor logo após o token de **Descrição do Bug** e, em seguida, pressione Enter para iniciar uma nova linha.
7. Coloque o cursor na nova linha e selecione o token **Etapas de Reprodução do Bug**:
   
    ![](./media/button-flow-with-user-input-tokens/12.png)

## <a name="customize-the-push-notification"></a>Personalizar a notificação por push
1. Toque na barra de título no cartão **Enviar uma notificação por push** para expandi-la.
2. Na lista de tokens de conteúdo dinâmicos, selecione **Ver mais** e, em seguida, adicione o token **URL** ao campo de texto **Link**.
3. No campo de texto **Rótulo do Link**, adicione o token **Id**:
   
    ![](./media/button-flow-with-user-input-tokens/13.png)  
4. Toque em **Criar fluxo** no menu para criar seu fluxo: ![](./media/button-flow-with-user-input-tokens/14.png)  

## <a name="run-your-flow"></a>Executar seu fluxo
Neste passo a passo, você usará o aplicativo móvel para Microsoft Flow para executar o fluxo de botão que você acabou de criar. Você fornecerá todas as entradas do usuário necessárias para criar um bug com um título, uma descrição, etapas de reprodução e um nível de gravidade.  

1. No aplicativo móvel do Microsoft Flow, toque na guia **Botões** e, em seguida, toque no botão **Criar relatório de bugs com etapas**.
   
    ![](./media/button-flow-with-user-input-tokens/runmt1.png)  
2. Insira o título para o bug que você está relatando e toque em **Avançar**. Por exemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt2.png)  
3. Insira a descrição do bug que você está relatando e toque em **Avançar**. Por exemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3.png)  
4. Insira as etapas para reproduzir o bug que você está relatando e toque em **Avançar**. Por exemplo:
   
    ![](./media/button-flow-with-user-input-tokens/runmt3-1.png)  
5. Insira a gravidade do bug que você está relatando e toque em **Concluído**.  
    ![](./media/button-flow-with-user-input-tokens/runmt3-2.png)  
   
    O fluxo é executado.
6. (opcional) Toque na guia **Atividade** para mostrar os resultados.
   
    ![](./media/button-flow-with-user-input-tokens/runmt5.png)  
7. (opcional) Mostre os resultados detalhados da execução do fluxo tocando na etapa **Criar um novo item de trabalho**.
   
    ![](./media/button-flow-with-user-input-tokens/runmt6.png)


## <a name="use-different-input-types"></a>Usar tipos de entrada diferentes

Os fluxos de botão também podem aceitar tipos de dados avançados. Aqui está a lista de tipos de entrada de dados compatíveis com fluxos de botão: 

- Texto
- Listas suspensas (como botões de opção)
- Endereço de email
- Arquivo (por exemplo, uma foto no telefone)
- Caixa de seleção Sim ou Não
- Número
- Data (com um seletor de calendário)

Para usar esses tipos de entrada, adicione o gatilho **Disparar um fluxo manualmente** e, em seguida, qualquer um dos seguintes tipos ao fluxo:

![Opções de entrada](media/button-flow-with-user-input-tokens/input-options.png)

Além disso, talvez você queira designar algumas entradas como obrigatórias e outras como opcionais. Use o menu de ação (... no lado direito) em cada campo de entrada. Há um limite de cinco entradas por botão.

![Selecionar tokens opcionais](media/button-flow-with-user-input-tokens/required-optional.png)

## <a name="next-steps"></a>Próximas etapas
* [Compartilhar fluxos de botão](share-buttons.md)
* [Saiba mais sobre fluxos de botão](introduction-to-button-flows.md)  
* [Saiba mais sobre fluxos de botão com tokens de gatilho](introduction-to-button-trigger-tokens.md)  

