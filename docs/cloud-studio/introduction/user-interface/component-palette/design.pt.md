[//]: # (Paleta de Componentes de *Design*)
[//]: # (This is a translation of Version 5, published on October 20, 2021.)

## Introdução

A paleta de componentes de *design* é um dos dois tipos de paletas de
componentes. (O outro tipo é a [paleta de componentes de
*script*](https://success.jitterbit.com/display/CS/Script+Component+Palette)).

A paleta de componentes de *design* é mostrada ao lado do design canvas
e provê acesso à criação de conexões e atividades usando conectores na
aba **Connectivity** (Conectividade):

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_amazon-s3_activities.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_amazon-s3_activities.png" /></span>

Para consultar definições, bem como um diagrama detalhado identificando
os recursos de conectividade, veja [Conectividade](https://success.jitterbit.com/display/CS/Cloud+Studio+Terminology#CloudStudioTerminology-connectivity) em
[Terminologia do Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Terminology).

## Expandindo e Escondendo

Para esconder a paleta de componentes a fim de ter mais espaço de tela
para o design canvas, clique no ícone de esconder no canto superior
direito:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/collapse_2.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/collapse_2.png" /></span>

Para expandir a paleta de componentes, clique no ícone da aba
**Connectivity**:

<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/tab_connectivity.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/tab_connectivity.png"
height="40" /></span>

## Filtrando e Buscando

No topo da aba **Connectivity** (Conectividade), você pode filtrar e
buscar para limitar os recursos de conectividade exibidos na paleta.

### Filtrando

Para filtrar o que é mostrado na aba **Connectivity**, use o menu
dropdown **Show** (Mostrar):

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/show.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/show.png" /></span>

-   **Endpoints**: Mostra as conexões. As conexões podem ser clicadas
    para exibir os tipos de atividade de cada conexão. Para mais
    detalhes, veja [Endpoints](#DesignComponentPalette-endpoints) mais à frente nesta mesma página.

-   **Connectors** (Conectores): Mostra os conectores. Para mais
    detalhes, veja [Conectores](#DesignComponentPalette-connectors) mais à frente nesta mesma página.

-   **All** (Tudo): Mostra tanto os conectores quanto os terminais
    conforme descritos acima.

### Buscando

Para buscar dentro da aba **Connectivity** usando o filtro selecionado,
use a caixa de busca para inserir uma única ou várias palavras-chave:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_amazon_search.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_amazon_search.png" /></span>

Para limpar a busca, clique no ícone de remoção
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_10.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_10.png"
height="18" /></span>.


## <span id="DesignComponentPalette-connectors" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Conectores

Um conector provê a interface para a inserção de entradas dadas pelo
usuário, tais como credenciais para criar uma conexão. O filtro
**Connectors** (Conectores) mostra os conectores disponíveis.

Para abrir a tela de configuração de uma conexão, clique em um conector:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_amazon-s3.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_amazon-s3.png" /></span>

Para os detalhes de configuração, veja a documentação da conexão do
*endpoint* em [Conectores](https://success.jitterbit.com/display/CS/Connectors).

## Endpoints

Um *endpoint* refere-se à conexão específica e às suas atividades. O
filtro **Endpoints** mostra as conexões.

Para selecionar uma conexão e revelar seus tipos de atividade, clique na
conexão:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_amazon-s3_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_amazon-s3_connection.png" /></span>

Uma conexão selecionada é mostrada com a borda branca e roxa. Os tipos
de atividade são mostrados abaixo da conexão:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_amazon-s3_activities.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_amazon-s3_activities.png" /></span>

Para posicionar o seu cursor para renomear uma conexão, clique no nome
da conexão ou clique numa conexão já selecionada.

Para criar uma instância de uma atividade que pode ser configurada,
arraste um tipo de atividade para o design canvas ou copie o tipo de
atividade e cole-o no design canvas (veja [Criando uma Instância de
Atividade](https://success.jitterbit.com/display/CS/Component+Reuse#ComponentReuse-creating-an-activity-instance) em [Reuso de Componentes](https://success.jitterbit.com/display/CS/Component+Reuse)). Para ver mais detalhes de
configuração, veja a documentação da atividade do *endpoint* em
[Conectores](https://success.jitterbit.com/display/CS/Connectors).

O menu de ações das conexões é descrito na próxima seção, [Menus de
Ações](#DesignComponentPalette-actions-menus).


## <span id="DesignComponentPalette-actions-menus" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Menus de Ações

Para abrir um menu de ações que podem ser tomadas em uma conexão ou tipo
de atividade, faça uma das seguintes opções:

-   Clique com o botão direito do mouse sobre a conexão ou o tipo de
    atividade.

-   Paire o mouse sobre a conexão ou o tipo de atividade, e daí clique
    no ícone do menu de ações
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_24.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_24.png"
    height="18" /></span>.

### Menu de Ações de Conexão

O menu de ações de uma conexão inclui as seguintes ações:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connection_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connection_actions-menu.png" /></span>

<div class="table-wrap">

<table class="relative-table confluenceTable" style="width: 87.7076%;">
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
<th><strong>View/Edit</strong> abre a tela de configuração da conexão
(veja a documentação da conexão do <em>endpoint</em> específico em
  <a
  href="https://success.jitterbit.com/display/CS/Connectors">Conectores</a>).</th>
</tr>
<tr class="header header">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/test.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/test.png"
height="33" /></span></p>
</div></th>
<th><strong>Test</strong> testa a conexão. Esta ação é o mesmo que
clicar no botão <strong>Test</strong> disponível numa tela de
configuração de conexão (veja a documentação da conexão do
<em>endpoint</em> específico em <a
href="https://success.jitterbit.com/display/CS/Connectors">Conectores</a>).</th>
</tr>
<tr class="odd odd">
<th class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
height="33" /></span></p>
</div></th>
<th><strong>Duplicate</strong> cria uma conexão nova e não-referenciada
usando as mesmas configurações que a conexão original (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de
Componentes</a>).</th>
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
<th><strong>Delete</strong> exclui permanentemente a conexão (veja
  <a
  href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de Componentes</a>).</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

</div>

### <span id="DesignComponentPalette-activity-type-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Menu de Ações de Tipo de Atividade

O menu de ações de um tipo de atividade inclui a seguinte ação:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/activity-type_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/activity-type_actions-menu.png" /></span>

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
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
height="33" /></span></p>
</div></th>
<th><strong>Copy</strong> coloca uma cópia do tipo de atividade na sua
área de transferência para ser usada para criar uma instância de
atividade (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de Componentes</a>).</th>
</tr>
</thead>
<tbody>
</tbody>
</table>

</div>
