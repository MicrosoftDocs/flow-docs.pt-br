---
title: Solucionando problemas de um fluxo | Microsoft Docs
description: Resolver alguns dos motivos mais comuns para os fluxos falharem
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
ms.openlocfilehash: 0e151f3c5cd69fe07263e5fa36d46eb3b8be19f5
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64992685"
---
# <a name="troubleshooting-a-flow"></a>Solução de problemas de um fluxo

## <a name="repair-tips-in-email"></a>Dicas de reparo por email

As dicas de reparo são enviadas por email para proprietários de fluxo, sempre que um fluxo falha. Os emails com dicas de reparo contêm comentários específicos e práticos sobre determinados erros. Por exemplo, um erro comum é a configuração de um fluxo que tenta obter o gerente de um usuário no Office 365, quando não há nenhum gerente configurado no Microsoft Azure AD (Azure Active Directory). Quando essa ou várias outras condições causam a falha do fluxo, você recebe um email com dicas de reparo como este:

![Dicas de reparo](media/fix-flow-failures/repair-tips-email.png)

O email com dicas de reparo inclui as seguintes seções:

Nome|Descrição
---|---
Tempo|Exibe a hora em que o fluxo falhou pela primeira vez.
O que aconteceu|Fornece uma descrição do problema que causou a falha no fluxo.
Como faço para corrigir isso|Fornece dicas para resolver o problema que causa a falha no fluxo.
Dicas de solução de problemas|Fornece detalhes, como o número de vezes em que o fluxo falhou, e um link para repetir o fluxo com os mesmos dados de entrada.

Para corrigir os erros relatados, selecione **Corrigir meu fluxo** e siga as etapas descritas no email de dicas de reparo.

Os emails com dicas de reparo são opcionais. Caso prefira não recebê-los, basta desativar este recurso no menu "Propriedades" do fluxo específico.

Se o fluxo falhar, você poderá também solucionar o problema diretamente no Microsoft Flow.  Veja alguns cenários de falhas comuns e dicas sobre como corrigi-las.

## <a name="identify-the-error"></a>Identificar o erro
Antes de você poder corrigir um fluxo, deverá identificar o motivo da falha. Clique ou toque no ícone de notificações na parte superior do portal da Web (ou abra a guia **Atividade** no aplicativo móvel) e clique ou toque em seu fluxo na lista que aparece.

![Notificações](./media/fix-flow-failures/notifications-toolbar.png)

Os detalhes sobre o fluxo aparecem e pelo menos uma etapa mostra um ícone com exclamação vermelho. Abra essa etapa e examine a mensagem de erro.

![Mensagem de erro](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Falhas de autenticação
Em muitos casos, os fluxos falham devido a um erro de autenticação. Se você tiver esse tipo de erro, a mensagem de erro conterá **Não autorizado** ou um código de erro **401** ou **403** aparecerá. Geralmente, você pode corrigir um erro de autenticação atualizando a conexão:

1. Na parte superior do portal da Web, clique ou toque no ícone de engrenagem para abrir o menu **Configurações** e, em seguida, clique ou toque em **Conexões**.
2. Role até a conexão para a qual você viu a mensagem de erro **Não autorizado**.
3. Ao lado da conexão, clique ou toque no link **Verificar senha** na mensagem sobre a conexão que não está sendo autenticada.
4. Verifique suas credenciais seguindo as instruções que aparecem, retorne para a execução do fluxo com falha e clique ou toque em **Reenviar**.
   
    Agora, ela deve ser executada conforme o esperado.

## <a name="action-configuration"></a>Configuração de ação
Os fluxos também falharão se uma configuração em uma ação do fluxo não funcionar conforme o esperado. Neste caso, a mensagem de erro conterá **Solicitação ruim** ou **Não encontrada**, ou um código de erro **400** ou **404** aparecerá.

A mensagem de erro deve especificar como corrigir a falha. Você precisará clicar ou tocar no botão **Editar**, em seguida, corrigir o problema na definição do fluxo. Salve o fluxo atualizado e clique ou toque em **Reenviar** para tentar executar novamente com a configuração atualizada.

## <a name="other-failures"></a>Outras falhas
Se o código de erro **500** ou **502** aparecer, a falha será temporária ou transitória. Clique ou toque em **Reenviar** para tentar novamente o fluxo.

## <a name="getting-help-from-support-or-the-community"></a>Como obter ajuda do suporte ou da comunidade

Se precisar de ajuda, basta usar as opções **Autoajuda** ou **Pedir ajuda** a outras pessoas.

### <a name="self-help"></a>Autoajuda 

1. Vá para o [site de Suporte](https://flow.microsoft.com/support/).
1. Acesse a categoria **Autoajuda** e escolha uma das opções de autoajuda.

    ![Seção Pedir ajuda. Contatar o Suporte.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Pedir ajuda a outras pessoas

1. Vá para o [site de Suporte](https://flow.microsoft.com/support/).
1. Selecione **Contatar o Suporte**, na seção **Pedir ajuda**.
    
    ![Seção Pedir ajuda. Contatar o Suporte.](media/fix-flow-failures/ask-for-help.png)

1. Preencha os campos **Tipo de problema**, **Categoria** e **Diga-nos com o que você precisa de ajuda**, e selecione **Ver soluções**. 

1. A seção **Soluções** será exibida, quando você selecionar **Ver soluções**. Ela contém uma lista de resultados que podem ajudar a solucionar o problema que você está enfrentando. 

    ![Detalhes do auxiliar integrado](media/fix-flow-failures/integrated-helper-details.png)

Se precisar de assistência para resolver problemas, a Microsoft e nossa [comunidade](https://go.microsoft.com/fwlink/?LinkID=787467) disponibilizam ajuda. 

