[//]: # (Permissões e Acesso ao Jitterbit Harmony)
[//]: # (This is a translation of Version 8, published on June 29, 2021.)

## Introdução

O acesso às diferentes áreas do Jitterbit Harmony é baseado numa
combinação de permissões de funções organizacionais e níveis de acesso
ambiental. Esta página oferece definições dos termos do Jitterbit
Harmony relacionados às permissões e aos níveis de acesso e provê uma
matriz para determinar quais áreas um membro pode acessar.


## Terminologia Administrativa do Jitterbit Harmony

Os administradores de organizações devem estar familiarizados com os
seguintes termos para organizações e ambientes:

-   **Organizações**

    -   **Organização**: Uma organização Jitterbit Harmony única na qual
        os administradores têm total controle sobre a lista de membros
        e a segurança. As configurações feitas a nível de organização
        (na página [Organizações](https://success.jitterbit.com/display/DOC/Organizations)) estão sujeitas e podem ser
        melhor definidas no nível de ambiente (na página
        [Ambientes](https://success.jitterbit.com/display/DOC/Environments)). Uma organização também pode ser chamada
        pela abreviação org.

    -   **Membro**: Um(a) usuário(a) do Jitterbit Harmony que foi
        adicionado(a) a uma organização por um(a) administrador(a)
        (descrito em [Membros](https://success.jitterbit.com/display/DOC/Organizations#Organizations-members) na página [Organizações](https://success.jitterbit.com/display/DOC/Organizations)).

    -   **Administrador**: Um membro que recebeu uma função com
        permissão de tipo *Admin* a nível de organização, o que lhe dá
        acesso a todos os recursos e funções disponíveis no
        [Management Console](https://success.jitterbit.com/display/DOC/Management+Console).

    -   **Funções**: Um grupo de membros que recebe uma ou mais
        permissões a nível de organização. Inicialmente, quando uma
        organização do Jitterbit Harmony é criada, uma função
        *Administrator* (Administrador, alguém com permissão de tipo
        *Admin*) e uma função *User* (Usuário, alguém com permissão de
        tipo *Read*, isto é, *Ler*) são criados por padrão. Os
        administradores podem criar funções adicionais e adicionar
        membros a várias funções (descritos em [Funções](https://success.jitterbit.com/display/DOC/Organizations#Organizations-roles) na
        página [Organizações](https://success.jitterbit.com/display/DOC/Organizations)).

    -   **Permissões**: As permissões são atribuídas a uma função no
        nível de organização e limitam o acesso de um membro da
        organização a áreas delimitadas de uma organização. As
        permissões incluem *Read* (Ler), *Admin* (Administrador),
        *Agent Install* (Instalação de Agent) e *ApiConsumer*
        (Consumidor API), todas as quais estão definidas em
        [Permissões](https://success.jitterbit.com/display/DOC/Organizations#Organizations-permissions) na página [Organizações](https://success.jitterbit.com/display/DOC/Organizations).

-   **Ambientes**:

    -   **Ambiente**: Um ambiente é estabelecido dentro de uma
        organização e é usado para segregar diferentes estados de um
        projeto de integração e seus recursos. Por exemplo, uma
        organização pode ter três ambientes: *Desenvolvimento*,
        *Teste* e *Produção*.

    -   **Níveis de Acesso**: Os níveis de acesso são atribuídos a uma
        função que recebeu acesso a um ambiente. Eles são usados em
        conjunto com as permissões organizacionais para aumentar a
        capacidade dos administradores de controlar o que os membros
        de uma função específica podem fazer num ambiente específico.
        Os níveis de acesso incluem *View Logs* (Visualizar
        Registros), *Read* (Ler), *Execute* (Executar) e *Write*
        (Escrever), e todos estão descritos em [Níveis de Acesso](https://success.jitterbit.com/display/DOC/Environments#Environments-access-levels)
        na página [Ambientes](https://success.jitterbit.com/display/DOC/Environments).

As áreas que um membro do Jitterbit Harmony pode acessar dependem da
combinação das permissões da sua função organizacional e níveis de
acesso ambiental. As permissões e os níveis de acesso são determinados
de maneira independente e são diferentes um do outro. Por exemplo:

-   Um membro de uma função com permissão *Read* (Ler) no nível de
    organização talvez ainda possa fazer edições em um ambiente caso o
    acesso *Write* (Escrever) seja atribuído a função dele no nível de
    ambiente.

-   Um membro de uma função com permissão *Admin* (Administrador) no
    nível de organização mas cujo papel tem apenas acesso *Read* (Ler)
    no nível de ambiente não pode implantar, executar nem editar
    projetos naquele ambiente.

-   Um membro de uma função com permissão *Admin* (Administrador) no
    nível de organização mas cuja função não recebeu acesso ao
    ambiente não consegue acessar o ambiente de modo algum.

-   Um membro de uma função com permissão *Read* (Ler) no nível de
    organização e cuja função recebeu acesso *Read* (Ler) no Ambiente
    A e acesso *Write* (Escrever) no Ambiente B pode migrar um projeto
    do Ambiente A para o Ambiente B.

Para acessar um ambiente, as funções (até as funções com permissão
*Admin*) precisam receber acesso a ele. Isto inclui poder acessar áreas
das aplicações do Jitterbit Harmony que requerem que um ambiente seja
selecionado e poder instalar [Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents) em um ambiente.
