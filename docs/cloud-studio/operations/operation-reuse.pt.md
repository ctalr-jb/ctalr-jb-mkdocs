[//]: # (Reuso de Operações)
[//]: # (This is a translation of Version 12, published on November 09, 2021.)


## Introdução

Esta página descreve como reusar operações em um projeto. O reuso de outros tipos de componentes de projeto é abordado no artigo [Reuso de Componentes](https://success.jitterbit.com/display/CS/Component+Reuse).

Esta página é organizada nas seguintes seções:

- [**Terminologia de Reuso de Componentes**](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-terminology)<br/>
  Esta seção define a terminologia usada para falar do reuso de componentes. Reconhecer a diferença entre os componentes independentes e as referências a tais componentes forma a base necessária para entender termos relacionados da interface do usuário:

  - Duplicar uma operação para criar uma cópia da operação, ou com referências às etapas da operação ou com cópias das etapas da operação

  - Referenciar uma operação existente

  - Recortar ou copiar operações para colocá-las na sua área de transferência

  - Colar como nova operação ou como referência dependendo do contexto

- [**Recortar e Copiar Operações**](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-copying-and-cutting)<br/>
  Esta seção descreve os vários lugares dos quais você pode recortar e copiar operações. Recortar uma operação também exclui a operação ou sua referência do projeto, dependendo do lugar de onde ela foi recortada.

- [**Criar uma Nova Operação a Partir de uma Operação Existente**](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-operations)<br/>
  Esta seção descreve as várias formas em que você pode criar uma nova operação a partir de uma operação existente. Isto é feito ao se duplicar uma operação existente ou recortando/copiando e colando em locais designados. Você pode criar uma cópia de uma operação ou com referências às etapas (menos para certos tipos de atividade) ou com cópias das etapas. Cópias das operações com atividades da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud) e [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax) sempre criam tais atividades como atividades novas em vez de referências, já que reusar uma mesma instância desses tipos de atividade mais de uma vez não é permitido.

- [**Criar uma Referência a um Componente**](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-referencing)<br/>
  Esta seção descreve as várias formas em que você pode referenciar uma operação. As operações podem ser referenciadas várias vezes por qualquer combinação de outros componentes. No entanto, elas podem ser referenciadas apenas uma vez em um mesmo workflow.


## Problema Conhecido

Existe um problema conhecido com o reuso de componentes:

- **Recortar, copiar e colar usando o navegador Safari**

  - **Resumo**: Recortar, copiar e colar com o navegador Safari não funciona com as versões 14.0 e anteriores do Safari.

  - **Solução**: Atualize para o Safari versão 14.1 ou posterior.


## Terminologia do Reuso de Componentes

Os componentes de projeto conforme aparecem na interface de usuário do Cloud Studio podem ser *componentes independentes* ou *referências a componentes*:

- ***Componentes independentes*** são as partes individuais separadas de um projeto e são contidos na [aba **Components**](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR) do painel de projeto.

- ***Referências a componentes*** apontam para os componentes independentes. As referências a componentes nos workflows de um projeto são contidas no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR) e na [aba **Workflows**](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR) do painel de projeto. Os componentes também podem ser referenciados por componentes que não fazem parte de nenhum workflow.

Uma operação como componente independente pode ser reusada dentro de um projeto de duas formas:

- [***Duplicar***](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-copying) é usar a configuração já existente de uma operação para criar um componente independente novo dentro do projeto. Depois que você duplica uma operação, todas as mudanças que você fizer no componente independente original não serão refletidas na cópia, e todas as mudanças que você fizer na cópia não vão afetar o componente independente original. Quando você duplica uma operação, uma nova operação aparece na aba **Components** do painel de projeto e torna-se um componente independente no projeto.

  Você pode duplicar uma operação ou com referências às etapas ou com cópias das etapas:

  - Uma operação duplicada com referências às etapas tem referências às etapas da operação original. (Uma exceção: Atividades da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud) e [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax) são duplicadas em vez de referenciadas.)

  - Uma operação duplicada com cópias das etapas cria cópias de cada etapa da operação original como novos componentes.

