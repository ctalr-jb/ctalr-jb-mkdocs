[//]: # (Aba Workflows do Painel de Projeto)
[//]: # (This is a translation of Version 4, published on October 20, 2021.)

## Introdução

A aba **Workflows** do painel de projeto é uma das duas abas acessíveis
no [painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane?showLanguage=pt_BR). (A outra é a [aba **Components**](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

A aba **Workflows** mostra uma visão em árvore hierarquicamente
organizada de todos os workflows de um projeto aberto, suas operações, e
outros componentes mencionados dentro de cada operação.

## Árvore Hierárquica

Em um projeto, os workflows estão no nível hierárquico mais alto,
seguidos pelas operações, e daí por outros componentes usados como
passos dentro de uma operação (feitas de atividades, *transformations*
ou *scripts*).

Esta estrutura é representada na aba **Workflows** de um projeto aberto,
onde os workflows aparecem no topo com um ícone de workflow
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/workflow.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/workflow.png"
height="15" /></span>
à esquerda. Os workflows são expansíveis para revelar as operações
indentadas abaixo de cada um. As operações são expansíveis para revelar
os componentes que compõem os passos dentro de cada operação. Tanto os
workflows quanto as operações recebem números gerados automaticamente
para representar a posição deles na árvore:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/overview.png" /></span>

Quando cada workflow e operação é expandido, todos os workflows,
operações, e etapas de operação são exibidos.

## Buscando

Para fazer buscas dentro da aba **Workflows**, use a caixa de busca para
inserir uma única palavra chave ou série de palavras chave. A árvore
hierárquica é automaticamente expandida para mostrar workflows e
componentes onde as palavras chave aparecem. Elas também serão
negritadas (se já não estiverem) e ficarão roxas dentro do nome do
workflow ou componente:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/search.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/search.png" /></span>

Para limpar a busca, clique no ícone de remoção
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_11.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_11.png"
height="18" /></span>.

## Expandindo e Selecionando Itens

Para expandir ou reduzir workflows ou operações, clique nos triângulos
de revelação
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/down-arrow_6.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/down-arrow_6.png"
height="9" /></span> <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/right-arrow_5.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/right-arrow_5.png"
height="12" /></span>
ao lado do workflow ou operação.

À medida que você trabalhar nos projetos, o Cloud Studio se lembrará dos
estados de exibição que um dado usuário usou pela última vez em um dado
projeto, incluindo se os itens no painel de projeto estavam expandidos
ou reduzidos.

Clique num workflow para selecioná-lo e abri-lo no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR).
Um workflow selecionado é exibido com o nome roxo e o fundo cinza:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_selected.png" /></span>

Quando um workflow for expandido, clique numa operação dentro do
workflow para selecioná-lo e rolar automaticamente até ele no [design
canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR). Uma operação selecionada é exibida com fundo cinza:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_expanded.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_expanded.png" /></span>

Quando uma operação é expandida, clique numa etapa de operação dentro da
operação para selecioná-la e rolar automaticamente até ela no [design
canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR). Uma operação selecionada é exibida com fundo cinza:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_expanded_operation-step.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_expanded_operation-step.png" /></span>


## Vendo Erros de Validação

Quando você estiver usando a opção **Highlight Invalid Items** (Destacar
Itens Inválidos) no design canvas, os nomes dos workflows, operações e
outros componentes inválidos vão aparecer em itálico e na cor vermelha.
Quando selecionado, um workflow inválido é exibido com um fundo rosa.

Se o workflow ou componente for implicitamente inválido, um ícone de
erro
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/error.png"
height="16" /></span>
também será mostrado:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_workflow.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_workflow.png" /></span>

Você pode ver os erros de validação associados com workflows e
componentes inválidos conforme descritos em [Validade de
Workflows](https://success.jitterbit.com/display/CS/Workflow+Validity?showLanguage=pt_BR), [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR), e [Validade de
Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR).


## Menus de Ações

Para abrir um menu de ações que podem ser tomadas em cada workflow ou
componente, faça uma das seguintes coisas:

-   Clique no item com o botão direito do mouse.

-   Paire o mouse sobre o item, e daí clique no ícone do menu de ações
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    height="6" /></span>.

As ações disponíveis em cada menu dependem do contexto e variam de
acordo com o item.

### <span id="ProjectPaneWorkflowsTab-workflow-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Menu de Ações de Workflow

O menu de ações de workflow inclui as seguintes ações:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_actions-menu.png" /></span>

<div class="table-wrap">

<table class="relative-table confluenceTable" style="width: 97.8058%;">
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header header">
<th><strong>Item do Menu</strong></th>
<th><strong>Descrição</strong></th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy.png"
height="33" /></span></p>
</div></th>
<th><strong>Deploy</strong> faz a implantação do workflow e de quaisquer
componentes dos quais ele dependa (veja <a
href="https://success.jitterbit.com/display/CS/Workflow+Deployment">Implantação de
Workflows</a>).</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/configurable-deploy.png"
height="33" /></span></p>
</div></th>
<th><strong>Configurable Deploy</strong> abre a tela de implantação,
onde você pode selecionar componentes do projeto para implantar (veja
<a href="https://success.jitterbit.com/display/CS/Workflow+Deployment">Implantação de Workflows</a>).</th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
height="33" /></span></p>
</div></th>
<th><strong>Rename</strong> posiciona o cursor sobre o nome do workflow
para que você faça quantas edições forem necessárias.</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
height="33" /></span></p>
</div></th>
<th><strong>View Dependencies</strong> muda a visualização no painel de
projeto para exibir quaisquer outras partes do projeto das quais aquele
workflow específico depende (veja <a
href="https://success.jitterbit.com/display/CS/Workflow+Dependencies+and+Deletion">Dependências e Exclusão de
Workflows</a>).</th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
height="33" /></span></p>
</div></th>
<th><strong>View Logs</strong> abre a tela de registros de operação, que
inclui os registros de quaisquer operações contidas no workflow que
tenham sido implantadas e executadas, bem como quaisquer operações com
links no workflow que tenham sido implantadas e executadas (veja
  <a
  href="https://success.jitterbit.com/display/CS/Operation+Logs">Registros de Operação</a>).</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
height="33" /></span></p>
</div></th>
<th><strong>Delete</strong> exclui permanentemente o workflow (veja
  <a
  href="https://success.jitterbit.com/display/CS/Workflow+Dependencies+and+Deletion">Dependências e Exclusão de Workflows</a>).</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

</div>

### <span id="ProjectPaneWorkflowsTab-component-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Menu de Ações de Componente

Algumas ações estão disponíveis apenas em certos tipos de componente,
conforme detalhado nas subseções abaixo:

-   **[Operações](#ProjectPaneWorkflowsTab-operations)**: O menu de ações de operação (mostrado na
    primeira imagem abaixo) tem itens únicos, como **Settings**
    (Configurações), **Run** (Executar) e **View Logs** (Ver
    Registros), bem como sub-menus diferentes em **Deploy**
    (Implantar). Ele também inclui ações comuns tais como **Cut**
    (Recortar), **Copy** (Copiar), **Rename** (Renomear), **View
    Dependencies** (Ver Dependências), **Delete** (Deletar) e
    **Remove** (Remover).

-   **[Atividades, *Scripts* e *Transformations*](#ProjectPaneWorkflowsTab-share)**: Os menus de
    ações destes componentes compartilham as mesmas ações, incluindo
    **View/Edit** (Ver/Editar), **Cut** (Recortar), **Copy** (Copiar),
    **Deploy** (Implantar), **Rename** (Renomear), **View
    Dependencies** (Ver Dependências), **Delete** (Deletar) e
    **Remove** (Remover) mostradas no menu de ações de atividade na
    segunda imagem abaixo.

**Menu de ações de operação**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/operation_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/operation_actions-menu.png" /></span>

**Menu de ações de atividade**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/activity_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/activity_actions-menu.png" /></span>

#### <span id="ProjectPaneWorkflowsTab-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operações

Os seguintes itens estão disponíveis em um menu de ações de operação:

<div class="table-wrap">

<table class="confluenceTable">
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header header">
<th><strong>Item do Menu</strong></th>
<th><strong>Descrição</strong></th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><strong><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/settings.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/settings.png"
height="33" /></span></strong></p>
</div></th>
<th><p><strong>Settings</strong> abre as configurações de operação,
contendo três abas:</p>
<ul>
<li>
<p><strong>Schedules</strong> (Agendas): Crie e aplique agendas para
operações executadas automaticamente (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Schedules">Agendas de
Operação</a>).</p>
</li>
<li>
<p><strong>Actions</strong> (Ações): Configure ações a serem tomadas em
caso de sucesso ou fracasso da operação (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Actions">Ações de
Operação</a>).</p>
</li>
<li>
<p><strong>Options</strong> (Opções): Configure opções tais como quanto
tempo a operação tem para executar, o que deve ser escrito no registro,
o prazo para registrar, quando a operação deverá executar, ou caso a
fragmentação de dados (<em>chunking</em>) deverá ser usada (veja
  <a
  href="https://success.jitterbit.com/display/CS/Operation+Options">Opções de Operação</a>).</p>
</li>
</ul></th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><strong><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
height="33" /></span></strong></p>
</div></th>
<th><strong>Cut</strong> coloca uma cópia da operação na sua área de
transferência e exclui a operação original do projeto (veja <a href="https://success.jitterbit.com/display/CS/Operation+Reuse">Reuso de
Operações</a>).</th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
height="33" /></span></p>
</div></th>
<th><strong>Copy</strong> coloca uma cópia da operação na sua área de
transferência (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Reuse">Reuso de Operações</a>).</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_deploy-and-run_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_deploy-and-run_configurable-deploy.png"
height="101" /></span></p>
</div></th>
<th><p><strong>Deploy</strong> mostra as seguintes ações de menu:</p>
<ul>
<li>
<p><strong>Deploy</strong>: Implanta a operação e quaisquer componentes
dos quais ela dependa (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e Execução de
Operações</a>).</p>
</li>
<li>
<p><strong>Deploy and Run</strong>: Implanta e executa a operação e
quaisquer operações (conectadas) abaixo dela na cadeia (veja
  <a
  href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e Execução de Operações</a>).</p>
</li>
<li>
<p><strong>Configurable Deploy</strong>: Abre a tela de implantação,
onde você pode selecionar componentes para implantar (veja
  <a
  href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e Execução de Operações</a>).</p>
</li>
</ul></th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/run.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/run.png"
height="33" /></span></p>
</div></th>
<th><strong>Run</strong> executa uma operação já implantada e quaisquer
operações (ligadas) abaixo dela na cadeia (veja <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e
Execução de Operações</a>).</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
height="33" /></span></p>
</div></th>
<th><strong>View Logs</strong> abre a tela de registro de operações, que
inclui os registros desta operação e também de quaisquer operações-filha
que tenham sido implantadas e executadas (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Logs">Registros de
Operação</a>).</th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
height="33" /></span></p>
</div></th>
<th><strong>Rename</strong> coloca o cursor sobre o nome da operação
para que você faça quantas edições forem necessárias.</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
height="33" /></span></p>
</div></th>
<th><strong>View Dependencies</strong> muda a visualização do painel de
projeto para exibir quaisquer outras partes do projeto das quais aquela
operação específica dependa (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de
Operações</a>).</th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
height="33" /></span></p>
</div></th>
<th><strong>Delete</strong> exclui permanentemente o componente (veja
  <a
  href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de Operações</a>).</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
height="33" /></span></p>
</div></th>
<th><strong>Remove</strong> tira todas as referências ao componente do
design canvas. Esta ação só é funcional quando usada numa operação que
está em um workflow (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de
Operações</a>).</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

</div>

#### <span id="ProjectPaneWorkflowsTab-share" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Atividades, *Scripts* e *Transformations*

Os menus de ações para estes componentes compartilham as mesmas ações:

<div class="table-wrap">

<table class="relative-table confluenceTable">
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header header">
<th><strong>Item do Menu</strong></th>
<th><strong>Descrição</strong></th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-edit.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-edit.png"
height="33" /></span></p>
</div></th>
<th><strong>View/Edit</strong> abre a tela de configuração do
componente. Para detalhes sobre configuração, consulte o componente
respectivo em <a
href="https://success.jitterbit.com/display/CS/Connectors">Conectores</a>, <a
href="https://success.jitterbit.com/display/CS/Scripts">Scripts</a> ou
<a
href="https://success.jitterbit.com/display/CS/Transformations">Transformações</a>.</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
height="33" /></span></p>
</div></th>
<th><strong>Cut</strong> coloca uma cópia do componente na sua área de
transferência e exclui o componente original do projeto (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso
de Componentes</a>).</th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
height="33" /></span></p>
</div></th>
<th><strong>Copy</strong> coloca uma cópia do componente na sua área de
transferência (veja <a
href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de Componentes</a>).</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
height="67" /></span></p>
</div></th>
<th><p><strong>Deploy</strong> mostra as seguintes ações:</p>
<ul>
<li>
<p><strong>Deploy</strong>: Implanta o componente e quaisquer outros
componentes dos quais ele dependa (veja <a
href="https://success.jitterbit.com/display/CS/Component+Deployment">Implantação de
Componentes</a>).</p>
</li>
<li>
<p><strong>Configurable Deploy</strong>: Abre a tela de implantação,
onde você pode selecionar componentes para implantar (veja
  <a
  href="https://success.jitterbit.com/display/CS/Component+Deployment">Implantação de Componentes</a>).</p>
</li>
</ul></th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
height="33" /></span></p>
</div></th>
<th><strong>Rename</strong> coloca o cursor sobre o nome do componente
para que você faça quantas edições forem necessárias. Você também pode
clicar duas vezes sobre um componente para entrar no modo de
renomeamento.</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
height="33" /></span></p>
</div></th>
<th><strong>View Dependencies</strong> muda a visualização do painel de
projeto para mostrar quaisquer outras partes do projeto das quais aquele
componente específico depende (veja <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção
de Componentes</a>).</th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
height="33" /></span></p>
</div></th>
<th><strong>Delete</strong> exclui permanentemente o componente (veja
  <a
  href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de Componentes</a>).</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
height="33" /></span></p>
</div></th>
<th><strong>Remove</strong> apaga referências ao componente do design
canvas (veja <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de
Componentes</a>).</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

</div>

## Reordenando Workflows e Operações

Workflows e operações podem ser reordenados quando alguém os arrasta e
solta na árvore de projeto.

### <span id="ProjectPaneWorkflowsTab-reorder-a-workflow" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Reordenando Workflows

Para reordenar workflows, arraste um workflow para outro local na árvore
de projeto:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/reorder-workflow.gif"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/reorder-workflow.gif" /></span>

Esta ação tem o efeito cascata de renumerar tanto os workflows quanto as
operações contidos dentro de cada workflow.

### <span id="ProjectPaneWorkflowsTab-reorder-an-operation" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Reordenando Operações

Para reordenar operações, arraste o nome de uma operação para outro
local dentro de ou entre workflows na árvore de projeto:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/reorder-operation.gif"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/reorder-operation.gif" /></span>

Esta ação tem o efeito cascata de renumerar as operações acima ou abaixo
dela na árvore.
