---
title: Resumo de solicitações de titular dos dados do RGPD para contas da Microsoft (MSA) | Microsoft Docs
description: Saiba como responder às Solicitações de entidade de dados de GPDR para o Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/16/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 3742ac7afed24b0a1523a6038978589d293ba00b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460304"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Responder a solicitações de DSRs (direitos do titular dos dados) do RGPD

Este artigo descreve o GDPR (Regulamento Geral sobre a Proteção de Dados) da União Europeia e fornece etapas a que serem seguidas para assegurar a conformidade com o RGPD para os usuários do Microsoft Flow que se autenticam com contas da Microsoft (MSA).

## <a name="prerequisites"></a>Pré-requisitos

É necessária uma MSA com uma [licença gratuita do Microsoft Flow](https://flow.microsoft.com/pricing/) para executar as etapas neste artigo.

>[!TIP]
> Também há informações de conformidade com o RGPD disponíveis para usuários que se autenticam com [contas do Azure Active Directory](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Responder às DSRs de dados de clientes do Microsoft Flow

Uma solicitação formal de um titular dos dados a um controlador para executar uma ação em seus dados pessoais é chamada de solicitação de DSR (Direitos do Titular dos Dados). O RGPD define dados pessoais como  **todos os dados relacionados a uma pessoa física identificada ou identificável**. O RGPD concede às pessoas (conhecidas como titulares dos dados) direitos para gerenciarem os dados pessoais coletados por um empregador, um órgão ou uma organização (conhecidos como controladores de dados ou apenas controladores). Esses direitos incluem:

* Obter cópias dos dados pessoais.
* Solicitar correções nos dados pessoais.
* Restringir o processamento de dados pessoais.
* Excluir dados pessoais.
* Receber dados pessoais em formato eletrônico para que ele possa ser passado para outro controlador.

A Microsoft fornece produtos, serviços e ferramentas para ajudar os controladores a localizar e executar ações em dados pessoais ao responder a solicitações de DSRs de dados que residem na nuvem.

Aqui está uma visão geral dos processos descritos neste guia:

1. **Descobrir**: Use ferramentas de pesquisa e a descoberta para localizar facilmente os dados do cliente que podem ser o assunto de uma solicitação de DSR. Se você determinar que os documentos coletados atendam às diretrizes do controlador para executar ações, execute uma ou mais das ações de DSR descritas nas etapas a seguir. Saiba mais na [Documentação de descoberta de DSR do Microsoft Flow para contas da Microsoft](gdpr-dsr-discovery-msa.md). Como alternativa, você pode determinar que a solicitação não atende às diretrizes do controlador para responder às solicitações de DSR.

1. **Acesso**: Recupere dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia do mesmo modo que pode estar disponível para a entidade de dados.

1. **Corrigir**: faça alterações ou implemente outras ações solicitadas nos dados pessoais, conforme o necessário.

1. **Restringir**: restrinja o processamento de dados pessoais, removendo licenças de vários serviços online ou desabilitando os serviços desejados sempre que possível. Você também pode remover dados da nuvem da Microsoft e retê-los no local ou em outro lugar.

1. **Delete**: remova permanentemente os dados pessoais que residem na nuvem da Microsoft. Saiba mais sobre a [exclusão de dados pessoais de contas da Microsoft](gdpr-dsr-delete-msa.md). Saiba mais sobre o [encerramento de uma conta da Microsoft](gdpr-dsr-accountclose-msa.md).

1. **Exportar**: Forneça uma cópia eletrônica (em um formato legível por máquina) dos dados pessoais. [Saiba mais sobre como exportar dados pessoais de contas da Microsoft](gdpr-dsr-export-msa.md).
