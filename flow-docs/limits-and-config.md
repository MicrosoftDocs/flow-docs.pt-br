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
ms.date: 05/30/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c6a9b3c344ac25afe90c607b4a665aeaab49321f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547368"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Limites e configuração no Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Este tópico contém informações sobre os limites atuais e detalhes de configuração para fluxos.

## <a name="request-limits"></a>Limites de solicitação
Esses são os limites para uma única solicitação de saída.

### <a name="timeout"></a>cedido

| Nomes | Limite |
| --- | --- |
| Tempo limite da solicitação para chamadas síncronas |120 segundos |
| Tempo limite da solicitação para chamadas assíncronas|Configurável. O máximo é de 30 dias. |

### <a name="message-size"></a>Tamanho da mensagem

| Nomes | Limite | Registra |
| --- | --- | --- |
| Tamanho da mensagem |100 MB |Nem todas as APIs dão suporte a 100 MB completos. |
| Limite de avaliação de expressão |131.072 caracteres |`@concat()`, `@base64()`, `string` não pode exceder esse limite. |

### <a name="retry-policy"></a>Política de repetição

| Nomes | Limite |
| --- | --- |
| Tentativas de repetição |90 | O padrão é 4. Para alterar as configurações de ação de uso padrão | 
| Atraso máximo de repetição |1 dia | |
| Atraso mínimo de repetição |5 segundos | |

## <a name="run-duration-and-retention"></a>Duração e retenção da execução
Esses são os limites para uma execução de fluxo único.

| Nomes | Limite | Registra |
| --- | --- | --- |
| Duração da execução |30 dias |Inclui fluxos de trabalho com etapas pendentes, como aprovações. Após 30 dias, qualquer tempo limite de etapas pendentes. Aprovações de tempo limite são removidas do centro de aprovações. Se alguém tentar aprovar uma solicitação de tempo limite, receberá uma mensagem de erro. |
| Retenção de armazenamento |30 dias |Isso é a partir da hora de início da execução. |
| Intervalo de recorrência mín. |1 minuto | |
| Intervalo de recorrência máximo |500 dias | |
| Retenção do histórico de execução máx. |28 dias, por regras de GDPR. | |
|Intervalo de adiamento mínimo – licença gratuita e plano 1|5 segundos||
|Intervalo de adiamento mínimo – licença do plano 2|1 segundo||

## <a name="looping-and-debatching-limits"></a>Limites de loop e delote
Esses são os limites para uma execução de fluxo único.

| Nomes | Limite | Registra |
| --- | --- | --- |
| Aplicar a cada item-licença gratuita|5\.000 |Você pode usar a ação de filtro para filtrar matrizes maiores, conforme necessário. |
| Aplicar a cada item-plano 1 e licença do plano 2|100.000 |Você pode usar a ação de filtro para filtrar matrizes maiores, conforme necessário. |
| Até iterações |5\.000 | |
| Itens de divisão-licença gratuita |5\.000 ||
| Itens de divisão – plano 1 e licença do plano 2 |100.000 ||
| Aplicar a cada paralelismo |50 |Por padrão, os loops são executados em sequência (essencialmente, o paralelismo é 1). Você pode configurar até 50 em paralelo. |
| Execuções de ações por 5 minutos – gratuita, Office365, plano 1 e planos de avaliação | 2\.000 | Além disso, você pode distribuir uma carga de trabalho entre mais de um fluxo, conforme necessário. |
|Execuções de ações por 5 minutos – licenças pagas do plano 2|100.000|Além disso, você pode distribuir uma carga de trabalho entre mais de um fluxo, conforme necessário.|
|Execuções de ações por 5 minutos – licenças pagas do plano 2|150.000|Além disso, você pode distribuir uma carga de trabalho entre mais de um fluxo, conforme necessário.|
| Ações de chamadas simultâneas de saída – licença gratuita e plano 1 | ~ 500 | Reduza o número de solicitações simultâneas ou reduza a duração conforme necessário. |
| Execuções de ações por 24 horas – gratuita, Office365, plano 1 e planos de avaliação | ~ 2.500 | Reduza o número de solicitações simultâneas ou reduza a duração conforme necessário. | 

