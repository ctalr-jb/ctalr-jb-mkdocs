[//]: # (Permissões e Acesso ao Jitterbit Harmony)
[//]: # (This is a translation of Version 13, published on April 15, 2022.)

## Introdução

O acesso às diferentes áreas do Jitterbit Harmony é baseado numa combinação de permissões de funções organizacionais, níveis de acesso ambiental e níveis de autorização de aplicações. Esta página oferece definições dos termos do Jitterbit Harmony relacionados a permissões, acesso e autorização.


## Terminologia Administrativa do Jitterbit Harmony

Os administradores de organizações devem estar familiarizados com os seguintes termos do Jitterbit Harmony para organizações, ambientes e aplicações:

-   **Organizações**

    -   **Organização**: Uma organização Jitterbit Harmony única na qual
        os administradores têm total controle sobre a lista de membros
        e a segurança. As configurações feitas a nível de organização
        (na página [Organizações](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR)) estão sujeitas e podem ser
        melhor definidas no nível de ambiente (na página
        [Ambientes](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR)). Uma organização também pode ser chamada
        pela abreviação org.

    -   **Membro**: Um(a) usuário(a) do Jitterbit Harmony que foi
        adicionado(a) a uma organização por um(a) administrador(a)
        (descrito em [Membros](https://success.jitterbit.com/display/DOC/Organizations#Organizations-members?showLanguage=pt_BR) na página [Organizações](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR)).

    -   **Administrador**: Um membro que recebeu uma função com
        permissão de tipo *Admin* a nível de organização, o que lhe dá
        acesso a todos os recursos e funções disponíveis no
        [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR).

    -   **Funções**: Um grupo de membros que recebe uma ou mais permissões a nível de organização. Inicialmente, quando uma organização do Jitterbit Harmony é criada, uma função *Administrator* (Administrador, alguém com permissão de tipo *Admin*) e uma função *User* (Usuário, alguém com permissão de tipo *Read*, isto é, *Ler*) são criadas por padrão. Os administradores podem criar funções adicionais e adicionar membros a várias funções (descritos em [Funções](https://success.jitterbit.com/display/DOC/Organizations#Organizations-roles?showLanguage=pt_BR) na página [Organizações](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR)).

    -   **Permissões**: As permissões são atribuídas a uma função no
        nível de organização e limitam o acesso de um membro da
        organização a áreas delimitadas de uma organização. As
        permissões incluem *Read* (Ler), *Admin* (Administrador),
        *Agent Install* (Instalação de Agent) e *ApiConsumer*
        (Consumidor API), todas as quais estão definidas em
        [Permissões](https://success.jitterbit.com/display/DOC/Organizations#Organizations-permissions?showLanguage=pt_BR) na página [Organizações](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR).

-   **Ambientes**:

    -   **Ambiente**: Um ambiente é estabelecido dentro de uma
        organização e é usado para segregar diferentes estados de um
        projeto de integração e seus recursos. Por exemplo, uma
        organização pode ter três ambientes: *Desenvolvimento*,
        *Teste* e *Produção*.

    -   **Níveis de Acesso**: Os níveis de acesso são atribuídos a uma função que recebeu acesso a um ambiente. Eles são usados em conjunto com as permissões organizacionais para aumentar a capacidade dos administradores de controlar o que os membros de uma função específica podem fazer num ambiente específico. Os níveis de acesso incluem *View Logs* (Visualizar Registros), *Read* (Ler), *Execute* (Executar) e *Write* (Gravar), e todos estão descritos em [Níveis de Acesso](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR#Environments-access-levels) na página [Ambientes](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR).

-   **Aplicações**:

    -   **Níveis de Autorização**: Os níveis de autorização das aplicações são especificados pelos administradores Harmony na aplicação App Builder. Eles são usados em conjunto com as permissões organizacionais e os níveis de acesso ambientais para permitir que usuários individuais acessem ou editem aplicações individuais criadas com o App Builder. O nível de autorização é selecionado dentre as duas opções Developer (Desenvolvedor[a]) ou Manager (Administrador[a]) (veja Colaboradores).


As áreas que um membro do Jitterbit Harmony pode acessar dependem da
combinação das permissões da sua função organizacional e níveis de
acesso ambiental. As permissões e os níveis de acesso são determinados
de maneira independente e são diferentes um do outro. Por exemplo:

-   Um membro de uma função com permissão *Read* (Ler) no nível de organização talvez ainda possa fazer edições em um ambiente caso o acesso *Write* (Gravar) seja atribuído à função dele no nível de ambiente.

-   Um membro de uma função com permissão *Admin* (Administrador) no
    nível de organização mas cujo papel tem apenas acesso *Read* (Ler)
    no nível de ambiente não pode implantar, executar nem editar
    projetos naquele ambiente.

-   Um membro de uma função com permissão *Admin* (Administrador) no
    nível de organização mas cuja função não recebeu acesso ao
    ambiente não consegue acessar o ambiente de modo algum.

-   Um membro de uma função com permissão *Read* (Ler) no nível de organização e cuja função recebeu acesso *Read* (Ler) no Ambiente A e acesso *Write* (Gravar) no Ambiente B pode migrar um projeto do Ambiente A para o Ambiente B.

Para acessar um ambiente, as funções (até as funções com permissão
*Admin*) precisam receber acesso a ele. Isto inclui poder acessar áreas
das aplicações do Jitterbit Harmony que requerem que um ambiente seja
selecionado e poder instalar [Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents?showLanguage=pt_BR) em um ambiente.

Ao contrário de outras aplicações do Harmony, os níveis de acesso ambientais não se aplicam no [App Builder](https://success.jitterbit.com/display/APP/App+Builder?showLanguage=pt_BR) exceto que o acesso ambiental Read (Ler) é necessário para acessar o App Builder. Em vez disso, a habilidade de visualizar ou editar aplicações individuais é definida com níveis de autorização de aplicação especificadas dentro da aplicação do App Builder (veja [Colaboradores](https://success.jitterbit.com/display/APP/Collaborators?showLanguage=pt_BR)).
