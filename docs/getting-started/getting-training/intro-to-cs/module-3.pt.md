[//]: # (Módulo 3 - XML para Banco de Dados)
[//]: # (This is a translation of Version 12, published on August 9, 2021.)

## Introdução

O Módulo 3 no curso de treinamento [Introdução ao Jitterbit Harmony
Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio?showLanguage=pt_BR) demonstra como ler dados XML de um servidor SFTP e
colocá-los num banco de dados PostgreSQL.


## Pré-requisitos

Esta página parte do pressuposto de que você completou o [Módulo 1 -
Banco de Dados para Texto](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text?showLanguage=pt_BR), onde você configurou conexões com o banco
de dados PostgreSQL de treinamento e o servidor SFTP da Jitterbit.


## Resumo

Nesse módulo, você vai se conectar ao servidor SFTP de treinamento para
puxar registros do arquivo `customer.xml` e adicioná-los à tabela
`customer` no banco de dados PostgreSQL.

A operação completa ficará assim:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_xml-to-db.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_xml-to-db.png" /></span>

Esta operação usa o seguinte mapeamento de *transformation*:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/xml-to-db.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/xml-to-db.png" /></span>


## 1. Baixar um *Schema* XML

Primeiro, baixe um arquivo XML para fornecer como *schema* em um outro
passo mais à frente:

1.  Faça *login* no <a href="https://learningsandbox.jitterbit.com/WebInterface/login.html"
    class="external-link" rel="nofollow">servidor SFTP de treinamento da Jitterbit</a>.

2.  No diretório `DataSets` \> `Customer`, baixe o arquivo
    `customer.xml`.


## 2. Configurar uma Atividade FTP

Para este módulo, você vai continuar trabalhando dentro do mesmo projeto
e reusar a mesma conexão com servidor SFTP do Módulo 1, mas vai
configurar uma atividade FTP Read separada para puxar os dados XML do
servidor:

1.  Dentro do mesmo projeto do Módulo 1, crie um novo workflow e dê a
    ele o nome de "Módulo 3".

2.  Na aba **Connectivity** (Conectividade) da paleta de componentes sob
    o filtro **Endpoints**, clique na conexão "SFTP" que você criou no
    Módulo 1 para mostrar os tipos de atividade da conexão:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png" /></span>

3.  Arraste um tipo de atividade FTP Read para a zona de inserção de
    componentes no design canvas para criar uma instância de uma
    atividade FTP Read em uma nova operação.

4.  Mude o nome da operação para "XML para DB".

5.  Clique duas vezes sobre a atividade FTP Read dentro da operação para
    abrir a configuração dela.

6.  Configure a [atividade FTP Read](https://success.jitterbit.com/display/CS/FTP+Read+Activity?showLanguage=pt_BR):

    -   **Name** (Nome): "XML SFTP"

    -   **Provide Response Schema** (Fornecer *Schema* de Resposta):
        Selecione a opção **Yes, Provide New Schema** (Sim, Fornecer Novo
        *Schema*) e clique em **Upload File** (Carregar Arquivo) para
        encontrar e carregar o arquivo `customer.xml` que você baixou do
        servidor SFTP de treinamento.

    -   **Path** (Caminho): Forneça o caminho até o arquivo `customer.xml`
        no servidor SFTP de treinamento: "/DataSets/Customer"

    -   **Get Files** (Pegar Arquivos): "\*.xml". Clique em **Next**
        (Próximo).

    -   **Data Schema** (*Schema* de Dados): Revise o *schema* de dados e
        clique em **Finished** (Concluído) para voltar para o design
        canvas.

A tela final de configuração da atividade ficará parecida com a imagem
abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/ftp_read_step-2_data-schema.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/ftp_read_step-2_data-schema.png" /></span>


## 3. Configurar uma Atividade de Banco de Dados

Neste passo, você vai usar a mesma conexão com o banco de dados
PostgreSQL que usou no Módulo 1, mas vai configurar uma atividade Upsert
separada:

1.  Na aba **Connectivity** (Conectividade) da paleta de componentes e
    sob o filtro **Endpoints**, clique sobre a conexão "Banco de Dados
    Postgres" que você criou no Módulo 1 para mostrar os tipos de
    atividade da conexão:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png" /></span>

2.  Arraste uma atividade Database Upsert para uma zona de inserção de
    componentes à direita da atividade FTP Read dentro da operação no
    design canvas.

3.  Clique duas vezes sobre a atividade Database Upsert dentro da
    operação para abrir a configuração dela.

4.  Configure a [atividade Database Upsert](https://success.jitterbit.com/display/CS/Database+Update+or+Upsert+Activity?showLanguage=pt_BR):

-   **Name** (Nome): "Upsert para BD Postgres"

-   **Provide the Table Names Reference** (Fornecer a Referência dos
    Nomes de Tabela): Atualize as tabelas e selecione a tabela
    "customer". Clique em **Next** (Próximo).

-   **Select Update Keys** (Selecione as Chaves de Atualização): Limpe o
    campo `id` (Chave) e selecione o campo `company`. Clique em
    **Next** (Próximo).

-   **Data Schema** (*Schema* de Dados): Revise o *schema* de dados e
    clique em **Finished** (Concluído) para voltar ao design canvas.

A última tela da configuração de atividade deve ficar parecida com a
imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_customer.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_customer.png" /></span>


## 4. Configurar o *Transformation*

A seguir, crie um *transformation* para transformar dados da fonte FTP
para o banco de dados alvo:

1.  No design canvas, paire o mouse sobre a área entre a atividade FTP
    Read e a atividade Database Upsert até aparecer uma zona de
    inserção de componentes.

2.  Clique sobre a zona de inserção e selecione **New Transformation**
    (Novo *Transformation*). Uma novo *transformation* vai abrir para
    que você a configure:

    -   **Transformation Name** (Nome do *Transformation*): "XML para DB"

    -   **Source** (Fonte): O *schema* fonte já é fornecido (à esquerda).

    -   **Target** (Alvo): O *schema* alvo já é fornecido (à direita).

3.  Arraste o nó fonte `customer` até o nó alvo `customer` e selecione
    **Automap** (Mapeamento Automático).

4.  No topo do cabeçalho do *transformation*, clique no botão cinza que
    diz **Preview** (Pré-Visualização) para começar o processo de
    testar e validar os mapeamentos. Clique em **Next** (Próximo) para
    implantar os componentes listados. Na tela seguinte, selecione
    **Upload New File to Test** (Carregar Novo Arquivo para Testar) e
    forneça o arquivo `customer.xml` que você baixou antes. Clique em
    **Finished** (Concluído).

5.  A tela de pré-visualização exibe dados populados da fonte e mapeados
    para o alvo. Clique nas setas à esquerda e à direita para
    transitar pelos dados importados.

6.  Depois de revisar os dados, clique em **Return to Workflow** (Voltar
    para o Workflow). Clicar neste botão salva o trabalho que você fez
    no *transformation*.

A pré-visualização do *transformation* deve ficar parecida com a imagem
abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/preview-mode/xml-to-db.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/preview-mode/xml-to-db.png" /></span>


## 5. Implantar e Executar a Operação

Finalmente, com todas as etapas da operação configuradas, basta
implantar e executar a operação:

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

2.  Uma vez que a operação tenha sido bem sucedida, faça *login* no
    <a href="https://training.jitterbit.com/DB/dbViewer.php"
    class="external-link" rel="nofollow">banco de dados PostgreSQL da Jitterbit</a> e visualize os
    recursos adicionais na tabela de clientes.
