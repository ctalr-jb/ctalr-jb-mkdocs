[//]: # (Registros de Operações)
[//]: # (This is a translation of Version 43, published on January 28, 2022.)


## Introdução

Quando uma operação é [executada](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR), um registro de operação é gerado. Um registro de operação contém informações sobre onde e quando uma operação foi executada, o *status* da operação, o número de registros fonte e alvo que foram processados, bem como mensagens de registro. Se tais mensagens serão exibidas ou não depende de duas coisas: os níveis de permissão e de acesso, e se o registro em nuvem está habilitado. Quando o registro de depuração de operações estiver habilitado para uma operação individual sendo executada num Private Agent 10.48 ou posterior, cada registro de operação contém também dados de entrada e saída da operação.

Registros de operação, incluindo mensagens detalhadas tanto dos Cloud Agents quanto dos Private Agents, são retidos por 30 dias pelo Jitterbit Harmony. Os dados de entrada e saída dentro dos registros de operação dos Private Agents são retidos por 7 dias pelo Jitterbit Harmony.

Os registros de operação também podem ser visualizados na página [Atividades](https://success.jitterbit.com/display/DOC/Activities?showLanguage=pt_BR) do Management Console.


## Acessando Registros de Operação

Os registros de operação podem ser acessados no Cloud Studio no nível de projeto, de workflow ou de operação. Dependendo de onde eles são acessados, a tela de registros de operação inclui registros de operações que foram executadas em um projeto, em um workflow em particular ou em uma operação em particular, respectivamente. Se as operações estiverem conectadas por meio de [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR), os registros das operações mais abaixo na cadeia também são incluídos.

### Por Projeto

A opção **View Logs** (Visualizar Registros) de um projeto, que mostra os registros das operações que foram executadas dentro dele, pode ser acessada nos seguintes locais:

- O índice de projetos (veja [Visualização de Cartões](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR#ProjectIndex-card-view) ou [Visualização de Lista](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR#ProjectIndex-list-view) em [Índice de Projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR)).

- A barra de ferramentas de projeto (veja [Menu de Ações de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR#ProjectToolbar-project-actions-menu) em [Barra de Ferramentas de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR)).

### Por Workflow

A opção **View Logs** (Visualizar Registros) de um workflow, que mostra os registros de operações que foram executadas dentro de um workflow em particular, pode ser acessada a partir da aba **Workflows** do painel de projeto (veja [Menu de Ações de Workflow](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-workflow-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

### Por Operação

A opção **View Logs** (Visualizar Registros) de uma operação é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Além disso, depois de executar uma operação manualmente, você pode clicar no *status* da operação no design canvas para exibir os registros (veja [*Status* da Operação](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR#OperationDeploymentandExecution-operation-status) em [Implantação e Execução de Operações](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR)).


## Visualizando os Registros de Operação

A tela de registros de operação exibe uma tabela de operações que foram implantadas e executadas dentro do projeto ou workflow selecionado, ou para uma operação específica (veja [Implantação e Execução de Operações](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR)). Caso as operações estejam conectadas com [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR), os registros de operações mais abaixo na cadeia também são incluídos.

As operações-mãe (bem como todas as operações-filha abaixo delas) são organizadas em ordem crescente sob **Time Started** (Hora de Início). Você pode limitar as informações exibidas na tabela filtrando ou buscando.

No máximo, 250 registros de operação são exibidos. Para visualizar registros adicionais, ajuste os filtros como quiser, ou use a página [Atividades](https://success.jitterbit.com/display/DOC/Activities?showLanguage=pt_BR) do Management Console, que não tem o limite de 250.

<div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**DICA**: A configuração básica do que é incluído em um registro de operação é definida na aba **Options** (Opções) das configurações de operação (veja [Opções de Operação](https://success.jitterbit.com/display/CS/Operation+Options?showLanguage=pt_BR)). Para outras opções de registro, veja [Registros de Depuração de Operações](https://success.jitterbit.com/display/DOC/Operation+Debug+Logging?showLanguage=pt_BR).

</div>

</div>

### Visualizações

A tela de registros de operação tem duas visualizações: *full screen* (tela cheia) e *drawer* (gaveta). Qual visualização será mostrada depende de onde os registros são acessados:

- **Full Screen**: Ao visualizar os registros por projeto, a visualização *full screen* (em tela cheia) é carregada, com a tela de registros de operação carregando na aba que está atualmente ativa:

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_full-screen.png" class="confluence-embedded-image confluence-external-resource" /></span>

  - **Project Name** (Nome do Projeto): O nome do projeto (logo após o texto **Log for:** (Registro de:) é listado no topo da tela de registros de operação.

  - **Close** (Fechar): Para voltar à tela anterior, clique no ícone de fechamento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_15.png" class="confluence-embedded-image confluence-external-resource" /></span>.

- **Drawer**: Ao visualizar os registros por workflow ou por operação, uma “gaveta” de registros de operação é aberta na parte de baixo do *designer* de projeto para manter o seu contexto no projeto:

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_drawer.png" class="confluence-embedded-image confluence-external-resource" /></span>

  - **Tabs** (Abas): As abas no topo da gaveta de registros de operação são rotuladas com a palavra **Logging** seguida pelo nome da operação ou do workflow (dependendo de onde os registros foram acessados). Quando você acessa registros adicionais, novas abas são adicionadas. Para reordenar as abas, arraste e solte uma aba. Para fechar uma delas, clique no ícone de fechamento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_16.png" class="confluence-embedded-image confluence-external-resource" /></span>. Fechar a última aba ou usar o ícone de fechamento localizado mais à direita <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_17.png" class="confluence-embedded-image confluence-external-resource" /></span> fecha a gaveta inteira.

  - **Resize** (Mudar o tamanho): A barra no topo da gaveta de registros pode ser usada para mudar o tamanho dela. Paire o mouse sobre a barra e arraste o ícone de mudança de tamanho <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/resize.png" class="confluence-embedded-image confluence-external-resource" /></span> para cima ou para baixo para mudar o tamanho da gaveta de registros.

  - **Collapse** (Recolher): O ícone de recolhimento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/collapse_7.png" class="confluence-embedded-image confluence-external-resource" /></span> recolhe a gaveta de registros para que todos os registros sejam ocultos. Depois de recolhida, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return_3.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar à visualização anterior.

  - **Expand** (Expandir): O ícone de expansão <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/expand_4.png" class="confluence-embedded-image confluence-external-resource" /></span> aumenta a gaveta de registros para que registros adicionais sejam mostrados. Uma vez expandida, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return_3.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar à visualização anterior.

  - **Open in a New Tab** (Abrir numa Nova Aba): O ícone de aumento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout_3.png" class="confluence-embedded-image confluence-external-resource" /></span> abre a visualização de registros de operação em tela cheia numa nova aba.

  - **Close** (Fechar): O ícone de fechamento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_17.png" class="confluence-embedded-image confluence-external-resource" /></span> fecha a gaveta de registros.

A informação no restante do corpo dessas visualizações é a mesma em ambas e é descrita nas subseções abaixo.

### Período de Tempo

Por padrão, a opção **Start Time Range** () está configurada para que as últimas 24 horas de registros desde a última execução da operação sejam mostradas:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_range.png" class="confluence-embedded-image confluence-external-resource" /></span>

A data e a hora da seleção de período de tempo usam a hora do navegador local. Paire o mouse sobre a dica ao lado do texto **Start Time Range** para ver o fuso horário do seu navegador local:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_range_hover.png" class="confluence-embedded-image confluence-external-resource" /></span>

Para mudar o período de tempo por meio do qual os registros são filtrados, clique dentro de um campo **Start Time Range** para abrir o selecionador de data/hora. Daí, use os controles dentro do selecionador para ajustar a data e/ou a hora:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/operation_range_month.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Month** (Mês): O mês atual é usado por padrão. Use as setas <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/left-arrow_2.png" class="confluence-embedded-image confluence-external-resource" /></span> <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/right-arrow.png" class="confluence-embedded-image confluence-external-resource" /></span> para navegar para outro mês.

- **Year** (Ano): O ano atual é usado por padrão. Clique no ano, daí use as setas <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/left-arrow_2.png" class="confluence-embedded-image confluence-external-resource" /></span> <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/right-arrow.png" class="confluence-embedded-image confluence-external-resource" /></span> para navegar para outro ano. Daí, selecione o mês desejado do ano dentro do selecionador de meses. Selecionar um mês levará você de volta para o selecionador de data/hora.

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/operation_range_year.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Day** (Dia): Selecione o dia desejado do calendário.

- **Time** (Hora): Use os cursores para ajustar a hora (cursor de cima) e os minutos (cursos de baixo).

### Atualizar

Os registros iniciais são exibidos com base na data e na hora em que a última operação foi executada, conforme mostrado no alto da tabela. Os registros são automaticamente atualizados a cada cinco segundos caso alguma operação ainda esteja no meio de uma execução (com os *status* **Received** \[Recebida\], **Submitted** \[Enviada\], **Pending** \[Pendente\] ou **Running** \[Executando\]). A data e a hora em que a visualização foi atualizada pela última vez são relatadas abaixo de **Start Time Range** (Período da Hora de Início):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_refreshed.png" class="confluence-embedded-image confluence-external-resource" /></span>

Você também pode atualizar os registros manualmente a qualquer hora para exibir informações atualizadas. Para atualizar manualmente os registros, clique em **Refresh** (Atualizar) no canto superior direito:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_refresh.png" class="confluence-embedded-image confluence-external-resource" /></span>

### *Status*

A tabela pode ser filtrada por [*status* de operação](https://success.jitterbit.com/display/CS/Operation+Logs#OperationLogs-operation-status) conforme descrito abaixo. O [*status* de etapa de operação](https://success.jitterbit.com/display/CS/Operation+Logs#OperationLogs-operation-step-status) também é listado na tabela.

#### *Status* de Operação

Para filtrar os registros por *status* de operação, use o menu *dropdown* no canto superior direito:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_status.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **All** (Tudo): Todas as operações são mostradas independentemente do status.

- **Error** (Erro): Se o agente completa a execução de uma operação, mas houve um erro fatal na hora de gravar no sistema alvo, ou se houve um erro de validação fatal no *transformation*, ou a lógica do *transformation* acionou a função [`RaiseError`](https://success.jitterbit.com/display/CS/Logging+and+Error+Functions?showLanguage=pt_BR), então o *status* da operação é mudado para **Error** (Erro) e a execução da operação termina.

- **SOAP Fault** (Erro SOAP): Se o agente completa a execução de uma operação, e o resultado foi um erro SOAP, então o *status* é alterado para **SOAP Fault** (Erro SOAP). Este *status* é aplicável apenas para operações usando atividades da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud?showLanguage=pt_BR), [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax?showLanguage=pt_BR), [SOAP](https://success.jitterbit.com/display/CS/SOAP?showLanguage=pt_BR) ou [Workday](https://success.jitterbit.com/display/CS/Workday?showLanguage=pt_BR).

- **Submitted** (Enviadas): Quando as operações são enviadas para a fila do Harmony, mas ainda precisam ser executadas por um agente, elas têm *status* de **Submitted** (Enviada). As operações podem ser enviadas de várias formas:

  - Serviço de agendamento da Jitterbit ou serviço de agendamento externo

  - Execução manual da operação no Cloud Studio

  - Uma função [`RunOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR) de um *script* ou de um *transformation*

  - Qualquer ferramenta, incluindo `JitterbitUtils`, que chame a Jitterbit Harmony API

- **Received** (Recebidas): Quando um agente é escolhido e o agente reconhece que recebeu o pedido para executar uma operação, o *status* é mudado para **Received** (Recebida).

- **Pending** (Pendentes): Quando uma operação é agendada para execução no motor de operação de um agente, o *status* é alterado para **Pending** (Pendente). As operações não devem permanecer com *status* de **Pending** por muito tempo, já que os agentes devem iniciar a execução das operações de forma rápida.

- **Running** (Executando): Quando o agente começa a executar uma operação, o *status* deve mudar para **Running** (Executando). As operações permanecem neste *status* até estarem completas ou até encontrarem um erro. O agente começa a registrar mensagens geradas pela operação enquanto ela executa para que os usuários possam rastrear qual parte da operação está sendo executada no momento.

- **Cancel Requested** (Cancelamento Solicitado): Se um usuário quer deter uma operação que está com *status* de **Submitted** (Enviada), **Received** (Recebida), **Pending** (Pendente) ou **Running** (Executando), ele pode fazer isso na página [Atividades](https://success.jitterbit.com/display/DOC/Activities?showLanguage=pt_BR) do [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR). Como alternativa, ele pode habilitar que uma operação seja cancelada por outra usando uma combinação das funções [`GetOperationQueue`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR) e [`CancelOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR). Quando um cancelamento for solicitado, o *status* da operação muda para **Cancel Requested** (Cancelamento Solicitado). Uma operação não deve permanecer nesse *status* por muito tempo, já que o agente deve cancelar a operação num período de tempo relativamente curto.

- **Canceled** (Canceladas): Quando um agente cancela uma operação, ele muda o *status* dela para **Canceled** (Cancelada) e a operação é encerrada. Todas as informações de registro até o momento do cancelamento ficam disponíveis para revisão nas mensagens de registro para que você saiba em que momento a operação foi cancelada.

- **Success** (Sucesso): Quando um agente completa a execução de uma operação, se o resultado tiver sido um sucesso sem avisos sérios do sistema alvo, ou aviso escrito no *transformation* usando a função [`WriteToOperationLog`](https://success.jitterbit.com/display/CS/Logging+and+Error+Functions?showLanguage=pt_BR), então o *status* é alterado para **Success** (Sucesso).

- **Success with Info** (Sucesso com Informações): Caso o agente complete a execução de uma operação, mas houve erros não-fatais no *transformation* ou na postagem para o sistema alvo ou a função [`WriteToOperationLog`](https://success.jitterbit.com/display/CS/Logging+and+Error+Functions?showLanguage=pt_BR) foi usada para escrever mensagens no registro, então o *status* é mudado para **Success with Info** (Sucesso com Informações). Isto alerta o usuário para que verifique as informações nas mensagens de registro.

- **Success with Warning** (Sucesso com Alerta): Se o agente completa a execução de uma operação, mas houve erros não-fatais no *transformation* ou na postagem para o sistema alvo e houve um alerta, então o *status* é alterado para **Success with Warning** (Sucesso com Alerta). Isto alerta o usuário para que verifique as informações nas mensagens de registro.

- **Success with Child Error** (Sucesso com Erro no Descendente): Se o agente completa a execução bem-sucedida de uma operação, mas dentro de uma ou mais das operações-filha houve um erro fatal na postagem para o sistema alvo, ou houve um erro de validação fatal no *transformation*, ou a lógica do *transformation* deu início à função [`RaiseError`](https://success.jitterbit.com/display/CS/Logging+and+Error+Functions?showLanguage=pt_BR), então o *status* da operação é mudado para **Success with Child Error** (Sucesso com Erro no Descendente). Este *status* não se aplica a operações assíncronas.

- **Delayed Status** (*Status* Atrasado): Se o agente não retornar um registro de operação por algum motivo, **Delayed Status** (*Status* Atrasado) é exibido. O Harmony tentará buscar registros seis vezes, com um intervalo de 10 segundos entre cada chamada. Atualize ou verifique os registros de novo mais tarde.

#### *Status* de Etapa de Operação

As etapas de operação aparecem somente quando aquela operação tem a opção de [registro da depuração da operação](https://success.jitterbit.com/display/DOC/Operation+Debug+Logging?showLanguage=pt_BR) habilitada a nível de operação e a operação foi executada num Private Agent versão 10.48 ou posterior.

As etapas de operação podem ter os seguintes possíveis *status*:

- **Complete** (Completa): A etapa de operação foi executada e completada sem nenhum erro.

- **Error** (Erro): A etapa de operação foi executada mas não pôde ser completada devido a um erro.

- **Incomplete** (Incompleta): A etapa de operação não foi executada ou completada. Possíveis razões para este *status* incluem que a etapa de operação ainda está esperando para ser executada ou que houve um erro em uma etapa anterior impedindo a etapa seguinte de ser executada.

### Busca

Clique no ícone de busca <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/search_2.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar uma caixa de busca para inserir palavras-chave no formato especificado para fazer uma busca dentro da tela de registro de operação.

Um símbolo de porcentagem (`%`) pode ser usado como coringa no início e/ou no final de uma palavra-chave.

#### Por Projeto ou Workflow

Ao visualizar registros para o projeto inteiro ou para um workflow, você pode buscar por nome de operação ou por mensagem dentro da tela de registro de operação:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_search_project.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Operation** (Operação): Buscas por nome de operação devem ser especificadas no formato `operation=keyword`.

- **Message** (Mensagem): Buscas por mensagem devem ser especificadas no formato `message=keyword`.

Apenas uma única palavra-chave de operação e uma única palavra-chave de mensagem são suportadas. Quando ambas são fornecidas, as palavras-chave são tratadas como uma combinação; ou seja, são retornados registros de operação que correspondem ***tanto*** à palavra-chave de operação ***quanto*** à palavra-chave de mensagem.

#### Por Operação

Ao ver os registros de uma única operação, você pode procurar por mensagem de registro de operação apenas:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_search_operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Message** (Mensagem): As buscas por mensagem devem ser especificadas no formato `message=keyword`.

<div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**DICA:** Para habilidades de busca em registro adicionais, você também pode ver registros por meio da página [Atividades](https://success.jitterbit.com/display/DOC/Activities?showLanguage=pt_BR) do [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR).

</div>

</div>

### Tabela de Registros

A tabela de registros de operação inclui as colunas descritas abaixo. A tabela pode ser organizada (apenas para operações de nível mais alto) por **Name** (Nome), **Time Started** (Hora de Início), **Time Done** (Hora de Término) ou **Duration** (Duração) clicando no cabeçalho da linha respectiva.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_table.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Name** (Nome): O nome da operação ou etapa da operação. Triângulos de revelação <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://success.jitterbit.com/download/thumbnails/91625184/down-arrow_6.png?version=1&modificationDate=1637701969655&api=v2" class="confluence-embedded-image confluence-external-resource" /></span>, <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://success.jitterbit.com/download/thumbnails/91625184/right-arrow_5.png?version=1&modificationDate=1637701969707&api=v2" class="confluence-embedded-image confluence-external-resource" /></span>, que podem ser usados para expandir ou recolher linhas adicionais, são mostradas nas operações-mãe e nas operações para as quais os dados de entrada e saída estão disponíveis:

  - **Operações-Mãe:** Quando uma operação-mãe é expandida, linhas adicionais para suas operações-filha aparecem na ordem em que foram executadas.

  - **Operações com Dados de Entrada e Saída**: Quando uma operação com dados de entrada e saída é expandida, linhas adicionais para cada etapa de operação aparecem na ordem em que foram executadas. Mais informações são dadas no próximo item desta lista, **Input/Output** (Entrada/Saída).

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: As operações têm dados de entrada e saída quando os [registros de depuração de operação](https://success.jitterbit.com/display/DOC/Operation+Debug+Logging?showLanguage=pt_BR) estão habilitados a nível de operação para operações sendo executadas num Private Agent versão 10.48 ou posterior.

    </div>

    </div>

- **Input/Output** (Entrada/Saída): Uma representação gráfica da operação ou etapa de operação. Cada operação ou etapa de operação tem ícones que podem ser clicados para mostrar informações de registro adicionais.

  - **Operation** (Operação): Paire o mouse sobre qualquer lugar de uma fila de operação para mostrar um ícone de registro <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/log.png" class="confluence-embedded-image confluence-external-resource" /></span>, que pode ser clicado para mostrar ou esconder o registro daquela operação:

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/logs_table_expanded.png" class="confluence-embedded-image confluence-external-resource" /></span>

    - **Source Records** (Registros da Fonte): Uma contagem dos registros que foram lidos do sistema fonte.

    - **Target Records** (Registros do Alvo): Uma contagem dos registros que foram postados no sistema alvo.

    - **Log Messages** (Mensagens de Registro): As mensagens de registro incluem os detalhes de registro da operação selecionada. Se as mensagens de registro são exibidas ou não depende das permissões e níveis de acesso do usuário atual e da opção de registro em nuvem estar ou não habilitada. Para mais informações, consulte a seção [Mensagens de Registro](https://success.jitterbit.com/display/DOC/Activities#Activities-log-messages) na página [Atividades](https://success.jitterbit.com/display/DOC/Activities?showLanguage=pt_BR) da documentação do Management Console.

      Sob certas circunstâncias, um botão **Try Again** (Tentar de Novo) pode ser exibido, abordado na seção [Retentativa de Operações](https://success.jitterbit.com/display/CS/Operation+Logs#OperationLogs-operation-retry), abaixo.

      <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

      <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

      <div class="confluence-information-macro-body">

      **NOTA**: Datas e horas exibidas dentro das mensagens de registro em si não são convertidas para a hora do navegador local, mas são reportadas em seu formato original da fonte da mensagem de registro.

      </div>

      </div>

    - **Copy** (Copiar): Clique no ícone de cópia <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/copy_2.png" class="confluence-embedded-image confluence-external-resource" /></span> para copiar os dados do registro para a sua área de transferência. Quando é clicado, um ícone de prancheta <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/clipboard.png" class="confluence-embedded-image confluence-external-resource" /></span> é temporariamente exibido.

    - **Close** (Fechar): Clique no ícone de fechamento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_14.png" class="confluence-embedded-image confluence-external-resource" /></span> para esconder o registro de operação.

  - **Operation Step** (Etapa de Operação): Etapas de operação com dados de entrada e saída exibem um ícone de expansão ou recolhimento (<https://docs-source.jitterbit.com/common/icons/expand_5.png>, <https://docs-source.jitterbit.com/common/icons/collapse_8.png>), que podem ser clicados para mostrar ou esconder os dados de entrada e saída daquela etapa de operação individual. Os dados de entrada e saída estão disponíveis apenas para as atividades e *transformations* usados como etapas de operação. Cada entrada nos registros de entrada e saída é limitada a 100MB. Se os dados de um registro de entrada ou saída individual excederem o limite de 100MB, nenhum dado será exibido.

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA:** As linhas de etapas de operação só aparecem quando aquela operação tem a opção dos [registros de depuração de operação](https://success.jitterbit.com/display/DOC/Operation+Debug+Logging?showLanguage=pt_BR) habilitada a nível de operação e quando a operação foi executada num Private Agent versão 10.48 ou posterior.

    A geração de dados de entrada e saída de operação não é afetada pela configuração do Grupo de Agentes chamada **Enable Cloud Logging** (Habilitar Registros em Nuvem) (veja [Agentes \> Grupo de Agentes](https://success.jitterbit.com/display/DOC/Agents+%3E+Agent+Groups)). Dados de entrada e saída de operação serão registrados na nuvem do Harmony mesmo que os registros em nuvem estejam desabilitados.

    Para desabilitar a geração de dados de entrada e saída de operação em um Grupo de Agentes, no [arquivo de configuração de Private Agent](https://success.jitterbit.com/display/DOC/Editing+the+Configuration+File+-+jitterbit.conf) sob a seção `[VerboseLogging]`, configure `verbose.logging.enable=false`.

    </div>

    </div>

    <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **AVISO:** Quando dados de entrada e saída de operação são gerados, todos os dados de solicitação e resposta daquela operação são registrados na nuvem do Harmony e permanecem lá por 7 dias. Esteja ciente de que informações pessoalmente identificáveis (PII) e dados sensíveis como credenciais fornecidas numa *payload* de resposta estarão visíveis em texto simples nos dados de entrada e saída dentro dos registros em nuvem do Harmony.

    </div>

    </div>

    <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/91625184/image2022-1-25_15-1-18.png?version=1&modificationDate=1643387394255&api=v2" class="confluence-embedded-image confluence-external-resource" /></span>

      - **Copy** (Copiar): Clique no ícone de cópia <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/copy_2.png" class="confluence-embedded-image confluence-external-resource" /></span> para copiar os dados do registro para a sua área de transferência. Quando é clicado, um ícone de prancheta <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/clipboard.png" class="confluence-embedded-image confluence-external-resource" /></span> é temporariamente exibido.

      - **Download** (Baixar): Clique no ícone de download <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/download.png" class="confluence-embedded-image confluence-external-resource" /></span> para baixar os dados de entrada ou saída como um arquivo no formato de dados apropriado. O arquivo tem o mesmo nome da etapa de operação seguido de `_input` (entrada) ou `_output` (saída) conforme apropriado.

- **Time Started** (Hora de Início): A data e a hora em que a operação ou etapa de operação começou a executar, exibidas na hora do navegador local.

- **Time Done** (Hora de Término): A data e a hora em que a operação ou etapa de operação terminou de executar, exibidas na hora do navegador local.

- **Duration** (Duração): O tempo decorrido entre a hora de início e a hora de término, relatada em segundos para as operações e em milissegundos para as etapas de operação.

- **Status**: O *status* da operação ou etapa de operação. Para uma lista completa de possíveis *status*, veja a seção [Status](https://success.jitterbit.com/display/CS/Operation+Logs#OperationLogs-FilterbyStatus) mais acima nesta mesma página.

#### Retentativa de Operação

Se uma operação falhar com um erro relacionado a dependências de arquivo, este problema pode ser resolvido ressincronizando o projeto entre o agente e o Harmony. Neste cenário, um botão **Try Again** (Tentar de Novo) aparece nos registros de operação.

Quando se clica em **Try Again**, o projeto é ressincronizado entre o agente e o Harmony.

Depois que a ressincronização está completa, uma tentativa de reexecução da operação ocorre imediatamente. Nos casos em que uma operação-mãe ou filha falhou, a cadeia de operações inteira passa pela tentativa de reexecução desde o nível mais alto até as operações mais abaixo na cadeia.

Se isso for bem-sucedido, um *status* de sucesso é exibido no novo registro de operação. Se a operação falhar de novo, novas tentativas de sincronizar o agente não vão ajudar e o motivo para a falha pode ser devido a outra coisa (entre em contato com o [Suporte Jitterbit](https://success.jitterbit.com/display/DOC/Getting+Support?showLanguage=pt_BR) para receber ajuda).
