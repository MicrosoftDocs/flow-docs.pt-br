---
ms.openlocfilehash: 253acf6677bf244c1719000c332102aa58c2e805
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64463709"
---
Neste tópico, você verá como a Contoso Flooring usa o Microsoft Flow para converter automaticamente os documentos em um formato padrão, em seguida, armazena-os no SharePoint Online para a proteção na nuvem. Você criará um fluxo que detecta quando um novo arquivo foi adicionado a uma pasta OneDrive para Empresas, em seguida, converte o arquivo em PDF e armazena-o em uma pasta SharePoint Online. 

## <a name="prerequisites"></a>Pré-requisitos
Para este cenário, você precisará de uma conta no **Muhimbi**, um serviço de conversão de PDF. Se você ainda não tiver uma conta Muhimbi, poderá inscrever-se para ter uma [avaliação gratuita de 30 dias](http://www.muhimbi.com/Products/PDF-Converter-for-SharePoint/Products-PDF-Converter-for-SharePoint-Free-Trial.aspx). Siga as instruções na página para implantar o aplicativo por meio do site do SharePoint Online. 

## <a name="create-the-source-and-target-folders"></a>Criar as pastas de origem e destino
Primeiro, você precisa criar as pastas de origem e destino no OneDrive para Empresas e SharePoint Online. 

1. No OneDrive para Empresas, em **Arquivos**, crie uma pasta chamada **Documentos Concluídos**. 
   
    ![](./media/learning-create-pdf/onedrive-folder.png)
2. No SharePoint Online, em **Documentos Compartilhados**, crie uma pasta chamada **PDF – Arquivos concluídos**. 
   
    ![](./media/learning-create-pdf/sharepoint-folder.png)

## <a name="create-the-flow"></a>Criar o fluxo
1. No Microsoft Flow, selecione **Meus Fluxos**e selecione **Criar do zero**. 
   
    ![](./media/learning-create-pdf/create-blank-flow.png)
2. Selecione **Pesquisar centenas de conectores e gatilhos**.
3. Procure **OneDrive**, selecione **OneDrive para Empresas**, em seguida, selecione o gatilho **OneDrive para Empresas - Quando um arquivo é criado**. Em **Pasta**, selecione o ícone de pasta e a pasta **Documentos Concluídos** que você criou na etapa anterior. 
   
    ![](./media/learning-create-pdf/onedrive-trigger.png)
4. Selecione **Nova Etapa** e depois selecione **Adicionar uma ação**. 
   
    ![](./media/learning-create-pdf/new-action.png)
5. Procure**Muhimbi**, selecione o conector **PDF do Muhimbi** e a ação **PDF do Muhimbi – Converter documento**.
   
    ![](./media/learning-create-pdf/muhimbi-action.png)
6. Neste ponto, o Microsoft Flow poderá solicitar a autenticação do Muhimbi. Você precisará registrar o Muhimbi usando a **ID de locatário do SharePoint** para o Microsoft Flow usar o serviço Muhimbi. 
   
   1. Para localizar a ID de locatário, selecione o ícone de engrenagem **Configurações** no SharePoint Online e selecione **Configurações do site**.
   2. Em **Administração do Conjunto de Sites**, selecione **Permissões do aplicativo do conjunto de sites**. A ID de locatário é o identificador após o símbolo "**@**" em qualquer uma das listagens de aplicativo. 
      
       ![](./media/learning-create-pdf/tenant-id.png)
7. Na ação **Converter documento**, defina os seguintes valores:
   
   * **Nome do arquivo de origem**: Na lista de conteúdo dinâmico, selecione **nome do arquivo**.
   * **Conteúdo do arquivo de origem**: Na lista de conteúdo dinâmico, selecione **conteúdo do arquivo**.
   * **Formato de saída**: No menu suspenso, selecione **PDF**.
     
     ![](./media/learning-create-pdf/muhimbi-configuration.png)

Até agora, você configurou seu fluxo com as seguintes etapas: 

1. O fluxo é acionado sempre que um novo arquivo é adicionado a uma pasta OneDrive para Empresas específica 
2. O serviço Muhimbi converte o arquivo em PDF. 

Para a etapa final, você adicionará uma ação que moverá o documento PDF para uma pasta SharePoint Online na qual a equipe pode acessá-la.  

1. Selecione **Nova Etapa** e depois selecione **Adicionar uma ação**.  Procure **SharePoint**e selecione a ação **SharePoint – Criar arquivo**. 
   
    ![](./media/learning-create-pdf/sharepoint-create-file.png)
2. Na ação **Criar arquivo**, defina os seguintes valores:
   
   * **Endereço do site**: A URL do seu site do SharePoint.  
   * **Caminho da pasta**: Selecione o ícone de pasta e navegue até a **PDF - arquivos concluídos** pasta.
   * **Nome do arquivo**: Na lista de conteúdo dinâmica para **converter documento**, selecione **nome de arquivo Base**, em seguida, adicione "**. PDF**" para que ele será salvo no SharePoint com a extensão de arquivo. 
   * **Conteúdo do arquivo**: Na lista de conteúdo dinâmica para **converter documento**, selecione **conteúdo do arquivo processado**.
3. Selecione **Criar fluxo** na parte superior da página para salvar seu trabalho.
   
    ![](./media/learning-create-pdf/sharepoint-configure-file.png)

## <a name="test-the-flow"></a>Testar o fluxo
1. Para testar o fluxo, adicione um novo arquivo à pasta **Documentos Concluídos** no OneDrive para Empresas. 
2. No fluxo, selecione **Meus fluxos**, em seguida, selecione o novo fluxo para exibir o histórico de execuções. Por padrão, o fluxo é configurado para ser executado a cada cinco minutos. 
3. Após a execução do fluxo, verifique se o arquivo foi convertido em PDF e salvo na pasta **PDF – Arquivos concluídos** do SharePoint. 
   
    ![](./media/learning-create-pdf/test-the-flow.png)

