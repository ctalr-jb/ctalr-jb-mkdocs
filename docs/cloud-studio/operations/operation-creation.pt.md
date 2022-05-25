[//]: # (Criação e Configuração de Operações)
[//]: # (This is a translation of Version 62, published on March 7, 2022.)


## Introdução

Uma operação é a menor unidade dentro de um workflow que é executada independentemente em um agente e registrada pelo Harmony. As operações são usadas para definir o que um processo de integração deve fazer e quando deve fazê-lo.

As operações são compostas de uma combinação de uma ou mais atividades, *scripts* ou *transformations*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

A combinação específica e a ordem desses componentes deve seguir um conjunto de padrões válidos. Para mais detalhes sobre esses padrões, consulte [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR).

Esta página explica as partes de uma operação, daí aborda como adicionar etapas a uma operação, como acessar as opções do menu, como renomear operações, expandi-las ou recolhê-las, reordená-las, além de como reusar, remover ou mover etapas de operação.


## Partes de uma Operação

As operações são formadas quando se arranja atividades, *scripts* ou *transformations* dentro de uma operação no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR). A operação pode ser composta de apenas um único *script*, ou o arranjo pode formar uma sequência de passos que consistem de uma ou mais atividades, *scripts* ou *transformations*. As combinações específicas que são permitidas são descritas em [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR).

### Atividades

Uma atividade é um componente que é criado a partir de uma conexão e que pode ser configurado para interagir com um *endpoint*. As atividades podem ser usadas em uma operação como fonte ou como alvo e podem ser configuradas com *schemas* de dados que representam os *schemas* de solicitação e resposta para a interação com o *endpoint*. Além de serem usadas como etapas de operação, algumas atividades também podem ser referenciadas em *scripts* (veja [*Endpoints*](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR#JitterbitScript-Connectors) em [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR)).

Para mais informações sobre conectores, tanto informações [básicas](https://success.jitterbit.com/display/CS/Connector+Basics?showLanguage=pt_BR) quanto as [classificações](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR) deles, além de recursos para configurar conexões e atividades por cada tipo de conector, veja as páginas sob [Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR).

#### Fontes

Uma *atividade fonte* é qualquer atividade que fornece dados dentro de uma [operação](https://success.jitterbit.com/display/CS/Operations?showLanguage=pt_BR), que podem então ser transferidos para um alvo sem passar por modificações ou podem ser alterados por um [*transformation*](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR) antes de chegar a um alvo.

Atividades fonte requerem um *schema* de dados apenas se forem ser usados como entrada em um *transformation*:

- Caso a atividade fonte esteja fornecendo dados que serão transformados, então ela deve ter um *schema* de dados de resposta, que pode ser automaticamente fornecido ou definido durante a configuração da atividade ou do *transformation*.

- Caso a atividade fonte esteja fornecendo dados que não serão transformados, então um *schema* de resposta não precisa ser definido, já que o *schema* de resposta não é usado na operação.

Atividades que são tipicamente (mas não necessariamente) usadas como fontes incluem aquelas que contêm uma das palavras abaixo em seus nomes:

- Download
- Get
- Read
- Request
- Query

#### Alvos

Uma *atividade alvo* é qualquer atividade que receba dados dentro de uma [operação](https://success.jitterbit.com/display/CS/Operations?showLanguage=pt_BR). Estes dados podem vir de uma atividade fonte, de um [*transformation*](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR) ou de qualquer outra entrada tais como [variáveis](https://success.jitterbit.com/display/CS/Variables?showLanguage=pt_BR) ou [*scripts*](https://success.jitterbit.com/display/CS/Scripts?showLanguage=pt_BR).

Atividades alvo precisam de um *schema* de dados somente se estiverem recebendo dados que foram transformados ou se fornecerem uma resposta que você deseje gravar em outro alvo:

-   Se a atividade alvo estiver recebendo dados que foram transformados, ela deve ter um *schema* de dados de solicitação, que pode ser automaticamente fornecido ou definido durante a configuração da atividade ou do *transformation*.

-   Se a atividade alvo estiver recebendo dados que não foram transformados, um *schema* de solicitação não precisa ser definido, já que o *schema* de solicitação não é usado na operação.

-   Se um tipo específico de atividade alvo fornecer uma resposta, então você também pode ter um *schema* de dados de resposta. Se você quiser gravar a resposta em outro alvo, o *schema* de dados de resposta pode ser automaticamente fornecido ([atividades SOAP](https://success.jitterbit.com/display/CS/SOAP?showLanguage=pt_BR) ou [atividades de aplicações](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-application)) ou definido durante a configuração da atividade ou do *transformation* ([HTTP](https://success.jitterbit.com/display/CS/HTTP?showLanguage=pt_BR)). Se o tipo de alvo fornecer uma resposta, não é necessário que uma operação grave a resposta em outro alvo; isto é, um *schema* de resposta pode ser fornecido mas pode ser ignorado dentro da operação caso não seja exigido.

Atividades que são tipicamente (mas não necessariamente) usadas como alvos incluem aquelas que contêm uma das palavras abaixo em seu nome:

- Add
- Create
- Delete
- Insert
- Post
- Put
- Response
- Upload
- Update
- Upsert
- Write

### *Scripts*

Um *script* que é criado como componente de projeto pode ser usado como etapa em uma operação para transformar dados, executar cálculos ou realizar validação lógica. Por exemplo, você pode usar um *script* antes ou depois de uma atividade para buscar dados e daí processar lógica de *script*, ou pode executar um *script* de validação antes de prosseguir para um *transformation*. Para mais informações, veja [Tipos e Criação de *Scripts*](https://success.jitterbit.com/display/CS/Script+Types+and+Creation?showLanguage=pt_BR).

### *Transformations*

Um *transformation* é um componente de projeto que é usado como etapa em uma operação para mapear ou transformar entradas em saídas através da movimentação ou limpeza de dados ou aplicação de lógica de negócio. Depois que você cria um *transformation*, precisa configurá-lo mapeando várias entradas, tais como objetos fonte, variáveis ou *scripts*, até a saída alvo resultante, que normalmente será uma estrutura de dados. Para mais informações, veja [Transformations](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR).


## Adicionando Etapas a uma Operação

As operações são compostas de componentes de projeto, consistindo de atividades, *scripts* ou *transformations*. Para criar operações, você deve colocar tais componentes em um workflow no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR) como etapas de operação.

### Escolhendo a Localização do Componente dentro de uma Operação Nova ou Existente

O método para adicionar um componente a uma operação depende de a operação já ser existente ou estar sendo criada agora:

- **Nova Operação**: Uma área de inserção de operações é exibida no design canvas nos lugares onde você pode adicionar um componente para criar uma nova operação. Em um workflow que ainda não tem operações, a área de inserção é mostrada sozinha no topo do design canvas. Em um workflow que tem pelo menos uma operação, uma área de inserção é mostrada sozinha na parte inferior do design canvas, abaixo da última operação. Para mostrar áreas de inserção adicionais, paire seu mouse sobre uma operação existente.

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Operação Existente**: Operações existentes são mostradas no design canvas com um fundo cinza claro. Pairar o mouse à esquerda ou à direita de um componente numa operação existente mostra uma área de inserção de componentes em qualquer lugar onde você pode adicionar um novo componente a uma operação já existente.

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component.png" class="confluence-embedded-image confluence-external-resource" /></span>

Depois que você decidiu a localização, os passos para adicionar o componente são diferentes dependendo se o componente for uma [atividade](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR#OperationCreationandConfiguration-add-and-configure-activities) ou um [*script* ou *transformation*](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR#OperationCreationandConfiguration-add-and-configure-scripts-or-transformations). Tais casos são cobertos a seguir.

### Criando Conexões, daí Adicionando e Configurando Atividades

A [paleta de componentes de *design*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR) fornece acesso a recursos de conectividade. Aqui, *conectores* proveem a interface para inserir entradas fornecidas pelo usuário, tais como credenciais, para criar uma conexão. Dentro da paleta de componentes, o filtro **Connectors** (Conectores) mostra os tipos de conectores que podem ser configurados:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/connectors_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

Cada conector é representado por um ícone de pasta de conector, abaixo do qual fica o nome do conector. Clique em um conector para abrir uma tela de configuração para criar uma nova conexão para acesso a um recurso de dados em específico:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_http_multiple.png" class="confluence-embedded-image confluence-external-resource" /></span>

Para instruções detalhadas sobre como configurar uma conexão, procure a conexão específica em [Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR). Cada vez que você cria uma nova conexão, deve fazer isso a partir do ícones de pasta de conector acessíveis no filtro **Connectors**.

Depois que você criou uma conexão, ela aparece no filtro **Endpoints**. Clique em uma conexão para revelar os tipos de atividades - interações com um *endpoint* - que podem ser configuradas para aquela conexão.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_http_activities.png" class="confluence-embedded-image confluence-external-resource" /></span>

Um *endpoint* refere-se a uma conexão específica e suas atividades, que são configuradas como fontes (para fornecer dados) ou alvos (para consumir dados) em um projeto. Como referência, o diagrama abaixo mostra o relacionamento entre conectores, conexões, atividades e *endpoints*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/connectivity-terms_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

Para criar uma instância de atividade, coloque um tipo de atividade no design canvas arrastando ou copiando o mesmo até uma área de inserção de operações ou componentes:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/create-activity-instance.gif" class="confluence-embedded-image confluence-external-resource" /></span>

Uma vez que uma atividade está criada, você pode clicar nela duas vezes para configurá-la conforme descrito para cada atividade específica em [Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR).

### Adicionando e Configurando *Transformations* ou *Scripts*

Você também pode querer adicionar *transformations* ou *scripts* a uma operação. Os *transformations* são usados quando você quer transformar dados antes que eles cheguem ao alvo. Os *scripts* podem ser usados dentro de *transformations* em campos ou nós alvo com o objetivo de aplicar lógica ou condições específicas aos dados. Os *scripts* também podem ser usados como etapas opcionais dentro de uma operação para uma série de propósitos, tais como tratamento de erros ou percorrimento de registros de dados.

Para adicionar um novo *transformation* ou *script* diretamente a uma operação, clique com o botão direito ou clique no menu de ações em uma área de inserção e selecione **New Script** (Novo *Script*) ou **New Transformation** (Novo *Transformation*):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component_actions-menu.png" class="confluence-embedded-image confluence-external-resource" /></span>

Quando você adiciona um *script* ou um *transformation*, a tela de configuração dele abre automaticamente. Para mais detalhes sobre as configurações, veja [Transformations](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR) e [Scripts](https://success.jitterbit.com/display/CS/Scripts?showLanguage=pt_BR), respectivamente.

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA:** Etapas de operação podem ser configuradas em qualquer ordem. No entanto, note que um *schema* fornecido em uma atividade adjacente tem precedência sobre um *schema* definido em um *transformation*. Caso você escolha definir um *schema* em uma atividade ou em um *transformation* dependerá do seu caso de uso. Para mais informações, veja [Uso de *Schemas*](https://success.jitterbit.com/display/CS/Schema+Usage?showLanguage=pt_BR).

</div>

</div>


## Menu de Ações de Operação

Depois que uma operação é criada, as ações de menu dela são disponíveis a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

As seguintes ações estão disponíveis em todos os menus de ações de operação:

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
</colgroup>
<tbody>
<tr class="header header">
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Item do Menu</strong></td>
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Descrição</strong></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/settings.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Configurações</em></p>
</div></td>
<td class="confluenceTd"><p>O botão <strong>Settings</strong> (Configurações) abre as configurações de operação, que contêm três abas:</p>
<ul>
<li><strong>Schedules</strong> (Agendas): Crie e aplique agendas para executar operações automaticamente (veja <a href="https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR">Agendas de Operação</a>).</li>
<li><strong>Actions</strong> (Ações): Configure ações a serem tomadas em caso de sucesso ou falha da operação (veja <a href="https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR">Ações de Operação</a>).</li>
<li><strong>Options</strong> (Opções): Configure opções tais como quando a operação irá exaurir seu tempo, o que registrar e o prazo para isso, quando a operação será executada, ou caso a fragmentação de dados (<em>chunking</em>) deverá ser usada (veja <a href="https://success.jitterbit.com/display/CS/Operation+Options?showLanguage=pt_BR">Opções de Operação</a>).</li>
</ul></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Cortar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Cut</strong> (Cortar) coloca uma cópia da operação na sua área de transferência e deleta a operação original do projeto (veja <a href="https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR">Reuso de Operações</a>).</td>
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
<td class="confluenceTd">O botão <strong>Copy</strong> (Copiar) coloca uma cópia da operação na sua área de transferência (veja <a href="https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR">Reuso de Operações</a>).</td>
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
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_deploy-and-run_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
height="101" /></span></p>
<p><em>Implantação</em></p>
<p><em>&gt; Implantar</em></p>
<p><em>&gt; Implantar e Executar</em></p>
<p><em>&gt; Implantação Configurável</em></p>
</div></td>
<td class="confluenceTd"><p>O botão <strong>Deploy</strong> (Implantação) mostra as seguintes ações de menu:</p>
<ul>
<li><strong>Deploy</strong> (Implantar): Implanta a operação e quaisquer componentes dos quais ela dependa (veja <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR">Implantação e Execução de Operações</a>).</li>
<li><strong>Deploy and Run</strong> (Implantar e Executar): Implanta e executa a operação e quaisquer operações abaixo dela na cadeia que estejam conectadas (veja <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR">Implantação e Execução de Operações</a>).</li>
<li><strong>Configurable Deploy</strong> (Implantação Configurável): Abre a tela de implantação, onde você pode selecionar componentes para implantar (veja <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR">Implantação e Execução de Operações</a>).</li>
</ul></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/run.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Executar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Run</strong> (Executar) executa uma operação já implantada, bem como quaisquer operações abaixo dela na cadeia que estejam conectadas (veja <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR">Implantação e Execução de Operações</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Visualizar Registros</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>View Logs</strong> (Visualizar Registros) abre a tela de registro de operação, que inclui registros daquela operação, bem como de quaisquer operações filhas que tenham sido implantadas e executadas (veja <a href="https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR">Registros de Operação</a>).</td>
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
<td class="confluenceTd">O botão <strong>Rename</strong> (Renomear) coloca o cursor no nome da operação para que você faça as edições que achar necessárias.</td>
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
<td class="confluenceTd">O botão <strong>View Dependencies</strong> (Visualizar Dependências) altera a visualização no painel de projeto para exibir quaisquer outras partes do projeto das quais aquela operação específica dependa (veja <a href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR">Dependências, Exclusão e Remoção de Operações</a>).</td>
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
<td class="confluenceTd">O botão <strong>Delete</strong> (Deletar) exclui permanentemente o componente (veja <a href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR">Dependências, Exclusão e Remoção de Operações</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Remover</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Remove</strong> (Remover) remove todas as referências ao componente do design canvas. Esta ação só é funcional quando usada em uma operação que está num workflow (veja <a href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR">Dependências, Exclusão e Remoção de Operações</a>).</td>
</tr>
</tbody>
</table>

As seguintes ações estão disponíveis apenas a partir dos menus de ações de atividade acessíveis na aba **Components** do painel de projeto e no design canvas:

<table>
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
</colgroup>
<tbody>
<tr class="header header">
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Item do Menu</strong></td>
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Descrição</strong></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu_with-step-references_with-step-copies.png
class="confluence-embedded-image confluence-external-resource image-right"
height="67" /></span></p>
<p><em>Duplicar</em></p>
<p><em>&gt; Com Referências à Etapa</em></p>
<p><em>&gt; Com Cópias da Etapa</em></p>
</div></td>
<td class="confluenceTd"><p>O botão <strong>Duplicate</strong> (Duplicar) mostra as seguintes ações de menu (veja <a href="https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR">Reuso de Operações</a>):</p>
<ul>
<li><strong>With Step References</strong> (Com Referências à Etapa): Duplica apenas a operação. A operação duplicada contém referências a cada uma das etapas da operação original.</li>
<li><strong>With Step Copies</strong> (Com Cópias da Etapa): Duplica a operação e os componentes referenciados como etapas de operação. Novos componentes são criados para cada etapa de operação e são referenciados pela operação duplicada.</li>
</ul></td>
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
<td class="confluenceTd">O botão <strong>Add to Group</strong> (Adicionar ao Grupo) abre uma nova caixa de diálogo para criar um novo grupo customizado ou para adicionar o componente a um grupo existente (veja <a href="https://success.jitterbit.com/display/CS/Component+Groups?showLanguage=pt_BR">Grupos de Componentes</a>).</td>
</tr>
</tbody>
</table>


## Renomeando Operações e Etapas de Operação

Quando você cria uma nova operação, o nome padrão dela é *New Operation* (em inglês, “nova operação”). Futuras novas operações com nomes padrão receberão também um número incrementado entre parênteses. Os nomes das operações devem ser únicos e não devem conter barras (/) nem dois pontos (:) para serem válidos.

As operações e as etapas de operação podem ser renomeados nos seguintes lugares:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Renomeando Workflows, Operações e Etapas de Operação](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-renaming) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Etapas de operação também podem ser renomeadas em suas telas de configuração individuais.


## Expandindo ou Recolhendo Operações

Quando uma operação é criada, ela é expandida por padrão. As operações podem ser recolhidas ou expandidas individualmente ou todas de uma vez:

- **Recolhendo uma Operação Individual**: Para recolher uma operação individual, clique no ícone de recolhimento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/collapse.png" class="confluence-embedded-image confluence-external-resource" /></span> na barra de ferramentas de operação:

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_collapse.png" class="confluence-embedded-image confluence-external-resource" /></span>

  Recolher uma operação faz com que ela seja exibida em uma visualização menor e mais condensada:

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_collapsed.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Expandindo uma Operação Individual**: Para expandir uma operação individual quando ela está recolhida, clique no ícone de expansão <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/expand.png" class="confluence-embedded-image confluence-external-resource" /></span> na barra de ferramentas de operação.

- **Recolhendo Todas as Operações**: Para recolher todas as operações em um workflow, clique em **Collapse All Operations** (Recolher Todas as Operações) ou no ícone de recolher todas <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/collapse_5.png" class="confluence-embedded-image confluence-external-resource" /></span> no topo do design canvas. Isto exibe todas as operações no workflow em uma visualização menor e mais condensada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_collapsed.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Expandindo Todas as Operações**: Para expandir todas as operações em um workflow quando elas estão recolhidas, clique em **Expand All Operations** (Expandir Todas as Operações) ou no ícone de expandir todas <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/expand_2.png" class="confluence-embedded-image confluence-external-resource" /></span> no topo do design canvas.


## Reordenando Operações

As operações podem ser reordenadas dentro de um workflow ou entre workflows a partir da aba **Workflows** do painel de projeto (veja [Reordenando Operações](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-reorder-an-operation) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

As operações podem ser reordenadas dentro do mesmo workflow a partir do design canvas (veja [Reordenando Operações](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-reordering-operations) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).
