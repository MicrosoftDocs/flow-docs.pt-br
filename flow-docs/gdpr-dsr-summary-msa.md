---
title: Resumo de solicitações de entidades de dados do GDPR para contas da Microsoft (MSA) | Microsoft Docs
description: Saiba como responder a solicitações de entidade de dados de às GPDR para Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: bff3e050db40c60622496202a092f94cc1d36fca
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548175"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Responder a solicitações DSRs (GDPR data Subject Rights)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este artigo descreve o Regulamento Geral sobre a Proteção de Dados da União Europeia (GDPR) e fornece as etapas que você pode seguir para dar suporte à conformidade do GDPR para Microsoft Flow usuários que se autenticam com o MSA (contas da Microsoft).

## <a name="prerequisites"></a>Pré-requisitos

Você precisa de um MSA com uma [licença de Microsoft Flow gratuita](https://flow.microsoft.com/pricing/) para executar as etapas neste artigo.

>[!TIP]
> As informações de conformidade do GDPR também estão disponíveis para usuários que se autenticam com [contas de Azure Active Directory](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Responder a DSRs para dados do cliente Microsoft Flow

A solicitação formal de uma entidade de dados a um controlador para realizar uma ação em seus dados pessoais é chamada de solicitação de DSR (direitos de entidade de dados). GDPR define dados pessoais como **quaisquer dados relacionados a uma pessoa natural identificada ou identificável**. O GDPR fornece direitos de pessoas (conhecidas como entidades de dados) para gerenciar os dados pessoais coletados por um empregador, agência ou organização (conhecido como controlador de dados ou controlador). Esses direitos incluem:

* Obtendo cópias de dados pessoais.
* Solicitando correções em dados pessoais.
* Restrição de processamento de dados pessoais.
* Excluindo dados pessoais.
* Receber dados pessoais em um formato eletrônico para que ele possa ser movido para outro controlador.

A Microsoft fornece produtos, serviços e ferramentas para ajudar os controladores a localizar e agir em dados pessoais ao responder a solicitações DSRs para dados que residem na nuvem.

Aqui está uma visão geral dos processos descritos neste guia:

1. **Descobrir**: Use as ferramentas de pesquisa e descoberta para localizar facilmente os dados do cliente que podem ser o assunto de uma solicitação de DSR. Se você determinar que os documentos coletados atendam às diretrizes do controlador para executar uma ação, você poderá executar uma ou mais das ações de DSR descritas nas etapas a seguir. Saiba mais na [documentação de descoberta do Microsoft Flow DSR para contas da Microsoft](gdpr-dsr-discovery-msa.md). Como alternativa, você pode determinar que a solicitação não atende às diretrizes do controlador para responder às solicitações de DSR.

1. **Acesso**: recupere dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia dele para que o possa estar disponível para a entidade de dados.

1. **Corrigir**: faça alterações ou implemente outras ações solicitadas nos dados pessoais, quando aplicável.

1. **Restringir**: restringir o processamento de dados pessoais, removendo licenças para vários serviços online ou desativando os serviços desejados sempre que possível. Você também pode remover dados da nuvem da Microsoft e mantê-los localmente ou em outro local.

1. **Excluir**: Remova permanentemente os dados pessoais que residem na nuvem da Microsoft. Saiba mais sobre como [excluir dados pessoais de contas da Microsoft](gdpr-dsr-delete-msa.md). Saiba mais sobre como [fechar uma conta da Microsoft](gdpr-dsr-accountclose-msa.md).

1. **Exportar**: forneça uma cópia eletrônica (em um formato legível por computador) de dados pessoais. [Saiba mais sobre como exportar dados pessoais para contas da Microsoft](gdpr-dsr-export-msa.md).
