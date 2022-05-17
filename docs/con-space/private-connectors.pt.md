# Conectores Privados
[//]: # (This is a translation of Version 9, published on May 13, 2022.)


## Visão Geral

Este tópico fornece informações sobre o uso do Jitterbit Harmony Cloud Studio para conectar vários recursos de dados usando Conectores Privados.

Dois tipos de conectores estão disponíveis no Jitterbit Harmony:

-   **Conectores Públicos**: Estes conectores estão disponíveis tanto para os [Grupos de Cloud Agents](https://success.jitterbit.com/display/DOC/Cloud+Agent+Groups) quanto os [Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents). Eles estão listados em [Conectores](https://success.jitterbit.com/display/CS/Connectors).

-   **Conectores Privados**: Descritos aqui, estes conectores são executados apenas nos [Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents).

Em ambos os casos, um conector é automaticamente baixado no agente conforme exigido durante a configuração e a testagem ou durante a execução das operações do projeto.

No Cloud Studio, os conectores são configurados primeiramente para criar *conexões*. As *atividades* são então criadas a partir das conexões e configuradas para serem ou fontes (para fornecer dados) ou alvos (para consumir dados) em uma operação. Juntas, uma conexão específica e suas atividades são chamadas de *endpoint*.

Antes de você começar, consulte as seguintes páginas para saber informações básicas sobre conectores e suas classificações:

-   [**Informações Básicas sobre Conectores**](https://success.jitterbit.com/display/CS/Connector+Basics): Terminologia e definições dos recursos de conectividade, como adicionar uma atividade a uma operação, e várias ações que estão disponíveis em todas as atividades.

-   [**Conexões e Atividades Comuns dos Conectores Privados**](https://success.jitterbit.com/display/CON/Common+Connections+and+Activities): Todos os Conectores Privados seguem um formato similar em suas conexões e atividades, e tais atividades comuns são documentadas juntas.


## Conectores Privados Disponíveis

As informações neste tópico estão organizadas separadamente por cada Conector Privado. Veja cada conector para conhecer os detalhes sobre seus pré-requisitos e configurações:

<div class="sectionColumnWrapper conf-macro output-block conf-macro output-block" data-hasbody="false" data-macro-name="marked">
<div class="sectionMacro"><div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Active Directory](https://success.jitterbit.com/display/CON/Active+Directory)

-   [Acumatica](https://success.jitterbit.com/display/CON/Acumatica)

-   [ADP](https://success.jitterbit.com/display/CON/ADP)

-   [Amazon Dynamo DB](https://success.jitterbit.com/display/CON/Amazon+Dynamo+DB)

-   [Amazon Marketplace](https://success.jitterbit.com/display/CON/Amazon+Marketplace)

-   [Dynamics 365 Business Central](https://success.jitterbit.com/display/CON/Dynamics+365+Business+Central)

-   [Dynamics 365 Finance and Operations](https://success.jitterbit.com/display/CON/Dynamics+365+Finance+and+Operations)

-   [Dynamics 365 Sales](https://success.jitterbit.com/display/CON/Dynamics+365+Sales)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Exact Online](https://success.jitterbit.com/display/CON/Exact+Online)

-   [Financial Edge NXT](https://success.jitterbit.com/display/CON/Financial+Edge+NXT)

-   [GraphQL](https://success.jitterbit.com/display/CON/GraphQL)

-   [Marketo](https://success.jitterbit.com/display/CON/Marketo)

-   [Microsoft Dataverse](https://success.jitterbit.com/display/CON/Microsoft+Dataverse)

-   [Microsoft Excel](https://success.jitterbit.com/display/CON/Microsoft+Excel)

-   [Microsoft Office 365](https://success.jitterbit.com/display/CON/Microsoft+Office+365)

-   [Microsoft OneDrive](https://success.jitterbit.com/display/CON/Microsoft+OneDrive)

</div>
<div class="columnMacro conf-macro output-block" style="width:33%;min-width:33%;max-width:33%;" data-hasbody="true" data-macro-name="column">

-   [Microsoft SharePoint](https://success.jitterbit.com/display/CON/Microsoft+SharePoint)

-   [Sage 300](https://success.jitterbit.com/display/CON/Sage+300)

-   [Sage Intacct](https://success.jitterbit.com/display/CON/Sage+Intacct)

-   [Salesforce Pardot](https://success.jitterbit.com/display/CON/Salesforce+Pardot)

-   [SAP Business One](https://success.jitterbit.com/display/CON/SAP+Business+One)

-   [SAP SuccessFactors](https://success.jitterbit.com/display/CON/SAP+SuccessFactors)

</div>

</div>
</div>
