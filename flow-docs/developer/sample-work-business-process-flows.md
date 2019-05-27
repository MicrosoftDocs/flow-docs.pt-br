---
title: 'Exemplo: Trabalhar com fluxos do processo empresarial (Guia do Desenvolvedor do Dynamics 365 Customer Engagement) | MicrosoftDocs'
description: A amostra demonstra como trabalhar programaticamente com fluxos de processo empresarial, como recuperar as instâncias de fluxo do processo empresarial para um registro de entidade, recuperando o caminho ativo para uma instância de fluxo de processo empresarial e seus estágios de processo e alterando o estágio ativo.
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
ms.openlocfilehash: 6f3543b666e471d1f7fa0fe24fc718e50d35aec8
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456028"
---
# <a name="sample-work-with-business-process-flows"></a>Exemplo: Trabalhar com fluxos dos processos empresariais

Essa amostra demonstra como trabalhar programaticamente com fluxos de processo empresarial, como recuperar as instâncias de fluxo do processo empresarial para um registro de entidade, recuperando o caminho ativo para uma instância de fluxo de processo empresarial e seus estágios de processo e alterando o estágio ativo. Para obter informações sobre esses conceitos, consulte [Trabalhar fluxos de trabalho de processo empresarial usando código](business-process-flows-code.md)  

 Este exemplo está disponível para download no [Exemplo: Trabalhar com fluxos dos processos empresariais](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Pré-requisitos  
 Antes de executar a amostra:  

1. Tenha acesso a um ambiente do Common Data Service.  

2. Tenha privilégios apropriados nas entidades de Cliente potencial, Oportunidade e Fluxo de trabalho e os registros de entidade de definição do processo empresarial usados nesta amostra.  

3. Tenha o Visual Studio 2015 ou posterior para executar a amostra.  

4. Tenha conexão com a Internet para baixar o projeto de amostra e restaurar os pacotes do NuGet usados no projeto de amostra.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>O que esta amostra faz  

1.  Cria um registro de cliente potencial de amostra. Isso cria automaticamente uma instância do fluxo de processos empresarial "Processo de vendas do cliente potencial à oportunidade" para o registro de cliente potencial.  

2.  Converte o registro de cliente potencial em um registro de oportunidade.  


4.  Recupera as instâncias de fluxo de processo empresarial associadas ao registro "Oportunidade" usando a mensagem `RetrieveProcessInstances`. O primeiro registro na coleção retornada é a instância de fluxo do processo empresarial ativa para o registro de oportunidade, que é "Processo de vendas do cliente potencial à oportunidade", nesse caso.  

5.  Recupera o caminho ativo e os estágios do processo para a instância "Processo de vendas do cliente potencial à oportunidade" usando a mensagem `RetrieveActivePath`.  

6.  Recupera o estágio ativo atual para a instância de "Processo de vendas do cliente potencial à oportunidade" e informa ao usuário se ele deve ir para o próximo estágio. Após a confirmação para mover, define o próximo estágio no caminho ativo como o estágio ativo para a instância "Processo de vendas do cliente potencial à oportunidade".  

7.  Por fim, informa ao usuário se é necessário excluir os registros criados durante a execução da amostra.  

     Aqui está a saída da amostra:  

    ![Saída da amostra](media/work-with-bpf-sample-output.png "Saída da amostra")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Executar a amostra  

1. [Baixar](https://go.microsoft.com/fwlink/p/?LinkId=846108) o projeto de amostra WorkWithBPF do Visual Studio e extraí-lo em uma pasta no seu computador.  

2. Localize o arquivo `WorkWithBPF.sln` na pasta extraída e abra-o no Visual Studio.  

3. O projeto de amostra usa pacotes do NuGet que devem ser restaurados antes de executar a amostra. Certifique-se de que a restauração automática dos pacotes do NuGet esteja habilitada no Visual Studio. Mais informações: [Habilitando e desabilitando a restauração de pacotes NuGet](https://go.microsoft.com/fwlink/?linkid=846106)  

    Como alternativa, selecione **Projeto** > **Gerenciar pacotes do NuGet**e selecione **Restaurar** para restaurar manualmente os pacotes usados na amostra.  

4. Pressione F5 ou selecione **Depurar** > **Iniciar depuração**.  

5. Se não executou anteriormente uma das amostras de antes, você precisará inserir informações para executar o código, caso contrário, digite o número de uma das instâncias que você configurou anteriormente.  


   |                                 Prompt                                  |                                                                                             Descrição                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Insira um nome do servidor do Dynamics 365 e a porta [crm.dynamics.com]       | Digite o nome do seu servidor do Dynamics 365. O padrão é o Dynamics 365 (online) (crm.dynamics.com) na América do Norte.<br /><br /> Exemplo: <br />crm5.dynamics.com |
   | Essa organização é provisionada nos serviços online da Microsoft? (s/n) [n] |                                                 Digite **s** se for uma organização provisionada nos serviços online da Microsoft. Caso contrário, digite **n**.                                                  |
   |                          Insira o domínio\nomedeusuário                          |                                                                                    Digite sua conta Microsoft.                                                                                     |
   |                             Insira a senha                              |                      Digite sua senha. Os caracteres serão exibidos como "\*" na janela. Sua senha é salva com segurança no Gerenciador de credenciais da Microsoft para reutilização posterior.                       |
   |                Especifique um número de organização (1-n) [1]                 |                      Na lista de organizações a qual você pertence, digite o número correspondente. O padrão é 1, que indica a primeira organização na lista.                       |


6. A amostra executará as operações descritas em [O que essa amostra faz?](#what-this-sample-does) e pode solicitar opções adicionais.  

7. Quando a amostra for concluída, pressione ENTER para fechar a janela do console.  

