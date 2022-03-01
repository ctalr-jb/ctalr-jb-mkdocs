[//]: # (Módulo 4 - Serviço Web SOAP)
[//]: # (This is a translation of Version 11, published on August 9, 2021.)

## Introdução

O Módulo 4 no curso de treinamento [Introdução ao Jitterbit Harmony
Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio?showLanguage=pt_BR) demonstra como executar uma *query* em um serviço web
SOAP e escrever a resposta num servidor SFTP como arquivo de texto.


## Pré-requisitos

Esta página parte do pressuposto de que você completou o [Módulo 1 -
Banco de Dados para Texto](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text?showLanguage=pt_BR), onde você configurou uma conexão com o
servidor SFTP de treinamento da Jitterbit.


## Resumo

Neste módulo, você fará uma chamada SOAP usando uma WSDL que nós
forneceremos para executar uma *query* em um serviço de clima baseado em
códigos postais (CEPs), e daí escrever estes dados no servidor SFTP de
treinamento como arquivo de texto.

A operação completa ficará parecida com a imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-soap.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-soap.png" /></span>

Esta operação usa os seguintes mapeamentos de *transformation* de
solicitação e resposta:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-request.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-request.png" /></span>

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-response.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-response.png" /></span>


## 1. Configurar uma Conexão e Atividade SOAP

Neste módulo, você continuará trabalhando dentro do mesmo projeto do
Módulo 1, e vai criar uma nova conexão e atividade SOAP:

1.  Dentro do mesmo projeto do Módulo 1, crie um novo workflow e dê a
    ele o nome "Módulo 4".

2.  Na aba **Connectivity** (Conectividade) da paleta de componentes e
    sob o filtro **Connectors** (Conectores), clique no conector SOAP:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_soap.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_soap.png" /></span>

    <div
    class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
    hasbody="true" macro-name="tip">

    <span
    class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **DICA**: SOAP (Simple Object Access Protocol, ou seja, Protocolo de
    Acesso a Objetos Simples) é um protocolo baseado em padrões bem
    estabelecido para acessar serviços web.

    </div>

    </div>

3.  Configure a [conexão SOAP](https://success.jitterbit.com/display/CS/SOAP+Connection?showLanguage=pt_BR):

    -   **Endpoint Name** (Nome do *Endpoint*): "CEP – SOAP"

    -   **Upload URL** (Carregar URL): Cole a URL deste arquivo WSDL (Web
        Service Definition Language, ou seja, Linguagem de Definição de
        Serviços Web):
        "[https://trainingoptrial112860.jitterbit.net/TrainingOpsCloud/v1/SOAP_Service/?WSDL](https://trainingoptrial112860.jitterbit.net/TrainingOpsCloud/v1/SOAP_Service/?WSDL)".
        Clique em **Upload** (Carregar).

    -   **Port** (Porta): Selecione "ZipCodeSoap".

    -   **Web Service URL** (URL do Serviço Web): Este campo será
        automaticamente preenchido a partir da WSDL que você carregou
        acima.

    -   **Select Methods** (Selecionar Métodos): Selecione "ZipCode". Clique
        em **Save Changes** (Salvar Mudanças).

4.  Na aba **Connectivity** (Conectividade) da paleta de componentes e
    sob o filtro **Endpoints**, clique na conexão "CEP – SOAP" que
    você acabou de criar. Isto mostrará o tipo de atividade SOAP do
    método que você selecionou enquanto configurava a conexão SOAP:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_soap_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_soap_activities.png" /></span>

5.  Arraste o tipo de atividade SOAP até uma zona de inserção de
    componentes no design canvas para criar uma instância de uma
    atividade SOAP em uma nova operação.

6.  Mude o nome da operação para "CEP – SOAP". Você não precisa abrir a
    atividade SOAP para configurá-la porque ela já configurou
    automaticamente com todas as informações necessárias.

A conexão SOAP deverá ter uma tela de configuração similar à imagem
abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/soap_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/soap_connection.png" /></span>


## 2. Configurar uma Atividade FTP

Nesta etapa, você usará a mesma conexão com o servidor SFTP que usou no
Módulo 1, mas configurando uma atividade FTP Write separada:

1.  Na aba **Connectivity** (Conectividade) da paleta de componentes e
    sob o filtro **Endpoints**, clique na conexão "SFTP" que você
    criou no Módulo 1 para mostrar os tipos de atividade da conexão:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png" /></span>

2.  Arraste uma atividade FTP Write até uma zona de inserção de
    componentes à direita da atividade SOAP dentro da operação no
    design canvas.

3.  Clique duas vezes sobre a atividade FTP Write dentro da operação
    para abrir a configuração dela.

4.  Configure a [atividade FTP Write](https://success.jitterbit.com/display/CS/FTP+Write+Activity?showLanguage=pt_BR):

    -   **Name** (Nome): "Dados do CEP"

    -   **Filename(s)** (Nome do\[s\] Arquivo\[s\]): "zipCode.txt"

    -   **Use FTP Rename** (Usar o Renomeamento FTP): Desmarque esta opção.
        Clique em **Next** (Próximo).

    -   **Data Schema** (*Schema* de Dados): Já que você não forneceu um
        *schema*, não há nada para revisar na segunda tela. Clique em
        **Finished** (Concluído).


## 3. Configurar um *Transformation* de Solicitação

Agora, você criará um *transformation* para a solicitação do serviço web
SOAP:

1.  No design canvas, paire o mouse sobre a área à esquerda da atividade
    SOAP até que uma zona de inserção de componentes apareça.

2.  Clique na zona de inserção e selecione **New Transformation** (Novo
    *Transformation*). Uma novo *transformation* vai aparecer para que
    você o configure:

    -   **Transformation Name** (Nome do *Transformation*): "CEP –
        Solicitação SOAP"

    -   **Source** (Fonte): Deixe o *schema* fonte indefinido (à esquerda).

    -   **Target** (Alvo): Dentro do *schema* alvo (à direita), paire o
        mouse sobre o campo `ZipField` e clique no ícone de adição
        <span
        class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/add_2.png"
        class="confluence-embedded-image confluence-external-resource"
        data-image-src="https://docs-source.jitterbit.com/common/icons/add_2.png"
        height="24" /></span>.
        No menu, clique em **Add Custom Value** (Adicionar Valor
        Customizado). Daí, coloque um CEP dos Estados Unidos na área de
        texto. Clique em **Return to Workflow** (Voltar para o Workflow).

O *transformation* de solicitação deverá ficar similar à imagem abaixo:


<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-request.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-request.png" /></span>


## 4. Configurar um *Transformation* de Resposta

Agora, você precisa criar um *transformation* para escrever a resposta
do serviço web SOAP no alvo FTP:

1.  No design canvas, paire o mouse sobre a área entre a atividade SOAP
    e a atividade FTP Write até que uma zona de inserção de
    componentes apareça.

2.  Clique na zona de inserção e selecione **New Transformation** (Novo
    *Transformation*). Um novo *transformation* vai aparecer para que
    você o configure:

    -   **Transformation Name** (Nome do *Transformation*): "CEP – Resposta
        SOAP"

    -   **Source** (Fonte): O *schema* fonte já é fornecido (à esquerda).

    -   **Target** (Alvo): Você precisa definir o *schema* alvo (à direita).
        Clique em **Define Schema** (Definir *Schema*), daí selecione
        **Create Flat** (Criar *Flat*). Configure o [*schema flat*
        customizado](https://success.jitterbit.com/display/CS/Custom+Flat+Schema?showLanguage=pt_BR):

        -   **Schema Name** (Nome do *Schema*): "Dados do CEP"

        -   **Options** (Opções): Mude o **Delimiter** (Delimitador) para
            que não seja mais uma vírgula, e sim um recuo de parágrafo
            inserindo "\\t".

        -   **Add Field** (Adicionar Campo): Use este botão para adicionar
            os seguintes campos: `zip` (CEP), "type" (tipo), "state"
            (estado), "primaryCity" (cidade primária), "county" (condado),
            "timeZone" (fuso horário), "areaCodes" (códigos de área),
            "country" (país) e "population" (população). Quando os campos
            tiverem sido adicionados, clique em **Save Changes** (Salvar
            Mudanças).

3.  Arraste o nó fonte `zipCodeResponse` até o nó alvo `__flat__` e
    selecione **Automap** (Mapeamento Automático). Daí clique em
    **Return to Workflow** (Voltar para o Workflow).

A configuração do *schema flat* customizado deve ficar parecida com a
imagem abaixo:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/schema/zip-code-data.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/schema/zip-code-data.png" /></span>

O *transformation* da solicitação deverá ficar mais ou menos assim:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-response.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-response.png" /></span>


## 5. Implantar e Executar a Operação

Finalmente, com todos os passos de operação configurados, implante e
execute a operação:

1.  Na parte superior direita da operação, clique no ícone do menu de
    ações <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> e, no
    menu que aparecer, clique em **Deploy and Run** (Implantar e
    Executar). O *status* da operação é exibido na parte inferior
    esquerda da operação.

2.  Uma vez que a operação tiver sido bem sucedida, faça *login* no
    <a href="https://learningsandbox.jitterbit.com/WebInterface/login.html"
    class="external-link" rel="nofollow">servidor SFTP de treinamento da Jitterbit</a> e visualize o
    arquivo que você gerou.
