---
title: Entender os gateways de dados locais | Microsoft Docs
description: Informações de referência, instalação e solução de problemas para os gateways de dados locais
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/15/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: af2e113278f480eb3c748cb1a2f9a81e34d32258
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64454805"
---
# <a name="understand-on-premises-data-gateways-for-microsoft-flow"></a>Entender os gateways de dados locais para o Microsoft Flow
Use o gateway de dados local com o Microsoft Flow para estabelecer conexões seguras para as fontes de dados locais, como o Microsoft SQL Server.

## <a name="installation-and-configuration"></a>Instalação e configuração
### <a name="prerequisites"></a>Pré-requisitos
Mínimos:

* [.NET Framework 4.6](https://www.microsoft.com/download/details.aspx?id=48130)
* Versão de 64 bits do Windows 7 ou Windows Server 2008 R2 (ou posterior)

Recomendados:

* CPU de 8 núcleos
* 8 GB de memória
* Versão de 64 bits do Windows Server 2012 R2 (ou posterior)

Considerações relacionadas:

* Você não pode instalar um gateway em um controlador de domínio.
* Você não deve instalar um gateway em um computador, como um laptop, que possa ser desativado, suspenso ou não conectado à Internet.
* O desempenho do gateway em uma rede sem fio pode ser pior.

## <a name="install-a-gateway"></a>Instalar um gateway
> [!IMPORTANT]
> Agora, os gateways de dados do Microsoft SharePoint suportam os tráfegos HTTP e HTTPS.
> 
> 

1. [Baixe o instalador](https://go.microsoft.com/fwlink/?LinkID=820931) e execute-o.
   
    ![Executar o instalador](./media/gateway-reference/run-installer.png)
2. Na primeira tela do assistente de instalação, selecione **Próximo** para confirmar o lembrete sobre a instalação de um gateway em um laptop.
   
    ![Tela de lembrete](./media/gateway-reference/laptop-reminder.png)
3. Selecione o local de instalação.
4. Aceite os termos de uso e a declaração de privacidade.
5. Selecione **Instalar**.
   
    ![tela da localização](./media/gateway-reference/location.png)
6. Nas caixas de diálogo **Controle de Conta de Usuário**, selecione **Sim** para continuar.
7. Na tela **Gateway de dados local**, insira o endereço de email para a conta que você usará para entrar no gateway, selecione **Entrar**e conclua o processo de conexão.
   
    ![Entrar](./media/gateway-reference/sign-in.png)

## <a name="register-new-gateway-or-take-over-existing-gateway"></a>Registrar o novo gateway ou controlar o gateway existente
1. Selecione **Registrar um novo gateway neste computador** ou **Migrar, restaurar ou controlar um gateway existente**, em seguida, selecione **Próximo**.
   
    ![Escolher novo ou existente](./media/gateway-reference/new-existing.png)
2. Para configurar um novo gateway, digite um nome na caixa **Novo nome do gateway de dados local**, digite uma chave de recuperação na caixa **Chave de recuperação**, digite a mesma chave de recuperação na caixa **Confirmar chave de recuperação**. Selecione **Configurar**e **Fechar**.
   
    ![Configurar um novo gateway](./media/gateway-reference/configure-new.png)
3. Especifique uma chave de recuperação que contenha pelo menos oito caracteres e mantenha-a em um local seguro. Você precisará dessa chave, se quiser migrar, restaurar ou assumir seu gateway.
4. Para migrar, restaurar ou controlar um gateway existente, forneça o nome do gateway e sua chave de recuperação, selecione **Configurar** e siga os prompts adicionais.
   
    ![Recuperar um gateway existente](./media/gateway-reference/recover-existing.png)

## <a name="restart-the-gateway"></a>Reiniciar o gateway
O gateway é executado como um serviço Windows e, assim como qualquer outro serviço Windows, você pode iniciá-lo e pará-lo de várias maneiras. Por exemplo, você pode abrir um prompt de comando com permissões elevadas no computador no qual o gateway está em execução e executar um destes comandos:

* Para interromper o serviço, execute este comando:

```batchfile
    net stop PBIEgwService
```

* Para iniciar o serviço, execute este comando:

```batchfile
    net start PBIEgwService
```

## <a name="configure-a-firewall-or-proxy"></a>Configurar um firewall ou proxy
Para obter informações sobre como fornecer informações de proxy para o gateway, consulte [Definir configurações de proxy](https://powerbi.microsoft.com/documentation/powerbi-gateway-proxy/).

Você pode verificar se o firewall ou proxy, pode estar bloqueando conexões, executando o comando a seguir em um prompt do PowerShell. Este comando testa a conectividade com o Barramento de Serviço do Azure. O comando testa apenas a conectividade de rede e não afeta o serviço do servidor de nuvem ou o gateway. Ele ajuda a determinar se seu computador pode acessar a Internet.

```powershell
Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350
```

Os resultados devem ser semelhantes à saída abaixo. Se **TcpTestSucceeded** não for *verdadeiro*, você poderá ser bloqueado por um firewall.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Se você quiser ser abrangente, substitua os valores **ComputerName** e **Port** pelos listados em **Configurar portas** mais adiante neste tópico.

O firewall também pode bloquear conexões que o barramento de serviço do Azure faz aos data centers do Azure. Se este for o caso, você desejará listar (desbloquear) todos os [endereços IP](https://www.microsoft.com/download/details.aspx?id=41653) de sua região para os data centers.

## <a name="configure-ports"></a>Configurar portas
O gateway cria uma conexão de saída para o barramento de serviço do Azure. Ele se comunica nas portas de saída: TCP 443 (padrão), 5671, 5672, 9350 até 9354. O gateway não exige portas de entrada.

Saiba mais sobre [soluções híbridas](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/).

| Nomes de domínio | Portas de saída | Descrição |
| --- | --- | --- |
| *.analysis.windows.net |443 |HTTPS |
| *.login.microsoftonline.com |443 |HTTPS |
| *.servicebus.windows.net |5671-5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350-9354 |Ouvintes de Retransmissão do Barramento de Serviço por TCP (requer 443 para aquisição de token de controle de acesso) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| *.msftncsi.com |443 |Usado para testar a conectividade com a Internet, caso o gateway não possa ser acessado. |

Se você precisar colocar em lista branca endereços IP em vez de domínios, poderá baixar e usar a [Lista de intervalos de IP de Datacenter do Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653). Em alguns casos, as conexões do Barramento de Serviço do Azure serão feitas com o endereço IP, em vez dos nomes de domínio totalmente qualificados.

## <a name="sign-in-account"></a>Conta de entrada
Os usuários entrarão com um conta corporativa ou de estudante. Esta é a conta da sua organização. Se você se inscreveu em uma oferta do Office 365 e não forneceu seu email de trabalho, ele poderá parecer com nancy@contoso.onmicrosoft.com. Sua conta, em um serviço de nuvem, é armazenada em um locatário no Azure Active Directory (AAD). Na maioria dos casos, o UPN de sua conta AAD será compatível com o endereço de email.

## <a name="windows-service-account"></a>Conta de serviço Windows
O gateway de dados local está configurado para usar *NT SERVICE\PBIEgwService* para as credenciais de logon de serviço Windows. Por padrão, ele tem o direito de logon como um serviço. Isso está no contexto do computador no qual você está instalando o gateway.

Esta não é a conta usada para conectar as fontes de dados locais, a conta corporativa ou de estudante com a qual você entra nos serviços de nuvem.

## <a name="tenant-level-administration"></a>Administração no nível de locatário

No momento, não há um único local onde os administradores de locatários podem gerenciar todos os gateways que outros usuários instalaram e configuraram.  Se você for um administrador de locatários, recomendamos que peça aos usuários em sua organização para adicioná-lo como um administrador de cada gateway instalado. Isso permite que você gerencie todos os gateways em sua organização por meio da página Configurações de Gateway ou pelos [comandos do PowerShell](https://docs.microsoft.com/power-bi/service-gateway-high-availability-clusters#powershell-support-for-gateway-clusters).

## <a name="frequently-asked-questions"></a>Perguntas frequentes
### <a name="general-questions"></a>Perguntas gerais
**Pergunta:** Com quais fontes de dados o gateway é compatível?
**Resposta:**

* SQL Server
* SharePoint
* Oracle
* Informix
* Filesystem
* DB2

**Pergunta:** Eu preciso de um gateway para fontes de dados na nuvem, como o SQL Azure?
**Resposta:** Não. Um gateway conecta somente a fontes de dados locais.

**Pergunta:** Preciso instalar um gateway no ambiente padrão?
**Resposta:** Sim. O Microsoft Flow tem suporte apenas para gateways instalados no ambiente padrão.

**Pergunta:** Como o serviço Windows realmente é chamado?
**Resposta:** Nos Serviços, o gateway é chamado de **Serviço de gateway do Power BI Enterprise**.

**Pergunta:** Existem conexões de entrada para o gateway provenientes da nuvem?
**Resposta:** Não. O gateway usa conexões de saída para o Barramento de Serviço do Azure.

**Pergunta:** E se eu bloquear as conexões de saída? O que é necessário abrir?
**Resposta:** Confira as [portas](gateway-reference.md#configure-ports) e os hosts que o gateway usa.

**Pergunta:** O gateway precisa ser instalado no mesmo computador que a fonte de dados?
**Resposta:** Não. O gateway será conectado à fonte de dados usando as informações de conexão fornecidas. Considere o gateway como um aplicativo cliente nesse sentido. Ele só precisa ser capaz de se conectar ao nome do servidor fornecido.

**Pergunta:** Qual é a latência para executar consultas provenientes do gateway em uma fonte de dados? Qual é a melhor arquitetura?
**Resposta:**  Para reduzir a latência de rede, instale o gateway o mais próximo possível da fonte de dados. Se você puder instalar o gateway na fonte de dados real, isso minimizará a latência apresentada. Considere também os data centers. Por exemplo, se o serviço estiver usando o data center do Oeste dos EUA o SQL Server estiver hospedado em uma VM do Azure, tenha também a VM do Azure no Oeste dos EUA. Isso minimizará a latência e evitar encargos de saída na VM do Azure.

**Pergunta:** Há algum requisito de largura de banda de rede?
**Resposta:** É recomendado que a conexão de rede tenha uma boa taxa de transferência. Cada ambiente é diferente e a quantidade de dados enviada afeta os resultados. Usar o ExpressRoute pode ajudar a assegurar um nível de taxa de transferência entre o local e os data centers do Azure.

Você pode usar o [aplicativo do Teste de Velocidade do Azure](http://azurespeedtest.azurewebsites.net/) da ferramenta de terceiros para determinar a taxa de transferência.

**Pergunta:** O serviço Windows de gateway pode ser executado com uma conta do Azure Active Directory?
**Resposta:** Não. O serviço Windows deve ter uma conta Windows válida. Por padrão, ele será executado com a SID de serviço, *NT SERVICE\PBIEgwService*.

**Pergunta:** Como os resultados são enviados para a nuvem?
**Resposta:** Os resultados são enviados usando o Barramento de Serviço do Azure. Para obter mais informações, consulte [como ele funciona](gateway-reference.md#how-the-gateway-works).

**Pergunta:** Onde minhas credenciais são armazenadas?
**Resposta:** As credenciais inseridas para uma fonte de dados são criptografadas e armazenadas no serviço de nuvem do gateway. As credenciais são descriptografadas no gateway local.

### <a name="high-availabilitydisaster-recovery"></a>Alta disponibilidade/recuperação de desastres
**Pergunta:** Há planos para habilitar cenários de alta disponibilidade com o gateway?
**Resposta:** Sim, a alta disponibilidade [agora está disponível](https://flow.microsoft.com/blog/gateway-ha-increased-apply-to-each).

**Pergunta:** Quais opções estão disponíveis para recuperação de desastre?
**Resposta:** Você pode usar a chave de recuperação para restaurar ou mover um gateway.

**Pergunta:** Qual é o benefício da chave de recuperação?
**Resposta:** Ela oferece uma maneira de migrar ou recuperar as configurações do gateway.

### <a name="troubleshooting-questions"></a>Perguntas da solução de problemas
**Pergunta:** Onde estão os logs do gateway?
**Resposta:** Confira [Ferramentas](gateway-reference.md#tools) mais adiante neste tópico.

**Pergunta:** Como saber quais consultas estão sendo enviadas à fonte de dados local?
**Resposta:** Você pode habilitar o rastreamento de consulta, que incluirá as consultas sendo enviadas. Lembre-se de alterá-lo para o valor original após a solução de problemas. Deixar o rastreamento de consulta habilitado fará com que os logs sejam maiores.

Você também pode examinar ferramentas de sua fonte de dados para consultas de rastreamento. Por exemplo, você pode usar o Extended Events ou o SQL Profiler para SQL Server e o Analysis Services.

## <a name="how-the-gateway-works"></a>Como funciona o gateway
![Como ele funciona](./media/gateway-reference/gateway-arch.png)

Quando um usuário interage com um elemento que está conectado a uma fonte de dados local:

1. O serviço de nuvem cria uma consulta, juntamente com as credenciais criptografadas para a fonte de dados e envia a consulta para a fila do gateway processar.
2. O serviço de nuvem do gateway analisa a consulta e envia a solicitação para o [Barramento de Serviço do Azure](https://azure.microsoft.com/documentation/services/service-bus/).
3. O gateway de dados local sonda o Barramento de Serviço do Azure quanto a solicitações pendentes.
4. O gateway obtém a consulta, descriptografa as credenciais e se conecta às fontes de dados com essas credenciais.
5. O gateway envia a consulta à fonte de dados para execução.
6. Os resultados são enviados da fonte de dados para o gateway e, em seguida, para o serviço de nuvem. O serviço, então, usa os resultados.

## <a name="troubleshooting"></a>Solução de problemas
### <a name="update-to-the-latest-version"></a>Atualizar para a versão mais recente
Muitos problemas podem surgir quando a versão do gateway está desatualizada. Verifique se você tem a versão mais recente.  Se você não atualizou o gateway recentemente, considere instalar a versão mais recente e ver se é possível reproduzir o problema.

#### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Erro: Falha ao adicionar usuário ao grupo.  (-2147463168 PBIEgwService Usuários de log de desempenho)
Você poderá ver este erro se estiver tentando instalar o gateway em um controlador de domínio que não tem suporte. Você precisará instalar o gateway em um computador que não seja um controlador de domínio.

## <a name="tools"></a>Ferramentas
### <a name="collecting-logs-from-the-gateway-configurator"></a>Coletar logs do configurador de gateway
Você pode coletar vários logs para o gateway. Comece sempre com os logs!

1. Logs de instalação
   
    %localappdata%\Temp\On-premises_data_gateway_*.log
2. Logs de configuração
   
    %localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log
3. Logs de serviço do gateway corporativo
   
    C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log
4. Logs de eventos

Os logs de evento do **Serviço do gateway de dados local** estão presentes no **Logs de aplicativos e serviços**.

![Logs de eventos](./media/gateway-reference/event-logs.png)

### <a name="fiddler-trace"></a>Rastreamento do Fiddler
O [Fiddler](http://www.telerik.com/fiddler) é uma ferramenta gratuita da Telerik que monitora o tráfego HTTP.  Você pode ver toda a extensão com o serviço Power BI do computador cliente. Isso pode mostrar erros e outras informações relacionadas.

