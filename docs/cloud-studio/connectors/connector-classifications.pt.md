[//]: # (Classificações de Conectores)
[//]: # (This is a translation of Version 75, published on May 6, 2022.)


## Introdução

Os conectores são documentados individualmente mas podem ser classificados quanto aos seus usos:

-   [**API**](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-api): Use o conector [API](https://success.jitterbit.com/display/CS/API?showLanguage=pt_BR) junto com uma API Customizada Jitterbit que é configurada por meio do [API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR).

-   [**Armazenamento de Curto Prazo**](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-short-term-storage): Use os conectores [Local Storage](https://success.jitterbit.com/display/CS/Local+Storage?showLanguage=pt_BR), [Temporary Storage](https://success.jitterbit.com/display/CS/Temporary+Storage?showLanguage=pt_BR) ou [Variable](https://success.jitterbit.com/display/CS/Variable?showLanguage=pt_BR) para armazenamento temporário de arquivos.

-   [**Armazenamento de Longo Prazo**](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-long-term-storage): Use os conectores [File Share](https://success.jitterbit.com/display/CS/File+Share?showLanguage=pt_BR), [FTP](https://success.jitterbit.com/display/CS/FTP?showLanguage=pt_BR) ou [Database](https://success.jitterbit.com/display/CS/Database?showLanguage=pt_BR) para armazenamento de longo prazo ou permanente de arquivos.

-   [**Baseado em Serviços**](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-service-based): Use os conectores [HTTP](https://success.jitterbit.com/display/CS/HTTP?showLanguage=pt_BR) ou [SOAP](https://success.jitterbit.com/display/CS/SOAP?showLanguage=pt_BR) para se conectar a serviços web que já não possuam um conector de aplicação ou que você queira conectar usando um serviço web padronizado.

-   [**Aplicação**](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-application): Use estes conectores como a maneira recomendada de se conectar a uma aplicação específica, como [NetSuite](https://success.jitterbit.com/display/CS/NetSuite?showLanguage=pt_BR), [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), [ServiceNow](https://success.jitterbit.com/display/CS/ServiceNow?showLanguage=pt_BR) ou [Workday](https://success.jitterbit.com/display/CS/Workday?showLanguage=pt_BR).

Os conectores também podem ser diferenciados pela forma como seus *schemas* são definidos:

-   [**Baseados em Servidor ou Baseados em Arquivo**](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-file-server): Estes termos são usados em conjunto com as classificações listadas acima para se referir a conectores que automaticamente pegam um *schema* do *endpoint* (baseados em servidor) em contraste com aqueles em que você fornece o *schema* (baseados em arquivo).


## Uso de Conectores

Estas classificações de conectores são pelo tipo de uso do conector.

### API

Este conector é usado em conjunto com uma API Customizada Jitterbit que é configurada por meio do [API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR). Ao contrário de outros conectores, a conexão API é um *endpoint* pré-configurado cujas atividades associadas incluem atividades Request (Solicitação) e Response (Resposta). Os *schemas* são definidos por arquivos fornecidos pelo(a) usuário(a).

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [API](https://success.jitterbit.com/display/CS/API?showLanguage=pt_BR)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

</div>

</div>
</div>

### Armazenamento de Curto Prazo

Estes conectores são normalmente usados quando você quer armazenar arquivos temporariamente para uso em uma operação mais abaixo na cadeia. As atividades associadas incluem atividades Read (Ler) e Write (Gravar). No entanto, não se pode contar com a presença de arquivos escritos depois da execução da operação, com exceção do conector Local Storage com algumas configurações adicionais. Os *schemas* são definidos por arquivos fornecidos pelo(a) usuário(a).

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Local Storage](https://success.jitterbit.com/display/CS/Local+Storage?showLanguage=pt_BR)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Temporary Storage](https://success.jitterbit.com/display/CS/Temporary+Storage?showLanguage=pt_BR)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Variable](https://success.jitterbit.com/display/CS/Variable?showLanguage=pt_BR)

</div>

</div>
</div>

### Armazenamento de Longo Prazo

Estes conectores são normalmente usados para armazenamento de longo prazo ou permanente de arquivos. As atividades associadas incluem atividades Read (Ler) e Write (Gravar). Os *schemas* são definidos por arquivos fornecidos pelo(a) usuário(a).

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [File Share](https://success.jitterbit.com/display/CS/File+Share)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [FTP](https://success.jitterbit.com/display/CS/FTP)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

</div>

</div>
</div>

O conector Database também pode ser considerado um conector de armazenamento de longo prazo, mas ele oferece mais funcionalidades que os outros. O conector Database é usado para acessar sistemas de gerenciamento de bancos de dados relacionais (RDMS, sigla em inglês) usando *drivers* de terceiros. As atividades incluem Query, Insert e Update (o Jitterbit Harmony também suporta uma atividade Upsert por meio de uma combinação dessas). Os *schemas* são obtidos através de *query* no banco de dados usando o *driver* escolhido.

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Database](https://success.jitterbit.com/display/CS/Database?showLanguage=pt_BR)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

</div>

</div>
</div>

### Baseado em Serviços

Estes conectores são usados com um serviço que fornece os metadados necessários para a conexão e suas atividades. No caso de serviços HTTP/REST, você busca e testa o serviço, e daí você fornece os *schemas* dentro de cada atividade. No caso de serviços SOAP, estes metadados são fornecidos em um arquivo Web Service Definition Language (WSDL, ou *linguagem de definição de serviços* web) e os *schemas* são obtidos a partir de *query* no serviço.

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [HTTP](https://success.jitterbit.com/display/CS/HTTP?showLanguage=pt_BR)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [SOAP](https://success.jitterbit.com/display/CS/SOAP?showLanguage=pt_BR)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

</div>

</div>
</div>

### Aplicação

Estes conectores são usados para interagir com aplicações específicas, e incorporam lógica específica àquela aplicação para se conectar ao *endpoint* e para várias atividades que são únicas de um *endpoint* para outro. Os *schemas* são obtidos por meio de *query* em cada aplicação.

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Amazon Redshift](https://success.jitterbit.com/display/CS/Amazon+Redshift)

-   [Amazon S3](https://success.jitterbit.com/display/CS/Amazon+S3)

-   [Amazon SQS](https://success.jitterbit.com/display/CS/Amazon+SQS)

-   [ANYMARKET](https://success.jitterbit.com/display/CS/ANYMARKET)

-   [Apache Kafka](https://success.jitterbit.com/display/CS/Apache+Kafka)

-   [BigCommerce](https://success.jitterbit.com/display/CS/BigCommerce)

-   [BMC Helix Business Workflows](https://success.jitterbit.com/display/CS/BMC+Helix+Business+Workflows)

-   [BMC Helix ITSM](https://success.jitterbit.com/display/CS/BMC+Helix+ITSM)

-   [BMC Helix Operations Management](https://success.jitterbit.com/display/CS/BMC+Helix+Operations+Management)

-   [Box](https://success.jitterbit.com/display/CS/Box)

-   [Cherwell](https://success.jitterbit.com/display/CS/Cherwell)

-   [Constant Contact](https://success.jitterbit.com/display/CS/Constant+Contact)

-   [Coupa](https://success.jitterbit.com/display/CS/Coupa)

-   [DocuSign](https://success.jitterbit.com/display/CS/DocuSign)

-   [EDI for Cloud](https://success.jitterbit.com/display/CS/EDI+for+Cloud)

-   [Elasticsearch](https://success.jitterbit.com/display/CS/Elasticsearch)

-   [Epicor ERP](https://success.jitterbit.com/display/CS/Epicor+ERP)

-   [Evernote](https://success.jitterbit.com/display/CS/Evernote)

-   [GitHub](https://success.jitterbit.com/display/CS/GitHub)

-   [Google Docs](https://success.jitterbit.com/display/CS/Google+Docs)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Google Drive](https://success.jitterbit.com/display/CS/Google+Drive)

-   [Google Sheets](https://success.jitterbit.com/display/CS/Google+Sheets)

-   [HubSpot](https://success.jitterbit.com/display/CS/HubSpot)

-   [Jenkins](https://success.jitterbit.com/display/CS/Jenkins)

-   [Jira](https://success.jitterbit.com/display/CS/Jira)

-   [Jitterbit App Builder](https://success.jitterbit.com/display/CS/Jitterbit+App+Builder)

-   [JMS](https://success.jitterbit.com/display/CS/JMS)

-   [LDAP](https://success.jitterbit.com/display/CS/LDAP)

-   [Magazine Luiza Companies](https://success.jitterbit.com/display/CS/Magazine+Luiza+Companies)

-   [Magazine Luiza Shopping](https://success.jitterbit.com/display/CS/Magazine+Luiza+Shopping)

-   [Magento](https://success.jitterbit.com/display/CS/Magento)

-   [Microsoft Dynamics AX](https://success.jitterbit.com/display/CS/Microsoft+Dynamics+AX)

-   [Microsoft Dynamics CRM](https://success.jitterbit.com/display/CS/Microsoft+Dynamics+CRM)

-   [Microsoft Teams](https://success.jitterbit.com/display/CS/Microsoft+Teams)

-   [MongoDB](https://success.jitterbit.com/display/CS/MongoDB)

-   [NetSuite](https://success.jitterbit.com/display/CS/NetSuite)

-   [OData](https://success.jitterbit.com/display/CS/OData)

-   [PagerDuty](https://success.jitterbit.com/display/CS/PagerDuty)

-   [RabbitMQ](https://success.jitterbit.com/display/CS/RabbitMQ)

-   [Salesforce](https://success.jitterbit.com/display/CS/Salesforce)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Salesforce Einstein Analytics](https://success.jitterbit.com/display/CS/Salesforce+Einstein+Analytics)

-   [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud)

-   [SAP](https://success.jitterbit.com/display/CS/SAP)

-   [SAP Concur](https://success.jitterbit.com/display/CS/SAP+Concur)

-   [SendGrid](https://success.jitterbit.com/display/CS/SendGrid)

-   [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax)

-   [ServiceNow](https://success.jitterbit.com/display/CS/ServiceNow)

-   [ShipStation](https://success.jitterbit.com/display/CS/ShipStation)

-   [Shopify](https://success.jitterbit.com/display/CS/Shopify)

-   [Slack](https://success.jitterbit.com/display/CS/Slack)

-   [Smartsheet](https://success.jitterbit.com/display/CS/Smartsheet)

-   [Snowflake](https://success.jitterbit.com/display/CS/Snowflake)

-   [Square](https://success.jitterbit.com/display/CS/Square)

-   [SugarCRM](https://success.jitterbit.com/display/CS/SugarCRM)

-   [VTEX](https://success.jitterbit.com/display/CS/VTEX)

-   [WooCommerce](https://success.jitterbit.com/display/CS/WooCommerce)

-   [Workday](https://success.jitterbit.com/display/CS/Workday)

-   [Workday Prism Analytics](https://success.jitterbit.com/display/CS/Workday+Prism+Analytics)

-   [Zendesk](https://success.jitterbit.com/display/CS/Zendesk)

</div>

</div>
</div>

Além disso, os seguintes conectores são conectores de aplicação:

-   Conectores customizados criados com o [Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder?showLanguage=pt_BR) (Construtor de Conectores)

-   Conectores customizados criados com o [Connector SDK](https://developer.jitterbit.com/connector-sdk/)

-   [Gzip](https://success.jitterbit.com/display/CS/Gzip?showLanguage=pt_BR) e [Email](https://success.jitterbit.com/display/CS/Email?showLanguage=pt_BR) (Embora estes conectores não se conectem a nenhuma aplicação, os *schemas* deles são fixos e eles seguem todos os [padrões de operação válidos](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR#OperationValidity-valid-operation-patterns) para um conector de aplicação).

Conectores adicionais específicos a certas aplicações são adicionados com cada novo [lançamento do Harmony](https://success.jitterbit.com/display/DOC/Harmony?showLanguage=pt_BR) e são atualizados aqui ao longo do tempo.

## Definição do *Schema* do Conector

Além das classificações de conector por uso mostradas acima, os conectores também podem ser descritos com base em como seus *schemas* são definidos.

### Baseado em Servidor ou Baseado em Arquivo

Os conectores podem ser descritos como sendo baseados em servidor ou baseados em arquivo dependendo de como os seus *schemas* são definidos.

Para saber mais sobre *schemas* em ambos os tipos de conectores, veja o artigo [Regeneração de *Schemas*](https://success.jitterbit.com/display/CS/Schema+Regeneration?showLanguage=pt_BR).

#### Baseado em Servidor

Um *endpoint* baseado em servidor refere-se a um *endpoint* cujos *schemas* são gerados diretamente a partir do *endpoint*, como ocorre com os endpoints [Database](https://success.jitterbit.com/display/CS/Database?showLanguage=pt_BR), [NetSuite](https://success.jitterbit.com/display/CS/NetSuite?showLanguage=pt_BR) e [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), assim como muitos *endpoints* específicos a certas aplicações e alguns *endpoints* customizados. *Schemas* baseados em servidor são sempre [definidos numa atividade](https://success.jitterbit.com/display/CS/Schemas+Defined+in+an+Activity?showLanguage=pt_BR). *Schemas* baseados em servidor têm um nome gerado automaticamente que depende de caso o *schema* é uma solicitação ou uma resposta:

```
User-Defined Endpoint Name→User-Defined Activity Name→Request
```

```
User-Defined Endpoint Name→User-Defined Activity Name→Response
```

Este *transformation* mostra os nomes de *schemas* baseados em servidor sendo herdados de atividades tanto nos lados da fonte quanto do alvo:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/schema-names_annotated.png" class="confluence-embedded-image confluence-external-resource" /></span>

Os nomes de *schemas* baseados em servidor e suas estruturas não podem ser editados diretamente. Dependendo do *endpoint*, a estrutura pode mudar dinamicamente com base na entrada do usuário fornecida durante a configuração da atividade ou nas mudanças feitas ao *endpoint* em si.

#### Baseado em Arquivo

Um *endpoint* baseado em arquivo refere-se a um *endpoint* cujos *schemas* são fornecidos pelo usuário, como *endpoints* [API](https://success.jitterbit.com/display/CS/API?showLanguage=pt_BR), [File Share](https://success.jitterbit.com/display/CS/File+Share?showLanguage=pt_BR), [FTP](https://success.jitterbit.com/display/CS/FTP?showLanguage=pt_BR), [HTTP](https://success.jitterbit.com/display/CS/HTTP?showLanguage=pt_BR), [Local Storage](https://success.jitterbit.com/display/CS/Local+Storage?showLanguage=pt_BR), [SOAP](https://success.jitterbit.com/display/CS/SOAP?showLanguage=pt_BR), [Temporary Storage](https://success.jitterbit.com/display/CS/Temporary+Storage?showLanguage=pt_BR) e [Variable](https://success.jitterbit.com/display/CS/Variable?showLanguage=pt_BR). *Schemas* baseados em arquivo podem ser [definidos numa atividade](https://success.jitterbit.com/display/CS/Schemas+Defined+in+an+Activity?showLanguage=pt_BR) ou [definidos num *transformation*](https://success.jitterbit.com/display/CS/Schemas+Defined+in+a+Transformation?showLanguage=pt_BR). Os nomes dos *schemas* baseados em arquivo são tirados do nome do arquivo fornecido ou são definidos pelo(a) usuário(a).
