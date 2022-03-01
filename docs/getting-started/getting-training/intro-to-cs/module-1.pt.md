[//]: # (Módulo 1 - Banco de Dados para Texto)
[//]: # (This is a translation of Version 11, published on August 9, 2021.)

## Introdução

O Módulo 1 do curso de treinamento [Introdução ao Jitterbit Harmony
Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio?showLanguage=pt_BR) demonstra como fazer uma *query* dos dados de uma única
tabela num banco de dados PostgreSQL e escrevê-los num servidor SFTP
como arquivo de texto *flat*.


## Pré-requisitos

Estes módulos partem do pressuposto de que você se registrou no
Jitterbit Learning Sandbox conforme previsto como parte do curso de
treinamento [Introdução ao Jitterbit Harmony Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio?showLanguage=pt_BR). O
registro no Jitterbit Learning Sandbox provê acesso à organização de
treinamento do Jitterbit Harmony, o que inclui dois ambientes, assim
como contas no servidor SFTP de treinamento da Jitterbit e no banco de
dados PostgreSQL.

Se você não tiver esses acessos, consulte a página [Como Receber
Treinamento](https://success.jitterbit.com/display/DOC/Getting+Training?showLanguage=pt_BR) para se cadastrar na Jitterbit University (Universidade
Jitterbit), daí matricule-se no curso [Introdução ao Jitterbit Harmony
Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio?showLanguage=pt_BR). O registro no Learning Sandbox é ensinado no Capítulo
4 – Registro no Learning Sandbox.


## Resumo

Neste módulo, você vai se conectar com a tabela "customer" (cliente) do
banco de dados PostgreSQL de treinamento, criar um arquivo CSV com
campos similares e escrever esses dados no servidor SFTP de treinamento.

A operação completa vai ficar assim:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_db-to-text.png" /></span> 

Esta operação usa o seguinte mapeamento de *transformation*:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-text.png" /></span>


## 1. Criar um Novo Projeto

Todos os módulos cobertos neste curso são criados em um único projeto.
Antes de começar o primeiro módulo, crie um projeto:

1.  Faça *login* no [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR) em
    [https://login.jitterbit.com](https://login.jitterbit.com)
    e opte pela organização Jitterbit Learning Sandbox na parte
    superior direita do cabeçalho.

2.  Clique no cartão da aplicação Cloud Studio.

3.  No índice de projetos, clique em **New Project** (Novo Projeto). Dê
    um nome ao projeto, tal como "Exemplos da Jitterbit University", e
    selecione o ambiente.

4.  Quando estiver dentro do projeto, mude o nome do workflow para
    "Módulo 1".

    <div
    class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
    hasbody="true" macro-name="tip">

    <span
    class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **DICA:** Aderir às convenções de nomenclatura da sua organização
    para os workflows, operações e componentes é uma boa prática que
    recomendamos.

    </div>

    </div>


## 2. Configurar uma Conexão com Banco de Dados

Para este módulo, a primeira coisa a fazer é estabelecer uma conexão com
o banco de dados PostgreSQL de treinamento:

1.  Na aba **Connectivity** (Conectividade) da [paleta de componentes
    de *design*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR) sob o filtro **Connectors** (Conectores), clique
    no conector Database (Banco de Dados):

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_database.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_database.png" /></span>

2.  Configure a [conexão com o Banco de Dados](https://success.jitterbit.com/display/CS/Database+Connection?showLanguage=pt_BR):

    -   **Endpoint Name** (Nome do *Endpoint*): "Banco de Dados Postgres"

    -   **Driver**: "PostgreSQL"

    -   **Server Name** (Nome do Servidor): "learningsandbox.jitterbit.com"

    -   **Database Name** (Nome do Banco de Dados), **Login**, **Password**
        (Senha): Estas credenciais são das informações que você forneceu
        quando completou o formulário de registro no Learning Sandbox.
        Estas informações podem ser encontradas no e-mail de confirmação
        do Learning Sandbox.

    -   **Port** (Porta): Não é necessário fazer nenhuma mudança do padrão.

    <div
    class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
    hasbody="true" macro-name="tip">

    <span
    class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **DICA:** Os Cloud Agents podem usar apenas *drivers* JDBC, enquanto
    os Private Agents podem usar *drivers* JDBC ou ODBC.

    </div>

    </div>

3.  Clique em **Test** (Testar) na parte de baixo da configuração para
    verificar a conectividade.

4.  Uma vez conectado(a), clique em **Save Changes** (Salvar Mudanças).
    Esta ação levará você de volta ao design canvas.

A conexão "Banco de Dados Postgres" tem uma configuração similar à
imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/database_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/database_connection.png" /></span>


## 3. Configurar uma Atividade de Banco de Dados

Agora, você deve configurar uma atividade para fazer uma *query* de
dados do banco PostgreSQL:

1.  Na aba **Connectivity** da paleta de componentes sob o filtro
    **Endpoints**, clique na conexão "Banco de Dados Postgres" que
    você acabou de criar para mostrar os tipos de atividade da
    conexão:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png" /></span>

2.  Arraste o tipo de atividade Query até a zona de inserção de
    componentes no design canvas para criar uma instância de uma
    atividade Database Query numa nova operação.

3.  Mude o nome da operação para "BD para Texto".

4.  Clique duas vezes sobre a atividade Query dentro da operação para
    abrir as configurações dela.

5.  Configure a [atividade Database Query](https://success.jitterbit.com/display/CS/Database+Query+Activity?showLanguage=pt_BR):

    -   **Name** (Nome): "Fazer uma Query na Tabela Customer"

    -   **Select Table(s)** (Selecionar Tabela\[s\]): Atualize as tabelas e
        selecione a tabela `customer` (cliente). Clique em **Next**
        (Próximo).

    -   **Select Fields** (Selecionar Campos): Selecione os campos `id`, que
        deverá ser o campo-chave, `company` (empresa), `address`
        (endereço), `city` (cidade), `state` (estado), `zip` (CEP),
        `country` (país), `phone` (telefone) e `fax`. Clique em **Next**
        (Próximo).

    -   **Data Schema** (*Schema* de Dados): Revise o *schema* de dados e
        clique em **Finished** (Concluído) para voltar ao design canvas.

A tela final da configuração da atividade deverá ficar similar à imagem
abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_customer.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_customer.png" /></span>


## 4. Configurar uma Conexão FTP

A seguir, você deverá configurar uma conexão com o servidor SFTP de
treinamento:

1.  Na aba **Connectivity** da paleta de componentes, sob o filtro
    **Connectors**, clique sobre o conector FTP:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_ftp.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_ftp.png" /></span>

2.  Configure a [conexão FTP](https://success.jitterbit.com/display/CS/FTP+Connection?showLanguage=pt_BR):

    -   **Endpoint Name** (Nome do *Endpoint*): "SFTP"

    -   **Host** (Anfitrião): "<a href="http://learningsandbox.jitterbit.com" class="external-link"
        rel="nofollow">learningsandbox.jitterbit.com</a>"

    -   **Username** (Nome de Usuário) e **Password** (Senha): Estas
        credenciais são das informações que você forneceu ao completar o
        formulário de registro no Learning Sandbox. Estas informações
        podem ser encontradas no e-mail de confirmação do Learning
        Sandbox.

3.  Clique em **Test** (Testar) para verificar a conectividade e clique
    em **Save Changes** (Salvar Mudanças) ao terminar.

A conexão FTP deve ficar parecida com a imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/ftp_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/ftp_connection.png" /></span>


## 5. Configurar uma Atividade FTP

Quando a configuração FTP estiver configurada, você pode configurar uma
atividade FTP Write associada com essa conexão:

1.  Na aba **Connectivity** da paleta de componentes sob o filtro
    **Endpoints**, clique na conexão "SFTP" que você acabou de criar
    para mostrar os tipos de atividade da conexão:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png" /></span>

2.  Arraste uma atividade FTP Write para uma área de inserção de
    componentes à direita da atividade Database Query dentro da
    operação no design canvas.

3.  Clique duas vezes na atividade FTP Write dentro da operação para
    abrir as configurações dela.

4.  Configure a [atividade FTP Write](https://success.jitterbit.com/display/CS/FTP+Write+Activity?showLanguage=pt_BR):

    -   **Name** (Nome): "Escrever Registros de Clientes"

    -   **Path** (Caminho): "/"

    -   **Filename(s)** (Nome do\[s\] Arquivo\[s\]):
        "resultado\_\[date\]\_\[time\].csv". Clique em **Next** (Próximo).

    -   **Data Schema** (*Schema* de Dados): Já que você não forneceu um
        *schema*, não há nada para revisar na segunda tela. Clique em
        **Finished** (Concluído).


## 6. Configurar um *Transformation*

A seguir, crie um *transformation* para transformar dados do banco fonte
para o alvo FTP:

1.  No design canvas, paire o mouse sobre a área entre a atividade
    Database Query e a atividade FTP Write até aparecer uma área de
    inserção de componentes.

2.  Clique na área de inserção e selecione **New Transformation** (Novo
    *Transformation*). Um novo *transformation* vai aparecer para que
    você o configure:

    -   **Transformation Name** (Nome do *Transformation*): "DB para Texto"

    -   **Source** (Fonte): O *schema* fonte já é fornecido (à esquerda).

    -   **Target** (Alvo): Você precisa definir o *schema* alvo (à direita).
        Clique em **Define Schema** (Definir *Schema*), daí selecione
        **Create Flat** (Criar *Flat*). Configure o [*flat schema*
        customizado](https://success.jitterbit.com/display/CS/Custom+Flat+Schema?showLanguage=pt_BR):

        -   **Schema Name** (Nome do *Schema*): "CSV de Clientes"

        -   **Add Field** (Adicionar Campo): Use este botão para adicionar
            os seguintes campos: `id`, `Customer` (cliente), `Address`
            (endereço), `City` (cidade), `State` (estado), `ZipCode`
            (CEP), `Country` (país), `Phone` (telefone) e `Fax`. Quando os
            campos estiverem adicionados, clique em **Save Changes**
            (Salvar Mudanças).

3.  Na parte superior direita do *schema* alvo, clique em **Automap
    Exact Matches** (Mapear Automaticamente Campos Iguais).

4.  Mapeie manualmente (arrastando e soltando) os campos que não têm
    nomes exatamente iguais e não foram detectados pelo mapeamento
    automático; associe `company` com `Customer` e `zip` com
    `ZipCode`.

5.  No topo do cabeçalho do *transformation*, clique no botão cinza que
    diz **Preview** (Pré-Visualização) para começar o processo de
    testar e validar os mapeamentos. Clique em **Next** (Próximo) para
    implantar os componentes listados e daí clique em **Finished**
    (Concluído).

6.  A tela de pré-visualização exibe dados trazidos a partir da fonte e
    mapeados para o alvo. Clique nas flechas da esquerda e da direita
    para navegar pelos dados importados.

7.  Depois de revisar os dados, clique em **Return to Workflow** (Voltar
    para o Workflow). Clicar neste botão salva o trabalho que você fez
    no *transformation*.

A configuração do *flat schema* customizado deve ficar parecida com a
imagem abaixo:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/schema/customer-csv.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/schema/customer-csv.png" /></span>

A pré-visualização do *transformation* deverá ficar parecida com a
imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-text.png" /></span>


## 7. Implantar e Executar a Operação

Finalmente, com todas as etapas de operação configuradas, você implanta
e executa a operação:

1.  Na parte superior direita da operação, clique no ícone do menu de
    ações <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> e, no
    menu, clique em **Deploy and Run** (Implantar e Executar). O
    *status* da operação é exibido na parte inferior esquerda da
    operação.

2.  Uma vez que a operação tenha sido bem-sucedida, faça *login* no
    <a href="https://learningsandbox.jitterbit.com/WebInterface/login.html"
    class="external-link" rel="nofollow">servidor SFTP de treinamento da Jitterbit</a> e visualize o
    arquivo que você gerou.
