[//]: # (Interface de Usuário do Cloud Studio)
[//]: # (This is a translation of Version 27, published on October 5, 2021.)

## Introdução

O [Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR) é a aplicação de *design* de projetos baseada na
Web da Jitterbit, acessível através do [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR).

Quando você acessa o Cloud Studio, você chega no índice de projetos, que
contém um repositório de todos os seus projetos, ou você pode trocar
para o índice do Connector Builder para ver os conectores customizados
criados com o Connector Builder.

Depois de abrir um projeto, você faz o *design* dele usando as
ferramentas oferecidas no *designer* de projetos. O *designer* de
projetos inclui a barra de ferramentas de projeto, o painel de projeto,
o design canvas e a paleta de componentes, bem como as telas de
configuração de cada componente, como as das *transformations*, dos
*scripts*, das conexões e das atividades.

À medida que você trabalha em projetos, o Cloud Studio salva os estados
de exibição que você usou pela última vez em um dado projeto na próxima
vez em que você o abrir.

## <span id="CloudStudioUserInterface-project-index" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Índice de Projetos

O [índice de projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR), exibido usando o menu *dropdown* **My
Projects** (Meus Projetos), exibe uma lista de todos os seus projetos do
Cloud Studio, e é onde você cria um novo projeto ou importa um projeto
existente. Projetos existentes podem ser mostrados como cartões que
podem ser virados para revelar informações adicionais sobre os projetos,
ou exibidos em visualização de lista. Em qualquer uma das formas de
visualização, você também pode abrir o projeto, os registros dele, ou a
lista de variáveis de projeto; bem como exportar ou excluir o projeto.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-index/card-view_flip.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-index/card-view_flip.png" /></span>

Criar um novo projeto (**New Project** \[Novo Projeto\]), importar um
projeto (**Import** \[Importar\]), ou ver/editar um projeto existente
(**View/Edit** \[Ver/Editar\]) abre o projeto e exibe a interface do
[*designer* de projetos](https://success.jitterbit.com/display/CS/Cloud+Studio+User+Interface?showLanguage=pt_BR#CloudStudioUserInterface-project-designer).

## <span id="CloudStudioUserInterface-connector-builder-index" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Índice do Connector Builder

O [índice do Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder+Index?showLanguage=pt_BR), exibido usando o menu *dropdown*
**Connector Builder**, oferece uma lista de conectores customizados
criados com o [Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder?showLanguage=pt_BR). Os conectores existentes podem ser
mostrados como cartões ou em forma de lista, da mesma forma que os
projetos. Em qualquer uma das visualizações, você pode criar um novo
conector, importar um conector, ou editar, deletar ou exportar um
conector existente.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector-builder/index_card-view_flip.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector-builder/index_card-view_flip.png" /></span>

A interface de usuário do Connector Builder é discutida numa outra seção
da documentação, no artigo [Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder?showLanguage=pt_BR).

## <span id="CloudStudioUserInterface-project-designer" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>*Designer* de Projetos

O *designer* de projetos é a interface onde você faz o *design* de um
projeto. O *designer* de projetos inclui a [barra de ferramentas de
projeto](https://success.jitterbit.com/display/CS/Cloud+Studio+User+Interface?showLanguage=pt_BR#CloudStudioUserInterface-project-toolbar), o [painel de projeto](https://success.jitterbit.com/display/CS/Cloud+Studio+User+Interface?showLanguage=pt_BR#CloudStudioUserInterface-project-menu), o [Design Canvas](https://success.jitterbit.com/display/CS/Cloud+Studio+User+Interface?showLanguage=pt_BR#CloudStudioUserInterface-design-canvas) e a
[paleta de componentes](https://success.jitterbit.com/display/CS/Cloud+Studio+User+Interface?showLanguage=pt_BR#CloudStudioUserInterface-component-palette), bem como as [telas de configuração](https://success.jitterbit.com/display/CS/Cloud+Studio+User+Interface?showLanguage=pt_BR#CloudStudioUserInterface-configuration-screens)
de cada componente, como as das *transformations*, dos *scripts* e das
atividades.

Ao abrir um projeto, estas partes do *designer* de projeto são exibidas:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/project-designer_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/project-designer_annotated_pp.png" /></span>

### <span id="CloudStudioUserInterface-project-toolbar" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Barra de Ferramentas de Projeto

A [barra de ferramentas de projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR) é a barra abaixo do cabeçalho
do Harmony Portal onde você pode acessar as ações de projeto, ver
informações do projeto, e navegar para os projetos recentes:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-toolbar/project-toolbar_annotated.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-toolbar/project-toolbar_annotated.png" /></span>

A barra de ferramentas de projeto persiste em todas as telas à medida
que você usa o Cloud Studio para acessar um projeto individual.

### <span id="CloudStudioUserInterface-project-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Painel de Projeto

O [painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane?showLanguage=pt_BR) é o painel à esquerda quando você abre um
projeto onde você pode ver e gerenciar workflows e componentes de
projeto. O painel de projeto tem duas visualizações, acessadas por abas
distribuídas no topo:

-   **Workflows**: Esta aba é focada em workflows individuais, suas
    operações, e os passos usados para executar estas operações (veja
    [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

-   **Componentes**: Esta aba mostra todos os componentes do projeto e
    aponta se eles são usados em apoio a uma operação (veja [Aba
    Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:33%;min-width:33%;max-width:33%;" hasbody="true"
macro-name="column">

#### Workflows

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/overview.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:33%;min-width:33%;max-width:33%;" hasbody="true"
macro-name="column">

#### Componentes

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/overview.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:33%;min-width:33%;max-width:33%;" hasbody="true"
macro-name="column">

</div>

</div>

</div>

### <span id="CloudStudioUserInterface-design-canvas" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Design Canvas

O [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR) é a área central quando você abre um projeto que
serve como o espaço de trabalho primário onde você faz o *design* das
integrações visualmente. Dentro do design canvas, você pode criar
múltiplos workflows, acessados por meio de abas ao longo do topo do
design canvas. Você projeta os workflows dentro do quadro mediante a
criação e ligação de operações usando as ferramentas oferecidas na
paleta de componentes, no painel de projeto, e no próprio design canvas.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script.png" /></span>

### <span id="CloudStudioUserInterface-component-palette" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Paleta de Componentes

Os dois tipos de [paletas de componentes](https://success.jitterbit.com/display/CS/Component+Palette?showLanguage=pt_BR) oferecem acesso a
componentes que podem ser usados dentro do projeto:

-   **[Paleta de componentes de *design*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR)**: A paleta de
    componentes de *design* é o painel expansível à direita quando
    você abre um projeto que oferece acesso a componentes de projeto
    que podem ser usados no design canvas. Dentro da aba
    **Conectividade** da paleta de *design*, os conectores recebem as
    primeiras configurações para criar conexões. Tipos de atividades
    associados com essas conexões ficam então disponíveis para criar
    instâncias de uma atividade num projeto.

-   **[Paleta de componentes de *script*](https://success.jitterbit.com/display/CS/Script+Component+Palette?showLanguage=pt_BR)**: A paleta de
    componentes de *script* é o painel expansível à direita das telas
    de *script* e de configuração de *transformations* modo *script*
    que oferece acesso a componentes de projeto que podem ser usados
    dentro de *scripts*. Cada componente dentro das abas **Source
    Objects** (presente apenas para as *transformations*), **Funções,
    Variáveis, Plugins, Operações, Notificações, Scripts** e
    **Endpoints** pode ser usado num *script*.

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:50%;min-width:50%;max-width:50%;" hasbody="true"
macro-name="column">

#### Paleta de Componentes de *Design*

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_http_activities.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_http_activities.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:50%;min-width:50%;max-width:50%;" hasbody="true"
macro-name="column">

#### Paleta de Componentes de *Script*

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/source-objects_items.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/source-objects_items.png" /></span>

</div>

</div>

</div>

</div>

### <span id="CloudStudioUserInterface-configuration-screens" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Telas de Configuração

Vários tipos de componentes de projeto, bem como outras áreas da
interface de usuário exigem configuração com entradas dadas pelo
usuário.

A interface onde você dá essas entradas é frequentemente chamada de tela
de configuração ou editor do tipo específico de componente ou área de
configuração.

Atividades e conexões são tipicamente descritas como tendo telas de
configuração de atividade e telas de configuração de conexão,
respectivamente. Aqui estão alguns outros exemplos de como a tela de
configuração de outros componentes pode ser chamada:

-   Se você adicionar um *script* a uma operação, você faria a
    configuração dele usando a tela de configuração de *script*, que
    também é chamada de editor do *script*.

-   Depois de criar uma *transformation*, você pode definir um *schema*
    manualmente, usando o editor de esquema de arquivo.

-   Você pode mais tarde adicionar uma agenda a uma operação, que você
    configura da tela de configuração de agenda ou do editor de
    agenda.

Nesta seção, a atividade File Share Read (Ler Arquivo Compartilhado) é
usada como exemplo para ilustrar uma típica tela de configuração de
atividade. A tela de configuração de *transformation* é única no sentido
de que pode ser acessada em vários modos de exibição: [Modo de
Mapeamento](https://success.jitterbit.com/display/CS/Mapping+Mode?showLanguage=pt_BR), [Modo de Script](https://success.jitterbit.com/display/CS/Script+Mode), ou [Modo de
Pré-Visualização](https://success.jitterbit.com/display/CS/Preview+Mode?showLanguage=pt_BR), conforme explicado abaixo.

#### Exemplo de Tela de Configuração de Atividade

Telas de configuração de componente são únicas a cada tipo de
componente. Como exemplo, após criar uma instância de uma atividade do
tipo Compartilhar Arquivo, você abre a tela de configuração dela e
insere informações como os arquivos com os quais você quer interagir e
os schemas de arquivo opcionais. Alguns editores podem ser compostos de
vários passos, exigindo que o usuário passe por toda a configuração,
como o editor da atividade Compartilhar Arquivo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_variable.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_variable.png" /></span>

<div
class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
hasbody="true" macro-name="tip">

<span
class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

***DICA**: Se você estiver tendo problemas com nomes e senhas populando
campos de configuração automaticamente, tente ajustar as configurações
do seu navegador (limpando o cache e desabilitando o preenchimento
automático), ou desabilitando seus gerenciadores de senhas.*

</div>

</div>

No topo de cada tela de configuração de atividade há um link para a
configuração da conexão com a qual cada atividade está associada. Para
navegar até a configuração da conexão, clique no nome da conexão
associada:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_activity_link.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_activity_link.png" /></span>

Muitas telas também incluem o nome do componente que você está
configurando. Dependendo do componente que você está configurando, o
nome exibido pode atualizar automaticamente baseado no nome inserido
pelo usuário para o componente ou a operação associada. Para outros
componentes, como as atividades, o nome pode ser estático e indicar um
tipo específico de componente, como por exemplo Ler para a atividade
File Share Read (Ler Arquivo Compartilhado):

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_title.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_title.png" /></span>

Em telas que possuem vários passos de configuração, os números dos
passos são exibidos, com o número do passo atual aumentado e com fundo
preto:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_step-1_steps.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_step-1_steps.png" /></span>

Uma vez que um passo está configurado, você pode navegar até esse passo
clicando sobre o seu número. Passos que são navegáveis mostram um fundo
laranja quando você paira o mouse sobre eles e são clicáveis:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_step-3_steps.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_step-3_steps.png" /></span>

Após a criação inicial, os passos devem ser configurados na ordem para
configurar totalmente e salvar o componente usando o botão **Finished**
(Concluído) no último passo.

Após a criação inicial e a edição subsequente, você pode navegar de
volta até qualquer passo já configurado usando o número do passo ou o
link **Back** (Voltar) no fundo de cada tela de configuração. No
entanto, fazer mudanças na configuração de um passo anterior exige que
você reconfigure ou refaça cada passo na ordem de novo.

Passos que devem ser configurados ou reconfigurados devem ser acessados
usando o botão **Next** (Próximo) no fundo de cada tela de configuração.

A configuração completa de um componente é salva ou descartada ao sair
da tela de configuração.

O botão **Next** (Próximo) e outros botões e links mostrados no fundo da
tela são cobertos na documentação de cada componente.

Muitas telas de configuração têm um ícone de fechamento no canto
superior direito que é usado para fechar e sair da tela de configuração:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/close_2.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_2.png" /></span>

Ao usar este método para fechar uma tela de configuração, as entradas do
usuário não são salvas em telas de configuração que usam botões para
salvar entradas manualmente, como é o caso com as telas de configuração
de atividade. Outros tipos de telas de configuração, como aqueles usados
para *scripts* e *transformations*, usam salvamento automático, conforme
indicado pelo *status* de salvamento ao aparecer no alto da tela. Para
mais informações sobre salvamento manual e salvamento automático, veja
[Salvando](https://success.jitterbit.com/display/CS/Cloud+Studio+Permissions%2C+Collaboration%2C+and+Saving?showLanguage=pt_BR#CloudStudioPermissions,Collaboration,andSaving-save-changes) em [Permissões, Colaboração e Salvamentos no Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Permissions%2C+Collaboration%2C+and+Saving?showLanguage=pt_BR).

Depois de fechar um componente configurado que usa passos, quando você
reabre o componente você é levado ao último passo da configuração. O
último passo é muitas vezes um passo de revisão, que permite que você
reveja as configurações atuais sem precisar reenviar as configurações
feitas em passos anteriores.

Dentro de cada tela de configuração, os campos exigidos são indicados
por um asterisco vermelho logo após o nome do campo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_required.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_required.png" /></span>

A ausência do asterisco vermelho indica que o campo é opcional e seu
preenchimento não é obrigatório.

Dependendo do tipo do campo, um campo pode ser completado de diferentes
formas, incluindo através da seleção de um botão de rádio, o uso de um
menu *dropdown*, ou a inserção de entradas.

Campos que mostram um ícone de variável
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/variable.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/variable.png"
height="16" /></span>
suportam o uso de [variáveis globais](https://success.jitterbit.com/display/CS/Global+Variables?showLanguage=pt_BR), [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR)
ou [variáveis Jitterbit](https://success.jitterbit.com/display/CS/Jitterbit+Variables?showLanguage=pt_BR). Comece digitando um colchete esquerdo `[`
no campo ou clique no ícone de variável
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/variable.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/variable.png"
height="16" /></span>
para mostrar as variáveis existentes que podem ser escolhidas. Uma vez
inseridas, as variáveis são exibidas em formato de pílula na mesma linha
que o restante da entrada em formato de texto, caso haja:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_variable-field.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_variable-field.png" /></span>

#### <span id="CloudStudioUserInterface-mapping-mode" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Modo de Mapeamento

O [modo de mapeamento](https://success.jitterbit.com/display/CS/Mapping+Mode?showLanguage=pt_BR) oferece uma visão geral do mapeamento e das
ferramentas básicas para fazer o mapeamento:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/overview.png" /></span>

#### <span id="CloudStudioUserInterface-script-mode" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Modo de Script

O [modo de *script*](https://success.jitterbit.com/display/CS/Script+Mode?showLanguage=pt_BR) oferece visões detalhadas dos campos e ferramentas
avançadas para adicionar *scripts* ao mapeamento:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/script-mode/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/script-mode/overview.png" /></span>

#### <span id="CloudStudioUserInterface-preview-mode" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Modo de Pré-Visualização

O [modo de pré-visualização](https://success.jitterbit.com/display/CS/Preview+Mode?showLanguage=pt_BR) permite que você use dados de amostra para
testar como a *transformation* vai processar os dados:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/preview-mode/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/preview-mode/overview.png" /></span>
