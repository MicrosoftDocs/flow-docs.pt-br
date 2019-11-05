---
title: Resumo de solicitações de entidades de dados do GDPR | Microsoft Docs
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
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: c4d2686e9da00aaccc46e62570de387678bd1ece
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548219"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Respondendo a solicitações de entidade de dados GDPR para Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Este artigo prepara você e sua organização para o Regulamento Geral sobre a Proteção de Dados da União Europeia (GDPR). Este artigo não apenas descreve o que a Microsoft está fazendo para se preparar para o GDPR, mas também compartilha exemplos de etapas que você pode tomar hoje para dar suporte à conformidade com o GDPR ao usar o PowerApps, Microsoft Flow e Common Data Service.

## <a name="prerequisites"></a>Pré-requisitos

Os usuários e administradores podem executar as ações descritas neste artigo.

### <a name="users"></a>Podem

Um usuário precisa ter uma conta de Azure Active Directory ativa com uma [licença de Microsoft Flow](https://preview.flow.microsoft.com/pricing/). Os usuários que não atendem a esse requisito precisam solicitar que um administrador execute essas ações.

### <a name="administrators"></a>Os

Você pode executar as operações que exigem privilégios de administrador, descritas neste artigo se você entrar no centro de [administração Microsoft Flow](https://admin.flow.microsoft.com/) ou no [PowerShell de administrador do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) com uma conta que tenha essas duas permissões:

- Uma licença paga ou de avaliação para o plano 2 do PowerApps.

    [Uma licença de avaliação](http://web.powerapps.com/trial) expira em 30 dias.

- Administrador [global do Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) ou [Azure Active Directory administrador global](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Locatários não gerenciados
Se você for um membro de um [locatário não gerenciado](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), o que significa que seu locatário do Azure ad não tem administrador global, você ainda poderá seguir as etapas descritas neste artigo para exportar e remover seus próprios dados pessoais. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Respondendo a DSRs para dados do cliente Microsoft Flow

O GDPR concede direitos às pessoas (conhecidas no GDPR como entidades de dados) para gerenciar os dados pessoais que foram coletados por um empregador ou outro tipo de agência ou organização (conhecido como controlador de dados ou apenas controlador). Os dados pessoais são definidos de forma muito ampla no GDPR como qualquer dado relacionado a uma pessoa natural identificada ou identificável. O GDPR concede direitos específicos aos entidades de dados aos seus dados pessoais; esses direitos incluem a obtenção de cópias de dados pessoais, a solicitação de correções, a restrição do processamento dele, a exclusão ou o recebimento deles em formato eletrônico, para que possam ser movidos para outro controlador. Uma solicitação formal por um dado sujeito a um controlador para realizar uma ação em seus dados pessoais é chamada de solicitação de DSR (direitos de entidade de dados).

Este artigo discute como usar os produtos, serviços e ferramentas administrativas da Microsoft para ajudar os controladores a localizar e agir sobre dados pessoais ao responder a DSRs. Especificamente, este artigo inclui como localizar, acessar e agir sobre dados pessoais que residem na nuvem da Microsoft. Veja uma visão geral rápida dos processos descritos neste guia:

1. Descobrir: Use as ferramentas de pesquisa e descoberta para encontrar mais facilmente os dados do cliente que podem ser o assunto de um DSR. Depois que os documentos potencialmente responsivos são coletados, você pode executar uma ou mais das ações de DSR descritas nas etapas a seguir para responder à solicitação. Como alternativa, você pode determinar que a solicitação não atende às diretrizes da sua organização para responder a DSRs. [Documentação de descoberta do Microsoft Flow DSR](gdpr-dsr-discovery.md)

1. Acesso: recupere dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia dele que possa estar disponível para a entidade de dados.

1. Corrigir: faça alterações ou implemente outras ações solicitadas nos dados pessoais, quando aplicável.

    Se uma entidade de dados solicitar que você corrija seus dados pessoais que residem em sua organização, você e sua organização deverão determinar se é apropriado honrar a solicitação.  Corrigir os dados pode incluir a execução de ações como editar, redação ou remover dados pessoais.

    Você pode usar Azure Active Directory para gerenciar as identidades de Microsoft Flow usuários. Os clientes corporativos podem gerenciar solicitações de retificação DSR, incluindo recursos de edição limitados, de acordo com a natureza de um determinado serviço da Microsoft.  Como um processador de dados, a Microsoft não oferece a capacidade de corrigir os logs gerados pelo sistema, pois esses logs refletem as atividades reais e constituem um registro histórico dos eventos nos serviços da Microsoft.  [Saiba mais sobre o DSR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Restringir: restringir o processamento de dados pessoais, removendo licenças para vários serviços online ou desativando os serviços desejados sempre que possível. Você também pode remover dados da nuvem da Microsoft e mantê-los localmente ou em outro local.

    As entidades de dados podem solicitar que você restrinja o processamento de seus dados pessoais.  A Microsoft fornece interfaces de programação de aplicativo (APIs) e interfaces de usuário (UIs) para essa finalidade.  Essas interfaces permitem que o administrador de locatários do cliente corporativo gerencie tal DSRs por meio de uma combinação de exportação de dados e exclusão de dados. Um cliente pode (1) exportar uma cópia eletrônica dos dados pessoais do usuário, incluindo contas, logs gerados pelo sistema e logs associados, seguido de (2) exclusão da conta e dos dados associados que residem nos sistemas da Microsoft.

1. Excluir: Remova permanentemente os dados pessoais que residem na nuvem da Microsoft. [Saiba mais sobre como excluir dados pessoais](gdpr-dsr-delete.md).

1. Exportar: forneça uma cópia eletrônica (em um formato legível por computador) de dados pessoais para a entidade de dados. Cada seção deste artigo descreve os procedimentos técnicos que uma organização do controlador de dados pode tomar para responder a um DSR para dados pessoais na nuvem da Microsoft. [Saiba mais sobre como exportar dados pessoais](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Logs gerados pelo sistema

Consulte este [guia](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) para obter mais informações sobre os logs gerados pelo sistema para Microsoft Flow.
