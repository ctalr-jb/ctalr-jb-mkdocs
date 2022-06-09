[//]: # (Configurando uma Aplicação Lançada)
[//]: # (This is a translation of Version 1, published on April 15, 2022.)


## Introdução

O processo pós-lançamento abrange as operações que precisam ser feitas sobre o *tenant* depois que a aplicação criada é lançada para a produção. Estas operações são realizadas pelo(a) administrador(a) do *tenant*. A esta altura, a criação de usuários de sistema e seus perfis, a configuração de visualizações e painéis e a criação de *templates* a serem usados no sistema já estão completas.


## Criando Perfis

Antes de qualquer usuário ser adicionado ao sistema, é preciso criar **Perfis** primeiro. Os perfis, em geral, especificam os direitos de acesso de seus usuários aos recursos do sistema. Desta forma, o usuário pode realizar transações e ver os registros dentro dos limites da autoridade de seu perfil enquanto usa o sistema. O processo de criação de perfis é descrito no artigo [Perfis](https://success.jitterbit.com/display/APP/Profiles?showLanguage=pt_BR).


## Criando Funcionários

O App Builder permite a criação de aplicações empresariais. Tais aplicações, em geral, interagem com informações de funcionários. Os nomes, endereços de e-mail e departamentos, etc. podem ser usados de várias formas pelo sistema. Então é importante ter informações de funcionários atualizadas dentro da aplicação criada.

Partes destes funcionários (ou todos eles) podem também ser *usuários* ativos da aplicação. Estes funcionários são chamados de funcionários *ativos*, o que lhes dá direitos de *login* na aplicação.

Os funcionários também têm informações *gerenciais* — que coletivamente permitem que a aplicação entenda a hierarquia organizacional. O controle de acesso aos perfis baseado em papéis depende dessa árvore organizacional para determinar quais usuários têm acesso a quais recursos no sistema.

Funcionários podem ser adicionados ao sistema de três formas diferentes:

-   Através da integração de dados de um sistema de RH usando o Jitterbit Harmony

-   Importação do Microsoft Excel

-   Manualmente

No processo de criação de usuários, a lista de usuários é transferida primeiro para o módulo **Organizational Changes** (Mudanças Organizacionais). Depois que tal transferência está completa, o processo **Start Organizational Changes** (Começar Mudanças Organizacionais) é chamado. Este processo garante que os registros de funcionários sejam criados em acordância com a árvore organizacional dos usuários no módulo **Employees** (Funcionários).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Depois deste passo, usuários que queiram fazer *login* no sistema devem ser selecionados como **Active User** (Usuário Ativo) no módulo **Employees** (Funcionários) e a atribuição de perfil deve ser realizada. Depois deste processo, os usuários podem fazer *login* no sistema com o e-mail de acesso enviado aos usuários.

</div>

</div>

### Criando Funcionários com um Projeto de Integração

Os usuários podem ser transferidos para a aplicação criada a partir de diferentes sistemas usando um projeto de integração do Harmony.

Por meio de um projeto de integração do Harmony, os funcionários podem ser transferidos para o módulo **Organizational Changes** (Mudanças Organizacionais) dentro dos confins de certas regras. Depois que a transferência é completada com sucesso, o processo **Start Organizational Changes** (Começar Mudanças Organizacionais) é acionado por integração. Com tal processo concluído, registros de funcionário são criados no módulo **Employees** (Funcionários) em acordância com a árvore organizacional.

### Criando Funcionários com Importações do Microsoft Excel

Funcionários podem ser transferidos para a aplicação criada por meio de uma importação do Microsoft Excel. Para ver mais instruções sobre como importar um arquivo Excel preparado, veja o artigo [Histórico de Importações](https://success.jitterbit.com/display/APP/Import+History?showLanguage=pt_BR).

Ao preparar o arquivo Excel para a importação, algumas informações que especificam a árvore organizacional de funcionários precisam ser definidas. Explicações sobre tais informações são dadas na tabela abaixo. Depois que o arquivo Excel está preparado, ele é importado para o módulo **Organizational Changes** (Mudanças Organizacionais). Depois da importação, as transferências necessárias são feitas para o módulo **Employees** (Funcionários) por meio das informações importadas ao se clicar no botão **Start Organizational Changes** (Começar Mudanças Organizacionais) na tela da lista.

<table class="relative-table confluenceTable">
<colgroup>
<col style="width: 25%" />
<col style="width: 20%" />
<col style="width: 16%" />
<col style="width: 37%" />
</colgroup>
<tbody>
<tr class="header header">
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Nome do Campo</strong></td>
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Tipo do Campo</strong></td>
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Validação</strong></td>
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Descrição</strong></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><p><strong>Employee ID</strong></p>
<p><em>ID do(a) Funcionário(a)</em></p></td>
<td class="confluenceTd">Número</td>
<td class="confluenceTd">Exigido</td>
<td class="confluenceTd">O ID único atribuído ao(à) funcionário(a) a ser transferido(a). Pode ser um ID de sistema diferente ou um valor como um número de registro.</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><p><strong>First Name</strong></p>
<p><em>Primeiro Nome</em></p></td>
<td class="confluenceTd">Texto</td>
<td class="confluenceTd">Exigido</td>
<td class="confluenceTd">O primeiro nome do(a) funcionário(a) a ser transferido(a).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><p><strong>Last Name</strong></p>
<p><em>Sobrenome</em></p></td>
<td class="confluenceTd">Texto</td>
<td class="confluenceTd">Exigido</td>
<td class="confluenceTd">O sobrenome do(a) funcionário(a) a ser transferido(a).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><strong>Email</strong></td>
<td class="confluenceTd">E-mail</td>
<td class="confluenceTd">Exigido</td>
<td class="confluenceTd">O endereço de e-mail do(a) funcionário(a) a ser transferido(a). Ao mesmo tempo, quando o método de identidade padrão é usado, este torna-se o nome de usuário para acessar o sistema.</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><p><strong>Manager ID</strong></p>
<p><em>ID do(a) Gerente</em></p></td>
<td class="confluenceTd">Número</td>
<td class="confluenceTd">Exigido</td>
<td class="confluenceTd">O ID de funcionário do(a) gerente atribuído(a) àquele(a) funcionário(a).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><p><strong>Execution Order</strong></p>
<p><em>Ordem da Execução</em></p></td>
<td class="confluenceTd">Número</td>
<td class="confluenceTd">Exigido</td>
<td class="confluenceTd">A ordem da organização entre os funcionários no arquivo Excel a ser importado. Depois que o(a) funcionário(a) no topo da organização na lista é definido(a) como número 1, os funcionários conectados a ele(a) precisam ser definidos como 2, 3, etc., respectivamente. A ordem na qual os usuários são processados dentro do processo <strong>Start Organizational Changes</strong> (Começar Mudanças Organizacionais) depende desta informação.</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><strong>Status</strong></td>
<td class="confluenceTd">Dropdown</td>
<td class="confluenceTd">Exigido</td>
<td class="confluenceTd">O <em>status</em> do processamento dos registros transferidos para o módulo <strong>Organizational Changes</strong> (Mudanças Organizacionais). Novas transferências são marcadas como <strong>New</strong> (Nova) por padrão. Registros que foram levados ao processo <strong>Start Organizational Changes</strong> (Começar Mudanças Organizacionais) e cujo processamento já foi completado são atualizados para <strong>Updated</strong> (Atualizado). Em caso de erro durante a transferência, o <em>status</em> é atualizado para <strong>Error</strong> (Erro).</td>
</tr>
</tbody>
</table>

### Criando Funcionários Manualmente

Os funcionários podem ser adicionados manualmente um por um além das opções acima.


## Criando Visualizações

Depois que a aplicação é lançada, as visualizações criadas no modo de pré-visualização do App Builder são transferidas para a aplicação. Além disso, novas visualizações e painéis podem ser criados opcionalmente dentro da aplicação lançada. O processo de criação de visualizações é descrito no artigo [Visualizações](https://success.jitterbit.com/display/APP/Views?showLanguage=pt_BR).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: As visualizações criadas no modo de pré-visualização do App Builder podem ser atualizadas pelos usuários depois de serem importadas na aplicação lançada. No entanto, uma nova atualização da mesma visualização no modo de pré-visualização vai cancelar a atualização feita pelo usuário na mesma visualização quando o lançamento for recebido.

</div>

</div>


## Criando Painéis

Quando a aplicação é lançada, o painel padrão criado no modo de pré-visualização do App Builder é transferido para a aplicação lançada. Além disso, uma nova exibição de painel pode ser necessária para cada perfil criado no sistema. A essa altura, você pode criar um novo painel e associá-lo com o perfil que você quer que ele veja. O processo de criação de painéis é descrito no artigo [Painéis](https://success.jitterbit.com/display/APP/Dashboards?showLanguage=pt_BR).


## Criando *Templates*

Depois que a aplicação é lançada, os *templates* de Adobe PDF, Microsoft Word, e-mail e planilhas que você está planejando usar na aplicação devem estar preparados. Estes conteúdos podem ser definidos na tela que abre quando o módulo **Templates** no menu esquerdo é clicado. As etapas para a criação de *templates* são descritas no artigo [Templates](https://success.jitterbit.com/display/APP/Templates?showLanguage=pt_BR).


## Processo de Importação de Dados

No período em que a aplicação está pronta para uso, pode haver a necessidade de transferir dados de vários sistemas para muitos módulos na aplicação. Projetos de integração do Jitterbit Harmony podem ser usados para a transferência contínua de dados. Além disso, o método de importação do Microsoft Excel pode ser uma boa solução para dados que precisam ser transferidos uma vez. Para transferir dados para a aplicação com uma importação do Excel, veja o artigo [Histórico de Importações](https://success.jitterbit.com/display/APP/Import+History?showLanguage=pt_BR).
