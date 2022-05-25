[//]: # (Dependências, Exclusão e Remoção de Operações)
[//]: # (This is a translation of Version 18, published on August 18, 2021.)


## Introdução

Ver as dependências de uma operação lista os outros componentes do projeto dos quais a operação depende. Caso outros componentes dependam da operação, estas dependências precisam ser removidas antes que uma operação possa ser deletada. Além disso, operações que são contidas dentro de um workflow podem ser removidas do workflow.


## Definições

É importante entender a terminologia quando se fala sobre dependências. Duas expressões distintas são usadas: *dependente* e *dependência*. Nos exemplos abaixo, o Componente A é ***dependente*** do Componente B. O Componente B é uma ***dependência*** do Componente A.

- **Dependente**: Se um componente é dependente de outro, então ele precisa desse outro para funcionar corretamente. Um componente que é dependente de outro não pode estar por si só sem o outro. Quando o Componente A precisa do Componente B para executar com sucesso, o Componente A é dependente do Componente B. Outra forma de dizer isso é que o Componente A depende do Componente B.

- **Dependência**: Se um componente for uma dependência de outro componente, ele é necessário para que o primeiro componente consiga funcionar corretamente. Um componente que é uma dependência de um outro é exigido por ele. Quando o Componente A precisa do Componente B para poder executar com sucesso, dizemos que o Componente B é uma dependência do Componente A.


## Visualizando Dependências

A opção **View Dependencies** (Visualizar Dependências) é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **View Dependencies** (Visualizar Dependências), a visualização de dependências abre na aba **Workflows** do painel de projeto):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

Na visualização de dependências, o nome da operação selecionada aparece abaixo das áreas de busca e de filtro.

O nome da operação é seguido por uma lista de **Dependencies** (Dependências) das quais a operação depende. Esta lista é organizada por categorias como **Outcome** (Resultado), que lista operações que são conectadas por [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR), **Activity** (Atividade), **Transformation** e **Schedule** (Agenda). Cada categoria pode ser expandida ou recolhida usando os triângulos de revelação <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/down-arrow_2.png" class="confluence-embedded-image confluence-external-resource" /></span> <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/right-arrow_2.png" class="confluence-embedded-image confluence-external-resource" /></span>.

Apenas as dependências da operação que têm um único nível de profundidade são mostradas. Por exemplo, embora o *transformation* listado “Magento Product Response” seja uma dependência da operação, outros componentes que são dependências do *transformation* não são listados. Assim como também não são os componentes que são dependentes da operação mostrada (isto é, componentes dos quais a própria operação é uma dependência não são listados).

Para sair da visualização de dependências, clique no ícone de fechamento <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close.png" class="confluence-embedded-image confluence-external-resource" /></span>:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_operation_close_annotated.png" class="confluence-embedded-image confluence-external-resource" /></span>


## Deletando uma Operação

A opção **Delete** (Deletar) para excluir permanentemente uma operação individual é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

A opção **Delete Unused** (Deletar Não-Usadas) para excluir permanentemente operações não-usadas em conjunto é acessível no seguinte local:

- A aba **Components** do painel de projeto (veja [Menu de Ações de Categoria](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-category-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

### Delete (Deletar)

Ao selecionar **Delete** (Deletar), uma caixa de diálogo pede que você confirme a exclusão ou indica que a operação tem dependências:

- [**Confirmar a Exclusão**](https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR#OperationDependencies,Deletion,andRemoval-confirming-deletion): Se a operação não tiver outros componentes dependentes dela, uma caixa de diálogo pede que você confirme a exclusão. Depois da confirmação, o Cloud Studio tentará excluir a operação e quaisquer outros componentes selecionados. Se a operação estiver sendo chamada por uma API externa, tanto a operação quanto quaisquer componentes selecionados não estarão disponíveis para exclusão.

- [**Outros Componentes São Dependentes desta Operação**](https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR#OperationDependencies,Deletion,andRemoval-components): Caso a operação tenha outros componentes dependentes da existência dela, uma caixa de diálogo indica imediatamente que a operação não está disponível para exclusão.

#### Confirmando a Exclusão

Se não houver outros componentes que tenham esta operação como dependência, uma caixa de diálogo pede que você confirme que quer excluir a operação:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/are-you-sure-you-want-to-delete-this-component_operation-components.png" class="confluence-embedded-image confluence-external-resource" /></span>

Incluída na caixa de diálogo está uma opção para também excluir quaisquer componentes que ficariam não-referenciados (não-usados) como resultado da exclusão da operação. São componentes que não são atualmente referenciados por nenhum componente além da operação sendo excluída. Esta opção é selecionada por padrão. Quando está selecionada, uma lista mostra os componentes que serão deletados quando a operação for. Clique em **Continue** (Continuar) para tentar excluir permanentemente a operação e seus componentes listados.

Para excluir apenas a operação sem deletar nenhum componente adicional, desmarque a seleção:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/are-you-sure-you-want-to-delete-this-component_operation-only.png" class="confluence-embedded-image confluence-external-resource" /></span>

Todo componente que seja referenciado apenas pela operação permanecerá no projeto e será acessível a partir da aba **Components** do painel de projeto. Nenhum componente adicional a ser deletado é listado na caixa de diálogo. Clique em **Continue** (Continuar) para tentar excluir permanentemente apenas a operação.

Caso haja uma API Customizada Jitterbit configurada por meio do [API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR) que chame esta operação, você não conseguirá deletá-la. Depois de clicar em **Continue** (Continuar), uma caixa de diálogo adicional será mostrada indicando que a operação está sendo chamada por uma API externa:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/unable-to-delete.png" class="confluence-embedded-image confluence-external-resource" /></span>

Clique em **Continue** (Continuar) para voltar ao *designer* de projeto sem que nenhuma ação ocorra. Para excluir uma operação assim, primeiro exclua a API por meio do API Manager ou então mude a configuração dela para que esta operação não seja mais iniciada pela API, daí tente de novo excluir a operação.

#### Outros Componentes São Dependentes da Operação

Caso haja outros componentes do projeto que sejam dependentes da operação, tais componentes são listados:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/unable-to-delete-operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

Note que o texto nesta caixa de diálogo (em inglês) afirma incorretamente que as dependências da operação estão listadas. Isto não é verdade, e na verdade todo componente que é ***dependente*** da operação é que é listado. Clique em **Continue** (Continuar) para voltar para o *designer* do projeto sem que nenhuma ação ocorra.

Para que uma operação assim seja excluída, você precisa modificar o projeto para que a operação não seja mais dependente destes componentes. Por exemplo, se a Operação B estiver conectada abaixo da Operação A na corrente usando [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR), primeiro remova a conexão e daí tente de novo excluir a operação.

#### Excluir Não-Usadas

Ao selecionar a opção **Delete Unused** (Excluir Não-Usadas), cada operação a ser deletada é listada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/delete-components_operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

Clique em **Continue** (Continuar) para excluir permanentemente as operações.


## Removendo uma Operação

A opção **Remove** (Remover) para remover uma opção do design canvas é acessível a partir dos seguintes locais:

- A aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

- A aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

- O design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

Ao selecionar **Remove** (Remover), a operação é removida de todos os workflows. Remover operações é permitido independentemente de dependências, já que as operações não são excluídas do projeto e continuam disponíveis na aba **Components** do painel de projeto.

Para reusar uma operação que você removeu do design canvas, veja o artigo [Reuso de Operações](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR).
