[//]: # (Conexões)
[//]: # (This is a translation of Version 3, published on April 13, 2022.)


## Introdução

Uma conexão, criada usando um [conector](https://success.jitterbit.com/display/CS/common), estabelece acesso a um *endpoint*. Quando uma conexão está configurada, você pode criar instâncias de atividades associadas àquela conexão para serem usadas ou como fontes (para fornecer dados em uma operação) ou como alvos (para consumir dados em uma operação).


## Criando ou Editando uma Conexão de Conector

Uma nova conexão é criada usando um conector da aba **Connectivity** (Conectividade) da paleta de componentes de *design* (veja a seção [Conectores](https://success.jitterbit.com/display/CS/Design+Component+Palette#DesignComponentPalette-connectors) no artigo [Paleta de Componentes de Design](https://success.jitterbit.com/display/CS/Design+Component+Palette)).

Uma conexão existente pode ser editada a partir dos seguintes locais:

-   A aba **Connectivity** da paleta de componentes de *design* (veja a seção [*Endpoints*](https://success.jitterbit.com/display/CS/Design+Component+Palette#DesignComponentPalette-endpoints) no artigo [Paleta de Componentes de *Design*](https://success.jitterbit.com/display/CS/Design+Component+Palette)).

-   A aba **Components** do painel de projeto (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab#ProjectPaneComponentsTab-component-actions-menu) no artigo [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab)).


## Configurando uma Conexão de Conector

Cada elemento da interface de usuário de uma tela de configuração de conexão típica é descrito abaixo. Muitos conectores usam uma tela de configuração semelhante. Conectores que usam uma tela diferente são documentados com imagens mostrando a sua interface particular. Este exemplo, comum a muitos conectores, mostra uma conexão Dynamics 365 Sales:

<span class="confluence-embedded-file-wrapper"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/common-configuration.png" class="confluence-embedded-image confluence-external-resource" /></span>

<div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

<span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**DICA**: Campos que têm um ícone de variável <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://jitterbit.github.io/connectors-docs/common-connector/assets/variable-icon.png" class="confluence-embedded-image confluence-external-resource" /></span> suportam o uso de [variáveis globais](https://success.jitterbit.com/display/CS/Global+Variables), [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables) e [variáveis Jitterbit](https://success.jitterbit.com/display/CS/Jitterbit+Variables). Comece digitando um colchete esquerdo `[` no campo ou clicando no ícone de variável para exibir uma lista das variáveis existentes para escolher.

</div>

</div>

-   **Endpoint Name** (Nome do *Endpoint*): Coloque um nome a ser usado para identificar a conexão. O nome deve ser único para cada conexão e não deve conter barras (`/`) nem dois pontos (`:`). Este nome também é usado para identificar o *endpoint*, que se refere tanto à conexão específica quanto às suas atividades.

-   **Authentication** (Autenticação): Selecione para especificar as configurações de autenticação. Documentação sobre os campos específicos normalmente está disponível na seção **Opções de *String* de Conexão** da documentação de cada conector específico. Por exemplo, veja a seção [Autenticação](https://connectors.docs.jitterbit.com/dynamics_365_sales/connection.html#RSBDynamics365_c_Authentication) do Dynamics 365 Sales.

-   **Azure Authentication** (Autenticação Azure): Selecione para especificar as configurações de autenticação específicas ao Azure. Os conectores podem ter requisitos e opções de autorização específicos, e este exemplo mostra a localização das configurações particulares ao Azure. Documentação sobre os campos disponíveis normalmente está disponível na seção **Opções de *String* de Conexão** da documentação de cada conector individual. Para este exemplo, veja a seção [Autenticação Azure](https://connectors.docs.jitterbit.com/dynamics_365_sales/connection.html#RSBDynamics365_c_AzureAuthentication) do Dynamics 365 Sales.

-   **OAuth**: Selecione para especificar as configurações OAuth. Documentação sobre os campos disponíveis normalmente fica disponível na seção **Opções de *String* de Conexão** da documentação de cada conector individual. Por exemplo, veja a seção [OAuth](https://connectors.docs.jitterbit.com/dynamics_365_sales/connection.html#RSBDynamics365_c_OAuth) do Dynamics 365 Sales.

-   **SSL**: Selecione para especificar as configurações SSL. Documentação sobre os campos disponíveis normalmente fica disponível na seção **Opções de *String* de Conexão** da documentação de cada conector individual. Por exemplo, veja a seção [SSL](https://connectors.docs.jitterbit.com/dynamics_365_sales/connection.html#RSBDynamics365_c_SSL) do Dynamics 365 Sales.

-   **Use Proxy Settings** (Usar Configurações de *Proxy*): Selecione para usar as [configurações de *proxy* de Private Agent](https://success.jitterbit.com/display/DOC/Enabling+Proxy+for+Private+Agents).

-   **Advanced Configurations** (Configurações Avançadas): Selecione para especificar propriedades de configuração avançadas como os pares chave-valor. Documentação sobre as chaves e valores disponíveis fica normalmente disponível embaixo de **Outras Informações** na seção **Opções de *String* de Conexão** da documentação de cada conector individual. Por exemplo, veja a seção [Outras Informações](https://connectors.docs.jitterbit.com/dynamics_365_sales/connection.html#RSBDynamics365_c_Miscellaneous) do Dynamics 365 Sales.

-   **Test** (Teste): Clique para verificar a conexão usando a configuração especificada.

-   **Save Changes** (Salvar Mudanças): Clique para salvar e fechar a configuração da conexão.

-   **Discard Changes** (Descartar Mudanças): Depois de fazer mudanças a uma configuração nova ou existente, clique para fechar a configuração sem salvar. Uma mensagem pede que você confirme que quer descartar as mudanças.

-   **Delete** (Excluir): Depois de abrir uma configuração de conexão existente, clique para excluir permanentemente a conexão do projeto e fechar a configuração (veja [Dependências, Exclusão e Remoção de Componentes](https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal)). Uma mensagem pede que você confirme que quer excluir a conexão.


## Próximos Passos

Depois que uma conexão de conector foi criada, você coloca um tipo de atividade no design canvas para criar instâncias de atividade com o objetivo de usá-las ou como fontes (para fornecer dados em uma operação) ou como alvos (para consumir dados em uma operação).

As ações de menu de cada conexão e seus tipos de atividade são acessíveis a partir do painel de projeto e da paleta de componentes de *design*. Para saber mais detalhes, veja a seção [Menus de Ações](https://success.jitterbit.com/display/CS/Connector+Basics#ConnectorBasics-actions-menus) no artigo [Informações Básicas sobre Conectores](https://success.jitterbit.com/display/CS/Connector+Basics#ConnectorBasics).

Os tipos de atividade disponíveis dependem daquele conector em particular. Para muitos conectores, as seguintes atividades estão disponíveis:

-   [**Query**](https://success.jitterbit.com/display/CS/common+query+activities): Esta atividade busca um objeto de um *endpoint* e tem como propósito ser usada como fonte em uma operação. (Documentada genericamente em [Atividades *Query*](https://success.jitterbit.com/display/CS/common+query+activities)).

-   [**Create**](https://success.jitterbit.com/display/CS/common+create+activities): Esta atividade cria um objeto em um *endpoint* e tem como propósito ser usada como alvo em uma operação. (Documentada genericamente em [Atividades *Create*](https://success.jitterbit.com/display/CS/common+create+activities)).

-   [**Update**](https://success.jitterbit.com/display/CS/common+update+activities): Esta atividade atualiza um objeto em um *endpoint* e tem como propósito ser usada como alvo em uma operação. (Documentada genericamente em [Atividades *Update*](https://success.jitterbit.com/display/CS/common+update+activities)).

-   [**Delete**](https://success.jitterbit.com/display/CS/common+delete+activities): Esta atividade exclui um objeto de um *endpoint* e tem como propósito ser usada como alvo em uma operação. (Documentada genericamente em [Atividades *Delete*](https://success.jitterbit.com/display/CS/common+delete+activities)).
