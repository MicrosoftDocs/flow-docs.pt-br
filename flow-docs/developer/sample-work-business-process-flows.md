---
title: 'Exemplo: trabalhar com fluxos de processo de negócios | MicrosoftDocs'
description: O exemplo demonstra como trabalhar programaticamente com fluxos de processo de negócios, como recuperar as instâncias de fluxo do processo de negócios para um registro de entidade, recuperar o caminho ativo para uma instância de fluxo de processo de negócios e seus estágios de processo e alterar o estágio ativo.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 2eb6f7586ddc8d5bf51b9c57f91bbc5c7c10131b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547765"
---
# <a name="sample-work-with-business-process-flows"></a>Exemplo: trabalhar com fluxos de processo de negócios
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Este exemplo demonstra como trabalhar programaticamente com fluxos de processo de negócios, como recuperar as instâncias de fluxo do processo de negócios para um registro de entidade, recuperar o caminho ativo para uma instância de fluxo de processo de negócios e seus estágios de processo e alterar o estágio ativo. Para obter informações sobre esses conceitos, consulte [trabalhar com fluxos de processos de negócios usando código](business-process-flows-code.md)  

 Este exemplo está disponível para download no [exemplo: trabalhar com fluxos de processo de negócios](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Pré-requisitos  
 Antes de executar o exemplo:  

1. Ter acesso a um ambiente de Common Data Service.  

2. Tenha os privilégios apropriados nas entidades do cliente potencial, oportunidade e fluxo de trabalho e nos registros de entidade de definição do fluxo de processos de negócios usados neste exemplo.  

3. Tenha o Visual Studio 2015 ou posterior para executar o exemplo.  

4. Ter conexão com a Internet para baixar o projeto de exemplo e restaurar os pacotes NuGet usados no projeto de exemplo.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>O que este exemplo faz  

1.  Cria um registro de Lead de exemplo. Isso cria automaticamente uma instância do fluxo do processo de negócios "gerar processo de vendas de oportunidades" para o registro de Lead.  

2.  Converte o registro de Lead em um registro de oportunidade.  


4.  Recupera as instâncias de fluxo do processo de negócios associadas ao registro "oportunidade" usando a mensagem de `RetrieveProcessInstances`. O primeiro registro na coleção retornada é a instância ativa do fluxo do processo de negócios para o registro de oportunidade, que é "cliente potencial para o processo de vendas da oportunidade" nesse caso.  

5.  Recupera o caminho ativo e os estágios do processo para a instância "processo de vendas do cliente potencial para oportunidade" usando a mensagem `RetrieveActivePath`.  

6.  Recupera o estágio atualmente ativo da instância "cliente potencial para o processo de vendas da oportunidade" e solicita ao usuário se mover para o próximo estágio. Quando a confirmação for movida, o definirá o próximo estágio no caminho ativo como o estágio ativo da instância "cliente potencial para o processo de vendas da oportunidade".  

7.  Por fim, o solicita ao usuário se deseja excluir os registros criados durante a execução de exemplo.  

     Aqui está a saída do exemplo:  

    ![Saída de exemplo](media/work-with-bpf-sample-output.png "Saída de exemplo")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Executar o exemplo  

1. [Baixe](https://go.microsoft.com/fwlink/p/?LinkId=846108) o projeto de exemplo do WorkWithBPF Visual Studio e extraia-o para uma pasta no seu computador.  

2. Localize o arquivo de `WorkWithBPF.sln` na pasta extraída e abra-o no Visual Studio.  

3. O projeto de exemplo usa pacotes NuGet que devem ser restaurados antes de executar o exemplo. Verifique se a restauração automática de pacotes NuGet está habilitada no Visual Studio. Mais informações: [Habilitando e desabilitando a restauração do pacote NuGet](https://go.microsoft.com/fwlink/?linkid=846106)  

    Como alternativa, selecione **projeto** > **gerenciar pacotes NuGet**e selecione **restaurar** para restaurar manualmente os pacotes usados no exemplo.  

4. Pressione F5 ou selecione **depurar** > **iniciar a depuração**.  

5. Se você não tiver executado anteriormente um dos exemplos antes, precisará inserir informações para executar o código, caso contrário, insira o número para uma das instâncias que você configurou anteriormente.  


   |                                 Aviso                                  |                                                                                             Ndescrição                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Insira um nome e uma porta do servidor do Dynamics 365 [crm.dynamics.com]       | Digite o nome do seu servidor do Dynamics 365. O padrão é o Dynamics 365 (online) (crm.dynamics.com) no América do Norte.<br /><br /> Exemplo <br />crm5.dynamics.com |
   | Esta organização foi provisionada no Microsoft serviços online (s/n) [n] |                                                 Digite **y** se esta for uma organização Microsoft serviços online provisionada. Caso contrário, digite **n**.                                                  |
   |                          Inserir domínio \ nomedeusuário                          |                                                                                    Digite seu conta Microsoft.                                                                                     |
   |                             Inserir senha                              |                      Digite sua senha. Os caracteres serão mostrados como "\*" na janela. Sua senha é salva com segurança no Gerenciador de credenciais da Microsoft para reutilização posterior.                       |
   |                Especificar um número de organização (1-n) [1]                 |                      Na lista de organizações mostrada para a qual você pertence, digite o número correspondente. O padrão é 1, indicando a primeira organização na lista.                       |


6. O exemplo executará as operações descritas em [o que esse exemplo faz](#what-this-sample-does) e pode solicitar opções adicionais.  

7. Quando o exemplo for concluído, pressione ENTER para fechar a janela do console.  

