---
title: Limites e configuração | Microsoft Docs
description: Limites e configuração
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
ms.date: 12/04/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8a8a6561840f91ab61b8d7440f1620c2e7cd0076
ms.sourcegitcommit: a505b0aac796960d57fccee92eb18c6566ac9c35
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2018
ms.locfileid: "53006945"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Limites e configuração no Microsoft Flow
Este tópico contém informações sobre os limites atuais e detalhes da configuração para os fluxos.

## <a name="request-limits"></a>Limites de solicitações
Estes são os limites para uma única solicitação de saída.

### <a name="timeout"></a>Tempo limite

| Nome | Limite |
| --- | --- |
| Tempo limite da solicitação para chamadas síncronas |120 segundos |
| Tempo limite da solicitação para chamadas assíncronas|Configurável. O máximo é 30 dias. |

### <a name="message-size"></a>Tamanho da mensagem

| Nome | Limite | Anotações |
| --- | --- | --- |
| Tamanho da mensagem |100 MB |Nem todas as APIs suportam os 100 MB totais. |
| Limite de avaliação de expressão |131.072 caracteres |`@concat()`, `@base64()`, `string` não podem exceder esse limite. |

### <a name="retry-policy"></a>Política de repetição

| Nome | Limite |
| --- | --- |
| Tentativas de repetição |90 | O padrão é 4. Para alterar as configurações de ação de uso padrão | 
| Atraso máximo de repetição |1 dia | |
| Atraso mínimo de repetição |5 segundos | |

## <a name="run-duration-and-retention"></a>Retenção e duração da execução
Estes são os limites para executar um único fluxo.

| Nome | Limite | Anotações |
| --- | --- | --- |
| Duração da execução |30 dias |Inclui fluxos de trabalho com etapas pendentes como aprovações. Após 30 dias, o tempo de qualquer etapa pendente se esgotará. As aprovações que atingiram o tempo limite serão removidas do centro de aprovação. Se alguém tentar aprovar uma solicitação que tenha atingido o tempo limite, ele receberá uma mensagem de erro. |
| Retenção de armazenamento |30 dias |Isso é a partir do início da execução. |
| Intervalo de recorrência mín. |1 minuto | |
| Intervalo de recorrência máx. |500 dias | |
| Retenção máxima de histórico de execução |28 dias, de acordo com as regras do RGPD. | |

## <a name="looping-and-debatching-limits"></a>Limites de loop e debatching
Estes são os limites para executar um único fluxo.

| Nome | Limite | Anotações |
| --- | --- | --- |
| Aplicar a cada item |100.000 |100.000 só está disponível para os planos premium. Caso contrário, você está limitado a 5.000. Você pode usar a ação de filtro para filtrar as matrizes maiores quando necessário. |
| Até iterações |5,000 | |
| Itens SplitOn |100.000 |Como se aplica a cada um, o limite é de 5.000, a menos que você esteja em um plano premium. |
| Aplicar a cada paralelismo |50 |Por padrão, os loops são executados em sequência (basicamente, o paralelismo é 1). Você pode configurar até 50 em paralelo. |
| Execuções de ações por 5 minutos | 100.000 | Além disso, você pode distribuir uma carga de trabalho entre mais de um fluxo, conforme necessário. |
| Chamadas de saída simultâneas de ações | Aproximadamente 2.500 | Reduza o número de solicitações simultâneas ou reduza a duração, conforme necessário. | 

## <a name="definition-limits"></a>Limites de definição
Estes são os limites para um único fluxo.

| Nome | Limite | Anotações |
| --- | --- | --- |
| Ações por fluxo de trabalho |250 |Você pode adicionar fluxos de trabalho aninhados para estender quando necessário. |
| Profundidade de aninhamento de ação de permissão |5 |Você pode adicionar fluxos de trabalho aninhados para estender quando necessário. |
| Máx. de caracteres por expressão |8,192 | |
| Limite de nome de `action`/`trigger` |80 | |
| Limite de tamanho de `description` |256 | |

## <a name="sharepoint-limits"></a>Limites do SharePoint
Há [limitações](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) sobre como você pode usar o Microsoft SharePoint com o Microsoft Flow e PowerApps.