- [***Referenciar***](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-copying) ou ***fazer referência*** é usar a mesma operação mais de uma vez em um projeto e é a forma em que se constrói workflows de projeto. Uma referência a um componente em um workflow é uma operação, atividade, *transformation*, *script* ou notificação de e-mail que é representada visualmente no design canvas e aparece na aba **Workflows** do painel de projeto (menos as notificações de e-mail). Referências a componentes também podem estar dentro de outros componentes, que podem ou não ser parte do workflow de um projeto. Por exemplo, uma operação pode ser referenciada numa ação de operação configurada em outra operação, e também referenciada em uma função de *script*, e também referenciada em um único workflow de projeto. Quando você faz referência a um componente dentro ou fora dos workflows de um projeto, a contagem de referências do componente na aba **Components** do painel de projeto aumenta.

A palavra ***cópia***, como substantivo, é usada para descrever um novo componente independente que foi criado a partir de uma operação existente.

As palavras ***recortar*** e ***copiar***, como ações, colocam uma cópia de uma operação na sua área de transferência que é então usada ou para criar um componente independente ou uma referência a componente. Qual das duas coisas será criada dependerá do contexto quando você colar:

- [***Recortar***](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-copying-and-cutting) coloca uma cópia de uma operação na sua área de transferência e exclui ou o componente independente original ou a referência ao componente, dependendo do lugar de onde a operação foi recortada:

  - Se uma operação for recortada da aba **Components** do painel de projeto, o componente independente original é excluído.

  - Se uma operação for recortada do design canvas ou da aba **Workflows** do painel de projeto, visto que o componente é uma referência a um componente independente original, apenas a referência é excluída e o componente independente original permanece inalterado.

- [***Copiar***](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-copying-and-cutting) coloca uma cópia de uma operação na sua área de transferência. O componente independente original permanece inalterado. Copiar e daí colar uma operação pode resultar em um componente independente novo ou em uma referência a componente, dependendo do contexto na hora de colar.

- ***Colar*** cria ou um componente independente ou uma referência a componente, dependendo do contexto na hora de colar. Por exemplo:

  - [Colar uma operação na aba **Components** do painel de projeto](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-paste-1) cria um componente independente novo.

  - [Colar uma operação uma única vez no design canvas](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-paste-1) cria um componente independente novo com referências às etapas (menos para as atividades da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud) e [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax), que são duplicadas) e uma referência a tal operação é adicionada ao workflow do projeto. [Colar a mesma operação mais vezes](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-paste-2) adiciona uma referência adicional à operação recém-criada no workflow do projeto.


## Recortar e Copiar Operações

Você pode acessar as ações de menu **Cut** (Recortar) e **Copy** (Copiar) a partir de um menu de ações de operação em qualquer um dos seguintes lugares:

- Componentes independentes na aba **Components** do painel de projeto (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-component-actions-menu) no artigo [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab)).

- Referências a componentes no design canvas (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) no artigo [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas)).

- Referências a componentes na aba **Workflows** do painel de projeto (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) no artigo [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu)).

Você também pode usar os atalhos de teclado padrão para recortar (`Control+X` no Windows ou no Linux e `Command+X` no macOS) e copiar (`Control+C` no Windows ou no Linux e `Command+C` no macOS).

Tanto recortar quanto copiar operações coloca uma cópia de uma operação na sua área de transferência.

Recortar uma operação do projeto (da aba **Components** do painel de projeto) exclui o componente independente original do projeto. Como a exclusão é exigida, recortar uma operação é possível apenas em operações não-referenciadas. As caixas de diálogo padrão para a exclusão são exibidas conforme está documentado no artigo [Dependências, Exclusão e Remoção de Operações](https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR).

Recortar uma operação de um workflow de projeto (do design canvas ou da aba **Workflows** do painel de projeto) exclui apenas a referência ao componente. O componente independente original permanece inalterado.


## Criando uma Nova Operação a Partir de uma Operação Existente

Você pode criar uma nova operação como um componente independente usando uma combinação das ações de menu **Cut** (Recortar), **Copy** (Copiar) e **Paste** (Colar) (ou seus respectivos atalhos de teclado) ou usando a ação de menu **Duplicate** (Duplicar).

Ao usar uma combinação das ações de menu **Cut**, **Copy** e **Paste** (ou seus atalhos), uma nova operação é criada usando a configuração da operação original com as seguintes exceções:

- Todas as agendas atribuídas são removidas.

- Todas as operações configuradas são removidas.

