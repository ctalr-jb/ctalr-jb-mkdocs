[//]: # (Agendas de Operação)
[//]: # (This is a translation of Version 27, published on October 20, 2021.)


## Introdução

Qualquer operação pode ser configurada para ser executada automaticamente mediante a aplicação de uma agenda. As agendas contêm informações sobre quando uma operação será automaticamente ativada. Você pode definir praticamente qualquer tipo de agenda que precisar, por exemplo, todas as sextas-feiras às 17 horas, na última sexta-feira de cada trimestre, ou uma vez por hora em um único dia.

Se um operação executando em uma agenda tiver [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) configuradas, todas as operações abaixo dela na cadeia também são executadas. Caso uma instância previamente agendada de uma operação agendada ainda esteja executando quando chegar a hora da execução pela agenda, a operação será saltada.

As agendas podem ser criadas e aplicadas diretamente no Cloud Studio, conforme descrito nesta página, ou podem ser criadas e aplicadas a partir da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) do [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR) (Console de Gerenciamento), onde você também pode ver uma lista de todas as agendas atribuídas a operações dentro de um projeto, ou habilitar ou desabilitar agendas.

Ao implantar uma agenda que já tenha sido implantada na nuvem do Harmony, você recebe opções para selecionar quais agendas usar. Isto é abordado em [Selecionando Agendas e Variáveis de Projeto](https://success.jitterbit.com/display/CS/Project+Deployment?showLanguage=pt_BR#ProjectDeployment-selecting-schedules-and-project-variables) em [Implantação de Projetos](https://success.jitterbit.com/display/CS/Project+Deployment?showLanguage=pt_BR).

Outras formas de executar operações incluem a execução manual de operações ou o uso de um gatilho de API, conforme descrito em [Implantação e Execução de Operações](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution?showLanguage=pt_BR).


## Criando uma Nova Agenda ou Abrindo uma Agenda Existente

Agendas de operação podem ser acessadas a partir do painel de projeto, das configurações de operação ou do design canvas dependendo se você está criando uma nova agenda ou editando uma agenda existente. Depois de criar uma agenda ou abrir uma agenda existente para editar, veja a seção [Configurando Agendas de Operação](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR#OperationSchedules-configuring-operation-schedules) mais à frente nesta mesma página para aprender a configurar.

Uma nova agenda pode ser criada a partir da aba **Components** do painel de projeto usando a opção **Create New** (Criar Nova) na categoria **Schedules** (Agendas) (veja [Menu de Ações de Categoria](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-category-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)). Novas agendas são criadas com o nome padrão *New Schedule*. Futuras novas agendas com nomes padrão receberão também um número incrementado entre parênteses.

Uma agenda existente pode ser editada a partir da aba **Components** do painel de projeto usando a opção **View/Edit** (Visualizar/Editar) em um componente de agenda (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

Para editar uma agenda existente que já foi atribuída a uma operação, clique no ícone de agenda <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/schedules.png" class="confluence-embedded-image confluence-external-resource" /></span> na barra de ferramentas de operação para exibir a aba **Schedules** (Agendas) das configurações de operação.

A aba **Schedules** (Agendas) das **Settings** (Configurações) de operação pode ser acessada nos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: As edições de agenda fazem efeito sobre todas as operações às quais foram atribuídas.

</div>

</div>


## Configurando Agendas de Operação

Na aba **Schedules** (Agendas) das configurações de operação, agendas existentes que tenham sido criadas no Cloud Studio ou no Management Console (Console de Gerenciamento) podem ser aplicadas às operações. Aqui, você também pode criar novas agendas, editar agendas existentes e desassociar agendas de operações. Cada uma das opções está descrita abaixo.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/schedules_settings.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Condition** (Condição): O primeiro menu *dropdown* já estará mostrando a seleção **On Schedule** (Na Agenda), indicando que a condição que dá início à operação é uma agenda. Nenhuma outra condição pode ser selecionada nesse momento.

- **Schedule** (Agenda): Use este menu *dropdown* para selecionar a agenda existente que você quer aplicar à operação. Caso a agenda que você queira usar não exista ainda, clique no link **Create New Schedule** (Criar Nova Agenda) para criar uma nova agenda. Esta opção está descrita abaixo.

- **Assign** (Atribuir): Clique em **Assign** (Atribuir) para aplicar a agenda selecionada à operação. Note que apenas uma agenda pode ser aplicada a cada operação, e que a agenda atribuída não fará efeito até que o projeto seja implantado.

  Quando uma operação tiver uma agenda atribuída, o campo **Schedule** (Agenda) muda para **Assigned Schedule** (Agenda Atribuída) com os detalhes da agenda atribuída sendo exibidos, e as opções **Assign** (Atribuir) ou **Create New Schedule** (Criar Nova Agenda) são ocultadas. Além disso, um ícone de agenda <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/schedules.png" class="confluence-embedded-image confluence-external-resource" /></span> aparece na operação no design canvas, e quando ele é clicado, a tela de agendas de operação reabre.

  <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

  <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **DICA**: Quando você aplica uma agenda a uma operação, uma boa prática que recomendamos é preparar uma ação de operação do tipo **On Fail** (Em Caso de Falha) para disparar uma notificação de e-mail na operação agendada.

  </div>

  </div>

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/schedules_assigned.png" class="confluence-embedded-image confluence-external-resource" /></span>

  - **Edit** (Editar): Para editar a agenda atribuída, clique no ícone de edição <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/edit_3.png" class="confluence-embedded-image confluence-external-resource" /></span> para abrir a tela de configuração de agenda e fazer as mudanças necessárias. Agendas existentes também podem ser acessadas a partir do [painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane?showLanguage=pt_BR). Na aba **Components**, para editar uma agenda, paire o mouse sobre o nome da agenda, daí clique no ícone do menu de ações <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/actions-menu_9.png" class="confluence-embedded-image confluence-external-resource" /></span> e, no menu, selecione a opção **View/Edit** (Visualizar/Editar).

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Caso a mesma agenda esteja atribuída a outras operações, as edições afetam a agenda de todas as operações às quais ela está atribuída.

    </div>

    </div>

  - **Remove** (Remover): Para desassociar a agenda da operação, clique no ícone de remoção <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/delete_3.png" class="confluence-embedded-image confluence-external-resource" /></span>. Note que a agenda em si não é removida, simplesmente desvinculada da operação.

- **Create New Schedule** (Criar Nova Agenda): Para criar uma nova agenda, clique no link que diz **Create New Schedule** (Criar Nova Agenda). Fazer isto abrirá a tela de configuração de agenda.

  <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

  <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

  <div class="confluence-information-macro-body">

  **NOTA**: A agenda não é criada até depois de você ter configurado e salvo a nova agenda. Depois que a agenda estiver criada, você precisa selecioná-la no menu *dropdown* **Available Schedule** (Agenda Disponível) e clicar na opção **Assign** (Atribuir) para aplicá-la à operação.

  </div>

  </div>

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/operation/schedule_dialog.png" class="confluence-embedded-image confluence-external-resource" /></span>

  - **Schedule Name** (Nome da Agenda): Coloque um nome para a agenda. Você pode querer dar à agenda um nome que faça referência à frequência da agenda ou, caso ela seja usada para uma operação específica, ao propósito da agenda (por exemplo, “Cada 5 Minutos” ou “Sincronização de Contatos”). O nome não deve começar nem terminar com um espaço.

  - **Occurrence** (Ocorrência): Use o menu *dropdown* para selecionar uma das três opções para os dias nos quais a agenda deve dar início à(s) operação(ões) a(s) que foi atribuída:

    - **Daily** (Diariamente): A agenda vai ativar a operação todos os dias, ou a cada poucos dias. Quando esta opção é selecionada, os seguintes campos ficam disponíveis para configurar:

      - **Every \[#\] Day(s)** (A Cada \[#\] Dia(s)): Coloque um número de dia(s) entre cada execução da operação.

    - **Weekly** (Semanalmente): A agenda vai ativar a operação durante um grupo especificado de dias da semana. Quando esta opção é selecionada, os seguintes campos ficam disponíveis para configurar:

      - **Every \[#\] Week(s)** (A Cada \[#\] Semana(s)): Coloque um número de semana(s) entre cada execução da operação.

      - **\[Sun, Mon, Tue, Wed, Thu, Fri, Sat\]** (Dom, Seg, Ter, Qua, Qui, Sex, Sáb): Clique para selecionar o(s) dia(s) da semana nos quais você quer que a operação seja executada. Pelo menos um dia deve ser selecionado.

    - **Monthly** (Mensalmente): A agenda vai ativar a operação em base mensal. Quando esta opção é selecionada, escolha uma das duas opções que ficam disponíveis para configurar:

      - **Day \[#\] of Every \[#\] Month(s)** (No Dia \[#\] de Cada \[#\] Mês(es)): Coloque o dia do mês e o número de mês(es) entre cada execução da operação.

      - **The \[1st, 2nd, 3rd, 4th or Last\] \[Day of Week\] of Every \[#\] Month** (No(a) \[1º, 2º, 3º, 4º ou Último(a)\] \[Dia da Semana\] de Cada \[#\] Mês(es)): Use os menus *dropdown* para selecionar qual dia do mês e coloque o número de mês(es) entre cada execução da operação.

  - **Frequency** (Frequência): Selecione uma de duas opções para as horas nas quais a agenda deve iniciar a operação nos dias em que ela executa:

    - **Occurs Once at \[hh:mm:ss\] \[AM/PM\]** (Ocorre Uma Vez às \[hh:mm:ss\] \[AM/PM\]): A agenda vai ativar a operação somente uma vez na hora determinada. Escolha a hora usando a barra de cima para ajustar a hora ou a de baixo para ajustar os minutos.

    - **Occurs Every \[#\] \[Minute(s)/Hour(s)\] Starting at \[hh:mm:ss\] \[AM/PM\] and Ending at \[hh:mm:ss\] \[AM/PM\]** (Ocorre a Cada \[#\] \[Minuto(s)/Hora(s)\] Começando às \[hh:mm:ss\] \[AM/PM\] e Acabando às \[hh:mm:ss\] \[AM/PM\]): A agenda vai reativar a operação repetidas vezes no período de tempo especificado ao longo do dia. Determine as horas ao longo do dia em que você quer que a operação execute usando a barra de cima para ajustar a hora ou a de baixo para ajustar os minutos.

      <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

      <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

      <div class="confluence-information-macro-body">

      **NOTA**: A questão dos fusos horários é discutida abaixo na seção [Fusos Horários das Operações](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR#OperationSchedules-time-zones).

      </div>

      </div>

  - **Duration** (Duração): Configure as datas de duração da agenda.

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: As datas de início e de término em uma agenda são inclusivas.

    </div>

    </div>

  - **Start Date** (Data de Início): Por padrão, a agenda estará ativa na data atual. Se você quiser que a agenda comece em outro dia, use o selecionador de data/hora para escolher a data de início desejada.

  - **Add End Date** (Adicionar Data de Término): Por padrão, a(s) operação(ões) à(s) qual(is) a agenda está atribuída serão executadas indefinidamente de acordo com a agenda. Se você quiser determinar uma data de término, primeiro clique no link **Add End Date** para adicionar o campo **End Date** (Data de Término). Daí use o selecionador de data/hora para escolher uma data em que você queira que a agenda termine.

  - **Remove End Date** (Remover Data de Término): Esse link só aparece depois que o campo **End Date** (Data de Término) é adicionado. Para remover o campo **End Date**, clique no link **Remove End Date**.

- **Save** (Salvar): Clique para salvar e fechar a configuração da agenda.


## Fusos Horários de Operação

Ao configurar uma agenda, o campo **Frequency** (Frequência) não exibe o fuso horário em que a operação será executada. O fuso horário em que a operação executará depende do agente que está executando a operação, a menos que a configuração **Override Schedule Agent Time Zone** (Substituir Fuso Horário do Agente da Agenda) esteja habilitada nas [políticas da sua organização](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR#Organizations-organization-policies):

- **Agent Time Zone** (Fuso Horário do Agente)

  - **Cloud Agents** (Agents da Nuvem): Todos os Agents da Nuvem estão no fuso horário UTC.

  - **Private Agents**: Os fusos horários dos Private Agents são determinados pelo fuso horário do sistema operacional do Private Agent. É altamente recomendável que todos os agentes em um Private Agent Group estejam executando no mesmo fuso horário, senão as horas em que uma agenda configurada inicia a operação podem se tornar imprevisíveis dependendo do agente específico sendo usado.

- **Override Schedule Agent Time Zone** (Substituir Fuso Horário do Agente da Agenda)

  - Se esta configuração estiver habilitada nas [políticas da sua organização](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR#Organizations-organization-policies), o fuso horário selecionado vai determinar o fuso horário em que todas as agendas atuais e futuras de toda a organização vão executar,


## Menu de Ações de Agenda

Depois que uma agenda é criada, as ações de menu dessa agenda são acessíveis a partir da aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

As seguintes ações de menu estão disponíveis:

<table class="relative-table confluenceTable">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
</colgroup>
<tbody>
<tr class="header header">
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Item do Menu</strong></td>
<td class="highlight-grey confluenceTd" data-highlight-colour="grey"><strong>Descrição</strong></td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-edit.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Visualizar/Editar</em></p>
</div></td>
<td class="confluenceTd"><p>O botão <strong>View/Edit</strong> (Visualizar/Editar) abre a tela de configuração de agenda (veja <a href="https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR?hideelements=false#OperationSchedules-configuring-operation-schedules">Configurando Agendas de Operação</a> mais acima nesta mesma página).</p>
<p><em><strong>NOTA</strong>: Edições feitas às agendas têm efeito sobre todas as operações às quais elas são atribuídas.</em></p></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Recortar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Cut</strong> (Recortar) coloca uma cópia da agenda na sua área de transferência e delete a agenda original do projeto (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR">Reuso de Componentes</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Copiar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Copy</strong> (Copiar) coloca uma cópia da agenda na sua área de transferência (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR">Reuso de Componentes</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Duplicar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Duplicate</strong> (Duplicar) cria uma agenda nova e não-referenciada usando as mesmas configurações do componente original (veja <a href="https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR">Reuso de Componentes</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
height="67" /></span></p>
<p><em>Implantar</em></p>
<p><em>&gt; Implantação</em></p>
<p><em>&gt; Implantação Configurável</em></p>
</div></td>
<td class="confluenceTd"><p>O botão <strong>Deploy</strong> (Implantar) mostra as seguintes ações de menu:</p>
<ul>
<li><strong>Deploy</strong> (Implantação): Implanta a agenda junto com quaisquer componentes dos quais ela dependa (veja <a href="https://success.jitterbit.com/display/CS/Component+Deployment?showLanguage=pt_BR">Implantação de Componentes</a>).</li>
<li><strong>Configurable Deploy</strong> (Implantação Configurável): Abre a tela de implantação, onde você pode selecionar componentes para implantar (veja <a href="https://success.jitterbit.com/display/CS/Component+Deployment?showLanguage=pt_BR">Implantação de Componentes</a>).</li>
</ul></td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Renomear</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Rename</strong> (Renomear) coloca o cursor sobre o nome da agenda para que você faça edições conforme necessário.</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Ver Dependências</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>View Dependencies</strong> (Ver Dependências) altera a visualização no painel de projeto para exibir quaisquer outras partes do projeto das quais a agenda dependa (veja <a href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR">Dependências, Exclusão e Remoção de Componentes</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/add-to-group.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Adicionar ao Grupo</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Add to Group</strong> (Adicionar ao Grupo) abre uma nova caixa de diálogo para criar um novo grupo customizado ou para adicionar a agenda a um grupo existente (veja <a href="https://success.jitterbit.com/display/CS/Component+Groups?showLanguage=pt_BR">Grupos de Componentes</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Deletar</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Delete</strong> (Deletar) exclui permanentemente a agenda (veja <a href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR">Dependências, Exclusão e Remoção de Componentes</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
height="33" /></span></p>
<p><em>Remover</em></p>
</div></td>
<td class="confluenceTd">O botão <strong>Remove</strong> (Remover) não funciona atualmente.</td>
</tr>
</tbody>
</table>


## Usando *Scripts* para Agendar Operações

Se as opções disponíveis na interface de usuário que estão descritas em Configurando Agendas de Operação não atenderem às suas necessidades, você pode criar agendas mais complexas usando *scripts*.

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Se você estiver com a configuração **Override Schedule Agent Time Zone** (Substituir Fuso do Horário do Agente da Agenda) habilitada nas [políticas da sua organização](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR#Organizations-organizations-policies), todos os *scripts* que usam as [funções de data e hora](https://success.jitterbit.com/display/DOC/Date+and+Time+Functions?showLanguage=pt_BR) descritas aqui não serão substituídos com o seu fuso horário selecionado.

</div>

</div>

Como exemplo, um caso de uso comum pode ser criar uma agenda para executar a operação no último dia do mês. Os seguintes passos descrevem este caso de uso:

1. [Crie uma operação](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR) contendo um único [script como componente de projeto](https://success.jitterbit.com/display/CS/Script+Types+and+Creation?showLanguage=pt_BR).

2. Configure o *script* como um Jitterbit Script contendo lógica de *script* que verifique se é o último dia do mês e execute a operação se a condição for verdadeira. Tenha o cuidado de substituir a referência da operação com aquela da operação que você quer executar na agenda.

    <div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeContent panelContent pdl">
    <div><div id="highlighter_877923" class="syntaxhighlighter sh-confluence nogutter  java"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Hint: double-click to select code"><div class="line number1 index0 alt2"><code class="java plain">&lt;trans&gt;</code></div><div class="line number2 index1 alt1"><code class="java keyword">if</code><code class="java plain">(DayOfMonth(LastDayOfMonth(Now()))==DayOfMonth(Now()),</code></div><div class="line number3 index2 alt2"><code class="java plain">RunOperation(</code><code class="java string">"&lt;TAG&gt;operation:Scheduled Operation&lt;/TAG&gt;"</code><code class="java plain">);</code></div><div class="line number4 index3 alt1"><code class="java plain">);</code></div><div class="line number5 index4 alt2"><code class="java plain">&lt;/trans&gt;</code></div></div></td></tr></tbody></table></div></div>
    </div></div>

3. Crie uma agenda que executa todos os dias na hora desejada e aplique-a à operação contendo o *script* que você acabou de criar.

4. A cadeia de operação deverá ficar com uma aparência semelhante à da imagem abaixo quando os passos estiverem completos:

   <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_schedule.png" class="confluence-embedded-image confluence-external-resource" /></span>


## Habilitando ou Desabilitando Agendas

Quando você cria e aplica uma agenda a uma operação, ela é habilitada por padrão. Usando o [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR) (Console de Gerenciamento), você pode escolher desabilitar ou reabilitar uma agenda (caso esteja desabilitada) remotamente a partir da página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLangauge=pt_BR).

Na página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR), isto pode ser feito nas abas **Operations** (Operações) ou **Schedules** (Agendas) usando o botão na coluna **Operation Status** (*Status* da Operação) para habilitar ou desabilitar uma agenda em uma única operação, ou usando o botão na coluna **Schedule Status** (*Status* da Agenda) para habilitar ou desabilitar uma agenda em todas as operações que têm aquela agenda atribuída. Note que desabilitar uma agenda a nível de projeto faz com que o **Effective Status** (*Status* Efetivo) seja desabilitado mesmo que a agenda esteja habilitada para uma operação individual. Para instruções detalhadas, veja [Projetos (Management Console)](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Na interface do Cloud Studio, não existe indicação de quais agendas estão habilitadas ou desabilitadas, e não é possível a partir do Cloud Studio desabilitar uma agenda ou reabilitar uma agenda que tenha sido desabilitada. Portanto, é importante se lembrar caso você desabilite uma agenda, já que a única forma de saber que ela está desabilitada ou de reabilitá-la é por meio do Management Console.

</div>

</div>


## Diagnosticando e Resolvendo Problemas com Agendas

Se uma agenda não estiver funcionando da maneira esperada, verifique os seguintes itens ao tentar diagnosticar e resolver os problemas com ela:

- **Você implantou a operação à qual a agenda foi atribuída?**<br/>
  No Cloud Studio, as agendas devem ser atribuídas a uma operação e depois implantadas para serem acionadas. Depois de ter atribuído uma agenda a uma operação no Cloud Studio, ela não fará efeito até ter sido implantada. (Em contraste, agendas atribuídas a uma operação por meio do Management Console fazem efeito imediatamente sem a necessidade de reimplantar o projeto no Harmony).

- **A agenda está habilitada?**<br/>
  As agendas podem ser desabilitadas e reabilitadas somente de dentro do Management Console. Verifique a página [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) dentro das abas **Operations** (Operações) e **Schedules** (Agendas) para ter certeza de que a agenda está habilitada.

- **Você sabe em que fuso horário sua agenda está?**<br/>
  A questão dos fusos horários é abordada na seção [Fusos Horários de Operação](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR?hideelements=false#OperationSchedules-time-zones).

- **Se você estiver usando um Private Agent, o serviço de agendamento está executando?**<br/>
  Na máquina em que o Private Agent está instalado, verifique se o Jitterbit Scheduler e o Jitterbit Scheduler Service estão executando. Em computadores Windows, isto pode ser verificado no Gerenciador de Tarefas na aba Processos.

- **Se você estiver usando um Private Agent, será que agendas muito agressivas estão sobrecarregando o Agent Group?**<br/>
  Se você estiver usando Private Agents, avaliações adicionais devem ser feitas para garantir que um número excessivo de agendas em um período de tempo curto não sobrecarregue o Agent Group, causando um *backlog* de operações.

  Private Agents têm o padrão de poder executar até duas vezes a contagem de CPUs para cada máquina do agente. Por exemplo, se a máquina do Private Agent tiver 4 núcleos de CPU, você poderá executar no máximo 8 operações simultâneas.

  Ao avaliar os requisitos, algumas das operações podem ser mais dependentes de tempo do que outras. Se várias operações não-críticas estivessem engarrafando a fila do agente, operações mais críticas poderiam ser afetadas. Para evitar isso, determine o número de operações que o Agent Group pode processar simultaneamente (usando os cálculos da contagem de CPUs descritos acima), daí compare isso com a prioridade do negócio e a duração do tempo de execução das operações agendadas.
