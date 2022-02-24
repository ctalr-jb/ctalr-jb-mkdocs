[//]: # (Visão Geral do Cloud Studio para Usuários do Design Studio)
[//]: # (This is a translation of Version 31, published on July 29, 2021.)

## Introdução

Se você usa o [Jitterbit Harmony Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR) (também chamado de
Jitterbit Studio), você já sabe que uma integração tem muitas partes e peças que se movem. O Design Studio oferece a
flexibilidade de fazer o *design* de projetos de várias formas, criando soluções poderosas para uma ampla gama de
problemas de integração. Desde o seu primeiro lançamento há mais de 10 anos, a nossa aplicação de *design* foi
melhorada inúmeras vezes para aumentar a sua capacidade de entregar as melhores funcionalidades da sua classe para
os desafios de integração, que estão sempre mudando.

Hoje, nós reinventamos a experiência do usuário ao fazer o *design* de integrações a partir do zero. Construído
sobre a sólida base da [Plataforma em Nuvem Jitterbit
Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper#JitterbitSecurityandArchitectureWhitePaper-MajorComponents?showLanguage=pt_BR),
que inclui os [Jitterbit Harmony Agents](https://success.jitterbit.com/display/DOC/Agent?showLanguage=pt_BR) que executam os processos que
suportam integrações, o [Jitterbit Harmony Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR) acelera o
design de integrações até o próximo nível. O Cloud Studio oferece uma experiência moderna e baseada na Web otimizada
para a maior facilidade de uso e de acesso por quem projeta integrações.

O propósito deste documento é ajudar usuários existentes do Design Studio a fazer a transição para o Cloud Studio e
inclui uma comparação das características principais.


## Acessando a Aplicação de *Design*

O Design Studio é uma aplicação *client* que deve ser baixada e instalada num sistema operacional suportado (Windows
ou macOS) com os requisitos de *hardware* específicos listados em [Requisitos de Sistema para o Design
Studio](https://success.jitterbit.com/display/DOC/System+Requirements+for+Design+Studio?showLanguage=pt_BR).

Com o Cloud Studio, você não precisa mais instalar a aplicação de *design* na sua máquina. Em vez disso, o [Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR) oferece acesso de qualquer lugar que tenha conexão com a
Internet, independentemente de plataforma ou localização, através do [Harmony
Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR). Os navegadores suportados incluem Chrome,
Firefox, e Safari (apenas para macOS). Além disso, você pode navegar diretamente de e para as outras aplicações
Harmony, tais como o [API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR), o
[Marketplace](https://success.jitterbit.com/display/DOC/Marketplace?showLanguage=pt_BR) e o [Management
Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR) enquanto faz o *design* do seu projeto.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/hp/landing/cards_cloud-studio_without-header.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/hp/landing/cards_cloud-studio_without-header.png" /></span>

**Pergunta:** *Posso usar as duas aplicações de* design *ao mesmo tempo?*

**Resposta:** Você pode usar o Cloud Studio e o Design Studio ao mesmo tempo para projetos ***diferentes***. No
entanto, usá-los para o mesmo projeto não é possível.


## <span id="CloudStudioOverviewforDesignStudioUsers-importing" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Criando e Importando Projetos

Quando você abre o Design Studio, você é recebido por uma tela de início onde você pode criar um novo projeto, abrir
um projeto existente ou importar um projeto do Design Studio. Depois de abrir um projeto, as mesmas ações podem ser
feitas a partir do menu **File** (Arquivo) na barra de menus.

No Cloud Studio, essas ações são feitas a partir do [índice de
projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR), que mostra um repositório com todos os seus projetos do
Cloud Studio em visualização de cartões ou de uma lista. A funcionalidade **Import** (Importar) permite que você
importe projetos que foram exportados do Cloud Studio.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-index/card-view.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-index/card-view.png" /></span>

**Pergunta:** *Posso exportar um projeto do Design Studio e importá-lo no Cloud Studio?*

**Resposta:** No momento, esta funcionalidade não está disponível. Porém, nós estamos desenvolvendo uma ferramenta
de importação que permitirá que você importe projetos do Design Studio para dentro do Cloud Studio no futuro.

**Pergunta:** *Posso exportar um projeto do Cloud Studio e importá-lo no Design Studio?*

**Resposta:** Projetos do Cloud Studio não são retrocompatíveis com o Design Studio. No entanto, você pode [exportar
projetos do Cloud Studio e importá-los no Cloud
Studio](https://success.jitterbit.com/display/CS/Project+Exports+and+Imports?showLanguage=pt_BR). Os projetos do Cloud Studio estão no formato
de um arquivo JSON.

**Pergunta:** *Existem modelos para que eu não precise construir projetos do zero?*

**Resposta:** O [Jitterbit Marketplace](https://success.jitterbit.com/display/DOC/Marketplace?showLanguage=pt_BR) oferece centenas de projetos
pré-construídos, na forma de [Protótipos de Integração do Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Integration+Recipes?showLanguage=pt_BR) e [*Templates* de Processo do Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Process+Templates?showLanguage=pt_BR), e sempre há mais deles sendo
desenvolvidos. Para começar a trabalhar com um protótipo ou *template* que já existe, veja [Começando um Projeto
com um Protótipo de Integração ou
*Template*](https://success.jitterbit.com/display/DOC/Starting+a+Recipe+or+Template+Project?showLanguage=pt_BR). Um número limitado de
protótipos do [Citizen Integrator](https://success.jitterbit.com/display/DOC/Citizen+Integrator?showLanguage=pt_BR), que são exclusivos para o
Design Studio, também está disponível.


## Interface de *Design*

No Design Studio, a área principal em que você trabalha e onde você constrói operações é chamada de janela de
*design* ou espaço de trabalho de *design*. Enquanto você constrói seu projeto, os itens dele são listados à
esquerda dentro do painel de listagem de itens de projeto, você pode organizá-los em pastas. Você também tem acesso
a uma barra de ferramentas e menus que oferecem mais opções.

O Cloud Studio oferece um fluxo de trabalho intuitivo e moderno com o *designer* de projetos. Ao abrir um projeto,
estas partes do *designer* de projetos aparecem:

-   **Barra de ferramentas de projeto:** A [barra de ferramentas de
    projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR) no topo permite que você acesse ações de projeto e
    navegue para projetos recentes.

-   **Painel de projeto:** O [painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane?showLanguage=pt_BR) à esquerda oferece
    navegação por todo o seu projeto.

-   **Design canvas:** O [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR) é o local de trabalho
    principal onde você projeta workflows.

-   **Paleta de componentes:** À direita, a [paleta de componentes de
    design](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR) dá acesso a recursos de conectividade.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/project-designer_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/project-designer_annotated_pp.png" /></span>

Em vez de pastas, as operações são organizadas dentro de [workflows](https://success.jitterbit.com/display/CS/Workflows?showLanguage=pt_BR) para
ajudar a segregar diferentes partes do projeto. Você pode navegar pelo seu projeto usando o painel de projeto em
duas visões diferentes:

-   **Workflows:** Esta aba mostra as operações dentro de cada workflow, e os passos individuais que compõem cada
    uma delas, ou seja, as atividades, as transformações e os scripts.

-   **Componentes:** Esta aba mostra todos os componentes que existem dentro do projeto. Como ao usar pastas, você
    também pode organizar componentes dentro de [grupos
    customizados](https://success.jitterbit.com/display/CS/Component+Groups?showLanguage=pt_BR).

Dentro da aba **Workflows**, a estrutura de cada workflow é retratada dinamicamente com cada uma das operações sendo
numerada automaticamente com base em sua localização na hierarquia do workflow.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/design-studio_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/design-studio_annotated_pp.png" /></span>


## Estabelecendo Conectividade

No Design Studio, as conexões com dados consistem de conectores nativos, fontes, alvos, métodos de serviço web e
outras entidades, muitas das quais têm configurações e comportamentos únicos. Por exemplo, estruturas de dados são
herdadas dos conectores, mas definidas nas *transformations* para as fontes e os alvos.

O Cloud Studio oferece grandes avanços em conectividade. O Cloud Studio não apenas tem novos conectores, mas a
arquitetura dos conectores foi redefinida desde o início. O desenvolvimento de conectores foi padronizado para
torná-lo mais rápido e mais fácil para que qualquer um desenvolva conectores.

O [Connector SDK](https://developer.jitterbit.com/pt/connector-sdk/) que a Jitterbit usa para desenvolver novas
conectividades na plataforma agora é oferecido a desenvolvedores para que eles criem novos conectores para suas
organizações. Isto também nos permitiu criar o [Connector Builder](https://success.jitterbit.com/display/CS/Connector+BuildershowLanguage=pt_BR),
uma interface aponte-e-clique para que não-desenvolvedores preparem rapidamente conectividades novas e marcadas com
interfaces baseadas em REST.

Agora tanto os conectores que você cria quanto aqueles ofertados pela Jitterbit são consistentes, com todas as
conexões sendo configuradas usando conectores que são acessíveis da [paleta de componentes de
*design*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR). Veja
[Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR) para conhecer todos os conectores disponíveis no Cloud
Studio.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_design-studio_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_design-studio_annotated_pp.png" /></span>

Para estabelecer conectividade, comece usando um conector para criar uma conexão com o recurso. Quando uma conexão
estiver configurada, os tipos de atividade associados àquelas conexões podem então ser colocados em operações no
quadro de *design* e configurados como fontes ou alvos num projeto. Um *endpoint* refere-se a uma conexão específica
e às suas atividades.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/connectivity-terms_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/connectivity-terms_annotated_pp.png" /></span>


## Definindo *Schemas*

No Design Studio, as estruturas de dados fonte e alvo são definidas diretamente numa *transformation*, e não dentro
da fonte ou do alvo em si (exceto no caso de conectores de aplicação e métodos de serviço web SOAP).

Com o Cloud Studio, você agora tem a opção de definir um *schema* numa atividade, e ele será automaticamente herdado
pela *transformation*, ou então dentro da *transformation* em si.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/ftp_write_design-studio_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/ftp_write_design-studio_annotated_pp.png" /></span>

É importante reconhecer que embora as fontes e os alvos do Design Studio sejam chamados de atividades no Cloud
Studio, o conceito de atividades que são usadas como fontes ou alvos ainda existe. Isto é, uma atividade fonte é
qualquer atividade que forneça dados para uma operação, enquanto uma atividade alvo é qualquer atividade que receba
dados dentro de uma operação. No fim das contas, determinar se um *schema* é necessário ou não dependerá de caso a
atividade esteja sendo usada como fonte ou como alvo de uma *transformation*.


## Criando Operações

Para construir operações no Design Studio, você deve selecionar um tipo de operação, o que criará uma operação com
certos componentes pré-colocados para configuração. Embora sejam fáceis de usar, os tipos de operação têm
flexibilidade limitada.

Com o Cloud Studio, você agora pode popular cada operação diretamente com as atividades, *scripts* ou
*transformations* apropriadas. Isto proporciona maior flexibilidade para criar operações que atendam ao caso de uso
de negócio. Menus contextuais ajudam você a adicionar os componentes na ordem correta.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/design-studio_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/design-studio_annotated_pp.png" /></span>

Tanto no Design Studio quanto no Cloud Studio, você pode encadear operações mediante condições de sucesso ou falha.
No Cloud Studio, elas são chamadas de [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR).
Operações podem ser encadeadas entre workflows.


## Mapeamento de *Transformations*

No Design Studio, as *transformations* consistem de mapeamentos visuais entre campos alvo e fonte. Identificar a
lógica alvo, as variáveis, e os campos fonte mapeados exige verificar cada um dos campos, e identificar quais campos
fonte estão mapeados a um alvo exige esforço adicional.

O Cloud Studio introduz uma navegação mais fácil pelos mapeamentos, permitindo que você veja facilmente os detalhes
de mapeamento de todos os campos de uma vez, incluindo os campos fonte, as variáveis e a lógica de *script*, sem
cliques adicionais. Cada campo fonte indica o número de campos alvo mapeados, e provê acesso direto a tais campos.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/design-studio_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/design-studio_annotated_pp.png" /></span>

Além disso, você ainda tem acesso aos mesmos tipos de recursos robustos oferecidos pelo Design Studio, incluindo
[ver uma prévia de uma *transformation*](https://success.jitterbit.com/display/CS/Preview+Mode?showLanguage=pt_BR) e [criar mapeamentos
condicionais](https://success.jitterbit.com/display/CS/Conditional+Mapping?showLanguage=pt_BR). Recursos adicionais que estão disponíveis somente
no Cloud Studio incluem [espelhar um *schema*](https://success.jitterbit.com/display/CS/Mirrored+Schemas?showLanguage=pt_BR) de um lado da
*transformation* para outro, e a [exportação e importação de
mapeamentos](https://success.jitterbit.com/display/CS/Transformation+Mapping+Exports+and+Imports?showLanguage=pt_BR) com a habilidade de
selecionar quais mapeamentos usar se houver conflitos.


## Usando *Scripts*

No Design Studio, você pode usar *scripts* por todo o seu projeto para adicionar funcionalidades onde isso for
necessário, não importa se o *script* é usado como passo de uma operação, como lógica dentro de um campo alvo
mapeado, ou como condição num nó alvo para filtrar quais registros são processados.

O Cloud Studio tem o mesmo uso de tipos de *script* e continua usando a linguagem [Jitterbit
Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR), com o mesmo suporte a
[JavaScript](https://success.jitterbit.com/display/CS/JavaScript?showLanguage=pt_BR) que tem o Design Studio. No geral, os *scripts* são tratados
da mesma forma, com apenas algumas diferenças pequenas.

A maior diferença é a sintaxe de como os componentes de projeto são chamados nos *scripts*. For exemplo, no Design
Studio, uma referência a uma fonte FTP teria esta sintaxe:

```
&lt;TAG&gt;Sources/My FTP Source Name&lt;TAG&gt;
```

No Cloud Studio, o componente correspondente seria uma atividade FTP Read com a seguinte sintaxe:

```
&lt;TAG&gt;activity:ftp/My FTP Endpoint Name/ftp_read/My FTP Read Activity Name&lt;TAG&gt;
```

Esta diferença é importante se você estiver copiando manualmente o *script* de um projeto do Design Studio para o
Cloud Studio, já que essas referências teriam que ser substituídas (para mais detalhes, leia
[Endpoints](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR#JitterbitScript-connectors) no artigo [Jitterbit
Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR)).

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/script/transformation-script_design-studio_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/script/transformation-script_design-studio_annotated_pp.png" /></span>


## Implantando e Migrando

Enquanto você faz o *design* de um projeto no Design Studio, você pode implantar itens selecionados do projeto ou o
projeto inteiro e até migrar projetos de um ambiente para o outro.

Estes conceitos são a mesma coisa no Cloud Studio: você pode selecionar certos componentes de projeto para implantar
ou implantar o projeto inteiro (veja [Implantação de Projetos](https://success.jitterbit.com/display/CS/Project+DeploymentshowLanguage=pt_BR)).
Projetos também podem ser migrados entre ambientes (veja [Migração de
Projetos](https://success.jitterbit.com/display/CS/Project+Migration?showLanguage=pt_BR)).

(O termo "migração" refere-se a mover um projeto de um ambiente para o outro. Se, em vez disso, você quiser
*importar* um projeto exportado pelo Cloud Studio para o Cloud Studio, veja [Criando e Importando
Projetos](https://success.jitterbit.com/display/CS/Cloud+Studio+Overview+for+Design+Studio+Users?showLanguage=pt_BR#CloudStudioOverviewforDesignStudioUsers-importing) acima nesta mesma página).

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/deploy_design-studio_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_design-studio_annotated_pp.png" /></span>


## Treinamento Prático

Nós elaboramos um curso de treinamento introdutório sobre o Cloud Studio, oferecido no nosso sistema de aprendizagem
online na Jitterbit University. Com o tempo, nós vamos desenvolver material de curso avançado no Cloud Studio, assim
como fizemos para o Design Studio. Saiba mais em [Como Receber
Treinamento](https://success.jitterbit.com/display/DOC/Getting+Training?showLanguage=pt_BR).


## Melhorias Futuras

Nossos desenvolvedores do Cloud Studio trabalham num ciclo rápido que entrega atualizações frequentes para o Cloud
Studio, com funcionalidades adicionais oferecidas através de novos recursos, melhorias aos recursos existentes, e
conserto de falhas.

Estamos abertos a quaisquer ideias que você tenha para melhorias futuras! Se você tiver sugestões, por favor envie
uma solicitação no nosso [Portal de
Ideias](https://community.jitterbit.com/s/login/?startURL=%2Fs%2Fideas) e um membro do nosso time
de produtos vai te responder sobre o *status* da sua solicitação.
