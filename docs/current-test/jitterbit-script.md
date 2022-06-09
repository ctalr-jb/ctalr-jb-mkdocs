[//]: # (Jitterbit Script)
[//]: # (This is a translation of Version 27, published on March 3, 2022.)


## Introdução

A linguagem Jitterbit Script pode ser usada em todos os tipos de *script* dentro do Jitterbit Harmony, incluindo dentro de operações e *transformations*. Os *scripts* são criados na linguagem Jitterbit Script por padrão. Esta página fornece informações específicas sobre a linguagem Jitterbit Script, tais como sintaxe, tipos de dados, operadores, sequências de escape e estruturas de controle. Veja também as páginas relacionadas sobre como [criar um *script*](https://success.jitterbit.com/display/CS/Script+Types+and+Creation?showLanguage=pt_BR), [usar o editor de *scripts*](https://success.jitterbit.com/display/CS/Script+Editor?showLanguage=pt_BR) e [testar um *script*](https://success.jitterbit.com/display/CS/Script+Testing?showLanguage=pt_BR).


## Sintaxe

Em Jitterbit Script, os *scripts* devem estar posicionados entre uma *tag* de abertura `<trans>` e uma *tag* de fechamento `</trans>`, a menos que você esteja usando funções que pedem especificamente que o código seja colocado fora destas *tags*, como várias [Funções de Banco de Dados](https://success.jitterbit.com/display/CS/Database+Functions?showLanguage=pt_BR).

Dentro de tais *tags*, um Jitterbit Script consiste de funções embutidas, variáveis ou lógica para executar, separadas por um ponto e vírgula (`;`).

O resultado que é retornado é igual ao valor retornado pela última declaração do *script* antes da *tag* de fechamento `</trans>`.

### Comentários

Dentro das *tags* `<trans>` … `</trans>`, o uso de duas barras diagonais `//` denota o início de um comentário de uma linha e afeta o texto até o final daquela linha. Os comentários não fazem parte do *script* que é executado nem do resultado transformado.

Por exemplo, um comentário de uma linha pode ser semelhante ao exemplo a seguir:

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;">
<b>Comentário de Uma Linha em Jitterbit Script</b>
</div>
<div class="codeContent panelContent pdl"><div>
<div id="highlighter_760954" class="syntaxhighlighter sh-confluence nogutter  java">
<div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div>
<table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Dica: clique duas vezes para selecionar o código"><div class="line number1 index0 alt2"><code class="java plain">&lt;trans&gt;</code></div><div class="line number2 index1 alt1"><code class="java comments">// Isto é um comentário</code></div><div class="line number3 index2 alt2"><code class="java plain">DbLookup(...)</code></div><div class="line number4 index3 alt1"><code class="java plain">&lt;/trans&gt;</code></div></div></td></tr></tbody>
</table>
</div></div>
</div></div>

Você também pode usar um comentário em bloco:

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;">
<b>Comentário de Várias Linhas em Jitterbit Script</b>
</div><div class="codeContent panelContent pdl"><div>
<div id="highlighter_524951" class="syntaxhighlighter sh-confluence nogutter  java">
<div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div>
<table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Dica: clique duas vezes para selecionar o código"><div class="line number1 index0 alt2"><code class="java plain">&lt;trans&gt;</code></div><div class="line number2 index1 alt1"><code class="java comments">/* Isto é um comentário de várias linhas</code></div><div class="line number3 index2 alt2"><code class="java comments">Esta linha também é um comentário</code></div><div class="line number4 index3 alt1"><code class="java comments">Esta é a última linha do comentário */</code></div><div class="line number5 index4 alt2"><code class="java plain">DbLookup(...)</code></div><div class="line number6 index5 alt1"><code class="java plain">&lt;/trans&gt;</code></div></div></td></tr></tbody>
</table>
</div></div>
</div></div>

### Estruturas de Controle

A linguagem Jitterbit Script não inclui declarações de controle como laços de tipo `if` ou `while`. Em vez disso, você pode usar funções Jitterbit para obter as mesmas funcionalidades.

Veja as funções `Case`, `If` e `While` no artigo [Funções Lógicas](https://success.jitterbit.com/display/CS/Logical+Functions?showLanguage=pt_BR). A função `Eval` no artigo [Funções Gerais](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR) pode ser usada como declaração do tipo "try-catch".

Um máximo de 50.000 iterações de um laço é permitido para cada laço individual em Jitterbit Scripts. Para aumentar o número de iterações permitidas por laço, consulte [`jitterbit.scripting.while.max_iterations`](https://success.jitterbit.com/display/CS/Scripting+Jitterbit+Variables#ScriptingJitterbitVariables-jitterbit.scripting.while.max_iterations) no artigo [Variáveis Jitterbit para Uso em *Scripts*](https://success.jitterbit.com/display/CS/Scripting+Jitterbit+Variables?showLanguage=pt_BR).

### Expressões Regulares

O Jitterbit Harmony suporta expressões regulares como forma de especificar e reconhecer sequências de texto, incluindo caracteres, palavras ou padrões de caracteres específicos. O Jitterbit Harmony suporta a sintaxe de expressões regulares da [linguagem de programação Perl 5](https://www.boost.org/doc/libs/1_49_0/libs/regex/doc/html/boost_regex/syntax/perl_syntax.html).

```
<trans>
RegExMatch(<input>,<expression>,...)
</trans>
```

### Sequências de Escape

O Jitterbit Harmony reconhece as seguintes sequências de escape quando usadas em *strings* literais:

<div class="table-wrap">
<table class="wrapped confluenceTable tablesorter tablesorter-default stickyTableHeaders" role="grid" resolved="" style="padding: 0px;">
<colgroup> <col> <col> </colgroup>
<thead class="tableFloatingHeaderOriginal" style="position: static; margin-top: 0px; left: 301px; z-index: 3; width: 213px; top: 61px;">
<tr role="row" class="tablesorter-headerRow">
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="0" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;"><div class="tablesorter-header-inner">Sequência</div></th>
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="1" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;"><div class="tablesorter-header-inner">Definição</div></th>
</tr>
</thead>
<thead class="tableFloatingHeader" style="display: none;">
<tr role="row" class="tablesorter-headerRow">
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="0" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none;"><div class="tablesorter-header-inner">Sequência</div></th>
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="1" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none;"><div class="tablesorter-header-inner">Definição</div></th>
</tr>
</thead>
<tbody aria-live="polite" aria-relevant="all">
<tr role="row">
<td class="confluenceTd"><code>\t</code></td>
<td class="confluenceTd">Tabulação (Recuo)</td>
</tr>
<tr role="row">
<td class="confluenceTd"><code>\r</code></td>
<td class="confluenceTd">Retorno de carro</td>
</tr>
<tr role="row">
<td class="confluenceTd"><code>\n</code></td>
<td class="confluenceTd">Nova linha</td></tr>
</tbody>
</table>
</div>

*Strings* literais devem ser cercadas por aspas duplas (`"`) ou aspas simples (`‘`).

Qualquer outra citação deve ser precedida por uma sequência de escape se for usada dentro da *string*. Por exemplo:

```
$str = "String com nova linha.\nEsta é a última linha.";

$str = 'Rob "The Gronk" Gronkowski';

$str = "Rob \"The Gronk\" Gronkowski";
```

### Operadores

Isto é um resumo dos operadores suportados pelo Jitterbit Script. O Jitterbit Script tenta converter os argumentos para possibilitar a operação. Caso isso não seja possível, um erro é relatado.

<div class="table-wrap">
<table class="wrapped confluenceTable" resolved="">
<colgroup>
<col style="width: 81.0px;">
<col style="width: 1164.0px;">
</colgroup>
<tbody>
<tr>
<td class="highlight-#c1c7d0 confluenceTd" colspan="2" data-highlight-colour="#c1c7d0"><strong title="">Aritmética</strong></td>
</tr>
<tr>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Operador</strong></td>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Descrição</strong></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>+</code></td>
<td colspan="1" class="confluenceTd">Adiciona dois números ou concatena duas <em>strings</em>. Se uma <em>string</em> for adicionada a qualquer outra coisa, ambos os argumentos são convertidos para <em>strings</em>. Se os dois argumentos forem números, o resultado é de tipo double.</td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>++</code></td>
<td colspan="1" class="confluenceTd">Incrementa o valor em 1. Por exemplo: <code>$count++;</code> quando houver prefixo, a atribuição vem antes do incremento.</td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>+=</code></td>
<td colspan="1" class="confluenceTd">Concatena uma <em>string</em> ou adiciona números à variável alvo. Por exemplo: <code>$count+=2</code> é o mesmo que <code>$count=$count+2</code>.</td>
</tr>
<tr>
<td class="confluenceTd"><code>-</code></td>
<td class="confluenceTd">Subtrai dois números. O resultado é de tipo <em>double</em>.</td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>--</code></td>
<td colspan="1" class="confluenceTd">Diminui um valor em 1. Por exemplo: <code>$count–;</code> quando houver prefixo, a atribuição vem antes da diminuição.</td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>-=</code></td>
<td colspan="1" class="confluenceTd">Subtrai números da variável alvo. Por exemplo: <code>$count-=2</code> é o mesmo que <code>$count=$count-2</code>.</td>
</tr>
<tr>
<td class="confluenceTd"><code>/</code></td>
<td class="confluenceTd">Divide dois números. O resultado é de tipo <em>double</em>.</td>
</tr>
<tr>
<td class="confluenceTd"><code>*</code></td>
<td class="confluenceTd">Multiplica dois números. O resultado é de tipo <em>double</em>.</td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>^</code></td>
<td colspan="1" class="confluenceTd">Eleva o argumento à potência equivalente ao número do segundo argumento. Se ambos os argumentos forem inteiros, o resultado também será.</td></tr>
<tr>
<td class="highlight-#c1c7d0 confluenceTd" colspan="2" data-highlight-colour="#c1c7d0"><strong title="">Lógica</strong></td>
</tr>
<tr>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Operador</strong></td>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Descrição</strong></td>
</tr>
<tr>
<td class="confluenceTd"><code>&amp;</code></td>
<td class="confluenceTd">Operador E lógico. O resultado é de tipo booleano. <code>&amp;&amp;</code> também pode ser usado. Este é sempre um operador de curto circuito, o que significa que se o argumento da esquerda for avaliado como falso, o argumento da direita não será avaliado.</td>
</tr>
<tr>
<td class="confluenceTd"><code>|</code></td>
<td class="confluenceTd">Operador OU lógico. O resultado é de tipo booleano. <code>||</code> também pode ser usado. Este é sempre um operador de curto circuito, o que significa que se o argumento da esquerda for avaliado como verdadeiro, o argumento da direita não será avaliado.</td>
</tr>
<tr>
<td class="highlight-#c1c7d0 confluenceTd" colspan="2" data-highlight-colour="#c1c7d0"><strong title="">Comparação</strong></td>
</tr>
<tr>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Operador</strong></td>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Descrição</strong></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>=</code></td>
<td colspan="1" class="confluenceTd">Atribui a uma variável. O argumento da direita é atribuído ao argumento da esquerda.</td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>==</code></td>
<td colspan="1" class="confluenceTd">Operador de equivalência. Retorna verdadeiro se os dois argumentos forem iguais. Retorna falso se eles não forem iguais.</td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>!=</code></td>
<td colspan="1" class="confluenceTd">Operador de não-equivalência. Retorna verdadeiro se os dois argumentos não forem iguais. Retorna falso se eles forem iguais.</td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>&lt;</code> <br><code>&gt;</code> <br><code>&lt;=</code> <br><code>&gt;=</code></td>
<td colspan="1" class="confluenceTd">Operadores de comparação. Retornam verdadeiro ou falso.</td>
</tr>
<tr>
<th class="highlight-#c1c7d0 confluenceTh" colspan="2" data-highlight-colour="#c1c7d0">Negação</th>
</tr>
<tr>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Operador</strong></td>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Descrição</strong></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>!</code></td>
<td colspan="1" class="confluenceTd"><div class="content-wrapper"><p>Operador de negação. Converte um valor verdadeiro em falso e também o contrário. Por exemplo:</p><div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeContent panelContent pdl">
<div><div id="highlighter_799919" class="syntaxhighlighter sh-confluence nogutter  java"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody>
<tr><td class="code"><div class="container" title="Dica: clique duas vezes para selecionar o código"><div class="line number1 index0 alt2"><code class="java plain">!IsNull($org.workorder.id)</code></div></div></td></tr></tbody></table></div></div>
</div></div></div></td>
</tr>
<tr>
<td class="highlight-#c1c7d0 confluenceTd" colspan="2" data-highlight-colour="#c1c7d0"><strong title="">Vetor (Array)</strong></td>
</tr>
<tr>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Operador</strong></td>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Descrição</strong></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><code>{ }</code></td>
<td colspan="1" class="confluenceTd">
<div class="content-wrapper"><p>Usado para construir um vetor (<em>array</em>). Exemplos:</p>
<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeContent panelContent pdl"><div><div id="highlighter_441874" class="syntaxhighlighter sh-confluence nogutter  java"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Dica: clique duas vezes para selecionar o código"><div class="line number1 index0 alt2"><code class="java plain">$a={</code><code class="java string">"Londres"</code><code class="java plain">,</code><code class="java string">"Paris"</code><code class="java plain">,</code><code class="java string">"Nova York"</code><code class="java plain">};</code></div><div class="line number2 index1 alt1"><code class="java plain">$b={{</code><code class="java string">"John"</code><code class="java plain">,</code><code class="java value">25</code><code class="java plain">},</code></div><div class="line number3 index2 alt2"><code class="java spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="java plain">{</code><code class="java string">"Steve"</code><code class="java plain">,</code><code class="java value">32</code><code class="java plain">},</code></div><div class="line number4 index3 alt1"><code class="java spaces">&nbsp;&nbsp;&nbsp;&nbsp;</code><code class="java plain">{</code><code class="java string">"Daniel"</code><code class="java plain">,</code><code class="java value">26</code><code class="java plain">}</code></div><div class="line number5 index4 alt2"><code class="java spaces">&nbsp;&nbsp;&nbsp;</code><code class="java plain">};</code></div><div class="line number6 index5 alt1"><code class="java plain">$c={</code><code class="java string">"\"citação\""</code><code class="java plain">, </code><code class="java string">'"citação"'</code><code class="java plain">};</code></div></div></td></tr></tbody></table></div></div>
</div></div></div>
</td>
</tr>
</tbody>
</table>
</div>

### Precedência de Operadores

Esta tabela mostra a precedência dos operadores, da mais alta à mais baixa:

<div class="table-wrap">
<table class="wrapped confluenceTable tablesorter tablesorter-default stickyTableHeaders" role="grid" resolved="" style="padding: 0px;">
<colgroup> <col> <col> </colgroup>
<thead class="tableFloatingHeaderOriginal" style="position: static; margin-top: 0px; left: 301px; z-index: 3; width: 375px; top: 61px;">
<tr role="row" class="tablesorter-headerRow">
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="0" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;"><div class="tablesorter-header-inner">Operadores</div></th>
<th colspan="1" class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="1" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;"><div class="tablesorter-header-inner">Descrição</div></th>
</tr>
</thead>
<thead class="tableFloatingHeader" style="display: none;">
<tr role="row" class="tablesorter-headerRow">
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="0" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none;"><div class="tablesorter-header-inner">Operadores</div></th>
<th colspan="1" class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="1" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none;"><div class="tablesorter-header-inner">Descrição</div></th>
</tr>
</thead>
<tbody aria-live="polite" aria-relevant="all">
<tr role="row">
<td class="confluenceTd"><p><code>()</code></p></td>
<td colspan="1" class="confluenceTd">Parênteses para agrupamento</td>
</tr>
<tr role="row">
<td class="confluenceTd"><code>{ }</code></td>
<td colspan="1" class="confluenceTd">Chaves para vetores (<em>arrays</em>)</td>
</tr>
<tr role="row">
<td class="confluenceTd"><code>++ -- -</code></td>
<td colspan="1" class="confluenceTd">Operadores pré e pós unários</td>
</tr>
<tr role="row">
<td class="confluenceTd"><code>^</code></td>
<td colspan="1" class="confluenceTd">Potenciação</td>
</tr>
<tr role="row">
<td class="confluenceTd"><code>!</code></td>
<td colspan="1" class="confluenceTd">Negação</td>
</tr>
<tr role="row">
<td class="confluenceTd"><p><code>* /</code></p></td>
<td colspan="1" class="confluenceTd">Multiplicação, divisão</td>
</tr>
<tr role="row">
<td class="confluenceTd"><code>+ -</code></td>
<td colspan="1" class="confluenceTd">Adição, subtração</td>
</tr>
<tr role="row">
<td class="confluenceTd"><p><code>&lt; &gt; == != &lt;= &gt;=</code></p></td>
<td colspan="1" class="confluenceTd">Operadores de comparação</td>
</tr>
<tr role="row">
<td class="confluenceTd"><code>&amp; &amp;&amp;</code></td>
<td colspan="1" class="confluenceTd">E lógico</td>
</tr>
<tr role="row">
<td class="confluenceTd"><code>| ||</code></td>
<td colspan="1" class="confluenceTd">OU lógico</td>
</tr>
<tr role="row">
<td colspan="1" class="confluenceTd"><code>= += -=</code></td>
<td colspan="1" class="confluenceTd">Atribuição</td>
</tr>
</tbody>
</table>
</div>


## Paleta de Componentes

A paleta de componentes de *script* fornece acesso a vários componentes que podem ser usados dentro de um *script*. Você pode usar componentes dentro de um *script* por arrastá-los ou clicar sobre eles duas vezes na paleta de componentes, por usar o recurso de autocompletar, ou por digitar ou colar manualmente com a sintaxe correta.

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Caso um *script* chame outros componentes de projeto que ainda não foram implantados, estes componentes precisam ser implantados antes que você possa executar o *script* com sucesso.

</div>

</div>

Você pode acessar a paleta de componentes de *script* no lado direito do *designer* de projetos e editor de *scripts*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/component-palette/source-objects_transaction.png" class="confluence-embedded-image confluence-external-resource" /></span>

### Objetos Fonte

A aba **Source Objects** (Objetos Fonte) está presente apenas para *scripts* criados dentro de um *transformation*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_source-objects.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script* de *transformation*, você pode referenciar dados fonte inserindo o caminho de referência de um campo, ou você pode referenciar nós de dados fonte inserindo o caminho de referência de um nó. Inserir o caminho de referência de um campo em um *script* de *transformation* mapeia o objeto fonte para um campo alvo (veja o artigo [Mapeamento de Objetos Fonte](https://success.jitterbit.com/display/CS/Mapping+Source+Objects?showLanguage=pt_BR)). Embora nós não possam ser mapeados para campos alvo, eles podem ser usados como argumentos com algumas [Funções XML](https://success.jitterbit.com/display/CS/XML+Functions?showLanguage=pt_BR) e [Funções de Dicionário e Vetor](https://success.jitterbit.com/display/CS/Dictionary+and+Array+Functions?showLanguage=pt_BR). Os nós também podem ser usados para criar condições em nós alvo (veja o artigo [Mapeamento Condicional](https://success.jitterbit.com/display/CS/Conditional+Mapping?showLanguage=pt_BR)).

Para adicionar o caminho de referência de um campo ou nó a um *script* de *transformation* (apenas com [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste o objeto da paleta para o *script* para inserir o caminho de referência do objeto.

-   Clique duas vezes sobre o objeto na paleta para inserir o caminho de referência do objeto no local do seu cursor dentro do *script*.

-   Digite manualmente o caminho de referência ao objeto fonte.

O exemplo a seguir atribui um objeto fonte a uma variável global em um mapeamento de *transformation*:

```
<trans>
$org.calculate.operand1=root$transaction.request$body$Calculate$input.Operand1$;
</trans>
```

Este exemplo usa um caminho de nó com uma função XML:

```
<trans>
GetXMLString([root$transaction.response$body$queryResponse$result$records.Case$Account$]);
</trans>
```

Para mais informações sobre como caminhos de referência de campos e de nós são construídos, consulte a seção [Notação de Caminhos de Referência](https://success.jitterbit.com/display/CS/Nodes+and+Fields#NodesandFields-reference-paths) no artigo [Nós e Campos](https://success.jitterbit.com/display/CS/Nodes+and+Fields?showLanguage=pt_BR).

### Funções

A aba **Functions** (Funções) fornece uma lista de funções disponíveis para uso em um *script*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_functions.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode usar funções inserindo a sintaxe da função.

Para adicionar a sintaxe da função a um *script* ([Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR) ou [JavaScript](https://success.jitterbit.com/display/CS/JavaScript?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste a função da paleta para o *script* para inserir a sintaxe da função.

-   Clique duas vezes sobre a função na paleta para inserir a sintaxe da função no local do seu cursor dentro do *script*. Ao inserir a sintaxe da função, o primeiro argumento da função fica em destaque e o seu cursor é movido para o final do argumento.

-   Comece a digitar o nome da função depois aperte `Control+Space` para exibir uma lista de sugestões do autocompletar. Selecione uma função para inserir a sintaxe dela.

-   Digite manualmente a sintaxe da função.

Para mais informações, consulte a documentação de cada função por categoria no artigo [Funções](https://success.jitterbit.com/display/CS/Functions?showLanguage=pt_BR).

### Variáveis

A aba **Variables** (Variáveis) fornece acesso a variáveis que estão disponíveis para serem referenciadas globalmente ao longo de todo um projeto, incluindo [variáveis globais](https://success.jitterbit.com/display/CS/Global+Variables?showLanguage=pt_BR), [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) e [variáveis Jitterbit](https://success.jitterbit.com/display/CS/Jitterbit+Variables?showLanguage=pt_BR):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_variables.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode usar variáveis inserindo a sintaxe da variável (veja a documentação de cada tipo de variável no artigo [Variáveis](https://success.jitterbit.com/display/CS/Variables?showLanguage=pt_BR)).

Para adicionar a sintaxe da variável a um *script* ([Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR) ou [JavaScript](https://success.jitterbit.com/display/CS/JavaScript?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste a variável da paleta para o *script* para inserir a sintaxe dela.

-   Clique duas vezes sobre a variável na paleta para inserir a sintaxe dela no local do seu cursor dentro do *script*.

-   Comece a digitar o nome da variável depois aperte `Control+Space` para exibir uma lista de sugestões do autocompletar. Selecione uma variável para inserir a sintaxe dela.

-   Digite manualmente a sintaxe da variável.

As variáveis globais são acessadas quando se digita um cifrão `$` antes do nome da variável ou quando se usam as funções `Set` e `Get`.

Os nomes das variáveis globais podem ser compostos dos seguintes caracteres: letras (a-z, A-Z), números (0-9), pontos finais e *underlines*. Outros caracteres, como hífens, não são recomendados e podem causar problemas. (Note que no caso de [variáveis locais](https://success.jitterbit.com/display/CS/Local+Variables?showLanguage=pt_BR), o caractere do ponto final também não é recomendado).

O seguinte exemplo referencia uma variável global usando um cifrão `$` para criar um dicionário global:

```
<trans>
$org.lookup.currency=Dict();
$org.lookup.currency[1]="USD";
$org.lookup.currency[2]="EUR";
</trans>
```

O exemplo a seguir atribui uma variável global a outra variável global usando as funções `Set` e `Get`:

```
<trans>
Set("op2", Get("op"));
</trans>
```

Note que para certas variáveis Jitterbit, como elas incluem um hífen, você deve referenciá-las usando as funções `Set` ou `Get`:

```
<trans>
Get("jitterbit.networking.http.request.header.content-type");
</trans>
```

As [variáveis locais](https://success.jitterbit.com/display/CS/Local+Variables?showLanguage=pt_BR), embora não estejam listadas na aba **Variables**, não são listadas porque não estão disponíveis globalmente. No entanto, você ainda pode usá-las localmente dentro de um *script*. As variáveis locais têm as seguintes características:

-   Uma variável local é definida e usada apenas dentro de um *script* específico. Portanto, não existe a preocupação de haver conflitos entre o valor de uma variável local no *script* atual e o valor de uma variável local com o mesmo nome em outro *script*.

-   A variável local não pode ser definida nem recuperada pelas funções `Set` ou `Get`.

-   A função `RunScript` pode passar argumentos para o *script*, por exemplo `RunScript(SCRIPT_ID, 5, "abc",...)`. Valores no *script* podem ser atribuídos a variáveis locais pré-definidas `_1`, `_2`, `...`. Neste exemplo, `_1` representa o valor inteiro `5`, enquanto o `_2` representa o valor *string* `"abc"`. A variável local deve ser definida antes de poder ser referenciada, menos no caso dos argumentos de entrada `_1`, `_2`, `...` descritos acima.

-   A função `ArgumentList` está disponível para redefinição de uma lista de variáveis locais como argumentos de entrada.

Para informações mais detalhadas sobre cada tipo de variável e exemplos, consulte o artigo [Variáveis](https://success.jitterbit.com/display/CS/Variables?showLanguage=pt_BR).

### Plugins

A aba **Plugins** fornece uma lista de *plugins* que podem ser executados dentro de um *script*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_plugins.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode usar um *plugin* como argumento para a função [`RunPlugin`](https://success.jitterbit.com/display/CS/General+Functions#GeneralFunctions-RunPlugin) inserindo o caminho de referência do *plugin* (veja o artigo [*Plugins* Chamados em um *Script*](https://success.jitterbit.com/display/CS/Plugins+Called+in+a+Script?showLanguage=pt_BR)).

Para adicionar um caminho de referência de *plugin* a um *script* (apenas com [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste o *plugin* da paleta até o *script* para inserir tanto a função [`RunPlugin`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR) quanto a referência do *plugin*.

-   Clique duas vezes sobre o *plugin* na paleta para inserir a referência do *plugin* no local do seu cursor dentro do *script*.

-   Comece a digitar o nome do *plugin* depois aperte `Control+Space` para exibir uma lista de sugestões do autocompletar. Selecione um *plugin* para inserir a referência do *plugin*.

-   Digite manualmente a referência do *plugin*.

A referência do *plugin* fica contido dentro das *tags* `<TAG>` e `</TAG>` e é composta do tipo do componente de projeto (`plugin`), seguido por dois pontos (`:`), seguidos pelo nome do *plugin* do manifesto XML. O exemplo a seguir usa a função [`RunPlugin`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR) com uma referência ao *plugin* [HMAC-SHA1 Generator](https://success.jitterbit.com/display/DOC/HMAC-SHA1+Generator):

```
<trans>
RunPlugin("<TAG>plugin:http://www.jitterbit.com/plugins/pipeline/user/HMACSHA1Generator</TAG>");
</trans>
```

Note que o nome do *plugin* do manifesto XML não é necessariamente o mesmo nome que é exibido no Management Console.

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Apenas os *plugins* que estão disponíveis para uso dentro de um *script* são listados.*Plugins* adicionais podem ser aplicados a uma atividade dentro de uma operação. Para ver a documentação sobre o uso de *plugins*, incluindo como configurar um *plugin* em nível de atividade e definir variáveis globais, veja as seções do artigo [*Plugins*](https://success.jitterbit.com/display/CS/Plugins?showLanguage=pt_BR).

</div>

</div>

### Operações

A aba **Operations** (Operações) fornece uma lista de operações no projeto que estão disponíveis para serem referenciadas em um *script*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_operations.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode usar uma operação como argumento para funções inserindo o caminho de referência da operação.

Para adicionar um caminho de referência de operação a um *script* (apenas com [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste a operação da paleta até o *script* para inserir tanto a função [`RunOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR) quanto a referência da operação.

-   Clique duas vezes sobre a operação na paleta para inserir a referência da operação no local do seu cursor dentro do *script*.

-   Comece a digitar o nome da operação depois aperte `Control+Space` para exibir uma lista de sugestões do autocompletar. Selecione uma operação para inserir a referência da operação.

-   Digite manualmente a referência da operação.

A referência da operação fica contida dentro das *tags* `<TAG>` e `</TAG>` e é composta pelo tipo de componente de projeto (`operation`), seguido por dois pontos (`:`), seguidos pelo nome da operação, fornecido pelo usuário. O exemplo a seguir usa a função [`RunOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR) com uma referência a uma operação chamada *My Example Operation*:

```
<trans>
RunOperation("<TAG>operation:My Example Operation</TAG>");
</trans>
```

Além de usar a função [`RunOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR), você também pode usar a referência da operação com outras funções da aba **Functions** que aceitam a referência da operação como argumento. Isto inclui funções listadas no artigo [Funções Gerais](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR) que usam `operationInstanceGUID`, `operationID` ou `operationTag` como parâmetros. Por exemplo:

-   [`CancelOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR)

-   [`GetLastOperationRunStartTime`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR)

-   [`GetOperationQueue`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR)

-   [`RunOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR)

-   [`WaitForOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR)

### Notificações

A aba **Notifications** (Notificações) fornece uma lista de notificações no projeto que estão disponíveis para serem referenciadas em um *script*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_notifications.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode referenciar uma notificação como argumento da função [`SendEmailMessage`](https://success.jitterbit.com/display/CS/Email+Functions#EmailFunctions-SendEmailMessage) inserindo o caminho de referência da notificação.

Para adicionar um caminho de referência de notificação a um *script* (apenas com [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste a notificação da paleta até o *script* para inserir tanto a função [`SendEmailMessage`](https://success.jitterbit.com/display/CS/Email+Functions#EmailFunctions-SendEmailMessage) quanto a referência da notificação.

-   Clique duas vezes sobre a notificação na paleta para inserir a referência da notificação no local do seu cursor dentro do *script*.

-   Comece a digitar o nome da notificação depois aperte `Control+Space` para exibir uma lista de sugestões do autocompletar. Selecione uma notificação para inserir a referência dela.

-   Digite manualmente a referência da notificação.

A referência da notificação fica contida dentro das *tags* `<TAG>` e `</TAG>` e é composta pelo tipo de componente de projeto (`email`), seguido por dois pontos (`:`), seguido pelo nome da notificação de *e-mail*, fornecido pelo usuário. O exemplo a seguir usa a função [`SendEmailMessage`](https://success.jitterbit.com/display/CS/Email+Functions?showLanguage=pt_BR) com uma referência a uma notificação de *e-mail* chamada *My Example Email Notification*:

```
<trans>
SendEmailMessage("<TAG>email:My Example Email Notification<TAG>");
</trans>
```

### Scripts

A aba **Scripts** fornece uma lista de todos os outros *scripts* componentes de projeto individuais daquele projeto - escritos seja em Jitterbit Script ou em JavaScript - que estão disponíveis para serem referenciados em um *script*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_scripts.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode referenciar outro *script* como argumento para a função [`RunScript`](https://success.jitterbit.com/display/CS/General+Functions#GeneralFunctions-RunScript) inserindo o caminho de referência do *script*.

Para adicionar um caminho de referência de *script* a um *script* (apenas em [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste o *script* da paleta para o *script* para inserir tanto a função [`RunScript`](https://success.jitterbit.com/display/CS/General+Functions#GeneralFunctions-RunScript) quanto a referência do *script*.

-   Clique duas vezes sobre o *script* na paleta para inserir a referência dele no local do seu cursor dentro do *script*.

-   Comece a digitar o nome do *script* depois aperte `Control+Space` para exibir uma lista de sugestões do autocompletar. Selecione um *script* para inserir a referência dele.

-   Digite manualmente a referência do *script*.

A referência do *script* fica contida dentro das *tags* `<TAG>` e `</TAG>` e é composta do tipo de componente de projeto (`script`), seguido por dois pontos (`:`), seguidos pelo nome do *script*, fornecido pelo usuário. O exemplo a seguir usa a função [`RunScript`](https://success.jitterbit.com/display/CS/General+Functions) com uma referência a um *script* chamado *My Example Script*:

```
<trans>
RunScript("<TAG>script:My Example Script</TAG>");
</trans>
```

### Endpoints

A aba **Endpoints** fornece uma lista de *endpoints* no projeto que estão disponíveis para serem referenciados em um *script*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_endpoints.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode referenciar *endpoints* como argumentos de funções inserindo a conexão ou o caminho de referência da atividade.

Para adicionar uma conexão ou caminho de referência de atividade a um *script* (esteja ele em [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR) ou em [JavaScript](https://success.jitterbit.com/display/CS/JavaScript?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste a conexão ou atividade da paleta até o *script* para inserir a referência apropriada.

-   Clique duas vezes sobre a conexão ou atividade na paleta para inserir a referência apropriada no local do seu cursor dentro do *script*.

-   Comece a digitar o nome da atividade ou conexão depois aperte `Control+Space` para exibir uma lista de sugestões do autocompletar. Selecione uma conexão ou atividade para inserir a referência apropriada.

-   Digite manualmente a referência da conexão ou atividade.

Os tipos de *endpoints* que podem ser usados dentro de *scripts* dependem de haver ou não funções que podem aceitar aquele tipo específico de conexão ou referência de atividade como argumento. As referências a *endpoints* devem ser usadas em conjunto com tais funções para serem válidas no *script*.

Conexões e atividades que podem ser usadas no *script* aparecem dentro de categorias que listam o número de cada item disponível sob cada categoria. Os nomes das atividades são precedidos por colchetes contendo o tipo de interação com o recurso de dados que é específico àquele tipo de atividade (por exemplo, Read, Write, Query, Upsert, GET, POST, etc.). Para aparecerem aqui, as conexões e atividades devem já estar configuradas dentro do projeto. Por exemplo, caso haja uma única conexão HTTP configurada no projeto, com duas atividades configuradas usando essa conexão, elas aparecem agrupadas como na imagem a seguir:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/component-palette/endpoints_http.png" class="confluence-embedded-image confluence-external-resource" /></span>

As referências de conexão ficam contidas dentro das *tags* `<TAG>` e `</TAG>` e são compostas do tipo de componente de projeto (`endpoint`), seguido por dois pontos (`:`), seguidos pelo tipo de *endpoint*, seguido pelo nome da conexão, fornecido pelo usuário. Por exemplo:

```
<TAG>endpoint:database/My Example Database</TAG>
```

Referências de atividades são mais longas, já que a referência à conexão a que elas estão associadas também precisam ser incluídas no caminho. Referências de atividades ficam contidas dentro das *tags* `<TAG>` e `</TAG>` e são compostas do tipo de componente de projeto (`activity`), seguido por dois pontos (`:`), seguidos pelo tipo e nome da conexão, seguidos pelo tipo de atividade, seguido pelo nome da atividade, fornecido pelo usuário. Por exemplo:

```
<TAG>activity:database/My Example Database/database_query/Query Employees</TAG>
```

Dependendo da conexão ou tipo de atividade específico conforme listado abaixo, você pode usar funções da aba **Functions** que aceitam uma referência de conector como argumento. As funções descritas abaixo estão disponíveis para uso com as conexões e atividades listadas.

<div class="table-wrap">
<table class="relative-table wrapped confluenceTable" style="width: 100.0%;" resolved="">
<colgroup>
<col style="width: 15.9836%;">
<col style="width: 40.7377%;">
<col style="width: 43.1148%;">
</colgroup>
<tbody>
<tr>
<td class="highlight-#f4f5f7 confluenceTd" data-highlight-colour="#f4f5f7"><strong title="">Category</strong></td>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Description</strong></td>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Use of Components as Function Parameters</strong></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><strong title=""><em>Endpoints</em> Database</strong></td>
<td class="confluenceTd"><p>Esta categoria inclui todas as conexões <a href="/display/CS/Database">Database</a> configuradas e suas atividades associadas, ambas as quais podem ser usadas em <em>scripts</em> dependendo da função específica.</p></td>
<td colspan="1" class="confluenceTd"><p>Conexões de banco de dados podem ser usadas com qualquer função listada no artigo <a href="/display/CS/Database+Functions">Conexões de Banco de Dados</a> que usam <code>databaseId</code> como parâmetro, incluindo:</p>
<ul><li style="list-style-type: none;"><ul><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-CacheLookup">CacheLookup</a></code></li><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-CallStoredProcedure">CallStoredProcedure</a></code></li><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-DBCloseConnection">DBCloseConnection</a></code></li><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-DBExecute">DBExecute</a></code></li><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-DBLookup">DBLookup</a></code></li><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-DBLookupAll">DBLookupAll</a></code></li><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-DBRollbackTransaction">DBRollbackTransaction</a></code></li><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-DBWrite">DBWrite</a></code></li></ul></li></ul>
<p>Atividades de banco de dados podem ser usadas com qualquer função listada em <a href="/display/CS/Database+Functions">Funções de Banco de Dados</a> que usam <code>target</code> como parâmetro, incluindo:</p>
<ul><li style="list-style-type: none;"><ul><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-DBLoad">DBLoad</a></code></li></ul></li></ul></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><p title=""><strong><em>Endpoints</em> File Share</strong></p><p title=""><strong><em>Endpoints</em> FTP</strong></p><p title=""><strong><em>Endpoints</em> HTTP</strong></p><p title=""><strong><em>Endpoints</em> Local Storage</strong></p><p title=""><strong><em>Endpoints</em> Temporary Storage</strong></p></td>
<td class="confluenceTd"><div class="content-wrapper"><p>Estas categorias incluem qualquer conexão configurada dos tipos <a href="/display/CS/File+Share">File Share</a>, <a href="/display/CS/FTP">FTP</a>, <a href="/display/CS/HTTP">HTTP</a>, <a href="/display/CS/Local+Storage">Local Storage</a>, e <a href="/display/CS/Temporary+Storage">Temporary Storage</a> (que não podem ser usadas em <em>scripts</em>) e suas atividades associadas (que podem ser usadas em <em>scripts</em>).</p>
<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info"><span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span><div class="confluence-information-macro-body"><p><strong>NOTA:</strong>&nbsp;Embora também exista uma categoria <strong><em>Endpoints</em> API</strong>, nem as conexões nem as atividades&nbsp;<a href="/display/CS/API">API</a> podem ser usadas em <em>scripts</em>.</p></div></div></div></td>
<td colspan="1" class="confluenceTd"><div class="content-wrapper"><p>As atividades incluídas (menos as atividades API) podem ser usadas com qualquer função listada nos artigos <a href="/display/CS/Cryptographic+Functions">Funções Criptográficas</a>, <a href="/display/CS/Database+Functions">Funções de Banco de Dados</a>, <a href="/display/CS/File+Functions">Funções de Arquivo</a>, ou <a href="/display/CS/Salesforce+Functions">Funções Salesforce</a> que usam <code>sourceId</code> ou <code>targetId</code> como parâmetro, incluindo as seguintes:</p><ul><li><code><a href="/display/CS/File+Functions#FileFunctions-ArchiveFile">ArchiveFile</a></code></li><li><code><a href="/display/CS/Cryptographic+Functions#CryptographicFunctions-Base64EncodeFile">Base64EncodeFile</a></code></li><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-DBLoad">DBLoad</a></code></li><li><code><a href="/display/CS/Database+Functions#DatabaseFunctions-DBWrite">DBWrite</a></code></li><li><code><a href="/display/CS/File+Functions#FileFunctions-DeleteFile">DeleteFile</a></code></li><li><code><a href="/display/CS/File+Functions#FileFunctions-DeleteFiles">DeleteFiles</a></code></li><li><code><a href="/display/CS/File+Functions#FileFunctions-DirList">DirList</a></code></li><li><code><a href="/display/CS/File+Functions#FileFunctions-FileList">FileList</a></code></li><li><code><a href="/display/CS/File+Functions#FileFunctions-FlushAllFiles">FlushAllFiles</a></code></li><li><code><a href="/display/CS/File+Functions#FileFunctions-FlushFile">FlushFile</a></code></li><li><code><a href="/display/CS/File+Functions#FileFunctions-ReadFile">ReadFile</a></code></li><li><code><a href="/display/CS/Salesforce+Functions#SalesforceFunctions-SfLookupAllToFile">SfLookupAllToFile</a></code></li><li><code><a href="/display/CS/File+Functions#FileFunctions-WriteFile">WriteFile</a></code></li></ul></div></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><strong title=""><em>Endpoints</em> Salesforce</strong></td>
<td class="confluenceTd">Esta categoria inclui qualquer conexão configurada da <a href="/display/CS/Salesforce">Salesforce</a> (que podem ser usadas em <em>scripts</em>). Atividades Salesforce não estão incluídas, já que não podem ser usadas em <em>scripts</em>.</td>
<td colspan="1" class="confluenceTd"><p>Conexões da Salesforce podem ser usadas com qualquer função listada no artigo <a href="/display/CS/Salesforce+Functions">Funções Salesforce</a> que usam <code>salesforceOrg</code> como parâmetro, incluindo:</p><ul><li><code><a href="/display/CS/Salesforce+Functions#SalesforceFunctions-LoginToSalesforceAndGetTimeStamp">LoginToSalesforceAndGetTimeStamp</a></code></li><li><code><a href="/display/CS/Salesforce+Functions#SalesforceFunctions-SalesforceLogin">SalesforceLogin</a></code></li><li><code><a href="/display/CS/Salesforce+Functions#SalesforceFunctions-SetSalesforceSession">SetSalesforceSession</a></code></li><li><code><a href="/display/CS/Salesforce+Functions#SalesforceFunctions-SfCacheLookup">SfCacheLookup</a></code></li><li><code><a href="/display/CS/Salesforce+Functions#SalesforceFunctions-SfLookup">SfLookup</a></code></li><li><code><a href="/display/CS/Salesforce+Functions#SalesforceFunctions-SfLookupAll">SfLookupAll</a></code></li><li><code><a href="/display/CS/Salesforce+Functions#SalesforceFunctions-SfLookupAllToFile">SfLookupAllToFile</a></code></li></ul></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><strong title=""><em>Endpoints</em> NetSuite</strong></td>
<td class="confluenceTd">Esta categoria inclui qualquer conexão configurada da <a href="/display/CS/NetSuite+Connection">NetSuite</a> (que podem ser usadas em <em>scripts</em>). Atividades NetSuite não estão incluídas, já que não podem ser usadas em <em>scripts</em>.</td>
<td colspan="1" class="confluenceTd">Conexões NetSuite podem ser usadas com qualquer função listada no artigo <a href="/display/CS/NetSuite+Functions">Funções NetSuite</a> que usam <code>netSuiteOrg</code> como parâmetro, incluindo:</span><ul><li style="list-style-type: none;"><ul><li><code><span class="toc-item-body"><a href="/display/CS/NetSuite+Functions#NetSuiteFunctions-NetSuiteGetSelectValue">NetSuiteGetSelectValue</a></span></code></li><li><code><span class="toc-item-body"><a href="/display/CS/NetSuite+Functions#NetSuiteFunctions-NetSuiteGetServerTime">NetSuiteGetServerTime</a></span></code></li><li><p><code><span class="toc-item-body"><a href="/display/CS/NetSuite+Functions#NetSuiteFunctions-NetSuiteLogin">NetSuiteLogin</a></span></code></p></li></ul></li></ul></td>
</tr>
</tbody>
</table>
</div>

## Tipos de Dado

Todos os objetos fonte e variáveis globais que não são nulos têm um tipo de dado associado. Vários tipos de dados podem ser mudados usando as funções na categoria [Funções de Conversão](https://success.jitterbit.com/display/CS/Conversion+Functions?showLanguage=pt_BR).

Os seguintes tipos de dados são suportados em Jitterbit Scripts:

<div class="table-wrap">
<table class="wrapped confluenceTable tablesorter tablesorter-default stickyTableHeaders" role="grid" resolved="" style="padding: 0px;">
<colgroup><col><col><col></colgroup>
<thead class="tableFloatingHeaderOriginal" style="position: static; margin-top: 0px; left: 301px; z-index: 3; width: 536px; top: 61px;"><tr role="row" class="tablesorter-headerRow">
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="0" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;"><div class="tablesorter-header-inner">Tipo</div></th>
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="1" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;"><div class="tablesorter-header-inner"><p>Descrição</p></div></th>
<th colspan="1" class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="2" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;"><div class="tablesorter-header-inner"><p>Classificação</p></div></th>
</tr></thead>
<thead class="tableFloatingHeader" style="display: none;"><tr role="row" class="tablesorter-headerRow">
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="0" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none;"><div class="tablesorter-header-inner">Tipo</div></th>
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="1" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none;"><div class="tablesorter-header-inner"><p>Descrição</p></div></th>
<th colspan="1" class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="2" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none;"><div class="tablesorter-header-inner"><p>Classificação</p></div></th>
</tr></thead>
<tbody aria-live="polite" aria-relevant="all">
<tr role="row">
<td colspan="1" class="confluenceTd"><code>binary</code></td>
<td colspan="1" class="confluenceTd">Binário</td>
<td colspan="1" class="confluenceTd">Dado</td>
</tr><tr role="row">
<td colspan="1" class="confluenceTd"><code>bit</code></td>
<td colspan="1" class="confluenceTd">Bit</td>
<td colspan="1" class="confluenceTd">Dado</td>
</tr><tr role="row">
<td colspan="1" class="confluenceTd"><code>bool</code></td>
<td colspan="1" class="confluenceTd">Booleano</td>
<td colspan="1" class="confluenceTd">Lógico</td>
</tr><tr role="row">
<td class="confluenceTd"><code>int</code></td>
<td class="confluenceTd"><p>Inteiro</p></td>
<td colspan="1" class="confluenceTd">Numérico</td>
</tr><tr role="row">
<td colspan="1" class="confluenceTd"><code>decimal</code></td>
<td colspan="1" class="confluenceTd">Decimal</td>
<td colspan="1" class="confluenceTd">Numérico</td>
</tr><tr role="row">
<td class="confluenceTd"><code>double</code></td>
<td class="confluenceTd"><em>Double</em></td>
<td colspan="1" class="confluenceTd">Numérico</td>
</tr><tr role="row">
<td colspan="1" class="confluenceTd"><code>float</code></td>
<td colspan="1" class="confluenceTd"><em>Float</em></td>
<td colspan="1" class="confluenceTd">Numérico</td>
</tr><tr role="row">
<td class="confluenceTd"><code>long</code></td>
<td class="confluenceTd"><em>Long</em></td>
<td colspan="1" class="confluenceTd">Numérico</td>
</tr><tr role="row">
<td colspan="1" class="confluenceTd"><code>date</code></td>
<td colspan="1" class="confluenceTd">Data</td>
<td colspan="1" class="confluenceTd">Data &amp; Hora</td>
</tr><tr role="row">
<td colspan="1" class="confluenceTd"><code>timespan</code></td>
<td colspan="1" class="confluenceTd"><em>Timespan</em> (Data com hora) </td>
<td colspan="1" class="confluenceTd">Data &amp; Hora</td>
</tr><tr role="row">
<td class="confluenceTd"><code>string</code></td>
<td class="confluenceTd"><em>String</em></td>
<td colspan="1" class="confluenceTd"><em>String</em></td>
</tr><tr role="row">
<td class="confluenceTd"><code>array</code></td>
<td class="confluenceTd">Vetor</td>
<td colspan="1" class="confluenceTd">Coleção</td>
</tr><tr role="row">
<td class="confluenceTd"><code>dictionary</code></td
<td class="confluenceTd">Dicionário (também conhecido como <code>map</code>)</td>
<td colspan="1" class="confluenceTd">Coleção</td>
</tr><tr role="row">
<td class="confluenceTd"><code>instance</code></td>
<td class="confluenceTd">Instância em uma fonte ou alvo de dados</td>
<td colspan="1" class="confluenceTd"><em>Schema</em></td>
</tr><tr role="row">
<td class="confluenceTd"><code>node</code></td>
<td class="confluenceTd">Nó em um <em>schema</em> de uma fonte ou alvo de dados</td>
<td colspan="1" class="confluenceTd"><em>Schema</em></td>
</tr><tr role="row">
<td colspan="1" class="confluenceTd"><code>type</code></td>
<td colspan="1" class="confluenceTd">Qualquer um destes tipos</td>
<td colspan="1" class="confluenceTd">Dado</td>
</tr><tr role="row">
<td colspan="1" class="confluenceTd"><code>null</code></td>
<td colspan="1" class="confluenceTd">Valor nulo</td>
<td colspan="1" class="confluenceTd">Dado</td>
</tr><tr role="row">
<td colspan="1" class="confluenceTd"><code>var</code></td>
<td colspan="1" class="confluenceTd">Referência a uma variável, seja local ou global</td>
<td colspan="1" class="confluenceTd"><em>Script</em></td>
</tr>
</tbody>
</table>
</div>

### Vetores

Um vetor é uma coleção de variáveis. Cada membro da coleção pode ser de qualquer tipo suportado, incluindo vetores. Os membros de um vetor podem ser acessados usando os métodos [`Get`](https://success.jitterbit.com/display/CS/General+Functions#GeneralFunctions-Get) e [`Set`](https://success.jitterbit.com/display/CS/General+Functions#GeneralFunctions-Set) ou usando a sintaxe `[] array`. Os vetores começam no índice zero, e os índices são numéricos, sequenciais e não podem ser pulados.

Você também pode criar vetores de variáveis globais. Uma variável global vetor é um vetor de outras variáveis globais que, por sua vez, também podem ser vetores.

#### Definindo um Vetor

Você pode definir os valores de um vetor usando a função [`Set`](https://success.jitterbit.com/display/CS/General+Functions#GeneralFunctions-Set) com a seguinte sintaxe:

```
type Set(string name, type value \[, int index1, int index2, ...\])
```

Isto torna o valor da variável global com o nome dado igual ao valor especificado, e retorna tal valor. Se o primeiro argumento for um vetor ou o nome de uma variável global vetor, você pode definir o valor da variável vetor especificando o índice (ou os índices, no caso de vetores multidimensionais) como o terceiro argumento.

Nem todos os itens de um vetor precisam ser do mesmo tipo. Por exemplo, você pode criar um vetor que contém uma data, um inteiro e uma *string*. Você pode até criar vetores dentro de outros vetores.

Este exemplo cria um vetor com três variáveis de diferentes tipos onde cada entrada representa a data e a hora atuais:

```
<trans>
$right_now = Now();
Set($now, $right_now, 0);
Set($now, Long($right_now), 1);
Set($now, String($right_now), 2);
</trans>
```

Visto que os vetores começam no índice zero, o primeiro elemento fica no índice 0 e o último elemento fica no índice (tamanho-1). Para adicionar dados a um vetor, passe um valor de índice negativo ou o tamanho do vetor (`Length($arr)`). Definir um elemento com um índice maior que o tamanho do vetor resulta em um erro de índice fora de escopo. Definir elementos de dados que não são vetores também pode ser feito usando a sintaxe `$de_name`.

Seguem-se alguns exemplos de como definir valores em um vetor:

```
// Definir a entrada na posição n de um vetor como a string "value"
Set($arr, "value", n-1);

// Outra forma de definir a entrada na posição n de um vetor
Set($arr, "value", Length($arr));

// Define o valor de uma nova variável no final do vetor
Set($arr, "value", -1);

// Definir a entrada na posição n do vetor na posição m
Set($record_set, "value", m-1, n-1);
```

<div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**DICA**: Para ver sintaxe adicional que pode ser usada para definir valores em um vetor, consulte o artigo [Funções de Dicionário e Vetor](https://success.jitterbit.com/display/CS/Dictionary+and+Array+Functions?showLanguage=pt_BR).

</div>

</div>

#### Acessando um Vetor

Você pode acessar os itens de um vetor usando o método [`Get`](https://success.jitterbit.com/display/CS/General+Functions#GeneralFunctions-Get) com a seguinte sintaxe:

```
type Get(string name\[, int index1, int index2, ...\])
```

Isto retorna o valor da variável global com o nome dado. Se o primeiro argumento for um vetor ou o nome de uma variável global vetor, você pode achar uma variável específica se determinar um índice (ou índices no caso de vetores multidimensionais como um conjunto de registros) como segundo argumento.

Algumas [funções](https://success.jitterbit.com/display/CS/Functions) têm vetores como seus valores de retorno. Por exemplo, a função [`SelectNodesFromXMLAny`](https://success.jitterbit.com/display/CS/XML+Functions#XMLFunctions-SelectNodesFromXMLAny) retorna os resultados de uma *query* XPath em formato de vetor. Como outro exemplo, a função [`DbExecute`](https://success.jitterbit.com/display/CS/Database+Functions#DatabaseFunctions-DbExecute) retorna um conjunto de registros como seu vetor bidimensional (às vezes chamado de matriz em português): fileiras primeiro, depois colunas. Isto retorna os dados selecionados como um vetor de vetores (representando as fileiras e colunas selecionadas):

```
<trans>
$resultSet = DbExecute("<TAG>endpoint:database/My Database</TAG>", "select Result from SimpleCalculatorResults");
$primeiraFileira = Get($resultSet, 0);
$terceiraColunaDaSegundaFileira = $resultSet[2][3];
$segundaColunaDaTerceiraFileira = Get($resultSet, 3, 2);
</trans>
```

Vetores começam do índice zero. Para acessar a enésima variável de um vetor chamado `"arr"`, use `Get("arr", n-1)`. Para vetores multidimensionais você precisa especificar todos os índices. Para acessar a enésima coluna da fileira `m` em um vetor chamado `ResultSet` você usaria `Get("ResultSet", m-1, n-1)`. Tentar buscar uma variável além do fim do vetor resulta em erro de índice fora do escopo.

Seguem-se exemplos de como buscar valores de um vetor:

```
// Retorna a terceira variável do vetor
Get($arr, 2);

// Outra forma de retornar a terceira variável do vetor
Get(“arr”, 2);

// Busca a enésima variável do vetor m em arr
Get($arr, m-1, n-1);
```

Este exemplo mostra como você pode primeiro criar um *script* que constrói e retorna um vetor. O segundo bloco mostra como executar este *script* e atribuir o valor que ele retorna a uma variável.

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;"><b>Construir Vetor</b></div><div class="codeContent panelContent pdl">
<div><div id="highlighter_645456" class="syntaxhighlighter sh-confluence nogutter  java"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Dica: clique duas vezes para selecionar o código"><div class="line number1 index0 alt2"><code class="java plain">&lt;trans&gt;</code></div><div class="line number2 index1 alt1"><code class="java comments">// Script para construir e retornar um vetor</code></div><div class="line number3 index2 alt2"><code class="java plain">a = Array();</code></div><div class="line number4 index3 alt1"><code class="java plain">a[Length(a)] = </code><code class="java string">"A"</code><code class="java plain">;</code></div><div class="line number5 index4 alt2"><code class="java plain">a[Length(a)] = </code><code class="java string">"B"</code><code class="java plain">;</code></div><div class="line number6 index5 alt1"><code class="java plain">a[Length(a)] = </code><code class="java string">"C"</code><code class="java plain">;</code></div><div class="line number7 index6 alt2"><code class="java plain">a;</code></div><div class="line number8 index7 alt1"><code class="java plain">&lt;/trans&gt;</code></div></div></td></tr></tbody></table></div></div>
</div></div>

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;"><b>Chamar o <em>Script</em></b></div><div class="codeContent panelContent pdl">
<div><div id="highlighter_342641" class="syntaxhighlighter sh-confluence nogutter  java"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Dica: clique duas vezes para selecionar o código"><div class="line number1 index0 alt2"><code class="java plain">&lt;trans&gt;</code></div><div class="line number2 index1 alt1"><code class="java comments">// Chamar o script para recuperar o vetor</code></div><div class="line number3 index2 alt2"><code class="java plain">$Arr = RunScript(</code><code class="java string">"&lt;TAG&gt;script:Construir Vetor&lt;/TAG&gt;"</code><code class="java plain">);</code></div><div class="line number4 index3 alt1"><code class="java plain">&lt;/trans&gt;</code></div></div></td></tr></tbody></table></div></div>
</div></div>

<div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**DICA**: Para ver sintaxe adicional que pode ser usada para acessar valores em um vetor, consulte o artigo [Funções de Dicionário e Vetor](https://success.jitterbit.com/display/CS/Dictionary+and+Array+Functions?showLanguage=pt_BR).

</div>

</div>

### Dicionários

Em Jitterbit Script, um dicionário é um tipo especial de vetor variável global que armazena valores chave-valor. As etapas e as funções são:

1.  Inicialize o dicionário usando a função [`Dict`](https://success.jitterbit.com/display/CS/Dictionary+and+Array+Functions#DictionaryandArrayFunctions-Dict):

    ```
    $d = Dict();
    ```

2.  Carregue dados com uma chave e um valor:

    ```
    $d[‘4011’] = ‘Banana’;
    $d[‘4063’] = ‘Tomate’;
    ```

3.  Verifique se a chave já existe no dicionário usando a função [`HasKey`](https://success.jitterbit.com/display/CS/Dictionary+and+Array+Functions#DictionaryandArrayFunctions-HasKey):

    ```
    HasKey($d, ‘4011’); // Retorna verdadeiro
    ```

    No exemplo, nós já carregamos a chave ‘4011’, portanto `HasKey` retornará o valor `true` (verdadeiro).

    ```
    HasKey($d, ‘4089’); // Retorna falso
    ```

    Se a chave já não estivesse carregada, por exemplo, ‘4089’, então `HasKey` retornaria o valor `false` (falso).

4.  Consulte um valor no dicionário fornecendo a chave e recebendo em troca o valor:

    ```
    $d\[‘4011’\]; // Retorna ‘Banana’
    ```

    Neste exemplo, o valor retornado seria `Banana`.

Ao trabalhar com dicionários, mantenha as seguintes características em mente:

-   O escopo de um dicionário é limitado ao workflow. Por exemplo, se uma operação carrega `$MyDict` com 10.000 registros, apenas aquelas operações que estão conectadas usando caminhos "em caso de sucesso" ou "em caso de falha", ou com a função `RunOperation` têm acesso ao dicionário. Mas, se uma operação usa fragmentação de dados (*chunking*) e *threading*, e tem um *transformation* que preenche um dicionário, o dicionário é inconsistente. Isto ocorre porque o Jitterbit Harmony não pega os valores atribuídos a variáveis por várias *threads* de operação e os concatena em um único conjunto de valores. Isto vale para todas as variáveis ou vetores globais. Use os valores de *chunking*/*threading* padrão ao construir uma operação que preenche um dicionário.

-   Dicionários, como usam busca binária, são rápidos para achar chaves e retornar valores. Uma chave normalmente pode ser achada em cinco a seis tentativas. Em contraste, compare esse tipo de busca com fazer iterações em um vetor de 10.000 registros para achar uma chave.

-   Os dicionários não são gravados na memória, então eles não têm impacto sobre a memória do servidor disponível para processamento.