## <a name="ip-address-configuration"></a>Configuração de endereço IP
O endereço IP do qual as solicitações do Microsoft Flow são enviadas depende da [região](regions-overview.md) onde o [ambiente](environments-overview-admin.md) que contém o fluxo está localizado. Atualmente, não publicamos FQDNs disponíveis para cenários de fluxo.

### <a name="logic-apps"></a>Aplicativos Lógicos
As chamadas feitas a partir de um fluxo percorrem diretamente o serviço de Aplicativo Lógico do Azure. Alguns exemplos dessas chamadas incluem HTTP ou HTTP + OpenAPI. Confira [a documentação dos Aplicativos Lógicos](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) para obter os endereços IP que são usados por esse serviço.

### <a name="connectors"></a>Conectores
As chamadas feitas de um conector em um fluxo (por exemplo, a API do SQL ou a API do SharePoint) virão do endereço IP especificado abaixo:

| Região | IP de saída |
| --- | --- |
| Pacífico Asiático | 13.75.36.64 – 13.75.36.79, 13.67.8.240 – 13.67.8.255, 52.175.23.169, 52.187.68.19, 52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 52.187.53.78, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124, 23.97.72.250  |
| Austrália  | 13.70.72.192 – 13.70.72.207, 13.72.243.10, 13.77.50.240 – 13.77.50.255, 13.70.136.174, 13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.188.38, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35, 13.70.88.23 |
| Canadá | 13.71.170.208 – 13.71.170.223, 13.71.170.224 – 13.71.170.239, 52.237.24.126, 40.69.106.240 – 40.69.106.255, 52.242.35.152, 52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56, 52.229.123.161, 52.233.27.68 |
| Europa | 13.69.227.208 – 13.69.227.223, 52.178.150.68, 13.69.64.208 – 13.69.64.223, 52.174.88.118, 52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 52.178.37.42, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254, 52.164.249.26, 137.117.161.181 |
| Índia  | 104.211.81.192 – 104.211.81.207, 52.172.211.12, 40.78.194.240 – 40.78.194.255, 13.71.125.22, 104.211.146.224 – 104.211.146.239, 104.211.189.218, 52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.49.180, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245, 52.172.153.107 |
| Japão | 13.78.108.0 – 13.78.108.15, 13.71.153.19, 40.74.100.224 – 40.74.100.239, 104.215.61.248, 104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 104.214.151.229, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229, 13.78.121.151 |
| América do Sul | 191.233.203.192 – 191.233.203.207, 104.214.19.48 – 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Reino Unido | 51.140.148.0 – 51.140.148.15, 51.140.80.51, 51.140.211.0 – 51.140.211.15, 51.141.47.105 |
| Estados Unidos | 13.89.171.80 – 13.89.171.95, 52.173.245.164, 40.71.11.80 – 40.71.11.95, 40.71.249.205, 40.70.146.208 – 40.70.146.223, 52.232.188.154, 52.162.107.160 – 52.162.107.175, 52.162.242.161, 40.112.243.160 – 40.112.243.175, 104.42.122.49, 104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Versão prévia (Estados Unidos)  | 13.71.195.32 – 13.71.195.47, 52.161.102.22, 13.66.140.128 – 13.66.140.143, 52.183.78.157, 52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 52.161.31.35, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29, 13.66.208.24 |

Por exemplo, se for necessário autorizar endereços IP para seu Banco de Dados SQL do Azure, você deverá usar esses endereços.

### <a name="required-services"></a>Serviços necessários
A tabela a seguir lista os serviços aos quais o Microsoft Flow se conecta. Certifique-se de que nenhum desses serviços esteja bloqueado na sua rede.

Domínios | Protocolos | Usos
--------|  ---------| -----
management.azure.com|https|Acesso ao Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Acesso à ADAL (Biblioteca de Autenticação do Active Directory).
graph.microsoft.com </br>graph.windows.net</br>|https|Acesso à API do Azure AD Graph – para obter informações de usuário, como uma foto de perfil.
*.azure-apim.net|https|Acesso ao tempo de execução para Conectores.
*.flow.microsoft.com|https|Acesso ao site do Microsoft Flow.
*.powerapps.com|https|Acesso ao site do PowerApps.
*.azureedge.net|https|Acesso à CDN do Microsoft Flow.
nps.onyx.azure.net|https|Acesso ao NPS (Net Promoter Score).
