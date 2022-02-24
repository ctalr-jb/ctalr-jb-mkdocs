[//]: # (Aba Components do Painel de Projeto)
[//]: # (This is a translation of Version 7, published on October 20, 2021.)

## Introdução

A aba **Components** do painel de projeto é uma das duas abas acessíveis
no [painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane?showLanguage=pt_BR). (A outra é a [aba **Workflows**](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

A aba **Components** exibe todos os componentes no projeto aberto
agrupados por categoria de componente.

## Categorias de Componente

Todas estas categorias de alto nível são mostradas, independentemente de
terem ou não componentes:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/categories.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/categories.png" /></span>

-   **Custom Groups** (Grupos Customizados): Grupos customizados são uma
    ferramenta organizacional para ajudar a organizar componentes de
    projeto (veja [Grupos de Componentes](https://success.jitterbit.com/display/CS/Component+Groups?showLanguage=pt_BR)). Depois de criar um
    grupo customizado, o nome dele, definido pelo usuário, é mostrado
    como subcategoria embaixo de **Custom Groups**. Embaixo de cada
    grupo customizado, quaisquer componentes contidos dentro do grupo
    são listados.

-   **Files** (Arquivos): Todos os schemas de arquivos são listados
    (veja [Schemas](https://success.jitterbit.com/display/CS/Schemas?showLanguage=pt_BR)).

-   **Endpoints**: Um *endpoint* refere-se a uma conexão específica e às
    suas atividades, criadas usando conectores (veja
    [Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR)).

    Depois de criar uma instância de atividade associada a uma conexão, o
    tipo de terminal é exibido como subcategoria embaixo de **Endpoints**,
    seguido pelo número de *endpoints* daquele tipo entre parênteses. Por
    exemplo, **Database Endpoints (2)** (isto é, há dois *Endpoints* de
    Bancos de Dados). As conexões não são mostradas ou contadas a menos
    que pelo menos uma atividade tenha sido criada a partir delas.

    O nome de conexão definido pelo usuário é mostrado como uma
    subcategoria adicional embaixo do tipo de *endpoint*, seguido pelo
    número de instâncias de atividade que foram criadas a partir de cada
    conexão entre parênteses. Por exemplo, **Oracle (4)**.

    Embaixo de cada conexão, o nome de cada instância de atividade é
    precedido por colchetes contendo o tipo de interação com o recurso de
    dados específico daquele tipo de atividade, em inglês. Na mesma linha,
    a seguir vem o nome da atividade, definido pelo usuário. Por exemplo,
    **\[Database_insert\] Insert Customers**.

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/project-pane/components/endpoints.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/endpoints.png" /></span>

-   **Operations** (Operações): Todas as operações são listadas (veja
    [Operações](https://success.jitterbit.com/display/CS/Operations?showLanguage=pt_BR)).

-   **Scripts**: Todos os *scripts* dos componentes do projeto são
    listados (veja [Scripts](https://success.jitterbit.com/display/CS/Scripts?showLanguage=pt_BR)). *Scripts* criados em campos alvo
    ou em nós de uma transformação não são componentes de projeto, já
    que são considerados parte do componente da *transformation*.

-   **Transformations**: Todas as *transformations* são listadas (veja
    [Transformations](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR)).

-   **Project Variables** (Variáveis de Projeto): Todas as variáveis de
    projeto são listadas (veja [Variáveis de Projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR)).

-   **Global Variables** (Variáveis Globais): Todas as variáveis globais
    são listadas (veja [Variáveis Globais](https://success.jitterbit.com/display/CS/Global+Variables?showLanguage=pt_BR)).

-   **E-mails**: Todas as notificações de e-mail são listadas (veja
    [Notificações de E-mail](https://success.jitterbit.com/display/CS/Email+Notifications?showLanguage=pt_BR)).

-   **Schedules** (Agendas): Todas as agendas de operação são listadas
    (veja [Agendas de Operação](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR)).


## Buscando e Filtrando

No topo da aba **Components**, você pode buscar e filtrar componentes
para limitar os que serão exibidos nesta aba.

### Buscando

Para buscar dentro da aba **Components**, use a caixa de busca para
inserir uma única palavra-chave ou série de palavras-chave. As
categorias são automaticamente expandidas para mostrar os componentes
nos quais as palavras-chave aparecem. Elas ficam roxas e em negrito
dentro do nome do componente.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/search.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/search.png" /></span>

Para limpar a busca, clique no ícone de remoção
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_11.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_11.png"
height="18" /></span>.

### <span id="ProjectPaneComponentsTab-orphaned" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Filtrando

Para filtrar por componente de projeto, use o menu *dropdown* que sai do
ícone de filtro
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/filter.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/filter.png"
height="16" /></span> para
selecionar uma das seguintes opções de filtro:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/filter.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/filter.png" /></span>

-   **All** (Todos): Mostra todos os componentes no projeto atual.

-   **Undeployed** (Não-implantados): Mostra apenas os componentes no
    projeto atual que não foram implantados ainda ou que foram
    modificados depois de terem sido implantados.

-   **Orphaned** (Órfãos): Mostra apenas os componentes que não são
    referenciados em nenhum outro componente ou workflow no projeto
    atual. Componentes órfãos são mostrados com um ícone de
    não-referenciado (uma corrente quebrada)
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
    height="14" /></span>
    independentemente de o filtro ter sido selecionado. Componentes
    órfãos também são chamados de componentes não-referenciados ou
    não-usados.

    <div
    class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
    hasbody="true" macro-name="info">

    <span
    class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **NOTA:** A classificação órfão é baseada no projeto conforme ele
    existe atualmente no *designer* de projeto do Cloud Studio e não leva
    em consideração caso algum componente tenha sido implantado no
    Harmony.

    </div>

    </div>

-   **Invalid** (Inválidos): Mostra apenas os componentes no projeto
    atual que são inválidos. Componentes inválidos não podem ser
    implantados. Os critérios de validação são descritos em
    [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR). Este filtro pode ser útil para
    identificar componentes inválidos que também estão órfãos caso
    você queira deletar os componentes não-referenciados em vez de
    resolver os erros.

Quando um filtro estiver aplicado, o nome do filtro é exibido abaixo do
ícone de filtro:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/filter_label.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/filter_label.png" /></span>

Para voltar à visualização **All** (Todos), clique no ícone de remoção
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_12.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_12.png"
height="14" /></span>
ao lado do nome do filtro.

## Expandindo e Selecionando Itens

Para expandir ou reduzir todas as categorias de uma vez, clique duas
vezes no nome da categoria ou nos triângulos de revelação
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/down-arrow_6.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/down-arrow_6.png"
height="9" /></span> <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/right-arrow_5.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/right-arrow_5.png"
height="12" /></span> ao lado da
categoria. Para expandir ou reduzir categorias individuais, use um único
clique.

À medida que você for trabalhando nos projetos, o Cloud Studio se lembra
dos estados de exibição que um dado usuário usou por último em qualquer
dado projeto, incluindo se as categorias no painel de projeto estavam
expandidas ou reduzidas.

Quando uma categoria é expandida, clique num componente dentro da
categoria para selecioná-lo. Um componente selecionado é exibido com um
fundo cinza:

<span
class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/activity_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/activity_selected.png" /></span>

Se o componente também for referenciado no design canvas, este será
exibido até a primeira instância dele.

As categorias em si não podem ser selecionadas.

## Vendo Erros de Validação e Referências

Indicações visuais da validade de componentes e o número de outros
componentes que fazem referência a um componente são exibidos conforme a
descrição abaixo.

### Erros de Validação

Quando a opção **Highlight Invalid Items** (Destacar Itens Inválidos) no
design canvas estiver sendo usada ou quando você estiver com o filtro
**Invalid** (Inválidos) ativo, um ícone de erro
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/error.png"
height="16" /></span>
é mostrado ao lado de componentes inválidos, cujos nomes aparecerão em
itálico e na cor vermelha:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/transformations_invalid.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/transformations_invalid.png" /></span>

Você pode ver os erros de validação associados a componentes inválidos
conforme descritos em [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity) e [Validade de
Operações](https://success.jitterbit.com/display/CS/Operation+Validity).

### Referências

Um componente pode ser referenciado por outros componentes ou workflows
ao longo de todo o projeto.

O número de componentes que fazem referência àquele componente é
indicado pela presença ou ausência de ícones à esquerda do nome do
componente:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_references.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_references.png" /></span>

-   Um componente que não é referenciado por nenhum outro componente ou
    workflow no projeto é conhecido como componente órfão, e é
    mostrado com um ícone de não-referenciado (corrente quebrada)
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
    height="14" /></span>.

-   Um componente que é referenciado por apenas um outro componente ou
    workflow é mostrado sem nenhum indicador visual.

-   Um componente que é referenciado por vários componentes - ou uma
    operação que é referenciada por componente(s) e um workflow, ou
    por vários componentes - tem o número de componentes que o
    referenciam mostrado dentro de um círculo
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/reference-count.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/reference-count.png"
    height="18" /></span>.

Maiores detalhes são dados em [Reuso de Componentes](https://success.jitterbit.com/display/CS/Component+Reuse) e [Reuso de
Operações](https://success.jitterbit.com/display/CS/Operation+Reuse).


## Menus de Ações

Para abrir um menu das ações que podem ser feitas em cada categoria de
componentes ou em cada componente, faça uma das seguintes coisas:

-   Clique com o botão direito do mouse sobre a categoria ou o
    componente.

-   Paire o mouse sobre a categoria ou o componente, daí clique no ícone
    do menu de ações
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_2.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_2.png"
    height="8" /></span>.

As ações disponíveis em cada menu dependem do contexto e variam de
acordo com a categoria ou o componente.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA**: A categoria **Custom Groups** (Grupos Customizados) e os
componentes mostrados ali dentro são discutidos em [Grupos de
Componentes](https://success.jitterbit.com/display/CS/Component+Groups).

</div>

</div>

### <span id="ProjectPaneComponentsTab-category-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Menu de Ações de Categoria

Algumas ações estão disponíveis apenas em certas categorias, como
detalhado abaixo. As imagens abaixo mostram os menus de ações para a
categoria **Scripts** (primeira imagem) e para a categoria **Endpoints**
(segunda imagem).

**Menu de Ações da Categoria Scripts**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_category-actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_category-actions-menu.png" /></span>

**Menu de Ações da Categoria Endpoints**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/endpoints_category-actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/endpoints_category-actions-menu.png" /></span>

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="header header">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><strong>Item do Menu</strong></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><strong>Descrição</strong></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/create-new.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/create-new.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Create New</strong> cria um novo componente
não-referenciado do tipo respectivo na categoria.</p>
<p>Esta ação está disponível nas categorias <strong>Scripts</strong>,
<strong>Transformations</strong>, <strong>Project Variables</strong>
(Variáveis de Projeto), <strong>E-mails</strong> e
<strong>Schedules</strong> (Agendas).</p>
<p>Ao criar o componente, a tela de configuração de componente abre para
você poder configurá-lo.</p></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/paste-script.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/paste-script.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Paste <em>Component Type</em></strong> (Colar <em>Tipo de
Componente)</em>: Coloca o componente recortado ou copiado que está na
sua área de transferência, criando assim uma duplicata do componente
como um novo componente não-referenciado (veja <a
href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de
Componentes</a>).</p>
<p>Esta ação está disponível em <strong>Files</strong> (Arquivos),
<strong>Endpoints</strong>, <strong>Operations</strong> (Operações),
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong> (Variáveis de Projeto),
<strong>E-mails</strong> e <strong>Schedules</strong> (Agendas). Ela é
habilitada apenas quando você tem um componente do tipo correspondente
na sua área de transferência.</p>
<p>Quando você cria a duplicata, o seu cursor é posicionado sobre o nome
do componente para a escolha do novo nome.</p></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete-unused.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete-unused.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Delete unused</strong> exclui permanentemente componentes
daquela categoria que não são referenciados por nenhum outro componente
no projeto atual (veja <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de
Componentes</a>).</p>
<p>Esta ação está disponível em <strong>Files</strong> (Arquivos),
<strong>Endpoints</strong>, <strong>Operations</strong> (Operações),
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong> (Variáveis de Projeto),
<strong>Global Variables</strong> (Variáveis Globais),
<strong>E-mails</strong> e <strong>Schedules</strong> (Agendas). Ela
está habilitada somente quando a categoria contém componentes
não-referenciados, exibidos com um ícone de não-referenciado (uma
corrente quebrada) <span><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
height="14" /></span></span><span>.</p></td>
</tr>
</tbody>
</table>

</div>

### <span id="ProjectPaneComponentsTab-component-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Menu de Ações de Componente

Algumas ações estão disponíveis somente em certos tipos de componentes,
conforme detalhado nas subseções abaixo:

-   **[Operations](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-operations)** (Operações): O menu de ações de operações
    (mostrado na primeira imagem) tem itens únicos, tais como
    **Settings** (Configurações), **Run** (Executar) e **View Logs**
    (Ver Registros), assim como submenus diferentes para **Duplicar**
    e **Implantar**. Ele também inclui ações comuns como **Cut**
    (Recortar), **Copy** (Copiar), **Rename** (Renomear), **View
    Dependencies** (Ver Dependências), **Add to Group** (Adicionar ao
    Grupo), **Delete** (Deletar) e **Remove** (Remover).

-   **[Files, Activities, Scripts, Transformations, Project Variables,
    Global Variables, Emails e Schedules](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-share)** (Arquivos, Atividades,
    *Scripts*, *Transformations*, Variáveis de Projeto, Variáveis
    Globais, E-mails e Agendas): Os menus de ações de todos esses
    componentes compartilham muitas das mesmas ações, como
    **View/Edit** (Ver/Editar), **Cut** (Recortar), **Copy** (Copiar),
    **Duplicate** (Duplicar), **Deploy** (Implantar), **Rename**
    (Renomear), **View Dependencies** (Ver Dependências), **Add to
    group** (Adicionar ao Grupo), **Delete** (Deletar) e **Remove**
    (Remover). O menu de ações de um *script* (mostrado na segunda
    imagem) mostra todas as ações disponíveis. Algumas dessas ações
    não estão disponíveis em todos os componentes, conforme descrito
    nesta seção.

-   **[Connections](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-connections)** (Conexões): O menu de ações de uma conexão
    (mostrado na terceira imagem) tem as ações **View/Edit**
    (Ver/Editar) e **Test** (Testar).

**Menu de ações de operação**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/operations_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/operations_actions-menu.png" /></span>

**Menu de ações de *script***

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_actions-menu.png" /></span>

**Menu de ações de conexão**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/connection_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/connection_actions-menu.png" /></span>

#### <span id="ProjectPaneComponentsTab-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operations

Os seguintes itens estão disponíveis no menu de ações de uma operação:

<div class="table-wrap">

<table class="wrapped confluenceTable">
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="header header">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><strong>Item do menu</strong></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><strong>Descrição</strong></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><strong><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/settings.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/settings.png"
height="33" /></span></strong></p>
</div></td>
<td class="confluenceTd"><p><strong>Settings</strong> abre as configurações de operação,
contendo três abas:</p>
<ul>
<li>
<p><strong>Schedules</strong> (Agendas): Criar e aplicar agendas para
operações que executam automaticamente (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Schedules">Agendas de
Operação</a>).</p>
</li>
<li>
<p><strong>Actions</strong> (Ações): Configurar ações que devem ser
tomadas em caso de sucesso ou falha da operação (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Actions">Ações de
Operação</a>).</p>
</li>
<li>
<p><strong>Options</strong> (Opções): Definir opções tais como quanto
tempo a operação tem para executar, o que deve ser escrito no registro,
o prazo para registrar, quando a operação deverá executar, ou caso a
fragmentação de dados (<em>chunking</em>) deverá ser usada (veja
  <a
  href="https://success.jitterbit.com/display/CS/Operation+Options">Opções de Operação</a>).</p>
</li>
</ul></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><strong><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
height="33" /></span></strong></p>
</div></td>
<td class="confluenceTd"><strong>Cut</strong> coloca uma cópia da operação na sua área de
transferência e deleta a operação original do projeto (veja <a href="https://success.jitterbit.com/display/CS/Operation+Reuse">Reuso de
Operações</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Copy</strong> coloca uma cópia da operação na sua área de
transferência (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Reuse">Reuso de Operações</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu.png"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu_with-step-references_with-step-copies.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu_with-step-references_with-step-copies.png"
height="67" /></span></p>
<p><br />
</p>
</div></td>
<td class="confluenceTd"><p><strong>Duplicate</strong> mostra os seguintes menus de ações
(veja <a href="https://success.jitterbit.com/display/CS/Operation+Reuse">Reuso de Operações</a>):</p>
<ul>
<li>
<p><strong>With Step References</strong>: Duplica apenas a operação. A
duplicata contém referências a cada um dos passos da operação
original.</p>
</li>
<li>
<p><strong>With Step Copies</strong>: Duplica a operação e os
componentes referenciados como passos de operação. Novos componentes são
criados para cada passo de operação e são referenciados pela
duplicata.</p>
</li>
</ul></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
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
</div></td>
<td class="confluenceTd"><p><strong>Deploy</strong> mostra os seguintes menus de ações:</p>
<ul>
<li>
<p><strong>Deploy</strong>: Implanta a operação e quaisquer componentes
dos quais ela dependa (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e Execução de
Operações</a>).</p>
</li>
<li>
<p><strong>Deploy and Run</strong>: Implanta e executa a operação, bem
como quaisquer operações conectadas que estiverem abaixo dela na cadeia
(veja <a
href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e Execução de Operações</a>).</p>
</li>
<li>
<p><strong>Configurable Deploy</strong>: Abre a tela de implantação,
onde você pode selecionar componentes para implantar (veja
  <a
  href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e Execução de Operações</a>).</p>
</li>
</ul></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/run.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/run.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Run</strong> executa uma operação já implantada e quaisquer
operações conectadas abaixo dela na cadeia (veja <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e
Execução de Operações</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>View Logs</strong> abre a tela de registros de operação, que
inclui registros desta operação e de quaisquer operações-filha que já
tenham sido implantadas e executadas (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Logs">Registros de
Operações</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Rename</strong> coloca o seu cursor sobre o nome da operação
para que você possa fazer quantas edições forem necessárias.</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>View Dependencies</strong> muda a visualização do painel de
projeto para mostrar quaisquer outras partes do projeto das quais aquela
operação específica dependa (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de
Operações</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/add-to-group.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/add-to-group.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Add to group</strong> abre um diálogo para criar um novo
grupo customizado ou para adicionar o componente a um grupo existente
(veja <a href="https://success.jitterbit.com/display/CS/Component+Groups">Grupos de Componentes</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Delete</strong> exclui permanentemente o componente (veja
  <a
  href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de Operações</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Remove</strong> apaga referências ao componente do design
canvas. Esta ação só é funcional quando usada numa operação que está em
um workflow (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de
Operações</a>).</td>
</tr>
</tbody>
</table>

</div>

#### <span id="ProjectPaneComponentsTab-share" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Files, Activities, Scripts, Transformations, Project Variables, Global Variables, Emails, e Schedules

Os menus de ações desses componentes compartilham muitas das mesmas
ações:

<div class="table-wrap">

<table class="relative-table wrapped confluenceTable"
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="header header">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><strong>Item do Menu</strong></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><strong>Descrição</strong></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-edit.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-edit.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>View/Edit</strong> abre a tela de configuração de
atividades listadas numa subcategoria de tipo <em>endpoint</em> sob
<strong>Endpoints</strong>, e componentes nas categorias
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong> (Variáveis de Projeto),
<strong>E-mails</strong> e <strong>Schedules</strong> (Agendas). (Esta
ação não está disponível para componentes nas categorias
<strong>Files</strong> [Arquivos] ou <strong>Global Variables</strong>
[Variáveis Globais].)</p>
<p>A tela de configuração de componente também pode ser aberta com um
clique duplo sobre o nome do componente.</p>
<p>Para mais detalhes sobre a configuração, consulte o componente
respectivo em <a href="https://success.jitterbit.com/display/CS/Connectors">Conectores</a>, <em><a
href="https://success.jitterbit.com/display/CS/Scripts">Scripts</a></em>, <a
href="https://success.jitterbit.com/display/CS/Project+Variables">Variáveis
de Projeto</a>, <em><a
href="https://success.jitterbit.com/display/CS/Transformations">Transformations</a></em>, <a
href="https://success.jitterbit.com/display/CS/Notifications">Notificações</a> ou
<a
href="https://success.jitterbit.com/display/CS/Operation+Schedules">Agendas de Operação</a>.</p></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Cut</strong> coloca uma cópia do componente na sua área
de transferência e apaga o componente original do projeto (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso
de Componentes</a>).</p>
<p>Esta ação está disponível para atividades listadas numa subcategoria
de tipo <em>endpoint</em> sob <strong>Endpoints</strong>, e para
componentes nas categorias <strong>Files</strong> (Arquivos),
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong> (Variáveis de Projeto),
<strong>E-mails</strong> e <strong>Schedules</strong> (Agendas). (Esta
ação não está disponível na categoria <strong>Global Variables</strong>
[Variáveis Globais].)</p></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Copy</strong> coloca uma cópia do componente na sua área
de transferência (veja <a
href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de Componentes</a>).</p>
<p>Esta ação está disponível para atividades listadas numa subcategoria
de tipo <em>endpoint</em> sob <strong>Endpoints,</strong> e para
componentes nas categorias <strong>Files</strong> (Arquivos),
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong> (Variáveis de Projeto),
<strong>E-mails</strong> e <strong>Schedules</strong> (Agendas). (Esta
ação não está disponível na categoria <strong>Global Variables</strong>
[Variáveis Globais].)</p></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Duplicate</strong> cria um novo componente
não-referenciado usando a mesma configuração que o componente original
(veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de Componentes</a>).</p>
<p>Esta ação está disponível para atividades listadas numa subcategoria
de tipo <em>endpoint</em> sob <strong>Endpoints</strong>, e para
componentes nas categorias <strong>Scripts</strong>, <strong>Project
Variables</strong> (Variáveis de Projeto), <strong>E-mails</strong> e
<strong>Schedules</strong> (Agendas). (Esta ação não está disponível nas
categorias <strong>Files</strong> [Arquivos],
<strong>Transformations</strong> ou <strong>Global Variables</strong>
[Variáveis Globais].)</p></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
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
</div></td>
<td class="confluenceTd"><p><strong>Deploy</strong> mostra as seguintes ações de menu:</p>
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
</ul></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Rename</strong> coloca o cursor sobre o nome do
componente para que você faça quantas edições forem necessárias.</p>
<p>Esta ação está disponível para atividades listadas numa subcategoria
de tipo <em>endpoint</em> sob <strong>Endpoints</strong>, e para
componentes nas categorias <strong>Files</strong> (Arquivos),
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong> (Variáveis de Projeto),
<strong>E-mails</strong> e <strong>Schedules</strong> (Agendas). (Esta
ação não está disponível na categoria <strong>Global Variables</strong>
[Variáveis Globais].)</p></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>View Dependencies</strong> muda a visualização do painel de
projeto para exibir quaisquer outras partes do projeto das quais aquele
componente específico dependa (veja <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção
de Componentes</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/add-to-group.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/add-to-group.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Add to group</strong> abre um diálogo para criar um novo
grupo customizado ou para adicionar o componente a um grupo existente
(veja <a href="https://success.jitterbit.com/display/CS/Component+Groups">Grupos de Componentes</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Delete</strong> exclui permanentemente o componente (veja
  <a
  href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de Componentes</a>).</p>
<p>Esta ação está disponível para atividades listadas numa subcategoria
de tipo <em>endpoint</em> sob <strong>Endpoints</strong>, e para
componentes nas categorias <strong>Files</strong> (Arquivos),
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong> (Variáveis de Projeto),
<strong>E-mails</strong> e <strong>Schedules</strong> (Agendas). (Esta
ação não está disponível na categoria <strong>Global Variables</strong>
[Variáveis Globais].)</p></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Remove</strong> apaga referências ao componente do design
canvas.</p>
<p>Esta ação está disponível para atividades listadas numa subcategoria
de tipo <em>endpoint</em> sob <strong>Endpoints</strong>, e para
componentes nas categorias <strong>Scripts</strong>,
<strong>Transformations</strong>, <strong>Project Variables</strong>
(Variáveis de Projeto), <strong>E-mails</strong> e
<strong>Schedules</strong> (Agendas). (Esta ação não está disponível
para componentes nas categorias <strong>Files</strong> [Arquivos] ou
<strong>Global Variables</strong> [Variáveis Globais].) Ela só é
funcional quando usada numa atividade, <em>transformation</em> ou
<em>script</em> que é referenciada como etapa numa operação, ou quando
usada numa notificação de e-mail que é configurada com uma ação de
operação (veja <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências de Componentes, Exclusão e
Remoção</a>).</p></td>
</tr>
</tbody>
</table>

</div>

#### <span id="ProjectPaneComponentsTab-connections" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Conexões

Conexões são listadas numa subcategoria do tipo *endpoint* sob
**Endpoints**. O menu de ações para uma conexão tem as ações
**View/Edit** (Ver/Editar) e **Test** (Testar):

<div class="table-wrap">

<table class="relative-table wrapped confluenceTable"
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="header header">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><strong>Item do Menu</strong></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><strong>Descrição</strong></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-edit.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-edit.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>View/Edit</strong> abre a tela de configuração daquela
conexão (veja a documentação da conexão do <em>endpoint</em> específico
em <a
href="https://success.jitterbit.com/display/CS/Connectors">Conectores</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/test.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/test.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Test</strong> testa a conexão. Esta ação é o mesmo que
clicar no botão <strong>Testar</strong> disponível numa tela de
configuração de conexão (veja a documentação da conexão do
<em>endpoint</em> específico em <a
href="https://success.jitterbit.com/display/CS/Connectors">Conectores</a>).</td>
</tr>
</tbody>
</table>

</div>
