[//]: # (Melhores Práticas de Segurança para Administradores, Construtores de Projeto e Especialistas de Integração)
[//]: # (This is a translation of Version 10, published on November 23, 2021.)

## Introdução

Este documento é para administradores, construtores de projeto e
especialistas de integração que integram a Jitterbit com outros
produtos, tais como Salesforce, NetSuite e outros *endpoints*. Ao
trabalhar em seus projetos, construam tendo a segurança em primeiro
lugar.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** O artigo [Metodologia de Projetos de Integração](https://success.jitterbit.com/display/DOC/Integration+Project+Methodology?showLanguage=pt_BR) contém
informações úteis para gerentes de projeto de integração.

</div>

</div>

Antes de implantar um projeto, você precisa ter completado uma auditoria
recente dos procedimentos e da infraestrutura de segurança da sua
empresa. Uma auditoria de segurança é uma avaliação estruturada e
validada da segurança do sistema de informação da sua empresa. A
auditoria de segurança mede o quão bem a segurança da sua empresa se
adequa a um conjunto de critérios estabelecidos e padrão na indústria, o
que inclui políticas, procedimentos e requisitos.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

Informações sobre auditoria e conformidade de segurança:

-   <a href="https://www.praxiom.com/iso-19011.htm" class="external-link"
    rel="nofollow">ISO 19011 Auditing Definitions Translated into Plain English</a>
    (Definições de Auditoria da ISO 19011 Traduzidas para Inglês
    Simples)

-   <a
    href="https://www.hhs.gov/hipaa/for-professionals/security/guidance/cybersecurity/index.html"
    class="external-link" rel="nofollow">Cyber Security Guidance from HHS.gov</a> (Guia de
    Ciber-Segurança do HHS.gov)

-   <a
    href="https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/aicpacybersecurityinitiative.html"
    class="external-link" rel="nofollow">SOC for Cybersecurity from AICPA.gov</a> (Sistemas de Controle e
    Organização para a Cibersegurança do AICPA.gov)

A lista acima não está completa. Outros recursos podem estar
disponíveis por meio do(a) especialista de segurança e conformidade da
sua organização.

</div>

</div>

Caso você opere sob requisitos regulatórios, como por exemplo os da FAA
ou FDA nos Estados Unidos, tenha certeza de que a sua estrutura de
segurança está em conformidade com eles.

### <span id="SecurityBestPracticesforAdministrators,ProjectBuilders,andIntegrationSpecialists-SecurityDataProtectionRegs" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Regulações de Segurança e Proteção de Dados

Existem regulações governamentais importantes às quais você pode estar
sujeito(a), dependendo de onde você opera o seu negócio ou onde os seus
clientes moram e trabalham. Estas regulações tratam da privacidade dos
dados, pela qual você, junto com a Jitterbit, é responsável.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

As seguintes regulamentações exigem que a Jitterbit, seus parceiros de
tecnologia e você implementem e mantenham todas as proteções
administrativas, físicas e técnicas apropriadas ou razoáveis. Estas leis
e regulações definem direitos de privacidade específicos aos quais você
deve aderir. Além disso, cada uma delas tem prazos e requisitos
específicos de relato.

</div>

</div>

#### Regulações Estaduais e Federais nos Estados Unidos

-   O <a href="https://www.hhs.gov/hipaa/for-professionals/index.html"
    class="external-link" rel="nofollow">HIPAA (Health Insurance Portability and Accountability Act)</a>
    e o <a
    href="https://www.hhs.gov/hipaa/for-professionals/special-topics/hitech-act-enforcement-interim-final-rule/index.html"
    class="external-link" rel="nofollow">HITECH (Health Insurance Technology for Clinical Health
    Act)</a> estabelecem requisitos para o uso, a divulgação e a
    proteção de informações pessoais de saúde. Estas leis aplicam-se a
    entidades cobertas tais como convênios de saúde, bem como serviços
    em nuvem e provedores de TI.

-   O <a href="https://www.oag.ca.gov/privacy/ccpa" class="external-link"
    rel="nofollow">CCPA (California Consumer Privacy Act)</a> aumenta os direitos
    do consumidor e as proteções de privacidade para os residentes do
    estado da Califórnia. Ele trata de quaisquer negócios que coletam
    dados pessoais de clientes que façam negócios neste estado.

#### Regulações da União Europeia e da Zona de Atividade Econômica Europeia

-   O <a href="https://gdpr.eu/" class="external-link" rel="nofollow">GDPR
    (General Data Protection Regulation)</a>GDPR (General Data Protection Regulation)</a>, em português,
    Regulamento Geral sobre a Proteção de Dados, dá controle aos
    indivíduos na União Europeia e na Área Econômica Europeia. Ele
    exige que os negócios se certifiquem que seus processos que lidam
    com dados pessoais sejam projetados e implementados com medidas de
    segurança para proteger os dados. Estes negócios também devem
    revelar suas políticas de coleção, uso e retenção de dados.


## Cloud Agents e Private Agents

Quando você executa uma integração, a Jitterbit conecta os seus dados
por meio dos agentes que você configurou. Os agentes podem ser [Cloud
Agents](https://success.jitterbit.com/display/DOC/Cloud+Agent+Groups?showLanguage=pt_BR) (Agentes da Nuvem) ou [Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents?showLanguage=pt_BR) (Agentes
Privados), e os Agents (agentes) existem em Groups (Grupos). Estes
Groups são conjuntos de Agents dentro do mesmo Ambiente, o que provê
alta disponibilidade. Isto significa que se um grupo cair ou estiver
indisponível, um outro pode tomar o lugar dele e continuar o seu
trabalho. Um Cloud Agent Group é um conjunto de agentes mantidos e
gerenciados pela Jitterbit na nuvem. Os Private Agent Groups são
mantidos e gerenciados por você, usando os seus próprios servidores ou
instâncias dentro do seu *firewall* ou armazenados virtualmente em
nuvens privadas. Ao executar Private Agents, seus dados de negócio
sensíveis permanecem dentro das suas redes gerenciadas.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

**Qual tipo de agente usar?**

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

-   Use Cloud Agent Groups quando você quiser executar a sua integração
    na nuvem e precisar da escalabilidade que os Cloud Agent Groups
    oferecem.

-   Use Private Agent Groups quando quiser - ou precisar - executar
    integrações nas suas instalações.

</div>

</div>

### Cloud Agent Groups

Os Cloud Agents são mantidos e gerenciados pela Jitterbit. Os Jitterbit
Cloud Agents são *multi-tenant* e são trancados. Dados que fluem por
eles são transientes e permanecem no agente apenas o suficiente para
completar o processamento. Você não pode controlar ou configurar o
Jitterbit Cloud Agent Group ou os seus agentes da forma como você pode
fazer com um Private Agent Group.

Quando o Jitterbit Cloud Agent Group realiza uma integração, ele se
conecta diretamente com a aplicação que requer integração de dados. Daí,
ele lê e posta os dados nestas aplicações. Caso você use armazenamento
persistente como parte do seu projeto, ele permanece no agente por 24
horas. Dados que persistem no Jitterbit Cloud Agent Group ficam
armazenados em *buckets* Amazon S3 criptografados que não são
diretamente acessíveis pelos usuários. Cada integração armazena dados
nos *buckets* do seu ambiente. Para informações detalhadas sobre a
segurança de rede e as melhores práticas com o Amazon S3, consulte a
página <a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/security.html"
class="external-link" rel="nofollow">Segurança do Amazon S3</a>.

Se você tiver um requisito regulatório que impede que dados residam na
nuvem ou fora de certos limites geográficos, use um Private Agent Group.

### Private Agent Groups

Já que os Private Agent Groups são gerenciados e controlados por você,
você é o(a) responsável pela segurança. Quando você usa Private Agents,
os dados não saem dos seus servidores. Se você usa uma nuvem privada,
você escolhe onde o seu ambiente de tempo de execução de integração
opera e você controla para qual rede os seus dados irão viajar e
residir.

Os Private Agents autenticam e se comunicam com o Jitterbit Harmony via
HTTPS. Private Agents implantados atrás de *firewalls* corporativos
podem ser configurados para se comunicar via um servidor *proxy*
corporativo. Não há requisitos de rede adicionais, tais como abertura de
portas dentro de *firewalls* corporativos. A segurança é
responsabilidade sua quando você usa Private Agents.

A Jitterbit oferece conselhos e recomendações de melhores práticas para
armazenar código de Private Agents na página [Requisitos de Sistema
para Private Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents?showLanguage=pt_BR).

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Se você está usando Private Agent Groups, reveja as
informações no artigo [Regulações de Segurança e Proteção de
Dados](https://success.jitterbit.com/display/DOC/Security+Best+Practices+for+Administrators%2C+Project+Builders%2C+and+Integration+Specialists?showLanguage=pt_BR#SecurityBestPracticesforAdministrators,ProjectBuilders,andIntegrationSpecialists-SecurityDataProtectionRegs).

</div>

</div>

### Como Tornar os *Endpoints* Seguros com Private Agents

Existem muitos métodos que você pode adotar para tornar os *endpoints*
seguros, incluindo:

-   Usar uma VPN (Rede Privada Virtual, sigla em inglês) junto com
    criptografia.

-   Usar *whitelists* (listas de permissões) de redes para controlar
    quem pode acessar a sua rede. Para usar *whitelists* com os
    Private Agents, consulte o artigo [Informação sobre
    *Whitelists*](https://success.jitterbit.com/display/DOC/Whitelist+Information?showLanguage=pt_BR).

-   Tenha certeza de que todos os *drivers* e *plugins* que você usa
    estão atualizados e testados.


## Organizações e Ambientes

Usuários e grupos diferentes vão precisar de níveis de acesso diferentes
para acessar as suas [Organizações](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR) e [Ambientes](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR). Um(a)
usuário(a) não precisa do mesmo nível de acesso que um(a)
desenvolvedor(a) ou um(a) administrador(a). Por exemplo, um(a)
desenvolvedor(a) na sua organização pode precisar de permissões Execute
(Executar) e Write (Escrever) no [API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR) (Gerente de APIs)
para criar e editar perfis de segurança, criar e editar APIs e acessar
certas funcionalidades no Management Console (Console de Gerenciamento).
Um(a) usuário(a) comum não precisa dessas permissões elevadas. Pense nos
usuários e nos grupos e no que eles fazem. Limite o acesso para que os
usuários possam usar apenas o que eles precisam para desempenhar suas
tarefas.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Para mais informações sobre as diferentes funções de acesso,
tais como User (Usuário), Administrator (Administrador) e Developer
(Desenvolvedor), e como defini-los, veja [Como Gerenciar o Acesso das
Funções aos Ambientes](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR) em [Ambientes](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR).

</div>

</div>

Aplique *patches* de *hardware* e *software*. Para os Cloud Agent
Groups, a Jitterbit é responsável pelas mudanças de código. Se você
estiver usando Private Agent Groups, monitore atualizações e *patches*
do seu sistema operacional e *softwares* de aplicação, *drivers* e
*plugins* e aplique-os quando apropriado.

Prover autenticação segura usando <a href="https://oauth.net/" class="external-link"
rel="nofollow">OAuth</a> e autenticação de
múltiplos fatores, tais como 2FA (autenticação de dois fatores) é
essencial. A OAuth é discutida em [Perfis de Segurança](https://success.jitterbit.com/display/DOC/Security+Profiles?showLanguage=pt_BR) no [API
Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR). A 2FA é discutida em [Controles de Senha Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Password+Controls?showLanguage=pt_BR).

Mantenha contas de desenvolvimento e testagem separadas da produção.
Isto inclui IDs e senhas separados. Remova estes IDs e senhas de
desenvolvimento e testagem antes de migrar o código para a produção. Em
vez disso, use [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) para armazenar informações
como IDs e senhas. Como melhor prática, mantenha ambientes separados de
desenvolvimento, testagem e produção. Você também deve se certificar de
que informações pessoais identificáveis (PII, sigla em inglês) não sejam
usadas nos testes.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Caso você pertença a uma indústria regulada, como a área da
saúde, ou se você está sujeito(a) a regulações do governo dizendo
respeito a dados e seus movimentos, reveja tais requisitos como parte do
seu planejamento de segurança.

</div>

</div>


## Segurança de APIs

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Para uma discussão aprofundada sobre este tópico, veja a
página [Segurança de APIs no Harmony](https://success.jitterbit.com/display/DOC/Harmony+API+Security?showLanguage=pt_BR).

</div>

</div>

O Harmony API Manager (Gerente de APIs do Harmony) suporta autenticação
<a
href="https://success.jitterbit.com/download/attachments/108167629/offsite-link-icon-4.png?version=1&amp;modificationDate=1580763471552&amp;api=v2"
data-linked-resource-id="108167623" data-linked-resource-version="1"
data-linked-resource-type="attachment"
data-linked-resource-default-alias="offsite-link-icon-4.png"
data-nice-type="Image" data-linked-resource-content-type="image/png"
data-linked-resource-container-id="108167629"
data-linked-resource-container-version="10">OAuth 2.0</a> com [Google](https://success.jitterbit.com/display/DOC/Google+OAuth+2.0+API+Security+Profile?showLanguage=pt_BR), [Okta](https://success.jitterbit.com/display/DOC/Okta+3-Legged+OAuth+2.0+API+Security+Profile?showLanguage=pt_BR) e [Salesforce](https://success.jitterbit.com/display/DOC/Salesforce+OAuth+2.0+API+Security+Profile?showLanguage=pt_BR) como
Identity Providers (Provedores de Identidade). A NetSuite agora impõe
autenticação baseada em *tokens* (TBA, sigla em inglês) para
Administrator (Administrador), Full Access (Acesso Total) e outros
papéis de alto privilégio desde seu lançamento 2018.2. Veja
[Autenticação Baseada em *Tokens* da NetStuite 2018.2](https://success.jitterbit.com/display/DOC/NetSuite+2018.2+Token-Based+Authentication?showLanguage=pt_BR) para mais
informações e instruções. As API Keys (Chaves de API) e API Secrets
(Segredos de API) podem ser usados para autenticar usuários com a API do
Harmony.


## Certificados

A Jitterbit pode autenticar com recursos externos com [certificados](https://success.jitterbit.com/display/DOC/Customizations+%3E+Client+Certificates?showLanguage=pt_BR) de
[cliente SSL](https://success.jitterbit.com/display/DOC/SSL+Client+Certificates?showLanguage=pt_BR) ao se conectar com *endpoints* [HTTP](https://success.jitterbit.com/display/CS/HTTP?showLanguage=pt_BR) ou [SOAP](https://success.jitterbit.com/display/CS/SOAP?showLanguage=pt_BR) no Cloud
Studio, e com *endpoints* HTTP ou [Web Services](https://success.jitterbit.com/display/DOC/Creating+a+Web+Service+Method?showLanguage=pt_BR) (Serviços da Web)
no Design Studio. As configurações dos Certificados de Cliente podem ser
acessadas no [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR) na página **Management
Console** (Console de Gerenciamento) \> **Customizations**
(Customizações) \> **Client Certificates** (Certificados de Cliente).

### Adicionando Certificados a um *Keystore*

Aplicações Jitterbit que são instaladas localmente incluem um *keystore*
(repositório de chaves) que contém os certificados necessários para
tornar segura a comunicação via HTTPS. Por exemplo, você adicionaria um
novo certificado ao *Java Keystore* da Jitterbit caso você usasse um
servidor *proxy* e precisasse permitir que o cliente local da Jitterbit
se comunique de forma segura por meio do servidor *proxy*. Você pode
adicionar novos certificados conforme a necessidade. Você também vai
precisar substituir ou renovar certificados se eles forem mudados. Mais
informações e instruções sobre a adição de certificados ao *keystore*
podem ser achadas nas seguintes páginas:

-   [Adicionando Certificados ao *Keystore* para o Data Loader](https://success.jitterbit.com/display/DOC/Adding+Certificates+to+Keystore+for+Data+Loader?showLanguage=pt_BR)

-   [Adicionando Certificados ao *Keystore* para o Design Studio](https://success.jitterbit.com/display/DOC/Adding+Certificates+to+Keystore+for+Design+Studio?showLanguage=pt_BR)

-   [Adicionando Certificados ao *Keystore* para Private Agents](https://success.jitterbit.com/display/DOC/Adding+Certificates+to+Keystore+for+Private+Agents?showLanguage=pt_BR)


## Segurança de Conectores

Ao migrar o seu projeto para outro ambiente, você quer evitar
compartilhar informações privadas. Comece com os seguintes recursos de
segurança de conector:

-   **Variáveis de Projeto**: Ao trabalhar com Conectores, as
    [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) podem proporcionar maior segurança. Se
    você estiver criando *scripts* ou *transformations*, use variáveis
    de projeto para as informações privadas, como *logins* ou IDs de
    usuários, senhas, chaves de acesso e outras informações que
    precisam ser mantidas seguras. Veja <a
    href="https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR#ProjectVariables-use-project-variablesUsingProjectVariablesinScriptsorTransformations"
    rel="nofollow">Usando Variáveis de Projeto
    em *Scripts* ou *Transformations*</a> para mais informações e
    procedimentos.

-   **Configuração**: Nomes de usuário e senhas não-criptografados são
    necessários durante o tempo de execução. Use *keystores* e puxe
    estas informações de um banco de dados armazenado fora do agente e
    que não seja chamado até o tempo de execução.

-   **Cofres Externos**: Cofres digitais seguros *on-line* são
    projetados para proteger a privacidade dos seus dados. Usando
    criptografia de dados, forte autenticação de usuários e
    armazenamento redundante, estes cofres permitem armazenamento em
    nuvem com segurança de dados. Os recursos específicos, os preços e
    as instruções dependem do provedor que você escolher.

-   ***Whitelists* de IPs**: Na maioria das situações você não precisa
    fazer nenhuma mudança especial de rede ou de *firewall* quando um
    Private Agent ou o Design Studio se comunicam com o Jitterbit
    Harmony. E se a sua rede estiver atrás de um *firewall*? Neste
    caso, configure a sua rede para se comunicar com o Jitterbit
    Harmony e use uma *whitelist* (lista de permissões) para permitir
    esta comunicação. A Jitterbit oferece endereços de IP integrantes
    de *whitelists* para cada região. Veja <a
    href="https://success.jitterbit.com/display/DOC/Whitelist+Information?showLanguage=pt_BR"
    style="letter-spacing: 0.0px;" rel="nofollow">Informações sobre
    *Whitelists*</a> para mais informações.


## Segurança dos Registros

Quando estiver pensando em registros e em segurança, examine os
requisitos do seu negócio. Decida que nível de mantenimento de registros
é necessário e quais riscos são aceitáveis para você baseado nos seus
requisitos de segurança. A Jitterbit gera registros para diferentes
funções, tais como [registros de operações](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR), [registros de
eventos Windows ou Linux](https://success.jitterbit.com/display/DOC/Log+File+Locations?showLanguage=pt_BR) e [registros de API](https://success.jitterbit.com/display/DOC/API+Logs?showLanguage=pt_BR). A maioria dos
clientes usa registros em nuvem na nuvem da Jitterbit. Os dados nos
registros são criptografados por questão de segurança. Você pode
desativar os registros em nuvem se quiser.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Se você desabilitar os registros em nuvem, os registros de
aplicação não são escritos.

</div>

</div>

### Cloud Agents

Quando um Cloud Agent Group executa uma operação de integração, ele cria
um registro de atividades que é armazenado na nuvem. Você pode
visualizar registros na página [Activities](https://success.jitterbit.com/display/DOC/Activities?showLanguage=pt_BR) (Atividades) do
[Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR) (Console de Gerenciamento). Estes registros e
os detalhes deles são guardados por 30 dias. A Jitterbit provê
[funções de registro e de erro](https://success.jitterbit.com/display/CS/Logging+and+Error+Functions?showLanguage=pt_BR) para ajudar você a criar e a fazer
o *debug* de *scripts*. `WriteToOperationLog()` pode ser usada para
escrever dados sensíveis em registros, mas nós desaconselhamos
fortemente que você faça isso, visto que isso pode criar um problema de
segurança.

A Jitterbit provê um Jitterpak com uma API que você pode usar para
baixar os seus registros. Este Jitterpak está disponível a partir do
Suporte Jitterbit se você <a
href="https://community.jitterbit.com/s/login/?startURL=%2Fs%2Fsupport&amp;src=sidebar"
class="external-link" rel="nofollow">enviar uma solicitação de suporte</a> e
pedir o Jitterpak com a Download Logs API. Veja a página [Como Receber
Ajuda](https://success.jitterbit.com/display/DOC/Getting+Support?showLanguage=pt_BR) para mais detalhes sobre como entrar em contato com o Suporte
Jitterbit. Fale com o Suporte Jitterbit para mais informações sobre a
agenda de retenção dos dados de registros.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Embora a Jitterbit não ofereça suporte nativo para o
compartilhamento de registros de operação usando ferramentas tais como
ELK, Splunk ou Loggly, muitas ferramentas de monitoramento de registros
têm agentes que podem ser implantados na mesma máquina que o Private
Agent. Estes agentes então coletam dados baseados nas regras definidas e
os inserem na ferramenta de monitoramento de registros.

</div>

</div>

### Private Agents

Usar um Private Agent Group mantém todas as suas informações dentro da
sua organização e nos seus próprios servidores. Desabilite o registro em
nuvem para evitar enviar registros para o Harmony. Ao final de cada
operação, você pode usar um *script* para enviar dados de registros
localmente. Registros de *debugs*, de *transformations*, de erros, de
erros de chamada de *endpoint* e outros estão disponíveis, e podem ser
definidos no arquivo `jitterbit.conf`. Veja [Editando o Arquivo de
Configuração - `jitterbit.conf`](https://success.jitterbit.com/display/DOC/Editing+the+Configuration+File+-+jitterbit.conf?showLanguage=pt_BR) para consultar as configurações e os
valores.
