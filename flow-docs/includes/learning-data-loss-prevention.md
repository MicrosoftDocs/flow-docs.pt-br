---
ms.openlocfilehash: 985e15451fd080e69310fea5617a0cf8f3c3c7f9
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64461088"
---
Com uma crescente lista de [serviços](https://flow.microsoft.com/services) disponíveis para criar fluxos de trabalho com o [Microsoft Flow](https://flow.microsoft.com), torna-se necessário proteger dados de negócios confidenciais ou essenciais armazenados em serviços corporativos, como o SharePoint ou o Salesforce. É provável que você pense que sua organização precisa criar uma política para garantir que dados corporativos confidenciais não sejam publicados nos serviços de clientes, como o Twitter e o Facebook. Com o Microsoft Flow, você pode facilmente criar políticas de **prevenção contra perda de dados** (DLP) para controlar exatamente com quais serviços de clientes seus dados corporativos podem ser compartilhados quando os usuários criarem fluxos.  

## <a name="terms-you-should-get-familiar-with"></a>Termos com os quais você deve se familiarizar

| Termo | Descrição |
| --- | --- |
| **DLP** |É a abreviação de prevenção contra perda de dados. Você criará uma política de DLP para gerenciar o compartilhamento de dados entre **serviços**. |
| **Serviços** |Os [Serviços](https://flow.microsoft.com/services) são aplicativos como o Salesforce, o SharePoint e o Twitter. Esses serviços, e muitos outros mais, são usados para criar fluxos. |
| **Grupo de dados** |Um agrupamento lógico de serviços. Você coloca os serviços que têm permissão para compartilhar dados no mesmo grupo de dados. Há dois grupos de dados disponíveis: **somente dados de negócios** e **dados de negócios não permitidos**. |
| **Ambiente** |Uma DLP é aplicada a um [ambiente](../environments-overview-admin.md). Um ambiente contém usuários. |
| **Usuários** |Os usuários são membros de sua organização aos quais uma política de DLP será aplicada, com base na associação a um ambiente. |
| **Fluxo** |Um fluxo é um aplicativo de fluxo de trabalho que usa combinações dos serviços disponíveis. |

## <a name="all-about-how-dlp-policies-work"></a>Tudo sobre o funcionamento das políticas de DLP
Uma política de DLP é simplesmente uma regra nomeada que dispõe cada serviço em um dos dois grupos de dados mutuamente exclusivos. Em seguida, essa regra é aplicada a um ambiente. Um ambiente é um agrupamento lógico de usuários. Os usuários não têm permissão para criar fluxos que compartilham dados entre os serviços dispostos em grupos de dados diferentes. Em outras palavras, os usuários só podem criar fluxos que compartilham dados entre os serviços dentro de um **único** grupo de dados. Não são permitidos compartilhamentos entre grupos de dados.  

| **Nome do grupo de dados** | **Descrição do grupo de dados** |
| --- | --- |
| **Somente dados de negócios** |Todos os serviços neste grupo podem compartilhar dados entre si. Eles não podem compartilhar dados com o grupo de dados **dados de negócios não permitidos**. |
| **Dados de negócios não permitidos** |Todos os serviços neste grupo podem compartilhar dados entre si. Eles não podem compartilhar dados com o grupo de dados **somente dados de negócios**. |

**Observação**: Adicionar um serviço a um grupo de dados automaticamente removerá este serviço do outro grupo de dados. Por exemplo, se atualmente o Twitter estiver localizado no grupo de dados **somente dados de negócios** e você não quiser permitir que os dados de negócios sejam compartilhados com o Twitter, basta adicionar o serviço do Twitter ao grupo de **dados de negócios não permitidos**. Isso removerá o Twitter do grupo de dados **somente dados de negócios**.

## <a name="heres-what-you-need-to-create-a-dlp"></a>Veja o que você precisa para criar uma DLP
* Acesso ao [centro de administração](https://admin.flow.microsoft.com) do Microsoft Flow  
* Uma conta na função de Administrador de Ambiente  
* Um ambiente com usuários atribuídos a ele  

## <a name="create-a-dlp-policy"></a>Criar uma política de DLP
Veja uma breve visão geral de como criar uma política de DLP:  

1. Dê um nome à política
2. Escolha o ambiente ao qual a política será aplicada
3. Adicione os serviços a um dos dois grupos de dados. Lembre-se de que somente os serviços localizados em um grupo específico podem compartilhar dados, portanto, qualquer fluxo que seja criado para compartilhar dados entre os serviços localizados nos dois grupos de dados serão bloqueados automaticamente quando o criador salvá-lo.  

Há também um [passo a passo detalhado](../prevent-data-loss.md) disponível nas políticas de DLP.  

## <a name="examples"></a>Exemplos
* Se você criasse uma política que restringisse os fluxos de compartilhamento de dados de negócios somente entre o SharePoint, usuários do Office 365, o Outlook do Office 365, o OneDrive for Business, o Dynamics 365, o SQL Server e o Salesforce, ela teria essa aparência:  
  ![](./media/learning-data-loss-prevention/a-few-business-centric-services.png)  
* Esta seria a aparência se você decidisse criar uma política para não permitir que membros de um ambiente específico criassem um fluxo para compartilhar dados do SharePoint. Observe que o SharePoint é o único serviço no grupo de dados **somente dados de negócios**:  
  ![somente dados de negócios](./media/learning-data-loss-prevention/sharepoint-only-no-sharing-guided-learning.png)

