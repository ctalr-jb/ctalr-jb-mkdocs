[//]: # (Exportação e Importação de Projetos)
[//]: # (This is a translation of Version 25, published on March 2, 2022.)

## Introdução

Você pode querer exportar um projeto do Cloud Studio para usar como *back-up* local ou como arquivo, ou para compartilhar uma cópia do projeto fora da sua organização. As exportações de projeto do Cloud Studio são no formato de um arquivo JSON. Quando você tiver exportado o arquivo JSON, ele pode ser importado em qualquer organização.


## Exportando um Projeto

As opções **Export** (Exportar) ou **Export Project** (Exportar Projeto) são acessíveis dos seguintes locais:

-   O índice de projetos (veja [Visualização de Cartões](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR#ProjectIndex-card-view) ou [Visualização de Lista](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR#ProjectIndex-list-view) em [Índice de Projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR)).

-   A barra de ferramentas de projeto (veja [Menu de Ações de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR#ProjectToolbar-project-actions-menu) em [Barra de Ferramentas de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR)).

Além disso, a tela de exportação de projeto é acessível usando o link **Export** na parte de baixo da tela **Project Settings** (Configurações de Projeto) (veja [Editando as Configurações do Projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR#ProjectCreationandConfiguration-edit-settings) em [Criação e Configuração de Projetos](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR)).

Ao selecionar **Export** (Exportar) ou **Export Project** (Exportar Projeto), a tela de exportação de projeto aparece, onde você pode escolher as opções de exportação e gerar o projeto como um arquivo JSON:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/export.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/export.png" /></span>

-   **Include Credentials** (Incluir Credenciais): Inclui no projeto exportado os valores especificados nos campos de credenciais das telas de configuração dos componentes do projeto.

    Os campos de configuração específicos que são tratados como campos de credenciais variam de acordo com o componente do projeto. Muitas vezes, estão incluidos nesse grupo campos como senhas ou *tokens* de segurança. Quem desenvolve conectores customizados usando o [Connector SDK](https://developer.jitterbit.com/connector-sdk/) podem designar tais campos com qualquer um dos atributos a seguir:

    -   **`"secret": "true"`:** Especifica apenas que o campo é tratado como um campo de credenciais. O valor do campo é criptografado na exportação do projeto.

    -   **`"widgetHint": "password"`:** Especifica que o campo é tratado como um campo de credenciais mas também esconde o valor na interface de usuário do Cloud Studio substituindo cada caractere com um ponto preto. O valor do campo é criptografado na exportação do projeto.

    Os valores das próprias variáveis de projeto não são tratados como credenciais, mesmo que a opção **Hide Value** (Esconder Valor) esteja selecionada na interface de usuário (veja [Variáveis de Projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR)). Em vez disso, o que controla se os valores das variáveis de projeto são incluídos ou não é a caixa de seleção **Include Project Variable Values** (Incluir Valores das Variáveis de Projeto).

    Se uma variável de projeto for usada num campo de credenciais (independentemente da caixa de seleção **Include Project Variable Values** estar marcada ou não), o valor `"value"` do campo de credencial é o valor criptografado da representação em sintaxe de colchetes do nome da variável de projeto e outras entradas, caso existam.

    Quando a caixa de seleção **Include Credentials** (Incluir Credenciais) não está selecionada, o valor `"value"` do campo de credencial não é incluído na exportação do projeto, a menos que uma variável de projeto seja usada num campo de credenciais. Neste caso, a entrada não-criptografada em texto puro do campo de credenciais é incluída. Isto pode ser um ponto de preocupação caso o campo de credenciais use qualquer outra entrada junto com a variável de projeto, embora este caso de uso não seja comum. Por exemplo, uma entrada em campo `[pv_password]1234suffix` seria incluída na exportação do projeto como `[pv_password]1234suffix`.

-   **Include Email Notifications** (Incluir Notificações de E-mail): Inclui [notificações de e-mail](https://success.jitterbit.com/display/CS/Email+Notifications?showLanguage=pt_BR) no projeto exportado. Esta opção se aplica a todas as notificações de e-mail de um projeto, independentemente de elas terem sido configuradas com [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) para executar em caso de sucesso, falha ou erro SOAP ou se elas são [referenciadas em um script](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR#JitterbitScript-notifications).

-   **Include Project Variable Values** (Incluir Valores de Variáveis de Projeto): Inclui valores padrão de [variáveis de projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR) no projeto exportado.

    Os valores de variáveis de projeto configuradas com a opção **Hide Value** (Esconder Valor) (veja [Variáveis de Projeto](https://success.jitterbit.com/display/CS/Project+Variables?showLanguage=pt_BR)) são criptografados no projeto exportado.

-   **Include Schedules** (Incluir Agendas): Inclui [agendas de operação](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR) no projeto exportado.

-   **Export** (Exportar): Gera e baixa o projeto como um arquivo JSON. Por padrão, o nome do arquivo JSON usa o nome do projeto.

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Um projeto exportado não inclui o [histórico do projeto](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR).

    </div>

    </div>


## Importando um Projeto

Para começar o processo de importação, do [índice de projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR), clique em **Import** (Importar) para começar:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project-index/import.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project-index/import.png" /></span>

Na próxima tela, você importa o projeto:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/project/import.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/project/import.png" /></span>

-   **Project File** (Arquivo do Projeto): Use o botão **Browse** (Navegar) para ir até um arquivo de projeto JSON que tenha sido exportado pelo Cloud Studio.

    <div class="confluence-information-macro confluence-information-macro-tip conf-macro output-block" hasbody="true" macro-name="tip">

    <span class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **DICA**: Caso o projeto use conectores customizados, eles devem existir na organização antes da importação do projeto. Para exportar um conector do Connector Builder e importá-lo em outra organização, veja [Exportações e Importações do Connector Builder](https://success.jitterbit.com/display/CS/Connector+Builder+Exports+and+Imports?showLanguage=pt_BR). Para instalar um conector do Connector SDK em outra organização, veja [Implementando um Conector do Harmony](https://developer.jitterbit.com/connector-sdk/implementing-a-harmony-connector/).

    </div>

    </div>

    Ao selecionar um arquivo, os campos a seguir ficam disponíveis:

    -   **Project Name** (Nome do Projeto): O nome do projeto é copiado do arquivo JSON. Para usar um nome diferente, você pode editá-lo aqui. O nome do projeto deve atender aos seguintes critérios:

        -   Ser único para cada ambiente.

        -   Não pode já estar em uso como um nome de projeto do [Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR) no mesmo ambiente.

        <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **NOTA**: Caso um projeto com o mesmo nome já exista na nuvem do Jitterbit Harmony, vá para a página [Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR) \> [Projetos](https://success.jitterbit.com/display/DOC/Projects?showLanguage=pt_BR) para gerenciar o projeto implantado.

        </div>

        </div>

    -   **Organization** (Organização): Use o menu *dropdown* para selecionar a [organização](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR) para a qual você deseja importar o projeto. Se você tiver apenas uma organização, ela é selecionada por padrão.

    -   **Environment** (Ambiente): Use o menu *dropdown* para selecionar o [ambiente](https://success.jitterbit.com/display/DOC/Environments?showLanguage=pt_BR) para o qual você deseja importar o projeto.

    -   **Include Email Notifications** (Incluir Notificações de E-mail): Por padrão, caso [notificações de e-mail](https://success.jitterbit.com/display/CS/Email+Notifications?showLanguage=pt_BR) tenham sido incluídas como parte do projeto quando ele foi exportado, elas serão incluídas quando ele é importado. Esta opção se aplica a todas as notificações de e-mail em um projeto, independentemente de elas terem sido configuradas com [ações de operação](https://success.jitterbit.com/display/CS/Operation+Actions?showLanguage=pt_BR) para executar em caso de sucesso, falha, ou erro SOAP ou se elas são [referenciadas em um *script*](https://success.jitterbit.com/display/CS/Jitterbit+Script?showLanguage=pt_BR#JitterbitScript-notifications). Para não incluir as notificações de e-mail na importação, desmarque a caixa de seleção.

        <div class="confluence-information-macro confluence-information-macro-note conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **CUIDADO**: Referências a um componente de notificação de e-mail em um *script* não são removidas mesmo que as notificações de e-mail sejam excluídas, então você pode precisar corrigir referências quebradas após excluir os e-mails.

        </div>

        </div>

    -   **Include Schedules** (Incluir Agendas): Por padrão, caso [agendas de operação](https://success.jitterbit.com/display/CS/Operation+Schedules?showLanguage=pt_BR) tenham sido incluídas como parte do projeto quando ele foi exportado, elas são incluídas quando ele é importado. Para excluir as agendas da importação, desmarque a caixa de seleção.

-   **Import** (Importar): Clique para importar o projeto. Se a importação do projeto ocorrer com sucesso, o projeto importado abrirá no [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas?showLanguage=pt_BR). Além disso, o novo projeto estará disponível no [índice de projetos](https://success.jitterbit.com/display/CS/Project+Index?showLanguage=pt_BR).

    Depois que um projeto é importado, ele ainda não está implantado. Quando você estiver pronto para implantar, veja [Implantação de Projetos](https://success.jitterbit.com/display/CS/Project+Deployment?showLanguage=pt_BR).
