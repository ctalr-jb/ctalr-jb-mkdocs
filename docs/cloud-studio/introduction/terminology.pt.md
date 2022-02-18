[//]: # (Terminologia do Cloud Studio)
[//]: # (This is a translation of Version 17, published on November 9, 2021.)

## Introdução

Esta página define conceitos e termos técnicos importantes usados no
[Cloud Studio](/display/CS/Cloud+Studio?showLanguage=pt_BR).


## <span id="CloudStudioTerminology-project" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Projeto

Um [projeto](/display/CS/Projects?showLanguage=pt_BR) é uma coleção de um ou mais
[workflows](#CloudStudioTerminology-workflow) que compõem e executam um caso de uso de integração. Um projeto contém
[operações](#CloudStudioTerminology-operation) bem como outros [componentes de
projeto](#CloudStudioTerminology-project-component) que podem ser parte de uma operação ou usados para apoiar
operações. Um projeto pode ser compartilhado, arquivado ou redistribuído por meio de sua exportação ou importação
como um arquivo JSON.


## <span id="CloudStudioTerminology-project-component" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Componente de Projeto

[Componentes de projeto](/display/CS/Project+Components?showLanguage=pt_BR) são as peças individuais de um projeto.
Alguns componentes, incluindo [atividades](#CloudStudioTerminology-activities),
*[transformations](#CloudStudioTerminology-transformation)* e *[scripts](#CloudStudioTerminology-scripts)*, podem
ser adicionados a [operações](#CloudStudioTerminology-operation) e executados como uma sequência de etapas. Outros
componentes podem ser usados em apoio a tais operações, como [variáveis](/display/CS/Variables?showLanguage=pt_BR),
[agendas](/display/CS/Operation+Schedules?showLanguage=pt_BR), [*schemas* de
arquivo](/display/CS/Schemas?showLanguage=pt_BR), [notificações](/display/CS/Notifications?showLanguage=pt_BR) e
[plugins](/display/CS/Plugins?showLanguage=pt_BR). As próprias operações também são componentes de projeto.


## <span id="CloudStudioTerminology-dependencies" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Dependências

Alguns componentes de projeto podem depender de outros componentes para funcionar corretamente. Dois termos
separados são usados para discutir esta situação: *dependente de* e *dependência de*. Nos exemplos a seguir, o
Componente A é ***dependente do*** Componente B. Portanto, o Componente B é ***uma dependência do*** Componente A:

-   **Dependente de**: Se um componente é dependente de outro, ele
    precisa deste segundo componente para funcionar direito. Um
    componente que é dependente de outro não pode estar por si só sem
    o segundo. Quando o Componente A precisa do Componente B para
    poder executar com sucesso, dizemos que o Componente A é
    dependente do Componente B. Outra forma de expressar isso é que o
    Componente A depende do Componente B.

-   **Dependência de**: Se um componente é uma dependência de outro, ele
    é necessário para que este segundo funcione direito. Um componente
    que é uma dependência de outro é exigido por ele. Quando o
    Componente A precisa do Componente B para executar com sucesso,
    dizemos que o Componente B é uma dependência do Componente A.


## <span id="CloudStudioTerminology-workflow" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Workflow

Um workflow é uma coleção de [operações](#CloudStudioTerminology-operation) usada como ferramenta para ajudar a
segregar diferentes partes do projeto para a conveniência do usuário.

Os workflows são criados no topo do [design canvas](/display/CS/Design+Canvas?showLanguage=pt_BR):

![](https://docs-source.jitterbit.com/cs/design-canvas/workflow-tab_new.png)

Quando você cria um novo workflow, um quadro em branco aparece, pronto para você desenhar o workflow criando
operações.

Os workflows não podem ser executados; apenas as operações dentro deles podem ser executadas. Mas caso o workflow
esteja configurado para que uma operação leve à execução em cadeia de todas as outras operações dentro do workflow,
você pode efetivamente executar todas as operações daquele workflow.

Você também pode executar operações individuais dentro de workflows, o que pode levar à execução de outras operações
no mesmo workflow ou em outros. Isto é, se alguma operação estiver acima de outras numa cadeia de operação, dentro
ou fora do workflow, as operações que estiverem abaixo serão executadas de acordo. Desta forma, você pode
efetivamente executar todas as operações dentro de um projeto.


## <span id="CloudStudioTerminology-operation" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operação

Uma operação é a menor unidade dentro de um [workflow](#CloudStudioTerminology-workflow) que é executada
independentemente num agente e registrada pelo Harmony (hora de início e duração, sucesso, falha, erros, etc.). As
operações são usadas para definir o que uma integração deve fazer e quando aquilo deve ser feito.

Uma operação consiste de, no mínimo, uma etapa de operação, e muitas vezes tem várias etapas de operação compostas
de [atividades](#CloudStudioTerminology-activities), *[transformations](#CloudStudioTerminology-transformation)* ou
*[scripts](#CloudStudioTerminology-scripts)*. Etapas de operação são os elementos individuais que compõem uma
operação e são representadas visualmente dentro de uma operação no design canvas:

![](https://docs-source.jitterbit.com/cs/design-canvas/operation.png)

As operações devem seguir um [padrão de operação válido](/display/CS/Operation+Validity?showLanguage=pt_BR).
Combinações que não são permitidas em uma única operação podem ser funcionalmente possíveis se você encadear várias
operações usando ações de operação. Quando estão criadas, as operações podem ser executadas manualmente, acionadas
por uma API, ou agendadas.


## <span id="CloudStudioTerminology-connectivity" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="CloudStudioTerminology-connectors" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="CloudStudioTerminology-connections" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="CloudStudioTerminology-activities" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="CloudStudioTerminology-endpoints" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Conectividade

Recursos de conectividade são acessados dentro da aba **Connectivity** (Conectividade) da [paleta de componentes de
design](/display/CS/Design+Component+Palette?showLanguage=pt_BR). Dentro desta aba, os
[conectores](/display/CS/Connectors?showLanguage=pt_BR) recebem as primeiras configurações para criar conexões.
Atividades associadas a essas conexões podem então ser instanciadas usando os tipos de atividade e configuradas como
fontes ou alvos em um projeto. Um *endpoint* refere-se a uma conexão específica e às suas atividades.

-   **Conectores**: Um conector provê a interface para a inserção de
    entradas vindas do usuário, como credenciais, para criar uma
    conexão. O filtro **Connectors** (Conectores) mostra os conectores
    disponíveis. Você também pode criar [conectores
    customizados](/display/CS/Custom+Connector?showLanguage=pt_BR).

-   **Conexões**: Uma conexão é um componente que é criado a partir de
    um conector e provê acesso a um recurso de dados. O filtro
    **Endpoints** mostra as conexões disponíveis.

-   **Atividades**: Uma atividade é um componente que é criado a partir
    de uma conexão e é configurado para interagir com um *endpoint*. O
    filtro **Endpoints** mostra as conexões, que podem ser clicadas
    para revelar os tipos de atividade. Os tipos de atividade são
    usados para criar uma instância de uma atividade num projeto.
    Instâncias de atividade podem atuar como fontes (provendo dados)
    ou como alvos (recebendo dados).

-   **Endpoints**: Um *endpoint* refere-se a uma conexão específica e às
    suas atividades.

![](https://docs-source.jitterbit.com/cs/project/connectivity-terms_annotated_pp.png)


## <span id="CloudStudioTerminology-scripts" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Scripts

Os *[scripts](/display/CS/Scripts?showLanguage=pt_BR)*, escritos em Jitterbit Script ou em JavaScript, trazem
flexibilidade e o poder de transformar dados, executar cálculos ou realizar validações lógicas além de um simples
mapeamento de campos.

Os *scripts* podem ser usados em vários lugares, tanto dentro do [design
canvas](/display/CS/Design+Canvas?showLanguage=pt_BR) como etapas de uma
[operação](#CloudStudioTerminology-operation), quanto dentro de *transformations* para aplicar aos dados uma lógica
especificada ou certas condições.


## <span id="CloudStudioTerminology-variables" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Variáveis

[Variáveis](/display/CS/Variables?showLanguage=pt_BR) são usadas ao longo de todo um projeto para tornar as
integrações mais flexíveis e dinâmicas. Elas permitem a configuração dinâmica de *endpoints*, apoiam a passagem de
dados entre [operações](#CloudStudioTerminology-operation), e são usadas em *scripts* de *transformations* para
guiar lógica de integração detalhada.

O Jitterbit Harmony suporta vários tipos de variáveis com diversos escopos:

-   **Variáveis locais**: Limitadas ao *script* atual.

-   **Variáveis globais**: Disponíveis para o *script* atual e para
    aqueles abaixo dele na cadeia.

-   **Variáveis de projeto**: Disponíveis em todos os workflows do
    projeto, e acessíveis de fora do Cloud Studio através do
    Management Console e do Citizen Integrator.

-   **Variáveis Jitterbit**: Pré-definidas pelo Harmony e disponíveis
    para os *scripts* atuais e para aqueles abaixo dele na cadeia.

Além disso, variáveis para nomes de arquivo podem ser usadas para gerar nomes únicos para campos configuráveis que
recebem nomes de arquivo como entrada.

As melhores práticas de integração sugerem que você use a variável com o escopo mais limitado, de modo a minimizar o
risco de que os valores mudem ao longo de vários componentes do projeto.


## <span id="CloudStudioTerminology-transformation" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Transformations

Uma *[transformation](/display/CS/Transformations?showLanguage=pt_BR)* é um componente de projeto que é usado como
etapa numa operação para mapear ou *transformar* entradas em saídas através da movimentação ou limpeza de dados, ou
da aplicação de uma lógica de negócio.

Uma *transformation* é composta por um *schema* fonte e um *schema* alvo que foram definidos na *transformation* e
pelo mapeamento que gera a saída. Um *schema* fonte é exigido apenas quando uma atividade fonte adjacente entrega
dados de entrada que precisam ser transformados. Um *schema* alvo é sempre exigido.

Os *schemas* fonte e alvo podem tanto ser definidos dentro da *transformation* ou entregues por uma atividade
adjacente, sendo que os *schemas* definidos dentro da *transformation* têm preferência. Os *schemas* entregues por
atividades adjacentes não fazem parte da *transformation*. Além disso, uma *transformation* não inclui os dados de
entrada e saída em si.

A configuração de uma *transformation* pode ocorrer tanto em modo de mapeamento quanto em modo *script*.

Ademais, ao configurar uma *transformation*, você também precisa estar familiarizado(a) com os seguintes termos:

-   **Mapeamento**: Um mapeamento de *transformation* é composto pelos
    nós ou campos alvo e pelos seus *scripts* correspondentes. Esses
    *scripts* podem conter referências aos nós ou aos campos fonte ou
    a componentes de projeto, podem usar funções, ou podem conter
    outras lógicas de *script* válidas. Um mapeamento não inclui
    campos alvo que não estejam mapeados.

-   **Condição**: Uma condição, conforme se usa o termo em uma
    *transformation*, é um *script* aplicado a um alvo para determinar
    se o registro fonte que está sendo processado deve ser enviado
    para o alvo. Se o *script* retornar o resultado "verdadeiro", o
    registro será colocado na saída. Se ele retornar o resultado
    "falso", aquele registro será pulado.

    ![](https://docs-source.jitterbit.com/cs/transformation/script-mode/condition_if.png)

-   **Loop Node**: Um *loop node*, ou nó de tipo loop, é um nó fonte ou
    alvo com valores de dado que se repetem, tais como itens de linha
    num orçamento ou um conjunto de registros de cliente. Quando os
    campos de um *loop node* são mapeados, uma linha iteradora preta
    sólida aparece automaticamente, indicando que o processo da
    *transformation* vai iterar sobre o conjunto de dados fonte. Uma
    *transformation* pode ter zero ou mais linhas iteradoras.

    ![](https://docs-source.jitterbit.com/cs/transformation/mapping-mode/loop-node.png)


## <span id="CloudStudioTerminology-recipes" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Protótipo de Integração

Um [Protótipo de Integração do Cloud Studio](/display/CS/Cloud+Studio+Integration+Recipes?showLanguage=pt_BR),
disponível através do Jitterbit Marketplace, é um projeto de integração distinto e pré-construído que move dados em
uma direção entre objetos ao longo de duas aplicações ou sistemas. Protótipos de integração estão disponíveis para
todos os usuários do Jitterbit Harmony.


## <span id="CloudStudioTerminology-templates" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Template de Processo

Um *template* de processo do Cloud Studio, disponível através do Jitterbit Marketplace, é um grupo de casos de uso
de integração pré-construídos que acelera a execução de um processo de negócio específico usando vários objetos ao
longo de várias aplicações ou sistemas.

*Templates* de processo são projetados para reduzir o tempo até a implantação de 50 a 80 por cento e podem ser tanto
*auto-implementados, entregues pela Jitterbit Professional Services, ou entregues por um parceiro de implementação.

Um *template* de processo consiste de um ou mais projetos usando vários pontos finais, pode incluir arquivos de
customização, e tem a sua própria documentação em formato PDF. Depois que os projetos são criados, você deve inserir
valores apropriados nas variáveis de projeto que estabelecem credenciais e outras informações para o projeto em cada
projeto individualmente.
