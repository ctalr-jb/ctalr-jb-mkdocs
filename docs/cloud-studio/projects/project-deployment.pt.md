[//]: # (Implantação de Projetos)
[//]: # (This is a translation of Version 19, published on February 16, 2022.)

## Introdução

Esta página descreve como implantar projetos ou componentes de projeto selecionados na nuvem do Jitterbit Harmony. Quando todos os componentes dos quais uma operação depende são implantados, ela pode ser executada (veja [Implantação e Execução de Operações](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR)).


## Implantando

Há duas opções para a implantação de um projeto; implantar diretamente e configurar uma implantação:

-   **Deploy** (Implantação): Esta opção refere-se à implantação direta de um projeto inteiro. Selecionar esta opção implanta imediatamente o projeto ou relata os erros de validação que impediram a implantação.

-   **Configurable Deploy** (Implantação Configurável): Esta opção refere-se à implantação de componentes de projeto selecionados. Selecionar esta opção abre uma tela de configuração de implantação onde você pode escolher quais componentes de projeto implantar.

Com ambas as opções, telas adicionais podem ser exibidas em certas circunstâncias:

-   [**Selecionando Agendas e Variáveis de Projeto**](https://success.jitterbit.com/display/CS/Project+Deployment?showLanguage=pt_BR#ProjectDeployment-selecting-schedules-and-project-variables): Se houver variáveis de projeto ou agendas sendo implantadas que já tenham sido implantadas antes na nuvem do Harmony, uma tela te dá opções para selecionar quais valores usar.

-   [**Adicionando** ***Tags*** **e Comentários**](https://success.jitterbit.com/display/CS/Project+Deployment?showLanguage=pt_BR#ProjectDeployment-deploy-requirements): Se as configurações de implantação a nível de projeto tiverem sido definidas de modo a exigir uma *tag* e/ou um comentário na hora da implantação, uma caixa de diálogo será exibida para que você insira a *tag* e/ou o comentário que é exigido.

Você pode continuar trabalhando durante uma implantação. Mensagens informativas no canto superior direito da tela indicam quando uma implantação está em andamento e quando uma implantação foi terminada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/project-deploy-in-progress.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/project-deploy-in-progress.png" /></span>

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/project-successful-deploy.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/project-successful-deploy.png" /></span>

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Ao renomear um projeto que foi implantado anteriormente, o novo nome do projeto é **automaticamente** implantado e atualizado no Jitterbit Harmony. Nenhuma outra parte do projeto além do nome é implantada automaticamente desta forma.

</div>

</div>

### Implantação

A opção **Deploy** (Implantar), que implanta um projeto inteiro, é acessível a partir dos seguintes locais:

-   A barra de ferramentas de projeto (veja [Menu de Ações de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR#ProjectToolbar-project-actions-menu) em [Barra de Ferramentas de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR)).

-   O quadro de design (veja [Menu de Ações de Implantação/Migração](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-deploy-migrate-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Quando você seleciona **Deploy**, imediatamente ocorre uma tentativa de implantação do projeto inteiro. Para que a implantação tenha sucesso, todos os workflows, operações e componentes usados como parte de uma operação ou em suporte a uma operação no projeto devem ser válidos. Por exemplo, componentes usados das seguintes formas devem ser válidos:

-   Um componente usado diretamente como etapa da operação, tal como uma atividade, um *transformation* ou um *script*.

-   Uma conexão da qual uma atividade usada na operação dependa.

-   Um componente chamado por um *script* na operação.

Qualquer componente que *não* faça parte da operação será implantado *somente* se a configuração dele estiver completa. Se a configuração de tal componente estiver incompleta, ele será saltado pela implantação.

Se qualquer workflow, operação ou componente usado como parte da operação for inválido, o(s) erro(s) de validação específico(s) é(são) mostrado(s) numa caixa de diálogo. Para consultar a documentação de cada erro individual e como resolvê-los, veja [Validade de Workflows](https://success.jitterbit.com/display/CS/Workflow+Validity?showLanguage=pt_BR), [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR) ou [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR), respectivamente.

### Implantação Configurável

A opção **Configurable Deploy** (Implantação Configurável) para configurar uma implantação para todos os componentes do projeto é acessível a partir dos seguintes locais:

-   A barra de ferramentas de projeto (veja [Menu de Ações de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR#ProjectToolbar-project-actions-menu) em [Barra de Ferramentas de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR)).

-   O design canvas (veja [Menu de Ações de Implantação/Migração](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-deploy-migrate-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Além disso, a opção da implantação configurável está disponível em componentes de projeto individuais (veja [Implantação de Componentes](https://success.jitterbit.com/display/CS/Component+Deployment?showLanguage=pt_BR)).

Quando você seleciona esta opção, uma tela de configuração de implantação abre onde você pode escolher quais componentes de projeto implantar:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_project.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_project.png" /></span>

Por padrão, nenhum componente de projeto é selecionado. Você deve selecionar pelo menos um componente de projeto para habilitar o botão **Deploy** (Implantar):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_button.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_button.png" /></span>

Quando você seleciona um componente de projeto, todos os outros componentes de projeto dos quais ele depende também são selecionados. Componentes que são dependências de outros componentes selecionados não podem ser desmarcados, já que a não implantação destes itens faria com que o componente que tem a dependência se tornasse inválido.

Para esconder ou expandir workflows, operações, e passos de operação, use os triângulos de revelação <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/down-arrow_4.png" class="confluence-embedded-image confluence-external-resource" /></span> <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/right-arrow_4.png" class="confluence-embedded-image confluence-external-resource" /></span> exibidos à esquerda do nome do componente.

Os nomes de componentes inválidos aparecem na cor vermelha e em itálico. Além disso, os nomes de componentes que não são usados diretamente em um workflow são precedidos por um til \~, como demonstrado na agenda abaixo:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_components_invalid.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_components_invalid.png" /></span>

Quando todos os componentes de projeto desejados que você queira implantar estiverem selecionados, clique no botão **Deploy** (Implantar).

Se qualquer um dos componentes selecionados for inválido, o(s) erro(s) de validação específico(s) aparece(m) numa caixa de diálogo. Para ver a documentação de cada erro e como resolvê-lo, consulte [Validade de Workflows](https://success.jitterbit.com/display/CS/Workflow+Validity?showLanguage=pt_BR), [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR), ou [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR), respectivamente.


## Selecionando Agendas e Variáveis de Projeto

Se houver alguma variável de projeto ou agenda sendo implantada que já tenha sido implantada na nuvem do Harmony, uma tela oferece opções para selecionar quais valores usar. Isso permite que você mantenha ou altere valores definidos fora do Cloud Studio, como por exemplo na página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_variable_operation-schedule_schedule.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_variable_operation-schedule_schedule.png" /></span>

Todas as categorias, de variáveis, agendas de operação, e agendas, são cobertas abaixo. Quando você tiver feito as suas seleções, clique em **Deploy** (Implantar) para prosseguir com a implantação ou implantação configurável conforme definido antes, ou em **Cancel** (Cancelar) para voltar à tela anterior sem implantar.

### Variáveis

Esta tabela inclui quaisquer [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) que tenham um valor ou descrição diferentes daqueles já implantados na nuvem do Harmony:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_variable.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_variable.png" /></span>

-   **Select** (Selecionar): Quando marcada, esta caixa de seleção é usada para alternar entre as seleções na coluna **Version** (Versão). Quando desmarcada, a opção selecionada no menu *dropdown* não tem efeito sobre a tabela. As opções a seguir estão disponíveis no *dropdown*:

    -   **All Updated Values** (Todos os Valores Atualizados): Quando tanto a caixa de seleção quanto esta opção estão selecionadas, todas as seleções na coluna **Version** são alteradas para **Update** (Atualizar).

    -   **All Deployed Values** (Todos os Valores Implantados): Quando tanto a caixa de seleção quanto esta opção estão selecionadas, todas as seleções na coluna **Version** são alteradas para **Deployed** (Implantada).

-   **Popout** (Aumentar): Clique no ícone de aumentar <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar apenas a tabela de variáveis, escondendo todas as agendas de operação e agendas. Depois de abrir esta visualização, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar à tela cheia.

-   **Name** (Nome): Os nomes de quaisquer variáveis de projeto que tenham um valor ou descrição diferentes daquelas já implantadas na nuvem do Harmony são listados.

    Isto *não inclui* variáveis de projeto que já estejam implantadas mas que tenham o mesmo valor e descrição que no projeto do Cloud Studio, ou variáveis de projeto que estão apenas dentro do projeto do Cloud Studio e não foram implantadas ainda.

    <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **DICA**: Uma variável de projeto pode já ter sido implantada na nuvem do Harmony se você tiver implantado o projeto antes ou se tiver editado a variável de projeto através da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

    </div>

    </div>

-   **Version** (Versão): Selecione entre as duas versões da variável de projeto:

    -   **Update** (Atualizar): Use o valor e a descrição da variável de projeto que estão presentes no projeto do Cloud Studio. Isto vai substituir o valor e a descrição atualmente implantadas na nuvem do Harmony. Uma vez implantada, o valor da variável de projeto e sua descrição no Cloud Studio e na nuvem do Harmony estarão em sincronia.

    -   **Deployed** (Implantada): Use o valor e a descrição da variável de projeto que estão atualmente implantados na nuvem do Harmony.

        <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **ALERTA**: Uma vez implantada, o valor da variável de projeto e sua descrição no Cloud Studio não serão atualizados. Para continuar usando a versão implantada na nuvem do Harmony, você precisará fazer esta seleção cada vez que você implantar o projeto no Cloud Studio, ou você pode atualizar a variável de projeto no Cloud Studio para combinar com a que está implantada na nuvem do Harmony para impedi-la de aparecer nesta tela.

        </div>

        </div>

-   **Value / Description** (Valor / Descrição): O valor da variável de projeto é listado. Se o valor estiver configurado para estar escondido na interface de usuário, asteriscos que escondem o valor são exibidos. Detalhes adicionais podem ser vistos quando se paira o mouse sobre a célula:

    -   **Value** (Valor): O valor da variável de projeto é listado. Se o valor estiver configurado para estar escondido na interface de usuário, asteriscos que escondem o valor são exibidos.

    -   **Description** (Descrição): A descrição da variável de projeto é listada.

-   **Updated By** (Atualizada Por): O nome de usuário do Jitterbit Harmony do último usuário que atualizou o componente variável de projeto é listado. A atualização pode ter sido feita no Cloud Studio ou no Management Console.

-   **Updated On** (Atualizada Em): A data e a hora em que o componente variável de projeto foi atualizado pela última vez, adaptadas ao fuso horário do seu navegador.

### Agendas de Operação

Esta tabela inclui quaisquer [operações](https://success.jitterbit.com/display/CS/Operations?showLanguage=pt_BR) que tenham uma diferença em agendas aplicadas comparadas com aquelas já implantadas na nuvem do Harmony:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_operation-schedule.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_operation-schedule.png" /></span>

-   **Select** (Selecionar): Quando está marcada, esta caixa de seleção é usada para alternar entre as seleções na coluna **Version** (Versão). Quando ela é desmarcada, a opção selecionada no menu *dropdown* não tem nenhum efeito sobre a tabela. As seguintes opções estão disponíveis no *dropdown*:

    -   **All Updated Values** (Todos os Valores Atualizados): Quando tanto a caixa de seleção quanto esta opção estão selecionadas, todas as seleções na coluna **Version** são trocadas para **Update** (Atualizar).

    -   **All Deployed Values** (Todos os Valores Implantados): Quando tanto a caixa de seleção quanto esta opção estão selecionadas, todas as seleções na coluna **Version** são trocadas para **Deployed** (Implantada).

-   **Popout** (Aumentar): Clique no ícone de aumentar <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar apenas a tabela de agendas de operação, escondendo as variáveis e as agendas. Depois de abrir esta visualização, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar para a tela cheia.

-   **Name** (Nome): Os nomes de quaisquer operações que tenham uma diferença nas agendas aplicadas quando comparadas com aquelas já implantadas na nuvem do Harmony são listadas.

    Isto *não inclui* operações que tenham agendas aplicadas que já estão implantadas mas são iguais no projeto do Cloud Studio, ou agendas aplicadas que estão apenas dentro do projeto do Cloud Studio e não foram implantadas ainda.

    Isto *não leva em consideração* se a agenda foi habilitada ou não no Management Console, já que essa configuração não pode ser alterada no Cloud Studio.

    <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **DICA**: Uma agenda aplicada numa operação pode já ter sido implantada na nuvem do Harmony se você tiver implantado o projeto antes ou se você aplicou ou removeu uma agenda de uma operação na página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

    </div>

    </div>

-   **Version** (Versão): Selecione entre as duas versões da operação que tem uma agenda aplicada:

    -   **Update** (Atualizar): Use a agenda que está aplicada na operação no projeto do Cloud Studio. Isto vai substituir a configuração de agenda aplicada que está atualmente implantada na nuvem do Harmony. Uma vez implantada, as agendas aplicadas no Cloud Studio e na nuvem do Harmony estarão em sincronia.

    -   **Deployed** (Implantada): Use a agenda que está aplicada na operação que está atualmente implantada na nuvem do Harmony.

        <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **ALERTA**: Uma vez implantada, a operação à qual a agenda está aplicada no Cloud Studio não é atualizada. Para continuar usando a versão implantada na nuvem do Harmony, você precisará fazer esta seleção cada vez que implantar o projeto no Cloud Studio, ou você pode atualizar a agenda aplicada no Cloud Studio para ser igual à que está implantada na nuvem do Harmony para impedi-la de aparecer nesta tela.

        </div>

        </div>

-   **Schedule Name** (Nome da Agenda): O nome da agenda aplicada à operação é listado. Se a operação não tiver uma agenda aplicada, esta célula estará vazia. Detalhes adicionais podem ser vistos quando se paira o *mouse* sobre a célula:

    -   **Name** (Nome): O nome da agenda aplicada à operação.

    -   **Occurs** (Ocorre): Os dias nos quais a agenda está configurada para executar.

    -   **Frequency** (Frequência): As horas em que a agenda está configurada para executar. O fuso horário é o do agente que está executando a operação.

    -   **Start Date** (Data de Início): A data em que a agenda está configurada para começar.

    -   **End Date** (Data de Término): A data em que a agenda está configurada para terminar.

-   **Updated By** (Atualizada Por): O nome de usuário do Jitterbit Harmony do usuário que fez a última atualização na agenda aplicada. A atualização pode ter sido feita no Cloud Studio ou no Management Console.

-   **Updated On** (Atualizada Em): A data e a hora em que a agenda aplicada foi atualizada pela última vez, adaptadas ao fuso horário do seu navegador.

### Agendas

Esta tabela inclui quaisquer [agendas de operação](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR) que tenham uma configuração diferente daquelas já implantadas na nuvem do Harmony. As agendas nesta categoria são listadas independentemente de estarem aplicadas a uma operação:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/deploy_schedule.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/deploy_schedule.png" /></span>

-   **Select** (Selecionar): Quando está marcada, esta caixa de seleção é usada para alternar entre as opções na coluna **Version** (Versão). Quando está desmarcada, a opção selecionada no menu *dropdown* não tem efeito nenhum sobre a tabela. As seguintes opções estão disponíveis no *dropdown*:

    -   **All Updated Values** (Todos os Valores Atualizados): Quando tanto a caixa quanto esta opção estão selecionadas, todas as seleções na coluna **Version** são trocadas para **Update** (Atualizar).

    -   **All Deployed Values** (Todos os Valores Implantados): Quando tanto a caixa quanto esta opção estão selecionadas, todas as seleções na coluna **Version** são trocadas para **Deployed** (Implantada).

-   **Popout** (Aumentar): Clique no ícone de aumentar <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/popout.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar apenas a tabela de agendas, escondendo quaisquer variáveis e agendas de operação. Depois de abrir esta visualização, clique no ícone de retorno <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/return.png" class="confluence-embedded-image confluence-external-resource" /></span> para voltar para a tela cheia.

-   **Name** (Nome): Os nomes de quaisquer agendas que tenham uma configuração diferente daquelas já implantadas na nuvem do Harmony são listadas. As agendas nesta categoria são listadas independentemente de estarem ou não aplicadas a uma operação.

    Isto *não inclui* agendas que já estão implantadas mas que têm a mesma configuração no projeto do Cloud Studio, ou agendas que só estão dentro do projeto do Cloud Studio e não foram implantadas ainda.

    <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **DICA**: Uma agenda pode já ter sido implantada na nuvem do Harmony se você tiver implantado o projeto antes ou se você criou, editou ou deletou uma agenda na página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do Management Console.

    </div>

    </div>

-   **Version** (Versão): Selecione entre as duas versões da agenda:

    -   **Update** (Atualizar): Use a configuração da agenda que está presente no projeto do Cloud Studio. Isto vai substituir a configuração atualmente implantada na nuvem do Harmony. Uma vez implantada, as configurações de agenda no Cloud Studio e na nuvem do Harmony estarão em sincronia.

    -   **Deployed** (Implantada): Use a configuração de agenda que está atualmente implantada na nuvem do Harmony.

        <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **ALERTA**: Uma vez implantada, a configuração de agenda no Cloud Studio não será atualizada. Para continuar usando a versão implantada na nuvem do Harmony, você precisará fazer esta seleção cada vez que implantar o projeto do Cloud Studio, ou você pode atualizar a configuração de agenda no Cloud Studio para ser igual à que está implantada na nuvem do Harmony para impedi-la de aparecer nesta tela.

        </div>

        </div>

-   **Value** (Valor): Um resumo da configuração de agenda é listado. Detalhes adicionais podem ser vistos quando se paira o mouse sobre a célula:

    -   **Name** (Nome): O nome da agenda.

    -   **Occurs** (Ocorre): Os dias nos quais a agenda está configurada para executar.

    -   **Frequency** (Frequência): As horas em que a agenda está configurada para executar. O fuso horário é aquele do agente executando a operação.

    -   **Start Date** (Data de Início): A data em que a agenda está configurada para iniciar.

    -   **End Date** (Data de Término): A data em que a agenda está configurada para terminar.

-   **Updated By** (Atualizada Por): O nome de usuário do Jitterbit Harmony do usuário que fez a última atualização na agenda é listado. A atualização pode ter sido feita no Cloud Studio ou no Management Console.

-   **Updated On** (Atualizada Em): A data e a hora em que a agenda foi atualizada pela última vez, adaptadas ao fuso horário do seu navegador.


## Adicionando *Tags* e Comentários

Os requisitos de implantação podem ser configurados para cada projeto durante a [criação e configuração do projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR).

Se as configurações de implantação a nível de projeto tiverem sido definidas de modo a exigir uma *tag* ou um comentário na hora da implantação, uma caixa de diálogo é apresentada para que se coloque a *tag* ou o comentário exigidos, ou ambos:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/deploy-requirements.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/deploy-requirements.png" /></span>

-   **Tag**: Insira uma *tag* a ser usada para rotular o evento de implantação. A *tag* será mostrada como uma etiqueta ou rótulo no evento de implantação e será registrada nos detalhes de implantação acessíveis no [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR). Inserir uma *tag* única é recomendado mas não exigido.

-   **Comment** (Comentário): Insira um comentário a ser usado para descrever o evento de implantação. O comentário ficará registrado nos detalhes de implantação acessíveis no [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR).

-   **Add Comment and Tag** (Adicionar Comentário e *Tag*): Clique para adicionar a *tag*, o comentário ou ambos e continuar com a implantação ou implantação configurável.

-   **Cancel** (Cancelar): Clique para fechar a caixa de diálogo e voltar para a tela anterior sem implantar.
