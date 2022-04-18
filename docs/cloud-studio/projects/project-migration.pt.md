[//]: # (Migração de Projetos)
[//]: # (This is a translation of Version 13, published on February 16, 2022.)

## Introdução

Dentro de uma única organização Harmony, você pode migrar projetos de um [ambiente](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR) Harmony para outro. A migração de projetos deve ser usada através da preparação de uma *corrente de migração* de ambientes onde você propaga mudanças de design migrando de um ambiente para o próximo. Por exemplo, você pode querer migrar mudanças de um ambiente de design para um ambiente de produção depois de completados os processos de Garantia da Qualidade e revisão.

Você pode migrar projetos independentemente de eles terem sido implantados ou não.

Para mover projetos entre organizações Harmony, veja o artigo [Exportação e Importação de Projetos](https://success.jitterbit.com/display/CS/Project+Exports+and+Imports?showLanguage=pt_BR).


## Corrente de Migração

Uma corrente de migração é uma corrente de ambientes que você usa para migrar um projeto, por exemplo, ao longo das etapas de design desde a criação inicial até a testagem e a produção:

1.  Crie um projeto num ambiente de *Desenvolvimento*.

2.  Migre o projeto do ambiente de *Desenvolvimento* para um ambiente de *Garantia de Qualidade* e implante-o para testagem.

3.  Faça mudanças de design adicionais no projeto no ambiente de *Desenvolvimento* conforme necessário.

4.  Migre o projeto revisado do ambiente de *Desenvolvimento* para o ambiente de *Garantia de Qualidade* e implante-o para testagem conforme necessário.

5.  Migre o projeto do ambiente de *Garantia de Qualidade* para um ambiente de *Produção* e implante-o para que ele entre no ar.

6.  Repita os passos 3 a 5 conforme necessário.

Um projeto migrado tem uma dependência do projeto do qual ele migrou. Como tal, um projeto no início de uma corrente de migração não pode ser deletado até que todos os projetos mais à frente na corrente tenham sido deletados também (veja [Deletando um Projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR#ProjectCreationandConfiguration-deleting-a-project) em [Criação e Configuração de Projetos](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR)). Uma vez que um projeto está migrado, a corrente dele não pode ser rompida exceto deletando projetos mais à frente na corrente ou exportando e importando o projeto (veja [Exportação e Importação de Projetos](https://success.jitterbit.com/display/CS/Project+Exports+and+Imports?showLanguage=pt_BR)). Renomear um projeto migrado não rompe a corrente.

Nós recomendamos as seguintes boas práticas ao criar uma corrente de migração:

-   Em geral, mudanças de design devem ser feitas apenas no primeiro ambiente da corrente (neste exemplo: o ambiente de *Desenvolvimento*). Nos ambientes seguintes, nós recomendamos que as únicas mudanças adicionais sejam mudanças de valores de variáveis de projeto, e que estas mudanças sejam feitas dentro da aplicação do Cloud Studio para que sejam capturadas pelo [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR), visto que as mudanças nos valores das variáveis de projeto feitas na página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console não são capturadas pelo histórico do projeto. Durante a migração, você pode optar entre migrar todos os valores das variáveis de projeto ou apenas valores de variáveis de projeto selecionados individuais (veja **Migrar Todos os Valores de Variáveis** e **Selecionar Valores de Variáveis para Migrar** na próxima seção, [Migrando um Projeto](https://success.jitterbit.com/display/CS/Project+Migration?showLanguage=pt_BR#ProjectMigration-migrate)).

-   O primeiro ambiente na corrente deve ser acessível por todos aqueles que podem precisar fazer mudanças no projeto ao longo do tempo. Nós desaconselhamos que um(a) único(a) desenvolvedor(a) faça o design de um projeto numa organização pessoal. Se tais circunstâncias ocorrerem, nós recomendamos primeiro exportar o projeto original e depois importá-lo para o ambiente que será o início da corrente. Mudanças futuras no projeto deverão então ser feitas no ambiente que começa a corrente.


## Migrando um Projeto

Durante a migração de projetos, todos os componentes e metadados do projeto são migrados. Os componentes e metadados do projeto são uma substituição completa dos componentes e metadados do projeto no ambiente alvo.

<div class="confluence-information-macro confluence-information-macro-note conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**CUIDADO**: Ao migrar uma operação de um ambiente fonte **que não tem** uma agenda atribuída para uma operação em ambiente alvo **que tem** uma agenda atribuída, a operação resultante no ambiente alvo **não terá** uma agenda atribuída.

</div>

</div>

A opção **Migrate** (Migrar) é acessível a partir destes locais:

-   A barra de ferramentas de projeto (veja [Menu de Ações de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR#ProjectToolbar-project-actions-menu) em [Barra de Ferramentas de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR)).

-   O design canvas (veja [Menu de Ações de Implantação/Migração](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-deploy-migrate-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **Migrate**, uma tela de configuração de migração abre onde você pode escolher o ambiente alvo e optar por migrar os valores de [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) individuais:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/migrate.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/migrate.png" /></span>

-   **Organization** (Organização) e **Project** (Projeto): A organização Harmony onde o projeto reside e o nome do projeto a ser migrado, separados por uma vírgula.

-   **Current Environment** (Ambiente Atual): O ambiente onde o projeto a ser migrado está localizado. Quando o projeto é migrado, o projeto existente no ambiente atual permanecerá inalterado.

-   **Target Environment** (Ambiente Alvo): Use o menu *dropdown* para selecionar o ambiente alvo para onde o projeto migrará. Quando o projeto migra, caso já tenha sido migrado para o ambiente alvo, ele será sobrescrito usando as seleções para valores de variáveis de projeto abaixo.

-   **Project History Tag Name** (Nome da *Tag* do Histórico do Projeto): Insira uma *tag* que será usada para rotular o evento migratório. A *tag* será exibida como uma etiqueta no evento migratório e será registrada nos detalhes de implantação acessíveis do [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR). Inserir uma *tag* única é recomendado mas não exigido.

-   **Migrate All Variable Values** (Migrar Todos os Valores de Variáveis): Selecione esta opção para todos os valores de variáveis de projeto a serem migrados. Caso o projeto já exista no ambiente alvo, os valores de todas as variáveis de projeto serão sobrescritos. Da primeira vez que um projeto migra, esta opção é selecionada por padrão. Migrações futuras terão como padrão **Select Variable Values to Migrate** (Selecionar Valores de Variáveis a Migrar).

-   **Select Variable Values to Migrate** (Selecionar Valores de Variáveis a Migrar): Selecione esta opção para migrar todos os componentes e metadados do projeto, exceto os valores de variáveis de projeto listados sob **Exclude** (Excluir). Caso o projeto já exista no ambiente alvo, todos os componentes de projeto, incluindo os valores das variáveis de projeto listados sob **Include** (Incluir), serão sobrescritos.

    Quando **Select Variable Values to Migrate** estiver selecionado, nenhuma variável de projeto é selecionada para migração por padrão. (Todas as variáveis de projeto aparecem listadas sob **Exclude** \[Excluir\].)

    -   **Search** (Buscar): Insira qualquer parte de um nome de variável de projeto para filtrar a lista de variáveis de projeto no ambiente atual.

    -   **Current Environment** (Ambiente Atual): Selecione variáveis de projeto cujos valores você queira migrar para o ambiente alvo. À medida que você seleciona variáveis de projeto, elas vão sendo listadas sob **Include** (Incluir). Os links **Select All** (Selecionar Todos) e **Deselect All** (Desselecionar Todos) podem ser usados para adicionar ou desmarcar todas as seleções de variáveis de projeto de uma vez.

    -   **Exclude** (Excluir): Variáveis de projeto cujos valores serão excluídos da migração. Caso o projeto já exista no ambiente alvo e já contenha a variável de projeto, o valor existente dela no ambiente alvo será retido. Caso a variável de projeto não exista ainda, então o componente da variável de projeto é migrado mas não recebe nenhum valor.

    -   **Include** (Incluir): Variáveis de projeto cujos valores serão incluídos na migração. Caso o projeto já exista no ambiente alvo e já contenha a variável de projeto, o valor existente dela no ambiente alvo será sobrescrito.

-   **Migrate** (Migrar): Clique para migrar o projeto para o ambiente selecionado. Caso o projeto já tenha sido migrado para o ambiente alvo, uma mensagem pede que você confirme que você quer migrar, já que isto vai sobrescrever o projeto existente no ambiente alvo usando as seleções de valores de variáveis de projeto descritas acima:

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/confirm-migrate.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/confirm-migrate.png" /></span>

    Ao clicar em **Continue** (Continuar), se a migração para o ambiente alvo for bem-sucedida, o projeto migrado abre no designer de projetos.