Ao usar a ação de menu **Duplicate**, uma nova operação é criada usando a mesma configuração da operação original, incluindo todas as agendas atribuídas e ações de operação configuradas.

O nome padrão da nova operação usa o nome do componente independente original acrescido da palavra *- Copy*. Cópias futuras receberão também um número incrementado entre parênteses.

### Colar

Quando você tiver uma cópia de uma operação na sua área de transferência, você pode colá-la no mesmo projeto usando a aplicação de navegação atual ou o modo do navegador do qual você a copiou. Colar operações entre projetos e entre modos de navegador não é suportado.

[Recorte ou copie uma operação](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-copying-and-cutting) e daí cole-a na aba **Components** do painel de projeto ou no design canvas:

- **Aba Components do Painel de Projeto**: Use a ação de menu **Paste Operation** (Colar Operação) no menu de ações de uma categoria de componente (veja a seção [Menu de Ações de Categoria](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-category-actions-menu) no artigo [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)). Esta ação está habilitada apenas quando você tem uma operação na sua área de transferência.

- **Design Canvas**: Selecione a área de inserção de uma operação no design canvas, e daí use a ação de menu **Paste** (Colar) que ela possui (veja a seção [Menu de Ações da Área de Inserção](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-drop-zone-actions-menu) no artigo [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)). Se um componente de operação for colado uma única vez no design canvas, um novo componente independente é criado e uma referência a este componente é adicionada ao workflow do projeto.

Ao criar a nova operação, o seu cursor será posicionado sobre o nome da operação para que você a renomeie.

### Duplicar

Você pode acessar a ação de menu **Duplicate** (Duplicar) no menu de ações de uma operação na aba **Components** do painel de projeto (veja a seção [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-component-actions-menu) no artigo [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)) ou no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR).

A ação de menu **Duplicate** (Duplicar) oferece a escolha entre dois métodos de duplicação:

- **With Step References** (Com Referências às Etapas): Cria apenas uma nova operação independente. A operação duplicada contém referências a cada uma das etapas da operação original, com exceção das atividades da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud) e [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax), que são duplicadas.

- **With Step Copies** (Com Cópias das Etapas): Cria uma nova operação independente e também novos componentes independentes referenciados como etapas de operação. Novos componentes são criados para cada etapa de operação e são referenciados pela nova operação.

Se a operação for criada a partir do design canvas, a nova operação também é referenciada no workflow do projeto. A nova operação é exibida imediatamente abaixo da operação original e o seu cursor é posicionado sobre o nome da operação original para que você a renomeie.


## Criar uma Referência a Componente

Uma operação pode ser referenciada por outros componentes ou workflows ao longo do projeto.

Uma operação pode ser referenciada várias vezes por qualquer combinação de outros componentes. No entanto, ela só pode ser referenciada uma vez dentro de um único workflow. Uma operação não pode ser referenciada várias vezes no mesmo workflow, nem referenciada em vários workflows.

### Referenciando uma Operação

Você pode referenciar a mesma operação várias vezes em vários lugares ao longo de um projeto conforme descrito abaixo.

#### Configurando uma Ação de Operação

Selecione uma operação ao configurar uma [ação de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) dentro de outra operação. A mesma operação pode ser sujeito de ações que estão configuradas para executar em caso de sucesso, erro ou erro SOAP de qualquer quantidade de outras operações no mesmo projeto.

#### Chamando uma Operação em um *Script*

Use uma operação com uma [Função Geral](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) Jitterbit Script que aceita um caminho de referência de operação como parâmetro, como por exemplo, `RunOperation` ou `GetLastOperationRunStartTime`. Uma operação pode ser chamada por funções qualquer número de vezes.

#### Arrastando e Soltando

Arraste uma operação que não está atualmente dentro de um workflow da [aba **Components** do painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR) até um workflow aberto no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/reuse-operation.gif" class="confluence-embedded-image confluence-external-resource" /></span>

Embora as operações não possam ser referenciadas por mais de um workflow, uma única operação pode tanto estar dentro de um único workflow quanto ser referenciada por uma ou várias ações de operação e/ou funções (independentemente de quaisquer associações com operações que podem ou não estar no mesmo ou em outro workflow).

Uma operação pode aparecer apenas uma vez no design canvas de um projeto.

