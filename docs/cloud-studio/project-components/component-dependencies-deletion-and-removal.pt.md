[//]: # (Dependências, Exclusão e Remoção de Componentes)
[//]: # (This is a translation of Version 25, published on September 30, 2021.)

## Introdução

Ver as dependências de um componente lista os outros componentes do projeto dos quais o componente depende. Se outros componentes forem dependentes do componente, estas dependências devem ser removidas antes que um componente possa ser deletado.

O processo para ver as dependências e realizar a exclusão de workflows e operações é coberto nestas páginas:

-   **Workflows**: [Dependências e Exclusão de Workflows](https://success.jitterbit.com/display/CS/Workflow+Dependencies+and+Deletion?showLanguage=pt_BR)

-   **Operações**: [Dependências, Exclusão e Remoção de Operações](https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR)

Ver as dependências de outros componentes de projeto, tais como atividades, *transformations*, *scripts*, *schemas*, variáveis de projeto, variáveis globais, notificações de e-mail e agendas também é possível. Cada um desses componentes também pode ser excluído ou removido de uma operação usando o mesmo método, exceto as variáveis globais, que são deletadas com a exclusão do trecho de *script* onde elas são definidas.


## Definições

É importante entender a terminologia quando se fala de dependências. Dois termos distintos são empregados: *dependente* e *dependência*. Nestes exemplos, o Componente A é ***dependente*** do Componente B. O Componente B é uma ***dependência*** do Componente A.

-   **Dependente**: Se um componente é dependente de outro, ele precisa desse outro para poder funcionar corretamente. Um componente que é dependente de outro não pode estar por si só sem a presença do outro. Quando o Componente A precisa do Componente B para executar com sucesso, o Componente A é dependente do Componente B. Outra forma de expressar essa relação é dizer que o Componente A depende do Componente B.

-   **Dependência**: Se um componente é uma dependência de outro, a presença dele é necessária para que o outro funcione corretamente. Um componente que é uma dependência de outro componente é exigido por ele. Quando o Componente A precisa do Componente B para poder executar com sucesso, o Componente B é uma dependência do Componente A.


## Vendo as Dependências

A opção **View Dependencies** (Ver Dependências) é acessível a partir dos seguintes locais:

-   A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

-   A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel do Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

Ao selecionar **View Dependencies** (Ver Dependências), a visualização das dependências abre na aba **Workflows** do painel de projeto:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_transformation.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_transformation.png" /></span>

Na visualização das dependências, o nome do componente selecionado aparece abaixo das áreas de busca e filtragem.

O nome do componente é seguido por uma lista de **Dependencies** (Dependências) das quais o componente depende. Esta lista é organizada por categorias tais como **Workflow**, **Operation** (Operação) e **Activity** (Atividade). Estas categorias variam dependendo do tipo de componente sendo visualizado. Para as variáveis globais, as categorias têm mais uma classificação, **Read** (Ler) ou **Write** (Gravar) para indicar o tipo de uma referência de variável em particular:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_global-variable.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_global-variable.png" /></span>

Cada categoria pode ser expandida ou escondida usando os triângulos de revelação <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/down-arrow_2.png" class="confluence-embedded-image confluence-external-resource" /></span> <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/right-arrow_2.png" class="confluence-embedded-image confluence-external-resource" /></span>.

Apenas as dependências do componente com um único nível de profundidade são exibidas. Por exemplo, ao ver as dependências da transformação “Magento Product Response”, embora a atividade listada “GET Magento Products” seja uma dependência do *transformation*, outros componentes que são dependências da atividade não são exibidos. Assim como não são exibidos os componentes que são dependentes do *transformation* mostrado (isto é, outros componentes dos quais o próprio componente é uma dependência não são listados).

Para fechar a visualização de dependências, clique no ícone de fechamento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close.png" class="confluence-embedded-image confluence-external-resource" /></span>:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_transformation_close_annotated.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_transformation_close_annotated.png" /></span>


## Deletando

A opção **Delete** (Deletar) para excluir permanentemente um componente individual pode ser acessada nos seguintes locais:

-   A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

-   A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

A opção **Delete Unused** (Deletar Não-Usados) para excluir permanentemente todos os componentes não-usados de uma vez pode ser acessada no seguinte local:

-   A aba **Components** do painel de projeto (veja [Menu de Ações de Categoria](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

### Deletar

Ao selecionar **Delete** (Deletar), se houver outros componentes de projeto que são dependentes do componente que está sendo deletado, tais componentes são listados:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/unable-to-delete-component.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/unable-to-delete-component.png" /></span>

Repare que o texto (em inglês) desta mensagem afirma incorretamente que as dependências do componente sendo deletado são listadas. Isto não é verdade, e de fato quaisquer outros componentes que são ***dependentes do*** componente é que na verdade estão sendo listados. Clique em **Continue** (Continuar) para voltar para o designer de projeto sem que nenhuma ação ocorra.

Para permitir a exclusão do componente, você deve modificar o projeto para que o componente não seja dependente desses outros componentes. Por exemplo, se a atividade Componente B precisa do *transformation* Componente A para funcionar corretamente, primeiro remova o *transformation* Componente A da operação e daí tente de novo deletar a atividade Componente B.

Se não houver outros componentes que têm o componente sendo deletado como dependência de nenhum componente, uma mensagem pede que você confirme que quer deletar o componente:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/delete-component.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/delete-component.png" /></span>

### Deletar Não-Usados

Ao selecionar **Delete Unused** (Deletar Não-Usados), cada componente é listado:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/delete-components_variable.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/delete-components_variable.png" /></span>

Clique em **Continue** (Continuar) para deletar permanentemente os componentes.


## Removendo

A opção **Remove** (Remover) para remover um componente do design canvas pode ser acessada nos seguintes locais:

-   A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

-   A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

-   O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **Remove** (Remover) para uma atividade, *script*, ou *transformation*, o componente é removido de quaisquer operações que sejam referenciadas no design canvas. Ao selecionar **Remove** (Remover) para uma notificação de e-mail que está configurada com uma [ação de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) para uma operação no design canvas, a ação de operação é removida. Para reusar um componente que você removeu de uma operação, veja [Reuso de Componentes](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR).

Remover componentes usados como etapas em uma operação é permitido independentemente das dependências, já que estes componentes não são deletados do projeto e ainda estão disponíveis na aba **Components** do painel do projeto.

No entanto, dependendo das dependências que existam, ao remover o componente da operação, isto pode causar que a operação ou outros componentes usados como etapas dentro da operação se tornem inválidos. Isto é, remover componentes de uma operação não afeta as dependências.

Remover todas as etapas de uma operação não exclui a operação do projeto. Caso você remova todos os passos de uma operação, a operação desaparece da aba **Workflows** do painel de projeto e é mostrada no design canvas como uma operação vazia:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_empty.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_empty.png" /></span>

Uma operação vazia continua disponível como componente na aba **Components** e é listada como um componente quando se implanta o projeto. Já que uma operação vazia é inválida, ela não pode ser implantada. Para deletar uma operação cujos passos foram removidos, faça isso no [menu de operações](https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR#ComponentDependencies,Deletion,andRemoval-accessing-menu-actions), que é acessível da aba **Components** ou do design canvas.
