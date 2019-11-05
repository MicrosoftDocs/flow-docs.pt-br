---
title: Aprenda a editar fluxos de interface do usuário da área de trabalho | Microsoft Docs
description: Aprenda a editar fluxos de interface do usuário da área de trabalho.
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
ms.openlocfilehash: d5b7e186ae5c644f00f57946fff5ef3e946ba2ba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589829"
---
# <a name="edit-desktop-ui-flows"></a>Editar fluxos de IU da área de trabalho

[Este tópico é uma documentação de pré-lançamento e está sujeito a alterações.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Fluxos de interface do usuário da área de trabalho automatizam aplicativos do Windows desktop. Consulte os [problemas conhecidos](create-desktop.md#known-issues-and-solutions) para saber mais sobre os problemas que você pode encontrar, soluções alternativas para esses problemas e cenários que não têm suporte nesta versão de visualização.

## <a name="prerequisites"></a>Pré-requisitos
Um fluxo de interface do usuário da área de trabalho. [Crie um fluxo de interface do usuário da área de trabalho agora](create-desktop.md#create-and-test-desktop-ui-flows) se você não tiver um para editar.

## <a name="edit-actions"></a>Editar ações

![Editar ações](../media/edit-desktop/edit-actions.png "Editar ações")

Você pode editar a gravação em:

-   Modifique o valor de ações que dão suporte a ele.
-   Excluir uma etapa.
-   Exclua toda a gravação.
-   Altere a ordem das ações com arrastar e soltar. Tenha cuidado com isso, pois pode interromper a consistência da gravação.

Os parâmetros avançados permitem que você altere:

-  O atraso após a ação ser executada. Por exemplo, você pode adicionar um atraso de um segundo alterando PT0S para PT1S. Isso pode ser útil quando o aplicativo de destino tem um tempo de resposta lento que não é concluído antes da próxima etapa do fluxo da interface do usuário.
-   O [seletor](edit-desktop.md#set-the-selector) para o elemento de interface do usuário de destino.

## <a name="add-a-recording"></a>Adicionar uma gravação

Talvez você queira registrar o fluxo da interface do usuário em várias sessões. Depois de concluir sua primeira gravação, você pode proceder da seguinte maneira:

1. Entre na [energia automatizada](https://flow.microsoft.com).
1. Selecione **meus fluxos** > **fluxos da interface do usuário (versão prévia)** .
1. Selecione o fluxo da interface do usuário que você deseja editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Selecione **Editar**. 
1. Selecione **nova etapa**.

   ![Nova etapa](../media/edit-desktop/new-step.png "Nova etapa")

1. Selecione **registrar aplicativo** na lista de ações.

   ![Registrar aplicativo](../media/edit-desktop/select-record-ui-actions.png "Registrar aplicativo")

1. Selecione **Iniciar gravador**.

   ![Selecione Iniciar gravador](../media/create-windows-ui-flow/select-launch-recorder.png "Selecione Iniciar gravador")

   O controle de gravador é exibido na parte superior da tela.

   ![O gravador-controle](../media/create-windows-ui-flow/recorder-control.png "O gravador-controle")

1. Inicie o aplicativo que você deseja registrar.

     >[!TIP]
     >À medida que o mouse focaliza os controles no aplicativo, você observará que um contorno azul realça cada controle. Sempre aguarde o realce azul antes de selecionar um controle.
     >
     >Se o realce azul não for exibido em volta do elemento, talvez ele não seja gravado corretamente.

1. Selecione **registro** no controle do gravador.

1. Execute as etapas na interface do usuário do aplicativo que você está gravando e, em seguida, selecione **concluído** no controle do gravador.
1. Selecione **salvar**e teste o fluxo da interface do usuário.

## <a name="add-a-manual-action"></a>Adicionar uma ação manual

Depois de gravar um aplicativo com pelo menos uma ação, você pode adicionar manualmente qualquer uma das seguintes ações para esse aplicativo.

| **Action**          | **Mente**                                                       |
|---------------------|-------------------------------------------------------------------|
| Fechar aplicativo   |                                                                   |
| Clique com o botão direito         |                                                                   |
| Enviar chaves           | Envie chaves e combinações de teclas, como CTRL + C.                             |
| Clique com o botão esquerdo          |                                                                   |
| Obter texto            | Leia o texto de um elemento de interface do usuário e use-o como uma saída. |
| Inserir texto          |                                                                   |
| Obter elemento habilitado | Verifique se um elemento da interface do usuário está habilitado ou desabilitado.         |
| Limpar elemento       | Limpe o valor em um elemento de interface do usuário editável.             |
| Aguardar segundos    | Aguarde antes de continuar para a próxima etapa.                           |

Siga estas etapas para adicionar uma ação manual:

1. Entre na [energia automatizada](https://flow.microsoft.com).
1. Selecione **meus fluxos** > **fluxos da interface do usuário (versão prévia)** .
1. Selecione o fluxo da interface do usuário que você deseja editar.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Selecione **Editar**. 
1. Selecione o cartão de gravação que contém as etapas para as quais você deseja adicionar uma nova etapa.
   O cartão expande e exibe as etapas gravadas.

   ![Selecionar cartão de gravação](../media/edit-desktop/manual-select-recording-card.png)

1. Selecione **Adicionar uma ação** no cartão de gravação, logo abaixo da última etapa gravada.
   Você verá a lista de ações manuais listadas anteriormente no passo a passos. 

1. Selecione a ação que você deseja adicionar. Aqui, selecionei **obter elemento habilitado**, mas você pode selecionar qualquer ação que faça sentido para seu cenário.

   ![Selecione a ação a ser adicionada. png](../media/edit-desktop/select-action-to-add.png)

Depois que a ação for adicionada, será necessário definir o **seletor** nas opções avançadas da ação.

![Opções avançadas de ação](../media/edit-desktop/action-advanced-options.png "Opções avançadas de ação")

### <a name="set-the-selector"></a>Definir o seletor

O seletor identifica o elemento de interface do usuário no qual a ação é executada durante a reprodução. Recomendamos que você copie/cole essas informações de uma etapa separada direcionando o mesmo elemento de interface do usuário, se possível.

O formato do seletor é:

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

Você precisa fornecer os dados para os campos **elemementStack** e **elementXPath** do elemento selector.

Aqui está um exemplo de como seria o **elemementStack** .

![Pilha de elementos](../media/edit-desktop/elementstack.png "Pilha de elementos")

Você pode capturar o **elementXPath** usando o [gravador de interface do usuário do WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![Ferramenta WAD](../media/edit-desktop/wad-tool.png "Ferramenta WAD")

Remova o primeiro elemento (tudo antes de/Window) antes de usar o resultado em **elementXPath** do seletor.

Teste seu fluxo de interface do usuário para confirmar se o seu seletor funciona corretamente.

## <a name="next-steps"></a>Próximas etapas

- Saiba como [executar o fluxo da interface do usuário](run-ui-flow.md) que você acabou de editar.

- Se você quiser fazer mais com os fluxos da interface do usuário, você também poderá experimentar fluxos de interface do usuário com parâmetros [de entrada e saída](inputs-outputs-web.md) .

