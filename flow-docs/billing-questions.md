---
title: Perguntas sobre cobrança e medição | Microsoft Docs
description: Respostas para perguntas frequentes sobre cobrança e medição no Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/21/2017
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 65f2776af5b0219ea887302d5cfa9e101f62c309
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460670"
---
# <a name="billing-and-metering-questions"></a>Perguntas sobre medição e cobrança

Este artigo responde a perguntas frequentes sobre cobrança e medição no Microsoft Flow.

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Como posso descobrir quais planos de preços estão disponíveis?

Consulte a [página de preços](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Como posso descobrir qual é meu plano?

Consulte a [página de preços](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Como mudar entre planos?

No menu de navegação superior, selecione **Saiba Mais** > **Preços** e, em seguida, selecione o plano para o qual você deseja alternar.

![Saiba Mais > Preços](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Como saber quanto eu usei?

Se você estiver em um plano gratuito ou de teste, clique ou toque no ícone de engrenagem na barra de navegação superior para mostrar seu uso atual no plano. 

![Botão Configurações](./media/billing-questions/settings.png)

Se você estiver em um plano pago, as execuções serão agrupadas para todos os usuários em sua organização. Estamos trabalhando em recursos para expor a cota e o uso disponível em toda a organização.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>O que acontece se o uso exceder os limites?

O Microsoft Flow limita as execuções de fluxo.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Onde posso encontrar mais informações sobre os limites de uso?

Na [página de preços](https://flow.microsoft.com/pricing/), consulte a seção **Perguntas frequentes**.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>O que acontece se eu tentar realizar execuções com muita frequência?

Seu plano determina com que frequência seus fluxos são executados. Por exemplo, se você estiver no plano gratuito, seus fluxos poderão ser executados a cada 15 minutos. Se um fluxo for disparado menos de 15 minutos após a sua execução mais recente, ele será enfileirado até que os 15 minutos tenham passado.

## <a name="what-counts-as-a-run"></a>O que conta como uma execução?

Sempre que um fluxo é acionado, por um gatilho automático ou manualmente, isso é considerado uma execução. Verificações por novos dados não contam como execuções.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Há diferenças entre Contas da Microsoft e de contas de trabalho ou escola para cobrança?

Sim. Se você entrar com uma conta da Microsoft (como uma conta que termina em @outlook.com ou @gmail.com), poderá usar apenas o plano gratuito. Para aproveitar os recursos do plano pago, entre com um endereço de email corporativo ou de estudante.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Estou tentando atualizar, mas fui informado de que minha conta não está qualificada

Para atualizar, use uma conta corporativa ou de estudante, ou crie uma [conta de avaliação do Office 365](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Por que as execuções se esgotaram se meu fluxo executou somente algumas vezes?

Determinados fluxos podem ser executados com mais frequência do que o esperado. Por exemplo, você pode criar um fluxo que envia uma notificação por push sempre que seu gerente lhe enviar um email. Esse fluxo deve ser executado sempre que você receber um email (de qualquer pessoa), pois o fluxo deve verificar se o email veio de seu gerente. Essa ação contará como uma execução.

Você pode contornar esse problema, colocando todas as filtragens necessárias no gatilho. No exemplo de notificação por push, expanda o menu **Opções Avançadas** e forneça o endereço de email do gerente no campo **De**.

## <a name="other-limits-and-caveats"></a>Outros limites e advertências

* Cada conta pode ter:
  * 250 fluxos.
  * 15 conectores personalizados.
  * 20 conexões por API e 100 conexões no total.
* Você pode instalar um gateway apenas no ambiente padrão.
* Determinados conectores externos, como o Twitter, implementam limitação de conexão para controlar a qualidade de serviço. Seus fluxos falham quando a limitação estiver em vigor. Se seus fluxos estiverem falhando, examine os detalhes da execução que falhou no histórico de execução do fluxo.
