[//]: # (JavaScript)
[//]: # (This is a translation of Version 24, published on October 14, 2021.)


## Introdução

O JavaScript está disponível para uso em *scripts* criados apenas como componentes de projeto (não em *scripts* usados dentro de um *transformation*). Esta página fornece informações sobre o suporte ao JavaScript no Jitterbit Harmony, além de alguns exemplos para ajudar você a começar. Veja também as páginas relacionadas sobre como [criar um *script*](https://success.jitterbit.com/display/CS/Script+Types+and+Creation?showLanguage=pt_BR), [usar o editor de *scripts*](https://success.jitterbit.com/display/CS/Script+Editor?showLanguage=pt_BR) e [testar um *script*](https://success.jitterbit.com/display/CS/Script+Testing?showLanguage=pt_BR).


## Suporte ao JavaScript no Jitterbit Harmony

O motor de JavaScript do Jitterbit Harmony suporta o padrão [ECMA-262 v5.1](https://jitterbit-documentation.s3.amazonaws.com/confluence-resources/Ecma-262-5.1-Edition-June-2011.pdf) conforme especificado no [ECMA International](https://www.ecma-international.org/). Esta versão do JavaScript tem suporte nativo ao JSON e à definição e uso de funções dentro de *scripts*. O JavaScript da Jitterbit conforma-se à manipulação de objetos e comportamento padrão do JavaScript.

<div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**AVISO**: Embora a Jitterbit suporte JavaScript baseado no padrão, nem todas as funcionalidades do JavaScript estão disponíveis. A Jitterbit **_não_** suporta as seguintes características do JavaScript:

-   APIs web do DOM (Document Object Model)

-   Funções e objetos Mozilla

-   Certos tipos do JavaScript como `Set` e `Map`

-   Acesso a objetos Java

</div>

</div>

Tipos de dados simples, vetores e objetos JSON são totalmente suportados. Mapas Jitterbit também são suportados dentro do JavaScript. O JavaScript trata os mapas Jitterbit como objetos JSON, e os Jitterbit Scripts tratam objetos JSON como mapas Jitterbit. As propriedades do JSON são acessadas usando as chaves dos mapas.

Por exemplo, dado o seguinte objeto JSON definido no JavaScript:

```
var $meuObjeto = {
    "nome":"John",
    "idade":30,
    "carros": {
        "carro1":"Ford",
        "carro2":"BMW",
        "carro3":"Fiat"
        }
    };
```

Em um Jitterbit Script, o objeto seria acessado por meio de um mapa. Acesse a propriedade `"carro3"` assim:

```
$meuCarro = $meuObjeto["carros"]["carro3"];
```

Depois de ter criado um novo JavaScript no Cloud Studio, você pode inserir o *script* diretamente dentro do editor de *scripts*. Nos JavaScripts usados no Cloud Studio, os *scripts* devem estar cercados por uma *tag* de abertura `<javascript>` e uma *tag* de fechamento `</javascript>`.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/script/javascript.png" class="confluence-embedded-image confluence-external-resource" /></span>

### Iterações de Laços

O maior número de iterações de um mesmo laço permitido no Jitterbit Harmony é 50.000. O número máximo de iterações de laço no JavaScript é por *script*, não por laço.

Por exemplo, um *script* JavaScript contendo três laços no qual cada laço executa 25.000 iterações daria um total de 75.000 iterações dentro de um mesmo *script*.

Para aumentar o número máximo de iterações permitidas em um único *script* JavaScript, adicione manualmente `JavaScriptMaxIterations=X` onde `X` seja maior que `50000`.

Para mais informações sobre como aumentar o número máximo de laços permitido, consulte a seção [`[Settings]`](https://success.jitterbit.com/display/DOC/Editing+the+Configuration+File+-+jitterbit.conf#EditingtheConfigurationFilejitterbit.conf-conf_settings) (Configurações) do artigo [Editando o Arquivo de Configuração - jitterbit.conf](https://success.jitterbit.com/display/DOC/Editing+the+Configuration+File+-+jitterbit.conf?showLanguage=pt_BR).

Para ver um exemplo de laço, consulte o subtópico [Laço JavaScript](https://success.jitterbit.com/display/CS/JavaScript#JavaScript-JavaScriptLoop) mais abaixo nesta mesma página, sob a seção [Exemplos](https://success.jitterbit.com/display/CS/JavaScript#JavaScript-examples).


## Paleta de Componentes

A paleta de componentes de *script* fornece acesso a vários componentes que podem ser usados dentro de um *script*. Você pode usar componentes dentro de um *script* por arrastá-los ou clicar sobre eles duas vezes na paleta de componentes, por usar o recurso do auto-completar, ou por manualmente digitar ou colar a sintaxe correta.

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Caso um *script* chame outros componentes de projeto que ainda não tenham sido implantados, tais componentes precisam ser implantados para que você possa executar o *script* com sucesso.

</div>

</div>

Você pode acessar a paleta de componentes de *script* no lado direito do *designer* de projetos e editor de *scripts*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/component-palette/functions_javascript.png" class="confluence-embedded-image confluence-external-resource" /></span>

Algumas das abas exibidas na paleta de componentes de *script* mostram componentes que não podem ser usados em um *script* escrito em JavaScript. Especificamente, referenciar *plugins*, operações, notificações e outros *scripts* em um *script* escrito em JavaScript não é suportado. As abas que contêm funções ou componentes que podem ser usados em *scripts* escritos em JavaScript são descritas abaixo.

### Funções

A aba **Functions** (Funções) fornece uma lista de funções disponíveis para uso dentro de um *script*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_functions.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode usar funções inserindo a sintaxe da função desejada.

Para adicionar a sintaxe de uma função a um *script* (em [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR) ou em [JavaScript](https://success.jitterbit.com/display/CS/JavaScript?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste a função da paleta para o *script* para inserir a sintaxe da função.

-   Clique duas vezes sobre a função na paleta para inserir a sintaxe da função no local do seu cursor dentro do *script*. Ao inserir a sintaxe da função, o primeiro argumento da função fica em destaque e o seu cursor é movido para o final do argumento.

-   Comece a digitar o nome da função depois aperte `Control+Space` para exibir uma lista de sugestões do autocompletar. Selecione uma função para inserir a sintaxe dela.

-   Digite manualmente a sintaxe da função.

As funções disponíveis para uso em um JavaScript estão disponíveis sob quatro categorias: **Jitterbit**, **Keywords** (Palavras-Chave), **Common Functions** (Funções Comuns) e **Math** (Matemática). Para informações detalhadas sobre cada função disponível em JavaScript no Jitterbit Harmony, consulte as seguintes páginas:

-   [Funções Jitterbit e Funções Comuns em JavaScript](https://success.jitterbit.com/display/CS/JavaScript+Jitterbit+and+Common+Functions?showLanguage=pt_BR)

-   [Propriedades e Funções Padrão em JavaScript](https://success.jitterbit.com/display/CS/JavaScript+Standard+Properties+and+Functions?showLanguage=pt_BR)

### Variáveis

A aba **Variables** (Variáveis) fornece acesso a variáveis que estão disponíveis para serem referenciadas globalmente por todo um projeto, incluindo as [variáveis globais](https://success.jitterbit.com/display/CS/Global+Variables?showLanguage=pt_BR), [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) e [variáveis Jitterbit](https://success.jitterbit.com/display/CS/Jitterbit+Variables?showLanguage=pt_BR):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_variables.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode usar uma variável inserindo a sintaxe dela (consulte a documentação de cada tipo de variável no artigo [Variáveis](https://success.jitterbit.com/display/CS/Variables?showLanguage=pt_BR)).

Para adicionar a sintaxe de uma variável a um *script* (em [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR) ou em [JavaScript](https://success.jitterbit.com/display/CS/JavaScript?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste a variável da paleta para o *script* para inserir a sintaxe dela.

-   Clique duas vezes sobre a variável na paleta para inserir a sintaxe dela no local do seu cursor dentro do *script*.

-   Comece a digitar o nome da variável depois aperte `Control+Space` para exibir uma lista de sugestões do autocompletar. Selecione uma variável para inserir a sintaxe dela.

-   Digite manualmente a sintaxe da variável.

[Variáveis locais](https://success.jitterbit.com/display/CS/Local+Variables?showLanguage=pt_BR) não são listadas porque não estão disponíveis globalmente; no entanto, você ainda pode usá-las localmente dentro de um *script*.

#### Variáveis Globais

Todas as variáveis globais Jitterbit podem ser acessadas e atualizadas por um JavaScript. Qualquer nova variável global JavaScript que for definida se tornará uma variável global Jitterbit.

A sintaxe usada para definir e para recuperar o valor de uma variável global depende se o nome dela contém ou não um ponto.

<div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**AVISO**: As funções `Jitterbit.SetVar` e `Jitterbit.GetVar` foram projetadas para permitir o uso de variáveis que contenham pontos em seus nomes. Porém, usar pontos no nome de uma variável não é recomendado. Visto que o valor é convertido em *string* quando a variável é definida, estas funções não podem ser usadas com tipos de dados complexos tais como vetores, dicionários ou objetos JSON. Em vez disso, recomendamos que você crie variáveis Jitterbit sem pontos e que use *underlines* no lugar deles, além de usar a sintaxe padrão do cifrão `$` conforme a descrição abaixo.

</div>

</div>

<div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**DICA**: Informações adicionais sobre as funções `Jitterbit.GetVar` e `Jitterbit.SetVar` estão disponíveis na próxima seção, sob o subtítulo [Funções](https://success.jitterbit.com/display/CS/JavaScript#JavaScript-Functions).

</div>

</div>

##### Definindo uma Variável Global

-   **Nomes sem pontos <span style="color: rgb(51,153,102);">(recomendado)</span>:** Uma variável global que não contém pontos em seu nome pode ser criada inicialmente ou atualizada usando o comando `var $`, ou atualizada usando um cifrão `$` sem a palavra `var`.

    -   **`var $`:** Usando a palavra `var` e começando com um cifrão `$`, o código exemplo var `$serverURL="https://www.exemplo.com"` cria ou atualiza uma variável global chamada `serverURL` com o valor `https://www.example.com`. As novas variáveis globais que estão sendo inicializadas precisam ter a palavra `var` antes do cifrão `$`.

    -   **`$`:** Usando como prefixo um cifrão `$`, o código exemplo `$serverURL="https://www.example.com"` atualiza a mesma variável global chamada "serverURL" com a mesma URL. Isto só funciona para variáveis globais que já estão inicializadas.

-   **Nomes com pontos <span style="color: rgb(255,0,0);">(não recomendado)</span>:** Uma variável global que contém pontos em seu nome pode ser criada inicialmente ou atualizada somente com a função `Jitterbit.SetVar`.

    -   **`Jitterbit.SetVar`:** Usando a função Jitterbit.SetVar, o código exemplo `Jitterbit.SetVar("$server.URL", "https://www.example.com")` cria ou atualiza uma variável global chamada `server.URL` com o valor `https://www.example.com` que é tratada como *string*. Repare que o cifrão `$` **_deve_** estar incluído dentro do nome da variável, caso contrário a variável não será global no sistema do Harmony.

##### Recuperando o Valor de uma Variável Global

-   **Nomes sem pontos:** O valor de uma variável global que não contém pontos em seu nome pode ser recuperado com o uso de um cifrão `$`.

    -   **`$`:** Com o uso de um cifrão `$`, o código exemplo `$serverURL` recupera o valor da variável global chamada `serverURL`.

-   **Nomes com pontos:** O valor de uma variável global que contém pontos em seu nome pode ser recuperado apenas com a ajuda da função `Jitterbit.GetVar`.

    -   **`Jitterbit.GetVar`:** Usando a função `Jitterbit.GetVar`, o código exemplo `Jitterbit.GetVar("$server.URL")` retorna o valor *string* da variável global que se chama `server.URL`. Note que o cifrão `$` **_deve_** estar incluído dentro do nome da variável para que o valor global seja lido do sistema do Harmony.

#### Variáveis de Projeto

As variáveis de projeto são criadas inicialmente como componentes de projeto dentro do Cloud Studio. Uma vez que uma variável de projeto é criada, você pode definir valores para elas por meio do [Cloud Studio](https://login.jitterbit.com/), do [Management Console](https://login.jitterbit.com/) ou do [Citizen Integrator](https://login.jitterbit.com/). Saiba mais sobre a criação e a atualização de variáveis de projeto no artigo [Variáveis de Projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR).

No JavaScript dentro da Jitterbit, a sintaxe usada para recuperar o valor de uma variável de projeto depende se o nome da variável contém ou não um ponto.

-   **Nomes sem pontos:** O valor de uma variável de projeto que não contém pontos em seu nome pode ser recuperado com o uso de um cifrão `$`.

    -   **`$`:** Com o uso de um cifrão `$`, o código exemplo `$org_netsuite_auth_username` recupera o valor de uma variável de projeto chamada `org_netsuite_auth_username`.

-   **Nomes com pontos:** O valor de uma variável de projeto que contém pontos em seu nome pode ser recuperado apenas com a ajuda da função `Jitterbit.GetVar`.

    -   **`Jitterbit.GetVar`:** Usando a função `Jitterbit.GetVar`, o código exemplo `Jitterbit.GetVar("$server.url")` retorna o valor da variável de projeto que se chama `server.URL`. Repara que o cifrão `$` **_deve_** estar incluído dentro do nome da variável.

#### Variáveis Jitterbit

O sistema do Harmony define certas variáveis globais que estão sempre disponíveis ao longo de todo um projeto, conhecidas como variáveis Jitterbit (ou conhecidas como variáveis globais pré-definidas). Elas podem ser usadas para reunir informações globais como o nome do arquivo fonte atual ou o nome da operação atual. Saiba mais no artigo [Variáveis Jitterbit](https://success.jitterbit.com/display/CS/Jitterbit+Variables?showLanguage=pt_BR).

No JavaScript dentro da Jitterbit, as variáveis Jitterbit pré-definidas pelo Harmony estão disponíveis somente por meio da função `Jitterbit.GetVar`. Isto ocorre porque todas as variáveis Jitterbit pré-definidas pelo Harmony contêm pontos em seus nomes.

-   **`Jitterbit.GetVar`:** Usando a função `Jitterbit.GetVar`, o código exemplo `Jitterbit.GetVar("$jitterbit.operation.error")` recupera o valor da variável Jitterbit `jitterbit.operation.error`. Repare que o cifrão `$` **_deve_** estar incluído dentro do nome da variável.

### Endpoints

A aba **Endpoints** fornece uma lista dos *endpoints* do projeto que estão disponíveis para serem referenciados em um *script*:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/tab_endpoints.png" class="confluence-embedded-image confluence-external-resource" /></span>

Dentro de um *script*, você pode referenciar *endpoints* como argumento para as funções ao inserir o caminho de referência da conexão ou da atividade.

Para adicionar um caminho de referência de conexão ou de atividade a um *script* ([Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR) ou [JavaScript](https://success.jitterbit.com/display/CS/JavaScript?showLanguage=pt_BR)), use um dos seguintes métodos:

-   Arraste a conexão ou atividade da paleta para o *script* para inserir a referência apropriada.

-   Clique duas vezes sobre a conexão ou a atividade na paleta para inserir a referência apropriada no local do seu cursor dentro do *script*.

-   Comece a digitar o nome da conexão ou da atividade e depois aperte `Control+Space` para exibir uma lista das sugestões do autocompletar. Selecione uma conexão ou atividade para inserir a referência apropriada.

-   Digite manualmente a referência da conexão ou da atividade.

Os tipos de *endpoints* que podem ser usados dentro dos *scripts* dependem de haver ou não funções capazes de aceitar referências àquele tipo específico de conexão ou atividade como argumento. As referências a *endpoints* devem ser usadas em conjunto com tais funções para serem válidas no *script*.

As conexões e atividades que podem ser usadas no *script* aparecem dentro de categorias que listam o número de cada item disponível em cada categoria. Os nomes das atividades são precedidos por colchetes que contêm o tipo de interação com o recurso de dados que é específico àquele tipo de atividade (por exemplo, Read, Write, Query, Upsert, GET, POST, etc.). Para que apareçam aqui, as conexões e atividades precisam já estar configuradas dentro do projeto. Por exemplo, se houver uma única conexão HTTP configurada no projeto, com duas atividades configuradas usando tal conexão, elas apareceriam agrupadas conforme mostrado na imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/component-palette/endpoints_http.png" class="confluence-embedded-image confluence-external-resource" /></span>

As referências a conexões ficam contidas dentro das *tags* `<TAG>` e `</TAG>` e são construídas a partir do tipo de componente de projeto (`connection`), seguido por dois pontos (`:`), seguidos pelo tipo de conexão, seguido pelo nome da conexão, fornecido pelo usuário.

As referências a atividades são mais longas, já que a referência à conexão da qual elas são associadas também deve ser incluída no caminho. As referências a atividades ficam contidas dentro das *tags* `<TAG>` e `</TAG>` e são construídas a partir do tipo de componente de projeto (`activity`), seguido por dois pontos (`:`), seguidos pelo tipo de conexão, seguido pelo tipo de atividade, seguido pelo nome da atividade, fornecido pelo usuário.

Dependendo do tipo de conexão ou atividade específica conforme listado abaixo, você pode usar funções da aba **Functions** (Funções) que aceitam uma referência a conector como argumento. As funções descritas abaixo estão disponíveis para serem usadas com as conexões e atividades listadas.

<div class="table-wrap"><table class="relative-table wrapped confluenceTable" style="width: 100.0%;" resolved="">
<colgroup><col style="width: 18.6885%;"><col style="width: 41.8852%;"><col style="width: 39.2623%;"></colgroup>
<tbody>
<tr>
<td class="highlight-#f4f5f7 confluenceTd" data-highlight-colour="#f4f5f7"><strong title="">Categoria</strong></td>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Descrição</strong></td>
<td class="highlight-#f4f5f7 confluenceTd" colspan="1" data-highlight-colour="#f4f5f7"><strong title="">Uso de Componentes como Parâmetros de Funções</strong></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><strong title="">Database Endpoints</strong></td>
<td class="confluenceTd"><p title="">Esta categoria inclui toda conexão configurada <a href="/display/CS/Database?showLanguage=pt_BR">Database</a> (que podem ser usadas em <em>scripts</em>) e suas atividades associadas (que não podem ser usadas em <em>scripts</em> escritos em JavaScript).</p></td>
<td colspan="1" class="confluenceTd"><p title="">Conexões de banco de dados podem ser usadas com qualquer função listada no artigo <a href="/display/CS/JavaScript+Jitterbit+and+Common+Functions?showLanguage=pt_BR">Funções Comuns e da Jitterbit em JavaScript</a> que usam <code>databaseId</code> como parâmetro, incluindo:</p><ul title=""><li><code><a href="/display/CS/JavaScript+Jitterbit+and+Common+Functions?showLanguage=pt_BR#JavaScriptJitterbitandCommonFunctions-Jitterbit.DbExecute">Jitterbit.DbExecute</a></code></li><li><code><a href="/display/CS/JavaScript+Jitterbit+and+Common+Functions?showLanguage=pt_BR#JavaScriptJitterbitandCommonFunctions-Jitterbit.DbLookup">Jitterbit.DbLookup</a></code></li></ul></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><p title=""><strong>File Share Endpoints</strong></p><p title=""><strong>FTP Endpoints</strong></p><p title=""><strong>HTTP Endpoints</strong></p><p title=""><strong>Local Storage Endpoints</strong></p><p title=""><strong>Temporary Storage Endpoints</strong></p></td>
<td class="confluenceTd"><div class="content-wrapper"><p>Estas categorias incluem toda conexão configurada <a href="/display/CS/File+Share?showLanguage=pt_BR">File Share</a>,&nbsp;<a href="/display/CS/FTP?showLanguage=pt_BR">FTP</a>,&nbsp;<a href="/display/CS/HTTP?showLanguage=pt_BR">HTTP</a>,&nbsp;<a href="/display/CS/Local+Storage?showLanguage=pt_BR">Local Storage</a>, e&nbsp;<a href="/display/CS/Temporary+Storage?showLanguage=pt_BR">Temporary Storage</a> (que não podem ser usadas em <em>scripts</em>) e suas atividades associadas (que podem ser usadas em <em>scripts</em>).</p><div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info"><span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span><div class="confluence-information-macro-body"><p><strong>NOTA:</strong> Embora uma categoria <strong>API Endpoints</strong> esteja incluída, as conexões e atividades do tipo <a href="/display/CS/API?showLanguage=pt_BR">API</a> não podem ser usadas em <em>scripts</em>.</p></div></div></div></td>
<td colspan="1" class="confluenceTd"><div class="content-wrapper"><p>As atividades incluídas (menos as atividades de API) podem ser usadas com qualquer função listada no artigo <a href="/display/CS/JavaScript+Jitterbit+and+Common+Functions?showLanguage=pt_BR">Funções Comuns e da Jitterbit em JavaScript</a>&nbsp;que usam&nbsp;<code>sourceId</code>&nbsp;ou&nbsp;<code>targetId</code>&nbsp;como parâmetro, incluindo:</p><ul><li><code><a href="/display/CS/JavaScript+Jitterbit+and+Common+Functions?showLanguage=pt_BR#JavaScriptJitterbitandCommonFunctions-Jitterbit.ReadFile">Jitterbit.ReadFile</a></code></li><li><code><a href="/display/CS/JavaScript+Jitterbit+and+Common+Functions?showLanguage=pt_BR#JavaScriptJitterbitandCommonFunctions-Jitterbit.WriteFile">Jitterbit.WriteFile</a></code></li></ul><p><br></p></div></td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><strong title="">Salesforce Endpoints</strong></td>
<td class="confluenceTd">Esta categoria inclui toda conexão configurada da <a href="/display/CS/Salesforce?showLanguage=pt_BR">Salesforce</a>. Conexões da Salesforce não podem ser usadas em <em>scripts</em> escritos em JavaScript.</td>
<td colspan="1" class="confluenceTd">Não se aplica.</td>
</tr>
<tr>
<td colspan="1" class="confluenceTd"><strong title="">NetSuite Endpoints</strong></td>
<td class="confluenceTd">Esta categoria inclui toda conexão configurada da <a href="/display/CS/NetSuite+Connection?showLanguage=pt_BR">NetSuite</a>. Conexões da NetSuite não podem ser usadas em <em>scripts</em> escritos em JavaScript.</td>
<td colspan="1" class="confluenceTd">Não se aplica.</td>
</tr></tbody></table></div>


## Exemplos

Os seguintes exemplos de JavaScript são fornecidos para servir como referência.

### Funções de Arquivo em JavaScript

```
<javascript>
// Este script:
// *Gera alguns números aleatórios
// *Grava tais números num arquivo alvo
// *Depois, volta a lê-los
// *Grava a saída no Registro de Operações
// *********************************************

// Obter 200 números aleatórios entre 1 e 10000
var minhaString = gerarNumerosAleatorios(200, 1, 10000);

// Gravar os dados num arquivo
Jitterbit.WriteFile(“<TAG>activity:tempstorage/Temporary Storage Endpoint/tempstorage_write/tmpdata</TAG>”, minhaString);

// Voltar a ler os dados do arquivo
var dadosDoArquivo = Jitterbit.ReadFile(“<TAG>activity:tempstorage/Temporary Storage Endpoint/tempstorage_read/tmpdata</TAG>”);

// Gravar a saída no Registro de Operações
WriteToOperationLog(“Arquivo lido, saída: ” + dadosDoArquivo);

// Exibir os dados no resultado da aba test script do Studio
SetScriptResult(dadosDoArquivo);

///////////////

function gerarNumerosAleatorios(quantos, min, max) {
    var saida = “”;

    for (var i=0; i<quantos; i++) {
        saida = saida + gerarNumeroAleatorio(min, max) + “ \n”;
    }

    return saida;
}

function gerarNumeroAleatorio(min, max) {
    return Math.floor((Math.random() * max) + min);
}

/////////////////
</javascript>
```

### Funções Matemáticas em JavaScript

```
<javascript>
// Criar 200 números aleatórios
var $saida = gerarNumerosAleatorios(200);

WriteToOperationLog($saida);
SetScriptResult($saida);

///////////////

function gerarNumerosAleatorios(quantos) {
    var saida = “”;

    for (var i=0; i<quantos; i++) {
        saida = saida + Math.floor((Math.random() * 10000) + 1) + “ \n”;
    }

    return saida;
}

//////////////
</javascript>
```

### Laços em JavaScript

```
<javascript>
// Criar 100 números aleatórios

var $saida = “”;

for (var i=0; i<100; i++) {
    $saida = $saida + Math.floor((Math.random() *  10000) + 1) + “ \n”;
}

SetScriptResult($saida);
</javascript>
```

### Exemplo 1 de JSON em JavaScript

```
<javascript>
WriteToOperationLog(“\n\n Parsing JSON...”);

var jsonData = Jitterbit.ReadFile(“<TAG>activity:tempstorage/Temporary Storage Endpoint/tempstorage_read/JSON Data</TAG>”);
var $jsonObj = JSON.parse(jsonData);

WriteToOperationLog(“O valor de ‘status’ é: ” + $jsonObj.status);
WriteToOperationLog(“O valor de ‘operation’ é: ” + $jsonObj.operation);
WriteToOperationLog(“O valor de ‘serverUrl’ é: ” + $jsonObj.serverUrl);

var $firstOrg = $jsonObj.orgAttrs[0];

WriteToOperationLog(“O ID da primeira organização é: ” + $firstOrg.orgId);
WriteToOperationLog(“O Nome da primeira organização é: ” + $firstOrg.orgName);
</javascript>
```

### Exemplo 2 de JSON em JavaScript

```
<javascript>
WriteToOperationLog(“\n\n Parsing JSON...”);

var $jsonData = Jitterbit.ReadFile(“<TAG>activity:tempstorage/Temporary Storage Endpoint/tempstorage_read/JSON Data</TAG>”);
var $jsonObj = JSON.parse(jsonData);

WriteToOperationLog(“Status: ” + $jsonObj.status);
WriteToOperationLog(“Operation: ” + $jsonObj.operation);

var organizacoes = “”;
var precisaVirgula = false;

for (var i=0; i<$jsonObj.orgAttrs.length; i++) {
    if (precisaVirgula) organizacoes = organizacoes + “,”;
    organizacoes = organizacoes + $jsonObj.orgAttrs[i].orgId;
    precisaVirgula = true;
}

WriteToOperationLog(“IDs das Organizações: ” + organizacoes);

// Você pode modificar valores JSON existentes
// Toda mudança é refletida no sistema da Jitterbit como uma variável map
// Aqui vamos inserir um número aleatório como token de autenticação
var numeroAleatorio = Math.floor(Math.random() * 10000) + 1);
$jsonObj.authenticationToken = numeroAleatorio;
</javascript>
```

### Exemplo 3 de JSON em JavaScript

```
<javascript>
// Este script usa JSON Stringify
// para criar uma estrutura de valores de propriedade
// e daí envia as informações para uma API

var $API_Complexa = {
    “propriedades”: [
        {
            “propriedade”: “email”;
            “valor”: $email
        },
        {
            “propriedade”: “primeiroNome”;
            “valor”: $firstname
        },
        {
            “propriedade”: “sobrenome”;
            “valor”: $lastname
        },
        {
            “propriedade”: “website”;
            “valor”: $website
        },
        {
            “propriedade”: “telefone”;
            “valor”: $phone
        }
    ]
}

var $saidaJSON = JSON.Stringify($API_Complexa);
Jitterbit.WriteFile(“<TAG>activity:http/HTTP Endpoint/http_post/Example HTTP POST</TAG>”, $saidaJSON);
WriteToOperationLog($saidaJSON);
SetScriptResult($saidaJSON);

</javascript>
```
