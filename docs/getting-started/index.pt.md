[//]: # (Primeiros Passos)
[//]: # (This is a translation of Version 54, published on February 4, 2022.)

## Visão Geral

A *Jitterbit Harmony API Integration Platform* (em português,
*Plataforma de Integração de APIs do Jitterbit Harmony*), ou
simplesmente o Harmony, é a plataforma de integração de APIs moderna,
*multi-tenant* e nascida na nuvem da Jitterbit, que conecta aplicações
dos tipos SaaS (*software* como serviço), *on-premises* (locais), em
nuvem ou legado.

### Componentes do Harmony

O Harmony é movido pelas capacidades de iPaaS (plataforma de integração
como serviço, sigla em inglês) da Jitterbit e consiste dos seguintes
componentes:

-   **Harmony Agents (Cloud Agents e Private Agents)**: Os Agents do
    Harmony fazem o trabalho no tempo de execução, conectando-se a
    vários sistemas *endpoints*, transformando dados, etc. Você pode
    usar Cloud Agents, ou seja, agentes sem servidor e/ou Private
    Agents, antigamente chamados de Local Agents, com um dos seguintes
    modelos de implantação:

    -   **Em Nuvem (Sem Servidor, Nuvem Completa, *Multi-Tenant*)**: Na
        nuvem do Jitterbit Harmony, onde o sistema e a escala são
        completamente administrados pela Jitterbit.

    -   **Privado (*On-Premises*, Local)**: Em um servidor local
        (*on-premises*) ou em uma nuvem pública/privada, onde o
        sistema é auto-armazenado e/ou auto-administrado.

    -   **Híbrido**: Em modo híbrido, onde partes selecionadas do
        sistema são auto-administradas e o restante é administrado
        inteiramente pela Jitterbit.

-   **Harmony API Gateway**: Oferece segurança, limitação e validação de
    toda e qualquer API nova que os usuários publicarem via Jitterbit.

-   **Harmony Backend Services**: Inclui um motor de notificação,
    gerenciamento remoto de Private Agents, bem como vários outros
    sistemas e serviços de *backend*.

-   **Harmony Design Repository**: Uma coleção segura, criptografada e
    centralizada dos projetos de integração.

-   **Harmony Messaging Services**: Facilitam a comunicação entre vários
    componentes do Harmony, oferecendo um método confiável para
    roteamento, monitoramento e mecanismos de retentativa de
    integração.

-   **Harmony Transaction Logs**: Oferecem uma forma fácil de encontrar
    *bugs* e podem ser armazenados por um período de tempo
    configurável localmente ou na nuvem.

### Aplicações do Harmony

O [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR) é a interface baseada na Web onde você
acessa as aplicações do Harmony:

-   **Studio**: A aplicação de *design* de projetos da Jitterbit onde
    você pode projetar, testar e implantar os seus projetos de
    integração. Duas versões estão disponíveis:

    -   **[Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR)**: O Cloud Studio oferece uma experiência
        de usuário moderna e colaborativa com interface de usuário
        baseada na nuvem.

    -   **[Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR)**: O Design Studio é um *thick client*
        independente que pode ser instalado numa estação de trabalho
        Windows ou macOS.

-   **[API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR)**: A interface web para gerenciamento de APIs
    da Jitterbit onde você pode criar e publicar APIs próprias para
    desenvolvedores além de executar tarefas de gerenciamento de todo
    o ciclo de vida das APIs.

-   **[Marketplace](https://success.jitterbit.com/display/DOC/Marketplace?showLanguage=pt_BR)**: O recurso da Jitterbit para buscar e acessar
    protótipos de integração e *templates* de processo do Cloud Studio
    para ajudar você a criar novos projetos do Cloud Studio
    rapidamente.

-   **[Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR)**: O console web da Jitterbit onde você
    pode gerenciar seus projetos de integração e executar funções
    administrativas relacionadas à sua organização.

-   **[Citizen Integrator](https://success.jitterbit.com/display/DOC/Citizen+Integrator?showLanguage=pt_BR)**: A aplicação web do tipo
    clique-e-execute da Jitterbit para que usuários não-técnicos
    possam rapidamente customizar e implantar integrações do Design
    Studio usando protótipos pré-construídos do Citizen Integrator.

-   **[Data Loader](https://success.jitterbit.com/display/DOC/Data+Loader?showLanguage=pt_BR)**: A ferramenta de migração de dados gratuita
    da Jitterbit que permite que administradores da Salesforce
    automatizem de forma rápida e fácil a importação e exportação de
    dados entre *flat files*, bancos de dados e a Salesforce.

Para ver uma representação gráfica e uma descrição detalhada dos
componentes do Harmony, consulte o [*Whitepaper* da Segurança e
Arquitetura da Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper?showLanguage=pt_BR).


## Criando e Registrando uma Conta do Jitterbit Harmony

Para dar os seus primeiros passos no Jitterbit Harmony, você vai
precisar criar e registrar uma conta:

1.  <a
    href="https://info.jitterbit.com/Harmony-Trial_Request-your-Trial_smart.html"
    class="external-link" rel="nofollow">Solicite uma prova gratuita do Harmony</a>.

2.  Registre a sua conta. As instruções de registro dependem de como
    você se cadastrou ou foi convidado(a):

-   **Eu me cadastrei para uma prova gratuita**: Se você se cadastrou
    para uma prova gratuita, um(a) representante de vendas Jitterbit
    vai aprovar a sua solicitação e enviar um e-mail de boas-vindas
    com mais instruções. Use o *link* contido neste e-mail de
    boas-vindas para completar o processo de registro.

-   **Eu fui convidado(a) para uma organização**: Se você foi
    convidado(a) por outro(a) usuário(a) do Jitterbit Harmony, use o
    *link* contido no seu e-mail de boas-vindas para registrar a sua
    conta.

-   **Eu fui convidado(a) para uma organização usando SSO (*single
    sign-on*)**: Se você foi convidado(a) por outro(a) usuário(a) do
    Jitterbit Harmony para uma organização configurada para [*single
    sign-on*, ou SSO](https://success.jitterbit.com/display/DOC/Single+Sign-On?showLanguage=pt_BR), você já estará registrado(a) por meio do seu
    Identity Provider.

3.  Uma vez registrado(a), você pode fazer *login* no [Jitterbit
    Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR) no site
    [https://login.jitterbit.com](https://login.jitterbit.com./).

Se você for um(a) administrador(a), (um\[a\] usuário\[a\] com permissão
tipo *Admin*), siga o [Manual Rápido para Administradores
Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Admin+Quick+Start+Tutorial?showLanguage=pt_BR) para preparar um ambiente, agentes e Agent Groups, e
convidar membros do time para a sua organização.

Para aprender o básico de como começar com o Cloud Studio, veja o
<a
href="https://success.jitterbit.com/display/CS/Cloud+Studio+Quick+Start+Guide?showLanguage=pt_BR"
rel="nofollow">Guia de Início Rápido do Cloud Studio</a>. Se você estiver usando o
Design Studio, veja o <a
href="https://success.jitterbit.com/display/DOC/Design+Studio+Quick+Start+Guide?showLanguage=pt_BR"
rel="nofollow">Guia de Início Rápido do Design Studio</a> para
fazer o *design* do seu primeiro projeto.


## Mais Informações

Para mais informações para novos usuários, consulte as seguintes páginas
dentro deste tópico:

-   **[Como Receber Ajuda](https://success.jitterbit.com/display/DOC/Getting+Support?showLanguage=pt_BR)**<br>
    Encontrou um problema único, ou precisa de ajuda para entender o que
    fazer? Pergunte à comunidade Jitterbit ou envie uma solicitação de
    suporte através do portal da <a href="https://community.jitterbit.com/s/" class="external-link"
    rel="nofollow">Jitterbit Community</a> (Comunidade
    Jitterbit).

-   **[Como Receber Treinamento](https://success.jitterbit.com/display/DOC/Getting+Training?showLanguage=pt_BR)**<br>
    Matricule-se em cursos e teste o seu conhecimento com a <a href="https://university.jitterbit.com/" class="external-link"
    rel="nofollow">Jitterbit
    University</a> (Universidade Jitterbit), nosso sistema de aprendizagem
    auto-guiada *on-line*.

-   **[Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR)**<br>
    Depois de ter feito *login* no <a href="https://login.jitterbit.com" class="external-link"
    rel="nofollow">Harmony Portal</a>, alguns elementos
    são comuns em todas as aplicações do Harmony, tais como acessar as
    informações da sua conta e mudar a sua senha.

-   **[Manual Rápido para Administradores Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Admin+Quick+Start+Tutorial?showLanguage=pt_BR)**<br>
    Se você estiver pronto(a) para interagir de forma prática com o
    Harmony, este guia introduz você ao Management Console para preparar
    um ambiente e depois conduz você através de todo o processo de criação
    do seu primeiro projeto, seja no [Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR) ou no [Design
    Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR).

-   **[Segurança Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Security?showLanguage=pt_BR)**<br>
    Informações de segurança são dadas para que administradores de
    servidores e funcionários de operação saibam mais sobre como nós
    mantemos os seus dados seguros na Jitterbit.

-   **[*Endpoints* e Protocolos Suportados](https://success.jitterbit.com/display/DOC/Supported+Endpoints+and+Protocols?showLanguage=pt_BR)**<br>
    A Jitterbit já se conectou com centenas de aplicações e fontes de
    dados. Nós estamos constantemente construindo conexões com novas
    aplicações, então se você não encontrar a sua aplicação na lista,
    <a href="https://www.jitterbit.com/contact/" class="external-link"
    rel="nofollow">fale conosco</a>.

-   **[Requisitos de Sistema](https://success.jitterbit.com/display/DOC/System+Requirements?showLanguage=pt_BR)**<br>
    Os requisitos de sistema de todos os produtos do Harmony em um só
    lugar. Alguns dos nossos produtos são baseados no navegador, mas para
    os que requerem instalação, nós damos instruções detalhadas para que
    você possa começar.

Além disso, consulte os recursos a seguir se precisar de ajuda para
começar com a Jitterbit no geral ou de informações sobre um *endpoint*
específico:

-   **[Melhores Práticas com a Jitterbit](https://success.jitterbit.com/display/DOC/Best+Practices+with+Jitterbit?showLanguage=pt_BR)**<br>
    Quando você estiver familiarizado(a) com o Harmony, descubra como os
    nossos especialistas Jitterbit conseguem introduzir melhores práticas
    nas integrações.

-   **[Biblioteca Jitterpak](https://success.jitterbit.com/display/DOC/Jitterpak+Library?showLanguage=pt_BR)**<br>
    Se você tiver um projeto simples ou um caso de uso comum, usar um
    exemplo pode ser a forma mais rápida de começar. Baixe um exemplo
    Jitterpak aqui e comece com o seu projeto.

-   **[Biblioteca de Vídeos](https://success.jitterbit.com/display/DOC/Video+Library?showLanguage=pt_BR)**<br>
    Prefere assistir em vez de ler? Podemos ajudar você, com uma série de
    tópicos de treinamento e demonstrações de *endpoints* específicos.
