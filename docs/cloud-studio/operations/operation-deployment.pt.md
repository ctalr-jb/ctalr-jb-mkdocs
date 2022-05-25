[//]: # (Implantação e Execução de Operações)
[//]: # (This is a translation of Version 33, published on February 16, 2022.)


## Introdução

Esta página descreve como implantar operações ou componentes de projeto selecionados na nuvem do Jitterbit Harmony. Uma vez que todos os componentes dos quais uma operação depende estejam implantados, a operação pode ser executada. Para a sua conveniência, você pode escolher executar uma operação usando componentes implantados existentes ou executar uma operação usando componentes que são automaticamente implantados no momento da execução.


## Implantando

Existem três opções para a implantação de operações: implantar diretamente, implantar diretamente e executar a operação e configurar uma implantação:

- **Deploy** (Implantar): Esta opção refere-se à implantação direta de uma operação e de seus componentes dependentes. Selecionar esta opção implanta a operação imediatamente junto com todos os componentes dos quais ela depende, ou reporta quais erros de validação impediram a implantação.

- **Deploy and Run** (Implantar e Executar): Esta opção é igual à opção **Deploy** (Implantar), com a diferença de que depois de uma implantação bem-sucedida, a operação e todas as operações abaixo dela na cadeia também são executadas (veja [Executando](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR#OperationDeploymentandExecution-execute) mais abaixo nesta mesma página).

- **Configurable Deploy** (Implantação Configurável): Esta opção refere-se à implantação de componentes do projeto selecionados. Selecionar esta opção abre uma tela de configuração de implantação onde você pode escolher quais componentes do projeto deseja implantar. A operação e os componentes do projeto dos quais a operação depende já são selecionados por padrão.

Em todas as três opções, telas adicionais podem ser apresentadas em certas circunstâncias:

- [**Selecionando Agendas e Variáveis de Projeto**](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR#OperationDeploymentandExecution-selecting-schedules-and-project-variables): Se houver variáveis de projeto ou agendas sendo implantadas que já tenham sido implantadas na nuvem do Harmony, uma tela dará a você opções para selecionar quais valores usar.

- [**Adicionando** ***Tags*** **e Comentários**](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR#OperationDeploymentandExecution-deploy-requirements): Caso as configurações de implantação a nível de projeto tenham sido definidas de modo a exigir uma *tag* e/ou um comentário na hora de implantar, uma caixa de diálogo será mostrada para que você possa inserir a *tag* e/ou o comentário.

Você pode continuar trabalhando durante uma implantação. Mensagens informativas no canto superior direito da tela indicam quando uma implantação está em progresso e quando foi completada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/operation-deploy-in-progress.png" class="confluence-embedded-image confluence-external-resource" /></span>

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/operation-successful-deploy.png" class="confluence-embedded-image confluence-external-resource" /></span>

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Ao renomear um projeto que já tenha sido implantado, o novo nome do projeto é **automaticamente** implantado e atualizado no Jitterbit Harmony. Nenhuma outra parte do projeto além do nome é implantada automaticamente desta forma.

</div>

</div>

### Deploy (Implantar)

A opção **Deploy** (Implantar) para uma operação é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **Deploy** (Implantar), uma tentativa de implantação ocorre imediatamente para a operação e para todos os componentes dos quais ela depende. Para que a implantação tenha sucesso, todos os componentes dependentes devem ser válidos. Se qualquer um dos componentes dependentes for inválido, o(s) erro(s) de validação específico(s) que impediu(ram) a implantação é(são) mostrado(s) numa caixa de diálogo. Para ver a documentação de cada erro e como resolvê-lo, consulte os artigos [Validade de Workflows](https://success.jitterbit.com/display/CS/Workflow+Validity?showLanguage=pt_BR), [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR) ou [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR), respectivamente.

### Deploy and Run (Implantar e Executar)

A opção **Deploy and Run** (Implantar e Executar) é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **Deploy and Run** (Implantar e Executar), uma tentativa de implantação ocorre imediatamente para a operação e para todos os componentes dos quais ela depende. Para que a implantação tenha sucesso, todos os componentes dependentes devem ser válidos. Se qualquer um dos componentes dependentes for inválido, o(s) erro(s) de validação específico(s) que impediu(ram) a implantação é(são) mostrado(s) numa caixa de diálogo. Para ver a documentação de cada erro e como resolvê-lo, consulte os artigos [Validade de Workflows](https://success.jitterbit.com/display/CS/Workflow+Validity?showLanguage=pt_BR), [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR) ou [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR), respectivamente.

Se a implantação tiver sucesso, a operação e todas as operações abaixo dela na cadeia também são executadas. Para saber mais detalhes, consulte [Executando](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR#OperationDeploymentandExecution-execute) mais abaixo nesta mesma página.

### Configurable Deploy (Implantação Configurável)

A opção **Configurable Deploy** (Implantação Configurável) para configurar uma implantação para todos os componentes do projeto, com a operação e seus componentes dependentes selecionados por padrão, é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **Configurable Deploy** (Implantação Configurável), uma tela de configuração de implantação abre onde você pode escolher quais componentes do projeto deseja implantar:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_operations.png" class="confluence-embedded-image confluence-external-resource" /></span>

A operação e seus componentes dependentes são selecionados por padrão. Desmarque as caixas de seleção conforme desejar para implantar apenas componentes do projeto selecionados. Componentes que são dependências de outros componentes selecionados não podem ser desmarcados, já que a não-implantação destes itens faria com que o componente que tem a dependência se tornasse inválido.

Para expandir ou recolher workflows, operações e etapas de operação, use os triângulos de revelação <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/down-arrow_4.png" class="confluence-embedded-image confluence-external-resource" /></span> <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/right-arrow_4.png" class="confluence-embedded-image confluence-external-resource" /></span> exibidos à esquerda do nome do componente.

Os nomes de componentes inválidos aparecem em vermelho e em itálico. Além disso, os nomes dos componentes que não são usados diretamente em um workflow são precedidos de um til \~, conforme demonstrado na agenda abaixo:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_components_invalid.png" class="confluence-embedded-image confluence-external-resource" /></span>

Quando todos os componentes do projeto desejados que você queira implantar estiverem selecionados, clique no botão **Deploy** (Implantar).

Se qualquer um dos componentes selecionados for inválido, o(s) erro(s) de validação específico(s) é(são) mostrado(s) numa caixa de diálogo. Para ver a documentação sobre cada erro e como resolvê-lo, consulte os artigos [Validade de Workflows](https://success.jitterbit.com/display/CS/Workflow+Validity?showLanguage=pt_BR), [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR) ou [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR), respectivamente.


## Executando

Uma vez que todos os componentes dos quais uma operação depende tenham sido implantados, ela pode ser executada. Para a sua conveniência, você pode escolher executar uma operação usando componentes implantados, ou executar uma operação usando componentes que são automaticamente implantados no momento da execução. Quando você executa uma operação, todas as operações abaixo dela na cadeia (que estejam conectadas) também são executadas.

Conforme descrito abaixo, você pode executar as operações manualmente no momento do *design*, usando um *script* (seja no Cloud Studio ou no Design Studio), a partir de uma linha de comando num agente, usando um gatilho de API ou usando uma agenda. Uma vez que as operações tenham sido executadas, você pode validar o comportamento apropriado verificando os [registros de operação](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR).

### Executando Manualmente

A execução manual de uma operação é normalmente usada durante o desenvolvimento de um projeto para testar operações selecionadas ou o projeto inteiro. Isto pode ser feito no Cloud Studio conforme descrito abaixo, ou pode ser realizado na página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR) (Console de Gerenciamento) para operações que já tenham sido implantadas.

Quase todas as operações podem ser executadas manualmente. A exceção são operações que são iniciadas por meio do [API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR) do Harmony caso usem uma [atividade de solicitação API ou API SOAP](https://success.jitterbit.com/display/CS/API?showLanguage=pt_BR) que fornece dados fonte para a operação. Estas operações não podem ser executadas manualmente porque exigem que dados sejam fornecidos por uma API que fica exposta por meio do API Manager.

Existem duas opções para a execução de operações manual: executar uma operação usando componentes implantados existentes ou executar uma operação usando componentes que são automaticamente implantados no momento da execução:

- **Run** (Executar): Se uma operação e todos os seus componentes dependentes já tenham sido implantados, selecionar esta opção executa imediatamente a operação e todas as operações abaixo dela na cadeia usando os componentes implantados. Note que a(s) operação(ões) executada(s) não inclui(em) mudanças de *design* feitas após a implantação mais recente. Para executar a operação com as mudanças de *design* mais recentes, use a opção **Deploy and Run** (Implantar e Executar).

- **Deploy and Run** (Implantar e Executar): Selecionar esta opção implanta imediatamente a operação junto com todos os componentes dos quais ela depende (ou relata quais foram os erros de validação que impediram a implantação), daí executa a operação junto com todas as operações abaixo dela na cadeia usando componentes recém-implantados.

As operações que são executadas manualmente com qualquer um desses dois métodos exibem o *status* da operação em tempo real no design canvas, conforme descrito abaixo.

#### Run (Executar)

A opção **Run** (Executar) para executar uma operação usando componentes implantados existentes é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **Run** (Executar), caso uma operação junto com seus componentes dependentes já tenham sido implantados, a operação e todas as operações abaixo dela na cadeia conectadas a ela por meio de [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) também são iniciadas com base nas condições configuradas.

Caso uma operação ou seus componentes dependentes ainda não tenha sido implantada, uma mensagem indicando que a operação não pôde ser executada é mostrada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/failed-to-run-operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

Clique em **Continue** (Continuar) para voltar à tela anterior. Para implantar a operação e seus componentes dependentes, além de executar a operação, use a opção **Deploy and Run** (Implantar e Executar).

Caso uma operação ou seus componentes dependentes tenham sido implantados mas tenham passado por mudanças no *designer* de projeto do Cloud Studio desde a última vez que foram implantados, uma mensagem avisando da existência de mudanças não-implantadas é mostrada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/operation-has-undeployed-changes.png" class="confluence-embedded-image confluence-external-resource" /></span>

Clique em **Continue** (Continuar) para demonstrar que está ciente de que existem mudanças não-implantadas que não serão implantadas, e para executar a versão da operação e dos componentes dependentes que foi implantada por último *sem* as mudanças mais recentes feitas no *designer* de projeto do Cloud Studio.

Se você não quiser executar a versão implantada por último, clique em **Cancel** (Cancelar) para voltar à tela anterior. Para implantar a versão mais recente da operação e de seus componentes dependentes, além de executar a operação, use a opção **Deploy and Run** (Implantar e Executar).

#### Deploy and Run (Implantar e Executar)

A opção **Deploy and Run** (Implantar e Executar) para executar uma operação usando componentes que são automaticamente implantados no momento da execução é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **Deploy and Run** (Implantar e Executar), uma tentativa de implantação ocorre imediatamente para a operação e todos os componentes dos quais ela depende. A implantação precisa ter sucesso para que a operação possa executar, conforme descrito mais acima nesta mesma página na seção [Implantando](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR#OperationDeploymentandExecution-deploy).

Caso a implantação tenha sucesso, a operação e todas as operações abaixo dela na cadeia conectadas por meio de [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) também são iniciadas com base nas condições configuradas.

#### Operation Status (*Status* da Operação)

Se uma operação tiver sido submetida com sucesso à fila de operações, o *status* em tempo real da operação é reportado no canto inferior esquerdo da operação:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_status.png" class="confluence-embedded-image confluence-external-resource" /></span>

O *status* da operação é mostrado para todas as operações que são executadas dentro de uma cadeia de operações.

O *status* reportado corresponde com os *status* descritos na página [Registros de Operação](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR) sob [Filtrar por *Status*](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR#OperationLogs-FilterbyStatus). Clique no *status* da operação para ver informações de registro detalhadas. A tela de registro de operação abre automaticamente numa aba separada para que você possa continuar trabalhando enquanto as operações estão sendo executadas (veja [Registros de Operação](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR)).

Quando você tiver executado a operação manualmente, o *status* da operação é exibido em um projeto aberto por 24 horas e não é afetado por implantações adicionais ou por se executar a operação de qualquer outra forma. Apenas ao se re-executar manualmente a operação é que o *status* da operação será atualizado. O *status* da operação é limpo quando se fecha o projeto.

Paire o mouse sobre o *status* da operação para ver a última vez em que o *status* foi atualizado (no fuso horário do navegador local):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_status_hover.png" class="confluence-embedded-image confluence-external-resource" /></span>

O estilo de formatação do texto do *status* da operação é negrito se a operação estiver sendo executada, ou texto normal se a operação estiver completa ou em pausa.

A cor do ícone à esquerda do *status* reportado indica a categoria do *status* da operação:

<table class="wrapped confluenceTable tablesorter tablesorter-default stickyTableHeaders" role="grid" resolved="" style="padding: 0px;">
<colgroup><col style="width: 50.0px;">
<col style="width: 59.0px;">
<col style="width: 522.0px;">
</colgroup>
<thead class="tableFloatingHeaderOriginal" style="position: static; margin-top: 0px; left: 413px; z-index: 3; width: 641px; top: 61px;">
<tr role="row" class="tablesorter-headerRow">
<th colspan="1" class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="0" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;">
<div class="tablesorter-header-inner">Ícone</div>
</th>
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="1" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;">
<div class="tablesorter-header-inner">Cor</div>
</th>
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="2" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none; min-width: 8px; max-width: none;">
<div class="tablesorter-header-inner">Estado</div>
</th>
</tr>
</thead>
<thead class="tableFloatingHeader" style="display: none;">
<tr role="row" class="tablesorter-headerRow">
<th colspan="1" class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="0" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" class="confluence-embedded-image confluence-external-resource" /></span> style="user-select: none;">
<div class="tablesorter-header-inner">Ícone</div>
</th>
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="1" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none;">
<div class="tablesorter-header-inner">Cor</div>
</th>
<th class="confluenceTh tablesorter-header sortableHeader tablesorter-headerUnSorted" data-column="2" tabindex="0" scope="col" role="columnheader" aria-disabled="false" unselectable="on" aria-sort="none" style="user-select: none;">
<div class="tablesorter-header-inner">Estado</div>
</th>
</tr>
</thead>
<tbody aria-live="polite" aria-relevant="all">
<tr role="row">
<td colspan="1" class="confluenceTd">
<div class="content-wrapper"><p><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" height="17" src="https://docs-source.jitterbit.com/common/icons/success.png" data-image-src="https://docs-source.jitterbit.com/common/icons/success.png"></span></p></div>
</td>
<td class="confluenceTd">Verde</td>
<td class="confluenceTd">A operação está sendo executada atualmente ou foi completada com <em>status</em> bem-sucedido.</td>
</tr>
<tr role="row">
<td colspan="1" class="confluenceTd">
<div class="content-wrapper"><p><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" height="17" src="https://docs-source.jitterbit.com/common/icons/error_2.png" data-image-src="https://docs-source.jitterbit.com/common/icons/error_2.png"></span></p></div>
</td>
<td class="confluenceTd">Vermelho</td>
<td class="confluenceTd">A operação foi completada com <em>status</em> de erro.</td>
</tr>
<tr role="row">
<td colspan="1" class="confluenceTd">
<div class="content-wrapper"><p><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" height="17" src="https://docs-source.jitterbit.com/common/icons/inactive.png" data-image-src="https://docs-source.jitterbit.com/common/icons/inactive.png"></span></p></div>
</td>
<td class="confluenceTd">Cinza</td>
<td class="confluenceTd">A operação está atualmente pendente, foi cancelada ou está inativa de alguma forma.</td>
</tr>
</tbody>
</table>

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Quando as operações estão na visualização recolhida, apenas os ícones coloridos indicando a categoria do *status* da operação são exibidos.

</div>

</div>

### Usando um *Script*

Para executar uma operação a partir de um *script*, chame a função [`RunOperation`](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR#GeneralFunctions-RunOperation) em um *script*, conforme descrito na [documentação das funções](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR#GeneralFunctions-RunOperation).

Para chamar outra operação no mesmo projeto, simplesmente arraste-a para o *script*. A função completa é criada automaticamente:

```
RunOperation("<TAG>operation:Operation 2</TAG>");
```

Para chamar uma operação em outro projeto, descubra o GUID da operação executando um *script* simples nela (usando [testagem de *scripts*](https://success.jitterbit.com/display/CS/Script+Testing?showLanguage=pt_BR)) que use o caminho de referência da operação para exibir o GUID da operação:

```
<trans>"<TAG>operation:Example Operation</TAG>";</trans>
```

(Quando você tiver o GUID da operação, o *script* pode ser removido). O resultado da [*testagem de script*](https://success.jitterbit.com/display/CS/Script+Testing?showLanguage=pt_BR) é similar a `op.52c3eaa8-bc45-491f-b77f-cfeff994cf31`.

Você pode então usá-lo com a função [RunOperation](https://success.jitterbit.com/display/CS/General+Functions?showLanguage=pt_BR#GeneralFunctions-RunOperation) na forma `op.<GUID>` onde `<GUID>` é o GUID da operação do outro projeto:

```
RunOperation("op.52c3eaa8-bc45-491f-b77f-cfeff994cf31");
```

Para chamar uma operação do Design Studio a partir do Cloud Studio, passe o parâmetro `operationId` para a função no formato `op.<GUID>` onde `<GUID>` é o GUID da operação do Design Studio. Esta informação pode ser descoberta dentro do Design Studio conforme explicado no artigo Chamando uma Operação de uma Linha de Comando, como por exemplo:

```
RunOperation("op.52c3eaa8-bc45-491f-b77f-cfeff994cf31");
```

Para chamar uma operação do Cloud Studio a partir do Design Studio, você precisa dos nomes do projeto e da operação. As operações do Cloud Studio, uma vez que seus projetos são implantados, ficam disponíveis para ser chamadas por projetos do Design Studio por projeto e por nome de operação. Veja a função [`RunOperationFromProject`](https://success.jitterbit.com/display/DOC/General+Functions?showLanguage=pt_BR#GeneralFunctions-RunOperationFromProject) do Design Studio:

```
RunOperationFromProject("<TAG>Projects/MyCloudStudioProject/Operations/MyCloudStudioOperation</TAG>");
```

### Usando uma Linha de Comando de um Agente

As operações também podem ser chamadas de uma linha de comando em um agente no ambiente onde o projeto está implantado. Veja o artigo [Chamando uma Operação de uma Linha de Comando](https://success.jitterbit.com/display/DOC/Calling+an+Operation+from+a+Command+Line?showLanguage=pt_BR) para saber mais detalhes.

### Usando um Gatilho de API

Para chamar a operação de uma aplicação externa, use o [API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR) para configurar uma API Customizada Jitterbit e atribua a operação para ser acionada mediante solicitação. Para saber mais informações, consulte a documentação do [API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR).

### Usando uma Agenda

Para executar a operação automaticamente mediante uma agenda, você deve primeiro configurar uma agenda e depois aplicá-la a uma operação. As agendas podem ser criadas e aplicadas diretamente no Cloud Studio conforme a descrição abaixo, ou então podem ser criadas e aplicadas a partir da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Depois que uma agenda é aplicada a uma operação, ela também pode ser habilitada ou desabilitada a partir da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR). Esta funcionalidade só está disponível no Management Console (não no Cloud Studio).

</div>

</div>

As agendas são adicionadas a partir da aba **Schedules** (Agendas) das configurações de operação. A opção **Settings** (Configurações) é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **Settings** (Configurações), a tela de configurações de operação abre na aba **Schedules** (Agendas). Para ver informações de configurações detalhadas, veja [Agendas de Operações](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR). Para criar uma agenda, primeiro use o link que diz **Create New Schedule** (Criar Nova Agenda). Uma vez que uma agenda é criada, selecione-a do menu *dropdown* **Schedule** (Agenda) e clique em **Assign** (Atribuir) para aplicá-lo a uma operação.

Para editar uma agenda existente que já esteja atribuída a uma operação, clique no ícone da agenda <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/schedules.png" class="confluence-embedded-image confluence-external-resource" /></span> no canto superior direito da operação para exibir a aba **Schedules** (Agendas) das configurações, onde você pode editar ou deletar a agenda.


## Selecionando Agendas e Variáveis de Projeto

Caso haja variáveis de projeto ou agendas sendo implantadas que já tenham sido implantadas na nuvem do Harmony, uma tela mostrará a você opções para selecionar quais valores usar. Isto permite que você mantenha ou substitua valores definidos fora do Cloud Studio, como por exemplo na página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_variable_operation-schedule_schedule.png" class="confluence-embedded-image confluence-external-resource" /></span>

Todas as categorias, de variáveis, agendas de operação e agendas, são cobertas abaixo. Quando você tiver feito as suas seleções, clique em **Deploy** (Implantar) para continuar com a implantação ou implantação configurável conforme definido, ou em **Cancel** (Cancelar) para voltar à tela anterior sem implantar nada.

### Variáveis

Esta tabela inclui [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) que tenham um valor ou descrição diferentes daqueles já implantados na nuvem do Harmony:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_variable.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Select** (Selecionar): Quando é selecionada, esta caixa de seleção é usada para alternar entre as seleções na coluna **Version** (Versão). Quando é desmarcada, a opção escolhida no menu *dropdown* não tem efeito nenhum sobre a tabela. As seguintes opções estão disponíveis no *dropdown*:

  - **All Updates Values** (Todos os Valores Atualizados): Quando tanto a caixa de seleção quanto esta opção estão marcadas, todas as seleções na coluna **Version** (Versão) são trocadas para **Update** (Atualizar).

  - **All Deployed Values** (Todos os Valores Implantados): Quando tanto a caixa de seleção quanto esta opção estão marcadas, todas as seleções na coluna **Version** (Versão) são trocadas para **Deployed** (Implantada).

- **Popout** (Aumentar): Clique no ícone de aumento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar apenas a tabela de variáveis, escondendo todas as agendas de operação e agendas. Depois de abrir esta visualização, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar à tela completa.

- **Name** (Nome): Os nomes de toda variável de projeto que tiver um valor ou descrição diferente dos que já estão implantados na nuvem do Harmony são listados.

  Isto *não inclui* variáveis de projeto que já estejam implantadas mas que tenham o mesmo valor e descrição no projeto do Cloud Studio, ou variáveis de projeto que estão apenas dentro do projeto do Cloud Studio e não foram implantadas ainda.

  <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

  <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **DICA**: Uma variável de projeto pode já ter sido implantada na nuvem do Harmony caso você já tenha implantado o projeto antes ou se você editou a variável do projeto por meio da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

  </div>

  </div>

- **Version** (Versão): Selecione entre as duas versões da variável de projeto:

  - **Update** (Atualizar): Use o valor e a descrição da variável de projeto que estão presentes no projeto do Cloud Studio. Isto substitui o valor e a descrição atualmente implantadas na nuvem do Harmony. Após a implantação, o valor e a descrição da variável de projeto no Cloud Studio e na nuvem do Harmony estarão em sincronia.

  - **Deployed** (Implantada): Use o valor e a descrição da variável de projeto que estão atualmente implantados na nuvem do Harmony.

    <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **AVISO**: Uma vez implantados, o valor e a descrição da variável de projeto no Cloud Studio não serão atualizados. Para continuar usando a versão implantada na nuvem do Harmony, você terá que fazer esta seleção toda vez que implantar o projeto do Cloud Studio, ou então você pode atualizar a variável de projeto no Cloud Studio para ficar igual à que está implantada na nuvem do Harmony para impedir que ela apareça nesta tela.

    </div>

    </div>

- **Value / Description** (Valor / Descrição): O valor da variável de projeto é listado. Se o valor estiver configurado para ser escondido na interface do usuário, asteriscos que escondem o valor são mostrados. Detalhes adicionais podem ser visualizados pairando o mouse sobre a célula:

  - **Value** (Valor): O valor da variável de projeto é listado. Se o valor estiver configurado para ser escondido na interface do usuário, asteriscos que escondem o valor são mostrados.

  - **Description** (Descrição): A descrição da variável de projeto é listada.

- **Updated By** (Atualizada Por): O nome de usuário do Jitterbit Harmony do usuário que fez a última atualização do componente variável de projeto é listado. A atualização pode ter sido feita no Cloud Studio ou no Management Console.

- **Updated On** (Atualizada Em): A data e a hora em que o componente variável de projeto foi atualizado pela última vez, reportadas no fuso horário do seu navegador local.

### Agendas de Operação

Esta tabela inclui todas as [operações](https://success.jitterbit.com/display/CS/Operations?showLanguage=pt_BR) que têm uma diferença entre as agendas aplicadas comparadas com aquelas já implantadas na nuvem do Harmony:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_operation-schedule.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Select** (Selecionar): Quando é selecionada, esta caixa de seleção é usada para alternar entre as seleções na coluna **Version** (Versão). Quando é desmarcada, a opção escolhida no menu *dropdown* não tem efeito nenhum sobre a tabela. As seguintes opções estão disponíveis no *dropdown*:

  - **All Updates Values** (Todos os Valores Atualizados): Quando tanto a caixa de seleção quanto esta opção estão marcadas, todas as seleções na coluna **Version** (Versão) são trocadas para **Update** (Atualizar).

  - **All Deployed Values** (Todos os Valores Implantados): Quando tanto a caixa de seleção quanto esta opção estão marcadas, todas as seleções na coluna **Version** (Versão) são trocadas para **Deployed** (Implantada).

- **Popout** (Aumentar): Clique no ícone de aumento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar apenas a tabela de agendas de operação, escondendo todas as variáveis e agendas. Depois de abrir esta visualização, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar à tela completa.

- **Name** (Nome): Os nomes de toda operação que tiver uma diferença entre as agendas aplicadas quando comparada àquelas já implantadas na nuvem do Harmony são listadas.

  Isto *não inclui* operações que tenham agendas aplicadas que já estão implantadas mas são iguais no projeto do Cloud Studio, ou agendas aplicadas que estão apenas dentro do projeto do Cloud Studio e não foram implantadas ainda.

  Isto *não leva em consideração* se a agenda foi habilitada ou desabilitada no Management Console, visto que esta configuração não pode ser alterada no Cloud Studio.

  <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

  <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **DICA**: Uma agenda aplicada a uma operação pode já ter sido implantada na nuvem do Harmony caso você já tenha implantado o projeto antes ou se você aplicou ou removeu uma agenda de uma operação por meio da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

  </div>

  </div>

- **Version** (Versão): Selecione entre as duas versões da operação que tem a agenda aplicada:

  - **Update** (Atualizar): Use a agenda que está aplicada à operação presente no projeto do Cloud Studio. Isto substitui a configuração de agenda aplicada atualmente implantada na nuvem do Harmony. Após a implantação, a agenda aplicada no Cloud Studio e na nuvem do Harmony estarão em sincronia.

  - **Deployed** (Implantada): Use a agenda que está aplicada à operação que está atualmente implantada na nuvem do Harmony.

    <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **AVISO**: Uma vez implantada, a operação à qual a agenda está aplicada no Cloud Studio não será atualizada. Para continuar usando a versão implantada na nuvem do Harmony, você terá que fazer esta seleção toda vez que implantar o projeto do Cloud Studio, ou então você pode atualizar a agenda aplicada no Cloud Studio para ficar igual à que está implantada na nuvem do Harmony para impedir que ela apareça nesta tela.

    </div>

    </div>

- **Schedule Name** (Nome da Agenda): O nome da agenda aplicada à operação é listado. Se a operação não tiver uma agenda aplicada, esta célula estará vazia. Detalhes adicionais podem ser visualizados pairando o mouse sobre a célula:

  - **Name** (Nome): O nome da agenda aplicada à operação.

  - **Occurs** (Ocorre): Os dias nos quais a agenda está configurada para executar.

  - **Frequency** (Frequência): Os horários nos quais a agenda está configurada para executar. O fuso horário é aquele do agente executando a operação.

  - **Start Date** (Data de Início): A data na qual a agenda está configurada para iniciar.

  - **End Date** (Data de Término): A data na qual a agenda está configurada para terminar.

- **Updated By** (Atualizada Por): O nome de usuário do Jitterbit Harmony do usuário que fez a última atualização da agenda aplicada. A atualização pode ter sido feita no Cloud Studio ou no Management Console.

- **Updated On** (Atualizada Em): A data e a hora em que a agenda aplicada foi atualizada pela última vez, reportadas no fuso horário do seu navegador local.

### Agendas

Esta tabela inclui todas as agendas de operação que tenham uma configuração diferente daquelas já implantadas na nuvem do Harmony. As agendas nesta categoria são listadas independentemente de já terem sido aplicadas a qualquer operação:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_schedule.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Select** (Selecionar): Quando é selecionada, esta caixa de seleção é usada para alternar entre as seleções na coluna **Version** (Versão). Quando é desmarcada, a opção escolhida no menu *dropdown* não tem efeito nenhum sobre a tabela. As seguintes opções estão disponíveis no *dropdown*:

  - **All Updates Values** (Todos os Valores Atualizados): Quando tanto a caixa de seleção quanto esta opção estão marcadas, todas as seleções na coluna **Version** (Versão) são trocadas para **Update** (Atualizar).

  - **All Deployed Values** (Todos os Valores Implantados): Quando tanto a caixa de seleção quanto esta opção estão marcadas, todas as seleções na coluna **Version** (Versão) são trocadas para **Deployed** (Implantada).

- **Popout** (Aumentar): Clique no ícone de aumento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar apenas a tabela de agendas, escondendo todas as variáveis e agendas de operação. Depois de abrir esta visualização, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar à tela completa.

- **Name** (Nome): Os nomes de toda agenda que tiver uma configuração diferente quando comparada àquelas já implantadas na nuvem do Harmony são listados. As agendas nesta categoria são listadas independentemente de já terem sido aplicadas a uma operação.

  Isto *não inclui* agendas que já estão implantadas mas têm as mesmas configurações no projeto do Cloud Studio, ou agendas que estão apenas dentro do projeto do Cloud Studio e não foram implantadas ainda.

  <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

  <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **DICA**: Uma agenda pode já ter sido implantada na nuvem do Harmony caso você já tenha implantado o projeto antes ou se você criou, editou ou deletou uma agenda por meio da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

  </div>

  </div>

- **Version** (Versão): Selecione entre as duas versões da agenda:

  - **Update** (Atualizar): Use a configuração de agenda presente no projeto do Cloud Studio. Isto substitui a configuração atualmente implantada na nuvem do Harmony. Após a implantação, a configuração de agenda no Cloud Studio e na nuvem do Harmony estarão em sincronia.

  - **Deployed** (Implantada): Use a configuração de agenda que está atualmente implantada na nuvem do Harmony.

    <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **AVISO**: Uma vez implantada, a configuração de agenda no Cloud Studio não será atualizada. Para continuar usando a versão implantada na nuvem do Harmony, você terá que fazer esta seleção toda vez que implantar o projeto do Cloud Studio, ou então você pode atualizar a configuração de agenda no Cloud Studio para ficar igual à que está implantada na nuvem do Harmony para impedir que ela apareça nesta tela.

    </div>

    </div>

- **Value** (Valor): Um resumo da configuração da agenda é listado. Detalhes adicionais podem ser visualizados pairando o mouse sobre a célula:

  - **Name** (Nome): O nome da agenda.

  - **Occurs** (Ocorre): Os dias nos quais a agenda está configurada para executar.

  - **Frequency** (Frequência): Os horários nos quais a agenda está configurada para executar. O fuso horário é aquele do agente executando a operação.

  - **Start Date** (Data de Início): A data na qual a agenda está configurada para iniciar.

  - **End Date** (Data de Término): A data na qual a agenda está configurada para terminar.

- **Updated By** (Atualizada Por): O nome de usuário do Jitterbit Harmony do usuário que fez a última atualização da agenda. A atualização pode ter sido feita no Cloud Studio ou no Management Console.

- **Updated On** (Atualizada Em): A data e a hora em que a agenda foi atualizada pela última vez, reportadas no fuso horário do seu navegador local.


## Adicionando *Tags* e Comentários

Os requisitos de implantação podem ser configurados para cada projeto durante a [criação e configuração do projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR).

Caso as configurações de implantação a nível de projeto tenham sido configuradas de modo a exigir uma *tag* ou comentário na hora da implantação, uma caixa de diálogo será mostrada para inserir a *tag* ou comentário exigido, ou ambos:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/deploy-requirements.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Tag**: Coloque uma *tag* para ser usada para etiquetar o evento de implantação. A *tag* será mostrada como etiqueta no evento de implantação e registrada nos detalhes de implantação acessíveis no [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR). Colocar uma *tag* única é recomendado mas não exigido.

- **Comment** (Comentário): Coloque um comentário para ser usado para descrever o evento de implantação. O comentário será registrado nos detalhes de implantação acessíveis a partir do [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR).

- **Add Comment and Tag** (Adicionar Comentário e *Tag*): Clique para adicionar a *tag*, o comentário, ou ambos, e continuar com a implantação ou implantação configurável.

- **Cancel** (Cancelar): Clique para fechar a caixa de diálogo e voltar para a tela anterior sem implantar nada.
