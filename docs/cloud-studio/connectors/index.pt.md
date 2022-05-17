# Conectores
[//]: # (This is a translation of Version 49, published on July 8, 2021.)


## Visão Geral

Este tópico fornece informações sobre o uso do Jitterbit Harmony Cloud Studio para se conectar a vários recursos de dados. Isto inclui Jitterbit Custom APIs (APIs Customizadas da Jitterbit), recursos padronizados (Local Storage, Temporary Storage, Variables, File Share, FTP, Database, HTTP, SOAP) e recursos específicos a certas aplicações (NetSuite, Salesforce, ServiceNow, Workday, etc.).

A conexão a estes recursos de dados é feita por meio da configuração dos conectores do Jitterbit Harmony, que fornecem a interface para criar uma conexão com um recurso de dados fora do Jitterbit Harmony.

No Cloud Studio, os conectores são configurados inicialmente para criar *conexões*. As *atividades* são então criadas a partir das conexões e são configuradas ou como fontes (para fornecer dados) ou como alvos (para consumir dados) em uma operação. Juntas, uma conexão específica e suas atividades são chamadas de *endpoint*.

Antes de você começar, consulte as seguintes páginas para informações básicas e classificações de conectores:

-   [**Informações Básicas sobre Conectores**](https://success.jitterbit.com/display/CS/Connector+Basics): Terminologia e definições de recursos de conectividade, como adicionar uma atividade a uma operação, e várias ações que estão disponíveis em todas as atividades.

-   [**Classificações de Conectores**](https://success.jitterbit.com/display/CS/Connector+Classifications): Classificações de conectores pelo uso: *API, armazenamento de curto prazo, armazenamento de longo prazo, orientado a serviços* ou *aplicação*. Os conectores também podem ser diferenciados com base no *schema* que usam: *baseado em servidor* ou *baseado em arquivo*.


## Conectores Disponíveis

As informações neste tópico estão organizadas por conector individual. Veja cada conector para conhecer mais detalhes sobre seus pré-requisitos e configurações:

**API**

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [API](https://success.jitterbit.com/display/CS/API)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

</div>

</div>
</div>

**Armazenamento de Curto Prazo**

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

**Armazenamento de Longo Prazo**

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [File Share](https://success.jitterbit.com/display/CS/File+Share)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [FTP](https://success.jitterbit.com/display/CS/FTP)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Database](https://success.jitterbit.com/display/CS/Database)

</div>

</div>
</div>

**Baseado em Serviços**

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [HTTP](https://success.jitterbit.com/display/CS/HTTP)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [SOAP](https://success.jitterbit.com/display/CS/SOAP)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

</div>

</div>
</div>

**Aplicação**

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

-   Conectores customizados criados com o [Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder) (Construtor de Conectores)

-   Conectores customizados criados com o [Connector SDK](https://developer.jitterbit.com/connector-sdk/)

-   [Gzip](https://success.jitterbit.com/display/CS/Gzip) e [Email](https://success.jitterbit.com/display/CS/Email) (Embora estes conectores não se conectem a nenhuma aplicação, os *schemas* deles são fixos e eles seguem todos os [padrões de operação válidos](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-valid-operation-patterns) para um conector de aplicação.)

Conectores específicos a certas aplicações adicionais são adicionados a cada novo [lançamento do Harmony](https://success.jitterbit.com/display/DOC/Harmony) e são atualizados aqui nesta página ao longo do tempo.

Conectores customizados criados com o [Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder) ou com o [Connector SDK](https://developer.jitterbit.com/connector-sdk/) também são conectores de aplicação.
