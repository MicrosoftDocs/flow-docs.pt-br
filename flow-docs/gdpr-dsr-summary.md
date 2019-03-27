---
title: Resumo de solicitações da entidade de dados de GDPR | Microsoft Docs
description: Saiba como responder às Solicitações de entidade de dados de GPDR para o Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 1eaa98b674e78f46988d253e2be76a5d92283a76
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58353115"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Responder às Solicitações de entidade de dados de GDPR do Microsoft Flow

Este artigo prepara você, e a sua organização, para o GDPR (Regulamento Geral sobre a Proteção de Dados). Este artigo descreve o que a Microsoft está fazendo para preparar-se para o RGPD e também compartilha exemplos de etapas que você pode executar hoje mesmo para estar em conformidade com o RGPD ao usar o PowerApps, o Microsoft Flow e o Common Data Service.

## <a name="prerequisites"></a>Pré-requisitos

Os usuários e administradores podem executar as ações descritas neste artigo.

### <a name="users"></a>Usuários

Um usuário precisa ter uma conta ativa do Azure Active Directory com uma [licença do Microsoft Flow](https://preview.flow.microsoft.com/pricing/). Os usuários que não atenderem a esse requisito deverão solicitar a um administrador que execute essas ações.

### <a name="administrators"></a>Administradores

Você pode executar as operações que exigem privilégios de administrador, descritas neste artigo se você entrar no [Centro de Administração do Microsoft Flow](https://admin.flow.microsoft.com/) ou [PowerShell para Administração do PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) com uma conta que tenha essas duas permissões:

- Uma licença de avaliação ou paga do PowerApps Plano 2.

    [Uma licença de avaliação](http://web.powerapps.com/trial) expira em 30 dias.

- [Administrador Global do Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) ou [Administrador Global do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Locatários não gerenciados
Se você for membro de um [locatário não gerenciado](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), o que significa que seu locatário do Azure AD não tem um administrador global, você ainda poderá seguir as etapas descritas neste artigo para exportar e remover seus próprios dados pessoais. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Resposta a DSRs para dados de cliente do Microsoft Flow

O GDPR concede direitos às pessoas (conhecidas no GDPR como entidades de dados) para gerenciar os dados pessoais coletados por um empregador ou outro tipo de agência ou organização (conhecido como controlador de dados ou apenas controlador). Os dados pessoais são definidos de forma muito abrangente no GDPR como quaisquer dados relacionados a uma pessoa física identificada ou passível de identificação. O GDPR fornece às entidades de dados direitos específicos aos seus dados pessoais; esses direitos incluem a obtenção de cópias de dados pessoais, a solicitação de correções, a restrição de processamento desses dados, exclusão ou recebimento em um formato eletrônico, para que possam ser transferidos para outro controlador. Uma solicitação formal de uma entidade de dados a um controlador para executar uma ação em seus dados pessoais é chamada de Solicitação DSR (Direitos de Entidade de Dados).

Este artigo descreve como usar os produtos, serviços e ferramentas administrativas da Microsoft para ajudar os controladores a localizar e agir sobre dados pessoais ao responder aos DSRs. Especificamente, este artigo inclui como localizar, acessar e agir sobre dados pessoais que residem na nuvem da Microsoft. Aqui está uma rápida visão geral dos processos descritos neste guia:

1. Descobrir: use as ferramentas de pesquisa e de descoberta para localizar com mais facilidade os dados do cliente que possam ser o assunto de um DSR. Após a coleta de documentos potencialmente responsivos, você pode executar uma ou mais ações de DSR descritas nas etapas a seguir para responder à solicitação. Como alternativa, você pode determinar que a solicitação não atende às diretrizes da sua organização por respostas aos DSRs. [Documentação de descoberta de DSR do Microsoft Flow](gdpr-dsr-discovery.md)

1. Acessar: recupere os dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia que possa ser disponibilizada para o titular dos dados.

1. Corrigir: faça alterações ou implemente outras ações solicitadas nos dados pessoais, conforme o necessário.

    Se uma entidade de dados solicitar a correção dos dados pessoais dela que residem em sua organização, você e sua organização deverão determinar se é apropriado aceitar a solicitação.  A correção dos dados pode incluir a execução de ações como edição, redação ou remoção de dados pessoais.

    Você pode usar o Azure Active Directory para gerenciar identidades de usuários do Microsoft Flow. Os clientes empresariais podem gerenciar solicitações de correção de DSR, incluindo recursos de edição limitada, de acordo com a natureza de um determinado serviço da Microsoft.  Como processador de dados, a Microsoft não oferece a capacidade de corrigir os logs gerados pelo sistema, pois esses logs refletem atividades reais e constituem um registro histórico de eventos nos serviços da Microsoft.  [Saiba mais sobre DSR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Restringir: restrinja o processamento de dados pessoais, removendo licenças de vários serviços online ou desabilitando os serviços desejados sempre que possível. Você também pode remover dados da nuvem da Microsoft e retê-los no local ou em outro lugar.

    As entidades de dados podem solicitar a restrição do processamento de seus dados pessoais.  A Microsoft fornece APIs (interfaces de programação de aplicativo) e UIs (interfaces de usuário) para essa finalidade.  Essas interfaces permitem que o administrador de locatário do cliente corporativo gerencie esses DSRs por meio de uma combinação de exportação e exclusão de dados. Um cliente pode (1) exportar uma cópia eletrônica dos dados pessoais do usuário, incluindo contas, logs gerados pelo sistema e logs associados, e logo depois (2) excluir a conta e os dados associados que residem nos sistemas da Microsoft.

1. Excluir: remova permanentemente os dados pessoais que residem na nuvem da Microsoft. [Saiba mais sobre como excluir dados pessoais](gdpr-dsr-delete.md).

1. Exportar: forneça uma cópia eletrônica (em um formato legível por computador) dos dados pessoais ao titular dos dados. Cada seção deste artigo descreve os procedimentos técnicos que uma organização controladora de dados pode seguir para responder a um DSR de dados pessoais na nuvem da Microsoft. [Saiba mais sobre como exportar dados pessoais](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Logs gerados pelo sistema

Veja este [guia](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) para saber mais sobre logs gerados pelo sistema para o Microsoft Flow.
