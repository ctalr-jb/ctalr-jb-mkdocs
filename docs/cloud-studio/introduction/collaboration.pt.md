[//]: # (Permissões, Colaboração e Salvamento no Cloud Studio)
[//]: # (This is a translation of Version 22, published on March 10, 2022.)

## Introdução

Esta página contém informações básicas sobre o trabalho com o Cloud Studio, incluindo qual nível de acesso é
concedido por diferentes permissões, além de como funciona o processo de colaboração quando você está editando projetos ao
mesmo tempo que outros usuários, como ocorrem os salvamentos e as ações de refazer e desfazer.


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

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/dialog/unable-to-import-project.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/dialog/unable-to-import-project.png" /></span>

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/dialog/error-failed-to-authorize.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/dialog/error-failed-to-authorize.png" /></span>


## <span id="CloudStudioPermissions,Collaboration,andSaving-collaboration" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Colaboração

Usuários que são membros de um papel com acesso *Write* (Escrever) em um ambiente podem editar projetos de
integração ao mesmo tempo que outros usuários &mdash; chamados colaboradores de projeto &mdash; assim como fazer edições em
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

Se um conflito for detectado enquanto se edita um componente que salva automaticamente (veja o subtítulo <a href="https://success.jitterbit.com/display/CS/Cloud+Studio+Permissions%2C+Collaboration%2C+and+Saving#heading-SalvamentoAutom%C3%A1tico">Salvamento Automático</a> na seção <a href="https://success.jitterbit.com/display/CS/Cloud+Studio+Permissions%2C+Collaboration%2C+and+Saving#heading-Salvando">Salvando</a>, mais abaixo), o salvamento automático é temporariamente suspenso até que você atualize manualmente aquele componente. Isto dá uma oportunidade para você copiar o seu trabalho, caso queira colá-lo depois de atualizar.

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
só se aplica enquanto aquela tela está aberta. O salvamento automático é temporariamente suspenso se um conflito for detectado com outro(a) usuário(a) (veja o subtítulo <a href="https://success.jitterbit.com/display/CS/Cloud+Studio+Permissions%2C+Collaboration%2C+and+Saving#heading-Edi%C3%A7%C3%B5esSimult%C3%A2neas">Edições Simultâneas</a> na subseção <a href="https://success.jitterbit.com/display/CS/Cloud+Studio+Permissions%2C+Collaboration%2C+and+Saving#heading-Colabora%C3%A7%C3%A3o">Colaboração</a>, mais acima).

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

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/header.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/header.png" /></span>

#### Script

O *status* de salvamento do editor de *script* é exibido abaixo do nome do *script*:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/script/header.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/script/header.png" /></span>

#### Transformation

O *status* de salvamento da tela de configuração de *transformation* é exibido à direita do nome da
*transformation*:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/save-status_name_saved.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/save-status_name_saved.png" /></span>

A presença de um asterisco vermelho ao lado da hora indica que o *transformation* possui mudanças não-salvas:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/save-status_name_unsaved_annotated.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/save-status_name_unsaved_annotated.png" /></span>

## Desfazer e Refazer

Ao fazer o *design* de um projeto, você pode desfazer ou refazer as suas próprias ações enquanto estiver com o projeto aberto. Fechar o projeto ou fazer logout do Harmony Portal vai reiniciar as pilhas de desfazer/refazer.

As ações de desfazer e refazer estão disponíveis somente para o design de projeto; ações que interagem com o Harmony, como implantar um projeto, não podem ser desfeitas nem refeitas.

### Ações Básicas de Desfazer e Refazer

As ações básicas de desfazer e refazer que são fornecidas pelo seu navegador e seu sistema operacional são suportadas dentro das telas de configuração de componentes para as conexões, atividades, notificações de e-mail, *schemas* e *scripts*.

Os componentes que oferecem vários passos de configuração suportam as ações de desfazer e refazer somente dentro de cada etapa de configuração; quando se sai da tela atual, a pilha de desfazer/refazer é reiniciada. Para as ações básicas de desfazer e refazer, cada pilha de desfazer/refazer é separada, funcionando etapa por etapa.

Para as ações básicas de desfazer e refazer, use os atalhos de teclado comuns suportados pelo seu navegador e sistema operacional.

### Ações Avançadas de Desfazer e Refazer

O design canvas e os *transformations* suportam ações avançadas de desfazer e refazer. Com elas, as pilhas de desfazer/refazer persistem enquanto você navega e faz mudanças em outros componentes. O design canvas tem uma única pilha de desfazer/refazer que persiste enquanto o projeto está aberto. Cada *transformation* tem a sua própria pilha de desfazer/refazer que persiste enquanto o projeto está aberto. Ou seja, você pode editar outros componentes e então voltar para o design canvas ou um *transformation* editados desde que o projeto esteve aberto para desfazer ou refazer mudanças feitas neles.

As opções de desfazer e refazer estão acessíveis por meio da interface de usuário usando o <a href="https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-deploy-migrate-actions-menu">menu de ações do design canvas</a> ou a <a href="https://success.jitterbit.com/display/CS/Common+Mode+Elements?showLanguage=pt_BR#CommonModeElements-transformation-toolbar">barra de ferramentas de transformation</a> e também são suportadas usando os atalhos de teclado `Control+Z` e `Control+Y` (Windows ou Linux) ou `Command+Z` e `Command+Y` (macOS).