[//]: # (Permissões, Colaboração e Salvamento no Cloud Studio)
[//]: # (This is a translation of Version 17, published on October 5, 2021.)

## Introdução

Esta página contém informações básicas sobre o trabalho com o Cloud Studio, incluindo qual nível de acesso é
concedido por diferentes permissões, como funcionam o processo de colaboração quando você está editando projetos ao
mesmo tempo que outros usuários e também o processo de salvamento.


## Permissões de Projeto

O acesso aos projetos é restrito baseado na combinação de permissões de papel organizacional e níveis de acesso
ambiental conforme definidos através do [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR)
(Console de Gerenciamento). As permissões de papel organizacional são dadas na página
[Organizações](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR), enquanto os níveis de acesso ambiental são definidos
na página [Ambientes](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR).

Um usuário deve ser membro de um papel organizacional com permissão do tipo *Read* (Ler) ou *Admin*
(Administrador\[a\]) para poder acessar o Cloud Studio. Tanto a permissão *Read* quanto a *Admin* oferecem os mesmos
privilégios dentro da aplicação Cloud Studio. Já que os projetos devem ser criados dentro de um ambiente, as áreas
do Cloud Studio que estes membros podem ver ou editar dependem dos níveis de acesso que aquele papel recebe no nível
ambiental.

### Matriz de Permissões e Níveis de Acesso para o Cloud Studio e Páginas Relacionadas

A tabela abaixo detalha a combinação de permissões de papel organizacional e níveis de acesso ambiental que são
necessárias para poder acessar, editar e fazer ações no Cloud Studio e páginas relacionadas. Note que as diferenças
concedidas pelas permissões *Read* e *Admin* são a possibilidade de acessar e editar outras páginas do Portal
Harmony e aplicações (veja [Permissões e Acesso ao Jitterbit
Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access?showLanguage=pt_BR)).

Além disso, o nível de acesso *View Logs* (Ver Registros) não provê acesso ao Cloud Studio. Em vez disso, dá acesso
aos registros de operação do Cloud Studio dentro do Management Console.

<table class="relative-table wrapped confluenceTable"
style="width: 80.2568%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 89%" />
</colgroup>
<tbody>
<tr class="odd">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Nível de Acesso Ambiental</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Permissão de Papel Organizacional
<em>Read</em> ou <em>Admin</em></strong></p></td>
</tr>
<tr class="even">
<td class="highlight-blue confluenceTd"
data-highlight-colour="blue"><strong>View Logs</strong> (<em>Ver Registros</em>)</td>
<td class="confluenceTd"><p>Acesso ao(à):</p>
<ul>
<li>Página <a
href="https://success.jitterbit.com/display/DOC/Activities?showLanguage=pt_BR">Atividades</a> do Console de Gerenciamento para ver os registros
das operações do Cloud Studio que foram implantadas e executadas dentro daquele ambiente.</li>
</ul></td>
</tr>
<tr class="odd">
<td class="highlight-blue confluenceTd"
data-highlight-colour="blue"><strong>Read</strong> (<em>Ler</em>)</td>
<td class="confluenceTd"><p>Acesso ao(à):</p>
<ul>
<li>Todas as áreas do Cloud Studio. Por exemplo:<br />
<ul>
<li>Ver a lista de projetos no índice de projetos.</li>
<li>Abrir projetos para ver dentro do <em>designer</em> de projetos.</li>
<li>Ver telas de configuração de componentes e projetos (por exemplo,
conexão/atividade, <en>transformation</em>, <em>script</em>).</li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td class="highlight-blue confluenceTd"
data-highlight-colour="blue"><strong>Execute</strong> (<em>Executar</em>)</td>
<td class="confluenceTd"><p>Habilidade de tomar as seguintes ações:</p>
<ul>
<li>Executar operações do Cloud Studio que já foram implantadas (veja
<a
href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution#OperationDeploymentandExecution-manually?showLanguage=pt_BR">Executando
Manualmente</a> em <a
href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR">Implantação
e Execução de Operações</a>).</li>
<li>Ações no Design Studio (veja <a
href="https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access?showLanguage=pt_BR">Permissões
e Acesso ao Jitterbit Harmony</a>).</li>
</ul>
<p>Acesso ao(à):</p>
<ul>
<li>Todas as áreas do Cloud Studio concedidas pelo nível de acesso <em>Read</em>
access level.</li>
</ul></td>
</tr>
<tr class="odd">
<td class="highlight-blue confluenceTd"
data-highlight-colour="blue"><strong>Write</strong> (<em>Escrever</em>)</td>
<td class="confluenceTd"><p><span>Acesso e habilidade de fazer
edições e realizar todas as ações do Cloud Studio. Por exemplo:</span></p>
<ul>
<li>Abrir projetos para ver e editar dentro do <em>designer</em> de projetos.</li>
<li>Ver e editar telas de configuração de componente e projeto.</li>
<li>Criar novos workflows.</li>
<li>Adicionar componentes de projeto.</li>
<li>Implantar e migrar projetos.</li>
</ul></td>
</tr>
</tbody>
</table>

### Resolução de Problemas

Usuários que têm apenas acesso *Read* (Ler) ou *Execute* (Executar) em um ambiente específico podem ver as mesmas
opções de realizar ações que estão disponíveis para os usuários com acesso *Write* (Escrever). No entanto, ao tentar
realizar uma ação assim, um erro acontece, com uma mensagem indicando que o usuário não tem permissão para realizar
aquela ação.

Se você receber uma mensagem de erro como uma das mostradas abaixo, entre em contato com um administrador da
organização Jitterbit Harmony para garantir que você é membro do papel organizacional adequado e que o seu papel
recebeu o nível de acesso apropriado no ambiente (veja [Permissões e Acesso ao Jitterbit
Harmony](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access?showLanguage=pt_BR)).

![](https://docs-source.jitterbit.com/cs/dialog/unable-to-import-project.png)

![](https://docs-source.jitterbit.com/cs/dialog/error-failed-to-authorize.png)


## <span id="CloudStudioPermissions,Collaboration,andSaving-collaboration" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Colaboração

Usuários que são membros de um papel com acesso *Write* (Escrever) em um ambiente podem editar projetos de
integração ao mesmo tempo que outros usuários - chamados colaboradores de projeto - assim como fazer edições em
diferentes partes de um projeto. O Cloud Studio sincroniza automaticamente workflows e componentes para múltiplos
usuários.

### Avatares de Usuário

Quando vários usuários estão com o mesmo projeto aberto no *designer* de projetos, os avatares dos outros usuários
são mostrados na [barra de ferramentas de projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR).

### Sincronização Automática

Se um workflow estiver sendo editado por outro usuário, essas mudanças são refletidas em tempo real no design
canvas. Você também pode fazer mudanças no workflow simultaneamente, com as suas mudanças sendo sempre refletidas em
tempo real para os outros usuários. Um registro de auditoria das mudanças feitas por todos os usuários está
disponível no [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR).

### Edições Simultâneas

Você pode editar componentes de projeto simultaneamente com outros usuários, com todas as edições sendo salvas e
sincronizadas em tempo real.

Nos raros casos em que o usuário A edita um componente antes de receber as últimas mudanças feitas pelo usuário B, a
edição do usuário A será rejeitada até que a sincronização esteja completa. Neste caso, uma mensagem de erro indica
que uma ação de edição do projeto conflitou com a de outro usuário. Atualize o componente para receber as mudanças
mais recentes.

### Implantação

Caso as edições de vários colaboradores do projeto ainda não tenham sido implantadas, todas as atualizações dos
usuários serão implantadas quando um único deles fizer uma implantação.


## <span id="CloudStudioPermissions,Collaboration,andSaving-save-changes" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Salvando

As mudanças que você fizer em um projeto são salvas ou automaticamente com o salvamento automático, ou salvas
manualmente com um botão de comando ou atalho de teclado em uma tela de configuração.

### Salvamento Automático

Ao editar um projeto ou componente de projeto, as suas mudanças são salvas automaticamente quando você faz uma
dessas ações:

-   Fechar um componente de projeto (*transformation*, *script*, etc.)

-   Fechar o projeto

-   Sair do Harmony Portal

Isso inclui quando o projeto ou componente é fechado porque a sessão do Harmony atingiu o limite de tempo ou porque
a pessoa navegou para outra página.

Além disso, algumas telas, como as telas de configuração de *[scripts](https://success.jitterbit.com/display/CS/Scripts?showLanguage=pt_BR)* e
*[transformations](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR)*, têm um componente de salvamento automático que
só se aplica enquanto aquela tela está aberta.

### Salvamento Manual

Muitas telas de configuração têm botões explícitos que podem ser clicados para salvar uma configuração de componente
individual. Estes botões podem ser rotulados de muitas formas. Por exemplo: **Save Changes** (Salvar Mudanças),
**Save & Exit** (Salvar e Sair), **Finish** (Concluir) ou **Finished** (Terminado).

Além disso, as telas de configuração de *script* e *transformation* suportam salvamento manual usando `Control+S`
(em Windows ou Linux) ou `Command+S` (macOS).

### *Status* de Salvamento

O *status* de salvamento em telas de salvamento automático é mostrado ao longo do topo de cada tela.

#### Design Canvas

O *status* de salvamento de um projeto é refletido dentro de cada workflow, bem na ponta esquerda do cabeçalho do
design canvas:

![](https://docs-source.jitterbit.com/cs/design-canvas/header.png)

#### Script

O *status* de salvamento do editor de *script* é exibido abaixo do nome do *script*:

![](https://docs-source.jitterbit.com/cs/script/header.png)

#### Transformation

O *status* de salvamento da tela de configuração de *transformation* é exibido à direita do nome da
*transformation*:

![](https://docs-source.jitterbit.com/cs/transformation/save-status_name_saved.png)

A presença de um asterisco vermelho ao lado da hora indica que o *transformation* possui mudanças não-salvas:

![](https://docs-source.jitterbit.com/cs/transformation/save-status_name_unsaved_annotated.png)
