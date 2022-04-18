[//]: # (Implantação de Componentes)
[//]: # (This is a translation of Version 18, published on February 16, 2022.)

## Introdução

A implantação de todos os componentes do projeto (de uma vez), bem como de workflows, operações ou *transformations* selecionados é coberta nestas páginas:

-   **Todos os Componentes do Projeto**: [Implantação de Projetos](https://success.jitterbit.com/display/CS/Project+Deployment?showLanguage=pt_BR), para implantar todos os componentes do projeto

-   **Workflows**: [Implantação de Workflows](https://success.jitterbit.com/display/CS/Workflow+Deployment?showLanguage=pt_BR), para implantar workflows selecionados e seus componentes dependentes

-   **Operações**: [Implantação e Execução de Operações](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR), para implantar e executar operações e seus componentes dependentes

-   ***Transformations***: [Modo de Pré-Visualização](https://success.jitterbit.com/display/CS/Preview+Mode?showLanguage=pt_BR), para implantar um *transformation* e seus componentes dependentes para pré-visualizar o *transformation* com dados de amostra

Componentes de projeto tais como atividades, *transformations*, *scripts*, *schemas*, variáveis de projeto, notificações de e-mail e agendas, bem como quaisquer componentes dos quais eles dependam, também podem ser implantados independentemente do resto do projeto. Isto pode ser feito através de uma implantação direta ou de uma implantação configurável, onde você seleciona quais componentes do projeto implantar.

Uma vez que todos os componentes dos quais uma operação depende sejam implantados na nuvem do Harmony, estas operações podem ser executadas (veja [Implantação e Execução de Operações](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR)).


## Implantando

Há duas opções para a implantação de componentes: implantar diretamente ou configurar uma implantação:

-   **Implantação**: Esta opção refere-se à implantação direta de um componente e seus componentes dependentes. Selecionar esta opção implanta imediatamente o componente e todos os componentes dos quais ele depende, ou mostra os erros de validação que impediram a implantação.

-   **Implantação Configurável**: Esta opção refere-se à implantação de componentes de projeto selecionados. Selecionar esta opção abre uma tela de configuração de implantação onde você pode escolher quais componentes de projeto implantar. Quaisquer componentes do projeto dos quais o componente de projeto selecionado dependa são selecionados por padrão.

Com ambas as opções, telas adicionais podem aparecer em certas circunstâncias:

-   [**Selecionando Agendas e Variáveis de Projeto**](https://success.jitterbit.com/display/CS/Component+Deployment?showLanguage=pt_BR#ComponentDeployment-selecting-schedules-and-project-variables): Se houver variáveis ou agendas sendo implantadas que já tenham sido implantadas na nuvem do Harmony, uma tela dá a você opções para selecionar quais valores usar.

-   [**Adicionando** ***Tags*** **e Comentários**](https://success.jitterbit.com/display/CS/Component+Deployment?showLanguage=pt_BR#ComponentDeployment-deploy-requirements): Caso as configurações a nível de projeto tenham sido definidas de modo a exigir uma *tag* e/ou um comentário ao implantar, uma caixa de diálogo aparece para que você insira a *tag* e/ou o comentário exigidos.

Você pode continuar trabalhando durante uma implantação. Mensagens informativas no canto superior direito da tela indicam quando uma implantação está em andamento e quando uma implantação foi concluída:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/component-deploy-in-progress.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/component-deploy-in-progress.png" /></span>

<span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img class="confluence-embedded-image confluence-external-resource" height="84" src="https://docs-source.jitterbit.com/cs/dialog/component-successful-deploy.png" data-image-src="https://docs-source.jitterbit.com/cs/dialog/component-successful-deploy.png"></span>

As opções de implantação para a maioria dos componentes de projeto são acessíveis a partir da aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

Além disso, componentes usados como passos de operação podem ser implantados a partir dos seguintes locais:

-   A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

-   O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

### Implantar

Ao selecionar **Deploy** (Implantar), uma tentativa de implantação ocorre imediatamente para o componente e quaisquer outros componentes dos quais ele dependa. Para que a implantação ocorra com sucesso, todos os componentes dependentes devem ser válidos. Se algum dos componentes dependentes for inválido, o(s) erro(s) de validação específico(s) é(são) mostrado(s) numa caixa de diálogo. Para ver a documentação de cada erro de componente e como resolvê-los, consulte [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR).

### Implantação Configurável

Ao selecionar **Configurable Deploy** (Implantação Configurável), uma tela de configuração de implantação aparece onde você pode escolher quais componentes do projeto implantar:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_components.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_components.png" /></span>

O componente e seus componentes dependentes são selecionados por padrão. Desmarque as caixas de seleção conforme desejar para implantar apenas componentes selecionados do projeto. Componentes que são dependências de outros componentes selecionados não podem ser desmarcados, já que a não-implantação destes itens faria com que o componente que tem a dependência se tornasse inválido.

Para esconder ou expandir workflows, operações e etapas de operação, use os triângulos de revelação <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/down-arrow_4.png" class="confluence-embedded-image confluence-external-resource" /></span><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/right-arrow_4.png" class="confluence-embedded-image confluence-external-resource" /></span> exibidos à esquerda do nome do componente.

Os nomes dos componentes inválidos aparecem na cor vermelha e em itálico. Além disso, os nomes dos componentes que não são usados diretamente num workflow são precedidos por um til \~, conforme demonstrado nesta agenda:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_components_invalid.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_components_invalid.png" /></span>

Quando todos os componentes de projeto desejados que você queira implantar estejam selecionados, clique no botão **Deploy** (Implantar).

Se algum componente selecionado for inválido, o(s) erro(s) de validação específico(s) é(são) mostrado(s) numa caixa de diálogo. Para ver a documentação de cada erro de componente e como resolvê-los, consulte [Validação de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR).


## Selecionando Agendas e Variáveis de Projeto

Se houver alguma variável de projeto ou agenda sendo implantada que já tenha sido implantada na nuvem do Harmony, uma tela exibirá opções para selecionar quais valores usar. Isto permite que você mantenha ou sobrescreva valores definidos fora do Cloud Studio, como por exemplo na página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_variable_operation-schedule_schedule.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_variable_operation-schedule_schedule.png" /></span>

Cada categoria, de variáveis, agendas de operação e agendas, é coberta abaixo. Quando você tiver feito suas escolhas, clique em **Deploy** (Implantar) para continuar com a implantação ou implantação configurável conforme definido, ou em **Cancel** (Cancelar) para voltar à tela anterior sem implantar.

### Variáveis

Esta tabela inclui quaisquer [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) que tenham um valor ou descrição diferentes daqueles já implantados na nuvem do Harmony:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_variable.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_variable.png" /></span>

-   **Select** (Selecionar): Quando é marcada, esta caixa de seleção é usada para alternar entre as opções na coluna **Version** (Versão). Quando é desmarcada, a opção selecionada no menu *dropdown* não tem efeito nenhum sobre a tabela. As seguintes opções estão disponíveis no *dropdown*:

    -   **All Updated Values** (Todos os Valores Atualizados): Quando a caixa e esta opção estão selecionadas, todas as seleções na coluna **Version** são alteradas para **Update** (Atualizar).

    -   **All Deployed Values** (Todos os Valores Implantados): Quando a caixa e esta opção estão selecionadas, todas as seleções na coluna **Version** são alteradas para **Deployed** (Implantada).

-   **Popout** (Aumentar): Clique no ícone de aumento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar apenas a tabela de variáveis, escondendo quaisquer agendas de operação ou agendas. Após abrir esta visualização, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar à tela cheia.

-   **Name** (Nome): Os nomes de quaisquer variáveis de projeto que tenham um valor ou descrição diferentes daqueles que já estão implantados na nuvem do Harmony são listados.

    Isto *não inclui* variáveis de projeto que já estão implantadas mas que têm o mesmo valor e descrição que estão no projeto do Cloud Studio, ou variáveis de projeto que estão apenas dentro do projeto do Cloud Studio e não foram implantadas ainda.

    <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **DICA**: Uma variável de projeto pode já ter sido implantada na nuvem do Harmony caso você já tenha implantado o projeto ou caso você tenha editado a variável de projeto através da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

    </div>

    </div>

-   **Version** (Versão): Selecione entre as duas versões da variável do projeto:

    -   **Update** (Atualizar): Use o valor e a descrição da variável do projeto que está presente no projeto do Cloud Studio. Isto sobrescreve o valor e a descrição que estão atualmente implantados na nuvem do Harmony. Uma vez implantados, o valor e a descrição da variável do projeto no Cloud Studio e na nuvem do Harmony estarão em sincronia.

    -   **Deployed** (Implantada): Use o valor e a descrição da variável do projeto que está atualmente implantada na nuvem do Harmony.

        <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **ALERTA**: Uma vez implantados, o valor e a descrição da variável do projeto no Cloud Studio não serão atualizados. Para continuar usando a versão implantada na nuvem do Harmony, você precisará fazer esta seleção cada vez que implantar o projeto do Cloud Studio, ou você pode atualizar a variável do projeto no Cloud Studio para ser igual à versão que está implantada na nuvem do Harmony para impedi-la de aparecer nesta tela.

        </div>

        </div>

-   **Value / Description** (Valor / Descrição): O valor da variável do projeto é listado. Caso o valor esteja configurado para estar escondido na interface de usuário, asteriscos que escondem o valor são exibidos. Detalhes adicionais podem ser vistos pairando o mouse sobre a célula:

    -   **Value** (Valor): O valor da variável do projeto é listado. Caso o valor esteja configurado para estar escondido na interface de usuário, asteriscos que escondem o valor são exibidos.

    -   **Description** (Descrição): A descrição da variável do projeto é listada.

-   **Updated By** (Atualizada Por): O nome de usuário do Jitterbit Harmony do usuário que fez a última atualização na variável do projeto é listado. A atualização pode ter sido feita no Cloud Studio ou no Management Console.

-   **Updated On** (Atualizada Em): A data e a hora da última atualização na variável do projeto, adaptadas ao fuso horário do seu navegador local.

### Agendas de Operação

Esta tabela inclui quaisquer [operações](https://success.jitterbit.com/display/CS/Operations?showLanguage=pt_BR) que tenham uma diferença nas agendas aplicadas comparadas com aquelas já implantadas na nuvem do Harmony:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_operation-schedule.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_operation-schedule.png" /></span>

-   **Select** (Selecionar): Quando é marcada, esta caixa de seleção é usada para alternar todas as seleções na coluna **Version** (Versão). Quando é desmarcada, a opção selecionada no menu *dropdown* não tem efeito nenhum sobre a tabela. As seguintes opções estão disponíveis no *dropdown*:

    -   **All Updated Values** (Todos os Valores Atualizados): Quando a caixa e esta opção estão selecionadas, todas as seleções na coluna **Version** são alteradas para **Update** (Atualizar).

    -   **All Deployed Values** (Todos os Valores Implantados): Quando a caixa e esta opção estão selecionadas, todas as seleções na coluna **Version** são alteradas para **Deployed** (Implantada).

-   **Popout** (Aumentar): Clique no ícone de aumento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar apenas a tabela de agendas de operação, escondendo quaisquer variáveis ou agendas. Após abrir esta visualização, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar à tela cheia.

-   **Name** (Nome): Os nomes de quaisquer operações que tenham uma diferença nas agendas aplicadas em comparação com aquelas já implantadas na nuvem do Harmony são listados.

    Isto *não inclui* operações que têm agendas aplicadas que já estão implantadas porém são iguais no projeto do Cloud Studio, ou agendas aplicadas que estão apenas dentro do projeto do Cloud Studio e não foram implantadas ainda.

    Isto *não leva em consideração* se a agenda foi habilitada ou desabilitada a partir do Management Console, já que esta é uma configuração que não pode ser alterada a partir do Cloud Studio.

    <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **DICA**: Uma agenda aplicada numa operação pode já ter sido implantada na nuvem do Harmony caso você já tenha implantado o projeto ou caso você tenha aplicado ou removido uma agenda de uma operação através da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

    </div>

    </div>

-   **Version** (Versão): Selecione entre as duas versões da operação que tem a agenda aplicada:

    -   **Update** (Atualizar): Use a agenda aplicada à operação que está presente no projeto do Cloud Studio. Isto sobrescreve a configuração de agenda que está atualmente implantada na nuvem do Harmony. Uma vez implantada, a agenda aplicada no Cloud Studio e na nuvem do Harmony estarão em sincronia.

    -   **Deployed** (Implantada): Use a agenda aplicada à operação que está atualmente implantada na nuvem do Harmony.

        <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **ALERTA**: Uma vez implantada, a operação na qual a agenda está aplicada no Cloud Studio não será atualizada. Para continuar usando a versão implantada na nuvem do Harmony, você precisará fazer esta seleção cada vez que implantar o projeto do Cloud Studio, ou você pode atualizar a agenda aplicada no Cloud Studio para ser igual à versão que está implantada na nuvem do Harmony para impedi-la de aparecer nesta tela.

        </div>

        </div>

-   **Schedule Name** (Nome da Agenda): O nome da agenda aplicada à operação é listado. Caso a operação não tenha uma agenda aplicada, esta célula estará vazia. Detalhes adicionais podem ser vistos pairando o mouse sobre a célula:

    -   **Name** (Nome): O nome da agenda aplicada à operação.

    -   **Occurs** (Ocorre): Os dias nos quais a agenda está configurada para executar.

    -   **Frequency** (Frequência): As horas nas quais a agenda está configurada para executar. O fuso horário é o do agente executando a operação.

    -   **Start Date** (Data de Início): A data na qual a agenda está configurada para começar.

    -   **End Date** (Data de Término): A data na qual a agenda está configurada para terminar.

-   **Updated By** (Atualizada Por): O nome de usuário do Jitterbit Harmony do usuário que fez a última atualização na agenda aplicada é listado. A atualização pode ter sido feita no Cloud Studio ou no Management Console.

-   **Updated On** (Atualizada Em): A data e a hora da última atualização na agenda aplicada, adaptadas ao fuso horário do seu navegador local.

### Agendas

Esta tabela inclui quaisquer [agendas de operação](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR) que tenham uma configuração diferente daquelas já implantadas na nuvem do Harmony. Agendas nesta categoria são listadas independentemente de terem sido aplicadas ou não a alguma operação:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_schedule.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_schedule.png" /></span>

-   **Select** (Selecionar): Quando é marcada, esta caixa de seleção é usada para alternar todas as seleções na coluna **Version** (Versão). Quando é desmarcada, a opção selecionada no menu *dropdown* não tem efeito nenhum sobre a tabela. As seguintes opções estão disponíveis no *dropdown*:

    -   **All Updated Values** (Todos os Valores Disponíveis): Quando a caixa e esta opção estão selecionadas, todas as seleções na coluna **Version** são alteradas para **Update** (Atualizar).

    -   **All Deployed Values** (Todos os Valores Implantados): Quando a caixa e esta opção estão selecionadas, todas as seleções na coluna **Version** são alteradas para **Deployed** (Implantada).

-   **Popout** (Aumentar): Clique no ícone de aumento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar apenas a tabela de agendas, escondendo quaisquer variáveis ou agendas de operação. Após abrir esta visualização, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar à tela cheia.

-   **Name** (Nome): Os nomes de quaisquer agendas que tenham uma configuração diferente daquelas já implantadas na nuvem do Harmony são listadas. Agendas nesta categoria são listadas independentemente de terem sido aplicadas ou não a alguma operação.

    Isto *não inclui* agendas que já estão implantadas mas que têm a mesma configuração no projeto do Cloud Studio, ou agendas que estão apenas dentro do projeto do Cloud Studio e não foram implantadas ainda.

    <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **DICA**: Uma agenda pode já ter sido implantada na nuvem do Harmony caso você já tenha implantado o projeto ou caso você tenha criado, editado ou deletado uma agenda através da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

    </div>

    </div>

-   **Version** (Versão): Selecione entre as duas versões da agenda:

    -   **Update** (Atualizar): Use a configuração de agenda que está presente no projeto do Cloud Studio. Isto sobrescreve a configuração que está atualmente implantada na nuvem do Harmony. Uma vez implantada, a configuração de agenda no Cloud Studio e na nuvem do Harmony estarão em sincronia.

    -   **Deployed** (Implantada): Use a configuração de agenda que está atualmente implantada na nuvem do Harmony.

        <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **ALERTA**: Uma vez implantada, a configuração de agenda no Cloud Studio não será atualizada. Para continuar usando a versão implantada na nuvem do Harmony, você precisará fazer esta seleção cada vez que implantar o projeto do Cloud Studio, ou você pode atualizar a configuração de agenda no Cloud Studio para ser igual à versão que está implantada na nuvem do Harmony para impedi-la de aparecer nesta tela.

        </div>

        </div>

-   **Value** (Valor): Um resumo da configuração da agenda é listado. Detalhes adicionais podem ser vistos pairando o mouse sobre a célula:

    -   **Name** (Nome): O nome da agenda.

    -   **Occurs** (Ocorre): Os dias nos quais a agenda está configurada para executar.

    -   **Frequency** (Frequência): As horas nas quais a agenda está configurada para executar. O fuso horário é o do agente executando a operação.

    -   **Start Date** (Data de Início): A data na qual a agenda está configurada para começar.

    -   **End Date** (Data de Término): A data na qual a agenda está configurada para terminar.

-   **Updated By** (Atualizada Por): O nome de usuário do Jitterbit Harmony do usuário que fez a última atualização na agenda é listado. A atualização pode ter sido feita no Cloud Studio ou no Management Console.

-   **Updated On** (Atualizada Em): A data e a hora da última atualização na agenda, adaptadas ao fuso horário do seu navegador local.


## Adicionando *Tags* e Comentários

Requisitos de implantação podem ser configurados para cada projeto durante a [criação e configuração do projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR).

Caso as configurações de implantação a nível de projeto tenham sido definidas de modo a exigir uma *tag* ou um comentário na hora da implantação, uma caixa de diálogo é mostrada para inserir a *tag* ou o comentário exigidos, ou ambos:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/deploy-requirements.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/deploy-requirements.png" /></span>

-   **Tag**: Coloque uma *tag* para ser usada para rotular o evento de implantação. A *tag* será exibida como um rótulo ou uma etiqueta no evento de implantação e será gravada nos detalhes de implantação acessíveis no [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR). Inserir uma *tag* única é recomendado mas não exigido.

-   **Comment** (Comentário): Insira um comentário a ser usado para descrever o evento de implantação. O comentário será registrado nos detalhes de implantação acessíveis no [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR).

-   **Add Comment and Tag** (Adicionar Comentário e *Tag*): Clique para adicionar a *tag*, o comentário ou ambos, e continuar com a implantação ou implantação configurável.

-   **Cancel** (Cancelar): Clique para fechar a caixa de diálogo e voltar para a tela anterior sem implantar.
