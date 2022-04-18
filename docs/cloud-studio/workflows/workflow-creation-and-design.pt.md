[//]: # (Criação e Design de Workflows)
[//]: # (This is a translation of Version 23, published on November 9, 2021.)

## Introdução

Um workflow é uma coleção de operações que é usado como ferramenta para ajudar a segregar as diferentes partes do projeto. Por agrupar operações em um workflow, você pode achar mais conveniente organizar fluxos de processo de maneira lógica.

Por exemplo, um workflow pode incluir um grupo de operações que acessa um objeto produto do Magento e grava o resultado em um armazenamento temporário, daí lê do armazenamento temporário e grava em um banco de dados e registra eventuais erros no registro de operações. Um outro workflow no mesmo projeto pode ser usado para criar um fluxo similar para o objeto pedido de venda do Magento.

Esta página abrange a criação, renomeação, reordenação e como fazer o *design* de um workflow.


## Criando um Workflow

Em um novo projeto, o primeiro workflow já é criado e aberto no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR) por padrão. O novo workflow mostra uma área de inserção de operações, que é uma representação visual de onde uma operação pode ser colocada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/workflow_new.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/workflow_new.png" /></span>

Para criar workflows adicionais, clique no ícone de novo workflow <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/add_4.png" class="confluence-embedded-image confluence-external-resource" /></span> na parte superior do design canvas para criar novas abas de workflows. Quando você cria um novo workflow, o nome padrão dele é *New Workflow*. Futuros novos workflows com nomes padrão recebem também um número cada vez maior entre parênteses:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/workflow_new_tab.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/workflow_new_tab.png" /></span>

À medida que você cria novos workflows, um quadro em branco com uma área de soltura de operações é mostrado, pronto para que você faça o *design* de cada workflow.


## Menu de Ações de Workflow

Depois que um workflow é criado, as ações de menu desse workflow são acessíveis a partir da aba **Workflows** do painel de projeto (veja [Menu de Ações de Workflow](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-workflow-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

Todas as seguintes ações de menu estão disponíveis:

<table class="relative-table wrapped confluenceTable">
<colgroup>
<col style="width: 13%" />
<col style="width: 86%" />
</colgroup>
<tbody>
<tr class="header">
<th class="confluenceTh">Item do Menu</th>
<th class="confluenceTh">Descrição</th>
</tr>

<tr class="odd odd">
<td class="confluenceTd"><p><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/cs/menu-items/deploy.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy.png" height="33" /></span></p>
<p><em>Implantação</em></p></td>
<td class="confluenceTd">O botão <strong>Deploy</strong> (Implantação) implanta o workflow e todos os componentes dos quais ele depende (veja <a href="https://success.jitterbit.com/display/CS/Workflow+Deployment?showLanguage=pt_BR">Implantação de Workflows</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><p><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/cs/menu-items/configurable-deploy.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/menu-items/configurable-deploy.png" height="33" /></span></p>
<p><em>Implantação Configurável</em></p></td>
<td class="confluenceTd">O botão <strong>Configurable Deploy</strong> (Implantação Configurável) abre a tela de implantação, onde você pode selecionar componentes do projeto para implantar (veja <a href="https://success.jitterbit.com/display/CS/Workflow+Deployment?showLanguage=pt_BR">Implantação de Workflows</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><p><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/cs/menu-items/rename.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png" height="33" /></span></p>
<p><em>Renomear</em></p></td>
<td class="confluenceTd">O botão <strong>Rename</strong> (Renomear) posiciona o cursor sobre o nome do workflow para que você faça edições conforme necessário.</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><p><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png" height="33" /></span></p>
<p><em>Ver Dependências</em></p></td>
<td class="confluenceTd">O botão <strong>View Dependencies</strong> (Ver Dependências) muda a visualização no painel de projeto para exibir as outras partes do projeto das quais aquele workflow específico depende (veja <a href="https://success.jitterbit.com/display/CS/Workflow+Dependencies+and+Deletion?showLanguage=pt_BR">Dependências e Exclusão de Workflows</a>).</td>
</tr>
<tr class="odd odd">
<td class="confluenceTd"><p><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png" height="33" /></span></p>
<p><em>Ver Registros</em></p></td>
<td class="confluenceTd">O botão <strong>View Logs</strong> (Ver Registros) abre a tela de registros de operações, que inclui os registros de quaisquer operações contidas no workflow que já tenham sido implantadas e executadas, bem como de quaisquer operações conectadas ao workflow que tenham sido implantadas e executadas (veja <a href="https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR">Registros de Operação</a>).</td>
</tr>
<tr class="header header">
<td class="confluenceTd"><p><span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/cs/menu-items/delete.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png" height="33" /></span></p>
<p><em>Deletar</em></p></td>
<td class="confluenceTd">O botão <strong>Delete</strong> (Deletar) exclui permanentemente o workflow (veja <a href="https://success.jitterbit.com/display/CS/Workflow+Dependencies+and+Deletion?showLanguage=pt_BR">Dependências e Exclusão de Workflows</a>).</td>
</tr>
</tdead>
<tbody>
</tbody>
</table>


## Renomeando um Workflow

Os workflows podem ser renomeados nos seguintes lugares:

-   A aba **Workflows** do painel de projeto (veja [Menu de Ações de Workflow](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-workflow-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

-   O design canvas (veja [Renomeando Workflows, Operações e Etapas de Operação](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-renaming) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Nomes de workflows dentro de um projeto devem ser únicos e não podem conter barras (`/`) ou dois pontos (`:`) para serem válidos.


## Reordenando Workflows

Os workflows podem ser reordenados na aba **Workflows** do painel de projeto (veja [Reordenando Operações](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-reorder-an-operation) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).


## Fazendo o *Design* de um Workflow

Os workflows podem ser projetados ao se colocar e configurar operações no design canvas. Outros elementos do design canvas como áreas de inserção, notificações e as linhas que unem operações e notificações conectadas ajudam você a fazer o *design* dos seus workflows (veja [Elementos do Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-design-canvas-elements) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Outros componentes de projeto podem não aparecer visualmente no design canvas mas podem ser usados em apoio a operações. Esses componentes, tais como atividades, *scripts*, variáveis de projeto, agendas e *schemas*, são reutilizáveis em operações e workflows.

À medida que você adiciona operações a um workflow, o *layout* é automaticamente renderizado no design canvas. Cada operação é numerada sequencialmente e automaticamente organizada no design canvas, e elas vão sendo empilhadas verticalmente abaixo da última operação no design canvas. A sequência numérica das operações dentro de um workflow é incluída no título da operação e se ajusta automaticamente caso você reordene as operações. Da mesma forma, a ordem e a numeração dos workflows se ajusta se os workflows forem reordenados.

Independentemente da ordem das operações, cada operação fica no mesmo nível hierárquico. O conceito de operações “mães” e “filhas” aplica-se apenas a operações que são encadeadas com [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR). (Isto é, se a execução de uma operação levar à execução de outra operação, dizemos que a primeira operação é a “mãe” e que a segunda operação é a “filha”). Este relacionamento é visualmente indicado pela presença de linhas conectando estas operações dentro ou fora do workflow.

Não é exigido que as operações dentro de um workflow estejam encadeadas a ações de operação. Você pode, por exemplo, criar várias operações no mesmo workflow que não estão ligadas umas às outras por ações de operação. Neste caso, a execução de qualquer uma dessas operações não leva à execução das outras operações no workflow, já que elas não estão conectadas. Em vez disso, você pode optar por executar essas operações individualmente, ou conectá-las a operações em um outro workflow usando ações de operação.

### Exemplo 1

O workflow modelo abaixo contém três operações: *1.0 Query Magento Products* (Fazer uma *Query* em Produtos Magento)*, 1.1 Upsert Postgres Products* (Fazer *Upsert* de Produtos Postgres) e *1.2 Write Product Failure Info to Log* (Gravar Informações da Falha de Produto nos Registros). As ações de operação que conectam essas operações estão configuradas de tal modo que, se for bem sucedida, a operação 1.0 dá início à operação 1.1; se a operação 1.0 falhar, a operação 1.2 é executada. Se a operação 1.1 for iniciada e executar com sucesso, a cadeia de execução está completa; se a operação 1.1 for iniciada e falhar, a operação 1.2 é executada.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script.png" /></span>

### Exemplo 2

Se as operações no mesmo workflow usado no Exemplo 1 fossem reordenadas, o mesmo resultado seria atingido. Neste caso, embora a operação *1.2 Query Magento Products* aparece como a última operação no workflow, enquanto ela for executada primeiro, as outras operações na cadeia são iniciadas por consequência como resultado das ações de operação configuradas.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script_reorder.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script_reorder.png" /></span>

### Exemplo 3

Se as operações no mesmo workflow usado nos Exemplos 1 e 2 tivesse suas ações de operação removidas, isso romperia a cadeia de operações. Você poderia executar as operações 1.0, 1.1 ou 1.2 individualmente, mas a execução de qualquer uma delas não levaria à execução de nenhuma das outras.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script_reorder_no-chain.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script_reorder_no-chain.png" /></span>