## <a name="throughput-limits"></a>Limites de taxa de transferência

|Nomes|Limite|Registra|
|---|---|---|
|Ponto de extremidade de tempo de execução-número de chamadas de leitura permitidas por 5 minutos – licença gratuita e plano 1|6\.000||
|Ponto de extremidade de tempo de execução-número de chamadas de leitura permitidas por 5 minutos-licença do plano 2|60.000||
|Ponto de extremidade de tempo de execução: invocar chamadas por 5 minutos – licença gratuita e plano 1|4\.500||
|Ponto de extremidade de tempo de execução: número de chamadas Invoke por 5 minutos-licença do plano 2|45.000||
|Quantidade de taxa de transferência permitida por 5 minutos – licença gratuita e plano 1|600 MB||
|Quantidade de taxa de transferência permitida por 5 minutos-licença do plano 2|6 GB||
|A quantidade de fluxos de conteúdo tem permissão para produzir (entradas/saídas de ações) por hora-gratuita, plano 1 e licença do plano 2|200 GB||


## <a name="definition-limits"></a>Limites de definição
Esses são os limites para um único fluxo.

| Nomes | Limite | Registra |
| --- | --- | --- |
| Ações por fluxo de trabalho |250 |Você pode adicionar fluxos de trabalho aninhados para estendê-lo conforme necessário. |
| Profundidade de aninhamento de ação permitida |8 |Você pode adicionar fluxos de trabalho aninhados para estendê-lo conforme necessário. |
| Máximo de caracteres por expressão |8\.192 | |
| limite de nome de `trigger` de /de `action` |80 | |
| limite de comprimento de `description` |256 | |

## <a name="sharepoint-limits"></a>Limites do SharePoint
Há [limitações](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) sobre como você pode usar o Microsoft SharePoint com o Microsoft Flow e o PowerApps.

## <a name="ip-address-configuration"></a>Configuração de endereço IP
O endereço IP do qual Microsoft Flow solicitações são enviadas depende da [região](regions-overview.md) em que o [ambiente](environments-overview-admin.md) que contém o fluxo está localizado. Atualmente, não publicamos FQDNs disponíveis para cenários de fluxo.

>[!IMPORTANT]
> Algumas chamadas de fluxo podem vir de endereços IP listados na documentação dos [aplicativos lógicos](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) . Alguns exemplos dessas chamadas incluem HTTP ou HTTP + OpenAPI.

### <a name="logic-apps"></a>Aplicativos lógicos
As chamadas feitas de um fluxo vão diretamente por meio do serviço de aplicativo lógico do Azure. Alguns exemplos dessas chamadas incluem HTTP ou HTTP + OpenAPI. Consulte [a documentação dos aplicativos lógicos](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) para os quais os endereços IP são usados por esse serviço.

### <a name="connectors"></a>Nos
As chamadas feitas de um conector em um fluxo (por exemplo, a API do SQL ou a API do SharePoint) serão provenientes dos endereços IP listados aqui:

| Regionais | IP de saída |
| --- | --- |
| Pacífico Asiático | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Austrália  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Canadá | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Européia | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| Índia  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japão | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| América do Sul | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Reino Unido | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| Estados Unidos | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Visualização (Estados Unidos)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Por exemplo, se você precisar autorizar endereços IP para seu banco de dados SQL do Azure, você deve usar esses endereços.

### <a name="required-services"></a>Serviços necessários
A tabela a seguir lista os serviços aos quais Microsoft Flow se conecta. Certifique-se de que nenhum desses serviços esteja bloqueado na sua rede.

domínios | Protocolos | Utilize
--------|  ---------| -----
management.azure.com|https|Acesso ao Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Acesso a Biblioteca de Autenticação do Active Directory (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Acesso ao Azure AD API do Graph-para obter informações do usuário, como uma foto de perfil.
*. azure-apim.net|https|Acesso ao tempo de execução para conectores.
*. flow.microsoft.com|https|Acesso ao site do Microsoft Flow.
*. powerapps.com|https|Acesso ao site do PowerApps.
*. azureedge.net|https|Acesso ao Microsoft Flow CDN.
nps.onyx.azure.net|https|Acesso ao NPS (Pontuação do promovar net).
