[//]: # (Opções de Operação)
[//]: # (This is a translation of Version 23, published on January 28, 2022.)


## Introdução

Toda operação pode ser configurada com opções tais como quando a operação esgotará seu tempo, o que registrar, e o prazo para os registros de depuração da operação. A presença de certos componentes como etapas de operação torna visíveis opções adicionais para decidir se uma operação subsequente deverá ser executada ou caso a fragmentação de dados (*chunking*) deverá ser usada.

## Acessando Opções de Operação

A opção **Settings** (Configurações) é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Quando a tela de configurações de operação estiver aberta, selecione a aba **Options** (Opções):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/options_tab.png" class="confluence-embedded-image confluence-external-resource" /></span>


## Configurando Opções de Operação

Todas as opções disponíveis na aba **Options** (Opções) das configurações de operação estão descritas abaixo.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/options_dialog.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Operation Time Out** (Limite de Tempo da Operação): Especifique a quantidade máxima de tempo que a operação pode executar antes de ser cancelada. No primeiro campo, insira um número e no segundo campo use o menu *dropdown* para selecionar as unidades em **Seconds** (Segundos), **Minutes** (Minutos) ou **Hours** (Horas). O padrão são 2 horas.

  Razões comuns para ajustar este parâmetro incluem:

  - Aumentar o tempo limite caso a operação tenha conjuntos de dados muito grandes que estejam demorando para executar.

  - Diminuir o tempo limite caso a operação tenha certa urgência; isto é, você não quer que a operação seja considerada bem-sucedida caso não possa ser completada dentro de certo prazo.

  <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

  <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **NOTA**: Operações que são iniciadas pelas [APIs do API Manager](https://success.jitterbit.com/display/DOC/My+APIs?showLanguage=pt_BR) não estão sujeitas à configuração **Operation Time Out** quando você estiver usando Cloud Agents. Com Private Agents, use a configuração `EnableAPITimeout` no [arquivo de configuração do Private Agent](https://success.jitterbit.com/display/DOC/Editing+the+Configuration+File+-+jitterbit.conf?showLanguage=pt_BR) para que a configuração **Operation Time Out** se aplique às operações iniciadas por APIs.

  </div>

  </div>

- **What to Log** (O que Registrar): Use o menu *dropdown* para selecionar o que registrar nos [registros da operação](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR), entre as opções **Everything** (Tudo) (esta é a opção padrão) ou **Errors Only** (Somente Erros):

  - **Everything** (Tudo): Operações com qualquer [*status* de operação](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR#OperationLogs-FilterbyStatus) são registradas.

  - **Errors Only** (Somente Erros): Apenas operações com um *status* de tipo erro (como **Error** (Erro), **SOAP Fault** (Erro SOAP) ou **Success with Child Error** (Sucesso com Erro na Filha)) são registradas. Operações-filha bem-sucedidas não são registradas. Operações-mãe (nível raiz) são sempre registradas, já que elas exigem registros para funcionar corretamente.

  Um motivo comum para querer limitar os registros a **Errors Only** (Somente Erros) é se você estiver tendo problemas de latência de operações. Desta forma, se você não estava planejando usar as outras mensagens (não as de erro) normalmente filtradas nos registros de operação, você pode impedi-las de serem geradas.

- **Enable Debug Mode Until** (Habilitar Modo de Depuração Até): Selecione esta opção para habilitar os registros de depuração da operação para os Private Agents e especificar uma data em que o modo de depuração será automaticamente desabilitado, com o limite máximo de duas semanas após a data atual. Os registros de depuração da operação serão desligados no início desta data (ou seja, à meia-noite) usando o fuso horário do Private Agent.

  <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

  <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **NOTA**: Esta opção não é aplicável ao usar Cloud Agents e não gera registros adicionais quando é selecionada.

  </div>

  </div>

  Quando você selecionar **Enable Debug Mode Until**, uma caixa de diálogo oferecerá uma caixa de seleção chamada **Also Apply to Child Operations** (Aplicar Também às Operações-Filha) que vai fazer as configurações “descerem” também para as operações-filha. Esta opção também aparece quando você remove a configuração do modo de depuração da operação.

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/enable-debug-logging.png" class="confluence-embedded-image confluence-external-resource" /></span>

  Quando os registros de depuração da operação estiverem habilitados, as mensagens de depuração são registradas em arquivos em um Private Agent e, quando Private Agents 10.48 ou posteriores estiverem em uso, os dados de entrada e saída são exibidos na [tela de registro de operação](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR) do Cloud Studio. Os arquivos de registro de depuração do Private Agent são acessíveis a partir das páginas [Atividades](https://success.jitterbit.com/display/DOC/Activities?showLanguage=pt_BR) e [Agents \> Agents](https://success.jitterbit.com/display/DOC/Agents+%3E+Agents?showLanguage=pt_BR) do Management Console.

  Esta opção é usada principalmente para problemas de depuração durante a testagem e não deve ser ativada em ambientes de produção. Os registros de depuração a nível de operação podem ajudar caso você esteja tendo dificuldades com uma operação específica e não precise ligar os registros de depuração da operação a nível de agente, já que isso pode criar arquivos muito grandes.

  Para detalhes adicionais, consulte [Registros de Depuração de Operação](https://success.jitterbit.com/display/DOC/Operation+Debug+Logging?showLanguage=pt_BR).

  <div class="confluence-information-macro confluence-information-macro-note conf-macro output-block" data-hasbody="true" data-macro-name="info">

  <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **CUIDADO**: A geração de dados de entrada e saída da operação não é afetada pela configuração **Enable Cloud Logging** (Habilitar Registros em Nuvem) do Agent Group (veja [Agentes \> Agent Groups](https://success.jitterbit.com/display/DOC/Agents+%3E+Agent+Groups?showLanguage=pt_BR)). Os dados de entrada e saída das operações serão registrados na nuvem do Harmony mesmo que os registros em nuvem estejam desabilitados.

  Para desabilitar a geração de dados de entrada e saída das operações em um Agent Group, no [arquivo de configuração do Private Agent](https://success.jitterbit.com/display/DOC/Editing+the+Configuration+File+-+jitterbit.conf?showLanguage=pt_BR) sob a seção `[VerboseLogging]`, defina `verbose.logging.enable=false`.

  </div>

  </div>

  <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

  <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **AVISO**: Quando dados de entrada e saída das operações forem gerados, todos os dados de solicitação e resposta daquela operação são registrados na nuvem do Harmony e permanecem lá por 7 dias. Esteja ciente de que informações pessoalmente identificáveis (PII, sigla em inglês) e dados sensíveis como credenciais fornecidas em uma *payload* de solicitação estarão visíveis em texto simples nos dados de entrada e saída dentro dos registros da nuvem do Harmony.

  </div>

  </div>

- **Run Success Operation Even If There Are No Matching Source Files** (Executar Operação de Sucesso Mesmo que Não Haja Arquivos Fonte Correspondentes): Selecione esta opção para forçar uma operação acima na cadeia a ser bem-sucedida. Isto permite que você inicie uma operação com uma condição **On Success** (Em Caso de Sucesso) (configurada com uma [ação de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR)) mesmo que o gatilho tenha falhado.

  Esta opção está presente apenas se a operação contiver uma [atividade baseada em arquivos](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-file-server) que seja usada como fonte na operação, e aplica-se somente quando a operação tiver uma condição **On Success** (Em Caso de Sucesso) configurada. Por padrão, toda operação **On Success** só executa se tiver um arquivo fonte correspondente para processar. Esta opção pode ser útil para preparar partes posteriores de um projeto sem exigir o sucesso de uma operação dependente.

  <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

  <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **NOTA**: A configuração `AlwaysRunSuccessOperation` na seção `[OperationEngine]` do [arquivo de configuração do Private Agent](https://success.jitterbit.com/display/DOC/Editing+the+Configuration+File+-+jitterbit.conf?showLanguage=pt_BR) anula esta configuração.

  </div>

  </div>

- **Enable Chunking** (Habilitar Fragmentação): Selecione para habilitar a fragmentação usando os parâmetros especificados:

  - **Chunk Size** (Tamanho dos Fragmentos): Insira um número de registros fonte (nós) a ser processados em cada *thread*. Quando a fragmentação estiver habilitada para operações que não contêm nenhuma atividade da Salesforce, o tamanho padrão dos fragmentos é `1`. Quando uma atividade da Salesforce for adicionada a uma operação que não tenha a fragmentação habilitada, a fragmentação é automaticamente habilitada com tamanho padrão dos fragmentos de `200`. Se você estiver usando uma atividade da Salesforce de tipo *bulk*, mude este valor para um número bem maior, como 10.000.

  - **Number of Records per File** (Número de Registros por Arquivo): Coloque um número exigido de registros a serem inseridos no arquivo alvo. O padrão é `0`, o que significa que não há limite para o número de registros por arquivo.

  - **Max Number of Threads** (Número Máximo de *Threads*): Coloque o número de *threads* simultâneas a processar. Quando a fragmentação estiver habilitada para operações que não contenham nenhuma atividade da Salesforce, o número padrão de *threads* é `1`. Quando uma atividade da Salesforce for adicionada a uma operação na qual a fragmentação não esteja habilitada, ela será automaticamente habilitada com um número padrão de *threads* de `2`.

  Esta opção só está presente se a operação contiver um [*transformation*](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR) ou um [banco de dados](https://success.jitterbit.com/display/CS/Database?showLanguage=pt_BR), ou uma atividade [NetSuite](https://success.jitterbit.com/display/CS/NetSuite?showLanguage=pt_BR), [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud?showLanguage=pt_BR), [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax?showLanguage=pt_BR) ou [SOAP](https://success.jitterbit.com/display/CS/SOAP?showLanguage=pt_BR), e se for usada para processar dados para o sistema alvo em fragmentos. Isto permite processamento mais rápido de grandes conjuntos de dados e também é usado para lidar com limites de registros impostos por vários sistemas baseados em serviços *web* ao fazer uma solicitação.

  Note que se você estiver usando um *endpoint* da Salesforce (ou seja, Salesforce, Salesforce Service Cloud ou ServiceMax):

  - Se uma atividade da Salesforce for adicionada a uma operação que não tem a fragmentação habilitada, ela será habilitada com configurações padrão especificamente para atividades da Salesforce conforme descrito acima.

  - Se uma atividade da Salesforce for adicionada a uma operação que já tem a fragmentação habilitada, as configurações da fragmentação não serão mudadas. Da mesma forma, se uma atividade da Salesforce for removida de uma operação, as configurações da fragmentação não são mudadas.

  Informações adicionais e melhores práticas de fragmentação são fornecidas na seção seguinte, [Fragmentação](https://success.jitterbit.com/display/CS/Operation+Options?showLanguage=pt_BR#OperationOptions-chunking).

- **Save Changes** (Salvar Mudanças): Clique para salvar e fechar as configurações da operação.

- **Discard Changes** (Descartar Mudanças): Depois de fazer mudanças nas configurações da operação, clique para fechar as configurações sem salvar.

### Fragmentação

A fragmentação é usada para dividir os dados fonte em vários fragmentos baseados no tamanho de fragmento que foi configurado. O tamanho de fragmento é o número de registros fonte (nós) para cada fragmento. O *transformation* é então realizado em cada fragmento separadamente, com cada fragmento fonte produzindo um fragmento alvo. Os fragmentos alvo resultantes são combinados para formar o alvo final.

A fragmentação pode ser usada somente se os registros forem independentes e advindos de uma fonte não-LDAP. Nós recomendamos que seja usado um tamanho de fragmento o maior possível, garantindo assim que os dados de um fragmento caibam na memória disponível. Para métodos adicionais para limitar a quantidade de memória que um *transformation* usa, veja [Processamento de *Transformations*](https://success.jitterbit.com/display/CS/Transformation+Processing?showLanguage=pt_BR).

<div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**AVISO**: Usar fragmentação afeta o comportamento das variáveis globais e de projeto. Veja [Usar Variáveis com Fragmentação](https://success.jitterbit.com/display/CS/Operation+Options?showLanguage=pt_BR#OperationOptions-variables) abaixo.

</div>

</div>

#### Limitações de API

Muitas APIs de serviços *web* (SOAP/REST) têm limitações de tamanho. Por exemplo, um *upsert* da Salesforce aceita apenas 200 registros para cada chamada. Com memória suficiente, você poderia configurar uma operação para usar um tamanho de fragmento igual a 200. A fonte seria dividida em fragmentos de 200 registros cada, e cada *transformation* chamaria o serviço *web* uma vez com um fragmento de 200 registros. Os arquivos alvo resultantes seriam então combinados. (Note que você poderia também usar atividades da Salesforce de tipo *bulk* para evitar o uso da fragmentação).

#### Processamento Paralelo

Se você tiver uma fonte grande e um computador com várias CPUs, a fragmentação pode ser usada para dividir a fonte para processamento paralelo. Já que cada fragmento é processado isoladamente, vários fragmentos podem ser processados paralelamente. Isto aplica-se somente se os registros fonte forem independentes uns dos outros a nível de nó fragmentado. Os serviços *web* podem ser chamados em paralelo usando a fragmentação, o que melhoraria a performance.

Ao usar fragmentação em uma operação na qual o alvo é um banco de dados, note que os dados alvo são primeiro registrados em vários arquivos temporários (um para cada fragmento). Estes arquivos são então combinados em um arquivo alvo, que é enviado para o banco de dados para o *insert*/*update*. Se você definir a variável Jitterbit [`jitterbit.target.db.commit_chunks`](https://success.jitterbit.com/display/CS/Target+Jitterbit+Variables?showLanguage=pt_BR) como `1` ou como `true` quando a fragmentação estiver habilitada, cada fragmento será posto no banco de dados quando ficar disponível. Isto pode melhorar a performance significativamente já que as atividades *insert*/*update* do banco de dados são feitas em paralelo.

#### Usando Variáveis com Fragmentação

Já que a fragmentação pode envolver várias *threads*, usá-la pode afetar o comportamento de variáveis que não são divididas entre *threads*.

As [variáveis globais](https://success.jitterbit.com/display/CS/Global+Variables?showLanguage=pt_BR) e [de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) são segregadas entre as instâncias da fragmentação, e embora os dados sejam combinados, mudanças a essas variáveis não são. Apenas as mudanças feitas à *thread* inicial são preservadas no fim do *transformation*.

Por exemplo, se uma operação - com fragmentação e várias *threads* - tiver um *transformation* que muda uma variável global, o valor da variável global depois do fim da operação será o valor da ***primeira*** *thread*. Quaisquer mudanças feitas à variável em outras *threads* são independentes e serão descartadas quando a operação for completada.

Estas variáveis globais são passadas às outras *threads* por valor e não por referência, o que garante que quaisquer mudanças feitas às variáveis não são refletidas em outras *threads* ou operações. Isto é similar à função [`RunOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR) quando está em modo assíncrono.
