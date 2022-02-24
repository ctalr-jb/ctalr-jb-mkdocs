[//]: # (Design Canvas)
[//]: # (This is a translation of Version 21, published on November 9, 2021.)

## Introdução

O design canvas é a área central quando você abre um projeto que serve
como o espaço de trabalho primário onde você faz o *design* de
integrações visualmente. Esta página cobre elementos da interface de
usuário que estão presentes no design canvas, assim como conceitos chave
que devem ser entendidos ao trabalhar no design canvas.

Para acessar o design canvas, primeiro [abra um projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR). Em um
projeto aberto, o design canvas é a área central localizada à direita do
[painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane?showLanguage=pt_BR) e à esquerda da [paleta de componentes](https://success.jitterbit.com/display/CS/Component+Palette?showLanguage=pt_BR),
abaixo da [barra de ferramentas de projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR):

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/project-designer_design-canvas_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/project-designer_design-canvas_annotated_pp.png" /></span>

## Cabeçalho do Design Canvas

Os seguintes elementos estão presentes ao longo do topo do design
canvas:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/header.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/header.png" /></span>

-   **Abas dos Workflows**: Os workflows são acessados por abas ao longo
    do topo do design canvas. Workflows adicionais podem ser criados
    clicando no ícone de novo workflow
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/add_4.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/add_4.png"
    height="16" /></span>.
    O novo workflow abre em uma aba dentro do design canvas. Os
    workflows são numerados sequencialmente na ordem em que são
    criados, como 1.0, 2.0, 3.0, etc. Se você reordenar os workflows,
    esta sequência numérica se ajusta automaticamente (veja
    [Reordenando Workflows](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design?showLanguage=pt_BR#WorkflowCreationandDesign-reordering-workflows) em [Criação e Design de
    Workflows](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design?showLanguage=pt_BR)).

-   ***Status* de Salvamento**: O *status* do salvamento automático é
    mostrado no lado superior esquerdo do design canvas. Os seguintes
    *status* estão disponíveis:

    -   **Saved** (Salvo): Todos os itens do projeto estão salvos da
        forma como estão configurados atualmente.

    -   **Saving** (Salvando): O projeto está sendo salvo atualmente.
        Este *status* ocorre apenas depois que mudanças tiverem sido
        feitas.

-   **Last Deployed** (Implantado pela Última Vez): A data e a hora da
    implantação mais recente de qualquer parte do projeto é exibida.
    Se nenhuma parte do projeto tiver sido implantada ainda, nada será
    mostrado aqui.

-   **Collapse All Operations** (Esconder Todas as Operações) **ou
    Expand All Operations** (Expandir Todas as Operações): Alterna a
    exibição de todas as operações dentro do workflow atual entre uma
    visualização condensada ou expandida (veja [Expandindo ou
    Escondendo Operações](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR#OperationCreationandConfiguration-expanding-or-collapsing) em [Criação e Configuração de
    Operações](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR)).

-   **Highlight Invalid Items** (Destacar Itens Inválidos): Alterna a
    exibição de itens inválidos (veja [Validade de Workflows](https://success.jitterbit.com/display/CS/Workflow+Validity?showLanguage=pt_BR),
    [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR) ou [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR),
    respectivamente).

-   **Actions** (Ações): Clique no ícone do menu de ações
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_18.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_18.png"
    height="8" /></span> para abrir
    o menu de ações do design canvas (veja [Menu de Ações do Design
    Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-deploy-migrate-actions-menu) mais abaixo nesta página).

## <span id="DesignCanvas-design-canvas-elements" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Elementos do Design Canvas

A função primária do design canvas é ter um espaço de trabalho onde você
possa fazer o *design* de workflows visualmente. Cada workflow é
composto de uma coleção de operações que é usada como ferramenta para a
sua conveniência para ajudar a segregar diferentes partes do projeto.

Os workflows são projetados ao se colocar e configurar operações no
design canvas. Os elementos do design canvas são os itens que aparecem
visualmente no design canvas para te ajudar a fazer o *design* de um
workflow, incluindo os seguintes:

-   [Área de inserção](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-drop-zones) para operações e para outros componentes
    usados como etapas de operação

-   [Operações](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-operations) e os componentes usados como etapas de operação
    dentro deles

-   [Notificações](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-notifications) que são acionadas a partir de operações

-   [Referências de operações](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-external-operations) que estão fora do workflow atual mas
    que são acionadas a partir de uma operação do workflow atual

-   [Linhas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-lines) que conectam as operações, *scripts* e notificações
    interligados

Cada um destes elementos do design canvas é descrito abaixo. Para
informações adicionais sobre como fazer o *design* de workflows, veja
[Criação e Design de Workflows](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design?showLanguage=pt_BR).

### <span id="DesignCanvas-drop-zones" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Áreas de Inserção

Uma área de inserção é uma representação visual de onde uma operação ou
outro componente pode ser colocado no design canvas. Existem dois tipos
de áreas de inserção; áreas de inserção de operação e áreas de inserção
de componente:

-   **Área de inserção de operação**: Áreas de inserção de operação
    indicam onde uma operação pode ser colocada. Uma área de inserção
    de operação é permanentemente mostrada no fundo do design canvas
    depois da última operação. Para mostrar áreas de inserção de
    operação adicionais, paire o mouse acima das operações existentes.
    Quando você clica para selecionar uma área de inserção de
    operação, ela é mostrada com uma borda roxa contornando a área de
    inserção e permanece selecionada até você mudar o foco:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_operation.gif"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_operation.gif" /></span>

-   **Área de inserção de componente**: Área de inserção de componentes
    indicam onde outros componentes que podem ser usados como passos
    de operação podem ser colocados numa operação existente. Para
    mostrar uma área de inserção de componentes, paire o mouse à
    esquerda ou à direita de um passo de operação em uma operação
    existente no design canvas. Quando você clica para selecionar uma
    área de inserção de componentes, ela é mostrada com uma borda roxa
    contornando a área de inserção e permanece selecionada até você
    mudar o foco:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component.gif"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component.gif" /></span>

Um menu de ações está disponível em toda área de inserção. Tanto as
áreas de inserção de operação quanto as áreas de inserção para outros
componentes mostram os mesmos itens no menu, conforme descritos em
[Menu de Ações da Área de Inserção](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-drop-zone-actions-menu), mais abaixo nesta mesma
página.

### <span id="DesignCanvas-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="DesignCanvas-operation-toolbar" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operações

Operações são representadas visualmente no design canvas por uma área
retangular dinâmica com fundo cinza:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_magento.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_magento.png" /></span>

-   **Título da Operação**: O título da operação aparece no canto
    superior esquerdo de uma operação e consiste do número e nome da
    operação:

    -   **Número da Operação**: Um número único que é atribuído
        automaticamente dependendo de onde a operação aparece em um
        workflow. Os workflows são automaticamente numerados
        sequencialmente começando com o número `1.0` e aumentando em
        intervalos de `1.0` para cada workflow que se segue (`1.0`, `2.0`,
        `3.0`, etc). Dentro de um workflow, as operações também recebem
        automaticamente um número decimal, começando com `.0` e
        aumentando em intervalos de `.1` para cada operação que se
        segue. Para ver exemplos, consulte [Fazendo o *Design* de um
        Workflow](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design?showLanguage=pt_BR#WorkflowCreationandDesign-designing-a-workflow) em [Criação e *Design* de Workflows](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design?showLanguage=pt_BR).

    -   **Nome da Operação**: O nome da operação, escolhido pelo
        usuário. Quando você cria uma nova operação, o nome padrão é
        *New Operation.* Novas operações seguintes com o nome padrão
        recebem também um número incrementado entre parênteses. Nomes
        de operações devem ser únicos e não podem conter barras (`/`)
        nem dois pontos (`:`) para serem válidos. Para renomear uma
        operação, veja [Renomeando Workflows, Operações e Etapas de
        Operações](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-renaming) mais à frente nesta mesma página.

-   **Barra de Ferramentas de Operação**: A barra de ferramentas de
    operação aparece no lado superior direito de uma operação e
    consiste da seguinte lista de itens:

    <div class="table-wrap">

    <table class="wrapped confluenceTable">
    <tbody>
    <tr class="header header">
    <td class="highlight-grey confluenceTd"
    data-highlight-colour="grey"><strong>Ícone</strong></td>
    <td class="highlight-grey confluenceTd"
    data-highlight-colour="grey"><strong>Descrição</strong></td>
    </tr>
    <tr class="odd odd">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/schedules.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/schedules.png" /></span></p>
    </div></td>
    <td class="confluenceTd"><p>Abre a aba <strong>Schedules</strong> (Agendas) das configurações
    de operação (veja <a
    href="https://success.jitterbit.com/display/CS/Operation+Schedules">Agendas de Operação</a>).</p>
    <p>Este ícone é mostrado apenas quando uma operação já tem uma agenda
    atribuída.</p></td>
    </tr>
    <tr class="header header">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/deploy.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/deploy.png" /></span></p>
    </div></td>
    <td class="confluenceTd">Implanta a operação e quaisquer componentes dos quais ela dependa
    (veja <a
    href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution#OperationDeploymentandExecution-deploy">Implantando</a> em <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e Execução de
    Operações</a>).</td>
    </tr>
    <tr class="odd odd">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/deploy-and-run.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/deploy-and-run.png" /></span></p>
    </div></td>
    <td class="confluenceTd">Abre a tela de implantação, onde você pode selecionar componentes de
    projeto para implantar (veja <a
    href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution#OperationDeploymentandExecution-deploy">Implantando</a> em <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e
    Execução de Operações</a>).</td>
    </tr>
    <tr class="header header">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/collapse.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/collapse.png" /></span></p>
    </div></td>
    <td class="confluenceTd"><p>Esconde a operação em uma visualização menor, mais condensada
    (veja <a
    href="https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration#OperationCreationandConfiguration-expanding-or-collapsing">Expandindo ou Escondendo Operações</a> em <a
    href="https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration">Criação e
    Configuração de Operações</a>).</p>
    <p>Este ícone só aparece quando a operação está expandida.</p></td>
    </tr>
    <tr class="odd odd">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/expand.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/expand.png" /></span></p>
    </div></td>
    <td class="confluenceTd"><p>Expande a operação para que ela fique com o tamanho padrão (veja
      <a
      href="https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration#OperationCreationandConfiguration-expanding-or-collapsing">Expandindo ou Escondendo Operações</a> em <a
      href="https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration">Criação e Configuração
    de Operações</a>).</p>
    <p>Este ícone só aparece quando a operação está escondida.</p></td>
    </tr>
    <tr class="header header">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    height="6" /></span></p>
    </div></td>
    <td class="confluenceTd">Abre o <a
    href="https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-operation-actions-menu">menu de ações de operação</a>, descrito mais à frente
    nesta mesma página.</td>
    </tr>
    </tbody>
    </table>

    </div>

-   **Etapas de Operação**: Toda operação que já foi configurada com
    etapas de operação inclui uma representação visual dessas etapas.
    Cada etapa é representada por um quadrado mostrando um ícone que
    representa o componente, abaixo do qual fica o nome do componente.

    -   **Menu de Ações**: Toda etapa de operação tem um menu de ações
        que é acessível com um clique com o botão direito em cima da
        etapa de operação ou usando o ícone do menu de ações
        <span
        class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
        src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
        class="confluence-embedded-image confluence-external-resource"
        data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
        height="18" /></span>.
        Cada item do menu é descrito em [Menu de Ações de
        Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) mais à frente nesta mesma página.

    -   **Ícone de *Plugin***: Atividades que foram configuradas com um
        *plugin* que é executado junto com a operação exibem um ícone
        de *plugin*
        <span
        class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/plugin.png"
        class="confluence-embedded-image confluence-external-resource"
        data-image-src="https://docs-source.jitterbit.com/common/icons/plugin.png"
        height="24" /></span>
        no canto superior direito da etapa de operação. Para mais
        informações, veja [*Plugins* Adicionados a uma
        Atividade](https://success.jitterbit.com/display/CS/Plugins+Added+to+an+Activity?showLanguage=pt_BR).

-   ***Status* da Operação**: Depois que uma operação foi submetida com
    sucesso à fila de operações, o *status* da operação em tempo real
    é informado no canto inferior esquerdo de uma operação. Para mais
    detalhes, veja [*Status* da Operação](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR#OperationDeploymentandExecution-operation-status) em [Implantação e
    Execução de Operações](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR).

#### Selecionando Operações e Passos de Operação

Para selecionar uma operação, clique no fundo da operação. Uma operação
selecionada é exibida com uma borda roxa destacando-a. Neste exemplo,
toda a operação *Upsert Postgres Products* foi selecionada:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_selected.png" /></span>

Para selecionar uma etapa de operação, clique na representação visual da
etapa. Uma etapa de operação selecionada é mostrada com uma borda roxa
destacando o componente. Neste exemplo, a transformação *Magento
Products to Postgres* está selecionada:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_selected.png" /></span>

### <span id="DesignCanvas-notifications" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Notificações

Uma representação visual de uma notificação aparece automaticamente no
design canvas quando você liga uma notificação de e-mail usando a
[ação de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) **Enviar Notificação por E-mail**. Informação
adicional sobre a exibição visual de links é dada mais à frente, debaixo
do subtítulo [Linhas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-lines).

A notificação de e-mail é exibida com um fundo cinza. Dentro da área de
fundo, a notificação de e-mail é representada por um quadrado mostrando
um ícone, abaixo do qual fica o nome da notificação de e-mail. Para
selecionar uma notificação de e-mail, clique na representação visual
dela. Uma notificação de e-mail selecionada é mostrada com uma borda
roxa destacando o componente:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/notification_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/notification_selected.png" /></span>

Para ver as ações de menu disponíveis numa notificação de e-mail, veja
[Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu)  mais à frente nesta mesma página.

### <span id="DesignCanvas-external-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Referências de Operação

Operações que existem fora do workflow atual podem ser referenciadas a
partir de uma operação dentro do workflow atual. Quando uma ligação
assim é feita, uma representação visual da operação externa aparece
automaticamente no design canvas no workflow atual. Informações
adicionais sobre a exibição visual de links são dadas mais à frente,
abaixo do subtítulo [Linhas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-lines).

A referência de operação é mostrada com um fundo cinza e contém ícones
de formas que servem como representação geral das etapas de operação.

Uma operação que não existe em outro workflow é mostrada apenas com o
nome da operação:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_reference.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_reference.png" /></span>

Uma operação que existe em outro workflow é exibida com o nome do
workflow, seguida pelo nome da operação. Clique nas palavras para abrir
o workflow no qual a operação existe:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_reference_workflow.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_reference_workflow.png" /></span>

### <span id="DesignCanvas-lines" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Linhas

Linhas que conectam operações, scripts e notificações interligadas
aparecem automaticamente no design canvas. As ligações podem ser criadas
usando [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) ou usando a função `RunOperation`.

A cor e a posição das linhas indicam o significado delas. Exemplos
dessas linhas são dados abaixo das seguintes descrições:

-   **Verde**: Linhas verdes são mostradas sob a condição **Em caso de
    sucesso** e aparecem à esquerda das operações ou e-mails
    interligados.

-   **Vermelho**: Linhas vermelhas são mostradas sob a condição **Em
    caso de falha** e aparecem à direita das operações ou e-mails
    interligados.

-   **Laranja**: Linhas laranjas são mostradas sob a condição **Em caso
    de erro SOAP** e aparecem à direita das operações ou e-mails
    interligados.

-   **Cinza**: Linhas cinzas são mostradas para operações chamadas de um
    *script* que está usando a função `RunOperation`.

#### Em caso de sucesso

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain.png" /></span>

#### Em caso de falha

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_email.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_email.png" /></span>

#### Em caso de erro SOAP

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_soap-fault.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_soap-fault.png" /></span>

#### Função `RunOperation`

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_runoperation.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_runoperation.png" /></span>


## Menus de Ações

Menus de ações acessíveis a partir do design canvas incluem aqueles do
design canvas, dos componentes, e das áreas de inserção.

### <span id="DesignCanvas-deploy-migrate-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Menu de Ações do Design Canvas

Clique no ícone do menu de ações
<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/actions-menu_18.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_18.png"
height="8" /></span> no canto
superior direito do design canvas para abrir um menu com as seguintes
ações:

<div class="table-wrap">

<table class="wrapped confluenceTable">
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
src="https://docs-source.jitterbit.com/cs/menu-items/undo.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/undo.png"
height="33" /></span></p>
<p><em>Desfazer</em></p>
</div></td>
<td class="confluenceTd"><strong>Undo</strong> reverte a sua última ação.</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/redo.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/redo.png"
height="33" /></span></p>
<p><em>Refazer</em></p>
</div></td>
<td class="confluenceTd"><strong>Redo</strong> reverte a sua última ação
<strong>Undo</strong>.</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
height="33" /></span></p>
<p><em>Implantar</em></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
height="67" /></span></p>
<p><em>Implantar</em></p>
<p><em>Implantação Configurável</em></p>
</div></td>
<td class="confluenceTd"><p><strong>Deploy</strong> mostra as seguintes ações de menu:</p>
<ul>
<li>
<p><strong>Deploy</strong>: Implanta o projeto inteiro (veja
  <a
  href="https://success.jitterbit.com/display/CS/Project+Deployment">Implantação de Projetos</a>).</p>
</li>
<li>
<p><strong>Configurable Deploy</strong>: Abre a tela de implantação de
projeto, onde você pode selecionar componentes para implantar (veja
  <a
  href="https://success.jitterbit.com/display/CS/Project+Deployment">Implantação de Projetos</a>).</p>
</li>
</ul></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/migrate.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/migrate.png"
height="33" /></span></p>
<p><em>Migrar</em></p>
</div></td>
<td class="confluenceTd"><strong>Migrate</strong> abre a tela de migração de projeto, onde
você pode escolher o ambiente alvo (veja <a
href="https://success.jitterbit.com/display/CS/Project+Migration">Migração de
Projetos</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/project-history.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/project-history.png"
height="33" /></span></p>
<p><em>Histórico do Projeto</em></p>
</div></td>
<td class="confluenceTd"><strong>Project History</strong> abre um painel do lado direito do
<em>designer</em> de projeto onde você pode ver eventos da história do
projeto, etiquetar eventos e restaurar projetos (veja <a
href="https://success.jitterbit.com/display/CS/Project+History">Histórico de
Projetos</a>).</td>
</tr>
</tbody>
</table>

</div>

### <span id="DesignCanvas-component-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Menu de Ações de Componente

Para abrir o menu de ações de uma operação, faça uma das seguintes
opções:

-   Clique com o botão direito do mouse sobre a [barra de ferramentas
    de operação](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-operation-toolbar).

-   Clique sobre o ícone do menu de ações
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    height="6" /></span> no lado
    superior direito de uma operação.

Para abrir o menu de ações de outro componente no design canvas,
incluindo as etapas de operação (atividades, *transformations* ou
*scripts*) e notificações de e-mail, faça uma das seguintes opções:

-   Clique com o botão direito do mouse sobre a etapa de operação ou a
    notificação de e-mail.

-   Paire o mouse sobre a etapa de operação ou a notificação de e-mail,
    e daí clique no ícone do menu de ações
    <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
    height="15" /></span>.

Algumas ações estão disponíveis apenas em certos tipos de componentes,
como detalhado nas subseções abaixo:

-   **[Operations](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-operations)** (Operações): O menu de ações das operações
    (mostrado na primeira imagem) tem itens únicos tais como
    **Settings** (Configurações), **Duplicate** (Duplicar), **Run**
    (Executar), **View Logs** (Ver registros), **Rename** (Renomear),
    **View Dependencies** (Ver Dependências), **Add to group**
    (Adicionar ao Grupo) e **Delete** (Deletar), bem como sub-menus
    únicos em **Deploy** (Implantar). Ele também inclui ações comuns
    como **Cut** (Recortar), **Copy** (Copiar) e **Remove** (Remover).

-   **[Activities, Scripts, Transformations, and Email
    Notifications](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-share)** (Atividades, *Scripts*, *Transformations* e
    Notificações de E-mail): Os menus de ações desses componentes
    compartilham as mesmas ações, incluindo **View/Edit**
    (Ver/Editar), **Cut** (Recortar), **Copy** (Copiar), **Deploy**
    (Implantar) e **Remove** (Remover) mostrados num menu de ações de
    atividade na segunda imagem.

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Menu de Ações de Operação**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Menu de Ações de Atividade**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:5%;min-width:5%;max-width:5%;" hasbody="true"
macro-name="column">

</div>

</div>

</div>

</div>

#### <span id="DesignCanvas-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operations

Estes itens estão disponíveis no menu de ações de uma operação:

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
<p><strong><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/settings.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/settings.png"
height="33" /></span></strong></p>
<p><em>Configurações</em></p>
</div></td>
<td class="confluenceTd"><p><strong>Settings</strong> abre as configurações de operação, que
contém três abas:</p>
<ul>
<li>
<p><strong>Schedules</strong> (Agendas): Criar e aplicar agendas a
operações executadas automaticamente (veja <a
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
<p><em>Recortar</em></p>
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
<p><em>Copiar</em></p>
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
<p><em>Duplicar</em></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu_with-step-references_with-step-copies.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu_with-step-references_with-step-copies.png"
height="67" /></span></p>
<p><em>Com Referências aos Passos</em></p>
<p><em>Com Cópias dos Passos</em></p>
</div></td>
<td class="confluenceTd"><p><strong>Duplicate</strong> mostra as seguintes ações de menu
(veja <a href="https://success.jitterbit.com/display/CS/Operation+Reuse">Reuso de Operações</a>):</p>
<ul>
<li>
<p><strong>With Step References</strong>: Duplica apenas a operação. A
operação duplicata contém referências a cada um dos passos da operação
original.</p>
</li>
<li>
<p><strong>With Step Copies</strong>: Duplica a operação e os
componentes referenciados como passos de operação. Novos componentes são
criados para cada passo de operação e são referenciados pela
original.</p>
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
<p><em>Implantar</em></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_deploy-and-run_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_deploy-and-run_configurable-deploy.png"
height="101" /></span></p>
<p><em>Implantar</em></p>
<p><em>Implantar e Executar</em></p>
<p><em>Implantação Configurável</em></p>
</div></td>
<td class="confluenceTd"><p><strong>Deploy</strong> mostra as seguintes ações de menu:</p>
<ul>
<li>
<p><strong>Deploy</strong>: Implanta a operação, bem como quaisquer
componentes dos quais ela dependa (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação e Execução de
Operações</a>).</p>
</li>
<li>
<p><strong>Deploy and Run</strong>: Implanta e executa a operação, bem
como quaisquer operações (ligadas) abaixo dela na cadeia (veja
  <a
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
<p><em>Executar</em></p>
</div></td>
<td class="confluenceTd"><strong>Run</strong> abre uma operação já implantada bem como
quaisquer operações (ligadas) abaixo dela na cadeia (veja <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Implantação
e Execução de Operações</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
height="33" /></span></p>
<p><em>Ver Registros</em></p>
</div></td>
<td class="confluenceTd"><strong>View Logs</strong> contém a tela de registros de operação,
que inclui registros desta operação e de quaisquer operações-filha que
tenham sido implantadas e executadas (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Logs">Registros de
Operação</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
height="33" /></span></p>
<p><em>Renomear</em></p>
</div></td>
<td class="confluenceTd"><strong>Rename</strong> coloca o cursor em cima do nome da operação
para que você faça quantas edições forem necessárias.</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
height="33" /></span></p>
<p><em>Ver Dependências</em></p>
</div></td>
<td class="confluenceTd"><strong>View Dependencies</strong> muda a visualização do painel de
projeto para exibir quaisquer outras partes do projeto das quais aquela
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
<p><em>Adicionar ao Grupo</em></p>
</div></td>
<td class="confluenceTd"><strong>Add to group</strong> abre uma caixa de diálogo para criar
um novo grupo customizado ou para adicionar o componente a um grupo já
existente (veja <a href="https://success.jitterbit.com/display/CS/Component+Groups">Grupos de Componentes</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
height="33" /></span></p>
<p><em>Deletar</em></p>
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
<p><em>Remover</em></p>
</div></td>
<td class="confluenceTd"><strong>Remove</strong> apaga todas as referências ao componente do
design canvas. Esta ação só é funcional quando usada numa operação que
está em um workflow (veja <a
href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de
Operações</a>).</td>
</tr>
</tbody>
</table>

</div>

#### <span id="DesignCanvas-share" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Activities, *Scripts*, *Transformations*, and Email Notifications

Os menus de ações desses componentes compartilham as mesmas ações:

<div class="table-wrap">

<table class="wrapped confluenceTable" style="width: 88.0399%;">
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
<td class="confluenceTd"><strong>View/Edit</strong> abre a tela de configuração do
componente. Para mais detalhes sobre a configuração, consulte o
componente respectivo em <a
href="https://success.jitterbit.com/display/CS/Connectors">Conectores</a>, <em><a
href="https://success.jitterbit.com/display/CS/Scripts">Scripts</a></em> ou
<em><a
href="https://success.jitterbit.com/display/CS/Transformations">Transformations</a></em>.</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
height="33" /></span></p>
<p><em>Recortar</em></p>
</div></td>
<td class="confluenceTd"><strong>Cut</strong> coloca uma cópia do componente na sua área de
transferência e deleta o componente original do projeto (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso
de Componentes</a>).</td>
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
<td class="confluenceTd"><strong>Copy</strong> coloca uma cópia do componente na sua área de
transferência (veja <a
href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de Componentes</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
height="33" /></span></p>
<p><em>Implantar</em></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
height="67" /></span></p>
<p><em>Implantar</em></p>
<p><em>Implantação Configurável</em></p>
</div></td>
<td class="confluenceTd"><p><strong>Deploy</strong> mostra as seguintes ações de menu:</p>
<ul>
<li>
<p><strong>Deploy</strong>: Implanta o componente, bem como quaisquer
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
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
height="33" /></span></p>
<p><em>Remover</em></p>
</div></td>
<td class="confluenceTd"><strong>Remove</strong> apaga as referências ao componente do design
canvas (veja <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Dependências, Exclusão e Remoção de
Componentes</a>).</td>
</tr>
</tbody>
</table>

</div>

### <span id="DesignCanvas-component-drop-zone-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Menu de Ações da Área de Inserção

As áreas de inserção de operações estão sempre visíveis no design
canvas. Para mostrar a área de inserção de um componente que pode ser
usado como etapa de operação, paire o mouse à esquerda ou à direita de
um passo de operação em uma operação existente no design canvas.

Para abrir o menu de ações de qualquer tipo de área de inserção, faça
uma das seguintes opções:

-   Clique com o botão direito do mouse sobre a área de inserção.

-   Paire o mouse sobre a área de inserção, e daí clique no ícone do
    menu de ações
    <span
        class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
        src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
        class="confluence-embedded-image confluence-external-resource"
        data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
        height="15" /></span><span style="letter-spacing: 0.0px;">.</span>

Tanto as áreas de inserção de operações quanto as áreas de inserção de
outros componentes mostram os mesmos itens de menu:

**Menu de Ações da Área de Inserção de Operações**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_operation_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_operation_actions-menu.png" /></span>

**Menu de Ações da Área de Inserção de Componentes**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component_actions-menu.png" /></span>

<div class="table-wrap">

<table class="wrapped confluenceTable" style="width: 86.5449%;">
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
src="https://docs-source.jitterbit.com/cs/menu-items/new-script.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/new-script.png"
height="33" /></span></p>
<p><em>Novo Script</em></p>
</div></td>
<td class="confluenceTd"><strong>New Script</strong> cria um novo script como passo numa
operação nova ou existente (veja <a
href="https://success.jitterbit.com/display/CS/Script+Types+and+Creation">Tipos e Criação de
<em>Scripts</em></a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/new-transformation.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/new-transformation.png"
height="33" /></span></p>
<p><em>Nova Transformação</em></p>
</div></td>
<td class="confluenceTd"><strong>New Transformation</strong> cria uma nova transformação como
passo numa operação nova ou existente (veja <a
href="https://success.jitterbit.com/display/CS/Transformation+Creation+and+Configuration">Criação e Configuração de
<em>Transformations</em></a>). Quando usado numa área de inserção de
operações, uma nova operação também é criada.</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/paste.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/paste.png"
height="33" /></span></p>
<p><em>Colar</em></p>
</div></td>
<td class="confluenceTd"><p><strong>Paste</strong> cria uma duplicata de uma atividade,
<em>script</em>, operação ou notificação de e-mail que esteja na sua
área de transferência como um novo componente referenciado por uma
operação nova ou existente (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Reuso de Componentes</a>). Quando
usado numa área de inserção de operações, uma nova operação também é
criada.</p>
<p>O nome padrão do novo componente usa o nome do componente original
acrescido do termo <em>- Copy</em>. Outras duplicatas terão, além deste
acréscimo, um número incrementável entre parênteses.</p></td>
</tr>
</tbody>
</table>

</div>

## <span id="DesignCanvas-renaming" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Renomeando Workflows, Operações e Etapas de Operação

Para renomear um workflow no design canvas, clique duas vezes sobre o
nome na aba do workflow no topo do design canvas:

<span style="color: rgb(23,43,77);"><span
class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/workflow-tab_rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/workflow-tab_rename.png" /></span></span>

Para renomear uma operação a partir do design canvas, clique no nome na
operação:

<span style="color: rgb(23,43,77);"><span
class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_rename.png" /></span></span>

Para renomear as etapas dentro de uma operação a partir do design
canvas, clique no nome da operação:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_rename.png" /></span>

## <span id="DesignCanvas-reordering-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Reordenando Operações

Operações no mesmo workflow podem ser reordenadas. Basta arrastá-las e
soltá-las no design canvas.

Clique e segure em qualquer lugar de uma operação para “levantá-la” e
arrastá-la para cima ou para baixo de outras operações dentro do
workflow:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/move-operation.gif"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/move-operation.gif" /></span>

Esta ação tem o efeito cascata de renumerar todas as operações acima ou
abaixo dela na árvore de projeto.
