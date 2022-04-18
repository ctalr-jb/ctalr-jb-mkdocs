[//]: # (Criação e Configuração de Projetos)
[//]: # (This is a translation of Version 26, published on February 16, 2022.)

## Introdução

Esta página descreve como criar e configurar um novo projeto dentro do Cloud Studio, como abrir um projeto existente, editar suas configurações ou deletá-lo.

Novos projetos do Cloud Studio também podem ser criados usando os [Protótipos de Integração do Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Integration+Recipes?showLanguage=pt_BR) ou os [*Templates* de Processo do Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Process+Templates?showLanguage=pt_BR) ofertados pelo [Jitterbit Marketplace](https://success.jitterbit.com/display/DOC/Marketplace?showLanguage=pt_BR). Para mais informações sobre como criar um novo projeto do Cloud Studio a partir do Marketplace, veja a página [Começando um Projeto com um Protótipo ou um *Template*](https://success.jitterbit.com/display/DOC/Starting+a+Recipe+or+Template+Project?showLanguage=pt_BR).


## Criando um Novo Projeto

Novos projetos são criados na página **My Projects** (Meus Projetos), também conhecida como [índice de projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR). Esta página contém um repositório dos projetos do Cloud Studio que estão acessíveis. Se nenhum projeto estiver acessível na organização selecionada, nenhum é mostrado.

Para criar um novo projeto do Cloud Studio, clique em **New Project** (Novo Projeto):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-index/no-projects.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-index/no-projects.png" /></span>

Ao clicar em **New Project**, a tela de configuração de projeto se abre. Duas abas estão disponíveis, **General** (Geral) e **Deploy** (Implantação):

-   **General** (Geral): Especifique informações gerais sobre o projeto, incluindo o nome, o ambiente e a descrição:

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/project_new_general.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/project_new_general.png" /></span>

-   **Project Name** (Nome do Projeto): Insira um nome a ser usado para identificar o projeto. O nome do projeto deve ser único para cada ambiente, e não pode já estar em uso como projeto do [Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR) no mesmo ambiente. Se um projeto com o mesmo nome já existir na nuvem do Jitterbit Harmony, vá até a página [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR) \> [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) para gerenciar o projeto implantado.

-   **Environment** (Ambiente): Use o menu *dropdown* para selecionar um ambiente existente onde você quer criar o projeto. Os administradores da organização podem preparar novos ambientes por meio da página [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR) \> [Ambientes](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR).

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Caso você não veja um ambiente recém-criado disponível para seleção, atualize a página do [índice de projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR) para forçar um recarregamento dos ambientes.

    </div>

    </div>

-   **Description** (Descrição): Insira uma descrição opcional para o projeto. Esta descrição vai aparecer no índice de projetos e pode ser útil para ajudar os colaboradores do projeto a entendê-lo.

-   **Deploy** (Implantação): Defina as configurações de implantação a nível de projeto, o que só pode ser feito por usuários que possuam tanto permissão de tipo *Admin* em seu papel organizacional e acesso ambiental de tipo *Write* (veja o artigo [Permissões e Acesso ao Jitterbit Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access?showLanguage=pt_BR)). Para usuários que não têm a permissão apropriada, a seguinte mensagem é exibida: “There is no requirement provided by your organization” (em português, *Não há nenhum requisito fornecido pela sua organização*).

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Estas configurações não estão disponíveis para serem definidas a nível organizacional.

    </div>

    </div>

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/project_new_deploy.png class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/project_new_deploy.png" /></span>

-   **Require Comments When Deploying** (Exigir Comentários ao Implantar): Selecione esta opção para exigir que sempre que um projeto for implantado, uma caixa de diálogo seja exibida pedindo que um comentário seja adicionado.

-   **Require Tags When Deploying** (Exigir *Tags* ao Implantar): Selecione esta opção para exigir que sempre que um projeto for implantado, uma caixa de diálogo seja exibida pedindo que uma *tag* seja adicionada.

Clique em **Start Designing** (Começar o *Design*) para enviar as informações do novo projeto e prosseguir para o *designer* de projeto:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/start-designing_button.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/start-designing_button.png" /></span>

Esta ação armazena o novo projeto no Cloud Studio; no entanto, note que o projeto ainda não foi implantado (veja o artigo [Implantação de Projetos](https://success.jitterbit.com/display/CS/Project+Deployment?showLanguage=pt_BR)).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Para fazer mudanças na configuração de um projeto depois que ele já foi criado, veja a seção [Editando as Configurações de um Projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR#ProjectCreationandConfiguration-edit-settings), mais abaixo nesta mesma página.

</div>

</div>


## Abrindo um Projeto Existente

Projetos existentes são exibidos no [índice de projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR) filtrados por ambiente. Use o menu *dropdown* **Filter By** (Filtrar Por) para selecionar um ambiente diferente para a sua organização selecionada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-index/environments.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-index/environments.png" /></span>

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA:** Os ambientes disponíveis são para a sua organização selecionada. A organização selecionada pode ser alterada na barra de navegação do topo (veja [Mudando a Organização Selecionada](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR#JitterbitHarmonyPortal-org) no [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR)).

</div>

</div>

Projetos existentes podem ser abertos tanto na visualização de cartões de projeto quanto na visualização de lista de projetos. Para mais detalhes sobre todas as opções disponíveis em cada uma dessas formas de visualização, veja o artigo [Índice de Projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR).

-   **Visualização de Cartões no Índice de Projetos**: Clique no ícone da visualização de cartões <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/card-view.png" class="confluence-embedded-image confluence-external-resource" /></span> para entrar na visualização de cartões. Daí, paire o mouse sobre um cartão de projeto e selecione **View/Edit** (Visualizar/Editar) para abrir o projeto no *designer* de projeto:

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-index/card-view_flip_cropped.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-index/card-view_flip_cropped.png" /></span>

-   **Visualização de Lista no Índice de Projetos**: Clique no ícone da visualização de lista <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/list-view.png" class="confluence-embedded-image confluence-external-resource" /></span> para entrar na visualização de lista. Daí, paire o mouse sobre a célula vazia na coluna rotulada com um ícone de menu de ações <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/actions-menu_10.png" class="confluence-embedded-image confluence-external-resource" /></span> e clique no ícone de editar <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/edit.png" class="confluence-embedded-image confluence-external-resource" /></span> para abrir o projeto no *designer* de projetos.

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-index/list-view.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-index/list-view.png" /></span>


## Editando as Configurações de um Projeto

Um projeto recebe as primeiras configurações durante a [sua criação](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR#ProjectCreationandConfiguration-new-project), descrita mais acima nesta mesma página. Depois que um projeto é criado, você pode editar as configurações dele para fazer mudanças no nome ou na descrição do projeto, ou para exportá-lo ou deletá-lo.

A opção **Project Settings** (Configurações de Projeto) é acessível a partir dos seguintes locais:

-   O índice de projetos (veja [Visualização de Cartões](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR#ProjectIndex-card-view) ou [Visualização de Lista](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR#ProjectIndex-list-view) em [Índice de Projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR)).

-   A barra de ferramentas de projeto (veja [Menu de Ações de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR#ProjectToolbar-project-actions-menu) em [Barra de Ferramentas de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR)).

Isto abre a tela de configuração de projeto. Duas abas estão disponíveis, **General** (Geral) e **Deploy** (Implantação):

-   **General** (Geral): Veja informações gerais sobre o projeto, e faça mudanças no nome ou na descrição dele:

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/project_existing_general.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/project_existing_general.png" /></span>

-   **Project Name** (Nome do Projeto): Edite o nome usado para identificar o projeto. O nome do projeto deve ser único para cada ambiente, e não pode já estar em uso como nome de um projeto do [Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR) no mesmo ambiente.

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Ao renomear um projeto que já foi implantado antes, o novo nome do projeto é automaticamente implantado e atualizado no Jitterbit Harmony. Nenhuma outra parte do projeto além do nome é implantada automaticamente desta forma.

    </div>

    </div>

-   **Description** (Descrição): Edite a descrição do projeto. Esta descrição vai aparecer no índice de projetos e pode ser útil para ajudar colaboradores do projeto a entendê-lo.

-   **Environment** (Ambiente): O [ambiente](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR) no qual o projeto reside (especificado durante a [criação](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR#ProjectCreationandConfiguration-new-project) ou a [migração do projeto](https://success.jitterbit.com/display/CS/Project+Migration?showLanguage=pt_BR)).

-   **Agent Group**: O [Agent Group](https://success.jitterbit.com/display/DOC/Agents+%3E+Agent+Groups?showLanguage=pt_BR) associado com o ambiente no qual o projeto reside (especificado no [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR)).

-   **Created On** (Criado Em): A data e a hora em que o projeto foi criado.

-   **Deploy** (Implantação): Defina as configurações de implantação a nível de projeto, o que só pode ser feito por usuários que possuam tanto permissão de tipo *Admin* em seu papel organizacional e acesso ambiental de tipo *Write* (veja o artigo [Permissões e Acesso ao Jitterbit Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access?showLanguage=pt_BR)). Para usuários que não possuem a permissão de papel apropriada, uma mensagem aponta quais configurações estão habilitadas. (Quando nenhuma configuração de implantação está habilitada, a seguinte mensagem é exibida: “There is no requirement provided by your organization”, em português, *Não há nenhum requisito fornecido pela sua organização*).

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Estas configurações não estão disponíveis para serem definidas a nível organizacional.

    </div>

    </div>

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/project_existing_deploy.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/project_existing_deploy.png" /></span>

-   **Require Comments When Deploying** (Exigir Comentários ao Implantar): Selecione esta opção para que, sempre que um projeto for implantado, uma caixa de diálogo seja exibida exigindo que um comentário seja adicionado.

-   **Require Tags When Deploying** (Exigir *Tags* ao Implantar): Selecione esta opção para que, sempre que um projeto for implantado, uma caixa de diálogo seja exibida exigindo que uma *tag* seja adicionada.

Os seguintes botões ou *links* estão disponíveis na parte inferior da tela de configuração de projeto:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/save_cancel_export_delete_buttons.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/save_cancel_export_delete_buttons.png" /></span>

-   **Save** (Salvar): Salva e fecha a configuração do projeto. Este botão só ficará habilitado depois que você tiver feito mudanças nas configurações existentes.

-   **Cancel** (Cancelar): Fecha a configuração do projeto sem salvar.

-   **Export** (Exportar): Gera e inicia o *download* de um arquivo JSON do projeto do Cloud Studio. Uma exportação de projeto pode ser usada, por exemplo, como *backup* do projeto ou para compartilhar uma cópia dele. Para mais detalhes, veja o artigo [Exportações e Importações de Projetos](https://success.jitterbit.com/display/CS/Project+Exports+and+Imports?showLanguage=pt_BR).

-   **Delete** (Deletar): Deleta de forma permanente o projeto do ambiente no Cloud Studio e da nuvem do Harmony (veja a seção [Deletando um Projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR#ProjectCreationandConfiguration-deleting-a-project) mais abaixo nesta mesma página).


## Deletando um Projeto

Deletar um projeto o apaga permanentemente do ambiente no Cloud Studio e da nuvem do Harmony, incluindo quaisquer projetos implantados.

A opção **Delete** (Deletar) é acessível dos seguintes lugares:

-   As configurações do projeto (veja a seção [Editando as Configurações de um Projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR#ProjectCreationandConfiguration-edit-settings) mais acima nesta mesma página).

-   O índice de projetos (veja [Visualização de Cartões](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR#ProjectIndex-card-view) ou [Visualização de Lista](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR#ProjectIndex-list-view) em [Índice de Projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR)).

Ao clicar em **Delete** (Deletar), uma mensagem de confirmação pede que você confirme que quer deletar o projeto:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/delete-project.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/delete-project.png" /></span>

Se o projeto que você está tentando deletar tiver sido migrado, ele não pode ser deletado antes que você delete também todos os projetos abaixo dele na corrente de migração (veja [Corrente de Migração](https://success.jitterbit.com/display/CS/Project+Migration?showLanguage=pt_BR#ProjectMigration-migration-chain) em [Migração de Projetos](https://success.jitterbit.com/display/CS/Project+Migration?showLanguage=pt_BR)). Depois de clicar em **Continue** (Continuar) na caixa de diálogo **Delete Project** (Deletar Projeto), uma segunda caixa de diálogo indica que o projeto não pode ser deletado porque ele tem projetos dependentes:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/unable-to-delete-project.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/unable-to-delete-project.png" /></span>

Para solucionar isto, primeiro delete todos os projetos abaixo dele na corrente de migração, e daí tente deletar este projeto novamente.
