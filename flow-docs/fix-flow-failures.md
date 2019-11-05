---
title: Solucionando problemas de um fluxo | Microsoft Docs
description: Resolver alguns dos motivos mais comuns pelos quais os fluxos falham
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
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2981c125d722cb766a1cc840f404d84dfa57ac96
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547872"
---
# <a name="troubleshooting-a-flow"></a>Solução de problemas de um fluxo
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="repair-tips-in-email"></a>Reparar dicas no email

As dicas de reparo são enviadas aos proprietários do fluxo por email sempre que um fluxo falha. Esses emails de dicas de reparo contêm comentários específicos e acionáveis sobre determinados erros. Por exemplo, um erro comum é a configuração de um fluxo que tenta obter o gerente de uma pessoa no Office 365, mas não há um Gerenciador configurado no Azure Active Directory (Azure AD). Se essa ou várias outras condições causarem falha no fluxo, você receberá um email de dicas de reparo como este:

![Dicas de reparo](media/fix-flow-failures/repair-tips-email.png)

O email de dicas de reparo contém as seguintes seções:

Nomes|Ndescrição
---|---
Momento|Exibe a hora em que o fluxo falhou primeiro.
O que aconteceu|Fornece uma descrição do problema que causou a falha no fluxo.
Correção de Como fazer|Fornece dicas para resolver o problema que causa a falha no fluxo.
Dicas de solução de problemas|Fornece detalhes, incluindo o número de vezes que o fluxo falhou e um link para repetir o fluxo com os mesmos dados de entrada.

Para corrigir os erros relatados, selecione **corrigir meu fluxo** e siga as etapas no email de dicas de reparo.

Os emails de dicas de reparo são opcionais. Se você não quiser recebê-los, basta desativá-los no menu Propriedades do fluxo específico.

Se o fluxo falhar, você também poderá solucioná-lo diretamente no Microsoft Flow.  Aqui estão alguns cenários comuns de falha e dicas sobre como corrigi-los.

## <a name="identify-the-error"></a>Identificar o erro
Para poder corrigir um fluxo, você deve identificar por que houve falha. Clique ou toque no ícone de notificações na parte superior do portal da Web (ou abra a guia **atividade** no aplicativo móvel) e, em seguida, clique ou toque em seu fluxo na lista exibida.

![Notificações](./media/fix-flow-failures/notifications-toolbar.png)

Os detalhes sobre o fluxo são exibidos e pelo menos uma etapa mostra um ícone de exclamação vermelho. Abra essa etapa e examine a mensagem de erro.

![Mensagem de erro](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Falhas de autenticação
Em muitos casos, os fluxos falham devido a um erro de autenticação. Se você tiver esse tipo de erro, a mensagem de erro conterá **não autorizado** ou um código de erro **401** ou **403** será exibido. Normalmente, você pode corrigir um erro de autenticação atualizando a conexão:

1. Na parte superior do portal da Web, clique ou toque no ícone de engrenagem para abrir o menu **configurações** e, em seguida, clique ou toque em **conexões**.
2. Role até a conexão para a qual você viu a mensagem de erro **não autorizado** .
3. Ao lado da conexão, clique ou toque no link **verificar senha** na mensagem sobre a conexão que não está sendo autenticada.
4. Verifique suas credenciais seguindo as instruções que aparecem, retorne à sua falha de execução de fluxo e, em seguida, clique ou toque em **reenviar**.
   
    O fluxo agora deve ser executado conforme o esperado.

## <a name="action-configuration"></a>Configuração da ação
Os fluxos também falham se uma configuração em uma ação do fluxo não funcionar conforme o esperado. Nesse caso, a mensagem de erro contém uma **solicitação inválida** ou **não foi encontrada**ou um código de erro **400** ou **404** é exibido.

A mensagem de erro deve especificar como corrigir a falha. Você precisará clicar ou tocar no botão **Editar** e corrigir o problema dentro da definição de fluxo. Salve o fluxo atualizado e, em seguida, clique ou toque em **reenviar** para tentar executar novamente com a configuração atualizada.

## <a name="other-failures"></a>Outras falhas
Se o código de erro **500** ou **502** for exibido, a falha será temporária ou transitória. Clique ou toque em **reenviar** para tentar o fluxo novamente.

## <a name="getting-help-from-support-or-the-community"></a>Obtendo ajuda do suporte ou da Comunidade

Quando precisar de ajuda, você poderá usar nossas opções de **auto-ajuda** ou **solicitar ajuda** de outras pessoas.

### <a name="self-help"></a>Auto-ajuda 

1. Vá para o [site de suporte](https://flow.microsoft.com/support/).
1. Vá para a categoria **auto-ajuda** e selecione uma das opções de autoajuda.

    ![Pedir a seção de ajuda. Contate o suporte.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Solicitar ajuda de outras pessoas

1. Vá para o [site de suporte](https://flow.microsoft.com/support/).
1. Selecione **contatar o suporte** na seção **solicitar ajuda** .
    
    ![Pedir a seção de ajuda. Contate o suporte.](media/fix-flow-failures/ask-for-help.png)

1. Conclua o **tipo de problema**, **categoria**e **diga-nos o que você precisa de ajuda com os** campos e, em seguida, selecione **Ver soluções**. 

1. Observe que a seção **soluções** é exibida depois que você seleciona **Ver soluções**. Ele contém uma lista de resultados que você pode usar para ajudar a resolver o problema que você está enfrentando. 

    ![Detalhes do auxiliar integrado](media/fix-flow-failures/integrated-helper-details.png)

Se você precisar de ajuda com um problema, a ajuda estará disponível em nossa [comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) e na Microsoft. 

