[//]: # (Validade de Workflows)
[//]: # (This is a translation of Version 8, published on August 6, 2021.)

## Introdução

Workflows devem ser válidos para poderem ser implantados. Esta página abrange como identificar workflows inválidos e ver os erros de validação associados a eles, assim como a maneira de resolvê-los.


## Erros de Validação

Esta seção abrange como identificar workflows inválidos e ver os erros de validação associados a eles.

Para os novos projetos, itens inválidos são destacados por padrão no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR), com a seleção padrão de **Highlight Invalid Items** (Destacar Itens Inválidos). Para desabilitar esta opção, desmarque a seguinte caixa de seleção:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/highlight-invalid-items.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/highlight-invalid-items.png" /></span>

Quando **Highlight Invalid Items** está selecionada, os nomes dos workflows inválidos aparecem em itálico e na cor vermelha na [aba **Workflows** do painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR). Se o workflow estiver inválido devido a um erro implícito com o workflow, um ícone de erro <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png" class="confluence-embedded-image confluence-external-resource" /></span> é exibido ao lado do nome do workflow:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_workflow_empty.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_workflow_empty.png" /></span>

Quando ele é clicado, uma caixa de diálogo mostra os erros de validação do workflow. Para mais informações sobre possíveis erros, veja a seção [Regras de Validação](https://success.jitterbit.com/display/CS/Workflow+Validity?showLanguage=pt_BR#WorkflowValidity-validity-rules), mais abaixo.

O ícone de erro <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png" class="confluence-embedded-image confluence-external-resource" /></span> não aparece se o motivo para o workflow estar inválido é que ele contém outros componentes com erros implícitos. Por exemplo, um workflow pode estar inválido por conter operações que são inválidas.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_workflow_components.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_workflow_components.png" /></span>


## Regras de Validação

Certas regras de validação devem ser seguidas para que os workflows possam ser implantados na nuvem do Harmony e para que as operações dentro deles sejam executadas em agentes do Harmony. Estas regras garantem que todas as partes de um projeto sejam suportadas e esperadas pelo agente. As regras para os workflows estão detalhadas a seguir.

### Workflows Devem Ser Válidos

Para que um workflow seja válido, ele deve conter pelo menos uma operação, e todas as operações que ele contém devem ser válidas. Se essas regras não forem atendidas, a seguinte mensagem de erro de validação é retornada:

> Workflow is empty.
>
> Workflow contains invalid operations.

As operações podem estar inválidas por vários motivos. Para resolver este erro, resolva os erros de validação de todas as operações contidas dentro do workflow, conforme explicado no artigo [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR).

Além disso, se um workflow estiver inválido por algum outro motivo que não pode ser facilmente determinado, a seguinte mensagem de erro é retornada:

> Workflow is invalid.

Para resolver isso, tente consultar a documentação em [Criação e *Design* de Workflows](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design?showLanguage=pt_BR).
