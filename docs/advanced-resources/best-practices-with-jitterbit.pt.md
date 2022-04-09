[//]: # (Melhores Práticas com a Jitterbit)

[//]: # (This is a translation of Version 46, published on February 16, 2022.)

## Introdução

Este documento tem a intenção de servir como guia para usar a Jitterbit. Ele não tem a intenção de ser totalmente abrangente nem de cobrir todos os cenários de integração. Em vez disso, ele almeja oferecer orientações para cenários de integração comuns e recomendar as melhores escolhas ao usar as muitas ferramentas disponíveis para um usuário Jitterbit.

É melhor ler esta página após já ter familiaridade com a Jitterbit: você passou pelo [Tutorial de Início Rápido](https://success.jitterbit.com/display/DOC/Jitterbit+Admin+Quick+Start+Tutorial), completou os cursos da [Jitterbit University](https://success.jitterbit.com/display/DOC/Getting+Training), e talvez até completou um projeto de integração sozinho. A essa altura, você já conhecerá os conceitos básicos e termos usados na Jitterbit, e entenderá o que a Jitterbit quer dizer com *projetos, operações, fontes, alvos, scripts* e *implantação*.

Este documento é um resumo dos recursos disponíveis por meio do [Jitterbit Harmony 9.9](https://success.jitterbit.com/display/DOC/9.9). Documentação mais abrangente está disponível nas seções abaixo:

-   [Agent](https://success.jitterbit.com/display/DOC/Agent)

-   [API Manager](https://success.jitterbit.com/display/DOC/API+Manager)

-   [Citizen Integrator](https://success.jitterbit.com/display/DOC/Citizen+Integrator)

-   [Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio)

-   [Management Console](https://success.jitterbit.com/display/DOC/Management+Console)

Desde a [primavera do hemisfério norte de 2019](https://success.jitterbit.com/display/DOC/Spring+2019), o [Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio), baseado na *web*, está disponível para uso em vez da aplicação de *design* de projetos para *desktop* [Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio). Até que este guia seja atualizado, muitas das melhores práticas descritas para o Design Studio podem também ser aplicadas ao Cloud Studio, embora a implementação possa ter pequenas diferenças. As diferenças principais são descritas no artigo [Visão Geral do Cloud Studio para Usuários do Design Studio](https://success.jitterbit.com/display/CS/Cloud+Studio+Overview+for+Design+Studio+Users).

Veja a seção [Recursos Adicionais](https://success.jitterbit.com/display/DOC/Best+Practices+with+Jitterbit#BestPracticeswithJitterbit-AdditionalResources) abaixo para encontrar *links* para vídeos e outros documentos que falam mais sobre as melhores práticas com a Jitterbit.


## Usando o Suporte, os CSMs e a Documentação

Todos os clientes têm acesso ao Jitterbit Support (Suporte Jitterbit) como parte de sua licença. Se você tiver dúvidas ou problemas, entre em contato e receba a assistência especializada deles. Consulte o artigo [Como Receber Ajuda](https://success.jitterbit.com/display/DOC/Getting+Support) para mais detalhes.

O seu ou a sua Gerente de Sucesso do Cliente (CSM, sigla em inglês) também pode ajudar você com as suas perguntas.

Este site, a [Jitterbit Success Central](https://success.jitterbit.com/), é constantemente atualizado e deve ser a sua primeira parada quando tiver perguntas.


## Atualizações Jitterbit

A Jitterbit lança novas atualizações do Harmony com melhorias ao Agent e ao Design Studio frequentemente. Até mesmo lançamentos pequenos contêm novos recursos além de consertos pontuais.

-   Se estiver usando um Cloud Agent, as atualizações são aplicadas automaticamente.

-   Se estiver usando um Private Agent, as atualizações precisam ser aplicadas manualmente por meio do instalador. No caso de um Private Agent, o processo é uma atualização.

-   No caso do Design Studio, o processo é uma nova instalação. Várias versões diferentes do Design Studio podem coexistir numa mesma máquina.

-   É recomendável se manter atualizado com os lançamentos, principalmente aqueles que incluem melhorias de recursos.

-   Se Private Agents forem usados, um ambiente de não-produção pode ser usado para avaliar ou testar um novo lançamento.


## Organização e *Design* de Projeto

### Reusabilidade

#### Reusabilidade de Projeto

Um cenário típico para reusar um projeto envolve o desenvolvimento de um projeto “padrão” com o uso extensivo de variáveis globais e — principalmente — variáveis de projeto. Itens configuráveis — tais como credenciais de *endpoint*, mapeamentos de campo opcionais, endereços de e-mail, nomes de arquivos — podem ser expostos como variáveis de projetos. O projeto “padrão” é implantado em vários ambientes e, usando o Management Console, as variáveis de projeto de cada ambiente são populadas.

#### Reuso de Fontes/Alvos

Embora fontes e alvos de arquivos sejam usados frequentemente em operações, um novo par fonte/alvo não precisa necessariamente ser construído para cada operação. Já que as fontes e alvos de arquivos aceitam variáveis globais para seus caminhos e nomes de arquivo, fontes e alvos de operações similares podem ser construídos só uma vez e transmitidos por meio de variáveis globais. Por exemplo, suponha que objetos “Fonte” e “Alvo” são criados, e no campo nome do arquivo está `[nomedoarquivo]`. A variável `$nomedoarquivo` pode ser definida em qualquer lugar antes do alvo ser escrito e será usada.

Isto se aplica a fontes e alvos dos tipos banco de dados, File Share, FTP Site, Local File e HTTP.

#### Reusabilidade de *Scripts*

*Scripts* individuais que fazem uma função específica, como realizar uma consulta num banco de dados ou fornecer um resultado a partir de uma série de argumentos são candidatos para reutilização, principalmente se forem usados em várias operações.

Por exemplo, se um *script* usa a função `DBLookup()` numa tabela de banco de dados, e esta for uma função que é usada ao longo de toda a integração, então um *script* (separado de uma operação) pode ser construído. Usando a função `ArgumentList()` ou variáveis globais simples, ele pode aceitar argumentos e retornar um resultado. Já que toda cadeia de operações é um escopo diferente, o mesmo *script* pode ser chamado de várias operações simultâneas com segurança.

<div class="confluence-information-macro confluence-information-macro-note conf-macro output-block" data-hasbody="true" data-macro-name="note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Se você armazenar os seus projetos em um *file share*, mudanças que são feitas a um projeto que são somente na interface do usuário (por exemplo, se você reposicionar objetos numa visualização) não são preservadas quando você reabre o projeto.

Como resultado, a Jitterbit não recomenda armazenar projetos em um *file share* porque:

-   Mudanças feitas na interface do usuário (posição de objetos) não são preservadas quando se salva um arquivo

-   A performance sofre: carregar e salvar um projeto pode ser um processo lento devido à falta de *caching*

-   Outros usuários na rede podem sobrescrever mudanças que estão sendo feitos a um projeto devido à falta de travas de arquivo

</div>

</div>

### Organizando as Operações num Projeto

O Design Studio provê pastas de operações, e organiza as operações alfabeticamente quando se reabre um projeto. Por usar um esquema de *numeração* ao nomear operações e pastas, o fluxo de integração é mais claro e mais fácil para se diagnosticar e resolver problemas.

Por exemplo: suponha que há dois fluxos de integração; um para o *Customer Master* e um segundo para o *Item Master*, cada um com duas operações. Duas pastas, “Customer Master” e “Item Master”, podem ser criadas no Design Studio. Na primeira pasta, as operações poderiam se chamar “CM001 Get Customer” e “CM002 Update Customer”. Na segunda pasta, as operações poderiam se chamar “IM001 Get Items” e “IM002 Update Items”:

<span class="confluence-embedded-file-wrapper"><img
src="https://success.jitterbit.com/download/attachments/60818003/Screen%20Shot%202018-08-30%20at%201.36.59%20PM.png?version=1&modificationDate=1535673785476&api=v2"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://success.jitterbit.com/download/attachments/60818003/Screen%20Shot%202018-08-30%20at%201.36.59%20PM.png?version=1&modificationDate=1535673785476&api=v2" /></span>

O registro de operações pode então mostrar facilmente os passos na cadeia de integração e também caso algum passo foi saltado. Por clicar com o botão direito em uma pasta no Design Studio, a lista de operações mostra apenas as operações de uma pasta. Uma estrutura de organização e de nomenclatura consistente torna mais fácil para que uma pessoa recém-chegada ao projeto entenda rapidamente o fluxo de operação básico.

#### Tratando as Condições de Corrida ao Usar Operações Assíncronas

Ao usar a função `RunOperation()` em seu modo assíncrono, as operações executam sem retornar o controle a quem as chamou. O uso de operações assíncronas pode levar a condições de corrida.

Por exemplo, se a operação A atualizar uma tabela de banco de dados e estiver acoplada à operação B que lê a mesma tabela (ambas são síncronas), nenhuma condição de corrida é encontrada. Mas se a operação A for chamada de forma assíncrona e seguida imediatamente pela operação B, pode ser que a B execute antes de a A ter terminado.

### Credenciais de *Endpoints*

Use um ID de sistema com permissões de administração como credenciais de *endpoint* em vez de usar um ID de nível de usuário. Os IDs de usuário normalmente expiram ou precisam ser desabilitados quando o usuário deixa a empresa.

Por usar variáveis de projeto (cujos valores podem ser escondidos) para o gerenciamento de credenciais, o Jitterbit Admin não precisa inserir credenciais de produção. Isso pode ser feito por um usuário por meio do Management Console. Esta abordagem pode ser usada para credenciais de e-mail, se necessário.

### Tratamento de APIs

A plataforma de APIs do Harmony deve ser usada em vez de *endpoints* HTTP. *Endpoints* HTTP eram uma forma de lidar com chamadas de baixo tráfego que entravam e requerem que portas de rede específicas estejam abertas, o que muitas empresas hoje consideram um sério risco de segurança.

A plataforma de APIs do Harmony é projetada para performance de alto volume, executa registros detalhados, implementa medidas de segurança comuns e tem uma interface de *design* de fácil uso que é parte do Harmony Portal. Nenhuma porta de rede para tratar tráfego que entra precisa estar configurada.

A API do Harmony deve ser usada para padrões de integração em tempo real/orientados a eventos. Por exemplo: o *Endpoint* A tem a capacidade de chamar uma API, como a Salesforce, usando mensagens que saem. A API do Harmony pode ser rapidamente implementada e acoplada a uma cadeia de operações.

A abordagem preferida para a resposta a um chamado é fazer isso o mais rápido possível. Se o *design* de integração for tal que as operações de seguimento demoram um tempo significativo para responder, existe o risco de se exceder o prazo, ou o risco de que outras chamadas que entram sobrecarreguem a habilidade do *endpoint* alvo de responder.

Se o *endpoint* fonte estiver fazendo muitos chamados por minuto, e a porta do *endpoint* alvo puder lidar apenas com um certo número de conexões, é possível que o *endpoint* alvo não consiga cuidar de todos os requisitos. Neste caso, responder de forma assíncrona pode ser a abordagem preferida. Isto é, a resposta é dada imediatamente, e o conjunto de dados do *endpoint* alvo é enviado via um chamado à API da fonte.


## Dados de Integração Persistentes

Existem muitos cenários nos quais poder armazenar dados “na nuvem” pode ser de ajuda. A Jitterbit oferece vários métodos: variáveis de projeto, funções de *caching* em nuvem e armazenamento temporário.

### Variáveis de Projeto

Variáveis de projeto são variáveis estáticas pré-inicializadas (similares às “constantes” de projeto) que podem ser editadas a partir do Design Studio ou do Management Console.

Um uso exemplo de variáveis de projeto é para credenciais de *endpoints*. Por usar variáveis de projeto, diferentes ambientes de *endpoints* (que normalmente têm credenciais diferentes) podem ser aplicados a diferentes ambientes Jitterbit e editados por meio do Management Console. Isto possibilita um processo de negócio em que um usuário com direitos de Management Console possa mudar credenciais sem requerer acesso ao Design Studio.

Um segundo exemplo é usar variáveis de projeto para segurar sinalizadores usados pela lógica de integração que podem customizar o comportamento da integração. Se um único projeto for desenvolvido mas for usado para *endpoints* diferentes, então uma variável de projeto booleana (como “Enviar_número_PO”) pode ser verificada pela lógica do *transformation* para obter o campo número PO. Se o valor da variável de projeto for falso, então o comando `UnMap()` poderia ser usado para “desligar” esse campo.

### Funções de *Caching* de Nuvem

As funções de *caching* de nuvem (`ReadCache()` e `WriteCache()`) são espaços para dados que podem ser atribuídos e que ficam disponíveis em vários projetos e ambientes. Um valor *cached* está visível para todas as operações sendo executadas no mesmo escopo até expirar, independentemente de como essa operação foi iniciada ou de em qual agente ela executa. Por fazer o *caching* de dados no Jitterbit Harmony, em vez de depender de armazenamentos de dados locais ou específicos a um agente, os dados podem ser compartilhados entre operações separadas e em vários projetos.

Por exemplo, suponha que as Cadeias de Operações A e B estejam num mesmo projeto. Essas cadeias são executadas separadamente. Com um único agente, o armazenamento temporário pode ser dividido pelas cadeias. Mas em um ambiente de vários agentes, o armazenamento temporário não pode ser usado, já que ele é local ao agente que executa a operação. Se o Agente 1 executar a Cadeia A e o Agente 2 executar a Cadeia B, então os dados gerados pela Cadeia A não estão disponíveis para a Cadeia B. Usar o *caching* de nuvem em vez do armazenamento temporário resolve este problema.

Usos adicionais do *caching* de nuvem incluem:

-   Dados podem ser divididos entre operações assíncronas dentro de um projeto.

-   Erros que são gerados em diferentes operações podem ser armazenados num *cache* comum. Por usar isso para acumular resultados de operação, alertas mais abrangentes podem ser construídos.

-   *Tokens* de *login* podem ser compartilhados entre várias operações.

-   As funções de *cache* de nuvem podem ser usadas para compartilhar dados entre projetos. Antes da introdução do *cache* de nuvem, todas as operações relacionadas tinham obrigatoriamente que estar dentro do mesmo projeto, o que conduzia a projetos muito grandes. Usando o *cache* de nuvem, projetos grandes podem ser esmiuçados em outros menores, o que permite acessos de permissões mais granulares, bem como divisão mais clara entre desenvolvimento e testes.

### Administrando Armazenamento Temporário

O armazenamento temporário é frequentemente usado em operações de integração. Isso é diferente dos Local Files ([fontes](https://success.jitterbit.com/display/DOC/Local+File+Source) ou [alvos](https://success.jitterbit.com/display/DOC/Local+File+Target)), que só podem ser usados em Private Agents. Mantenha essas diretrizes em mente, principalmente quando estiver dando os passos para usar um ambiente em *cluster*:

-   Torne o seu projeto “à prova de atualizações” e use o armazenamento temporário de tal forma que fazer a mudança de um único servidor para um ambiente de *cluster* não exija refatoramento.

-   O armazenamento temporário é escrito no diretório temporário do sistema operacional padrão no agente que está fazendo o trabalho. No caso de um único Private Agent, então é o diretório temporário padrão do servidor daquele Private Agent. Se você estiver usando mais de um Private Agent, então é o diretório temporário padrão do servidor do agente que estiver fazendo o trabalho. Se estiver usando um Cloud Agent (que sempre vêm em *clusters*), então é o diretório temporário padrão do servidor daquele Cloud Agent em particular.

-   Por padrão, o armazenamento temporário é deletado após 24 horas por um serviço de limpeza da Jitterbit. No caso de Cloud Agents, isto pode ser imediato.

-   Uma abordagem simples é construir um alvo, dar a ele um nome único, depois usar o “Copy to New Source” (“Copiar para uma Nova Fonte”) para criar uma fonte usando o mesmo nome de arquivo. Os alvos e as fontes são na verdade independentes, e dependem do uso do mesmo nome de arquivo para sincronizar suas leituras e escritas.

-   Em um ambiente de agentes em *cluster* (Private Agents ou Cloud Agents), enquanto as operações usando o armazenamento temporário estiverem conectadas (encadeadas), então todas as leituras e escritas no armazenamento temporário vão acontecer no mesmo servidor. Mas, se a cadeia de operação A escrever no armazenamento temporário “meuarquivo”, e a cadeia de operação B ler o armazenamento temporário “meuarquivo”, a ação de leitura pode ser inconsistente porque ela pode não ler no mesmo servidor que a cadeia A.

-   Para os alvos, o padrão é sobrescrever o arquivo. Isto pode ser mudado com a opção “Append to File” (“Acrescentar ao Arquivo”). Normalmente isto então requer que depois que a fonte tenha sido lida que o arquivo seja deletado ou arquivado. Uma maneira simples de fazer isso é escolhendo “Delete File” (“Deletar Arquivo”) ou “Rename File” (“Renomear Arquivo”) na fonte.

-   Palavras-chave de nomes de arquivos estão disponíveis que podem ser usadas ao criar um nome de arquivo.

-   Um arquivo num armazenamento temporário pode ser rapidamente lido construindo-se um *script* com a função `ReadFile()`, como por exemplo `ReadFile(“<TAG>Sources/test</TAG>”)`. Tenha em mente que isto só funciona confiavelmente se só houver um único Private Agent.

Veja o artigo [Variável Global contra Armazenamento Temporário](https://success.jitterbit.com/display/DOC/Global+Variable+versus+Temporary+Storage) para uma comparação destes dois tipos e as recomendações de quando cada um é apropriado.


## Uso de *Scripts*

### Quando Usar *Scripts*

Embora a Jitterbit forneça uma capacidade de *scripts* robusta, o uso de *scripts* deve acontecer *somente* quando isso for necessário. Se houver escolha entre usar *scripts* ou usar um método padrão, escolha o método padrão. Um “método padrão” é um método fornecido por meio da interface de usuário do Jitterbit Design Studio para cumprir uma tarefa.

Um exemplo seria organizar as execuções de operações. A interface de usuário do Jitterbit Design Studio permite que você crie “cadeias de operação” ligadas por caminhos de sucesso e de falha. Alternativamente, é possível construir operações individuais e daí conectá-las usando *scripts* e a função `RunOperation()`. A menos que haja requisitos técnicos que conduzam esta abordagem (tais como o uso de caminhos assíncronos ou opcionais), é preferível confiar no método da interface de usuário da Jitterbit para conectar diferentes operações.

Os *scripts* geralmente funcionam melhor em dois lugares: dentro do Formula Builder (Construtor de Fórmulas) em *transformations* e em *scripts* individuais. Se o mesmo código estiver sendo usado em mais de um *transformation*, cogite mover este código para um *script* individual e chamá-lo de dentro de cada *transformation* usando `RunScript()`.

### Convenção de Nomenclatura para Variáveis

A Jitterbit tem quatro tipos de variáveis:

-   variáveis locais

-   variáveis globais

-   variáveis de projeto

-   variáveis Jitterbit

Variáveis locais e globais são criadas nos *scripts* Jitterbit; as variáveis de projeto são definidas no Jitterbit Design Studio; variáveis Jitterbit são pré-definidas no sistema Jitterbit.

Como o escopo de uma variável local é limitado a um único *script*, uma convenção de nomenclatura para eles pode ser muito simples, como por exemplo usar apenas letras minúsculas ou uma palavra inicial, como `“retorno”` ou `“minhaVariavel”`.

Variáveis globais, como o escopo delas é maior (uma variável global está disponível para ser referenciada nas mesmas operações e *scripts* ou mais abaixo delas na mesma cadeia de operações), devem usar uma convenção de nomenclatura consistente para evitar reusos indesejados. Por exemplo, usar vários componentes para um nome de variável, separado por pontos finais, você poderia seguir um padrão tal como:

`primeiro.segundo.terceiro[.quarto]`

onde:

-   **Primeiro componente**: especificador de organização

-   **Segundo componente**: um tipo, como *id, error* (erro), *date* (data), *file* (arquivo), *token, timestamp* (hora), *timezone* (fuso horário), *flag* (bandeira), *email, guid, user* (usuário), *externalid* (id externo), *val* (valor) (para um valor miscelâneo), *arr* (vetor) ou um tipo de *endpoint* como *sfdc*

-   **Terceiro componente**: nome da variável

-   **Quarto componente**: nome da sub-variável opcional

Combinando estes componentes e supondo que o nome da sua organização seja “exemplo”, possíveis nomes de variáveis poderiam ser:

-   `$exemplo.arr.nomes`

-   `$exemplo.sfdc.sucesso.mensagem`

Como as variáveis de projeto são visíveis por meio do Management Console, e geralmente são usadas para configurar comportamento de integração, nomes mais amigáveis podem ser usados. Como um nome de variável de projeto não pode conter espaços, *underlines* podem ser usadas em vez disso. Por exemplo: `“Data_De_Inicio”` e `“Incluir_Montagens”`.

Sem importar qual convenção você escolha usar, nós recomendamos que você a codifique e documente para que todos os membros da equipe possam usá-la consistentemente em todos os projetos.

<div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**ALERTA**: Se você estiver planejando usar as suas variáveis globais Jitterbit em um *script* JavaScript, é importante usar *underlines* em vez de pontos:

-   `$exemplo_arr_nomes`

-   `$exemplo_sfdc_sucesso_mensagem`

</div>

</div>

## Ambientes e Implantações

A Jitterbit torna possíveis metodologias de ciclo de vida de desenvolvimento de *software* por meio do uso de ambientes e opções de implantação.

### Ambientes

No Jitterbit Harmony, o recurso do ambiente pode ser usado para preparar ambientes de produção e de não-produção.

Por exemplo, suponha que um ambiente “Dev” (de “desenvolvimento” em inglês) e “Prod” sejam preparados no Management Console e ambos sejam atribuídos ao Agent Group A. O Projeto 1 é desenvolvido sob o ambiente “Dev”. A Jitterbit fornece um recurso de “Migração” que vai copiar este projeto para o ambiente “Prod”, e depois disso as credenciais do *endpoint* são mudadas para as credenciais do *endpoint* “Prod”. Outras fontes e alvos também são mudados. Depois disso, quaisquer migrações de “Dev” para “Prod” excluem os *endpoints*, as fontes e os alvos a menos que sejam novos.

### Opções de Gerenciamento de Implantação

Há várias opções para implantar projetos.

-   **Implantação Completa**: Selecionar **Actions \> Deploy \> Everything** (Ações \> Implantar \> Tudo) pega o projeto inteiro e sobrescreve o projeto na nuvem.

-   **_Backup_ do Projeto**: Ao escolher **Actions \> Deploy \> Everything**, existe uma opção que diz “Also store a backup in the Cloud”, em português, “Também armazenar um *backup* na Nuvem”. Antes de fazer grandes mudanças em um projeto, selecione esta opção para ter um ponto de restauração salvo no Harmony.

-   **Todos os Itens Novos e Modificados**: Esta opção está disponível em **Actions \> Deploy \> Advanced Options** (Ações \> Implantar \> Opções Avançadas). Como o Design Studio rastreia itens “sujos”, isto implanta as mudanças bem como as dependências.

-   Um novo recurso é desabilitar a caixa de diálogo do progresso durante uma implantação (veja **Preferences \> Deploy**, ou seja, Preferências \> Implantação), o que permite que as implantações de itens individuais ocorram no fundo.

### Avisos de Versão

Ao implantar mudanças em um projeto, caso uma versão mais nova de um projeto tenha sido implantada, um aviso vai aparecer indicando que uma versão mais nova existe e identificando quem a implantou. O Administrador Jitterbit tem a opção de sobrescrever o projeto. Em geral, em um ambiente com vários desenvolvedores, baixar o projeto atual da nuvem antes de fazer qualquer mudança é preferível.


## Testes, Diagnóstico e Resolução de Problemas, e Registros

### Usando Recursos de Teste para Desenvolvimento Rápido de Integração

A Jitterbit pode tornar possível o desenvolvimento rápido de integração e os testes unitários deixando visíveis os dados de integração durante o tempo de *design*. A vantagem óbvia é possibilitar um processo de desenvolvimento iterativo mostrando os dados antes e depois das transformações dos campos, em vez de construir a operação inteira, executá-la e depois inspecionar a saída. Isto é feito principalmente através da ferramenta Transformations, principalmente usando os recursos “Test Transformation” (ou seja, “Testar o *Transformation*”) e “Run Operation” (“Executar Operação”).

Se os objetos a serem integrados forem conhecidos, um desenvolvedor experiente pode desenvolver uma integração rapidamente usando o Assistente de Transformação e seu *kit* de ferramentas. Por exemplo, faça uma conexão a um banco de dados e, usando o Assistente de Transformação, construa a operação e o *transformation*. Daí, execute um “Run Operation” com o *transformation* aberto. Os dados serão exibidos na tela do *transformation* e os registros podem ser consultados. Isso vai mostrar instantaneamente os dados exatos que a Jitterbit vai receber quando a operação for executada.

Se um campo exigir um *transformation*, clique duas vezes no campo para abrir o Formula Builder (Construtor de Fórmulas) e construa o *script* exigido. Por usar o recurso “Test” no Formula Builder, a saída vai usar os dados do *transformation* e mostrar a saída exata que será gerada durante o tempo de execução.

Se a fonte não estiver disponível, mas os dados fonte estiverem disponíveis num arquivo (CSV, XML, JSON), o arquivo pode ser importado na ferramenta Transformations usando os recursos “Load Sample Source Data” (isto é, “Carregar Dados Fonte de Amostra”) e “Test the Transformation” (“Testar o *Transformation*”).

### Habilitar o Diagnóstico e Resolução de Erros de Integração

Um conceito chave para uma arquitetura de integração saudável é reconhecer que haverá perguntas feitas pelo negócio concernentes à exatidão do trabalho de integração, principalmente quando aparecerem discrepâncias nos dados do *endpoint*. A integração pode ou não ser a culpada. É obrigação da integração fornecer um alto grau de transparência para ajudar a resolver dúvidas sobre a exatidão dos dados.

Por exemplo, se os dados num *endpoint* alvo aparentarem estar incorretos, então tipicamente o apoio da integração é chamado para fornecer detalhes no que diz respeito a ações de integração, como horários, fontes, lógica de transformação, mensagens de sucesso ou falha, etc. O processo de diagnóstico e resolução de erros será beneficiado por tornar esta informação disponível como uma parte padrão da arquitetura de integração.

Na Jitterbit, isto é suportado por meio dos recursos de registros e de alertas.

### Registros

O registro da operação Jitterbit vai capturar os dados chave por padrão, como os horários de execução da operação e mensagens de sucesso, falha ou cancelamento. Se houver falhas e o *endpoint* retornar informações sobre elas, o registro também as capturará.

Ao desenvolver uma integração, use a função `WriteToOperationLog()` nos mapeamentos e nos *scripts* para capturar dados e passos chave no processo. Isto costuma ser tão simples quanto: `WriteToOperationLog(“O id é: “+sourcefieldid)`.

Se capturar a saída inteira de um *transformation* for desejado, isto pode ser feito construindo uma operação que lê a fonte, executa o *transformation* e escreve num arquivo temporário. Um *script* de pós-operação pode ler o arquivo e escrevê-lo no registro de operação: `WriteToOperationLog(ReadFile(<tempfile>))`. Então a operação “real” pode ser executada.

Registros podem ser visualizados ou no Design Studio ou no Management Console. A vantagem do Management Console é que o pessoal do suporte pode acessá-lo por meio do navegador sem precisar de um cliente Design Studio em seus *desktops*.

Os dados nos registros podem ser achados por buscas, o que permite o cenário em que a *string* exata envolvida no diagnóstico e resolução do erro é um valor conhecido e é registrada.

Frequentemente, as APIs têm uma mensagem de sucesso ou não-sucesso que é bastante informativa. Dê o passo adicional de capturar essa informação no registro.

Registros de operação, incluindo mensagens de registros detalhadas tanto dos Cloud Agents quanto dos Private Agents, são retidas por 30 dias pelo Jitterbit Harmony.

### Alertas

Frequentemente os resultados de integração não apenas precisam ser registrados, mas precisam também ser escalados. A Jitterbit oferece integração por e-mail, que pode ser facilmente anexada a operações e a caminhos de sucesso/falha ou chamados de *scripts*.

Para informações adicionais, consulte [Como Preparar Alertas, Registros e Tratamento de Erros](https://success.jitterbit.com/display/DOC/Setting+Up+Alerting%2C+Logging%2C+and+Error+Handling).


## Recursos Adicionais

Estas seções e páginas na documentação têm a ver com as melhores práticas e serão de interesse.

### Tech Talks

Os Jitterbit Tech Talks são apresentações de vídeo que abrangem áreas de interesse para usuários de todos os níveis:

-   [Tech Talks de Melhores Práticas do Harmony com Dicas & Truques](https://success.jitterbit.com/pages/viewpage.action?pageId=81071482)<br/>
    Um Tech Talk direcionado a clientes, usuários de amostras e parceiros em busca das melhores práticas para a plataforma do Harmony.

-   [Tech Talk de APIs](https://success.jitterbit.com/display/DOC/APIs+Tech+Talk)<br/>
    As melhores práticas em torno da criação e implementação de APIs usando o API Manager da Jitterbit e como documentá-las usando os padrões OpenAPI (antes chamados de Swagger).

-   [Tech Talk de Ambientes](https://success.jitterbit.com/display/DOC/Environments+Tech+Talk)<br/>
    As melhores práticas ao se trabalhar com ambientes na Jitterbit: todo processo desde a criação de ambientes até a migração de projetos.

-   [Tech Talk de Melhores Práticas de Tratamento de Erros](https://success.jitterbit.com/display/DOC/Error+Handling+Best+Practices+Tech+Talk)<br/>
    Desenvolver um método de tratamento de erros robusto é uma parte crítica do seu projeto de integração que pode tomar até 25% do tempo do *design*. Este Tech Talk cobre as cinco melhores práticas de tratamento de erros.

-   [Tech Talk de Melhores Práticas com Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents+Best+Practices+Tech+Talk)<br/>
    Um Tech Talk cobrindo Private Agents *versus* Cloud Agents, recomendações de *hardware* para Private Agents, agrupamento de agentes, opções de sistema operacional, e melhores práticas de agentes que podem ajudar você a extrair o máxima das suas integrações Jitterbit.

-   [Tech Talk de Melhores Práticas de Organização de Projeto](https://success.jitterbit.com/display/DOC/Project+Organization+Best+Practices+Tech+Talk)<br/>
    As melhores práticas em torno da organização dos seus projetos.

Vídeos adicionais estão disponíveis na [Biblioteca de Vídeos Jitterbit](https://success.jitterbit.com/display/DOC/Video+Library).

### Documentação

A documentação da Jitterbit tem melhores práticas inclusas com as nossas páginas sobre o uso da Jitterbit:

#### Segurança

-   [*Whitepaper* da Segurança e Arquitetura Jitterbit](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper)<br/>
    As melhores práticas de segurança usadas na Jitterbit e no Jitterbit Harmony.

#### Metodologia de Projeto de Integração

-   [Metodologia de Projeto de Integração](https://success.jitterbit.com/display/DOC/Integration+Project+Methodology)<br/>
    Este documento aborda os itens chave que um Gerente de Projeto em um projeto do Jitterbit Harmony deve saber. Ele mostra como organizar a sua equipe, como reunir e validar requisitos de forma clara e concisa, e como usar bem os pontos fortes do Jitterbit Harmony para entregar um projeto de sucesso.

#### Padrões e Exemplos de *Design*

-   [Melhores Práticas para SAP](https://success.jitterbit.com/display/DOC/Best+Practices+for+SAP)<br/>
    Problemas e considerações que podem surgir ao integrar de e para instâncias SAP, principalmente ao se criar uma integração bidirecional.

-   [Biblioteca de Padrões de *Design*](https://success.jitterbit.com/display/DOC/Design+Pattern+Library)<br/>
    Problemas de integração comuns encontrados pelos nossos clientes que podem ser resolvidos usando nosso *software*.

-   [Biblioteca Jitterpak](https://success.jitterbit.com/display/DOC/Jitterpak+Library)<br/>
    Projetos exemplos para ajudar você a começar.

#### Criando Projetos

-   [Melhores Práticas para SAP](https://success.jitterbit.com/display/DOC/Best+Practices+for+SAP)<br/>
    Problemas e considerações que podem surgir ao integrar de e para instâncias SAP, principalmente ao se criar uma integração bidirecional.

-   [Capturando Mudanças de Dados com Mudanças de Tabela ou Arquivo](https://success.jitterbit.com/display/DOC/Capturing+Data+Changes+with+Table+or+File+Changes)<br/>
    Melhores práticas para seguir ao capturar mudanças de dados.

-   [Criando uma Agenda](https://success.jitterbit.com/display/DOC/Schedules)<br/>
    As melhores práticas para seguir ao criar e executar uma agenda.

-   [Conectando o Banco de Dados Alvo ao MySQL](https://success.jitterbit.com/display/DOC/Database+Target+Connecting+to+MySQL)<br/>
    As melhores práticas para se conectar com um banco de dados MySQL.

-   [Como Preparar Alertas, Registros e Tratamento de Erros](https://success.jitterbit.com/display/DOC/Setting+Up+Alerting%2C+Logging%2C+and+Error+Handling)<br/>
    As melhores práticas para como alertar os usuários sobre problemas de integração.

#### Registros

-   [Atividades](https://success.jitterbit.com/display/DOC/Activities)

-   [Limpando Espaço no *Drive*](https://success.jitterbit.com/display/DOC/Cleaning+Up+Drive+Space)

-   [Registro do *Debug* de Operações](https://success.jitterbit.com/display/DOC/Operation+Debug+Logging)

-   [Localizações dos Arquivos de Registros](https://success.jitterbit.com/display/DOC/Log+File+Locations)

-   [Como Preparar Alertas, Registros e Tratamento de Erros](https://success.jitterbit.com/display/DOC/Setting+Up+Alerting%2C+Logging%2C+and+Error+Handling)

#### Gerenciando Projetos

-   [Criando Novos Protótipos](https://developer.jitterbit.com/citizen-recipes/creating-new-recipes/)<br/>
    Melhores práticas para seguir ao criar Jitterpaks para usar com os protótipos do Citizen Integrator para o Design Studio.

-   [Metodologia de Projeto de Integração](https://success.jitterbit.com/display/DOC/Integration+Project+Methodology)<br/>
    Este documento aborda os itens chave que um Gerente de Projeto de um projeto do Jitterbit Harmony deve saber. Ele mostra como organizar a sua equipe, como reunir e validar requisitos de forma clara e concisa, e como usar bem os pontos fortes do Jitterbit Harmony para entregar um projeto de sucesso.

-   [Restaurando a Partir de um *Backup* na Nuvem](https://success.jitterbit.com/display/DOC/Restoring+from+Cloud+Backup)<br/>
    As melhores práticas em torno do uso de *backups* e da restauração de projetos.

-   [Como Preparar um Projeto de Colaboração em Equipe](https://success.jitterbit.com/display/DOC/Setting+Up+a+Team+Collaboration+Project)<br/>
    As melhores práticas para suportar vários desenvolvedores trabalhando no mesmo projeto.

#### Private Agents

-   [Requisitos de Sistema para Private Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents)<br/>
    As melhores práticas ao criar, instalar e configurar um Private Agent.

-   [Alta Disponibilidade e Balanceamento de Cargas de Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing)<br/>
    Recomendações que devem ser levadas em consideração antes da instalação de Private Agent(s) para permitir alta disponibilidade (ativo/ativo) e balanceamento de carga.

#### Usando APIs

-   [Roteando Erros SOAP para uma Operação ou um E-mail](https://success.jitterbit.com/display/DOC/Routing+SOAP+Faults+to+an+Operation+or+Email)<br/>
    As melhores práticas ao chamar uma API SOAP dentro de uma operação de serviço *web*.

-   [Configurando Mensagens de Saída com a API do Harmony](https://success.jitterbit.com/display/DOC/Configuring+Outbound+Messages+with+Harmony+API)<br/>
    As abordagens recomendadas para configurar mensagens de saída na Jitterbit.
