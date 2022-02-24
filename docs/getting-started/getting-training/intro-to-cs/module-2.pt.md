[//]: # (Módulo 2 - Banco de Dados para XML Complexo)
[//]: # (This is a translation of Version 9, published on August 9, 2021.)

## Introdução

O Módulo 2 do curso de treinamento [Introdução ao Jitterbit Harmony
Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio?showLanguage=pt_BR) demonstra como fazer uma *query* de dados de várias
tabelas num banco de dados PostgreSQL e escrevê-los em um servidor SFTP
em formato XML hierárquico.


## Pré-requisitos

Esta página parte do pressuposto de que você completou o [Módulo 1 -
Banco de Dados para Texto](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text?showLanguage=pt_BR), onde você configurou conexões com o banco
de dados PostgreSQL de treinamento e o servidor SFTP da Jitterbit.


## Resumo

Neste módulo, você vai usar o banco de dados PostgreSQL para se conectar
com as tabelas `OrderDetail` e `OrderHeader`. Uma vez conectado(a), você
vai fundir os dados e escrevê-los em formato hierárquico no servidor
SFTP de treinamento.

A operação completa terá esta aparência:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_db-to-xml.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_db-to-xml.png" /></span>

Esta operação usa o seguinte mapeamento de *transformation*:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-xml.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-xml.png" /></span>


## 1. Configurar uma Atividade de Banco de Dados

Para este módulo, você vai continuar trabalhando dentro do mesmo projeto
e vai reusar a mesma conexão "Banco de Dados Postgres" que usou no
Módulo 1, porém vai configurar uma nova atividade Query para extrair
dados diferentes do banco de dados:

1.  Dentro do mesmo projeto do Módulo 1, crie um novo workflow e dê a
    ele o nome "Módulo 2".

2.  Na aba **Connectivity** (Conectividade) da paleta de componentes e
    sob o filtro **Endpoints**, clique na conexão "Banco de Dados
    Postgres" que você criou no Módulo 1 para mostrar os tipos de
    atividade da conexão:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png" /></span>

3.  Arraste um tipo de atividade Query até a área de inserção de
    componentes no design canvas para criar uma instância de uma
    atividade Database Query numa nova operação.

4.  Mude o nome da operação para "BD para XML".

5.  Clique duas vezes sobre a atividade Query dentro da operação para
    abrir a configuração dela.

6.  Configure a [atividade Database Query](https://success.jitterbit.com/display/CS/Database+Query+Activity?showLanguage=pt_BR):

    -   **Name** (Nome): "Executar Query nas Tabelas OrderHeader e
        OrderDetail"

    -   **Select Table(s)** (Selecionar Tabela\[s\]): Atualize as tabelas e
        selecione as tabelas `OrderHeader` e `OrderDetail`. Daí, dentro da
        fileira `OrderDetail`:

        -   **Parent** (Mãe): Use o menu *dropdown* para selecionar
            `OrderHeader`.

        -   **Link Keys** (Chaves de Ligação): Clique em **Assign**
            (Atribuir). Quando surgir o *popup*, arraste `OrderID` na
            tabela mãe para `OrderID` na tabela filha. Clique em
            **Finished** (Concluído).

        -   **Join Type** (Tipo de Junção): Este campo fica disponível após
            você ter feito a atribuição das chaves de ligação. Use o menu
            *dropdown* para selecionar **Zero or More** (Zero ou Mais).
            Clique em **Next** (Próximo).

    -   **Source** (Fonte): **PostgreSQL**: Marque a caixa ao lado de
        `OrderHeader` para incluir todos os campos na sua *query*.

    -   **Data Schema** (*Schema* de Dados): Revise o *schema* de dados e
        clique em **Finished** (Concluído) para voltar ao design canvas.

A tela final da configuração de atividade deverá ficar parecida com a
imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_order.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_order.png" /></span>


## 2. Configurar uma Atividade FTP

Além de reutilizar a conexão Database, você também pode reusar a conexão
FTP do Módulo 1. Nesta etapa, você usa a mesma conexão com o servidor de
treinamento SFTP, mas configura uma atividade Write separada:

1.  Na aba **Connectivity** da paleta de componentes e sob o filtro
    **Endpoints**, clique na conexão "SFTP" que você criou no Módulo 1
    para mostrar os tipos de atividade da conexão:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png" /></span>

2.  Arraste um tipo de atividade FTP Write para uma zona de inserção de
    componentes à direita da atividade Database Query dentro da
    operação no design canvas.

3.  Clique duas vezes sobre a atividade FTP Write dentro da operação
    para abrir a configuração dela.

4.  Configure a [atividade FTP Write](https://success.jitterbit.com/display/CS/FTP+Write+Activity?showLanguage=pt_BR):

    -   **Name** (Nome): "XML SFTP"

    -   **Path** (Caminho): "/"

    -   **Filename (s)** (Nome do Arquivo\[s\]):
        "resultado\_\[date\]\_\[time\].xml". Clique em **Next** (Próximo).

    -   **Data Schema** (*Schema* de Dados): Já que você não forneceu um
        *schema*, não há nada para revisar na segunda tela. Clique em
        **Finished** (Concluído).


## 3. Configurar um *Transformation*

A seguir, crie um *transformation* para transformar dados do banco de
dados fonte para o alvo FTP:

1.  No design canvas, paire o mouse sobre a área entre a atividade
    Database Query e a atividade FTP Write até que apareça uma zona de
    inserção de componentes.

2.  Clique sobre a zona de inserção e selecione **New Transformation**
    (Novo *Transformation*). Um novo *transformation* abrirá para que
    você a configure:

    -   **Transformation Name** (Nome do *Transformation*): "BD para XML"

    -   **Source** (Fonte): O *schema* fonte já é fornecido (à esquerda).

    -   **Target** (Alvo): Você precisa definir o *schema* alvo (à direita).
        Clique em **Mirror Source Schema** (Espelhar *Schema* Fonte) para
        replicar a estrutura do banco de dados no XML.

3.  Arraste o nó fonte `OrderHeader` para o nó alvo `row` e selecione
    **Automap** (Mapear Automaticamente).

    <div
    class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
    hasbody="true" macro-name="tip">

    <span
    class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **DICA:** As linhas pretas sólidas que são exibidas entre os nós
    fonte e alvo são chamadas de *linhas iteradoras*. Estas linhas indicam
    que o mapeamento suporta vários registros (instâncias).

    </div>

    </div>

4.  No topo do cabeçalho do *transformation*, clique no botão cinza que
    diz **Preview** (Pré-visualização) para começar o processo de
    testar e validar os mapeamentos. Clique em **Next** (Próximo) para
    implantar os componentes listados e daí clique em **Finished**
    (Concluído).

5.  A tela de pré-visualização exibe dados populados da fonte e mapeados
    para o alvo. Clique nas setas à esquerda e à direita para
    transitar pelos dados importados.

6.  Após revisar os dados, clique em **Return to Workflow** (Voltar para
    o Workflow). Clicar neste botão salva o trabalho que você fez no
    *transformation*.

A pré-visualização do *transformation* deve ficar parecida com a imagem
abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-xml.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-xml.png" /></span>


## 4. Implantar e Executar a Operação

Finalmente, com todos estas etapas de operação configuradas, você
implanta e executa a operação:

1.  Na parte superior direita da operação, clique no ícone do menu de
    ações <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> e, no
    menu, clique no botão **Deploy and Run** (Implantar e Executar). O
    *status* da operação é exibido na parte inferior esquerda da
    operação.

2.  Uma vez que a operação tenha sido bem sucedida, faça *login* no
    <a href="https://learningsandbox.jitterbit.com/WebInterface/login.html"
    class="external-link" rel="nofollow">servidor SFTP de treinamento da Jitterbit</a> e veja o arquivo
    que você gerou.
