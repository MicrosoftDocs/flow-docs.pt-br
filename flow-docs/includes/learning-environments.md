## <a name="what-is-an-environment"></a>O que é um ambiente:
Um ambiente é um espaço virtual usado para armazenar, gerenciar e compartilhar aplicativos, fluxos e dados de negócios no Common Data Service. Os ambientes são geolocalizados para que todos os aplicativos e dados armazenados no banco de dados de um ambiente também sejam geolocalizados.  

## <a name="terms-you-should-get-familiar-with"></a>Termos com os quais você deve se familiarizar

| **Termo** | **Descrição** |
| --- | --- |
| **Centro de administração** |O centro de administração é um [portal da Web](https://admin.flow.microsoft.com) para gerenciar todos os ambientes e políticas de prevenção contra perda de dados. |
| **Common Data Service** |O Common Data Service permite adicionar recursos aos seus aplicativos de modelagem e armazenamento de dados. |
| **Funções de ambiente** |As duas funções de ambiente são Administrador de Ambiente e Criador de Ambiente. |
| **Funções de usuário** |As duas funções de usuário padrão são Usuário da Organização e Proprietário do Banco de Dados. Você pode adicionar funções e associar permissões a essas funções. |

## <a name="purposes-for-an-environment"></a>Finalidades de um ambiente
Você pode usar ambientes para:  

* Aplicativos separados, dados de fluxos e de negócios baseados em funções, requisitos de segurança ou usuários diferentes.  
* Separar aplicativos, fluxos e dados de negócios com base na localização de suas equipes ou departamentos.
* Gerenciar ambientes de teste e de produção.  

## <a name="how-to-use-environments"></a>Como usar ambientes
Os ambientes podem suprir várias finalidades diferentes, dependendo das suas necessidades organizacionais. Veja alguns exemplos:  

* Você pode optar por criar todos os aplicativos em um único ambiente. 
* Você pode optar por criar um ambiente para diferentes tipos de aplicativos e fluxos. Por exemplo, você pode criar um ambiente para teste e outro ambiente para produção.  
* Você também pode optar por criar ambientes com base em sua estrutura organizacional ou mesmo com base na localização geográfica de suas equipes ou departamentos. Por exemplo, se você tiver equipes na Austrália, México e na Europa, é possível criar um ambiente para cada um desses locais e gerenciá-los de forma independente.  

**Observação**: os ambientes não ficam visíveis aos usuários para que eles não precisem se preocupar em saber em quais ambientes estão. Os ambientes são uma ferramenta para administradores categorizar, gerenciar e compartilhar aplicativos e fluxos organizacionais.  

## <a name="what-are-roles"></a>O que são funções?
Uma pessoa com acesso a um ambiente deve ser atribuída à função **Administrador de Ambiente** ou a função **Criador de Ambiente**. Os administradores de ambiente podem executar todas as tarefas administrativas em um ambiente. Um criador de ambiente pode criar recursos em um ambiente existente. Uma pessoa pode ter ambas as funções simultaneamente.  

**Observação**: todos os usuários terão acesso a um ambiente padrão quando cada usuário receber acesso ao Microsoft Flow. Os usuários podem ter acesso a vários ambientes.  

## <a name="create-an-environment"></a>Criar um ambiente
Crie ambientes do [centro de administração do Microsoft Flow](https://admin.flow.microsoft.com) com estas etapas:  

1. Dê um nome ao seu ambiente.
2. Escolha uma região onde seu ambiente será hospedado.
3. Opcionalmente, você pode decidir criar um banco de dados para seu ambiente. Se desejar, após ter criado um ambiente, crie um banco de dados.
4. Opcionalmente, escolha quem terá acesso ao banco de dados. Você pode restringir o acesso ou permitir que todos acessem o banco de dados. 

## <a name="add-users-to-an-environment"></a>Adicionar usuários a um ambiente
Depois de criar um ambiente, você pode adicionar usuários à função Administrador de Ambiente ou à função Criador de Ambiente. Isso é feito no centro de administração como acontece com as demais tarefas administrativas.  

Depois de criar o ambiente e adicionar usuários, talvez você queira criar uma política de DLP (prevenção contra perda de dados) para ajudar a gerenciar o uso dos dados corporativos. Nós abordaremos isso no próximo tópico. 

