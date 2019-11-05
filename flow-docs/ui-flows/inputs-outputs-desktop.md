---
title: Usar entradas e saídas em fluxos de interface do usuário da área de trabalho | Microsoft Docs
description: Use entradas e saídas em fluxos de interface do usuário da área de trabalho.
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
ms.openlocfilehash: 88bea3b8a038c01360fc5f3e61dbf30599b5deba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589776"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Usar entradas e saídas em fluxos de interface do usuário da área de trabalho

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs"></a>Definir entradas

As entradas permitem que você transmita informações de uma fonte externa, como um banco de dados ou qualquer conector com suporte para o software herdado que os fluxos da interface do usuário automatizam.

Por exemplo, você pode usar informações do cliente de uma lista do SharePoint como uma fonte para entrada em seu software de contabilidade herdado.

### <a name="define-inputs-in-the-ui-flows-wizard"></a>Definir entradas no assistente de fluxos de interface do usuário

1. Selecione "nova entrada"

   ![](../media/inputs-outputs-desktop/2eb6313a0e966f1fbfc352445b89ee39.png)

1. Adicione um nome, um exemplo de dados e uma descrição à sua entrada.

    - Os dados de exemplo são usados durante a gravação ou o teste.

    - A descrição será útil para diferenciar as entradas que você criou.

   ![](../media/inputs-outputs-desktop/e33d206bf2158228277a276261c49785.png)

1.  Depois que suas entradas forem criadas, você poderá clicar em avançar para usá-las em uma gravação.

### <a name="use-inputs-to-pass-information-to-the-application"></a>Usar entradas para passar informações para o aplicativo

1. Durante a gravação, você pode usar uma entrada em um aplicativo selecionando **usar entrada**.

1. Na lista, você pode escolher entre três opções:

    - Selecione uma das entradas que você definiu em fluxos de interface do usuário na etapa **Configurar campos de entrada** .

    - Use uma saída definida anteriormente (consulte a seção de saídas). Isso é útil para passar informações entre diferentes aplicativos dentro do mesmo fluxo de interface do usuário.

    - Crie uma nova entrada enquanto estiver gravando. Você o encontrará de volta na etapa ' **Configurar campos de entrada** ' de fluxos de interface do usuário.

   ![](../media/inputs-outputs-desktop/de36baa0f85d5a19304e1606de25aa3e.png)

1. Selecione o local onde você deseja usar a entrada. O valor de exemplo que você definiu é usado automaticamente. No exemplo abaixo, "Olá, mundo" é o valor de exemplo para o nome de entrada "minha entrada" e é adicionado à página no Microsoft Word.  
    
    ![](../media/inputs-outputs-desktop/d6b74dc86f38c51cf1daa0582ff0cc33.png)

1. Em energia automatizar **registro e editar etapas**, expanda ações que usam entradas para exibir qual delas está selecionada.

   ![](../media/inputs-outputs-desktop/340aa71942b618431b0455b632f76f52.png)

1. Ao disparar o fluxo de interface do usuário, você pode alterar o valor de entrada em. Consulte usar entradas & saídas para obter mais informações.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Usar saídas para extrair informações do aplicativo

As saídas permitem que você transmita informações do software herdado que o fluxo de interface do usuário automatiza para um destino externo, como um banco de dados ou qualquer [conector com suporte](https://flow.microsoft.com/connectors/).

Por exemplo, você pode extrair informações do cliente de seu software de contabilidade herdado e adicioná-lo a uma lista do SharePoint.

As saídas só podem ser criadas à medida que você registra seu fluxo de interface do usuário.

1. Durante uma gravação, selecione no botão "obter saída" do gravador

   ![](../media/inputs-outputs-desktop/13f8dfca19c0ed04ca2a0f87bf7055ea.png)

1. Selecione o botão "selecionar texto" (esse é o único tipo de saída disponível por enquanto)

   ![](../media/inputs-outputs-desktop/2845b73ee807a5be747c1dc494570ab7.png)

1. Clique em um elemento de interface do usuário para selecionar seu texto para a saída. O valor será capturado automaticamente.

   ![](../media/inputs-outputs-desktop/7df19b56aadcd0aef207c7372a04b3c6.png)

   ![](../media/inputs-outputs-desktop/af55a0bf39d805b154a783eff3de131b.png)

1. Defina o nome e a descrição da saída.

   ![](../media/inputs-outputs-desktop/a083579ee011dfb76aa21fac116796a3.png)

1. Selecione **salvar.** 

Sua saída agora está disponível na área dedicada do assistente

   ![](../media/inputs-outputs-desktop/b9f396de0b5893c5a3152b592911f67a.png)

Cada saída tem:

-  Um nome de saída conforme definido durante a gravação
-  Uma descrição: esse campo pode ser muito útil quando você define várias saídas durante uma gravação e deseja identificá-las facilmente.
-  Um nome de ação: a ação em que a saída foi definida em seu fluxo de interface do usuário

## <a name="delete-an-output-from-a-ui-flow"></a>Excluir uma saída de um fluxo de interface do usuário

Se você não precisar mais de uma saída, poderá excluí-la voltando para a ação associada e removendo o nome de saída no valor dinâmico.

## <a name="test-your-ui-flow"></a>Testar o fluxo da interface do usuário

O teste de fluxos de interface do usuário permite que você valide suas alterações e o comportamento de reprodução apropriado.

1. Adicional Insira o novo valor no campo de entrada. 
    
    ![](../media/inputs-outputs-desktop/0b4aef639c4ab30b93413e1e7a5e662d.png)

1. Clique em **testar agora** para ver o software herdado que está sendo automatizado. Você verá a automação do fluxo da interface do usuário reproduzindo as etapas que você registrou. **Não interaja com seu dispositivo durante a reprodução.**

1. Depois que a reprodução for concluída, você verá o status de execução do seu fluxo de interface do usuário:

    - Para cada ação, um status que indica que o teste funcionou bem e as entradas associadas.

    - O valor das saídas obtidas para este teste.

    - Caso um erro tenha sido gerado, você poderá ver qual etapa foi problemática com uma captura de tela do momento em que o erro ocorreu.

   ![](../media/inputs-outputs-desktop/85056d7942d12a5408005f5b683d432b.png)

## <a name="learn-more"></a>Saiba Mais

- Saiba como [disparar o fluxo de interface do usuário](run-ui-flow.md) que você acabou de criar.

- Se você quiser fazer mais com os fluxos da interface do usuário, você também poderá experimentar fluxos de interface do usuário com parâmetros [de entrada e saída](inputs-outputs-web.md) .


