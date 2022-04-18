[//]: # (Dependências e Exclusão de Workflows)
[//]: # (This is a translation of Version 11, published on August 6, 2021.)

## Introdução

Ver as dependências de um workflow lista os componentes do projeto dos quais o workflow depende. Visto que os componentes de projeto em si não podem ser dependentes de um workflow, os workflows podem ser deletados sem considerar as dependências.


## Definições

É importante entender a terminologia quando se fala de dependências. Dois termos distintos são empregados: *dependente* e *dependência*. Nestes exemplos, o Componente A é ***dependente*** do Componente B. O Componente B é uma ***dependência*** do Componente A.

-   **Dependente**: Se um componente é dependente de outro, ele precisa desse outro para poder funcionar corretamente. Um componente que é dependente de outro não pode estar por si só sem a presença do outro. Quando o Componente A precisa do Componente B para executar com sucesso, o Componente A é dependente do Componente B. Outra forma de expressar essa relação é dizer que o Componente A depende do Componente B.

-   **Dependência**: Se um componente é uma dependência de outro, a presença dele é necessária para que o outro funcione corretamente. Um componente que é uma dependência de outro componente é exigido por ele. Quando o Componente A precisa do Componente B para poder executar com sucesso, o Componente B é uma dependência do Componente A.


## Vendo as Dependências

A opção **View Dependencies** (Ver as Dependências) é acessível a partir da aba **Workflows** do painel de projeto (veja [Menu de Ações de Workflow](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-workflow-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

Ao selecionar **View Dependencies** (Ver Dependências), a visualização das dependências abre na aba **Workflows** do painel de projeto:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_workflow.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_workflow.png" /></span>

Na visualização das dependências, o nome do workflow selecionado aparece abaixo das áreas de busca e filtragem.

O nome do workflow é seguido por uma lista de **Dependencies** (Dependências) das quais ele depende. Esta lista é organizada por categorias tais como **Operation** (Operação), **Activity** (Atividade), ***Transformation*** e ***Script***. Cada categoria pode ser expandida ou escondida usando os triângulos de revelação <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/down-arrow_2.png" class="confluence-embedded-image confluence-external-resource" /></span> <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/right-arrow_2.png" class="confluence-embedded-image confluence-external-resource" /></span>.

Apenas as dependências do workflow que tenham um único nível de profundidade são mostradas. Por exemplo, embora o *script* “Format and Log Product Failure” seja uma dependência do workflow, outros componentes que são dependências desse *script* não são mostrados. Também não são mostrados os componentes que são dependentes do workflow exibido (isto é, componentes dos quais o próprio workflow é uma dependência não são listados).

Para fechar a visualização das dependências, clique no ícone de fechamento <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/close.png" class="confluence-embedded-image confluence-external-resource" /></span>:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_workflow_close_annotated.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/dependencies_workflow_close_annotated.png" /></span>


## Deletando

A opção **Delete** (Deletar) para excluir permanentemente um workflow é acessível a partir da aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

Ao selecionar **Delete** (Deletar), uma mensagem pede que você confirme que quer deletar o workflow:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/delete-workflow.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/delete-workflow.png" /></span>

Clique em **Continue** (Continuar) para excluir permanentemente o workflow. Note que quaisquer componentes de projeto usados dentro do workflow, incluindo as operações, não são deletados e ainda podem ser acessados na aba **Components** do painel de projeto.
