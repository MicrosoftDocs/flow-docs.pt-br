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
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 69fecb42ba2b89f7a3f5b7541f62a4ee984832ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546191"
---
# <a name="billing-and-metering-questions"></a>Perguntas sobre cobrança e medição
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este artigo responde a perguntas frequentes sobre cobrança e medição em Microsoft Flow.

>[!NOTE]
> O PowerApps e o Microsoft Flow usarão um [novo modelo de licenciamento](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) a partir de 1º de outubro de 2019. 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Onde posso descobrir quais planos de preços estão disponíveis?

Consulte a [página de preços](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Onde posso descobrir qual é meu plano?

Consulte a [página de preços](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Como fazer planos de comutador?

No menu de navegação superior, selecione **saiba mais** > **preços**e selecione o plano para o qual você deseja alternar.

![Saiba mais > preços](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Como fazer saber quanto eu usei?

Se você estiver em um plano gratuito ou em um plano de avaliação, clique ou toque no ícone de engrenagem na barra de navegação superior para mostrar seu uso atual em relação ao plano. 

![Botão Configurações](./media/billing-questions/settings.png)

Se você estiver em um plano pago, as execuções serão agrupadas em todos os usuários em sua organização. Estamos trabalhando em recursos para expor a cota e o uso disponíveis em uma organização.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>O que acontece se meu uso exceder os limites?

Microsoft Flow acelera o fluxo é executado.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Onde posso encontrar mais informações sobre os limites de uso?

Na [página de preços](https://flow.microsoft.com/pricing/), consulte a seção **perguntas frequentes** .

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>O que acontece se eu tentar executar execuções com muita frequência?

Seu plano determina com que frequência seus fluxos são executados. Por exemplo, seus fluxos podem ser executados a cada 15 minutos se você estiver no plano gratuito. Se um fluxo for disparado menos de 15 minutos após sua última execução, ele será enfileirado até que 15 minutos tenham decorrido.

## <a name="what-counts-as-a-run"></a>O que conta como uma execução?

Sempre que um fluxo é disparado, seja por um gatilho automático ou iniciando-o manualmente, isso é considerado uma execução. Verifica se os novos dados não contam como execuções.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Há diferenças entre contas da Microsoft e contas corporativas ou de estudante para cobrança?

Ok. Se você entrar com uma conta da Microsoft (como uma conta que termina com @outlook.com ou @gmail.com), poderá usar apenas o plano gratuito. Para aproveitar os recursos no plano pago, entre com um endereço de email corporativo ou de estudante.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>Estou tentando atualizar, mas estou informado de que minha conta não está qualificada.

Para atualizar, use uma conta corporativa ou de estudante ou crie uma [conta de avaliação do Office 365](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Por que eu esgotava as execuções quando meu fluxo fosse executado apenas algumas vezes?

Determinados fluxos podem ser executados com mais frequência do que o esperado. Por exemplo, você pode criar um fluxo que envia uma notificação por push sempre que seu gerente enviar um email. Esse fluxo deve ser executado toda vez que você receber um email (de qualquer pessoa), pois o fluxo deve verificar se o email veio do seu gerente. Essa ação conta como uma execução.

Você pode contornar esse problema colocando toda a filtragem necessária no gatilho. No exemplo de notificação por push, expanda o menu **Opções avançadas** e forneça o endereço de email do gerente no campo **de** .

## <a name="other-limits-and-caveats"></a>Outros limites e limitações

* Cada conta pode ter até:
  * fluxos de 250.
  * 15 conectores personalizados.
  * total de 20 conexões por API e 100 conexões totais.
* Você pode instalar um gateway somente no ambiente padrão.
* Determinados conectores externos, como o Twitter, implementam a limitação de conexão para controlar a qualidade do serviço. Seus fluxos falham quando a limitação está em vigor. Se os fluxos estiverem falhando, examine os detalhes da execução que falhou no histórico de execução do fluxo.
