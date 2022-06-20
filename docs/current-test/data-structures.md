[//]: # (Estruturas de Dados)
[//]: # (This is a translation of Version 7, published on August 18, 2021.)


## Introdução

As estruturas de dados podem ser fornecidas como *schemas* [durante a configuração das atividades](https://success.jitterbit.com/display/CS/Schemas+Defined+in+an+Activity?showLanguage=pt_BR) ou podem ser [definidas dentro do próprio *transformation*](https://success.jitterbit.com/display/CS/Schemas+Defined+in+a+Transformation?showLanguage=pt_BR). Quando as estruturas de dados são fornecidas em uma atividade, os *schemas* são herdados pelo *transformation* usando a atividade como fonte ou como alvo na operação. Uma vez que os *schemas* alvo e fonte de um *transformation* estão definidos, você pode criar mapeamentos de *transformation* entre os *schemas* fonte e alvo para definir como os dados devem ser processados.


## Tipos de Estrutura de Dados

No Jitterbit Harmony, os *schemas* fonte e alvo podem usar estruturas de dados que são definidas como [planas](https://success.jitterbit.com/display/CS/Data+Structures?hideelements=false#DataStructures-FlatStructure) (*flat*) ou [hierárquicas](https://success.jitterbit.com/display/CS/Data+Structures?hideelements=false#DataStructures-HierarchicalStructure).

### Estrutura Plana

Uma estrutura de dados plana (*flat*) consiste de um ou mais campos e registros individuais em uma estrutura bidimensional. Exemplos incluem arquivos CSV, arquivos XML simples e tabelas de banco de dados soltas. Uma estrutura de dados plana também pode ser chamada pelo anglicismo estrutura de *flat files*.

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;"><b>Exemplo de Estrutura Plana em Formato XML</b></div><div class="codeContent panelContent pdl">
<div><div id="highlighter_796215" class="syntaxhighlighter sh-confluence nogutter  xml"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Dica: clique duas vezes para selecionar o código"><div class="line number1 index0 alt2"><code class="xml plain">&lt;</code><code class="xml keyword">cliente</code><code class="xml plain">&gt;</code></div><div class="line number2 index1 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">id</code><code class="xml plain">&gt;10123&lt;/</code><code class="xml keyword">id</code><code class="xml plain">&gt;</code></div><div class="line number3 index2 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">nome</code><code class="xml plain">&gt;ABC Ltda.&lt;/</code><code class="xml keyword">nome</code><code class="xml plain">&gt;</code></div><div class="line number4 index3 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">rua</code><code class="xml plain">&gt;Rua Central 1&lt;/</code><code class="xml keyword">rua</code><code class="xml plain">&gt;</code></div><div class="line number5 index4 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">cidade</code><code class="xml plain">&gt;Cidadelândia&lt;/</code><code class="xml keyword">cidade</code><code class="xml plain">&gt;</code></div><div class="line number6 index5 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">estado</code><code class="xml plain">&gt;SP&lt;/</code><code class="xml keyword">estado</code><code class="xml plain">&gt;</code></div><div class="line number7 index6 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">cep</code><code class="xml plain">&gt;12345-678&lt;/</code><code class="xml keyword">cep</code><code class="xml plain">&gt;</code></div><div class="line number8 index7 alt1"><code class="xml plain">&lt;/</code><code class="xml keyword">cliente</code><code class="xml plain">&gt;</code></div></div></td></tr></tbody></table></div></div>
</div></div>

### Estrutura Hierárquica

Uma estrutura de dados hierárquica tem um ou mais relacionamentos pai-filho ou aninhamentos de campos e registros em uma estrutura complexa. As estruturas de dados hierárquicas são às vezes chamadas de estruturas *relacionais*, *multiníveis*, *de dados complexos* ou *de árvore*.

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;"><b>Exemplo de Estrutura Hierárquica em Formato XML</b></div><div class="codeContent panelContent pdl">
<div><div id="highlighter_474880" class="syntaxhighlighter sh-confluence nogutter  xml"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Dica: clique duas vezes para selecionar o código"><div class="line number1 index0 alt2"><code class="xml plain">&lt;</code><code class="xml keyword">cliente</code><code class="xml plain">&gt;</code></div><div class="line number2 index1 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">id</code><code class="xml plain">&gt;10123&lt;/</code><code class="xml keyword">id</code><code class="xml plain">&gt;</code></div><div class="line number3 index2 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">nome</code><code class="xml plain">&gt;ABC Ltda.&lt;/</code><code class="xml keyword">nome</code><code class="xml plain">&gt;</code></div><div class="line number4 index3 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">enderecos</code><code class="xml plain">&gt;</code></div><div class="line number5 index4 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">endereco</code><code class="xml plain">&gt;</code></div><div class="line number6 index5 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">rua</code><code class="xml plain">&gt;Rua Central 1&lt;/</code><code class="xml keyword">rua</code><code class="xml plain">&gt;</code></div><div class="line number7 index6 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">cidade</code><code class="xml plain">&gt;Cidadelândia&lt;/</code><code class="xml keyword">cidade</code><code class="xml plain">&gt;</code></div><div class="line number8 index7 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">estado</code><code class="xml plain">&gt;SP&lt;/</code><code class="xml keyword">estado</code><code class="xml plain">&gt;</code></div><div class="line number9 index8 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">cep</code><code class="xml plain">&gt;12345-678&lt;/</code><code class="xml keyword">cep</code><code class="xml plain">&gt;</code></div><div class="line number10 index9 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;/</code><code class="xml keyword">endereco</code><code class="xml plain">&gt;</code></div><div class="line number11 index10 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">endereco</code><code class="xml plain">&gt;</code></div><div class="line number12 index11 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">rua</code><code class="xml plain">&gt;Avenida Paulista 1&lt;/</code><code class="xml keyword">rua</code><code class="xml plain">&gt;</code></div><div class="line number13 index12 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">cidade</code><code class="xml plain">&gt;São Paulo&lt;/</code><code class="xml keyword">cidade</code><code class="xml plain">&gt;</code></div><div class="line number14 index13 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">estado</code><code class="xml plain">&gt;SP&lt;/</code><code class="xml keyword">estado</code><code class="xml plain">&gt;</code></div><div class="line number15 index14 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;</code><code class="xml keyword">cep</code><code class="xml plain">&gt;98765-432&lt;/</code><code class="xml keyword">cep</code><code class="xml plain">&gt;</code></div><div class="line number16 index15 alt1"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;/</code><code class="xml keyword">endereco</code><code class="xml plain">&gt;</code></div><div class="line number17 index16 alt2"><code class="xml spaces">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="xml plain">&lt;/</code><code class="xml keyword">enderecos</code><code class="xml plain">&gt;</code></div><div class="line number18 index17 alt1"><code class="xml plain">&lt;/</code><code class="xml keyword">cliente</code><code class="xml plain">&gt;</code></div></div></td></tr></tbody></table></div></div>
</div></div>


## Exibição de Estruturas de Dados

As estruturas de dados são exibidas em formato de árvore que pode ser expandida ou reduzida para mostrar a árvore inteira ou apenas parte dela.

Cada árvore consiste de [nós e campos](https://success.jitterbit.com/display/CS/Nodes+and+Fields?showLanguage=pt_BR), onde os campos dentro da estrutura de dados fonte podem ser mapeados para campos dentro da estrutura de dados alvo.

Os nós contêm um triângulo de revelação à esquerda do nome do nó que é usado para reduzir ou expandir o nó. Por padrão, os nós podem ser expandidos até um máximo de 8 níveis de profundidade para *schemas* com 750 nós ou menos e até um máximo de 5 níveis de profundidade para *schemas* com mais de 750 nós. Todos os nós abaixo de um nó alvo podem ser expandidos de uma vez usando a opção **Expand All Nodes Beneath This Node** (Expandir Todos os Nós Abaixo deste Nó), presente no menu de ações de *schema* (consulte a seção [Nós Alvo](https://success.jitterbit.com/display/CS/Mapping+Mode#MappingMode-target-nodes) no artigo [Modo de Mapeamento](https://success.jitterbit.com/display/CS/Mapping+Mode?showLanguage=pt_BR)). Se você expandir ou reduzir nós, o Cloud Studio se lembra do último estado de expansão que você estava usando da próxima vez que você acessar o *transformation*.

Uma vez expandidos, os nós exibem todos os nós e campos-filho contidos neles. Os nós podem ser considerados pastas com seus nós-filho sendo as subpastas. Os campos ficam contidos dentro dos nós e são listados junto com seus tipos de dados (`boolean`, `integer`, `double`, `binary`, `string`).

Por exemplo, na estrutura alvo mostrada abaixo, o nó `json` inclui o nó-filho `item`, que por sua vez contém os campos `employeeId`, `name` e `title`. O nó `item` também contém o nó-filho `employeeDetails`, que por sua vez contém os campos `salary`, `isWorking` e `status`.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/target_data-structure.png" class="confluence-embedded-image confluence-external-resource" /></span>


## Exibição de Campos Mapeados

Um mapeamento de *transformation* consiste de campos ou nós-alvo e seus *scripts* correspondentes. Tais *scripts* podem conter referências a campos ou nós-alvo ou a componentes de projeto, usar funções ou conter outras lógicas de *script* válidas. Um mapeamento *não* inclui campos-alvo que não estejam mapeados.

Quando objetos e variáveis fonte são definidos dentro do campo alvo, eles aparecem como blocos dentro do campo alvo. O campo alvo mapeado é exibido com uma linha vertical roxa no lado esquerdo do bloco do campo alvo:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/target-field_source-objects.png" class="confluence-embedded-image confluence-external-resource" /></span>

Quando tanto um *schema* fonte quanto um *schema* alvo estão visíveis na tela e você está em modo de mapeamento, uma linha visual mostra a conexão com o objeto fonte. Paire seu *mouse* sobre um campo alvo mapeado para mostrar uma linha cinza clara que mostra a conexão desde o(s) objeto(s) fonte usado(s) no mapeamento até o campo alvo mapeado:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/target_lines.png" class="confluence-embedded-image confluence-external-resource" /></span>

A linha preta sólida mostrada na imagem acima é explicada na próxima seção, [Loop Nodes](https://success.jitterbit.com/display/CS/Data+Structures#DataStructures-loop-nodes).

O lado alvo do mapeamento também indica se um campo tem valores padrão (destacados em vermelho na imagem abaixo) ou junções (destacadas em verde na imagem abaixo). Por exemplo, este *transformation* insere dados num banco de dados cujos campos `id` são auto-incrementados e cujo campo `created_at` é definido para ser igual à hora atual por padrão. Ele também mostra que a tabela filha `qa_employee` foi juntada à tabela mãe `qa_restaurant` no campo id:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/target-field_default-values_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

Caso um nó recolhido contenha mapeamentos de campos alvo, tal nó será mostrado em negrito para indicar que ele contém mapeamentos:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/target-node_collapsed.png" class="confluence-embedded-image confluence-external-resource" /></span>


## Loop Nodes

Um *loop node* (literalmente, um nó-laço) é um nó fonte ou alvo com valores de dados que se repetem, como itens em linha de um orçamento ou um conjunto de registros de clientes.

Quando os campos de *loop nodes* são mapeados, uma linha *iteradora* preta sólida aparece automaticamente, indicando que o processo do *transformation* irá iterar pelo conjuntos de dados fonte. O local em que as linhas iteradoras são geradas depende da multiplicidade dos *loop nodes* fonte correspondentes.

Um *transformation* pode ter zero ou mais linhas iteradoras. Quando várias linhas iteradoras estão presentes, a precedência é dada do alto à base da estrutura alvo.

Para ocultar uma linha iteradora em particular, clique diretamente sobre a forma de círculo mais próxima ao nó alvo:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/loop-node_toggle.png" class="confluence-embedded-image confluence-external-resource" /></span>

A linha do *loop node* individual torna-se então uma bola laranja que ao ser clicada volta a mostrar a linha inteira:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/loop-node_stub.png" class="confluence-embedded-image confluence-external-resource" /></span>

### Exemplo

Como exemplo de mapeamento de um *loop node*, considere a seguinte estrutura fonte hierárquica, contendo um nó fonte no topo (`item`) com campos que fornecem informações sobre uma empresa. Um nó fonte filho, `locationDetails`, inclui um vetor (`json$item.locationDetails$item.`) de objetos com campos para os locais de várias lojas dentro de uma empresa. Tanto o nó pai quanto o filho são considerados *loop nodes* pois os dados podem conter vários registros de empresa com vários registros de locais de loja para cada empresa.

Agora considere que estes dados estão sendo mapeados para uma estrutura alvo plana, resultando num registro para cada local de loja. Enquanto você mapeia os campos, uma linha iteradora aparece automaticamente, conectando os *loop nodes* fonte e alvo. Tal linha indica que o alvo vai iterar a mesma quantidade de vezes que o número de conjuntos de dados na fonte, ou, neste exemplo, iterar por cada registro de local de loja na empresa.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/loop-node.png" class="confluence-embedded-image confluence-external-resource" /></span>

### Mapeando de uma Fonte de Várias Instâncias para um Alvo de Instância Única

Quando o *loop node* alvo gerado depende de mais de um *loop node* fonte, pode ser que você precise resolver um conflito de múltiplas ocorrências com o mapeamento.

Se a estrutura de dados fonte for um vetor multi objetos e estiver sendo mapeada para uma estrutura de dados alvo com um único objeto, a seguinte caixa de diálogo será mostrada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/multiple-instance-source-cannot-be-mapped-to-single-instance-target.png" class="confluence-embedded-image confluence-external-resource" /></span>

Para usar a primeira instância da fonte no mapeamento, selecione **Yes**. Isto significa que apenas o primeiro registro será mapeado. Por exemplo, com o mapeamento abaixo, apenas o primeiro registro de cliente no vetor será mapeado para a estrutura alvo contendo apenas um único cliente. Note que cada campo alvo mapeado agora contém um *script*, conforme indicado pela presença do ícone de *script* <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/script.png" class="confluence-embedded-image confluence-external-resource" /></span>.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/loop-node_instance-resolution.png" class="confluence-embedded-image confluence-external-resource" /></span>

Quando você alternar para o modo de *script* em qualquer campo mapeado, você verá que um `#1` foi adicionado dentro do caminho do objeto fonte mapeado para indicar que a primeira instância está mapeada.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/script-mode/instance-mapping.png" class="confluence-embedded-image confluence-external-resource" /></span>

Se você não quiser que a primeira instância da fonte seja usada, você pode especificar uma lógica diferente usando as funções que resolvem instâncias (veja o artigo [Funções de Instância](https://success.jitterbit.com/display/CS/Instance+Functions?showLanguage=pt_BR)).


## Normalização de Dados

Se você estiver mapeando dados de uma estrutura plana para uma estrutura hierárquica, os dados talvez precisem ser normalizados antes de serem transformados.

Por padrão, o Jitterbit Harmony usa um algoritmo de normalização para construir a árvore alvo. Isto transformará a estrutura plana da fonte em uma estrutura fonte hierárquica que poderá então ser mapeada para a estrutura alvo hierárquica.

Na estrutura alvo, o elemento raiz e todos os elementos de múltipla instância abaixo da raiz são usados para criar a estrutura dos elementos fonte secundários. Os atributos (ou campos) de tais elementos fonte secundários são elementos de dados planos que são então usados nos mapeamentos do elemento alvo correspondente.

Com a estrutura fonte propriamente definida, o processo de normalização é simplificado e passa a ser simplesmente combinar nós com os mesmos pais.

Há três opções de normalização:

-   **Normalização Completa:** Todos os elementos com o mesmo pai e todos os campos são reduzidos a um elemento. (Este é o padrão).

-   **Normalização Parcial:** Igual à normalização completa, com a diferença de que os filhos mais baixos não são normalizados.

-   **Sem Normalização:** Cada registro plano (*flat*) cria um galho de elementos; não é feita nenhuma redução de elementos ao se criar a estrutura fonte hierárquica.

É possível que a estrutura hierárquica contenha um único nó de instância. Neste caso, apenas o primeiro elemento para esta raiz será mantido, e os registros planos (*flat*) que entrem em conflito com tal nó de dados raiz serão ignorados.

Para desabilitar a normalização, defina a variável Jitterbit chamada `jitterbit.transformation.disable_normalization` com o valor `true` (veja o artigo [Variáveis Jitterbit de Transformations](https://success.jitterbit.com/display/CS/Transformation+Jitterbit+Variables?showLanguage=pt_BR)).


## Mapeamento de Instâncias e Múltiplo

O mapeamento de *transformations* é o processo usado para definir o relacionamento dos dados entre as entradas e a saída de dados resultante. Dependendo de quais tipos de estruturas de dados forem usados, o mapeamento do *transformation* pode ser descrito como *mapeamento de instâncias* ou *mapeamento múltiplo*.

### Mapeamento de Instâncias

O termo mapeamento de instâncias descreve quando o mapeamento de uma instância alvo depende de possivelmente mais de uma instância de uma fonte. O mapeamento de instâncias pode ser de plano-para-plano (um-para-um) ou hierárquico-para-plano (muitos-para-um).

### Mapeamento Múltiplo

O termo mapeamento múltiplo descreve o mapeamento de duas estruturas de dados hierárquicas ou o mapeamento de uma única estrutura plana que na realidade é de natureza hierárquica, com seus segmentos mais baixos contendo vários conjuntos de valores como pares nome/valor. O mapeamento múltiplo pode ser de hierárquico-para-hierárquico (muitos-para-muitos) ou plano-para-hierárquico (um-para-muitos).

### Exemplos

Situações exemplo tanto de mapeamento de instâncias quanto de mapeamento múltiplo podem ser encontradas dentro da documentação do Design Studio:

-   **Mapeamento de Instâncias**

    -   [Mapeando Estruturas Hierárquicas para Planas](https://success.jitterbit.com/display/DOC/Mapping+Hierarchical+to+Flat+Structures?showLanguage=pt_BR)

-   **Mapeamento Múltiplo**

    -   [Mapeando Estruturas Planas para Hierárquicas](https://success.jitterbit.com/display/DOC/Mapping+Flat+to+Hierarchical+Structures?showLanguage=pt_BR)
    -   [Mapeamento Múltiplo](https://success.jitterbit.com/display/DOC/Multiple+Mapping?showLanguage=pt_BR)

Embora estes exemplos sejam para o Design Studio, os mesmos conceitos podem ser aplicados no Cloud Studio.

Para módulos de treinamento prático que contêm exemplos de como mapear arquivos de texto, XML, e bancos de dados simples e complexos, faça o curso [Introdução ao Jitterbit Harmony Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio?showLanguage=pt_BR).
