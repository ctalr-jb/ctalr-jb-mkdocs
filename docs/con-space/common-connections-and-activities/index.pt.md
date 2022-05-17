[//]: # (Conexões e Atividades Comuns)
[//]: # (This is a translation of Version 6, published on April 18, 2022.)


## Resumo

Os conectores estabelecem acesso aos *endpoints* e são executados nos agentes do Harmony (em inglês, [Harmony Agents](https://success.jitterbit.com/display/DOC/Agent?showLanguage=pt_BR)). Estas páginas documentam as características em comum compartilhadas por vários dos [conectores do Jitterbit Harmony Cloud Studio](https://success.jitterbit.com/display/CS/Connectors?showLanguage=pt_BR).

Um conector fornece uma interface para criar uma conexão, a base usada para gerar instâncias de atividades de conector. Estas atividades, uma vez configuradas, interagem com um *endpoint* por meio da conexão.

Um conector é acessado a partir da aba **Connectivity** (Conectividade) da paleta de componentes de *design* (veja a seção [Conectores](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR#DesignComponentPalette-connectors) no artigo [Paleta de Componentes de *Design*](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR)).

## Visão Geral de um Conector

Um conector é usado para fazer a configuração inicial de uma [conexão](https://success.jitterbit.com/display/CS/common+connections). Daí, os tipos de atividade associados àquela conexão são usados para criar instâncias de atividades que têm o propósito de serem usadas como fontes (para fornecer dados em uma operação) ou alvos (para consumir dados em uma operação).

Juntas, uma conexão específica e as suas atividades são chamadas de *endpoint*. As atividades disponíveis dependem do conector. Este exemplo mostra um *endpoint* Dynamics 365 Sales junto com suas atividades:

<span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-activities.png" class="confluence-embedded-image confluence-external-resource" /></span>

Os tipos de atividade disponíveis dependem daquele conector em particular. Para muitos conectores, as seguintes atividades estão disponíveis:

-   [**Query**](https://success.jitterbit.com/display/CS/common+query+activities): Esta atividade busca um objeto de um *endpoint* e tem como propósito ser usada como fonte em uma operação. (Documentada genericamente em [Atividades *Query*](https://success.jitterbit.com/display/CS/common+query+activities)).

-   [**Create**](https://success.jitterbit.com/display/CS/common+create+activities): Esta atividade cria um objeto em um *endpoint* e tem como propósito ser usada como alvo em uma operação. (Documentada genericamente em [Atividades *Create*](https://success.jitterbit.com/display/CS/common+create+activities)).

-   [**Update**](https://success.jitterbit.com/display/CS/common+update+activities): Esta atividade atualiza um objeto em um *endpoint* e tem como propósito ser usada como alvo em uma operação. (Documentada genericamente em [Atividades *Update*](https://success.jitterbit.com/display/CS/common+update+activities)).

-   [**Delete**](https://success.jitterbit.com/display/CS/common+delete+activities): Esta atividade exclui um objeto de um *endpoint* e tem como propósito ser usada como alvo em uma operação. (Documentada genericamente em [Atividades *Delete*](https://success.jitterbit.com/display/CS/common+delete+activities)).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Os registros detalhados (*verbose logging*) podem ser habilitados para muitos conectores quando são usados com um Private Agent. Consulte a documentação de cada conector, bem como o artigo [Registros Detalhados para Conectores](https://success.jitterbit.com/display/DOC/Verbose+Logging+for+Connectors) para saber mais detalhes.

</div>

</div>

## Pré-requisitos e Versões de API Suportadas

Um conector requer o uso de um agente versão [10.1](https://success.jitterbit.com/display/DOC/10.1) ou posterior. Estas versões de agente baixam automaticamente a versão mais atual do conector quando isso é exigido. Certos conectores podem exigir uma versão de agente específica ou mais posterior.

Os conectores normalmente usam uma API REST e um *driver* JDBC. Consulte a documentação da API, conforme a disponibilidade, para obter mais informações sobre os nós e os campos dos *schemas*.
