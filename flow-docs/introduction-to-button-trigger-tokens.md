---
title: Introdução aos tokens de gatilho do botão | Microsoft Docs
description: Introdução aos tokens de gatilho de botão para fluxos de botão da Microsoft.
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
ms.date: 12/12/2016
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: dc1b93553938221c3f1c995b63b984cfff913c06
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64462591"
---
# <a name="get-started-with-button-trigger-tokens"></a>Introdução aos tokens de gatilho de botão
## <a name="what-are-button-trigger-tokens"></a>O que são os tokens de gatilho de botão?
Tokens de gatilho do botão são pontos de dados que são conhecidos e estão disponíveis para o dispositivo no qual um [fluxo de botão](introduction-to-button-flows.md) está em execução. Esses tokens se alteram com base em fatores como a hora atual ou a localização geográfica do dispositivo em um determinado momento.  

Por exemplo, se você estiver executando um fluxo de botão em um Smartphone, é provável que o **telefone saiba a hora** em seu local atual, bem como a data e o endereço atual. Nesse contexto, o tempo, a data e o endereço onde o telefone está localizado todos serão determinados durante a execução do fluxo de botão. Eles estão automaticamente disponíveis para uso em qualquer fluxo de botão que são executados no dispositivo. Você pode usar esses tokens de gatilho para construir fluxos úteis que irão minimizar tarefas repetitivas, como fornecer seu local a alguém ou controlar quanto tempo você gasta em uma chamada de trabalho/serviço específica.

### <a name="list-of-button-trigger-tokens"></a>Lista de tokens de gatilho de botão
Veja uma lista dos tokens de gatilho de botão que estão disponíveis para uso durante a criação de seus fluxos de botão.

| Parâmetro | Descrição |
| --- | --- |
| Cidade |A cidade onde o dispositivo que está executando o fluxo está localizado. |
| País/Região |O país/região onde o dispositivo que está executando o fluxo está localizado. |
| Endereço completo |O endereço completo onde o dispositivo que está executando o fluxo está localizado. |
| Latitude |A latitude onde o dispositivo que está executando o fluxo está localizado. |
| Longitude |A longitude onde o dispositivo que está executando o fluxo está localizado. |
| CEP |O CEP onde o dispositivo que está executando o fluxo está localizado. |
| Estado |O estado onde o dispositivo que está executando o fluxo está localizado. |
| Rua |A rua onde o dispositivo que está executando o fluxo está localizado. |
| Carimbo de data/hora |A hora na área onde o dispositivo que está executando o fluxo está localizado. |
| Data |A data na área onde o dispositivo que está executando o fluxo está localizado. |
| Nome de usuário |O nome de usuário da pessoa que está conectada no dispositivo que está executando o fluxo. |
| Email do usuário |O endereço de email da pessoa que está conectada no dispositivo que está executando o fluxo. |

## <a name="create-a-button-flow-that-uses-trigger-tokens"></a>Criar um fluxo de botão que usa tokens de gatilho
Quando você cria um botão, pode usar tokens de gatilho para adicionar uma funcionalidade avançada ao botão.

Neste passo a passo, nós criaremos um fluxo de botão em um dispositivo Android. O fluxo de botão usará tokens de gatilho para enviar a data e o endereço completo para seu chefe em um email "**trabalhando em casa**".

Neste passo a passo, você verá capturas de tela de um dispositivo Android. No entanto, a experiência é semelhante em dispositivos iOS e Windows Phone.

### <a name="prerequisites"></a>Pré-requisitos
* Um endereço de email corporativo ou de estudante ou uma [Conta da Microsoft](https://account.microsoft.com/about?refd=www.microsoft.com) com acesso ao Microsoft Flow.
* O aplicativo móvel Microsoft Flow para [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), ou [Windows Phone](https://aka.ms/flowmobilewindows).

Vamos começar:

1. Inicie o Flow e selecione **Procurar**   
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/1.png)  
2. Selecione o serviço **Enviar um email 'Trabalhando em casa hoje' para seu gerente** na categoria **Botão**   
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/2.png)  
3. Selecione **USAR ESTE MODELO**  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/3.png)  
4. Selecione **Editar** no cartão **Enviar um email**  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/3-5.png)  
5. Toque na caixa de texto **Assunto** e digite: " **hoje -** " na caixa de texto depois do texto "WFH". Observe que quando você tocou na caixa de texto, uma lista de parâmetros/tokens também abriu. Vamos usar um desses tokens na próxima etapa para adicionar a data ao assunto do email.  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/4.png)  
6. Com o cursor ainda na caixa de texto de assunto, role até a lista **manual** de parâmetros e toque em **Data**. Observe que o parâmetro de data agora está na caixa de texto **Assunto**:  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/6.png)  
7. Role até a caixa de texto **Corpo** e toque depois do padrão de mensagem para que os tokens adicionais possam ser incluídos lá.  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/7.png)  
8. Toque no parâmetro **Endereço completo** e, em seguida, toque em **Criar**  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/8.png)  
9. Toque em **Concluído**. Seu fluxo de botão está agora criado.  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/9.png)  

## <a name="run-the-button-flow"></a>Executar o fluxo de botão
**OBSERVAÇÃO**: Esse fluxo de botão enviará seu local atual por email.  

1. Toque na categoria **Botões** na parte inferior da tela. Você verá uma lista dos botões que você tem permissões para usar. Toque no botão que representa o fluxo de botão que você acabou de criar:  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/10.png)  
2. Toque em **PERMITIR** para indicar que o fluxo de botão pode acessar informações sobre o local do seu dispositivo:  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/11.png)  
3. Em poucos instantes, observe que o email foi enviado para seu chefe:  
   ![token de gatilho de botão](./media/introduction-to-button-trigger-tokens/12.png)  

Parabéns! Você acabou de criar um fluxo de botão que usa a data e a tokens de gatilho de endereço completo. 

## <a name="next-steps"></a>Próximas etapas
* [Compartilhar fluxos de botão](share-buttons.md)
* [Saiba mais sobre fluxos de botão](introduction-to-button-flows.md)
