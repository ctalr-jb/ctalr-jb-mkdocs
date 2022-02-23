[//]: # (Módulo 5 - Serviço Web RESTful)
[//]: # (This is a translation of Version 10, published on August 9, 2021.)

## Introdução

O Módulo 5 no curso de treinamento [Introdução ao Jitterbit Harmony
Cloud Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio) demonstra como fazer uma *query* a um serviço web REST
e escrever a resposta num servidor SFTP como arquivo de texto.


## Pré-requisitos

Esta página parte do pressuposto de que você completou o [Módulo 1 -
Banco de Dados para Texto](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text), onde você configurou uma conexão com o
servidor SFTP de treinamento da Jitterbit. Ela também requer que você
tenha completado o [Módulo 4 - Serviço Web SOAP](https://success.jitterbit.com/display/DOC/Module+4+-+SOAP+Web+Service), já que ela
reutiliza vários componentes de projeto deste módulo.


## Resumo

Neste módulo, você fará uma *query* a um serviço web RESTful de clima
baseado em CEP, e daí escreverá os dados no servidor SFTP de treinamento
como arquivo de texto.

A operação completa ficará parecida com a imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest.png" /></span>

Esta operação usa o seguinte mapeamento de *transformation*:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-rest-response.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-rest-response.png" /></span>


## 1. Configurar uma Conexão HTTP

Para este módulo, você vai continuar trabalhando dentro do mesmo projeto
do Módulo 1, e vai criar uma nova conexão SOAP:

1.  Dentro do mesmo projeto do Módulo 1, crie um novo workflow e dê a
    ele o nome “Módulo 5”.

2.  Na aba **Connectivity** (Conectividade) da paleta de componentes e
    sob o filtro **Connectors** (Conectores), clique no conector HTTP:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_http_single.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_http_single.png" /></span>

3.  Configure a [conexão HTTP](https://success.jitterbit.com/display/CS/HTTP+Connection):

    -   **Endpoint Name** (Nome do *Endpoint*): “CEP - REST”

    -   **Base URL** (URL Base): Cole a URL base deste serviço:
        “https://trainingoptrial112860.jitterbit.net/TrainingOpsCloud/v1/REST_Service/”.

4.  Clique em **Save Changes** (Salvar Mudanças).

A conexão HTTP deverá ser parecida com a imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/http_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/http_connection.png" /></span>


## 2. Configurar uma Atividade HTTP

Agora, configure uma atividade associada com a conexão HTTP para obter
os dados do serviço web:

1.  Na aba **Connectivity** (Conectividade) da paleta de componentes e
    sob o filtro **Endpoints**, clique na conexão “CEP - REST” que
    você acabou de criar:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_http_activities_zip-code-rest.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_http_activities_zip-code-rest.png" /></span>

2.  Arraste um tipo de atividade HTTP GET até a zona de inserção de
    componentes no design canvas para criar uma instância de uma
    atividade HTTP GET numa nova operação.

3.  Mude o nome da operação para “CEP - REST”.

4.  Clique duas vezes sobre a atividade HTTP GET dentro da operação para
    abrir as configurações dela.

5.  Configure a [atividade HTTP](https://success.jitterbit.com/display/CS/HTTP+Activities):

    -   **Name** (Nome): “Detalhes do CEP”

    -   **HTTP Verb** (Verbo HTTP): “GET”

    -   **Path** (Caminho): “zip”

    -   **Request Parameters** (Parâmetros da Solicitação): Clique em
        **Add** (Adicionar) para determinar um parâmetro de *query*
        chamado “code” (isto é, “código”) cujo valor deverá ser um CEP dos
        Estados Unidos (por exemplo, “94501”). Clique em **Next**
        (Próximo).

    -   **Provide Request Schema** (Fornecer *Schema* da Solicitação): Já
        que não há necessidade de fornecer um *schema* de solicitação
        (visto que uma solicitação GET padrão não contém corpo), clique em
        **Next** (Próximo) de novo.

    -   **Provide Response Schema** (Fornecer *Schema* da Resposta):
        Selecione **Yes, Provide New Schema** (Sim, Fornecer Novo
        *Schema*) e forneça o nome “Detalhes do CEP” para o *schema*, daí
        cole a seguinte estrutura de resposta JSON esperada na caixa de
        texto mais abaixo:

        ```
        {
          "zip": 12345,
          "type": "",
          "primaryCity": "",
          "state": "",
          "county": "",
          "timeZone": "",
          "areaCodes": "",
          "latitude": "",
          "longitude": "",
          "country": "",
          "population": 123456
        }
        ```

        Clique em **Next** (Próximo).

    -   **Data Schema** (*Schema* de Dados): Revise o *schema* de dados e
        clique em **Finished** (Concluído) para voltar para o design
        canvas.

A tela final de configuração da atividade deverá estar parecida com a
imagem abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/http_get_step-4_data-schema.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/http_get_step-4_data-schema.png" /></span>


## 3. Configurar uma Atividade FTP

Nesta etapa, você reutilizará a atividade FTP Write que você criou no
Módulo 4:

1.  Na aba **Components** (Componentes), navegue até **Endpoints** \>
    **FTP Endpoints** para encontrar a conexão “SFTP” e a atividade de
    escrita “Dados do CEP” que você criou como parte do Módulo 4.

2.  Arraste a atividade de escrita “Dados do CEP” até uma zona de
    inserção à direita da atividade HTTP dentro da operação no design
    canvas para reutilizá-la na operação.


## 4. Configurar um *Transformation*

Agora, você precisa criar um *transformation* para transformar dados da
fonte HTTP para o alvo FTP:

1.  No design canvas, paire o mouse sobre a área entre a atividade HTTP
    GET e a atividade FTP Write até que uma zona de inserção de
    componentes apareça.

2.  Clique na zona de inserção e selecione **New Transformation** (Novo
    *Transformation*). Uma nova *transformation* vai abrir para que
    você a configure:

    -   **Transformation Name** (Nome do *Transformation*): “CEP - Resposta
        REST”

    -   **Source** (Fonte): O *schema* fonte já é fornecido (à esquerda)
        porque você o definiu na atividade GET.

    -   **Target** (Alvo): Você precisa definir o *schema* alvo (à direita).
        Clique em **Define Schema** (Defnir *Schema*), daí selecione **Use
        Sample File** (Usar Arquivo Modelo). Configure o [*schema*
        arquivo modelo](https://success.jitterbit.com/display/CS/Sample+File+Schema):

        -   **Provide Schema File** (Fornecer Arquivo *Schema*): Selecione
            **Use Saved Schema** (Usar *Schema* Salvo).

        -   **Saved Schemas** (*Schemas* Salvos): Use o menu *dropdown* para
            selecionar o *schema* “Dados do CEP”, que usa recuos de
            parágrafo como delimitadores, que você definiu como parte do
            Módulo 4. Clique em **Finished** (Concluído).

3.  Na parte superior direita do *schema* alvo, clique em **Automap
    Exact Matches** (Mapear Automaticamente Campos Idênticos). Daí
    clique em **Return to Workflow** (Voltar para o Workflow).

O mapeamento do *transformation* deverá ficar parecido com a imagem
abaixo:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-rest-response.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-rest-response.png" /></span>


## 5. Implantar e Executar a Operação

Finalmente, com todos os passos de operação configurados, você implanta
e executa a operação:

1.  Na parte superior direita da operação, clique no ícone do menu de
    ações <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> e, no
    menu que aparecer, clique em **Deploy and Run** (Implantar e
    Executar). O *status* da operação é mostrado na parte inferior
    esquerda da operação.

2.  Uma vez que a operação tiver sido bem sucedida, faça *login* no
    <a href="https://learningsandbox.jitterbit.com/WebInterface/login.html"
    class="external-link" rel="nofollow">servidor SFTP de treinamento da Jitterbit</a> e visualize o
    arquivo que você gerou.
