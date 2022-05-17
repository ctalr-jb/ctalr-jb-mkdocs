[//]: # (Informações Básicas sobre Conectores)
[//]: # (This is a translation of Version 13, published on October 20, 2021.)


## Introdução

Ao trabalhar com conectores, é importante que você entenda as seguintes informações básicas:

-   [**Recursos de Conectividade**](https://success.jitterbit.com/display/CS/Connector+Basics?showLanguage=pt_BR#ConnectorBasics-connectivity-resources): Terminologia e definições de vários recursos de conectividade, incluindo conectores, conexões, atividades e *endpoints*.

-   [**Testando uma Conexão**](https://success.jitterbit.com/display/CS/Connector+Basics?showLanguage=pt_BR#ConnectorBasics-connection-testing): Como testar uma conexão para verificar a conectividade do *endpoint*.

-   [**Atividades como Etapas de Operação**](https://success.jitterbit.com/display/CS/Connector+Basics?showLanguage=pt_BR#ConnectorBasics-activity): Como adicionar uma atividade como etapa de uma operação com o objetivo de usá-la como fonte ou alvo de dados.

-   [**Menus de Ações**](https://success.jitterbit.com/display/CS/Connector+Basics?showLanguage=pt_BR#ConnectorBasics-actions-menus): Como acessar um menu de ações que podem ser tomadas com os conectores, tipos de atividades e instâncias de atividades.


## Recursos de Conectividade

Os recursos de conectividade são acessados a princípio dentro da aba **Connectivity** (Conectividade) da [paleta de componentes de *design*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR):

-   **Connectors** (Conectores): Um conector disponibiliza a interface para a inserção de entradas fornecidas pelo usuário tais como credenciais para criar uma conexão. O filtro **Connectors** mostra os conectores disponíveis. Você também pode criar [conectores customizados](https://success.jitterbit.com/display/CS/Custom+Connector?showLanguage=pt_BR).

-   **Connections** (Conexões): Uma conexão é um componente criado a partir de um conector e que fornece acesso a um recurso de dados. O filtro **Endpoints** mostra as conexões disponíveis.

-   **Activities** (Atividades): Uma atividade é um componente que é criado a partir de uma conexão e que é configurado para interagir com um *endpoint*. O filtro **Endpoint** mostra as conexões, que podem ser clicadas para revelar os tipos de atividade. Os tipos de atividade são usados para criar uma instância de uma atividade em um projeto. As instâncias de atividades podem agir como fontes (fornecendo dados) ou como alvos (recebendo dados).

-   **Endpoints**: Um *endpoint* refere-se a uma conexão específica e suas atividades.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/connectivity-terms_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>


## Testando uma Conexão

Uma vez que uma conexão é criada, você pode verificar a conectividade do *endpoint* testando-a.

Para testar uma conexão, clique no botão **Test** (Testar) dentro das configurações da conexão. Caso a conexão seja bem-sucedida, uma mensagem que diz *Connection Success* será exibida. Caso a conexão não seja bem-sucedida, detalhes sobre o(s) erro(s) será(ão) fornecido(s).

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/connector/temporary-storage_connection_test_annotated.png" class="confluence-embedded-image confluence-external-resource" /></span>

Você também pode testar uma conexão a partir do painel de projeto usando o menu de ações de uma conexão (veja [Menu de Ações de Conexão](https://success.jitterbit.com/display/CS/Connector+Basics?showLanguage=pt_BR#ConnectorBasics-connection-actions-menu), mais abaixo).


## Atividades como Etapas de Operação

As operações são formadas quando se arranjam atividades, [*scripts*](https://success.jitterbit.com/display/CS/Scripts?showLanguage=pt_BR) e [*transformations*](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR) dentro de uma operação no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR).

Uma vez que uma conexão é estabelecida, os tipos de atividade associados à conexão tornam-se disponíveis para colocação dentro da operação no design canvas. Quando um tipo de atividade é posto no design canvas, isto cria uma instância de uma atividade que pode então ser configurada para uso como fonte (para fornecer dados) ou como alvo (para receber dados) em uma operação.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/create-activity-instance.gif" class="confluence-embedded-image confluence-external-resource" /></span>

Mais informações sobre este processo são descritas na seção [Adicionando Etapas a uma Operação](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR#OperationCreationandConfiguration-adding-steps-to-an-operation) no artigo [Criação e Configuração de Operações](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR).


## Menus de Ações

Conexões, tipos de atividades e instâncias de atividades têm um menu a partir do qual você pode acessar ações relevantes a estes itens.

### Menu de Ações de Conexão

Depois de criar uma conexão, os menus de ações dessa conexão ficam disponíveis nos seguintes locais:

-   A aba **Components** do painel de projeto (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) no artigo [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

-   A aba **Connectivity** da paleta de componentes de *design* (veja a seção [Menu de Ações de Conexão](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR#DesignComponentPalette-connection-actions-menu) no artigo [Paleta de Componentes de *Design*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR)).

As seguintes ações de menu estão disponíveis em todos os menus de ações de conexão:

<table class="relative-table confluenceTable" style="width: 87.7076%;">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
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
<p><em>Ver/Editar</em></p>
</div></td>
<td class="confluenceTd"><strong>View/Edit</strong> abre a tela de configuração da conexão
(veja a documentação da conexão do <em>endpoint</em> específico em
  <a
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
<p><em>Testar</em></p>
</div></td>
<td class="confluenceTd"><strong>Test</strong> testa a conexão. Esta ação é o mesmo que
clicar no botão <strong>Test</strong> disponível numa tela de
configuração de conexão (veja a documentação da conexão do
<em>endpoint</em> específico em <a
href="https://success.jitterbit.com/display/CS/Connectors">Conectores</a>).</td>
</tr>
</tbody>
</table>

As seguintes ações de menu estão disponíveis apenas na aba **Connectivity** da paleta de componentes de *design*:

<table class="relative-table confluenceTable" style="width: 87.7076%;">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
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
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
height="33" /></span></p>
<p><em>Duplicar</em></p>
</div></td>
<td class="confluenceTd"><strong>Duplicate</strong> cria uma conexão nova e não-referenciada
usando as mesmas configurações que a conexão original (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de
Componentes</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
height="33" /></span></p>
<p><em>Deletar</em></p>
</div></td>
<td class="confluenceTd"><strong>Delete</strong> exclui permanentemente a conexão (veja
  <a
  href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de Componentes</a>).</td>
</tr>
</tbody>
</table>

### Menu de Ações de Tipo de Atividade

O menu de ações de cada tipo de atividade associado a uma conexão está disponível apenas na aba **Connectivity** (Conectividade) da paleta de componentes de *design* (veja a seção [Menu de Ações de Tipo de Atividade](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR#DesignComponentPalette-activity-type-actions-menu) no artigo [Paleta de Componentes de *Design*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR)). A seguinte ação de menu está disponível:

<table class="relative-table confluenceTable">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
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
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
height="33" /></span></p>
<p><em>Copiar</em></p>
</div></td>
<td class="confluenceTd"><strong>Copy</strong> coloca uma cópia do tipo de atividade na sua
área de transferência para ser usada para criar uma instância de
atividade (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de Componentes</a>).</td>
</tr>
</tbody>
</table>

### Menu de Ações de Atividade

Depois que uma instância de atividade foi criada, as ações de menu de tal atividade ficam acessíveis nos seguintes locais:

-   A aba **Workflows** do painel de projeto (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) no artigo [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

-   A aba **Components** do painel de projeto (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) no artigo [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

-   O design canvas (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) no artigo [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

<table class="relative-table confluenceTable">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
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
height="33" /></span></p>
<p><em>Visualizar/Editar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>View/Edit</strong> (Visualizar/Editar) abre a tela de configuração para que você configure a atividade. Para mais detalhes, veja a documentação de cada conector em <a href="https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR">Conectores</a>.</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Recortar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Cut</strong> (Recortar) coloca uma cópia da atividade na sua área de transferência e exclui a atividade original do projeto (veja o artigo <a href="https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR">Reuso de Componentes</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Copiar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Copy</strong> (Copiar) coloca uma cópia da atividade na sua área de transferência (veja o artigo <a href="https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR">Reuso de Componentes</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
height="67" /></span></p>
<p><em>Implantar</em></p>
<p><em>&gt; Implantação</em></p>
<p><em>&gt; Implantação Configurável</em></p>
</div></td>
<td class="confluenceTd"><p>O botão <strong>Deploy</strong> (Implantar) mostra as seguintes ações de menu:</p>
<ul>
<li><blockquote>
<p><strong>Deploy</strong> (Implantação): Implanta a atividade e todos os componentes dos quais ela depende (veja o artigo <a href="https://success.jitterbit.com/display/CS/Component+Deployment?showLanguage=pt_BR">Implantação de Componentes</a>).</p>
</blockquote></li>
<li><blockquote>
<p><strong>Configurable Deploy</strong> (Implantação Configurável): Abre a tela de implantação, onde você pode selecionar componentes para implantar (veja o artigo <a href="https://success.jitterbit.com/display/CS/Component+Deployment?showLanguage=pt_BR">Implantação de Componentes</a>).</p>
</blockquote></li>
</ul></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Remover</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Remove</strong> (Remover) remove referências à atividade do design canvas (veja o artigo <a href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR">Dependências, Exclusão e Remoção de Componentes</a>).</td>
</tr>
</tbody>
</table>

As seguintes ações estão disponíveis apenas nos menus de ações de atividade acessíveis nas abas **Workflows** e **Components** do painel de projeto:

Os menus de ações destes componentes compartilham muitas das mesmas ações:

<table class="relative-table confluenceTable">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
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
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Renomear</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Rename</strong> (Renomear) coloca o cursor sobre o nome da atividade para que você faça edições conforme for necessário.</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Visualizar Dependências</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>View Dependencies</strong> (Visualizar Dependências) altera a visualização no painel de projeto para exibir quaisquer outras partes do projeto dos quais aquela atividade específica depende (veja o artigo <a href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR">Dependências, Exclusão e Remoção de Componentes</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Deletar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Delete</strong> (Deletar) exclui permanentemente a atividade (veja o artigo <a href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR">Dependências, Exclusão e Remoção de Componentes</a>).</td>
</tr>
</tbody>
</table>

As seguintes ações estão disponíveis apenas nos menus de ações de atividade acessíveis na aba **Components** do painel de projeto:

Os menus de ações desses componentes compartilham muitas das mesmas ações:

<table class="relative-table confluenceTable">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
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
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png">https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Duplicar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Duplicate</strong> (Duplicar) cria uma atividade nova e não-referenciada usando as mesmas configurações da atividade original (veja o artigo <a href="https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR">Reuso de Componentes</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/add-to-group.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Adicionar ao Grupo</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Add to Group</strong> (Adicionar ao Grupo) abre uma caixa de diálogo para criar um novo grupo customizado ou para adicionar a atividade a um grupo existente (veja o artigo <a href="https://success.jitterbit.com/display/CS/Component+Groups?showLanguage=pt_BR">Grupos de Componentes</a>).</td>
</tr>
</tbody>
</table>
