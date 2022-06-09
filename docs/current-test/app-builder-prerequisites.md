[//]: # (Pré-requisitos)
[//]: # (This is a translation of Version 5, published on April 21, 2022.)


## Introdução

O acesso ao App Builder é controlado por meio de uma combinação de permissões de papel organizacional do Jitterbit Harmony e níveis de acesso ambientais. Além disso, um tempo de execução de aplicação deve ser estabelecido. O acesso também é controlado no nível da aplicação por meio da autorização de colaboradores individuais.


## Acessando o App Builder

Para acessar o App Builder, os seguintes pré-requisitos devem ser atendidos:

-   Você deve ser membro de um papel organizacional do Harmony com permissão de tipo *Admin* ou com permissões tanto *Read* quanto *App Developer* (veja a seção [Permissões](https://success.jitterbit.com/display/DOC/Organizations#Organizations-permissions) no artigo [Organizações](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR)).

-   A organização do Harmony deve ter pelo menos um ambiente com um tempo de execução de aplicação associado a ele, seja **Sandbox** ou **Production** (veja a seção [Gerenciando Ambientes](https://success.jitterbit.com/display/DOC/Environments#Environments-managing-environments) no artigo [Ambientes](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR)). Depois de associar um tempo de execução de aplicação, pode ser que você precise fazer *logout* depois fazer *login* novamente no Harmony Portal para habilitar o acesso ao App Builder.

-   O papel organizacional do Harmony deve ter pelo menos acesso de tipo *Read* no ambiente já mencionado (veja a seção [Níveis de Acesso](https://success.jitterbit.com/display/DOC/Environments#Environments-access-levels) no artigo [Ambientes](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR)).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: O App Builder atualmente está disponível para algumas organizações selecionadas antes de estar disponível geralmente. Caso você não veja o cartão do App Builder, entre em contato com o(a) seu(sua) [CSM](mailto:success@jitterbit.com) para obter mais informações.

</div>

</div>


## Criando uma Aplicação

Para criar uma aplicação nova, o papel organizacional do Harmony deve ter permissão de tipo *Admin*. Isto permite que os usuários vejam o botão **Create New App** (Criar Nova Aplicação) na interface de usuário do App Builder (veja o artigo [Criação de Aplicações](https://success.jitterbit.com/display/APP/App+Creation?showLanguage=pt_BR)).


## Editando uma Aplicação Existente

Aqueles que possuem permissão de tipo *Admin* têm a habilidade de controlar quem pode acessar e contribuir com cada aplicação gerenciando os colaboradores. Isso é feito através da página **Collaborators** (Colaboradores) do App Builder (veja a seção [Colaboradores](https://success.jitterbit.com/display/APP/Development#Development-collaborators) no artigo [Desenvolvimento](https://success.jitterbit.com/display/APP/Development?showLanguage=pt_BR)). Os seguintes níveis de autorização estão disponíveis:

-   **Developer** (Desenvolvedor): Tem autoridade para desenvolver na aplicação definida.

-   **Manager** (Gerente): Tem autoridade para acessar e editar todas as aplicações criadas.


## Navegadores Suportados

Visto que o App Builder é acessado por meio do Harmony Portal, ele não requer a instalação de nenhum *hardware* ou *software* adicional. Os seguintes navegadores comuns são suportados:

-   Chrome

-   Firefox

-   Safari (apenas para macOS)
