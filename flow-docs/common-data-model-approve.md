---
title: Criar um loop de aprovação com o Common Data Service | Microsoft Docs
description: Crie uma entidade, um fluxo e um aplicativo que trabalhem juntos para que os revisores possam aprovar ou rejeitar arquivos adicionados ao Dropbox.
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
ms.date: 10/22/2016
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6c48d79138dfdafa94e56380343840d6aa0fcbb5
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64470749"
---
# <a name="build-an-approval-loop-by-using-microsoft-flow-and-the-microsoft-common-data-service"></a>Criar um loop de aprovação com o Microsoft Flow e o Common Data Service da Microsoft
O Common Data Service pode fornecer uma maneira de criar fluxos que tenham informações armazenadas em um banco de dados, independente de um fluxo. O melhor exemplo disso é com as aprovações. Se você armazenar o status da aprovação em uma entidade, o fluxo poderá trabalhar com ele.

Neste exemplo, você criará um processo de aprovação que começa quando um usuário adiciona um arquivo ao Dropbox. Quando o arquivo é adicionado, as informações sobre ele aparecem em um aplicativo, no qual um revisor pode aprovar ou rejeitar a alteração. Quando o revisor aprova ou rejeita a alteração, um email de notificação é enviado e os arquivos rejeitados são excluídos do Dropbox.

Seguindo as etapas nesta seção, você criará:

* uma **entidade personalizada** que conterá informações sobre cada arquivo adicionado ao Dropbox e se o status do arquivo é Aprovado, Rejeitado ou Pendente.
* um **fluxo** que adiciona informações à entidade personalizada quando um arquivo é adicionado ao Dropbox, envia uma mensagem quando o arquivo é aprovado ou rejeitado e exclui os arquivos rejeitados. Essas etapas demonstram como criar tal fluxo do zero, mas você pode criar um fluxo semelhante de um modelo.
* um **aplicativo** no qual um revisor pode aprovar ou rejeitar arquivos adicionados ao Dropbox. Você usará PowerApps para gerar esse aplicativo automaticamente, com base nos campos na entidade personalizada.

**Pré-requisitos**