#### Colando

Quando você tiver uma cópia de uma operação na sua área de transferência, você pode colá-la no mesmo projeto usando a mesma aplicação de navegador ou modo de navegação com que você a copiou. Colar operações entre projetos ou entre modos de navegação não é suportado.

[Recorte ou copie uma operação](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR#OperationReuse-copying-and-cutting), daí cole-a no design canvas usando a ação de menu **Paste** (Colar) disponível no menu de ações da área de inserção de uma operação (veja a seção [Menu de Ações da Área de Inserção](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-drop-zone-actions-menu) no artigo [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)). Se um componente de operação for colado uma única vez no design canvas, um componente novo e independente é criado e uma referência a tal componente é adicionada ao workflow do projeto. Colar a mesma operação mais vezes adiciona uma referência adicional à operação recém-criada no workflow do projeto.

### Ver o Número de Componentes e Referências a Workflows

Os componentes e referências a workflows são contados e exibidos dentro da [aba **Components** do painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR). A exibição depende de quantos componentes ou workflows fazem referência a tal componente.

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: O número de referências é baseado no projeto conforme ele existe atualmente no designer de projeto do Cloud Studio e não leva em consideração se os componentes já foram implantados no Harmony.

</div>

</div>

- **Nenhuma Referência**

  Se uma operação não for referenciada por nenhum outro componente ou workflow no projeto atual, ela é conhecida como operação órfã. Componentes órfãos, incluindo operações, são exibidos no painel de projeto com um ícone de não-referência (elo de corrente quebrado) <span class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://success.jitterbit.com/download/thumbnails/120718447/image2020-11-16_11-26-53.png?version=1&modificationDate=1605554061933&api=v2" class="confluence-embedded-image confluence-external-resource" /></span> ao lado do nome do componente.

  Por exemplo, depois de duplicar uma operação no painel de projeto, ela não aparece em nenhum workflow no design canvas, nem é referenciada por nenhum outro componente:

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/components/operations_unreferenced.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Uma Única Referência**

  Se uma operação for referenciada por apenas um outro componente ou workflow, ela é exibida sem nenhum indicador visual ao lado do nome do componente.

  Por exemplo, as seguintes operações estão ambas contidas em um workflow:

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/components/operations_single-reference.png" class="confluence-embedded-image confluence-external-resource" /></span>

- **Várias Referências**

  Se uma operação for referenciada por um componente ou workflow, ou se ele for referenciada por vários componentes, o número de componentes e/ou workflows que a referenciam é exibido ao lado do nome do componente, dentro de um círculo.

  Neste exemplo, as operações *Example Operation* e *Second Example Operation* estão ambas contidas em um workflow e cada uma tem uma ação de operação configurada para chamar *Example Operation - Copy*, que não está em nenhum workflow, o que resulta em duas contagens de referências:

  <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/components/operations_multiple-references.png" class="confluence-embedded-image confluence-external-resource" /></span>

  A contagem não é necessariamente o número de vezes que uma operação é referenciada; se uma operação for referenciada várias vezes por outro componente, isso pode contar como uma única ou várias referências, dependendo de como a operação foi referenciada. Cada ação de operação configurada conta como uma referência, mas várias referências por componentes que não são operações não são incluídas na contagem total.

  Por exemplo:

  - Um *script* que faz referência a uma operação duas vezes por meio de seu caminho de referência em um *script* - talvez usando tanto a função `GetLastOperationRunStartTime` quanto `RunOperation` — conta a referência à operação uma única vez.

  - Uma operação configurada para executar uma operação tanto em caso de sucesso quanto de falha da operação conta a referência à operação duas vezes.

Embora não haja indicação visual no painel de projeto de que uma ação de operação está configurada, você pode descobrir como as operações estão conectadas visualizando as dependências delas ou iniciando a caixa de diálogo de exclusão de operação, conforme descrito no artigo [Dependências, Exclusão e Remoção de Operações](https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR).

Por exemplo, quando você visualiza as dependências das operações *Example Operation* e *Second Example Operation*, você vê que *Example Operation - Copy* depende das duas primeiras operações. Quando você tenta excluir *Example Operation - Copy*, você vê *Example Operation* e *Second Example Operation* listadas como componentes que impedem a possibilidade de excluir *Example Operation - Copy*.
