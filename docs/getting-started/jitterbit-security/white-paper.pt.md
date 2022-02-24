[//]: # (Whitepaper da Segurança e Arquitetura Jitterbit)
[//]: # (This is a translation of Version 85, published on February 3, 2022.)

## Introdução

A Jitterbit entrega ferramentas e serviços de integração poderosos por
meio de uma plataforma de integração em nuvem *multi-tenant* chamada
Jitterbit Harmony.

Embora o Jitterbit Harmony possa simplificar e acelerar drasticamente a
maioria dos aspectos dos processos de integração, a introdução de um
sistema em nuvem *multi-tenant* pode fazer surgir perguntas em clientes
e usuários.

O Jitterbit Harmony cuida da segurança das informações por meio da
aplicação de um *framework* de segurança da informação (modelo híbrido)
baseado em recomendações NIST, CIS, CSA e CERT. A Jitterbit também
recebeu certificados por satisfazer às seguintes exigências:

-   <a href="https://www.hhs.gov/hipaa/for-professionals/privacy/index.html"
    class="external-link" rel="nofollow">Health Insurance Portability and Accountability Act (HIPAA)</a>

-   <a
    href="https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/socforserviceorganizations.html"
    class="external-link" rel="nofollow">SOC1 and SOC2 type 2 compliance</a>

-   [ISO 27001:2013 with supplemental controls for 27017](https://success.jitterbit.com/display/DOC/ISO+27001+and+ISO+27017+Certification?showLanguage=pt_BR)

-   <a href="https://oag.ca.gov/privacy/ccpa" class="external-link"
    rel="nofollow">California Consumer Privacy Act (CCPA)</a>

-   <a href="https://gdpr.eu/" class="external-link"
    rel="nofollow">European Union - General Data Protection Regulation (GDPR)</a>

A Jitterbit recebeu a <a href="https://www.jitterbit.com/privacy-shield/"
class="external-link" rel="nofollow">certificação Privacy Shield</a>, cumprindo os
requisitos da <a href="https://www.privacyshield.gov/welcome" class="external-link"
rel="nofollow">EU-U.S. Privacy Shield Framework</a>.

Este documento descreve os seguintes aspectos da segurança oferecida
pela plataforma Jitterbit Harmony:

-   [Segurança Lógica e Arquitetura](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-Logical-Security-and-Architecture)

-   [Segurança Física](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-Physical-Security)

-   [Segurança Organizacional](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-Organizational-Security)

Este documento provê uma visão generalizada da segurança e aborda pontos
a considerar da perspectiva da disponibilidade e do desempenho, além da
proteção aos dados.


## <span id="JitterbitSecurityandArchitectureWhitePaper-Logical-Security-and-Architecture" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Segurança Lógica e Arquitetura

A segurança lógica é composta de todas as medidas de segurança tomadas
dentro do *software* do Jitterbit Harmony. Esta seção descreve os
seguintes pontos:

-   [Arquitetura do Sistema](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-SystemArchitecture)

-   [Componentes Principais](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-MajorComponents)

-   [Usuários, Organizações e Papéis do Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-HarmonyUsers,Organizations,andRoles)

-   [Ambientes e Controle de Acesso no Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-HarmonyEnvironmentsandAccessControl)

-   [Armazenamento de Dados do Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-HarmonyDataStorage)

-   [Topologias de Segurança do Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-HarmonySecurityTopologies)

### <span id="JitterbitSecurityandArchitectureWhitePaper-SystemArchitecture" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Arquitetura do Sistema

<span class="confluence-embedded-file-wrapper"><img
src="https://success.jitterbit.com/download/attachments/55148575/jitterbit-harmony.png?version=2&amp;modificationDate=1643907380083&amp;api=v2"
class="confluence-embedded-image"
data-image-src="https://success.jitterbit.com/download/attachments/55148575/jitterbit-harmony.png?version=2&amp;modificationDate=1643907380083&amp;api=v2"
data-unresolved-comment-count="0" data-linked-resource-id="136188109"
data-linked-resource-version="2" data-linked-resource-type="attachment"
data-linked-resource-default-alias="jitterbit-harmony.png"
data-base-url="https://success.jitterbit.com"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="55148575"
data-linked-resource-container-version="85" /></span>

A Jitterbit permite que os usuários projetem, testem, implantem,
executem e administrem seus projetos de integração Jitterbit. Usando o
Jitterbit Harmony, os clientes podem executar seus processos de
integração Jitterbit completamente na nuvem sem a necessidade de
providenciar ou lidar com qualquer *software* ou a infraestrutura
necessária para operá-lo. Aqueles que escolhem implantar a plataforma do
Jitterbit Harmony localmente (*on-premises*) ou em modo híbrido têm a
flexibilidade de executar seus processos de integração implantando
agentes privados atrás do *firewall*, obtendo assim maior controle sobre
onde seus dados fluem.

A Jitterbit reconhece que os clientes precisam que seus processos de
integração se comuniquem com aplicações que operam por trás de
*firewalls* corporativos por várias razões de segurança e de observância
de regulações.

A arquitetura do sistema do Jitterbit Harmony atende aos dois cenários:
os processos de integração podem ser executados completamente na nuvem
ou podem ser executados por trás de *firewalls* corporativos para
garantir que dados de negócios não sejam expostos à nuvem. Os usuários
também podem utilizar modelos híbridos onde algumas integrações são
executadas na nuvem, tais como desenvolvimento, enquanto outras, por
exemplo na produção, podem ser executadas atrás de *firewalls*
corporativos.

Embora o sistema simplifique a provisão, a implantação e o gerenciamento
de projetos de integração, ele também oferece aos usuários a
flexibilidade de executar suas operações de integração usando Private
Agent Groups destacáveis. Eles são subsistemas auto-contidos que podem
ser instalados atrás de *firewalls* corporativos ou em nuvens privadas
dedicadas.

A separação dos *designs* de integração, que são armazenados no
Jitterbit Harmony, do tempo de execução de integração que ocorre nos
Agent Groups permite que os clientes controlem o acesso e o fluxo de
dados de negócios sensíveis.

### <span id="JitterbitSecurityandArchitectureWhitePaper-MajorComponents" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Componentes Principais

Os vários componentes principais da arquitetura do sistema do Harmony, e
como eles abordam os requisitos de segurança, são descritos abaixo.

#### Plataforma em Nuvem do Harmony

O Jitterbit Harmony inclui bancos de dados *multi-tenant*, arquivos,
serviços e uma infraestrutura de serviço de mensagem que são usados para
implantar, gerenciar e executar projetos de integração. O Jitterbit
Harmony é executado no Amazon Web Services (AWS), que provê uma
plataforma de hospedamento segura, a melhor de sua classe, que se
sobressai no oferecimento de serviços chave à Jitterbit, tais como:

-   Segurança de *datacenter*

-   Conformidade

-   Segurança física

-   Segurança ambiental

-   Segurança de rede

-   *Hardening* de *host* (anfitrião)

-   Alta disponibilidade

-   Tolerância a erros

-   Recuperação de desastres

A Jitterbit desenvolve e melhora suas aplicações usando práticas sólidas
de ciclo de vida de desenvolvimento de *software* (na sigla em inglês,
SDLC), tais como:

-   **Identificar vulnerabilidades** de fontes externas para orientar
    mudanças e melhorias no código.

-   **Aplicar *patches* de *software* e *hardware.*** A Jitterbit é
    responsável por mudanças de código e a Amazon Web Services (AWS) é
    responsável por prover *patches* de *hardware*; nosso ambiente
    virtual permite que apliquemos mudanças sem perda de tempo.

-   **Prover autenticação segura e capacidade de registro.**

-   **Remover contas de desenvolvimento, IDs e senhas** dos ambientes de
    produção.

-   **Aderir a práticas estritas de gerenciamento de mudanças** para
    atualizações de código, bem como para *patches*.

-   **Separar ambientes de teste e desenvolvimento** daqueles de
    produção.

-   **Manter separação de deveres** entre o pessoal de desenvolvimento e
    de suporte.

-   **Garantir que Informações Pessoais Identificáveis (PII, em inglês)
    não sejam usadas** em ambientes de teste.

-   **Remover IDs de teste e desenvolvimento** antes de migrar o código
    para a produção.

-   **Fazer revisões de código regulares.**

-   **Documentar mudanças de código.**

-   **Solicitar contribuições e a aprovação de desenvolvedores sênior**
    para todas as mudanças no código.

-   **Completar testes de funcionalidade e regressão** antes de fazer
    lançamentos para produção.

-   **Manter procedimentos de *backout*** para preservar alta
    disponibilidade e integridade.

-   **Seguir práticas de código seguro** de acordo com uma política SDLC
    e abordar as necessidades de treinamento de segurança do time de
    desenvolvimento.

-   **Verificar falhas de segurança conforme designado pelo Open Web
    Application Security Project (OWASP)**, tais como falhas de
    injeção, vazamentos de *buffer*, erros de criptografia,
    manejamento de erros, etc.

-   **Avaliar vulnerabilidades em cada novo lançamento.**

-   **Conduzir testes anuais de penetração.**

Antes que um usuário possa começar a trabalhar, ele precisa se
autenticar com o Jitterbit Harmony usando suas credenciais de conta de
usuário; a força, a complexidade e os atributos da senha, tal como
autenticação de dois fatores, são customizáveis para que os clientes
possam satisfazer os requisitos de suas políticas de segurança. Quando o
*single sign-on* (SSO) estiver habilitado, estes requisitos são
administrados pelo Identity Provider (Provedor de Identidade). Todas as
comunicações com o Jitterbit Harmony ocorrem via HTTPS (maior que
TLS1.2).

Uma vez autenticado, o Jitterbit Harmony identifica todas as
organizações e ambientes aos quais este usuário tem acesso. O Jitterbit
Harmony oferece ao usuário uma lista dos *assets* de integração nos
quais ele pode trabalhar e permite que ele crie um novo projeto em
qualquer ambiente onde ele tenha privilégios suficientes. Os privilégios
são baseados em funções, além de selecionáveis e configuráveis por
ambiente por organização. Funções comuns incluem *Administrator*
(Administrador), *User* (Usuário) e *Read Only* (Somente Leitura).

##### Repositório de *Design*

O Jitterbit Harmony armazena todos os projetos implantados num
repositório de *design* *multi-tenant*. A Jitterbit faz *back-up* destes
projetos e do sistema todas as noites. Todos os *back-ups* são
criptografados com um algoritmo da Federal Information Processing
Standard (<a href="https://csrc.nist.gov/publications/detail/fips/140/2/final"
class="external-link" rel="nofollow">FIPS 140-2</a>). Este repositório de projetos é construído numa
arquitetura de banco de dados *multi-tenant*, que oferece uma partição
lógica de projetos por organizações e, na maioria dos casos, por
ambientes. Especificamente, o Harmony isola os projetos por:

-   **Arquitetura de banco de dados segura** - Inclui bancos de dados
    separados e arquitetura de *schemas* separada.

-   **Conexões ou tabelas seguras** - Usa conexões de bancos de dados
    confiáveis.

-   **Criptografia** - Obscurece dados críticos para que permaneçam
    inacessíveis a partidos não-autorizados mesmo que estes obtenham
    posse deles.

-   **Filtragem** - Usa uma camada intermediária entre um *tenant* e uma
    fonte de dados que age como uma peneira, fazendo parecer para o
    *tenant* que os dados dele são os únicos no banco de dados.

-   **Listas de controle de acesso** - Determina quem pode acessar dados
    na aplicação e o que eles podem fazer com eles.

Projetos normalmente contêm credenciais tais como nomes de usuários e
senhas usados para se conectar com vários *endpoints*. Esta informação é
criptografada dentro do repositório *multi-tenant*.

O repositório é replicado em duas regiões. Cada banco de dados também
passa por um *back-up*, podendo ser restaurado, se necessário, pela
equipe de Operações Jitterbit.

Os clientes não têm acesso direto a este repositório. Os vários
componentes da plataforma do Jitterbit Harmony, tais como o Studio e os
Cloud Agents, usam APIs para acessar o repositório. Uma vez autenticados
e com o controle de acesso validado, todas as comunicações com o
repositório são feitas através de várias camadas de APIs. Além do
controle de acesso de APIs via sessões HTTPS e no lado do servidor
(*server-side*), as APIs devem validar o acesso dos usuários através de
listas baseadas em ambiente e Controle de Acesso Baseado em Funções
(RBAC, em inglês). Estas listas garantem que os usuários só possam
visualizar, mudar ou executar ações sobre o sistema baseados nas
permissões dadas a eles por um(a) administrador(a) de organização (um(a)
usuário(a) com permissão *Admin*). Além disso, a granularidade da trilha
de auditoria é customizável por cliente.

O banco de dados de atividades rotatórias do Jitterbit Harmony armazena
informações sobre o *status* do tempo de execução bem como registros das
operações de execução de todos os usuários Jitterbit.

O banco de dados de atividades é construído sobre uma arquitetura
*multi-tenant*, e embora os dados das atividades de todos os usuários
residam no mesmo banco de dados, existe segmentação lógica por
organização e por ambiente aplicada por meio de uma camada de controle
de acesso de *software* e chaves criptográficas únicas para garantir que
os usuários possam visualizar apenas as atividades às quais eles têm
acesso.

O banco de dados de atividades é replicado pelas Regiões AWS e Zonas de
Disponibilidade para garantir alta disponibilidade e também possui um
*back-up* caso haja necessidade de restaurá-lo.

O acesso ao banco de dados de atividades é provido por um grupo de APIs.
O registro de atividades usa APIs e infraestrutura de lista de controle
de acesso (ACL, em inglês) similares às do repositório de projetos.

##### Serviços de Arquivos

O Jitterbit Harmony inclui um grupo de serviços de arquivos usados para
armazenar arquivos, tais como os *schemas*, e as customizações. Todos os
arquivos são armazenados no serviço AWS S3 e podem ser acessados somente
pelo *software* do Jitterbit Harmony e não podem ser acessados
diretamente.

##### Repositório de *Schemas*

Para dar suporte às integrações de vários *endpoints*, o Jitterbit
Harmony armazena vários tipos de *schemas*, tais como WSDL, XSD, JTR e
DTDs.

##### Repositório de Customizações

Para dar suporte às integrações de vários *endpoints* de bancos de
dados, o Jitterbit Harmony armazena vários *drivers* JDBC e ODBC. A
Jitterbit também oferece um *framework* onde os clientes podem
customizar as operações Jitterbit usando *plugins*.

*Plugins* seguros certificados estão disponíveis nos Cloud Agents. Para
os clientes que executam Private Agents, eles podem usar *plugins*
criados por clientes para conseguir ambientes eficientes do tipo
*plug-and-play*. Neste modelo de segurança privada, os clientes são
responsáveis pela aplicação de controles técnicos e administrativos
razoáveis para os *plugins* que eles criam para seu(s) agente(s)
privado(s).

##### <span id="JitterbitSecurityandArchitectureWhitePaper-harmony-design-studio" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Harmony Studio

O Jitterbit Harmony Studio expõe o maior conjunto de funcionalidades
para criar, configurar e testar projetos de integração Jitterbit. O
Jitterbit Harmony Studio está disponível em duas versões:

-   **Design Studio**: O <a href="https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR"
    rel="nofollow">Design Studio</a> é um *thick client*
    individual que pode ser instalado num aparelho Windows ou Mac. Ele
    requer acesso à internet no computador ou *laptop* em que estiver
    executando. A comunicação por meio de servidores *proxy*
    corporativos é plenamente suportada, assim como o uso de
    *whitelists* de IPs para garantir aderência a VPNs corporativas se
    ou quando isso for requerido.

-   **Cloud Studio**: O <a href="https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR"
    rel="nofollow">Cloud Studio</a> oferece uma experiência de
    *design* baseada no navegador independente de plataforma e de
    localização. Suportando as versões atuais dos navegadores Chrome,
    Firefox, Safari e Edge e usando tecnologia moderna, o Cloud Studio
    se integra de forma homogênea com a plataforma do Harmony para
    prover *design*, monitoramento e implantação de integrações
    realmente baseado na nuvem.

O Design Studio e o Cloud Studio utilizam os recursos de segurança da
Jitterbit incluindo o *single sign-on* (SSO), funções de usuário e
permissões. Ambos os produtos usam a Harmony Cloud (Nuvem do Harmony),
executando na mesma plataforma com a capacidade de gerenciar os mesmos
projetos.

#### Cloud Agent Group

Os Harmony Cloud Agents são serviços, conhecidos como *Backend as a
Service* (*back-end* como serviço, ou BaaS, na sigla em inglês),
projetados para processar e servir as necessidades dos clientes em base
*ad hoc* (pontual para cada situação). Eles fazem todo o seu trabalho de
forma dirigida por eventos, eliminando portanto a necessidade de
qualquer configuração ou administração comum a sistemas de servidores do
tipo “sempre ligados” que ficam atrás de aplicações.

A Jitterbit oferece aos seus clientes a opção de executar todas as suas
integrações na nuvem através da oferta de um Agent Group escalável,
tolerante a falhas e agregado totalmente mantido e administrado pela
Jitterbit.

Para melhorar a segurança e proteger a privacidade, os Cloud Agents da
Jitterbit são codificados de forma a garantir que os dados processados
localmente não sejam persistentes; eles são usados pelo tempo mínimo
necessário para completar o processo desejado, daí são removidos.

Quando o Jitterbit Cloud Agent Group realiza uma integração, ele vai se
conectar diretamente com a aplicação que requer a integração de dados.
Daí ele vai ler e postar dados nessas aplicações. Os clientes também
podem escolher persistir os dados dos seus negócios em arquivos
temporários em prol da velocidade e da eficiência, principalmente ao
processar *bulk data*.

Dados persistidos no Jitterbit Cloud Agent Group são armazenados em
*buckets* Amazon S3 criptografados que só são acessíveis pelo grupo dos
agentes. Cada integração armazena dados no *bucket* do seu ambiente.

Para os clientes que precisam que as aplicações residam dentro de seus
*firewalls*, ou para os usuários que realizam integrações sob estritas
observâncias regulatórias que proíbem que dados viajem fora de uma dada
barreira geográfica ou residam na nuvem, a Jitterbit recomenda o uso de
um Private Agent Group.

#### Private Agents e Private Agent Group

A Jitterbit oferece a flexibilidade de que os clientes providenciem e
gerenciem seus próprios Groups (Grupos) de Agents e de Private Agents
(antes conhecidos como Local Agents) dentro dos seus *firewalls*
corporativos ou nuvens privadas virtuais. Isto permite que os clientes
escolham onde seus ambientes de tempo de execução de integração operem e
deixa que controlem em qual rede os dados dos seus negócios transitam e
residem. Ao usar Private Agent Groups para as integrações, as empresas
podem garantir que seus dados de negócios sensíveis nunca fluam pela
plataforma do Jitterbit Harmony.

Jitterbit Harmony Agents que pertençam a Private Agent Groups se
autenticam e comunicam com o Jitterbit Harmony por meio de HTTPS. Os
Private Agent Groups implantados atrás de *firewalls* corporativos podem
ser configurados para se comunicar via um servidor *proxy* corporativo.
Não há requisitos adicionais de rede, tais como a abertura de portas
dentro de *firewalls* corporativos.

O código dos Private Agents é criado com o mesmo rigor que o código do
Harmony.

Embora os Private Agent Groups atendam requisitos rígidos de segurança,
o(a) usuário(a) ou cliente é responsável por instalar e administrar seus
Private Agents. No Cloud Agent Group, o Jitterbit Harmony providencia
alta disponibilidade e escalabilidade imediatas à altura do que é
esperado de uma tecnologia sem servidor. No entanto, nos Private Agent
Groups, a segurança e escalabilidade dos Private Agents é
responsabilidade do(a) cliente (embora a alta disponibilidade ainda seja
garantida pela plataforma do Harmony sempre que mais de um agente
estiver sendo usado dentro de um Grupo de Private Agents). A Jitterbit
oferece conselhos a respeito das melhores práticas para armazenar código
de Private Agents em [Requisitos de Sistema para Private Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents?showLanguage=pt_BR).

##### Serviços de Mensagem em Tempo de Execução

A comunicação entre os vários componentes Jitterbit, tais como o
Jitterbit Harmony Studio, os Cloud Agents e o Jitterbit Harmony, é
conseguida por meio do uso de um grupo de serviços de mensagem em tempo
de execução seguros baseados na API Java Messaging Services (JMS)
disponível na Plataforma Java. Estas APIs são internas aos componentes
Jitterbit e os clientes não têm acesso a elas.

Os Jitterbit Cloud Agents incluem ouvintes (*listeners*) do serviço de
mensagens da JMS. Todos os agentes que ouvem solicitações autenticam
fortemente e recebem sessões autorizadas na rede de mensagens do
Jitterbit Harmony. Eles só podem ouvir solicitações para seus Grupos de
Agents específicos ou que são feitas diretamente a eles por meio do
Jitterbit Harmony. As mensagens nunca são enviadas para agentes; os
agentes sempre as recebem via HTTPS. Isto permite que os agentes
executem atrás de *firewalls* corporativos e permaneçam protegidos sem a
necessidade de portas operacionais que permitiriam tráfego proveniente
da internet.

#### Harmony Management Console

O Jitterbit Harmony Management Console (Console de Gerenciamento do
Jitterbit Harmony) se comunica com o Jitterbit Harmony por meio de um
grupo de APIs de gerenciamento bem definido. As APIs são criadas com o
mesmo rigor de segurança de código que o próprio Harmony, conforme
descrito acima na seção [Harmony Studio](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-harmony-design-studio). Todos os usuários destas
APIs devem estar autenticados com o Jitterbit Harmony e todas as
comunicações são transmitidas seguramente via HTTPS.

Todas as funções de gerenciamento ofertadas pelo Management Console são
controladas também por um modelo de camadas de controle de acesso
definido para cada ambiente. Como resultado, qualquer usuário usando o
Management Console será capaz de visualizar apenas os dados para os
quais eles têm permissão de acesso. Os controles de acesso são aplicados
a toda e qualquer função, incluindo a busca por operações, execução de
operações, visualização de registros, etc.

#### Data Loader

O Jitterbit Harmony Data Loader é um produto gratuito dentro do
Salesforce AppExchange que oferece recursos de integração úteis voltados
para clientes Salesforce. O Data Loader permite que os clientes movam
dados para dentro e para fora da Salesforce para *flat files* ou bancos
de dados. O produto Data Loader é codificado com o mesmo rigor que o
Harmony.

O Data Loader instala um Private Agent customizado na mesma máquina onde
o cliente Data Loader está instalado. Para cada ambiente, *um* Private
Agent é instalado. O Data Loader não é pensado para projetos escaláveis
e altamente disponíveis; em vez disso, ele é destinado a usuários de
*desktops* ou *laptops*.

O Data Loader tem sido posto em operação em versões de produção do
Jitterbit Harmony desde o verão (do Hemisfério Norte) de 2013. Ele foi
adotado por milhares de usuários e foi usado para testar a segurança,
escalabilidade e disponibilidade do Jitterbit Harmony.

### <span id="JitterbitSecurityandArchitectureWhitePaper-HarmonyUsers,Organizations,andRoles" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Usuários, Organizações e Funções do Harmony

Para poder acessar o Jitterbit Harmony, um usuário deve registrar sua
conta de usuário. Todo usuário do Jitterbit Harmony criado dentro do
Jitterbit Harmony tem sua própria conta pessoal, baseada na sua função,
bem como credenciais de *login* onde as ferramentas de integração e os
projetos pessoais são armazenados de forma segura.

Além disso, toda organização tem uma função chamada *Administrator*
(Administrador(a)) cuja permissão *Admin* permite o acesso a todos os
recursos pertencentes àquela organização. Os administradores podem
adicionar novas funções às organizações e convidar outros usuários do
Jitterbit Harmony a se juntar quando precisam trabalhar em equipe para
projetar, construir, testar e gerenciar seus projetos de integração.

Para mais informações sobre autenticação, veja a seção [Harmony
Studio](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-harmony-design-studio).

### <span id="JitterbitSecurityandArchitectureWhitePaper-HarmonyEnvironmentsandAccessControl" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Ambientes do Harmony e Controle de Acesso

Todo projeto implantado no Jitterbit Harmony é implantado em um
ambiente. Os ambientes representam um dado estado de um projeto de
integração. Muitos projetos existem em vários estágios dentro de
diferentes ambientes (por exemplo, uma configuração de ciclo de vida de
projeto comum poderia ter três ambientes: desenvolvimento, teste e
produção.) Um projeto pode existir em diferentes estados dentro de cada
ambiente.

Os administradores das organizações (usuários com permissão *Admin*)
gerenciam o acesso a cada ambiente usando uma estratégia de acesso
baseada nas funções. Por exemplo, usuários com função de desenvolvedor
podem ter privilégios de leitura, execução e escrita no ambiente de
desenvolvimento, mas apenas acesso de leitura no ambiente de teste e
nenhum acesso ao ambiente de produção.

Os níveis de acesso a um ambiente incluem:

-   **Visualização de Registros**: Permite que um(a) usuário(a) veja os
    registros de um ambiente particular mas não oferece visibilidade
    nem controle dos projetos nele. Isto pode ser usado para deixar
    que certos usuários apoiem mas não afetem projetos cuja
    implantação é feita em ambientes críticos, tais como produção.

-   **Instalação de Agentes**: Permite que um(a) usuário(a) instale
    agentes mas não oferece controle nem visibilidade fora desta
    função. Isto pode ser usado para permitir que administradores
    dentro e fora da empresa estabeleçam conectividade adicional sem
    nenhum impacto aos projetos ou mesmo conhecimento da plataforma.

-   **Acesso de Leitura**: Permite que um(a) usuário(a) leia um projeto
    de um dado ambiente. Isto pode ser usado para compartilhar
    *templates* de processo com vários usuários ou para permitir que
    eles vejam mas não afetem projetos.

-   **Acesso de Execução**: Provê acesso de leitura e permite que os
    usuários executem operações dentro de um dado ambiente. Isto é um
    controle de acesso comum para ambientes de teste e é muitas vezes
    dado a usuários que precisam apoiar uma integração já que eles
    terão que tanto testá-la quanto executar tarefas *ad hoc*.

-   **Acesso de Escrita**: Permite controle total de um dado ambiente.
    Usuários que pertencem a uma função com acesso de escrita podem
    ler, testar, executar e mudar projetos dentro daquele ambiente em
    particular.

### <span id="JitterbitSecurityandArchitectureWhitePaper-HarmonyDataStorage" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Armazenamento de Dados do Harmony

A seguir, são descritos os tipos de informação armazenados no Jitterbit
Harmony.

#### Dados de Usuários

Quando um(a) usuário(a) se registra e se inscreve no Jitterbit Harmony,
ele deve fornecer as seguintes informações, que são armazenadas no
repositório de projetos: primeiro nome, sobrenome, e-mail e número de
telefone. Empresa, endereço da empresa e *site* da empresa podem ser
providos mas são opcionais.

#### Dados de Projetos

Para executar e gerenciar um projeto de integração, um(a) usuário(a)
deve implantar o projeto no Jitterbit Harmony. O projeto armazena
detalhes de *design* e implementação para instruir os Agent Groups de
quais atividades eles precisam fazer. Isto inclui as seguintes:

-   **Operações de integração** que descrevem o que uma unidade de
    integração vai fazer. Por exemplo, sincronizar todas as mudanças
    nos dados dos clientes no sistema CRM com os dados dos clientes no
    sistema ERP.

-   ***Transformations* e *scripts*** que descrevem como os dados são
    transpostos do sistema fonte para o sistema alvo. Isto inclui
    quaisquer regras de validação ou manipulação de dados requeridas
    para transferir os dados com sucesso.

-   **Interfaces** que descrevem as várias estruturas dos objetos fonte
    e alvo. Estas interfaces podem ser simples estruturas de texto ou
    representações complexas de objetos XML, JSON ou EDI.

-   **Conexões e *endpoints*** que são usados como fontes ou alvos.
    Embora esses valores possam ser *hard-coded*, incluindo endereços
    e credenciais de sistema, eles também podem ser referidos por meio
    de variáveis que podem ser armazenadas em bancos de dados internos
    para clientes que implementam seus próprios cofres de credenciais.

-   **Agendas e notificações** que determinam quando grupos de operações
    precisam executar e o que fazer em caso de sucesso ou falha.

-   ***Endpoints* de APIs** que informam aos agentes ou Agent Groups
    como expor APIs para que eventos de sistema externos possam chamar
    e invocar integrações Jitterbit.

Durante o armazenamento, os dados persistidos são assegurados com:

-   Autenticação

-   Listas de controle de acesso

-   Criptografia FIPS 140-2 e chaves criptográficas únicas por cliente

Durante o trânsito, os dados persistidos são assegurados com:

-   Autenticação

-   Criptografia TLS (Transport Layer Security, ou “Segurança de Camadas
    de Transporte”)

#### Registro de Atividades de Integração

Quando um Agent Group executa uma operação de integração, ele sincroniza
seus registros com o registro de atividades rotatórias *multi-tenant* do
Jitterbit Harmony. Isto inclui as seguintes informações:

-   ***Status***: O estado de uma operação (por exemplo, pendente,
    executando, sucesso, falha).

-   **Agente**: Qual agente do Agent Group executou a operação.

-   **Horários**: Quando a execução da operação foi enviada, iniciada e
    completada.

-   **Enviada por**: Quem enviou a solicitação para executar a operação.

-   **Registros Processados**: O número de registros processados do
    sistema fonte e quantos registros foram postados no alvo.

-   **Mensagem**: Qualquer informação adicional que seja relevante para
    resolver os problemas de um resultado de falha, ou informações de
    resumo que um usuário explicitamente diz à Jitterbit para escrever
    no registro usando a função interna `WriteToOperationLog()`.

Os dados dos registros de atividades são armazenados na nuvem em um
sistema particionado diariamente rotatório. As atividades de cada dia
são capturadas na partição daquele dia e cada partição é apagada depois
de 31 dias. Dados de registros de atividades mais velhos que 31 dias são
permanentemente removidos.

#### Registros de Agentes

Cada agente pode gerar dados adicionais que podem ser acessados via
Jitterbit Harmony ou podem ser armazenados em dispositivos de
armazenamento de arquivos locais, tais como *file shares* e SFTP, e
acessados de dentro de um *firewall*. Estes são registros detalhados,
que incluem:

-   Registros dos *debugs*

-   Arquivos de registros de sucesso processados

-   Arquivos de registros de falha processados

Os Agent Groups e os agentes não sincronizam os itens listados acima com
o Jitterbit Harmony automaticamente, já que eles normalmente incluem
dados de negócios confidenciais. Por usar seus próprios dispositivos de
armazenamento, os clientes podem assegurar seus dados dentro de seus
*firewalls* ou em suas próprias infraestruturas de nuvem privadas.

Estes registros são úteis para resolução detalhada de problemas e também
para propósitos de auditoria. Por padrão, um Agent Group vai armazenar
isso de um a catorze dias. O Agent Group pode ser configurado para
limpar estes dados em outros intervalos.

#### Dados de Teste que Fluem pelo Jitterbit Harmony

Além de dados armazenados no Jitterbit Harmony, dados de negócios podem
fluir pela plataforma em nuvem durante o *design* da integração. Estes
dados de teste não-persistentes fluem quando se realizam funções tais
como:

-   **Carregar dados fonte**: Traz dados de amostra para uma árvore de
    transformação para ajudar um(a) usuário(a) a identificar elementos
    numa interface e a testar transformações.

-   **Testar transformações**: Mostra o resultado do alvo transformado
    para um dado grupo de dados que está carregado.

-   **Testar função ou *script* de transformação**: Permite que um(a)
    usuário(a) teste funções e *scripts* que podem incluir um comando
    *select* de banco de dados ou ver valores de variáveis retornados
    de uma API de serviço web.

-   **Testar chamadas de serviços web e testar operações**: Permite que
    um(a) usuário(a) execute uma integração e visualize todos os
    resultados na tela.

Os serviços de *design* Jitterbit estabelecem um limite de 100 KB em
todos os dados de teste, limitando assim este tipo de dado na nuvem a um
subgrupo muito limitado.

### <span id="JitterbitSecurityandArchitectureWhitePaper-HarmonySecurityTopologies" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Topologias de Segurança do Harmony

Qualquer projeto ou serviço de integração, incluindo APIs, pode ser
implantado com as topologias de segurança descritas abaixo. Dependendo
das necessidades ambientais específicas e/ou imediatas, você deve
aplicar a topologia que satisfaz os requisitos de dados e políticas de
governança da sua organização. Estas arquiteturas de implantação, com
suas topologias de segurança associadas, são resumidas conforme o que se
segue e é detalhado nesta seção:

-   **Nuvem**: Na nuvem do Jitterbit Harmony, onde o sistema e a escala
    são completamente gerenciados pela Jitterbit.

-   **Privado (*On-Premises*, Local)**: Um servidor *on-premises*
    (local) ou nuvem privada, onde o sistema é auto-armazenado e
    gerenciado localmente.

-   **Híbrido**: Em um modelo híbrido, onde partes específicas do
    sistema são auto-armazenadas, e o resto é gerenciado pela
    Jitterbit.

Além disso, a Jitterbit permite qualquer número de combinações e
localizações para seus componentes, além de permitir a troca de opções
de implantação *ad hoc* em diferentes situações. Esta flexibilidade
conduz aos seguintes benefícios:

-   **Melhor desempenho de processamento**: O desempenho pode ser
    melhorado através do uso de processamento de borda (*edge
    processing*), onde os agentes são localizados ao lado de onde os
    dados residem.

-   **Facilidade de gerenciamento**: Gerenciamento remoto está
    disponível até mesmo para implantações privadas/locais.

-   **Seguridade e privacidade**: Todo o processamento é feito pelos
    agentes diretamente sem exposição a terceiros além da fonte
    imediata e das conexões alvo.

#### Topologia da Segurança da Implantação de Nuvem Completa

Clientes que precisam realizar integrações onde todas as suas fontes de
dados são acessíveis por meio da nuvem podem implantar seus projetos
para os ambientes do Jitterbit Harmony e executar seus projetos no
Jitterbit Harmony Cloud Agent Group.

<span class="confluence-embedded-file-wrapper"><img
src="https://success.jitterbit.com/download/attachments/55148575/real-time-apis-full-cloud-deployment.png?version=1&amp;modificationDate=1525284779779&amp;api=v2"
class="confluence-embedded-image"
data-image-src="https://success.jitterbit.com/download/attachments/55148575/real-time-apis-full-cloud-deployment.png?version=1&amp;modificationDate=1525284779779&amp;api=v2"
data-unresolved-comment-count="0" data-linked-resource-id="77109904"
data-linked-resource-version="1" data-linked-resource-type="attachment"
data-linked-resource-default-alias="real-time-apis-full-cloud-deployment.png"
data-base-url="https://success.jitterbit.com"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="55148575"
data-linked-resource-container-version="85" /></span>

Aqui, o Cloud Agent Group, que é público, *multi-tenant* e operado pela
Jitterbit, vai acessar dados de negócios de clientes diretamente pela
internet usando HTTPS. Os Jitterbit Agents dentro deste Agent Group vão
processar os dados de negócios e postá-los para qualquer sistema alvo
requerido. Os dados vão fluir dentro da rede Jitterbit usando HTTPS.

<div
class="confluence-information-macro confluence-information-macro-note conf-macro output-block"
hasbody="true" macro-name="note">

<span
class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Todos os dados mencionados acima vão persistir no ambiente de
operação seguro do Jitterbit Harmony por um breve período de tempo.

</div>

</div>

Clientes que têm políticas que não permitem a utilização da nuvem ou que
requerem responsabilidade excessiva ou garantias de indenização precisam
se certificar de que o <a href="https://www.jitterbit.com/cloud-eula" class="external-link"
rel="nofollow">Jitterbit Master Subscription Agreement</a> (*Acordo
de Assinatura Mestre Jitterbit*) e a <a href="https://www.jitterbit.com/privacy-policy/"
class="external-link" rel="nofollow">Privacy Policy</a> (*Política de
Privacidade*) satisfaçam as suas necessidades específicas, que incluem
as suas regulações de indústria, bem como as provisões, as indenizações
e os termos de responsabilidade dos clientes.

#### Topologia da Segurança da Implantação Híbrida

Num cenário de implantação híbrida, partes específicas do sistema são
auto-armazenadas, e o restante é gerenciado pela Jitterbit. Por exemplo,
você pode preferir não expor bancos de dados e aplicações a qualquer
sistema na nuvem, incluindo a Jitterbit, caso os requisitos da sua
organização não permitam que dados residam na nuvem (fora do *firewall*)
devido a questões de privacidade e regulação.

<span class="confluence-embedded-file-wrapper"><img
src="https://success.jitterbit.com/download/attachments/55148575/real-time-apis-hybrid-deployment.png?version=1&amp;modificationDate=1525284878511&amp;api=v2"
class="confluence-embedded-image"
data-image-src="https://success.jitterbit.com/download/attachments/55148575/real-time-apis-hybrid-deployment.png?version=1&amp;modificationDate=1525284878511&amp;api=v2"
data-unresolved-comment-count="0" data-linked-resource-id="77109905"
data-linked-resource-version="1" data-linked-resource-type="attachment"
data-linked-resource-default-alias="real-time-apis-hybrid-deployment.png"
data-base-url="https://success.jitterbit.com"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="55148575"
data-linked-resource-container-version="85" /></span>

Neste caso, os Jitterbit Private Agents residem atrás do *firewall*,
enquanto o Portão de APIs fica na nuvem do Jitterbit Harmony. O Agent
requer as informações por meio da camada de mensagens e coloca o
*payload* das aplicações e das fontes de dados de volta no portão via
*payload*. Os clientes podem limitar o que fica armazenado nos registros
(*logs*) para evitar que estes dados cheguem à nuvem do Jitterbit
Harmony.

#### Topologia da Segurança da Implantação Privada

Na maioria dos cenários de integração empresarial, o Agent Group tem que
acessar aplicações tanto internas quanto da nuvem. Aqui, os usuários
fariam a implantação de seus projetos para ambientes Jitterbit,
instalariam seus próprios Private Agent Groups dentro de suas redes que
têm acesso às suas aplicações, e aí gerenciariam esses Agent Groups
oferecidos via a plataforma do Jitterbit Harmony.

<span class="confluence-embedded-file-wrapper"><img
src="https://success.jitterbit.com/download/attachments/55148575/real-time-apis-on-premise-deployment.png?version=1&amp;modificationDate=1525284918025&amp;api=v2"
class="confluence-embedded-image"
data-image-src="https://success.jitterbit.com/download/attachments/55148575/real-time-apis-on-premise-deployment.png?version=1&amp;modificationDate=1525284918025&amp;api=v2"
data-unresolved-comment-count="0" data-linked-resource-id="77109906"
data-linked-resource-version="1" data-linked-resource-type="attachment"
data-linked-resource-default-alias="real-time-apis-on-premise-deployment.png"
data-base-url="https://success.jitterbit.com"
data-linked-resource-content-type="image/png"
data-linked-resource-container-id="55148575"
data-linked-resource-container-version="85" /></span>

Esta topologia permite que os usuários alimentem e gerenciem seus Agent
Groups usando o Jitterbit Harmony, mas o Agent Group e quaisquer dados
de negócios sensíveis que sejam processados ou persistidos residem
dentro de suas redes. Nesta topologia, o Private Agent Group pode
executar em ambientes de servidores físicos ou virtuais Windows ou Linux
(veja [Requisitos de Sistema para Private Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents?showLanguage=pt_BR) para ver mais
informações).


## <span id="JitterbitSecurityandArchitectureWhitePaper-Physical-Security" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Segurança Física

O Jitterbit Harmony é armazenado na infraestrutura de nuvem da AWS. A
Jitterbit escolheu a AWS, pois esta oferece uma plataforma que atende à
escalabilidade e à disponibilidade da Jitterbit, bem como muitos de seus
requisitos de segurança.

### Conformidade de Infraestrutura

A infraestrutura de TI que a AWS oferece é projetada, gerenciada e
auditada por terceiros em alinhamento com as melhores práticas de
segurança e com uma variedade de padrões de segurança de TI. Veja a
página <a
href="https://d0.awsstatic.com/whitepapers/Security/AWS_Security_Whitepaper.pdf"
class="external-link" rel="nofollow">Amazon Web Services: Overview of Security Processes</a> (em
inglês) para uma descrição dos serviços de segurança essenciais da AWS.

Além disso, projetos de integração no Jitterbit Harmony podem ser
configurados para satisfazer várias regulações e padrões específicos da
indústria, incluindo:

-   HIPAA

-   GDPR

-   Cloud Security Alliance (CSA)

-   SOC1 tipo 2

-   SOC2 tipo 2

-   ISO 27017, 27001

### Segurança Física e Ambiental

O Jitterbit Harmony fica em *datacenters* (centrais de dados)
gerenciados pela AWS. Mais informações sobre a segurança física da AWS
podem ser encontradas na página <a href="https://aws.amazon.com/compliance/data-center/controls/"
class="external-link" rel="nofollow">AWS Datacenters - Nossos
Controles</a> (em inglês).

### **Gerenciamento de Continuidade de Negócio**

O Jitterbit Harmony utiliza a infraestrutura da AWS para fornecer níveis
muito altos de disponibilidade. A AWS projetou seus sistemas para
tolerar falhas de sistema ou de *hardware* com impacto mínimo.

### Alta Disponibilidade e Tolerância a Erros

Os *datacenters* (centrais de dados) são construídos em grupos em várias
regiões do globo. Em caso de falha, processos integrados redirecionam o
tráfego de dados de clientes para longe da área afetada para evitar que
a queda afete os seus dados. Aplicações centrais são implantadas em
configuração *N+1*, então se ocorrer uma falha em um *datacenter*, há
capacidade suficiente para permitir que o tráfego seja equilibrado entre
os locais restantes.

O Jitterbit Harmony é implantado em três nuvens independentes e
geograficamente distintas (cada uma com uma região primária e
secundária): NA East (América do Norte/Leste) e NA West (América do
Norte/Oeste); EMEA East (Europa, Oriente Médio e África/Leste) e EMEA
West (Europa, Oriente Médio e África/Oeste); APAC East
(Ásia-Pacífico/Leste) e APAC West (Ásia-Pacífico/Oeste), com três
*datacenters* (zonas de disponibilidade) em cada região.

Cada zona de disponibilidade é projetada como uma zona de falha
independente. Isto significa que as zonas de disponibilidade são
separadas fisicamente dentro de uma típica região metropolitana e são
localizadas em planícies com baixo risco de inundação; a categorização
das zonas de inundação específica varia de acordo com a região. Além de
instalações de geração de *back-up* locais e com UPS (fontes de
alimentação ininterrupta), cada uma delas é alimentada por grades
diferentes de utilidades independentes para reduzir mais ainda os pontos
de falha individual. As zonas de disponibilidade são todas conectadas
redundantemente a vários provedores de tráfego de Tier 1.

Isto provê altos níveis de resiliência para o Jitterbit Harmony, já que
ele pode tolerar a maioria dos modos de falha, incluindo desastres
naturais ou falhas de sistema sem cair.

Nos Estados Unidos, em caso de falta de energia catastrófica
generalizada, a Jitterbit também pode redirecionar todo o tráfego
destinado ao *datacenter* afetado para um *datacenter* na costa do outro
lado do país.

O acesso físico é estritamente controlado tanto no perímetro quanto nos
pontos de ingresso por pessoal de segurança profissional utilizando
monitoramento por vídeo, sistemas de detecção de intrusão e outros meios
eletrônicos. Funcionários autorizados devem passar por autenticação de
dois fatores no mínimo duas vezes para acessar os andares do
*datacenter*. Todos os visitantes e prestadores de serviço são obrigados
a apresentar identificação e são recebidos e acompanhados continuamente
por funcionários autorizados.

A AWS somente provê acesso e informações sobre o *datacenter* para
funcionários e para prestadores de serviço que tenham uma necessidade de
negócio legítima para tais privilégios. Quando um(a) funcionário(a) não
tem mais necessidade de negócio para estes privilégios, o acesso dele(a)
é imediatamente revogado, mesmo que ele(a) continue trabalhando na AWS.
Todo o acesso físico aos *datacenters* pelos funcionários da AWS é
registrado e auditado rotineiramente.

#### **Resposta a Incidentes**

As equipes de Operações e de Suporte ao Cliente da Jitterbit trabalham
para identificar quaisquer problemas que possam impactar os usuários do
Jitterbit Harmony. Eles monitoram o uso da API, os bancos de dados, os
serviços, a infraestrutura de mensagens e os Jitterbit Cloud Agent
Groups do Jitterbit Harmony. As equipes de Suporte e de Operações da
Jitterbit oferecem cobertura global para detectar quaisquer problemas
críticos e gerenciar o impacto e a resolução destes incidentes.

A infraestrutura do Jitterbit Harmony é suportada pela equipe do Amazon
Incident Management, que emprega procedimentos de diagnóstico padrão da
indústria para acelerar a resolução durante eventos que causam impacto
sobre os negócios. Operadores oferecem cobertura 24 horas por dia, todos
os dias do ano, para detectar incidentes e administrar o impacto e a
resolução.

#### **Comunicação**

A Jitterbit implementa vários métodos de comunicação interna a nível
global para coordenar todas as comunicações críticas entre as equipes de
Operações, Suporte ao Cliente, Engenharia, Controle de Qualidade e
Serviços. Estas equipes têm presença por todos os Estados Unidos, na
Ásia e na Europa. Nossos funcionários entendem seus papéis e
responsabilidades individuais e sabem quando comunicar eventos
significativos de maneira rápida.

A Jitterbit tem reuniões diárias padronizadas entre as várias equipes,
que incluem os gerentes de equipe e outros funcionários para salientar
quaisquer problemas conhecidos e garantir que não haja gargalos dentro
da organização impedindo resolução rápida.

### Segurança de Rede

O Jitterbit Harmony reside dentro da rede da AWS, que foi projetada para
oferecer o nível de segurança e resiliência exigido para que o Jitterbit
Harmony suporte altos níveis de confiança e serviço.

O Jitterbit Harmony é geograficamente disperso, com arquitetura
tolerante a falhas suportada em todos os serviços chave. O Jitterbit
Harmony se apoia na infraestrutura de rede de primeira linha da AWS, que
é cuidadosamente monitorada e gerenciada. Isto inclui:

#### <span id="JitterbitSecurityandArchitectureWhitePaper-secure-network-architecture" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Arquitetura de Rede Segura

Dispositivos de rede, incluindo *firewalls* e outros dispositivos de
fronteira, estão em uso para monitorar e controlar as comunicações na
fronteira externa da rede e também em fronteiras internas essenciais
dentro da rede. Estes dispositivos de fronteira empregam conjuntos de
regras, listas de controle de acesso (ACL) e configurações para garantir
o fluxo de informações para serviços de sistema de informação
específicos.

Especificamente, a AWS provê os seguintes serviços para a Jitterbit e
para o Harmony:

-   **Arquitetura Segura**<br>
    Os componentes da infraestrutura do Jitterbit Harmony executam em AWS
    Virtual Private Clouds (Nuvens Privadas Virtuais da AWS) separadas.
    Cada pilha é uma rede isolada. A maioria dos serviços executa numa
    subrede privada. Apenas *endpoints* TLS e um *host bastion* (para o
    gerenciamento Jitterbit) são expostos à internet. Usuários do
    *back-end* se conectam à pilha por meio do *host bastion*, que
    restringe o acesso aos componentes da pilha e registra as atividades
    para as revisões de segurança.

-   ***Firewalls***<br>
    Todos os *hosts* (anfitriões) da pilha executam *firewalls* *inbound*
    obrigatórios configurados em modo “negar tudo”. Portas HTTP, HTTPS e
    SSH somente são abertas conforme a necessidade.

-   **Proteção e Mitigação de Ataques DDoS**

    -   A abordagem baseada em Virtual Private Cluster (VPC) do
        Jitterbit Harmony significa que nenhuma infraestrutura de
        *back-end* é acessível diretamente pela internet. Portanto, os
        componentes do Harmony não podem ser feitos de alvos diretos
        de um ataque DDoS (Negação Distribuída de Serviço, sigla em
        inglês). Controles de perímetro da AWS estão ativos (e
        testados) e são projetados para prevenir e detectar ataques
        DDoS. Equipes de resposta e processos de suporte estão ativos
        para o benefício de todos os clientes AWS.

    -   Os *endpoints* do Jitterbit Harmony TLS incluem um AWS Elastic
        Load Balancer (Balanceador de Cargas Elástico da AWS), que
        suporta apenas solicitações TCP válidas, o que significa que
        ataques DDoS tais como *UDP flood* ou *SYN flood* não atingem
        a camada da aplicação Harmony.

    -   Nós reconhecemos que nenhum conjunto de controles é perfeito.
        Caso a Jitterbit venha a precisar de capacidade extra para
        lidar com um potencial ataque DDoS, nós podemos imediatamente
        escalar nossa pilha de tecnologia.

-   **Escaneamento de Portas**<br>
    As ferramentas e equipes AWS monitoram e bloqueiam escaneamentos de
    portas não-autorizados. Porque a infraestrutura da nuvem do Harmony é
    privada e todos os *hosts* (anfitriões) são protegidos por *firewalls*
    robustos, o escaneamento de portas é geralmente inefetivo.

-   **Ataques de *spoofing* ou *sniffing***<br>
    A AWS configura a sua rede e os seus *hosts* para proibir o envio de
    tráfego que tenha um IP fonte ou um endereço MAC diferente do seu
    próprio. O hipervisor da AWS é configurado para não permitir a entrega
    de qualquer tráfego para um *host* a quem ele não esteja endereçado.
    Isto significa que qualquer *host* que esteja tentando executar em
    modo promíscuo não conseguirá fazer *sniffing* de tráfego destinado a
    outros *hosts*.

-   **Ataques do tipo Man-in-the-Middle (MITM)**<br>
    Todas as APIs do Jitterbit Harmony estão disponíveis via *endpoints*
    protegidos por TLS, que oferecem autenticação de servidor.

-   **Detecção e Prevenção de Intrusões**<br>
    A AWS aplica controles de IPS e IDS para todos os ambientes
    hospedados. A Jitterbit também implantou sua própria ferramenta de IPS
    para prevenir e detectar atividades anômalas e maliciosas.

-   **Escaneamento de Vulnerabilidades de Rede e de *Host***<br>
    A AWS escaneia regularmente a rede voltada à internet e a Jitterbit
    faz o mesmo com os sistemas de rede privados do Harmony. A AWS e a
    Jitterbit são conjuntamente responsáveis pela segurança de *host*. A
    AWS e/ou a Jitterbit remediam descobertas adversas sem intervenção ou
    perda de tempo dos clientes.

-   **Teste de Penetração**<br>
    A AWS faz testes de penetração frequentes na sua infraestrutura.
    Anualmente, a Jitterbit também providencia que uma firma de serviços
    de segurança terceirizada faça um teste de penetração da
    infraestrutura do Harmony. Tanto na AWS quanto na Jitterbit, qualquer
    coisa descoberta pelo teste de penetração é corrigida imediatamente.

-   ***Hosts* Seguros do Harmony**<br>
    A AWS dá à Jitterbit *hardwares* seguros (servidores/*hosts*) e
    sistemas operacionais. A AWS usa o Center for Internet Security (CIS)
    Configuration Benchmark para os sistemas e versões operacionais.

#### *Hardening* dos *Hosts*

Para todos os sistemas operacionais:

-   Ferramentas de gerenciamento de configuração automatizadas instalam
    sistemas operacionais puros a partir de imagens “douradas”.

-   *Logins* com senha estão desabilitados para *hosts*. *Root keys* SSH
    não são permitidas.

-   Nenhuma chave SSH de usuários não-autorizados é permitida nos
    *hosts* por padrão. O acesso dos usuários da força de trabalho
    interna da Jitterbit é configurado em base individual, e somente
    quando necessário para prover apoio a desenvolvedores ou a
    clientes.

-   Portas SSH não-padrão são usadas.

-   Atualizações de segurança do *host* são automatizadas.

-   Todas as portas do *host* são abertas somente mediante *whitelist*.

#### **Proteção de Transmissão**

A única comunicação externa possível com o Jitterbit Harmony é via HTTPS
usando Transport Layer Security (TLS), um protocolo criptográfico
projetado para proteger contra escutas não-autorizadas, alteração e
falsificação de mensagens.

#### **Proteção e Monitoramento de Rede**

O Jitterbit Harmony aplica a utilização de uma grande variedade de
sistemas de monitoramento automático por parte da AWS para oferecer um
alto nível de desempenho e disponibilidade de serviço. As ferramentas de
monitoramento da AWS são projetadas para detectar atividades e condições
incomuns ou não-autorizadas em pontos de comunicação de entrada e saída.
Estas ferramentas monitoram o uso de servidor e de rede, as atividades
de escaneamento de portas, o uso de aplicações e tentativas de intrusão
não-autorizadas. As ferramentas têm a habilidade de estabelecer
patamares de medição de desempenho personalizados para atividades
incomuns.

Os sistemas dentro da AWS são extensamente instrumentalizados para
monitorar métricas operacionais chave. Alarmes automaticamente notificam
o pessoal de operações e de gerenciamento quando patamares de alerta
prévio são ultrapassados em métricas operacionais chave. Uma agenda
baseada em chamados é usada para que sempre haja pessoas disponíveis
para reagir a problemas operacionais. Isto inclui um sistema de *pager*,
de modo que os alarmes sejam comunicados de forma rápida e confiável
para o pessoal de operações.

As equipes de Operações e Suporte da Jitterbit trabalham com a
Engenharia para cuidar de quaisquer incidentes ou problemas relacionados
a *softwares* ou infraestrutura desenvolvidos pela Jitterbit. Todos os
problemas críticos são identificados e discutidos durante chamadas
diárias entre as equipes. Relatórios de Incidente são documentados
depois de qualquer problema operacional significativo, independentemente
do impacto externo, e relatórios de análise de causa raiz (RCA, sigla em
inglês) são redigidos para que a causa raiz seja capturada, e ações
corretivas e preventivas são tomadas.

A Jitterbit usa as ferramentas de monitoramento de segurança da AWS para
ajudar a identificar e resolver ataques DDoS, incluindo ataques
distribuídos, do tipo *flooding* ou de *software*/lógica. Além disso, a
Jitterbit emprega suas próprias ferramentas, monitoramento e sistema de
detecção com a habilidade de redirecionar para outra região caso
necessário.

O Jitterbit Harmony ganha os benefícios da rede AWS, que oferece
proteção significativa contra problemas de segurança de rede
tradicionais conforme descritos na seção [Arquitetura de Rede
Segura](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR#JitterbitSecurityandArchitectureWhitePaper-secure-network-architecture).

### **Princípios de *Design* Seguro**

O processo de desenvolvimento do Jitterbit Harmony segue as melhores
práticas de desenvolvimento de *software* seguro. Revisões de *design*
formais e escaneamentos de código e de vulnerabilidades garantem que o
*software* Jitterbit seja projetado e desenvolvido para evitar que
mensagens de erro transmitam informações sensíveis e que os serviços de
*software* rejeitem acessos não-autorizados e maus usos.

### Gerenciamento de Mudanças

Mudanças de rotina, de emergência e de configuração na infraestrutura
existente do Jitterbit Harmony são autorizadas, registradas, testadas,
aprovadas e documentadas de acordo com normas da indústria para sistemas
similares. Atualizações na infraestrutura do Jitterbit Harmony são
feitas para minimizar os impactos no cliente e no uso que ele faz dos
serviços. O <a href="https://trust.jitterbit.com/" class="external-link"
rel="nofollow">Jitterbit Harmony Trust Site</a> oferece um painel
voltado para o público que apresenta quaisquer quedas e períodos de
degradação de desempenho de sistema, assim como manutenções agendadas e
lançamentos de *software*.

#### *Software*

A Engenharia Jitterbit aplica uma abordagem sistemática para gerenciar
mudanças de modo que as mudanças em serviços que impactam o cliente
sejam minuciosamente revisadas, testadas, aprovadas e bem-comunicadas. O
processo de gerenciamento de mudanças é projetado para evitar
interrupções de serviço não-intencionadas e para manter a integridade do
serviço ao cliente. Mudanças implantadas nos ambientes de produção são:

-   **Revisadas**: Revisões dos aspectos técnicos de uma mudança são
    requeridas.

-   **Testadas**: Mudanças sendo aplicadas são testadas por uma equipe
    de controle de qualidade separada para garantir que elas se
    comportem da maneira como se espera e que elas não afetem
    negativamente o desempenho.

-   **Aprovadas**: Todas as mudanças devem ser autorizadas para poderem
    ser despachadas pela Engenharia, Controle de Qualidade e Suporte
    ao Cliente.

Quando possível, as mudanças são agendadas durante janelas de mudança
comuns. Mudanças emergenciais em sistemas de produção que requerem
desvios dos procedimentos de gerenciamento de mudanças padrão são
associados a um incidente e registrados e aprovados conforme apropriado.

#### **Infraestrutura**

O Jitterbit Harmony é executado dentro de um Virtual Private Cluster
(VPC) e inclui os seguintes serviços dentro de cada região:

1.  **Elastic Load Balancer (ELB)**. Este serviço se certifica de que os
    requisitos aos serviços e APIs do Jitterbit Harmony escalem e
    sejam altamente disponíveis junto com o Apache Tomcat Cluster onde
    os serviços do Jitterbit Harmony executam. O número de *nodes* por
    *cluster* (aglomerado) escala dinamicamente à medida que os
    volumes de requisições escalam para cima e para baixo.

2.  **Caching Server Cluster** para gerenciar sessões de usuário. Este
    *cluster* é projetado com redundância integrada para garantir que
    a sessão do usuário não seja afetada, e troca para outro *node*
    quando necessário.

3.  **MQ Broker Network** que gerencia as solicitações dos agentes. Isto
    garante que haja uma rede redundante altamente disponível entre o
    Jitterbit Harmony e todos os agentes.

4.  **Relational Database Server** com replicação assíncrona quase em
    tempo real por todas as regiões. Isto garante que todos os
    *designs* de projeto e dados de atividade fiquem disponíveis em
    todas as regiões para o caso de uma região inteira ficar
    indisponível.

Os serviços AWS são organizados de modo a funcionar efetivamente e
seguramente com todas as redes e plataformas da AWS. Cada serviço
oferece recursos de segurança extensos para proteger dados e aplicações
sensíveis.

### **Amazon Elastic Compute Cloud (Amazon EC2) Security**

O Jitterbit Harmony usa extensivamente a AWS Elastic Compute Cloud
(Amazon EC2), que oferece capacidade de computação redimensionável
usando instâncias de servidores nos *datacenters* da AWS.

#### **Múltiplos Níveis de Segurança**

O Jitterbit Harmony faz uso da segurança dentro da Amazon EC2 oferecida
por meio do *firewall* de instância virtual de sistema operacional.
Acesso externo por APIs só é disponível nos servidores HTTPS do
Jitterbit Harmony. Todos os outros serviços ficam protegidos atrás do
*firewall*.

#### **O Hipervisor**

A Amazon EC2 do Jitterbit Harmony atualmente utiliza uma versão
altamente customizada do hipervisor Xen, aproveitando a
para-virtualização (no caso dos convidados Linux). Visto que os
convidados para-virtualizados dependem do hipervisor para oferecer
suporte a operações que normalmente exigem acesso privilegiado, o
sistema operacional convidado não tem acesso elevado à CPU. A CPU
oferece quatro modos de privilégio separados: do 0 ao 3, chamados de
anéis. O Anel 0 é o mais privilegiado, e o 3 é o menor. O sistema
operacional anfitrião executa no Anel 0. No entanto, em vez de executar
no Anel 0 como a maioria dos sistemas operacionais, o sistema
operacional convidado executa em um Anel 1 com menos privilégios e as
aplicações executam no menos privilegiado de todos, o Anel 3. Esta
virtualização explícita dos recursos físicos leva a uma clara separação
entre convidado e hipervisor, resultando em separação de segurança
adicional entre os dois.

Cada instância do Jitterbit Harmony Virtual EC2 é controlada pela equipe
de Operações da Jitterbit. Todas as instâncias do Jitterbit Harmony
passam por *hardening* e utilizam SSHv2 baseado em certificados para
acessar a instância virtual. Todos os pares chave são gerados pela
Operações Jitterbit com o objetivo de garantir que eles são únicos, e
não compartilhados fora da Operações Jitterbit.

### **Segurança do *Load Balancing* (Balanceamento de Carga)**

O Amazon Elastic Load Balancing (ELB) é usado para gerenciar tráfego em
várias instâncias da Amazon EC2. O ELB tem todas as vantagens de um
*load balancer* (balanceador de carga) *on-premises* (local), além de
vários benefícios de segurança:

-   Assume o trabalho de criptografar e descriptografar que era das
    instâncias da Amazon EC2 e o administra centralmente no *load
    balancer*.

-   Provê um único ponto de contato, e também serve como primeira linha
    de defesa contra ataques contra a sua rede.

-   Suporta criptografia de tráfego *end-to-end* (de ponta a ponta)
    usando TLS (*Transport Layer Security*, antes chamada de SSL)
    naquelas redes que usam conexões Secure HTTP (ou seja, HTTPS).
    Quando o TLS é usado, o certificado do servidor TLS usado para
    encerrar conexões de clientes pode ser administrado centralmente
    no *load balancer* (balanceador de carga), em vez de em cada
    instância individual.

-   Suporta a criação e o gerenciamento de grupos de segurança
    associados com o seu Elastic Load Balancing, quando usados numa
    Amazon VPC, para oferecer *networking* e opções de segurança
    adicionais.

### **Armazenamento de Dados**

O Jitterbit Harmony usa o Amazon S3 para armazenamento de dados de
arquivos. Estes dados incluem *schemas* de *transformations*, *drivers*
de bancos de dados, *plugins* e, em certos casos, arquivos de registros
e temporários.

O Jitterbit Harmony usa o Amazon S3 Encryption Client para criptografar
dados antes de fazer o *upload* deles para o Amazon S3. O Amazon S3 usa
uma das cifras de bloco mais fortes disponíveis: 256-bit Advanced
Encryption Standard (AES-256). Com o Amazon S3, todo objeto protegido é
criptografado com uma chave criptográfica única. Este objeto chave então
também é criptografado com uma chave mestre que é rotacionada
regularmente. O Amazon S3 oferece segurança adicional armazenando os
dados criptografados e as chaves criptográficas em *hosts* (anfitriões)
diferentes.

### **Durabilidade e Confiabilidade dos Casos**

O Amazon S3 é projetado para oferecer 99.999999999% de durabilidade e
99.99% de disponibilidade de objetos ao longo de um ano. Os objetos são
redundantemente armazenados em vários dispositivos espalhados por várias
instalações em uma região do Amazon S3. Para ajudar a oferecer
durabilidade, as operações PUT e COPY do Amazon S3 armazenam os dados
dos clientes de forma síncrona em várias instalações antes de retornar
SUCCESS. Uma vez armazenados, o Amazon S3 ajuda a manter a durabilidade
dos objetos detectando e reparando quaisquer redundâncias perdidas. O
Amazon S3 também verifica regularmente a integridade dos dados usando
*checksums* (somas de verificação). Caso seja detectada alguma
corrupção, ela é reparada usando dados redundantes. Além disso, o Amazon
S3 calcula *checksums* (somas de verificação) em todo o tráfego de rede
para detectar corrupção de pacotes de dados ao armazenar ou recuperar
dados.


## <span id="JitterbitSecurityandArchitectureWhitePaper-Organizational-Security" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Segurança Organizacional

A Jitterbit se esforça para aplicar as melhores práticas operacionais
dos líderes globais de computação em nuvem. Isto inclui:

### **Confidencialidade**

As medidas de confidencialidade do Jitterbit Harmony funcionam para
proteger dados de clientes sensíveis de acessos não-autorizados. Além
das camadas de segurança física e lógica oferecidas pelo nosso
*software* e nossa infraestrutura física, nossas políticas internas
também ditam:

-   **Separação de Deveres**: O Acesso ao sistema de produção do
    Jitterbit Harmony está disponível somente para a equipe de
    Operações da Jitterbit. Quaisquer mudanças no ambiente de produção
    devem ser aplicadas pela equipe de Operações.

-   **Mínimo Necessário e Menor Privilégio**: Dentro da equipe de
    Operações da Jitterbit, o acesso é restrito aos vários serviços
    Jitterbit conforme a necessidade. A equipe sabe quais funcionários
    têm acesso a quais recursos de produção Jitterbit Harmony em todos
    os momentos e pode revogar tais acessos conforme a necessidade.

### **Política de Pessoal**

A política de pessoal da Jitterbit é projetada para manter um alto nível
de confiabilidade nos funcionários e para mantê-los cientes de aspectos
chave da segurança da informação e da privacidade. Os funcionários devem
cumprir com um código de conduta que enfatiza a confidencialidade, a
ética e o profissionalismo em todas as interações com os usuários,
parceiros e competidores da Jitterbit. Todos os funcionários assinam um
acordo de confidencialidade que protege os dados dos clientes da
Jitterbit. Todos os funcionários da Jitterbit recebem treinamentos e
testes de segurança frequentes.

### **Operações Jitterbit**

A equipe de Operações da Jitterbit é responsável por definir e executar
procedimentos para o gerenciamento do lançamento de aplicações,
atualizações de *hardware* e de sistemas operacionais, monitoramento da
saúde de sistemas e outras atividades requeridas para a manutenção do
Jitterbit Harmony.

As responsabilidades da equipe incluem:

-   Rever a segurança do *design* e da implementação da infraestrutura
    da nuvem.

-   Implementar procedimentos que seguem padrões de segurança, tais como
    Cloud Security Alliance (CSA) e Cloud Internet Security (CIS).

-   Definir e implementar políticas de gerenciamento de identidade e de
    acesso, e procedimentos para atribuir identidades únicas e
    rastreáveis para cada membro de equipe Jitterbit autorizado.

-   Definir classificações de confidencialidade de dados que exigem que
    funcionários que acessem as informações dos clientes do Jitterbit
    Harmony façam isso da maneira prescrita que limita a possibilidade
    de acesso não-autorizado.

-   Identificar e implementar tecnologias que mantenham seguras as
    informações dos clientes, incluindo tecnologias de criptografia
    nível FIPS 140-2 para dados em trânsito e dados parados.

-   Conduzir avaliações técnicas e não-técnicas de segurança da
    informação que são baseadas em testes de penetração, escaneamentos
    de vulnerabilidade, e auditorias contra regulações base e códigos
    de práticas padrão.

-   Monitorar as aplicações e a infraestrutura do Jitterbit Harmony em
    busca de possíveis problemas de segurança.

-   Remediar rapidamente quaisquer problemas detectados.

### **Engenharia Jitterbit**

A equipe de Engenharia da Jitterbit é responsável por projetar,
desenvolver, implementar e testar os serviços de *software* ofertados
pelo Jitterbit Harmony. A equipe de Engenharia trabalha juntamente com a
equipe de Operações para identificar preocupações de segurança,
desenvolver procedimentos de monitoramento e implementar tecnologia
protetora. As responsabilidades de segurança da equipe de Engenharia
incluem:

-   Definir e implementar práticas de *design* e de código seguras.

-   Conduzir revisões de *design* para identificar possíveis
    preocupações de segurança antes da escrita do código.

-   Conduzir revisões de código para identificar código que poderia ser
    explorado para ganhar acesso não-autorizado aos dados dos
    clientes.

-   Conduzir revisões de código para identificar código que poderia
    impactar negativamente a disponibilidade.

-   Executar testes de carga em ambientes de pré-produção para verificar
    que os requisitos de segurança foram satisfeitos.

### **Controle de Qualidade Jitterbit**

A equipe de Controle de Qualidade da Jitterbit é responsável por
conduzir testes de regressão novos e existentes em todos os *softwares*
lançados pela Engenharia para garantir que nenhum problema de segurança
ou funcional seja introduzido com mudanças no *software*. A equipe de
Controle de Qualidade realiza sua função num ambiente separado que
lembra bastante as configurações de produção. A equipe de Controle de
Qualidade da Jitterbit precisa aprovar todos os lançamentos de
*software* antes que a equipe de Operações possa implantar tal
*software* no ambiente de produção do Jitterbit Harmony.

### **Jitterbit Harmony Trust Site**

A disponibilidade e o *status* de segurança do Jitterbit Harmony são
monitorados 24 horas por dia e sete dias por semana pela equipe de
Operações Jitterbit. Os dados relacionados a tal monitoramento são
publicados no <a href="https://trust.jitterbit.com/" class="external-link"
rel="nofollow">Jitterbit Harmony Trust Site</a>, dando aos usuários e
ao público visibilidade transparente das nossas operações.

### **Gerenciamento de Identidades e de Acesso**

#### **Controle de Acesso e Menor Privilégio**

A política de gerenciamento de identidades e de acesso exige que todos
os funcionários da Jitterbit que têm acesso aos ambientes de produção do
Jitterbit Harmony recebam identidades únicas e rastreáveis na forma de
um ID de usuário. A política de gerenciamento de identidades e de acesso
reforça o princípio do menor privilégio, que restringe o pessoal ao
nível mínimo de acesso que eles precisam para poder completar suas
tarefas designadas.

#### **Revisão de Acesso Periódica**

Instâncias virtuais, *firewalls*, servidores de banco de dados e outros
*softwares* e *hardwares* de infraestrutura são protegidos por
identidades de usuários que receberam um conjunto limitado de
permissões. As concessões de permissões são frequentemente revisadas
pela equipe de Operações e revogadas quando um funcionário deixa a
empresa. A equipe de Operações impõe uma política de senhas em todos os
ambientes de produção do Jitterbit Harmony que exige senhas fortes,
expiração regular de senhas e restrições ao reuso de senhas.

### Gerenciamento de Incidentes

O objetivo da política de gerenciamento de incidentes da Jitterbit é não
apenas fechar incidentes de forma rápida e eficiente, mas também coletar
e distribuir informações sobre os incidentes para que processos sejam
continuamente melhorados e as respostas futuras sejam conduzidas por
conhecimento acumulado.

O gerenciamento de incidentes inclui diagnósticos iniciais,
classificação, priorização, escalação e conclusão. Todos os incidentes
que não afetam os usuários do Jitterbit Harmony são registrados no
sistema de rastreio de problemas de engenharia. Quaisquer problemas que
afetem os usuários são registrados no sistema de Suporte ao Cliente para
que quaisquer efeitos sobre os SLAs sejam rastreados.

### **Gerenciamento de *Patches* e Alta Disponibilidade**

A Jitterbit está sempre melhorando seus produtos à medida que novas
ameaças à segurança vão surgindo. Além disso, a infraestrutura de
*software* que nós usamos também está sendo melhorada.

Para manter os *softwares* atualizados, a equipe de Operações trabalha
com as equipes de Engenharia e de Controle de Qualidade seguindo uma
política de gerenciamento de *patches* que abrange a descoberta, a
testagem e a implantação de *patches* de segurança. A estratégia de
infraestrutura virtual da AWS e do Harmony permite que o Harmony
permaneça disponível, mesmo durante atualizações.

A equipe de Operações monitora ativamente as consultivas de segurança de
vendedores e se mantém atualizada com as notificações de lançamento de
*patches*.

### **Gerenciamento de Capacidade**

O Jitterbit Harmony atualmente suporta milhares de usuários ativos que
realizam vários processos de integração. A plataforma do Jitterbit
Harmony foi desenvolvida para escalar dinamicamente. Os serviços base
que expõem APIs às nossas ferramentas e usuários executam no Apache
Tomcat. Nossos sistemas rastreiam a taxa de uso atual e automaticamente
providenciam e interrompem instâncias da EC2 conforme necessário.