* Inscreva-se no [Microsoft Flow](sign-up-sign-in.md) e [PowerApps](https://powerapps.microsoft.com/tutorials/signup-for-powerapps/).
* Crie conexões com o Dropbox e Office 365 Outlook, como descrito em [Gerenciar suas conexões](https://powerapps.microsoft.com/tutorials/add-manage-connections/).

## <a name="build-the-entity"></a>Criar a entidade
1. Entrar no [powerapps.com](https://web.powerapps.com).
2. Se a barra de navegação à esquerda não aparecer por padrão, clique ou toque no ícone com três linhas horizontais no canto superior esquerdo.
   
    ![Abrir a barra de navegação à esquerda](./media/common-data-model-approve/hamburger-icon.png)
3. Na barra de navegação à esquerda, clique ou toque em **Gerenciar** e, em seguida, clique ou toque em **Entidades**.
   
    ![Gerenciar entidades](./media/common-data-model-approve/manage-entities.png)
4. Se solicitado, clique ou toque em **Criar meu banco de dados**.
   
    ![Criar banco de dados](./media/common-data-model-approve/create-database.png)
5. No canto superior direito, clique ou toque em **nova entidade**.
   
    ![Criar entidade](./media/common-data-model-approve/new-entity.png)
   
    Se a janela do navegador não estiver maximizada, esse botão poderá aparecer em um local diferente.
6. Em **Nome da entidade**, especifique um nome que não contenha espaços e que nenhuma outra entidade no banco de dados tenha.
   
    Para seguir este exemplo exatamente, especifique **ReviewDropboxFiles**.
   
    ![Especificar o nome da entidade](./media/common-data-model-approve/entity-name.png)
7. Em **Nome de exibição**, especifique um nome amigável.
   
    ![Especificar nome de exibição](./media/common-data-model-approve/display-name.png)
8. Clique ou toque em **Próximo**.
   
    ![Botão Próximo](./media/common-data-model-approve/next-button.png)

## <a name="add-fields-to-the-entity"></a>Adicionar campos à entidade
1. No canto superior direito, clique ou toque em **Adicionar campo**.
   
    ![Adicionar campo](./media/common-data-model-approve/add-field.png)
2. Na linha em branco que aparece na parte inferior da lista de campos, defina as propriedades de um campo **Aprovador**. (À medida que você define essas propriedades, pode mudar para a próxima coluna pressionando Tab.)
   
   * Na coluna **Nome de exibição**, digite **Aprovador**.
   * Na coluna **Nome** digite **ApproverEmail**.
   * Na coluna **Tipo**, clique ou toque na opção **Email**.
   * Na coluna **Necessário**, marque a caixa de seleção.
     
     ![Campo Aprovador](./media/common-data-model-approve/approver-field.png)
3. Na próxima linha, defina as propriedades de um campo de **Status**:
   
   * Na coluna **Nome de exibição**, digite **Status**.
   * Na coluna **Nome** digite **Status**.
   * Na coluna **Tipo**, clique ou toque na opção **Texto**.
   * Na coluna **Propriedades**, deixe o valor padrão.
   * Na coluna **Necessário**, marque a caixa de seleção.
     
     ![Campo Status](./media/common-data-model-approve/status-field.png)
4. Na próxima linha, defina as propriedades de um campo **FileID**:
   
   * Na coluna **Nome de exibição**, digite **Identificador de arquivo**.
   * Na coluna **Nome** digite **FileID**.
   * Na coluna **Tipo**, clique ou toque na opção **Texto**.
   * Na coluna **Propriedades**, deixe o valor padrão.
   * Na coluna **Exclusivo**, marque a caixa de seleção.
   * Na coluna **Necessário**, marque a caixa de seleção.
     
     ![Campo FileID](./media/common-data-model-approve/fileid-field.png)
5. Próximo à extremidade direita, clique ou toque no botão de reticências (...) do campo **FileID** e, em seguida, clique ou toque em **Definir como título do campo**.
   
    ![Definir título do campo](./media/common-data-model-approve/set-title-field.png)
6. Próximo ao canto inferior esquerdo, clique ou toque em **Criar**.
   
    ![Criar uma entidade](./media/common-data-model-approve/create-button.png)
7. (opcional) Quando a lista de entidades reaparece, maximize a janela do navegador, se ainda não estiver maximizada e clique ou toque no cabeçalho da coluna **Tipo**. A lista é classificada com as entidades personalizadas, como a que você acabou de criar, exibida na parte superior.

## <a name="sign-in-and-create-a-flow"></a>Entrar e criar um fluxo
1. Abra o [portal do Microsoft Flow](https://flow.microsoft.com).
2. Maximize a janela do navegador, se ainda não estiver maximizada e clique ou toque em **Entrar** próximo ao canto superior direito.
   
    ![Botão de entrada para o Microsoft Flow](./media/common-data-model-approve/signin-flow.png)
3. No menu superior direito, selecione o ambiente que você criou o banco de dados em powerapps.com.
   
    **Observação**: caso não selecione o mesmo ambiente, você não verá suas entidades.
4. Próximo ao canto inferior esquerdo, clique ou toque em **Meus fluxos**.
   
    ![Botão Meus fluxos](./media/common-data-model-approve/myflows-button.png)
5. Próximo ao canto superior direito, clique ou toque em **Criar novo fluxo**.
   
    ![Botão Criar novo fluxo](./media/common-data-model-approve/create-flow.png)

## <a name="start-when-a-file-is-added"></a>Iniciar quando um arquivo for adicionado
1. Na caixa que contém **Pesquisar mais gatilhos**, digite ou cole **Dropbox** e, em seguida, clique ou toque **Dropbox – quando um arquivo é criado**.
   
    ![Criar gatilho](./media/common-data-model-approve/create-trigger.png)
2. Em **Pasta**, clique ou toque no ícone de pasta e, em seguida, navegue até a pasta no qual os arquivos serão adicionados.
   
    ![Escolher pasta](./media/common-data-model-approve/folder-icon.png)

## <a name="add-data-to-the-entity"></a>Adicionar dados à entidade
1. Clique ou toque em **Nova etapa** e, em seguida, clique ou toque **Adicionar uma ação**.
   
    ![Adicionar uma ação](./media/common-data-model-approve/add-action.png)
2. Na caixa que contém **Pesquisar mais ações**, digite ou cole **Common Data Service** e, em seguida, clique ou toque em **Common Data Service – Criar objeto**.
   
    ![Criar um objeto no Common Data Service](./media/common-data-model-approve/cdm-create-object.png)
3. Em **A entidade**, digite ou cole **Examinar** e, em seguida, clique ou toque em **Examinar aquivos do Dropbox**.
   
    ![Escolher a entidade](./media/common-data-model-approve/choose-entity-flow.png)
4. Em **Título**, clique ou toque na caixa e clique ou toque em **Nome do arquivo** na lista de tokens de parâmetro para adicionar esse token ao campo.
   
    ![Adicionar token de nome do arquivo](./media/common-data-model-approve/add-filename-token.png)
5. Em **Aprovador**, digite ou cole o endereço de email da pessoa que examinará os arquivos.
   
    **Observação**: Para fazer o teste do fluxo, especifique seu próprio endereço. Você pode alterá-lo mais tarde, quando o fluxo estiver pronto para uso real.
   
    ![Adicionar aprovador](./media/common-data-model-approve/add-approver.png)
6. Em **Status**, digite ou cole **Pendente**.
   
    ![Adicionar status padrão](./media/common-data-model-approve/add-default-status.png)
7. Em **Identificador de arquivo**, clique ou toque na caixa e clique ou toque em **Identificador de arquivo** na lista de tokens de parâmetro para adicionar esse token ao campo.
   
    ![Adicionar token de identificador de arquivo](./media/common-data-model-approve/add-file-identifier.png)

## <a name="check-whether-the-file-has-been-reviewed"></a>Verificar se o arquivo foi revisado
1. Na ação **Criar objeto**, clique ou toque em **Nova etapa**, clique ou toque em **Mais** e, em seguida, clique ou toque em **Adicionar um do until**.
   
    ![Adicionar do until](./media/common-data-model-approve/add-do-until.png)
2. No canto superior esquerdo da ação **Do until**, clique ou toque na caixa que contém **Escolher um valor**.
   
    ![Escolher um valor](./media/common-data-model-approve/choose-value.png)
   
    **Observação**: Se a janela do navegador não estiver maximizada, clique ou toque na caixa superior que contém **escolher um valor**.
3. Em **Saídas de Criar objeto**, clique ou toque em **Status** para adicionar esse token de parâmetro ao campo.
   
    ![Adicionar token de status](./media/common-data-model-approve/add-status.png)
4. Abra a lista próxima ao centro da ação **Do until** e clique ou toque em **não é igual a**.
   
    ![Especificar não é igual a](./media/common-data-model-approve/is-not-equal.png)
5. No canto superior esquerdo da ação **Do until**, digite ou cole **Pendente** na caixa que contém **Escolher um valor**.
   
    ![Especificar status a inspecionar](./media/common-data-model-approve/do-until-not-pending.png)
   
    **Observação**: Se a janela do navegador não estiver maximizada, clique ou toque na caixa inferior que contém **escolher um valor**.
6. Próximo à parte inferior da ação **Do until**, clique ou toque **Adicionar uma ação**.
   
    ![Adicionar ação dentro de um do until](./media/common-data-model-approve/add-action-in-dountil.png)
7. Na caixa que contém **Pesquisar mais ações**, digite **Comum** e clique ou toque em **Common Data Service – Obter objeto**.
   
    ![Obter um objeto](./media/common-data-model-approve/get-object.png)
8. Em **O namespace**, clique ou toque em seu banco de dados.
9. Em **A entidade**, digite ou cole **Examinar** e, em seguida, clique ou toque em **Examinar aquivos do Dropbox**.
   
    ![Escolher entidade](./media/common-data-model-approve/choose-entity-flow.png)
10. Em **ID de objeto**, clique ou toque na caixa e clique ou toque a **identificador de arquivo** token de parâmetro para adicioná-lo ao campo.
    
     ![Adicionar identificador de objeto](./media/common-data-model-approve/add-object-id.png)

## <a name="check-whether-the-item-has-been-approved"></a>Verifique se o item foi aprovado
1. Na ação **Do-Until**, clique ou toque em **Nova etapa** e clique ou toque em **Adicionar uma condição**.
   
    ![Adicionar condição](./media/common-data-model-approve/add-condition.png)
2. No canto superior esquerdo da condição, clique ou toque na caixa que contém **Escolher um valor**.
   
    ![Canto superior esquerdo da condição](./media/common-data-model-approve/condition-upper-left.png)
   
    **Observação**: Se a janela do navegador não estiver maximizada, clique ou toque na caixa superior que contém **escolher um valor**.
3. Em **Saídas de Obter objeto**, clique ou toque no token de parâmetro **Status** para adicioná-lo ao campo.
   
    ![Adicionar status à condição](./media/common-data-model-approve/add-status-to-condition.png)
4. No canto superior direito da condição, digite ou cole **Aprovado** na caixa que contém **Escolher um valor**.
   
    ![Verificar se o status está definido como aprovado](./media/common-data-model-approve/status-equals-approved.png)
   
    **Observação**: Se a janela do navegador não estiver maximizada, digite ou cole **aprovado** na caixa inferior que contém **escolha um valor**.

## <a name="send-notification-mail"></a>Enviar email de notificação
1. Em **Se Sim, não faça nada**, clique ou toque em **Adicionar uma ação**.
   
    ![Se sim, adicionar uma ação](./media/common-data-model-approve/if-yes-action.png)
2. Na caixa que contém **Pesquisar mais ações**, digite ou cole **enviar email** e, em seguida, clique ou toque em **Outlook do Office 365 – enviar um email**.
   
    ![Se sim, enviar email](./media/common-data-model-approve/if-yes-send-mail.png)
3. Em **Para**, digite ou cole o endereço da pessoa a quem você deseja notificar quando um item é aceito.
   
    **Observação**: Para fazer o teste do fluxo, especifique seu próprio endereço. Você pode alterá-lo quando o fluxo estiver pronto para uso real.
   
    ![Destinatário de aprovação](./media/common-data-model-approve/approval-recipient.png)
4. Em **Assunto**, clique ou toque na caixa e clique ou toque no token de parâmetro **Nome do arquivo** para adicioná-lo ao campo.
   
    ![Especificar o nome de arquivo como o assunto do email](./media/common-data-model-approve/subject-is-file-name.png)
5. No **Corpo**, digite ou cole **O item foi aprovado.**
   
    ![Corpo do email de aprovação](./media/common-data-model-approve/approval-body.png)
6. Em **Se não, não faça nada**, repita as etapas 1 a 5 neste procedimento, mas especifique o corpo da mensagem de email como **O item foi rejeitado.**
   
    ![Corpo do email de rejeição](./media/common-data-model-approve/rejection-body.png)

## <a name="delete-rejected-files"></a>Excluir arquivos rejeitados
1. Nos campos do email de rejeição, clique ou toque em **Adicionar uma ação**.
   
    ![Adicionar ação de exclusão](./media/common-data-model-approve/add-delete-action.png)
2. Na caixa que contém **Pesquisar mais ações**, digite ou cole **Dropbox** e, em seguida, clique ou toque em **Dropbox – Excluir arquivo**.
   
    ![Excluir arquivo do Dropbox](./media/common-data-model-approve/dropbox-delete-file.png)
3. Em **Arquivo**, clique ou toque na caixa e clique ou toque no parâmetro de token **Identificador de arquivo** para adicioná-lo ao campo.
   
    ![Identificar arquivo a ser excluído](./media/common-data-model-approve/identify-file-delete.png)

## <a name="save-the-flow"></a>Salvar o fluxo
1. Na parte superior da tela, digite ou cole um nome para o fluxo que você está criando e clique ou toque em **Criar fluxo**.
   
    ![Salvar fluxo](./media/common-data-model-approve/save-flow.png)
2. Clique ou toque **Fechar** e, em seguida, clique ou toque em **Concluído**.
3. No Dropbox, adicione pelo menos dois arquivos à pasta que você especificou: um para testar a aprovação e outro para testar a rejeição.

## <a name="build-the-app"></a>Criar o aplicativo
1. Entre em [powerapps.com](https://web.powerapps.com) e clique ou toque em **Novo aplicativo** próximo à parte inferior da barra de navegação à esquerda.
   
    ![Criar um aplicativo em um navegador](./media/common-data-model-approve/new-app-button.png)
2. Na caixa de diálogo que aparece, clique ou toque na opção para abrir PowerApps Studio para Windows ou PowerApps Studio para a Web.
3. Se você abriu PowerApps Studio para Windows, clique ou toque em **Novo** na barra de navegação à esquerda.
4. Em **Criar um aplicativo com os dados**, clique ou toque em **Layout de telefone** no bloco **Common Data Service**.
   
    ![Criar aplicativo](./media/common-data-model-approve/afd-cdm.png)
5. Na caixa **Pesquisar** digite ou cole **Examinar**.
   
    ![Pesquisar uma entidade](./media/common-data-model-approve/search-entities.png)
6. Em **Escolher uma entidade**, clique ou toque em **Examinar Arquivos do Dropbox**.
   
    ![Escolher uma entidade](./media/common-data-model-approve/choose-entity.png)
7. Próximo ao canto inferior direito, clique ou toque em **Conectar**.
   
    ![Botão Conectar](./media/common-data-model-approve/connect-button.png)
8. Se for exibida a tela de abertura do tour de Introdução, faça o tour para se familiarizar com PowerApps (ou clique ou toque em **Ignorar**).
   
    ![Tour de introdução](./media/common-data-model-approve/quick-tour.png)
   
    Você sempre pode fazer o tour mais tarde clicando ou tocando no ícone de ponto de interrogação no canto superior esquerdo e, em seguida, clicando ou tocando em **Faça o tour de introdução**.
9. (opcional) Próximo à parte inferior da tela, arraste o controle deslizante para aumentar o zoom, para que o aplicativo seja mais fácil de ver.
   
    ![Controle de zoom](./media/common-data-model-approve/zoom-control.png)

## <a name="customize-the-app"></a>Personalizar o aplicativo
1. Na barra de navegação à direita, clique ou toque no layout que inclui um cabeçalho e uma descrição.
   
    ![Botão Conectar](./media/common-data-model-approve/choose-layout.png)
2. Em **BrowseScreen**, clique ou toque abaixo da barra de pesquisa para selecionar o controle de caixa de texto maior.
   
    ![Selecionar cabeçalho](./media/common-data-model-approve/select-header.png)
3. No painel à direita, abra a lista inferior clicando ou tocando na seta para baixo.
   
    ![Abrir lista suspensa](./media/common-data-model-approve/open-dropdown.png)
4. Na lista inferior, clique ou toque em **Título** para mostrar o nome de arquivo dos arquivos adicionados.
   
    ![Definir dados do cabeçalho](./media/common-data-model-approve/set-heading.png)
5. No painel à direita, abra a lista superior e clique ou toque em **Status** para mostrar o status de cada arquivo.
   
    ![Definir dados do corpo](./media/common-data-model-approve/set-body.png)

## <a name="test-the-overall-solution"></a>Testar a solução geral
1. No PowerApps, abra o modo de visualização clicando ou tocando no botão Reproduzir próximo ao canto superior esquerdo.
   
    ![Abrir o modo de visualização](./media/common-data-model-approve/open-preview.png)
2. Para o primeiro arquivo na lista, clique ou toque na seta para mostrar os detalhes sobre esse arquivo.
   
    ![Abrir a tela Detalhes](./media/common-data-model-approve/open-details.png)
3. No canto superior direito, clique ou toque no ícone de lápis para alterar os detalhes do arquivo.
   
    ![Abrir a tela Editar](./media/common-data-model-approve/edit-record.png)
4. Na caixa **Status** digite ou cole **Aprovado**.
   
    ![Aprovar um arquivo](./media/common-data-model-approve/change-status.png)
5. No canto superior direito, clique ou toque no ícone de marca de seleção para salvar as alterações e retornar para a tela de detalhes.
   
    ![Salvar alterações](./media/common-data-model-approve/save-record.png)
   
    Em alguns minutos, você receberá um email informando que o arquivo foi aprovado.
6. No canto superior direito, clique ou toque no botão Voltar para retornar à tela de pesquisa.
   
    ![Retornar à tela de navegação](./media/common-data-model-approve/back-arrow.png)
7. Para o outro arquivo na lista, clique ou toque na seta para mostrar os detalhes sobre esse arquivo.
   
    ![Abrir a tela Detalhes](./media/common-data-model-approve/open-details.png)
8. No canto superior direito, clique ou toque no ícone de lápis para alterar os detalhes do arquivo.
   
    ![Abrir a tela Editar](./media/common-data-model-approve/edit-record.png)
9. Na caixa **Status** digite ou cole **Rejeitado** (ou qualquer coisa, exceto **Aprovado**, incluindo **Aprovado** ou **Aprovado**).
   
    ![Rejeitar arquivo](./media/common-data-model-approve/reject-file.png)
10. No canto superior direito, clique ou toque no ícone de marca de seleção para salvar as alterações e retornar para a tela de detalhes.
    
     ![Salvar alterações](./media/common-data-model-approve/save-record.png)
    
     Em alguns minutos, você receberá um email informando que o arquivo foi rejeitado e será excluído do Dropbox.

