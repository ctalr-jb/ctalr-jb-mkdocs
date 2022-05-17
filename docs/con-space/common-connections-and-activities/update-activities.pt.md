[//]: # (Atividades Update)
[//]: # (This is a translation of Version 4, published on April 13, 2022.)


## Introdução

As atividades **Update**, usando sua [conexão](https://success.jitterbit.com/display/CS/common+connections), colocam um objeto em um *endpoint* e têm como propósito serem usadas como alvos para consumir dados em uma operação.


## Criando uma Atividade Update

Uma instância de uma atividade **Update** de conector é criada a partir de uma [conexão](https://success.jitterbit.com/display/CS/common+connections) usando seu tipo de atividade **Update**.

Para criar uma instância de uma atividade, arraste o tipo de atividade até o design canvas ou copie o tipo de atividade e cole-o no design canvas. Para mais detalhes, leia a seção [Criando uma Instância de Atividade](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-creating-an-activity-instance) em [Reuso de Componentes](https://success.jitterbit.com/display/CS/Component+Reuse).

Uma atividade **Update** existente pode ser editada a partir dos seguintes locais:

-   A aba **Connectivity** da paleta de componentes de *design* (veja a seção [*Endpoints*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR#DesignComponentPalette-endpoints) no artigo [Paleta de Componentes de *Design*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR)).

-   A aba **Components** do painel de projeto (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR#ProjectPaneComponentsTab-component-actions-menu) no artigo [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).


## Configurando uma Atividade Update

Certos conectores têm uma pequena variação dos passos a seguir para suas atividades **Update** e são documentados claramente. Para muitos conectores, basta seguir os passos abaixo para configurar suas atividades **Update**:

-   [Passo 1: Digite um Nome e Selecione um Objeto](https://success.jitterbit.com/display/CS/common+update+activities#step-1-enter-a-name-and-select-an-object)<br/>
    Forneça um nome para a atividade e selecione um objeto.

-   [Passo 2: Revise os *Schemas* de Dados](https://success.jitterbit.com/display/CS/common+update+activities#step-2-review-the-data-schemas)<br/>
    Eventuais *schemas* de solicitação ou de resposta gerados pelo *endpoint* são mostrados.

### Passo 1: Digite um Nome e Selecione um Objeto

Neste passo, forneça um nome para a atividade e selecione um objeto. Todo elemento da interface de usuário deste passo é descrito abaixo.

<span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-update-activity-1.png" class="confluence-embedded-image confluence-external-resource" /></span>

-   **Name** (Nome): Coloque um nome para identificar a atividade. O nome deve ser único para cada atividade **Create** do conector e não deve conter barras (`/`) nem dois pontos (`:`).

-   **Select an Object** (Selecione um Objeto): Esta seção mostra os objetos disponíveis no *endpoint*. Quando se reabre a configuração de uma atividade existente, apenas o objeto selecionado é mostrado em vez de se recarregar a lista de objetos inteira.

    -   **Selected … Object** (Objeto … Selecionado): Depois que um objeto é selecionado, ele é listado aqui.

    -   **Search** (Buscar): Coloque qualquer parte do nome do objeto na caixa de busca para filtrar a lista de objetos. A busca não distingue entre maiúsculas e minúsculas. Caso os objetos já estejam sendo exibidos na tabela, os resultados da tabela são filtrados em tempo real com cada tecla apertada. Para se recarregar objetos do *endpoint* durante a busca, coloque os critérios de busca e depois atualize, conforme descrito abaixo.

    -   **Refresh** (Atualizar): Clique no ícone de atualização <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/refresh-icon.png" class="confluence-embedded-image confluence-external-resource" /></span> ou na palavra **Refresh** para recarregar os objetos do *endpoint*. Isto pode ser útil caso objetos tenham sido adicionados ao *endpoint*. Esta ação atualiza todos os metadados usados para construir a tabela de objetos exibida na configuração.

    -   **Selecting an Object** (Selecionando um Objeto): Dentro da tabela, clique em qualquer lugar de uma linha para selecionar um objeto. Apenas um objeto pode ser selecionado. As informações disponíveis para cada objeto são buscadas no *endpoint*:

        -   **Name** (Nome): O nome do objeto do *endpoint*.

        -   **Description** (Descrição): A descrição do objeto do *endpoint*.

    <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **DICA**: Caso a tabela não seja preenchida com objetos disponíveis, a [conexão](https://success.jitterbit.com/display/CS/common+connections) pode não ser bem-sucedida. Tenha certeza de que você está conectado(a) reabrindo a conexão e testando novamente as credenciais.

    </div>

    </div>

-   **Continue on Error** (Continuar em Caso de Erro): Selecione para continuar a operação caso um erro seja encontrado. Se algum erro for encontrado, ele será escrito no [registro de operação](https://success.jitterbit.com/display/CS/Operation+Logs?showLanguage=pt_BR). O valor padrão é não-selecionado.

-   **Save & Exit** (Salvar & Sair): Quando está habilitada, clique para salvar a configuração deste passo e fechar a configuração da atividade.

-   **Next** (Próximo): Clique para armazenar temporariamente a configuração deste passo e continuar para o passo seguinte. A configuração não será salva até você clicar no botão **Finished** (Concluído) no último passo.

-   **Discard Changes** (Descartar Mudanças): Depois de fazer mudanças, clique aqui para fechar a configuração sem salvar as mudanças feitas em nenhum dos passos. Uma mensagem pede que você confirme que quer descartar as mudanças.

### Passo 2: Revise os *Schemas* de Dados

Todos os *schemas* de solicitação ou de resposta gerados pelo *endpoint* são mostrados. Todo elemento da interface de usuário deste passo é descrito abaixo.

<span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-update-activity-2.png" class="confluence-embedded-image confluence-external-resource" /></span>

-   **Data Schemas** (*Schemas* de Dados): Estes *schemas* de dados são herdados de *transformations* adjacentes e são exibidos de novo durante o [mapeamento do *transformation*](https://success.jitterbit.com/display/CS/Transformation+Mapping?showLanguage=pt_BR).

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Dados fornecidos em um *transformation* têm precedência sobre a configuração da atividade.

    </div>

    </div>

    O conector usa uma API REST e um *driver* JDBC. Consulte a documentação da API, conforme disponível, para mais informações sobre os nós e campos do *schema*.

-   **Refresh** (Atualizar): Clique no ícone de atualização <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/refresh-icon.png" class="confluence-embedded-image confluence-external-resource" /></span> ou na palavra **Refresh** para regenerar *schemas* do *endpoint*. Esta ação também regenera um *schema* em outros locais espalhados pelo projeto onde o mesmo *schema* é referenciado, como por exemplo, num *transformation* adjacente.

-   **Back** (Voltar): Clique para armazenar temporariamente a configuração deste passo e voltar ao passo anterior.

-   **Finished** (Concluído): Clique para salvar a configuração de todos os passos e fechar a configuração da atividade.

-   **Discard Changes** (Descartar Mudanças): Depois de fazer mudanças, clique para fechar a configuração sem salvar as mudanças feitas em nenhum dos passos. Uma mensagem pedirá que você confirme que quer descartar as mudanças.


## Próximos Passos

Depois de configurar a atividade **Update** de um conector, complete a configuração da operação adicionando ou configurando outras atividades, *transformations* ou *scripts* como etapas de operação. Você também pode definir as configurações da operação, o que inclui a habilidade de encadear operações que estejam no mesmo *workflow* ou em *workflows* diferentes.

As ações de menu de uma atividade ficam disponíveis no painel de projeto e no design canvas. Para mais detalhes, leia a seção [Menu de Ações de Atividade](https://success.jitterbit.com/display/CS/Connector+Basics#ConnectorBasics-actions-menu) no artigo [Informações Básicas sobre Conectores](https://success.jitterbit.com/display/CS/Connector+Basics#ConnectorBasics).

As atividades **Update** podem ser usadas como alvo com os seguintes [padrões de operação](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-valid-operation-patterns):

-   [*Padrão de Transformation*](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-transformation-pattern)

-   [*Padrão de Dois Transformations*](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-two-transformation-pattern) (como primeiro ou segundo alvo)

Um caso de uso típico é mostrado abaixo usando uma atividade **Update** do Dynamics 365 Sales dentro do *Padrão de Dois Transformations*. Neste exemplo, o primeiro *transformation* (*Update Request*) cria uma estrutura de solicitação que é passada para a atividade **Update** do Dynamics 365 Sales. O segundo *transformation* (*Update Response*) recebe a estrutura de resposta, que é então escrita numa variável por uma atividade **Write** Variable (*Write Update Response*) e uma mensagem é então gravada nos registros pelo *script* chamado *Write to Operation Log*:

<span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-update-activity-operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

Para usar a atividade com funções de *script*, grave os dados num local temporário e daí use este local temporário na função de *script*.

Quando estiver tudo pronto, [implante e execute](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution) a operação e valide o comportamento dela verificando os [registros de operação](https://success.jitterbit.com/display/CS/Operation+Logs).
