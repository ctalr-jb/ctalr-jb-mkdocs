[//]: # (Reuso de Componentes)
[//]: # (This is a translation of Version 25, published on November 9, 2021.)

## Introdução

Esta página descreve como reusar componentes de projeto que são usados como etapas de operação ou em apoio a operações.

Esta página está organizadas nas seguintes seções:

-   [**Terminologia de Reuso de Componentes**](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-terminology)<br/>
    Esta seção define a terminologia usada para discutir o reuso de componentes. Reconhecer a diferença entre componentes independentes e referências a tais componentes é a base necessária para compreender os termos de interface do usuário relacionados:

    -   Duplicar um componente para criar uma cópia

    -   Referenciar um componente existente

    -   Recortar ou copiar componentes para colocá-los na sua área de transferência

    -   Colar como novo componente ou como referência dependendo do contexto

-   [**Recortando e Copiando Componentes**](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-copying-and-cutting)<br/>
    Esta seção descreve os vários lugares dos quais você pode recortar e copiar componentes. Recortar um componente também exclui o componente ou a sua referência do projeto, dependendo do lugar de onde ele foi recortado.

-   [**Criando um Novo Componente a Partir de um Componente Existente**](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-copying)<br/>
    Esta seção descreve as várias formas que você pode usar para criar um novo componente a partir de um componente existente. Tipicamente, isto é feito duplicando um componente existente ou recortando/copiando e depois colando em locais designados. Certos tipos de atividades (atividades da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), da [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud?showLanguage=pt_BR) e do [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax?showLanguage=pt_BR)) sempre resultam num novo componente quando são colados, já que reusar mais de uma da mesma instância desses tipos de atividade não é permitido.

-   [**Criando uma Instância de Atividade**](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-creating-an-activity-instance)<br/>
    Esta seção descreve as várias formas que você pode usar para criar um tipo de atividade como um componente novo e independente. Isto é feito arrastando e soltando ou copiando/recortando e colando em locais designados.

-   [**Criando uma Referência a Componente**](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-referencing)<br/>
    Esta seção descreve as várias formas em que você pode referenciar um componente. Certos componentes podem ser usados como etapas de operação, enquanto outros tipos de componentes podem ser usados em apoio a operações. A maioria desses tipos de componentes pode ser referenciada várias vezes.

Detalhes sobre como referenciar um *transformation* que usa um *schema* herdado de uma atividade são dados como complemento desta página em [Reuso de *Transformations*](https://success.jitterbit.com/display/CS/Transformation+Reuse?showLanguage=pt_BR).

A forma de reusar as próprias operações é descrita em [Reuso de Operações](https://success.jitterbit.com/display/CS/Operation+Reuse?showLanguage=pt_BR).


## Problema Conhecido

Existe um problema conhecido com o reuso de componentes:

-   **Recortando, copiando e colando com o navegador Safari**:

    -   **Resumo**: Recortar, copiar e colar com o navegador Safari não funciona com o Safari versões 14.0 ou anteriores.

    -   **Solução**: Atualize para o Safari 14.1 ou posterior.


## Terminologia do Reuso de Componentes

Os componentes de projeto conforme aparecem na interface de usuário do Cloud Studio podem ser *componentes independentes* ou *referências a componentes*:

-   ***Componentes independentes*** são as partes individuais que compõem um projeto e estão contidos na [aba **Components**](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR) do painel de projeto. Componentes independentes são os componentes do projeto.

-   ***Referências a componentes*** referem-se aos componentes independentes. Referências a componentes nos workflows do projeto são contidas no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR) e na [aba **Workflows**](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR) do painel de projeto. Os componentes também podem ser referenciados por componentes que não fazem parte de nenhum workflow.

Um componente independente pode ser reusado num projeto de dois jeitos:

-   [***Duplicar***](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-copying) é usar a configuração de um componente existente para criar um componente novo e independente em um projeto. Depois que você duplica um componente, quaisquer mudanças que você faça ao componente independente original não serão refletidas na cópia, e quaisquer mudanças que você faça à cópia não afetarão o componente independente original. Quando você duplica um componente, um novo componente aparece na aba **Components** do painel de projeto e é um componente independente no projeto.

-   [***Referenciar***](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-referencing) é usar o mesmo componente mais de uma vez num projeto e é a forma como os workflows de projeto são construídos. Uma referência a componente num workflow é uma operação, atividade, *transformation*, *script* ou notificação de e-mail que é representada visualmente no design canvas e aparece na aba **Workflows** do painel de projeto (menos as notificações de e-mail). Referências a componentes também podem estar em outros componentes, que podem ou não estar em workflows do projeto. Por exemplo, uma variável de projeto pode ser referenciada na configuração de uma atividade usada como etapa de operação em um workflow de projeto, e pode ser referenciada também num *script* mesmo que tal *script* não seja referenciado por nenhum workflow de projeto. Quando você referencia um componente dentro ou fora de workflows de projeto, a contagem de referências ao componente na aba **Components** do painel de projeto aumenta.

A palavra **cópia** é usada para descrever um componente novo e independente que foi criado a partir de um componente existente.

As ações de **recortar** e **copiar** ambas colocam uma cópia do componente na sua área de transferência que é então usada ou para criar um componente independente ou uma referência a componente. Qual das duas coisas será criada depende do contexto durante a colagem:

-   [***Recortar***](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-copying-and-cutting) coloca uma cópia do componente na sua área de transferência e exclui o componente independente original ou a referência ao componente, dependendo de onde o componente foi recortado:

    -   Se um componente é recortado da aba **Components** do painel de projeto, o componente independente original é excluído.

    -   Se um componente é recortado do design canvas ou da aba **Workflows** do painel de projeto, já que o componente é uma referência a um componente independente original, apenas a referência é excluída e o componente independente original permanece inalterado.

-   [***Copiar***](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-copying-and-cutting) coloca uma cópia do componente ou tipo de atividade na sua área de transferência. O componente independente original permanece inalterado. Recortar e daí colar um componente pode resultar ou num novo componente independente ou numa referência a componente, dependendo do contexto durante a colagem.

-   ***Colar*** cria um componente independente ou uma referência a componente, dependendo do contexto durante a colagem. Por exemplo:

    -   [Colar um componente ou tipo de atividade na aba **Components** do painel de projeto](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-paste-1) cria um componente novo e independente. [Colar um tipo de atividade](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-paste-2) cria uma instância de atividade como um componente novo e independente.

    -   [Colar um componente no design canvas](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-paste-3) adiciona uma referência ao componente independente original no workflow do projeto. (Uma exceção: colar uma atividade da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), da [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud?showLanguage=pt_BR) ou da [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax?showLanguage=pt_BR) no design canvas cria um componente independente novo em vez de uma referência a componente).

    -   [Colar um tipo de atividade no design canvas ou na aba **Workflows** do painel de projeto](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-paste-1) cria uma instância de atividade como um componente novo e independente e adiciona uma referência a tal atividade no workflow do projeto.


## Recortando e Copiando Componentes

Você pode acessar as ações de menu **Cut** (Recortar) e **Copy** (Copiar) a partir do menu de ações de um componente ou de um tipo de atividade em qualquer um dos seguintes locais:

-   Componentes independentes na aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-component-actions-menu) em [Aba Components do Painel do Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

-   Referências ao componente no design canvas (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

-   Referências ao componente na aba **Workflows** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR#ProjectPaneWorkflowsTab-component-actions-menu) em [Aba Workflows do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab?showLanguage=pt_BR)).

-   Tipos de atividade na aba **Connectiviy** (Conectividade) da paleta de componentes de design (veja [Menu de Ações de Conexão](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR#DesignComponentPalette-connection-actions-menu) e [Menu de Ações de Tipo de Atividade](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR#DesignComponentPalette-activity-actions-menu) em [Paleta de Componentes de Design](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR)).

Você também pode usar os atalhos de teclado padrão para recortar (`Control+X` no Windows ou no Linux e `Command+X` no macOS) e copiar (`Control+C` no Windows ou no Linux e `Command+C` no macOS).

Tanto recortar quanto copiar componentes colocam uma cópia do componente na sua área de transferência. Tipos de atividade também podem ser copiados da paleta de componentes de design; a cópia na área de transferência será usada para criar um novo componente no projeto (uma instância de atividade).

Recortar um componente independente do projeto (da aba **Components** do painel de projeto) exclui o componente independente original do projeto. Já que a exclusão é requerida, recortar um componente só é possível para componentes que não são referenciados. As caixas de diálogo padrão para exclusão são mostradas conforme documentado em [Dependências, Exclusão e Remoção de Componentes](https://success.jitterbit.com/display/DOC/Component+Dependencies%2C+Deletion%2C+and+Removal?showLanguage=pt_BR).

Recortar uma referência a componente de um workflow de projeto (do design canvas ou da aba **Workflows** do painel de projeto) exclui apenas a referência ao componente. O componente independente original permanece inalterado.


## Criando um Novo Componente a Partir de um Componente Existente

Criar um componente novo e independente a partir de um componente independente já existente está disponível para *schemas*, atividades, *scripts*, *transformations*, variáveis de projeto, notificações de e-mail e agendas.

Você pode criar um novo componente a partir destes componentes existentes usando uma combinação das ações de menu **Cut** (Recortar) e **Copy** (Copiar) (veja [Recortando e Copiando Componentes](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-copying-and-cutting) acima) e **Paste** (Colar) (veja [Colando](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-paste-1) abaixo) (ou os atalhos de teclado equivalentes) ou usando a ação de menu **Duplicate** (Duplicar) (veja [Duplicando](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-duplicate-1) abaixo). Existem formas adicionais de criar novas atividades da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud?showLanguage=pt_BR) e [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax?showLanguage=pt_BR) (veja [Atividades da Salesforce, Salesforce Service Cloud e ServiceMax](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-salesforce-based-activities) abaixo).

O nome padrão do novo componente usa o nome do componente independente original acrescido de *- Copy*. Cópias futuras são acrescidas também de um número incrementado entre parênteses. Já que os nomes de variáveis de projeto não podem ter espaços, hífens ou parênteses, o nome padrão de uma variável de projeto duplicada não usa parênteses e usa uma *underline* em vez dos espaços e do hífen.

### Colando

Quando você tem uma cópia de um componente na sua área de transferência, você pode colá-la no mesmo projeto usando a aplicação de navegação atual ou o modo do navegador de onde você a copiou. Colar componentes entre projetos ou modos de navegador diferentes não é suportado.

[Recorte ou copie um componente](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-copying-and-cutting), e daí use a ação de menu **Paste *Component Type*** (Colar *Tipo de Componente*) no menu de ações da categoria do componente na aba **Components** do painel de projeto (veja [Menu de Ações das Categorias](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-category-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)). Esta ação está disponível nas categorias **Files** (Arquivos), **Endpoints**, **Scripts**, **Transformations**, **Project Variables** (Variáveis de Projeto), **E-mails** e **Schedules** (Agendas), e só está disponível quando você tem um componente do tipo correspondente na sua área de transferência.

Ao criar o novo componente, o seu cursor é colocado sobre o nome do componente para renomeá-lo.

### Duplicando

Você pode acessar a ação de menu **Duplicate** (Duplicar) de um componente no projeto a partir do menu de ações do componente na aba **Components** do painel de projeto (veja [Menu de Ações de Componente](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-component-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)).

Ao clicar em **Duplicate**, um componente independente, não-referenciado e novo é criado usando a mesma configuração que o componente independente original.

### Atividades da Salesforce, Salesforce Service Cloud e ServiceMax

Para atividades da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud?showLanguage=pt_BR) e [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax?showLanguage=pt_BR), você também pode colar a atividade no design canvas para criar um componente novo e independente de uma das seguintes formas:

-   Selecione uma área de inserção no design canvas, daí use a ação de menu **Paste** (Colar) dela (veja [Menu de Ações da Área de Inserção](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-drop-zone-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)) para criar uma instância de atividade no projeto e adicionar uma referência a tal instância de atividade no workflow do projeto.

-   Selecione uma área de inserção no design canvas, daí use o atalho de teclado `Control+V` (no Windows ou no Linux) ou `Command+V` (macOS) para criar uma instância de atividade no projeto e adicionar uma referência a tal instância de atividade no workflow do projeto.

Você também pode arrastar uma atividade existente da Salesforce, Salesforce Service Cloud ou ServiceMax da [aba **Components** do painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR) para uma área de inserção de componentes no design canvas.

Ao colocar a atividade no design canvas, uma caixa de diálogo indica que um componente novo e independente será criado:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/creating-component-copy.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/creating-component-copy.png" /></span>


## Criando uma Instância de Atividade

Você pode criar uma instância de atividade como um componente novo e independente arrastando e soltando (veja [Arrastando e Soltando](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-drag-and-drop-1) abaixo) ou usando uma combinação das ações de menu **Copy** (Copiar) (veja [Copiando e Colando Componentes](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-copying-and-cutting) acima) e **Paste** (Colar) (veja [Colando](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-paste-2) abaixo) ou seus atalhos de teclado respectivos.

### Arrastando e Soltando

Arraste um tipo de atividade da [aba **Conectividade** da paleta de componentes de design](https://success.jitterbit.com/display/CS/Design+Component+Palette?showLanguage=pt_BR) para uma operação no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/create-activity-instance.gif" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/create-activity-instance.gif" /></span>

### Colando

Quando você copia um tipo de atividade, a cópia é usada para criar um componente novo e independente no projeto (uma instância de atividade).

Depois que você copia o tipo de atividade, você pode colá-lo no mesmo projeto usando a aplicação de navegação ou o modo do navegador de onde você o copiou. Colar tipos de atividades entre projetos e modos de navegador não é suportado.

[Copie um tipo de atividade](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-cutting-and-copying) e daí cole-o - criando uma instância de atividade como um componente independente - de uma das seguintes formas:

-   Use a ação de menu **Paste Activity** (Colar Atividade) acessível no menu de ações da categoria do componente na aba **Components** do painel de projeto (veja [Menu de Ações de Categoria](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-category-actions-menu) em [Aba Components do Painel de Projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR)) para criar uma instância de atividade no projeto.

-   Selecione uma área de inserção no design canvas, e daí use a ação de menu **Paste** (Colar) ofertada por ela (veja [Menu de Ações da Área de Inserção](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-drop-zone-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)) para criar uma instância de atividade no projeto e adicionar uma referência a tal instância de atividade no workflow do projeto.

-   Selecione uma área de inserção no design canvas, e daí use o atalho de teclado `Control+V` (Windows ou Linux) ou `Command+V` (macOS) para criar uma instância de atividade no projeto e adicionar uma referência a tal instância de atividade no workflow do projeto.


## Criando uma Referência a Componente

Certos tipos de componentes podem ser usados como etapas de operação, incluindo atividades, *scripts* e *transformations*. Outros tipos de componentes podem ser usados em apoio a operações. A maioria desses tipos de componentes pode ser referenciada várias vezes, conforme exposto abaixo.

### Componentes Usados como Etapas de Operação

Certos tipos de atividades, *transformations* e *scripts* podem ser referenciados múltiplas vezes como etapas numa operação:

-   **Atividades**: A maioria das atividades pode ser referenciada várias vezes como etapas de operação. Exceções incluem as atividades da [Salesforce](https://success.jitterbit.com/display/CS/Salesforce?showLanguage=pt_BR), [Salesforce Service Cloud](https://success.jitterbit.com/display/CS/Salesforce+Service+Cloud?showLanguage=pt_BR) e [ServiceMax](https://success.jitterbit.com/display/CS/ServiceMax?showLanguage=pt_BR), que não podem ser referenciadas por mais de um componente. Em vez disso, você pode fazer uma cópia de uma atividade da Salesforce, Salesforce Service Cloud ou ServiceMax para usar em outro lugar.

-   ***Transformations***: Todos os *transformations* podem ser referenciados várias vezes como etapas de operação. Ao referenciar um *transformation* usando um *schema* herdado de uma atividade, a ordem na qual as etapas de uma operação são configuradas controla como os *schemas* são propagados pelas referências aos *transformations*, conforme descrito em [Reuso de *Transformations*](https://success.jitterbit.com/display/CS/Transformation+Reuse?showLanguage=pt_BR).

-   ***Scripts***: Todos os *scripts* de componentes de projeto podem ser referenciados várias vezes como etapas de operação.

Você pode criar uma referência a um desses tipos de componentes como uma etapa de operação por arrastá-lo e soltá-lo ou usando uma combinação das ações de menu **Cut** (Recortar) ou **Copy** (Copiar) e **Paste** (Colar) ou seus atalhos de teclado respectivos.

#### Arrastando e Soltando

Arraste o componente da [aba **Components** do painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR) para uma operação no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR):

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/reuse-activity.gif" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/reuse-activity.gif" /></span>

#### Colando

Quando você tiver uma cópia de um componente na sua área de transferência, você pode colá-la no mesmo projeto usando a aplicação de navegação atual ou o modo do navegador do qual você a copiou. Colar componentes entre projetos e modos de navegador não é suportado.

[Recorte ou copie um componente](https://success.jitterbit.com/display/CS/Component+Reuse?showLanguage=pt_BR#ComponentReuse-copying-and-cutting), selecione uma área de inserção no design canvas, daí cole o componente de uma das seguintes formas:

-   Use a ação de menu **Paste** (Colar) acessível do menu de ações da área de inserção no design canvas (veja [Menu de Ações da Área de Inserção](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR#DesignCanvas-component-drop-zone-actions-menu) em [Design Canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR)).

-   Use o atalho de teclado `Control+V` (Windows ou Linux) ou `Command+V` (macOS).

### Componentes Usados em Apoio a uma Operação

A maioria dos componentes que não podem ser usados como etapas de uma operação podem ser reusados ou referenciados de outras formas. O reuso de componentes em apoio a operações é descrito na documentação de cada componente:

-   **Endpoints**: Os [endpoints](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR#JitterbitScript-connectors) no [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR), para usar certos tipos de conexões e atividades existentes como argumentos com funções Jitterbit

-   **Notificações**: [Notificações de email](https://success.jitterbit.com/display/CS/Email+Notifications?showLanguage=pt_BR), para conectar uma mensagem de e-mail existente em várias correntes de operação

-   **Operações**: [Operações](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR#JitterbitScript-operations) em [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR), para usar operações existentes como argumentos com funções Jitterbit

-   **Agendas**: [Agendas de Operações](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR), para aplicar agendas de operação a várias operações

-   ***Schemas***: [Schema de Arquivo Modelo](https://success.jitterbit.com/display/CS/Sample+File+Schema?showLanguage=pt_BR), para selecionar um *schema* salvo durante a definição de *schemas*

-   ***Scripts***: [Scripts](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR#JitterbitScript-scripts) em [Jitterbit Script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR), para usar *scripts* existentes como argumentos com funções Jitterbit

-   **Variáveis**: [Variáveis](https://success.jitterbit.com/display/CS/Variables?showLanguage=pt_BR), para referenciar variáveis que podem ser lidas diversas vezes

-   ***Plugins***: [*Plugins*](https://success.jitterbit.com/display/CS/Plugins?showLanguage=pt_BR), para aplicar *plugins* a atividades em uma operação ou executar um *plugin* dentro de um *script*

### Visualizando o Número de Referências a Componentes

Referências a componentes são contadas e exibidas dentro da [aba **Components** do painel de projeto](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab?showLanguage=pt_BR).

Caso um componente não seja referenciado por nenhum outro componente no projeto atual, ele é conhecido como um componente órfão. Componentes órfãos são exibidos com um ícone de não-referenciado (corrente quebrada) <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/unreferenced.png" class="confluence-embedded-image confluence-external-resource" /></span> ao lado do nome do componente.

Por exemplo, estes dois novos *scripts* não são usados dentro de nenhuma operação ou referenciados em outro lugar dentro do projeto:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_unreferenced.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_unreferenced.png" /></span>

Caso um componente seja referenciado por apenas um outro componente, ele é exibido no painel de projeto sem nenhum indicador visual ao lado do nome do componente.

Por exemplo, estes *scripts* são usados dentro de uma única operação cada um:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_single-reference.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_single-reference.png" /></span>

Caso um componente seja referenciado por vários componentes, o número de componentes que fazem isso é exibido ao lado do nome do componente, dentro de um círculo.

Neste exemplo, o primeiro *script* é referenciado tanto dentro de uma operação quanto por outro *script*, e o segundo *script* é referenciado por um *script* adicional:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_multiple-references.png class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_multiple-references.png" /></span>

Esta contagem não é necessariamente a quantidade de vezes que o componente é referenciado; caso um componente seja referenciado várias vezes por outro componente, isto conta como uma única referência. Por exemplo:

-   Uma variável de projeto que é referenciada várias vezes dentro de um *script* conta como tendo sido referenciada uma única vez.

-   Uma variável de projeto que é referenciada várias vezes dentro de uma configuração de atividade conta como tendo sido referenciada uma única vez.

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: O número de referências é baseado no projeto conforme ele existe atualmente no designer de projeto do Cloud Studio e não leva em consideração se os componentes foram implantados no Harmony.

</div>

</div>
