[//]: # (Validade de Componentes)
[//]: # (This is a translation of Version 9, published on August 4, 2021.)

## Introdução

Componentes devem ser válidos para serem implantados. Esta página abrange como identificar componentes inválidos e visualizar os erros de validação associados a eles, além de como resolvê-los.


## Erros de Validação

Esta seção aborda como identificar componentes de projeto inválidos e visualizar os erros de validação associados a componentes inválidos.

Para novos projetos, itens inválidos são destacados por padrão no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR), com a seleção padrão **Highlight Invalid Items** (Destacar Itens Inválidos). Para desativar esta opção, desmarque a caixa:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/highlight-invalid-items.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/highlight-invalid-items.png" /></span>

Quando esta opção estiver selecionada, os nomes dos componentes inválidos aparecem em itálico e na cor vermelha, e os ícones deles são destacados com uma borda vermelha no design canvas:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_invalid.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_invalid.png" /></span>

No [painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane?showLanguage=pt_BR), os nomes dos componentes inválidos também aparecem em itálico e na cor vermelha. Além disso, os componentes inválidos que têm um erro implícito são mostrados com um ícone de erro <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png" class="confluence-embedded-image confluence-external-resource" /></span>. O ícone de erro <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png" class="confluence-embedded-image confluence-external-resource" /></span> não aparece se o motivo pelo qual o componente está inválido for porque ele contém outros componentes com erros implícitos. For exemplo, um workflow pode estar inválido porque contém operações ou outros componentes que estão inválidos, ou uma operação pode estar inválida porque contém outros componentes que são inválidos, como mostrado abaixo:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_components.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_components.png" /></span>

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/components/invalid.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/invalid.png" /></span>

Para exibir os erros de validação dos componentes identificados como implicitamente inválidos, clique no ícone de erro <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png" class="confluence-embedded-image confluence-external-resource" /></span> ao lado do nome do componente. Uma caixa de diálogo exibirá os erros de validação do componente. Para informações detalhadas sobre o que faz com que componentes se tornem inválidos e como resolver erros de validação, veja Regras [de Validação](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR#ComponentValidity-validity-rules), abaixo.


## Regras de Validação

Certas regras de validação devem ser seguidas para que os componentes de projeto sejam implantados na nuvem do Harmony e para que as operações dentro das quais eles são usados sejam executadas nos agentes do Harmony. Estas regras garantem que todas as partes do projeto sejam suportadas e esperadas pelo agente. As regras de validação dos workflows e das operações são descritas nas seguintes páginas:

-   [Validade de Workflows](https://success.jitterbit.com/display/CS/Workflow+Validity?showLanguage=pt_BR)

-   [Validade de Operações](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR)

As regras para os outros componentes de projeto individuais são detalhadas a seguir.

### Os Nomes Devem Ser Únicos

Os nomes de alguns tipos de componentes de projeto devem ser únicos para cada tipo de componente.

Dependendo de qual componente está inválido, a variação apropriada da seguinte mensagem de erro é retornada se esta regra não for seguida:

\[Operation / Connection / Activity / Transformation / Script / Email / Variable\] names must be unique.

Ao criar um novo componente de projeto do zero, a validação de campos incluída na tela de configuração de componente não deixará que você entre o mesmo nome para vários componentes de projeto. No entanto, você pode receber esta mensagem de erro se, por exemplo, você tiver [importado um projeto](https://success.jitterbit.com/display/CS/Project+Exports+and+Imports?showLanguage=pt_BR) que contém componentes com nomes duplicados.

Se você receber um desses erros, verifique para ter certeza que você deu nomes únicos a cada componente do projeto e mude os nomes de quaisquer duplicatas que houver. Os *links* da documentação de cada componente de projeto estão na página [Componentes de Projeto](https://success.jitterbit.com/display/CS/Project+Components?showLanguage=pt_BR).

### Componentes de Projeto Devem Ser Válidos

As regras de validação dependem do tipo de componente.

#### Atividades

Para que uma atividade seja válida, ela deve ser configurada corretamente. Se uma atividade não tiver sido configurada ou se estiver com a configuração errada, a seguinte mensagem de erro de validação é retornada:

Activity is not configured properly.

Esta mensagem aparece em alguns cenários comuns:

-   Quando novas atividades são adicionadas a uma operação a partir da [paleta de componentes de design](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR), elas ainda não estão configuradas, então você pode receber esta mensagem de erro caso tenha adicionado uma nova atividade sem configurá-la. Para resolver isso, abra a tela de configuração de atividade e configure a atividade.

-   Caso a atividade esteja parcialmente configurada, ou caso a validação de campos individuais dentro da configuração da atividade não tenha sido satisfeita, você também pode receber esta mensagem de erro. Para resolver isso, abra as configurações da atividade e complete todos os campos requeridos com entradas válidas.

Se uma atividade estiver inválida por causa de alguma outra razão que não pôde ser determinada imediatamente, esta mensagem de erro é retornada:

Activity is invalid.

Para resolver isso, consulte a documentação de cada atividade disponível em [Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR).

#### *Scripts*

Para que um *script* seja válido, ele deve ser configurado corretamente. Caso um script não tenha sido configurado ou esteja configurado incorretamente, a seguinte mensagem de erro é retornada:

Script is not configured properly.

É mais comum esta mensagem aparecer depois que você adiciona um novo *script* a uma operação e ele está vazio. Para resolver isso, abra a tela de configuração do *script* e construa um *script* no editor.

Além disso, para que um [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR) seja válido, ele não deve ter nenhum erro de validação dentro do *script* em si. (A validação não está disponível para scripts escritos em [JavaScript](https://success.jitterbit.com/display/CS/JavaScript?showLanguage=pt_BR).) Se um [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR) contiver erros de validação, esta mensagem de erro de validação é retornada:

Script is invalid.

Para resolver isso, abra a tela de configuração de *script*. O texto mostrado na parte de baixo do editor de *script* indicará as validações específicas de cada linha do *script*. Nós também recomendamos [testar o *script*](https://success.jitterbit.com/display/CS/Script+Testing?showLanguage=pt_BR) para garantir que ele seja válido. Documentação adicional está disponível em [*Scripts*](https://success.jitterbit.com/display/CS/Scripts?showLanguage=pt_BR).

#### *Transformations*

Para que um *transformation* seja válido, ele deve ser configurado corretamente. Caso um *transformation* não tenha sido configurado ou esteja configurado incorretamente, a seguinte mensagem de erro de validação é retornada:

Transformation is not configured properly.

É mais comum esta mensagem aparecer depois que você adiciona um novo *transformation* a uma operação e ele ainda não foi configurado. Para resolver isso, abra a tela de configuração de *transformation*, daí configure-o conforme necessário.

Além disso, para que um *transformation* seja válido, não deve haver nenhum erro de validação dentro do *transformation* em si. Para ser considerada válido, um *transformation* deve obedecer às seguintes regras:

-   Um mapeamento não pode conter referências a campos ou variáveis que não existem.

-   Um mapeamento não pode conter conflitos de tipo de dados.

-   Um *loop node* (nó do tipo *loop*) alvo não pode ter mais de uma fonte.

-   Um *schema* deve ser fornecido para uma atividade fonte ou alvo adjacente.

Além disso, certos campos alvo podem exigir mapeamento, ou podem não permitir mapeamento. Mapeamentos inválidos são visualmente indicados dentro da tela de configuração de transformação (veja [Validação de Mapeamento de *Transformations*](https://success.jitterbit.com/display/CS/Transformation+Mapping+Validity?showLanguage=pt_BR)).

Dependendo do erro, a variação apropriada das mensagens de erro possíveis abaixo é retornada caso esta regra não seja seguida:

Mapping refers to a non-existent \[source / target / variable\] field $\[path\].

Potential data type conflict in mapping.

Target field $\[node.name\] \[must be mapped / cannot be mapped\].

Mappings of a target loop node depend on more than one source loop node.

\[Source / Target\] schema must be provided.

Para resolver isso, tente as seguintes dicas de resolução de problemas:

-   Caso você tenha referências a campos não-existentes, conflitos de tipo de dados, ou outros mapeamentos inválidos, você pode encontrar o mapeamento inválido e desfazê-lo ou verificar o [*schema*](https://success.jitterbit.com/display/CS/Schemas?showLanguage=pt_BR) para garantir que todos os campos estão incluídos e têm tipos de dados compatíveis. Caso você tenha referências a variáveis não-existentes, certifique que a [variável](https://success.jitterbit.com/display/CS/Variables?showLanguage=pt_BR) existe.

-   Caso você tenha um *loop node* (nó do tipo *loop*) alvo que depende de mais de um *loop node* fonte, siga as instruções dadas em [Mapeando de Uma Fonte de Várias Instâncias para Uma Fonte de Instância Única](https://success.jitterbit.com/display/CS/Nodes+and+Fields?showLanguage=pt_BR#NodesandFields-multi-source) em [Nós e Campos](https://success.jitterbit.com/display/CS/Nodes+and+Fields?showLanguage=pt_BR).

-   Caso você tenha atividades fonte ou alvo adjacentes ao *transformation*, tenha certeza de estar dando um *schema* para cada um. *Schemas* de arquivo podem ser dados a partir de [dentro da atividade](https://success.jitterbit.com/display/CS/Schemas+Defined+in+an+Activity?showLanguage=pt_BR) em si durante a sua configuração (veja a documentação de cada [conector](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR)), ou [definindo um *schema*](https://success.jitterbit.com/display/CS/Schemas+Defined+in+a+Transformation?showLanguage=pt_BR) dentro do *transformation* em si.

Além disso, se um *transformation* for inválido por algum outro motivo que não pôde ser determinado imediatamente, a seguinte mensagem de erro é retornada:

Transformation is invalid.

Para informações mais detalhadas, veja [Validade do Mapeamento de *Transformations*](https://success.jitterbit.com/display/CS/Transformation+Mapping+Validity?showLanguage=pt_BR), assim como páginas adicionais em [*Transformations*](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR).
