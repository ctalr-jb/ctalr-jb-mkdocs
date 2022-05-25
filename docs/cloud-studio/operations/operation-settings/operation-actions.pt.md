[//]: # (Ações de Operação)
[//]: # (This is a translation of Version 14, published on November 09, 2021.)


## Introdução

Toda operação pode ser configurada com ações a serem tomadas em caso de sucesso ou falha da operação, incluindo a execução de outra operação ou o envio de uma notificação por e-mail. O resultado são operações ou notificações interconectadas que são iniciadas quando certas condições são atendidas. Dizemos que uma operação que é iniciada com base em ações de operação está abaixo da outra operação na cadeia.

## Acessando Ações de Operação

A opção **Settings** (Configurações) para as operações é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Uma vez que a tela de configurações de operação esteja aberta, selecione a aba **Actions** (Ações):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/actions_tab.png" class="confluence-embedded-image confluence-external-resource" /></span>

## Configurando Ações de Operação

Todas as opções disponíveis dentro da aba **Actions** (Ações) das configurações de operação estão descritas abaixo.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/actions_dialog.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Condition** (Condição): Use o primeiro menu *dropdown* para selecionar a condição que deverá dar início à ação. As seguintes condições podem ser colocadas:

  - **On Success** (Em Caso de Sucesso): A ação só é iniciada quando a operação é bem-sucedida.

    <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **DICA**: Você pode forçar uma inicialização de sucesso mesmo que a operação falhe. Esta configuração está disponível na aba **Options** (Opções) das configurações de operação e pode ser útil para preparar partes futuras do projeto sem exigir o sucesso de uma operação dependente (veja [Opções de Operação](https://success.jitterbit.com/display/CS/Operation+Options?showLanguage=pt_BR)).

    </div>

    </div>

  - **On Fail** (Em Caso de Falha): A ação é iniciada quando a operação falha.

  - **On SOAP Fault** (Em Caso de Erro SOAP): A ação é iniciada quando um erro SOAP ocorre. Um erro SOAP é um erro que resulta de um formato de mensagem incorreto, processamento de cabeçalhos ou incompatibilidade. Esta condição é aplicável somente a operações que usam [atividades SOAP](https://success.jitterbit.com/display/CS/SOAP?showLanguage=pt_BR) ou atividades baseadas na Salesforce (usando os conectores [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud?showLanguage=pt_BR) ou [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax?showLanguage=pt_BR)).

- **Action** (Ação): Use o segundo menu *dropdown* para selecionar a ação a ser realizada, com o limite de um de cada tipo de ação para cada condição. As seguintes ações podem ser configuradas:

  - **Run Operation** (Executar Operação): Inicia a operação selecionada no próximo menu *dropdown*, e pode ser usada para conectar ou encadear operações a serem executadas na sequência.

    - **Operation** (Operação): Quando a opção **Run Operation** é selecionada, o terceiro menu *dropdown* exibe as operações disponíveis dentro do projeto, incluindo quaisquer operações que estejam incluídas em outros *workflows* dentro do projeto que já não tenham sido associadas a uma ação.

  - **Send Email Notification** (Enviar Notificação de E-mail): Envia uma notificação de e-mail selecionada no próximo menu *dropdown*.

    - **Email Notification** (Notificação de E-mail): Quando a opção **Send Email Notification** é selecionada, o terceiro menu *dropdown* exibe as notificações de e-mail configuradas dentro do projeto que já não tenham sido associadas a uma ação.

    - **Create New Email Notification** (Criar Nova Notificação de E-mail): Quando a opção **Send Email Notification** é selecionada, um *link* fica disponível para configurar uma nova notificação de e-mail. Documentação sobre a configuração está disponível em [Notificações de E-mail](https://success.jitterbit.com/display/CS/ServiceMax?showLanguage=pt_BR).

- **Add Action** (Adicionar Ação): Para adicionar a ação à operação, tenha certeza de que todos os três menus *dropdown* tenham seleções e daí clique em **Add Action** (Adicionar Ação). A ação então é exibida na tabela abaixo.

- **Remove Action** (Remover Ação): Para remover uma ação de uma operação, clique no ícone de remoção <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_13.png" class="confluence-embedded-image confluence-external-resource" /></span> ao lado do parâmetro dentro da tabela. A ação é removida da tabela.


## Exibição de Conexões no Design Canvas

Quando você adiciona ações de operação, você pode visualmente enxergar as conexões entre os elementos com linhas conectadas no design canvas. Para mais detalhes, veja a seção sobre [Linhas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-lines) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR).
