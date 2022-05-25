[//]: # (Validade de Operações)
[//]: # (This is a translation of Version 46, published on March 4, 2022.)


## Introdução

As operações devem ser válidas para que possam ser implantadas. Esta página aborda como identificar operações inválidas e como ver os erros de validação associados a elas, além de como resolver erros de validação por meio do uso de um padrão de operação válido. Exemplos de arranjos de operação comuns também são dados.

## Erros de Validação

Esta seção aborda como identificar operações inválidas e como ver os erros de validação associados a elas.

Para novos projetos, os itens inválidos são destacados por padrão no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR), com a seleção padrão **Highlight Invalid Items** (Destacar Itens Inválidos). Para desligar esta opção, desmarque a seguinte caixa de seleção:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/highlight-invalid-items.png" class="confluence-embedded-image confluence-external-resource" /></span>

Quando a opção **Highlight Invalid Items** (Destacar Itens Inválidos) está selecionada, os nomes das operações inválidas aparecem em itálico e vermelho no design canvas e no [painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane?showLanguage=pt_BR). Além disso, no design canvas, os ícones das etapas de operação inválidas são contornados com uma borda vermelha:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_invalid.png" class="confluence-embedded-image confluence-external-resource" /></span>

No painel de projeto, operações inválidas que contêm um erro implícito são mostradas com um ícone de erro <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png" class="confluence-embedded-image confluence-external-resource" /></span>:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_operation.png" class="confluence-embedded-image confluence-external-resource" /></span>

Clique no ícone de erro <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png" class="confluence-embedded-image confluence-external-resource" /></span> ao lado do nome da operação para ver uma mensagem listando os erros de validação da operação. As operações que têm um erro implícito podem estar inválidas por qualquer uma das seguintes razões:

- A operação está vazia.

- A operação não atende aos padrões de operação estabelecidos que garantem que a operação seja suportada e esperada pelo agente. Estes padrões são abordados a seguir na seção [Padrões de Validação](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR#OperationValidity-valid-operation-patterns).

- A operação contém um *transformation* com um [*schema* fornecido por atividade](https://success.jitterbit.com/display/CS/Schemas+Defined+in+an+Activity?showLanguage=pt_BR) que não corresponde à estrutura de *schema* fornecida por uma atividade adjacente.

- A operação contém um *transformation* com um *schema* fonte [fornecido por atividade](https://success.jitterbit.com/display/CS/Schemas+Defined+in+an+Activity?showLanguage=pt_BR) ou [fornecido por *transformation*](https://success.jitterbit.com/display/CS/Schemas+Defined+in+a+Transformation?showLanguage=pt_BR) no qual não há atividade fonte precedendo o *transformation*.

Dependendo do erro, a variação apropriada dos seguintes possíveis erros de operação implícitos será retornada:

> Operation is empty.
>
> Operation does not conform to any valid pattern.
>
> Operation rules and patterns can be found [here](https://success.jitterbit.com/display/CS/Operation+Validity).
>
> The transformation \[source / target\] schema does not match the schema structure provided by \["Activity Name"\] activity. Open transformation \["Transformation Name"\] in \["Operation Name"\] operation and refresh the target schema.
>
> Transformation \["Transformation Name"\] has a source schema but no source activity. Remove the source schema from the transformation or add a source activity before the transformation.

1. *A operação está vazia.*

2. *A operação não se conforma a nenhum padrão válido.*

3. *As regras e padrões de operação podem ser encontrados [aqui](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR).*

4. *O schema do transformation \[fonte / alvo\] não corresponde à estrutura de schema fornecida pela atividade \[“Nome da Atividade”\]. Abra o transformation \[“Nome do Transformation”\] na operação \[“Nome da Operação”\] e atualize o schema alvo.*

5. *O transformation \[“Nome do Transformation”\] tem um schema fonte mas nenhuma atividade fonte. Remova o schema fonte do transformation ou adicione uma atividade fonte antes do transformation.*

O ícone de erro <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png" class="confluence-embedded-image confluence-external-resource" /></span> não aparece se o motivo para a operação estar inválida for que ela contém outros componentes com erros implícitos. Os componentes de projeto usados como parte de uma operação devem ser válidos para que a operação seja válida. Isto inclui componentes usados como etapas de uma operação, bem como outros componentes usados em apoio a uma operação. Por exemplo:

- Um componente usado diretamente como etapa em uma operação, como uma atividade, um *transformation* ou um *script*.

- Um *endpoint* do qual uma atividade usada na operação depende.

- Um componente chamado por um *script* na operação.

As regras de validação dependem do tipo de componente, e são descritas conjuntamente na seção [Validade de Componentes](https://success.jitterbit.com/display/CS/Component+Validity?showLanguage=pt_BR).


## Padrões de Validação

Certos padrões de validação devem ser seguidos para que as operações sejam implantadas na nuvem do Harmony e executadas nos agentes do Harmony. Estes padrões garantem que todas as partes de um projeto sejam suportadas e esperadas pelo agente:

- [Padrão de Arquivo](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-archive-pattern)

- [Padrão de *Script*](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-script-pattern)

- [Padrão de *Transformation*](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-transformation-pattern)

- [Padrão de Arquivo com Dois Alvos](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-two-target-archive-pattern)

- [Padrão de Dois *Transformations*](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-two-transformation-pattern)

- [Padrão Fonte Salesforce Bulk](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-salesforce-bulk-source-pattern)

- [Padrão Alvo Salesforce Bulk](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-salesforce-bulk-target-pattern)

O diagrama a seguir resume todos os padrões de operação válidos. Cada padrão é apresentado individualmente e descrito no texto abaixo do diagrama, no qual **componentes opcionais aparecem em cinza negrito** e **componentes exigidos aparecem em vermelho negrito**.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation-patterns_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

### Perguntas Frequentes

À medida que você vai projetando operações, talvez ajude considerar as respostas às seguintes perguntas frequentes:

- **Qual é a diferença entre uma fonte e um alvo?**<br/>
  Considera-se que as atividades são usadas como *fontes* se elas fornecem dados dentro de uma operação, e que são usadas como *alvos* se recebem dados dentro de uma operação. Para explicações adicionais sobre fontes *versus* alvos e as partes de uma operação, consulte o artigo [Criação e Configuração de Operações](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration?showLanguage=pt_BR).

- **Quais padrões são válidos com o meu *endpoint*?**<br/>
  Os padrões que podem ser usados com cada tipo de atividade específica são documentados dentro das páginas de atividade individual na seção [Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR). Em cada página de atividade, os padrões específicos que podem ser usados estão incluídos na seção “Próximos Passos”, que é tipicamente a última seção em cada página de atividade.

- **E se meu caso de uso não se encaixar em um padrão válido?**<br/>
  Se um certo arranjo de operação desejado não se adequar a um padrão válido, você talvez consiga usar uma combinação de operações em que cada uma delas segue um padrão válido. Para fazer isso, crie cada operação separadamente e daí coloque-as em cadeia usando [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR).

- **Como eu posso me lembrar destes padrões?**<br/>
  Operações que não seguem um padrão válido são apontadas como inválidas e não podem ser implantadas. À medida que você for se familiarizando com os padrões, generalizações como as que vêm a seguir talvez se tornem evidentes:

  - [*Endpoints* baseados em arquivos](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-file-server), como FTP, HTTP e Temporary Storage podem ser usados sem um *transformation*.

  - [*Endpoints* baseados em servidor](https://success.jitterbit.com/display/CS/Connector+Classifications?showLanguage=pt_BR#ConnectorClassifications-file-server) para atividades que não são de tipo *bulk*, como por exemplo, SOAP, Database, Epicor, ServiceNow e Workday exigem um *transformation*.

  - *Scripts* podem ser adicionados em praticamente qualquer lugar.

- **Existem exemplos de como outras pessoas configuraram operações?**<br/>
  Para ver exemplos comuns usando estes padrões, veja a seção [Exemplos de Padrões de Operação Comuns](https://success.jitterbit.com/display/CS/Operation+Validity?showLanguage=pt_BR#OperationValidity-patterns) no final desta página, ou consulte as páginas de atividade individuais em [Conectores](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR).

### Padrão de Arquivos

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation-pattern_archive_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

<p style="margin-left: 30.0px;"><strong><span style="color: rgb(128,128,128);">Script(s)</span></strong>&nbsp;+&nbsp;<span style="color: rgb(255,0,0);"><strong>Atividade Fonte</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script(s)</span></strong>&nbsp;+&nbsp;<strong><span style="color: rgb(255,0,0);">Atividade Alvo</span></strong>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script(s)</span></strong></p>

Neste padrão, as atividades fonte e alvo podem ser associadas com qualquer um dos seguintes tipos de *endpoints*:

- [API](https://success.jitterbit.com/display/CS/API) <sup>A</sup>

- [File Share](https://success.jitterbit.com/display/CS/File+Share)

- [FTP](https://success.jitterbit.com/display/CS/FTP)

- [HTTP](https://success.jitterbit.com/display/CS/HTTP) <sup>B</sup>

- [Local Storage](https://success.jitterbit.com/display/CS/Local+Storage)

- [NetSuite](https://success.jitterbit.com/display/CS/NetSuite)

- [Salesforce](https://success.jitterbit.com/display/CS/Salesforce) <sup>F</sup>

- [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud) <sup>F</sup>

- [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax) <sup>F</sup>

- [Temporary Storage](https://success.jitterbit.com/display/CS/Temporary+Storage)

- [Variable](https://success.jitterbit.com/display/CS/Variable)

<sup>A</sup> *Se uma cadeia de operação contiver uma atividade API, ela deve ser a única atividade API ou API SOAP Request na cadeia de operação e ela deve ser a fonte da primeira operação. Isto é, nenhuma outra operação pode estar chamando esta operação de um script nem de uma ação de operação “em caso de sucesso” ou “em caso de falha”.*

<sup>B</sup> *Atividades HTTP são aquelas associadas com um endpoint HTTP e não incluem atividades associadas com um endpoint customizado baseado em REST.*

<sup>F</sup> *Apenas atividades que não são do tipo bulk podem ser usadas aqui.*

### Padrão de Script

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation-pattern_script_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

<p style="margin-left: 30.0px;"><span style="color: rgb(255,0,0);"><strong>Script(s)</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Atividade Alvo</span></strong></p>

Neste padrão, a atividade alvo pode estar associada a qualquer um dos seguintes tipos de *endpoint*:

- [API](https://success.jitterbit.com/display/CS/API)

- [File Share](https://success.jitterbit.com/display/CS/File+Share)

- [FTP](https://success.jitterbit.com/display/CS/FTP)

- [HTTP](https://success.jitterbit.com/display/CS/HTTP) <sup>B</sup>

- [Local Storage](https://success.jitterbit.com/display/CS/Local+Storage)

- [Temporary Storage](https://success.jitterbit.com/display/CS/Temporary+Storage)

- [Variable](https://success.jitterbit.com/display/CS/Variable)

<sup>B</sup> *Atividades HTTP são aquelas associadas com um endpoint HTTP e não incluem atividades associadas com um endpoint customizado baseado em REST.*

### Padrão de Transformation

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation-pattern_transformation_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

<p style="margin-left: 30.0px;"><span style="color: rgb(122,134,154);"><strong>Script(s)</strong></span>&nbsp;+&nbsp;<span style="color: rgb(122,134,154);"><strong>(Grupo:</strong></span>&nbsp;<span style="color: rgb(255,0,0);"><strong>Atividade Fonte</strong></span>&nbsp;+&nbsp;<span style="color: rgb(122,134,154);"><strong>Script[s]</strong></span>) +&nbsp;<span style="color: rgb(255,0,0);"><strong>Transformation</strong></span>&nbsp;+&nbsp;<span style="color: rgb(122,134,154);"><strong>(Grupo:</strong>&nbsp;<strong>Script(s)</strong></span>&nbsp;+&nbsp;<span style="color: rgb(255,0,0);"><strong>Atividade Alvo</strong></span><strong><span style="color: rgb(122,134,154);">)</span></strong>&nbsp;+&nbsp;<span style="color: rgb(122,134,154);"><strong>Script[s])</strong></span></p>

Neste padrão, as atividades fonte e/ou alvo podem estar associadas com qualquer tipo de *endpoint*, desde que pelo menos uma atividade esteja incluída. Um *transformation* não pode existir por si só sem uma atividade.

<sup>A</sup> *Se uma cadeia de operação contiver uma atividade API, ela deve ser a única atividade API ou API SOAP Request na cadeia de operação e ela deve ser a fonte da primeira operação. Isto é, nenhuma outra operação pode estar chamando esta operação de um script nem de uma ação de operação “em caso de sucesso” ou “em caso de falha”.*

<sup>C</sup> *Se Salesforce, Salesforce Service Cloud ou ServiceMax Query forem usados como a atividade fonte, então uma atividade alvo é exigida.*

<sup>D</sup>*As operações não podem incluir mais de uma atividade NetSuite, Salesforce, Salesforce Service Cloud, SAP, ServiceMax ou SOAP.*

<sup>E</sup> *As operações que incluem uma atividade Salesforce, Salesforce Service Cloud ou ServiceMax não podem incluir nenhuma outra [atividade de aplicação](https://success.jitterbit.com/display/CS/Connector+Classifications#ConnectorClassifications-application).*

<sup>F</sup> *Apenas atividades que não são do tipo bulk podem ser usadas aqui.*

### Padrão de Arquivo com Dois Alvos

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation-pattern_two-target-archive_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

<p style="margin-left: 30.0px;"><strong><span style="color: rgb(128,128,128);">Script(s)</span></strong>&nbsp;+&nbsp;<span style="color: rgb(128,128,128);"><strong>(Grupo:</strong></span>&nbsp;<span style="color: rgb(255,0,0);"><strong>Atividade Fonte 1</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script[s]</span><span style="color: rgb(128,128,128);">)</span></strong>&nbsp;+&nbsp;<span style="color: rgb(255,0,0);"><strong>Transformation</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script(s)</span></strong>&nbsp;+&nbsp;<strong><span style="color: rgb(255,0,0);">Atividade Alvo 1 / Atividade Fonte 2</span></strong>&nbsp;+ <strong><span style="color: rgb(122,134,154);">Script(s)</span></strong> +&nbsp;<span style="color: rgb(255,0,0);"><strong>Atividade Alvo 2</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script(s)</span></strong></p>

Neste padrão, a segunda atividade alvo é usada para arquivar uma resposta da atividade do meio, que funciona tanto como primeiro alvo quanto como segunda fonte.

A resposta da atividade do meio passa os dados de resposta crus para um segundo alvo sem transformá-los. Você pode pensar nisso como um arquivamento ou simplesmente como uma transferência de dados (às vezes chamado em inglês de *passthrough*).

As atividades fonte e alvo devem estar associadas com certos tipos de *endpoint* dependendo de onde são usados no padrão:

- **Atividade Fonte 1 <sup>A</sup>:** Se usada, a primeira atividade fonte pode ser associada com qualquer tipo de *endpoint*.

- **Atividade Alvo 1 / Atividade Fonte 2:** A primeira atividade alvo (também chamada de segunda atividade fonte) pode ser associada com qualquer um dos tipos de *endpoint* a seguir:

  - [HTTP](https://success.jitterbit.com/display/CS/HTTP) <sup>B, G</sup>

  - [NetSuite](https://success.jitterbit.com/display/CS/NetSuite)

  - [Salesforce](https://success.jitterbit.com/display/CS/Salesforce) <sup>E, F</sup>

  - [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud) <sup>E, F</sup>

  - [SAP](https://success.jitterbit.com/display/CS/SAP)

  - [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax) <sup>E, F</sup>

  - [SOAP](https://success.jitterbit.com/display/CS/SOAP)

- **Atividade Fonte 2**: A segunda atividade alvo pode ser associada com qualquer um dos seguintes tipos de *endpoint*:

  - [API](https://success.jitterbit.com/display/CS/API)

  - [File Share](https://success.jitterbit.com/display/CS/File+Share)

  - [FTP](https://success.jitterbit.com/display/CS/FTP)

  - [HTTP](https://success.jitterbit.com/display/CS/HTTP) <sup>B</sup>

  - [Local Storage](https://success.jitterbit.com/display/CS/Local+Storage)

  - [Temporary Storage](https://success.jitterbit.com/display/CS/Temporary+Storage)

  - [Variable](https://success.jitterbit.com/display/CS/Variable)

<sup>A</sup> *Se uma cadeia de operação contiver uma atividade API, ela deve ser a única atividade API ou API SOAP Request na cadeia de operação e ela deve ser a fonte da primeira operação. Isto é, nenhuma outra operação pode estar chamando esta operação de um script nem de uma ação de operação “em caso de sucesso” ou “em caso de falha”.*

<sup>B</sup> *Atividades HTTP são aquelas associadas com um endpoint HTTP e não incluem atividades associadas com um endpoint customizado baseado em REST.*

<sup>D</sup> *As operações não podem incluir mais de uma atividade NetSuite, Salesforce, Salesforce Service Cloud, SAP, ServiceMax ou SOAP.*

<sup>E</sup> *As operações que incluem uma atividade Salesforce, Salesforce Service Cloud ou ServiceMax não podem incluir nenhuma outra [atividade de aplicação](https://success.jitterbit.com/display/CS/Connector+Classifications#ConnectorClassifications-application).*

<sup>F</sup> *Apenas atividades que não são do tipo bulk podem ser usadas aqui.*

<sup>G</sup> *Uma atividade HTTP GET retorna uma mensagem indicando sucesso* `{“success”: true}` *ou falha* `{“success”: false}` *em vez da resposta propriamente dita.*

### Padrão de Dois Transformations

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation-pattern_two-transformation_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

<p style="margin-left: 30.0px;"><strong><span style="color: rgb(128,128,128);">Script(s)</span></strong>&nbsp;+&nbsp;<span style="color: rgb(128,128,128);"><strong>(Grupo:</strong></span>&nbsp;<span style="color: rgb(255,0,0);"><strong>Atividade Fonte 11</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script[s]</span><span style="color: rgb(128,128,128);">)</span></strong>&nbsp;+&nbsp;<span style="color: rgb(255,0,0);"><strong>Transformation 1</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(255,0,0);">Atividade Alvo 1 / Atividade Fonte 2</span></strong>&nbsp;+&nbsp;<span style="color: rgb(255,0,0);"><strong>Transformation 2</strong></span>&nbsp;+ <strong><span style="color: rgb(122,134,154);">Script(s)</span></strong> +&nbsp;<span style="color: rgb(122,134,154);"><strong>Atividade Alvo 2</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script(s)</span></strong></p>

Neste padrão, o segundo *transformation* é usado para pegar a resposta da atividade do meio (que funciona tanto como primeiro alvo e como segunda fonte), transformá-la e daí opcionalmente gravá-la em um segundo alvo.

As atividades fonte e alvo devem ser associadas com certos tipos de *endpoint* dependendo do lugar onde são usadas no padrão:

- **Atividade Fonte 1 <sup>A</sup>:** Se usada, a primeira atividade fonte pode ser associada com qualquer tipo de *endpoint*.

- **Atividade Alvo 1 / Atividade Fonte 2:** A primeira atividade alvo (também chamada de segunda atividade fonte) pode ser associada com qualquer um dos seguintes tipos de *endpoint*:

  - [Aplicação](https://success.jitterbit.com/display/CS/Connector+Classifications#ConnectorClassifications-application) <sup>F</sup>

  - [SOAP](https://success.jitterbit.com/display/CS/SOAP)

- **Atividade Alvo 2 <sup>F</sup>:** Se usada, a segunda atividade alvo pode ser associada com qualquer tipo de *endpoint*.

<sup>A</sup> *Se uma cadeia de operação contiver uma atividade API, ela deve ser a única atividade API ou API SOAP Request na cadeia de operação e ela deve ser a fonte da primeira operação. Isto é, nenhuma outra operação pode estar chamando esta operação de um script nem de uma ação de operação “em caso de sucesso” ou “em caso de falha”.*

<sup>D</sup> *As operações não podem incluir mais de uma atividade NetSuite, Salesforce, Salesforce Service Cloud, SAP, ServiceMax ou SOAP.*

<sup>E</sup> *As operações que incluem uma atividade Salesforce, Salesforce Service Cloud ou ServiceMax não podem incluir nenhuma outra [atividade de aplicação](https://success.jitterbit.com/display/CS/Connector+Classifications#ConnectorClassifications-application).*

<sup>F</sup> *Apenas atividades que não são do tipo bulk podem ser usadas aqui.*

### Padrão Fonte Salesforce Bulk

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation-pattern_salesforce-bulk-source_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

<p style="margin-left: 30.0px;"><strong><span style="color: rgb(128,128,128);">Script(s)</span></strong>&nbsp;+&nbsp;<span style="color: rgb(255,0,0);"><strong>Atividade Fonte</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script(s)</span></strong>&nbsp;+&nbsp;<strong><span style="color: rgb(255,0,0);">Atividade Alvo</span></strong>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script(s)</span></strong></p>

Neste padrão, a atividade fonte deve ser uma atividade [Salesforce Bulk Query](https://success.jitterbit.com/display/CS/Salesforce+Bulk+Query+Activity), [Salesforce Service Cloud Bulk Query](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud) ou [ServiceMax Bulk Query](https://success.jitterbit.com/display/CS/ServiceMax+Bulk+Query+Activity). A atividade alvo pode ser associada com qualquer um dos seguintes tipos de *endpoint*:

- [File Share](https://success.jitterbit.com/display/CS/File+Share)

- [FTP](https://success.jitterbit.com/display/CS/FTP)

- [HTTP](https://success.jitterbit.com/display/CS/HTTP) <sup>B</sup>

- [Local Storage](https://success.jitterbit.com/display/CS/Local+Storage)

- [Temporary Storage](https://success.jitterbit.com/display/CS/Temporary+Storage)

- [Variable](https://success.jitterbit.com/display/CS/Variable)

<sup>B</sup> *Atividades HTTP são aquelas associadas com um endpoint HTTP e não incluem atividades associadas com um endpoint customizado baseado em REST.*

### Padrão Alvo Salesforce Bulk

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation-pattern_salesforce-bulk-target_annotated_pp.png" class="confluence-embedded-image confluence-external-resource" /></span>

<p style="margin-left: 30.0px;"><strong><span style="color: rgb(128,128,128);">Script(s)</span></strong>&nbsp;+&nbsp;<span style="color: rgb(255,0,0);"><strong>Atividade Fonte</strong></span>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script(s)</span></strong>&nbsp;+&nbsp;<strong><span style="color: rgb(255,0,0);">Atividade Alvo</span></strong>&nbsp;+&nbsp;<strong><span style="color: rgb(128,128,128);">Script(s)</span></strong></p>

Neste padrão, a atividade fonte pode ser associada com qualquer um dos seguintes tipos de *endpoint*:

- [File Share](https://success.jitterbit.com/display/CS/File+Share)

- [FTP](https://success.jitterbit.com/display/CS/FTP)

- [HTTP](https://success.jitterbit.com/display/CS/HTTP) <sup>B</sup>

- [Local Storage](https://success.jitterbit.com/display/CS/Local+Storage)

- [Temporary Storage](https://success.jitterbit.com/display/CS/Temporary+Storage)

- [Variable](https://success.jitterbit.com/display/CS/Variable)

A atividade alvo pode ser associada com qualquer um dos seguintes tipos de *endpoint*:

- [Salesforce Bulk Insert](https://success.jitterbit.com/display/CS/Salesforce+Bulk+Insert+or+Bulk+Update+Activity)

- [Salesforce Bulk Update](https://success.jitterbit.com/display/CS/Salesforce+Bulk+Insert+or+Bulk+Update+Activity)

- [Salesforce Bulk Upsert](https://success.jitterbit.com/display/CS/Salesforce+Bulk+Upsert+Activity)

- [Salesforce Bulk Delete](https://success.jitterbit.com/display/CS/Salesforce+Bulk+Delete+or+Bulk+Hard+Delete+Activity)

- [Salesforce Bulk Hard Delete](https://success.jitterbit.com/display/CS/Salesforce+Bulk+Delete+or+Bulk+Hard+Delete+Activity)

- [Salesforce Service Cloud Bulk Insert, Update, Upsert, Delete, or Hard Delete](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud)

- [ServiceMax Bulk Insert](https://success.jitterbit.com/display/CS/ServiceMax+Bulk+Insert+or+Bulk+Update+Activity)

- [ServiceMax Bulk Update](https://success.jitterbit.com/display/CS/ServiceMax+Bulk+Insert+or+Bulk+Update+Activity)

- [ServiceMax Bulk Upsert](https://success.jitterbit.com/display/CS/ServiceMax+Bulk+Upsert+Activity)

- [ServiceMax Bulk Delete](https://success.jitterbit.com/display/CS/ServiceMax+Bulk+Delete+or+Bulk+Hard+Delete+Activity)

- [ServiceMax Bulk Hard Delete](https://success.jitterbit.com/display/CS/ServiceMax+Bulk+Delete+or+Bulk+Hard+Delete+Activity)

<sup>B</sup> *Atividades HTTP são aquelas associadas com um endpoint HTTP e não incluem atividades associadas com um endpoint customizado baseado em REST.*


## Exemplos de Padrões de Operação Comuns

Esta seção fornece vários exemplos comuns de operações configuradas usando um padrão de operação válido. Estes exemplos estão simplificados para demonstrar os elementos constituintes básicos de operações comumente construídas e não têm o propósito de abranger todas as combinações possíveis. Consulte a seção [Padrões de Validação](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-known-patterns) mais acima nesta mesma página para ver todos os arranjos possíveis.

### Script

Uma operação pode simplesmente conter um único [*script*](https://success.jitterbit.com/display/CS/Scripts?showLanguage=pt_BR). Neste caso, todas as ações na operação são executadas pelo *script*.

Este padrão é tipicamente usado no início de um workflow para criar um “*script* de lançamento” que executa um ou mais de vários caminhos de operação com base numa variável de sistema ou outro valor de dado.

Os *scripts* também podem ser usados em qualquer lugar de uma operação para executar cálculos complexos que exigem lógica customizada.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_kickoff-script.png" class="confluence-embedded-image confluence-external-resource" /></span>

### Arquivo

Se você só precisa mover arquivos de uma fonte de dados para um alvo, você pode usar uma operação sem um *transformation*.

A primeira atividade é usada como fonte, fornecendo dados dentro da operação. A segunda atividade é usada como alvo, recebendo dados dentro da operação.

Para arquivar dados, as atividades fonte e alvo são limitadas àquelas que interagem com arquivos. Em vez de uma atividade fonte, você pode também usar um *script*.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_simple-file-transfer.png" class="confluence-embedded-image confluence-external-resource" /></span>

### Transformation

Operações que fazem uso de [transformations](https://success.jitterbit.com/display/CS/Transformations?showLanguage=pt_BR) servem uma grande variedade de casos de uso. Por exemplo, você pode criar operações que (1) transformam dados de uma fonte para um alvo, (2) transformam dados, daí gravam a resposta em outro alvo ou (3) transformam dados de uma chamada a um serviço web convertendo a resposta da chamada da aplicação e gravando-a num alvo.

#### Operação Transforma Dados de uma Fonte para um Alvo

Este exemplo puxa dados de uma atividade fonte que são então transformados e gravados numa atividade alvo:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_ftp-read.png" class="confluence-embedded-image confluence-external-resource" /></span>

#### Operação Transforma Dados, daí Grava a Resposta em Outro Alvo

Neste exemplo, quando uma atividade HTTP é usada como o alvo do *transformation*, como HTTP PUT ou HTTP POST, uma atividade alvo adicional pode ser colocada diretamente depois dela, ou depois de outro *transformation*, para gravar a resposta HTTP em outro alvo.

Este arranjo de operação, usado para obter um *token* REST, mostra a resposta HTTP sendo gravada em uma variável global para uso na próxima operação:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_get-token.png" class="confluence-embedded-image confluence-external-resource" /></span>

#### Operação Chama um Serviço Web

Este exemplo é para atualizar uma aplicação como [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR) por meio da API da aplicação, ou chamar um método de serviço web [SOAP](https://success.jitterbit.com/display/CS/SOAP?showLanguage=pt_BR).

Neste arranjo, a operação tem três partes;

- A primeira atividade fonte e *transformation* para construir a estrutura de dados de resposta.

- A chamada à aplicação em si, que funciona como primeira atividade alvo e segunda atividade fonte.

- Um segundo *transformation* e alvo para converter a resposta da chamada à aplicação e gravar os dados ou o arquivo num alvo.

##### *Chamada à Aplicação*

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_salesforce-insert.png" class="confluence-embedded-image confluence-external-resource" /></span>

##### *Chamada SOAP*

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/operation_check-credit-card-info.png" class="confluence-embedded-image confluence-external-resource" /></span>
