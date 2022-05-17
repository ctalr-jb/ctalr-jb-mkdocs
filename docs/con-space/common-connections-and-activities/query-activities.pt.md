[//]: # (Atividades Query)
[//]: # (This is a translation of Version 4, published on April 13, 2022.)


## Introdução

Atividades **Query**, por meio da sua [conexão](https://success.jitterbit.com/display/CS/common+connections), buscam objetos de um *endpoint* e têm como propósito serem usadas como fontes para fornecer dados em uma operação


## Criando uma Atividade Query de Conector

Uma instância de uma atividade **Query** de conector é criada a partir de uma [conexão](https://success.jitterbit.com/display/CS/common+connections) usando o tipo de atividade **Query**.

Para criar uma instância de uma atividade, arraste um tipo de atividade até o design canvas ou copie o tipo de atividade e cole-o sobre o design canvas. Para mais detalhes, leia a seção [Criando uma Instância de Atividade](https://success.jitterbit.com/display/CS/Component+Reuse#heading-CriandoumaInst%C3%A2nciadeAtividade) no artigo [Reuso de Componentes](https://success.jitterbit.com/display/CS/Component+Reuse).

Uma atividade **Query** existente pode ser editada nos seguintes locais:

-   A aba **Connectivity** (Conectividade) da paleta de componentes de *design* (veja a seção [Endpoints](https://success.jitterbit.com/display/CS/Design+Component+Palette#DesignComponentPalette-endpoints) em [Paleta de Componentes de *Design*](https://success.jitterbit.com/display/CS/Design+Component+Palette)).

-   A aba **Components** do painel de projeto (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab#ProjectPaneComponentsTab-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab)).


## Configurando uma Atividade Query

Certos conectores têm uma variação dos passos a seguir para suas atividades **Query** e são documentados claramente. Porém, para muitos conectores, basta seguir os seguintes passos para configurar as suas atividades **Query**:

-   [Passo 1: Digite um Nome e Selecione um Objeto](https://success.jitterbit.com/display/CON/Query+Activities#heading-Step1EnteraNameandSelectanObject)<br/>
    Forneça um nome para a atividade e selecione um objeto.

-   [Passo 2: Construa a Sua *Query*](https://success.jitterbit.com/display/CON/Query+Activities#heading-Step2BuildYourQuery)<br/>
    Defina as condições da *query* usando os campos do objeto e aplique paginação à sua *query*.

-   [Passo 3: Revise os *Schemas* de Dados](https://success.jitterbit.com/display/CON/Query+Activities#heading-Step3ReviewtheDataSchemas)<br/>
    Eventuais *schemas* de solicitação ou de resposta gerados pelo *endpoint* são mostrados.

### Passo 1: Digite um Nome e Selecione um Objeto

Neste passo, forneça um nome para a atividade e selecione um objeto. Cada elemento da interface de usuário deste passo é descrito abaixo.

<span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-query-activity-1.png" class="confluence-embedded-image confluence-external-resource" /></span>

-   **Name** (Nome): Digite um nome para identificar a atividade. O nome deve ser único para cada atividade **Query** do conector e não deve conter barras (`/`) ou dois pontos(`:`).

-   **Select an Object** (Selecione um Objeto): Esta seção exibe os objetos disponíveis no *endpoint*. Quando se reabre a configuração de uma atividade existente, apenas o objeto selecionado é mostrado em vez de se recarregar a lista de objetos inteira.

    -   **Selected … Object** (Objeto … Selecionado): Depois que um objeto é selecionado, ele é mostrado aqui.

    -   **Search** (Buscar): Coloque qualquer parte do nome do objeto na caixa de busca para filtrar a lista de objetos. A busca não distingue entre maiúsculas e minúsculas. Caso os objetos já estejam sendo exibidos na tabela, os resultados da tabela são filtrados em tempo real com cada tecla apertada. Para se recarregar objetos do *endpoint* durante a busca, coloque os critérios de busca e depois atualize, conforme descrito abaixo.

    -   **Refresh** (Atualizar): Clique no ícone de atualização <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/refresh-icon.png" class="confluence-embedded-image confluence-external-resource" /></span> ou na palavra **Refresh** para recarregar os objetos do *endpoint*. Isto pode ser útil caso objetos tenham sido adicionados ao *endpoint*. Esta ação atualiza todos os metadados usados para construir a tabela de objetos exibida na configuração.

    -   **Selecting an Object** (Selecionando um Objeto): Dentro da tabela, clique em qualquer lugar de uma linha para selecionar um objeto. Apenas um objeto pode ser selecionado. As informações disponíveis para cada objeto são buscadas no *endpoint*:

        -   **Name** (Nome): O nome do objeto do *endpoint*.

        -   **Type** (Tipo): O tipo do objeto do *endpoint*.

        -   **Description** (Descrição): A descrição do objeto do *endpoint*.

        <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

        <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **DICA**: Caso a tabela não seja preenchida com objetos disponíveis, a [conexão](https://success.jitterbit.com/display/CS/common+connections) pode não ser bem-sucedida. Tenha certeza de que você está conectado(a) reabrindo a conexão e testando novamente as credenciais.

        </div>

        </div>

-   **Save & Exit** (Salvar e Sair): Quando esta opção estiver habilitada, clique para salvar a configuração deste passo e fechar a configuração da atividade.

-   **Next** (Próximo): Clique para armazenar temporariamente a configuração deste passo e continuar para o passo seguinte. A configuração não será salva até você clicar no botão **Finished** (Concluído) no último passo.

-   **Discard Changes** (Descartar Mudanças): Depois de fazer mudanças, clique aqui para fechar a configuração sem salvar as mudanças feitas em nenhum dos passos. Uma mensagem pede que você confirme que quer descartar as mudanças.

### Passo 2: Construa a Sua *Query*

Neste passo, defina as condições de uma *query* usando os campos do objeto e aplique paginação a uma *query*. Todo elemento da interface de usuário desse passo é descrito abaixo.

<span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-query-activity-2.png" class="confluence-embedded-image confluence-external-resource" /></span>

<div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**DICA**: Campos com um ícone de variável <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/variable-icon.png" class="confluence-embedded-image confluence-external-resource" /></span> suportam o uso de [variáveis globais](https://success.jitterbit.com/display/CS/Global+Variables), [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables) e [variáveis Jitterbit](https://success.jitterbit.com/display/CS/Jitterbit+Variables). Comece digitando um colchete esquerdo `[` no campo ou clicando no ícone de variável para exibir uma lista das variáveis existentes para escolher.

</div>

</div>

-   **Search** (Buscar): Escreva qualquer parte do nome de um campo na caixa de pesquisa para filtrar a lista de campos do objeto selecionado. A busca não distingue entre maiúsculas e minúsculas. Os resultados listados são filtrados em tempo real com cada tecla apertada.

-   **Refresh** (Atualizar): Clique no ícone de atualização <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/refresh-icon.png" class="confluence-embedded-image confluence-external-resource" /></span> ou na palavra **Refresh** (Atualizar) para recarregar os campos do objeto do *endpoint* Common.

-   **Select All** (Selecionar Todos): Quando estiver usando a caixa de busca para filtrar, você pode usar essa caixa de seleção para selecionar todos os campos visíveis de uma vez.

-   **Select Fields** (Selecionar Campos): Selecione as caixas de seleção dos campos que você quer que sejam incluídos na *query* para que eles sejam automaticamente adicionados à frase SELECT dentro do campo **Query String**, isto é, a *string* que será usada para fazer a *query*. Você também pode **Select All** (Selecionar Todos) os campos de uma vez usando a caixa de seleção.

-   **Paging** (Paginação): Para adicionar uma cláusula de paginação (um limite no número de registros com a opção de adicionar também um *offset*), você pode usar o menu *dropdown* para definir o limite de paginação e o campo para inserir o *offset*. Caso um *offset* não seja definido, o padrão 0 será aplicado. Apenas uma cláusula de paginação é suportada. Se uma cláusula de paginação não for incluída, todos os registros são retornados.

    -   **Apply** (Aplicar): Clique para construir automaticamente a cláusula com base nas seleções do *dropdown* e no valor inserido. A cláusula de paginação construída automaticamente aparece na caixa de texto chamada **Query String**.

    -   **Remove** (Remover): Clique para remover uma cláusula de paginação que tenha sido aplicada.

-   **Conditions** (Condições): Para adicionar cláusulas condicionais, use os campos abaixo como entrada para ajudar a construir as cláusulas, que aparecem então na caixa de texto chamada **Query String**.

    -   **Object: Field** (Objeto: Campo): Use o menu *dropdown* para selecionar um campo do objeto selecionado.

    -   **Operator** (Operador): Use o menu *dropdown* para selecionar um operador que seja apropriado para o tipo de dado do campo:

        <table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid" resolved="">
          <thead>
            <tr role="row">
              <th class="confluenceTh">Operador</th>
              <th class="confluenceTh">Rótulo</th>
              <th class="confluenceTh">Descrição</th>
            </tr>
            <tr role="row">
              <td class="confluenceTd" colspan="3"></td>
            </tr>
          </thead>
          <tbody aria-live="polite" aria-relevant="all">
            <tr role="row">
              <td class="confluenceTd">=</td>
              <td class="confluenceTd">Igual</td>
              <td class="confluenceTd"></td>
            </tr>
            <tr role="row">
              <td class="confluenceTd">!=</td>
              <td class="confluenceTd">Não-igual</td>
              <td class="confluenceTd"></td>
            </tr>
            <tr role="row">
              <td class="confluenceTd">LIKE 'string'</td>
              <td class="confluenceTd">Como</td>
              <td class="confluenceTd">Como <em>string</em></td>
            </tr>
            <tr role="row">
              <td class="confluenceTd">LIKE 'string%'</td>
              <td class="confluenceTd">Começa com</td>
              <td class="confluenceTd">Começa com <em>string</em></td>
            </tr>
            <tr role="row">
              <td class="confluenceTd">LIKE '%string'</td>
              <td class="confluenceTd">Termina com</td>
              <td class="confluenceTd">Termina com <em>string</em></td>
            </tr>
            <tr role="row">
              <td class="confluenceTd">LIKE '%string%'</td>
              <td class="confluenceTd">Contém</td>
              <td class="confluenceTd">Contém <em>string</em></td>
            </tr>
            <tr role="row">
              <td class="confluenceTd">&lt;</td>
              <td class="confluenceTd">Menor que</td>
              <td class="confluenceTd"></td>
            </tr>
            <tr role="row">
              <td class="confluenceTd">&lt;=</td>
              <td class="confluenceTd">Menor ou igual</td>
              <td class="confluenceTd"></td>
            </tr>
            <tr role="row">
              <td class="confluenceTd">&gt;</td>
              <td class="confluenceTd">Maior que</td>
              <td class="confluenceTd"></td>
            </tr>
            <tr role="row">
              <td class="confluenceTd">&gt;=</td>
              <td class="confluenceTd">Maior ou igual</td>
              <td class="confluenceTd"></td>
            </tr>
          </tbody>
        </table>

    -   **Value** (Valor): Coloque o valor desejado para usar com as seleções do *dropdown*.

        <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

        <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **DICA**: Ao usar variáveis globais nas condições de uma cláusula WHERE, é recomendado que se especifique um valor padrão para que a testagem do* script *seja possível. Caso contrário, já que as variáveis globais recebem seus valores no tempo de execução, a sintaxe pode ser invalidada durante a testagem ou pode ser que nenhum dado seja retornado caso nenhum valor padrão seja especificado.

        </div>

        </div>

    -   **Add** (Adicionar): Clique para construir automaticamente a cláusula com base nas seleções do *dropdown* e do valor inserido. A cláusula condicional é adicionada à caixa de texto chamada **Query String**.

    -   **Remove All** (Remover Tudo): Clique para remover todas as cláusulas condicionais inseridas.

-   **Query String**: À medida que você seleciona campos, especifica condições e define a paginação, a declaração *query* nesta caixa de texto vai sendo preenchida automaticamente com os campos selecionados, as condições e os limites de paginação.

-   **Test Query** (Testar a *Query*): Clique para validar a *query*. Caso ela seja válida, uma amostra de até 10 registros recuperados pela *query* é exibida em uma tabela. Caso a *query* não seja válida, as mensagens de erro relevantes são mostradas. A *query* precisa ser válida e validada por meio deste botão para que o botão **Next** (Próximo) seja habilitado.

    <span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-query-activity-2b.png" class="confluence-embedded-image confluence-external-resource" /></span>

-   **Back** (Voltar): Clique para armazenar temporariamente a configuração deste passo e voltar ao passo anterior.

-   **Next** (Próximo): Clique para armazenar temporariamente a configuração deste passo e seguir para o próximo. A configuração não será salva até você clicar no botão **Finished** (Concluído) no passo seguinte.

-   **Discard Changes** (Descartar Mudanças): Depois de fazer mudanças, clique para fechar a configuração sem salvar as mudanças feitas em nenhum dos passos. Uma mensagem pedirá que você confirme que quer descartar as mudanças.

### Passo 3: Revisar os *Schemas* de Dados

Todos os *schemas* de solicitação ou de resposta gerados pelo *endpoint* são mostrados. Todo elemento da interface de usuário deste passo é descrito abaixo.

<span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-query-activity-3.png" class="confluence-embedded-image confluence-external-resource" /></span>

-   **Data Schemas** (*Schemas* de Dados): Estes *schemas* de dados são herdados de *transformations* adjacentes e são exibidos de novo durante o [mapeamento do *transformation*](https://success.jitterbit.com/display/CS/Transformation+Mapping?showLanguage=pt_BR).

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Dados fornecidos em um *transformation* têm precedência sobre a configuração da atividade.

    </div>

    </div>

    O conector usa uma API REST e um *driver* JDBC. Consulte a documentação da API, conforme disponível, para mais informações sobre os nós e campos do *schema*.

-   **Refresh** (Atualizar): Clique no ícone de atualização <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/refresh-icon.png" class="confluence-embedded-image confluence-external-resource" /></span> ou na palavra **Refresh** para regenerar *schemas* do *endpoint* Common. Esta ação também regenera um *schema* em outros locais espalhados pelo projeto onde o mesmo *schema* é referenciado, como por exemplo, num *transformation* adjacente.

-   **Back** (Voltar): Clique para armazenar temporariamente a configuração deste passo e voltar ao passo anterior.

-   **Finished** (Concluído): Clique para salvar a configuração de todos os passos e fechar a configuração da atividade.

-   **Discard Changes** (Descartar Mudanças): Depois de fazer mudanças, clique para fechar a configuração sem salvar as mudanças feitas em nenhum dos passos. Uma mensagem pedirá que você confirme que quer descartar as mudanças.


## Próximos Passos

Depois de configurar a atividade **Query** de um conector, complete a configuração da operação adicionando ou configurando outras atividades, *transformations* ou *scripts* como etapas de operação. Você também pode definir as configurações da operação, o que inclui a habilidade de encadear operações que estejam no mesmo *workflow* ou em *workflows* diferentes.

As ações de menu de uma atividade ficam disponíveis no painel de projeto e no design canvas. Para mais detalhes, leia a seção [Menu de Ações de Atividade](https://success.jitterbit.com/display/CS/Connector+Basics#ConnectorBasics-actions-menu) no artigo [Informações Básicas sobre Conectores](https://success.jitterbit.com/display/CS/Connector+Basics#ConnectorBasics).

As atividades **Query** podem ser usadas como fonte com os seguintes [padrões de operação](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-valid-operation-patterns):

-   [*Padrão de Transformation*](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-transformation-pattern)

-   [*Padrão de Arquivo com Dois Alvos*](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-two-target-archive-pattern) (apenas como a primeira fonte)

-   [*Padrão de Dois Transformations*](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-two-transformation-pattern) (como a primeira ou segunda fonte)

Um caso de uso típico é mostrado abaixo usando uma atividade **Query** do Dynamics 365 Sales dentro do *Padrão de Dois Transformations*. Neste exemplo, o primeiro *transformation* (*Query Request*) cria uma estrutura de solicitação que é passada para a atividade **Query** do Dynamics 365 Sales. O segundo *transformation* (*Query Response*) recebe a estrutura de resposta, que é então escrita numa variável por uma atividade **Write** Variable (*Write Query Response*) e uma mensagem é então gravada nos registros pelo *script* chamado *Write to Operation Log*:

<span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-query-activity-operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

Para usar a atividade com funções de *script*, grave os dados num local temporário e daí use este local temporário na função de *script*.

Quando estiver tudo pronto, [implante e execute](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution) a operação e valide o comportamento dela verificando os [registros de operação](https://success.jitterbit.com/display/CS/Operation+Logs).
