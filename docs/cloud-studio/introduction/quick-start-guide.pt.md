[//]: # (Guia de Início Rápido com o Cloud Studio)
[//]: # (This is a translation of Version 48, published on November 9, 2021.)

## Introdução

Este guia é direcionado a novos usuários do [Cloud Studio](/display/CS/Cloud+Studio?showLanguage=pt_BR), a aplicação
para *design* de projetos baseada na Web da Jitterbit. Este guia explica todo o processo inicial básico,
demonstrando como criar um projeto novo a partir do zero, e também dá uma visão geral de conceitos de *design* de
projeto.

Se desejar um guia mais detalhado e mais completo, assim como um passo-a-passo, faça o curso [Introdução ao
Jitterbit Harmony Cloud Studio](/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio?showLanguage=pt_BR)
na [Jitterbit University](/display/DOC/Getting+Training?showLanguage=pt_BR) (em inglês). Como parte deste curso,
você também pode consultar o [Manual de Apoio do Treinamento
Prático](/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio#IntroductiontotheJitterbitHarmonyCloudStudio-manual?showLanguage=pt_BR),
um material complementar que traz uma série de casos de uso para ajudar você a começar.

O [Jitterbit Marketplace](/display/DOC/Marketplace?showLanguage=pt_BR) também contém centenas de projetos
pré-construídos. Ele oferece [Protótipos de Integração do Cloud
Studio](/display/CS/Cloud+Studio+Integration+Recipes?showLanguage=pt_BR) e [*Templates* de Processo do Cloud
Studio](/display/CS/Cloud+Studio+Process+Templates?showLanguage=pt_BR). Para começar com um protótipo de integração
ou *template* já existente, veja [Iniciando um Projeto com um Protótipo de Integração ou *Template* de
Processo](/display/DOC/Starting+a+Recipe+or+Template+Project?showLanguage=pt_BR).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">
  <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>
  <div class="confluence-information-macro-body">

    <strong>NOTA:</strong> Antes de fazer o* design *de um projeto, você precisa já ter se cadastrado no Jitterbit
    Harmony e preparado um ambiente e um Agent Group, como descrito no <a
    href="/display/DOC/Jitterbit+Admin+Quick+Start+Tutorial?showLanguage=pt_BR">Tutorial de Início Rápido do
    Jitterbit Admin</a>.

  </div>
</div>


## <span id="CloudStudioQuickStartGuide-access-cloud-studio" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Acessando o Cloud Studio

O Cloud Studio é acessado diretamente pelo [Jitterbit Harmony
Portal](/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR).

Na página inicial do Harmony Portal, clique no cartão da aplicação **Cloud Studio**:

![](https://docs-source.jitterbit.com/hp/landing/card_cloud-studio.png)

O Cloud Studio abre no índice de projetos, onde você poderá criar o seu primeiro projeto.


## Criando um Projeto

O índice de projetos mostra um repositório contendo todos os seus projetos no Cloud Studio. Na primeira vez em que
você acessar o Cloud Studio, esta tela estará vazia. Clique em **New Project** (Novo Projeto) para começar:

![](https://docs-source.jitterbit.com/cs/project-index/no-projects.png)

Preencha as informações básicas sobre o seu projeto e depois clique em **Start Designing** (Começar o *Design*) para
abrir o *designer* de projetos.

![](https://docs-source.jitterbit.com/cs/project/project_new_start.png)


## <span id="CloudStudioQuickStartGuide-design-your-project" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Fazendo o *Design* de um Projeto

O *designer* de projetos é a interface onde você constrói um projeto. O *designer* de projetos inclui a barra de
ferramentas de projeto, o painel de projeto, o design canvas, e uma paleta de componentes, bem como as telas de
configuração de cada um dos componentes, tais como das *transformations*, dos *scripts*, das conexões e das
atividades.

Ao abrir um projeto, estas partes do *designer* de projetos são exibidas, como mostrado no exemplo abaixo, que é de
um projeto cujo *design* já está feito.

![](https://docs-source.jitterbit.com/cs/project/project-designer_annotated_pp.png)

Geralmente, fazemos o *design* de workflows - ou seja, coleções de operações agrupadas para a conveniência do
usuário - dentro do design canvas usando as ferramentas oferecidas na paleta de componentes, no painel do projeto e
no design canvas em si.

As próximas seções percorrem o processo de *design* básico:

1.  [Estabelecendo Conectividade](#CloudStudioQuickStartGuide-establish-connectivity)

2.  [Criando Etapas de Operação](#CloudStudioQuickStartGuide-create-operation-steps)

3.  [Encadeando Operações Usando Ações de Operação](#CloudStudioQuickStartGuide-chain-operations)

4.  [Implementando e Executando Operações](#CloudStudioQuickStartGuide-deploy-and-run)

### <span id="CloudStudioQuickStartGuide-establish-connectivity" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Estabelecendo Conectividade

A [paleta de componentes de *design*](/display/CS/Design+Component+Palette?showLanguage=pt_BR) dá acesso a recursos
de conectividade. Aqui, *conectores* oferecem a interface para a inserção de entradas dadas pelo usuário, como
credenciais, para criar uma conexão. Dentro da paleta de componentes, o filtro **Connectors** (Conectores) mostra os
tipos de conectores que podem ser configurados:

![](https://docs-source.jitterbit.com/cs/project/connectors_annotated_pp.png)

Cada conector é representado por um ícone de pasta de conectores, e abaixo do ícone fica o nome do conector. Clique
em qualquer conector para abrir uma tela de configuração e criar uma nova conexão para acessar um recurso de dados
em específico:

![](https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_http_multiple.png)

Para ver instruções detalhadas sobre como configurar uma conexão, veja a conexão específica em
[Conectores](/display/CS/Connectors?showLanguage=pt_BR). Cada vez que você criar uma nova conexão, deverá fazer isso
nos ícones de pasta de conectores, acessíveis no filtro **Connectors**.

Quando você tiver criado uma conexão, ela aparecerá no filtro **Endpoints**. Clique em uma conexão para revelar os
tipos de atividades - interações com um *endpoint* - que podem ser configurados para aquela conexão.

![](https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_http_activities.png)

Um *endpoint* refere-se a uma conexão específica e às suas atividades, que são configuradas como fontes (provendo
dados) ou como alvos (recebendo dados) em um projeto. Como referência, o diagrama abaixo mostra a relação entre os
conectores, as conexões, as atividades e os *endpoints*:

![](https://docs-source.jitterbit.com/cs/project/connectivity-terms_annotated_pp.png)

### <span id="CloudStudioQuickStartGuide-create-operation-steps" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Criando Etapas de Operação {#CloudStudioQuickStartGuide-create-operation-steps}

Operações que definem o que a integração deve fazer são criadas mediante a adição e a configuração de etapas de
operação - compostos de atividades, *transformations* e/ou *scripts* - no quadro de *design*.

A seção [Estabelecendo Conectividade](#CloudStudioQuickStartGuide-establish-connectivity), acima, mostra como criar
uma conexão e ver os seus tipos de atividade.

Para criar uma instância de uma atividade, coloque um tipo de atividade no design canvas. Você pode fazer isso ao
arrastá-la e soltá-la, ou ao copiá-la para dentro de uma operação ou de uma área de inserção de componentes.

![](https://docs-source.jitterbit.com/cs/project/create-activity-instance.gif)

Quando uma atividade estiver criada, você pode dar um duplo clique sobre ela para configurá-la, de acordo com a
descrição de cada atividade específica encontrada em [Conectores](/display/CS/Connectors?showLanguage=pt_BR).

Você também pode querer adicionar *transformations* ou *scripts* a uma operação. As *transformations* são usadas
quando você quer transformar dados antes que eles cheguem ao seu alvo. Os *scripts* podem ser usados dentro das
*transformations* em um campo ou um nó alvo para aplicar uma lógica específica ou certas condições a um dado. Os
*scripts* também podem ser usados como passos opcionais dentro de uma operação para uma série de propósitos, como
manejamento de erros ou para iterar sobre registros de dados.

Para adicionar uma nova *transformation* ou *script* diretamente a uma operação, clique com o botão direito ou
clique no menu de ações sobre uma área de inserção de componentes e selecione **New Script** (Novo *Script*) ou
**New Transformation** (Nova *Transformation*):

![](https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component_actions-menu.png)

Quando você adiciona um *script* ou uma *transformation*, a tela de configuração dele abre automaticamente. Para
mais detalhes sobre estas configurações, leia [Scripts](/display/CS/Scripts?showLanguage=pt_BR) e
[Transformations](/display/CS/Transformations?showLanguage=pt_BR), respectivamente.

### span id="CloudStudioQuickStartGuide-chain-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Encadeando Operações Usando Ações de Operação

Depois que mais de uma operação estiver criada, você pode configurar ações de operação para que elas disparem a
execução de outras operações, enviem e-mails, ou escrevam mensagens no registro depois do sucesso ou da falha de uma
operação.

Para configurar estas ações, clique no menu de ações, no ícone
![](https://docs-source.jitterbit.com/common/icons/actions-menu_21.png) na parte superior direita de uma operação e
selecione **Settings** (Configurações):

![](https://docs-source.jitterbit.com/cs/design-canvas/operation_settings.png)

Na aba **Actions** (Ações) das configurações, selecione a condição que deverá dar início à ação, qual ação deverá
ser tomada, bem como quaisquer parâmetros adicionais que forem necessários, como qual outra operação deve ser
configurada para executar. Para mais detalhes, veja [Ações de
Operação](/display/CS/Operation+Actions?showLanguage=pt_BR).

Quando estas ações estiverem configuradas, vão aparecer linhas no design canvas para indicar visualmente todas as
ações que estão configuradas para executar em caso de sucesso (linha verde) ou falha (linha vermelha) da operação.
Quando uma operação é iniciada com base em ações de operação, dizemos que ela está abaixo da outra na cadeia.

![](https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script.png)

### <span id="CloudStudioQuickStartGuide-deploy-and-run" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Implantando e Executando Operações

Depois que você desenvolve uma cadeia de operações, você a implanta em um Harmony Agent e a executa. Para implantar
e executar uma operação, clique no ícone implantar-e-executar
![](https://docs-source.jitterbit.com/common/icons/deploy-and-run.png) na parte superior direita da operação:

![](https://docs-source.jitterbit.com/cs/design-canvas/operation_deploy-and-run.png)

Quaisquer operações que estiverem abaixo na cadeia que está sendo implantada e executada também serão incluídas.

Em vez da execução manual, você também pode configurar operações para serem executadas mediante agendamento ou
mediante um gatilho de API. Para mais informações, veja [Implantação e Execução de
Operações](/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR).

Depois que as operações são executadas, você pode confirmar se o comportamento delas está correto verificando os
registros. Para ver os registros de uma operação em particular e todas as que estão abaixo dela na cadeia, clique no
ícone do menu de ações ![](https://docs-source.jitterbit.com/common/icons/actions-menu_21.png), na parte superior
direita de uma operação, e selecione **View Logs** (Ver Registros). Para mais informações, veja [Registros de
Operação](/display/CS/Operation+Logs?showLanguage=pt_BR).

Para incluir atividades adicionais, coloque-as em outra área de inserção. Áreas de inserção de operação adicionais
são mostradas quando você paira o mouse sobre uma operação existente. Áreas de inserção de componentes em operações
existentes são mostradas pairando o mouse à esquerda ou à direita das etapas de operação existentes. Uma
configuração comum é configurar uma atividade como a fonte de dados, e uma segunda atividade à direita desta como o
alvo de dados.


## Recursos Adicionais

Quando você estiver fazendo o *design* de um projeto, use como referência as informações aprofundadas organizadas
por tópico em [Cloud Studio](/display/CS/Cloud+Studio?showLanguage=pt_BR):

-   **[Projetos](/display/CS/Projects?showLanguage=pt_BR)**: Aprenda o básico sobre permissões de projeto,
    colaboração, salvamentos e também sobre como criar, configurar, implantar, migrar, exportar, importar e deletar
    projetos.

-   **[Componentes de Projeto](/display/CS/Project+Components?showLanguage=pt_BR)**: Navegue por informações sobre
    quais componentes de projeto existem e quais ações compartilhadas você pode tomar com cada componente.

-   **[Workflows](/display/CS/Workflows?showLanguage=pt_BR)**: Encontre informações sobre como criar, implantar e
    deletar workflows, dependências, e o que torna um workflow válido.

-   **[Operações](/display/CS/Operations?showLanguage=pt_BR)**: Detalhes sobre a criação de operações; como ajustar
    configurações de operações, tais como ações, opções e agendas; como ver os registros de operações; como
    implantar e executar operações; ver dependências e deletar operações; e o que torna uma operação válida.

-   **[Conectores](/display/CS/Connectors?showLanguage=pt_BR)**: Consulte a documentação específica sobre
    *endpoints*, em assuntos como a configuração de conexões e atividades que se conectam e interagem com um
    *endpoint* específico.

-   **[Transformations](/display/CS/Transformations?showLanguage=pt_BR)**: Leia sobre o básico e aprenda as
    complexidades sobre mapear entradas de dados para as saídas alvo desejadas.

-   **[Schemas](/display/CS/Schemas?showLanguage=pt_BR)**: Conheça os vários tipos de *schemas* e aprenda como
    distinguir a melhor hora de usá-los.

-   **[Scripts](/display/CS/Scripts?showLanguage=pt_BR)**: Descubra a flexibilidade e o poder dos *scripts* para
    transformar dados, executar cálculos, ou fazer validação lógica dentro de operações e *transformations*.

-   **[Funções](/display/CS/Functions?showLanguage=pt_BR)**: Busque descrições e exemplos de funções que podem ser
    usadas em *scripts* para melhorar e refinar processos de dados.

-   **[Variáveis](/display/CS/Variables?showLanguage=pt_BR)**: Veja os diferentes tipos de variáveis e como elas
    podem ajudar você a ser mais eficiente ao fazer o *design* de um projeto.

-   **[Notificações](/display/CS/Notifications?showLanguage=pt_BR)**: Veja como customizar mensagens de e-mail que
    podem ser acionadas pelo sucesso ou pela falha de uma operação ou chamadas por um *script*.

-   **[Plugins](/display/CS/Plugins?showLanguage=pt_BR)**: Saiba mais sobre como você pode expandir as capacidades
    nativas do Harmony usando *plugins* providos pela Jitterbit ou por usuários.

Usuários avançados também podem se interessar em criar seus próprios conectores para o Cloud Studio usando o
[Connector Builder](/display/CS/Connector+Builder?showLanguage=pt_BR) da Jitterbit ou o [Connector
SDK](https://developer.jitterbit.com/pt/connector-sdk/).
