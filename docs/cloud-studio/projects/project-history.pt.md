[//]: # (Histórico do Projeto)
[//]: # (This is a translation of Version 16, published on February 16, 2022.)

## Introdução

Esta página descreve como ver o histórico dos eventos do projeto, como adicionar *tags* a eventos, e como restaurar um projeto. O histórico do projeto é armazenado por no máximo 90 dias, e é limpado em projetos exportados.


## Vendo o Histórico do Projeto

A opção **Project History** (Histórico do Projeto) é acessível da barra de ferramentas de projeto (veja [Menu de Ações de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR#ProjectToolbar-project-actions-menu) em [Barra de Ferramentas de Projeto](https://success.jitterbit.com/display/CS/Project+Toolbar?showLanguage=pt_BR)).

Ao selecionar **Project History** (Histórico do Projeto), o histórico do projeto é mostrado dentro de um painel no lado direito do designer de projeto. Este painel mostra uma lista das mudanças e implantações do projeto, com a data e a hora em que um usuário específico realizou a ação, filtradas por período de tempo. Atualizações no histórico do projeto aparecem em tempo real, incluindo quando um projeto está sendo editado simultaneamente por vários colaboradores de projeto.

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_overview.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_overview.png" /></span>

-   **Last 30 Days** (Últimos 30 Dias), **Last 60 Days** (Últimos 60 Dias), ou **Last 90 Days** (Últimos 90 Dias): Use o menu *dropdown* para selecionar um período de tempo para exibir os eventos do histórico do projeto, entre 30, 60 ou 90 dias:

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_last-30-days.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_last-30-days.png" /></span>

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: O histórico do projeto é armazenado por no máximo 90 dias.

    </div>

    </div>

-   **All Events** (Todos os Eventos), **Deploys** (Implantações), **Migrations** (Migrações) ou **Tagged** (Com *Tags*): Use o menu *dropdown* para selecionar os tipos de eventos a exibir:

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_all-events.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_all-events.png" /></span>


    -   **All Events** (Todos os Eventos): Todos os eventos no histórico do projeto são exibidos, incluindo eventos do tipo mudança, exportação, migração, implantação e restauração. As *tags* que acompanham tais eventos são mostradas caso existam.

    -   **Deploys** (Implantações): Eventos de implantação são mostrados.

    -   **Migrations** (Migrações): Eventos migratórios são mostrados.

    -   **Tagged** (Com *Tags*): Eventos migratórios, de implantação e restauração que tenham [recebido uma *tag*](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR#ProjectHistory-tag) são mostrados.

-   **Date** (Data) e **Time** (Hora): Eventos do histórico do projeto são agrupados por dia e por intervalos de 30 minutos dentro de cada dia em ordem cronológica reversa (tanto para cada intervalo como para o período de tempo relatado), usando a hora do navegador local. Clique na fileira do dia ou da hora para expandir ou esconder os eventos que estão agrupados. Uma contagem de cada implantação, mudança ou migração é exibida abaixo de cada período de 30 minutos:

    <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_today.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_today.png" /></span>


-   **Events** (Eventos): Cada evento no histórico do projeto é listado com a hora e mostra o primeiro nome e a inicial do sobrenome do usuário que realizou a ação. Quando é selecionado, um evento é exibido com um fundo verde no painel do histórico do projeto. Cada tipo de evento é coberto da seguinte forma:

    -   **Change** (Mudança): O nome do componente no momento em que foi criado, atualizado ou deletado:

        <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_change.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_change.png" /></span>

        Quando selecionado, o design canvas põe o foco no componente selecionado (quando aplicável) e o destaca com um contorno verde, a aba **Workflows** do painel de projeto é exibida com um fundo verde, e o componente é selecionado na aba **Components** do painel de projeto.

    -   **Export** (Exportação): O nome do projeto na hora em que foi exportado:

        <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_export.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_export.png" /></span>

    -   **Migrate** (Migração): O nome do ambiente para onde o projeto migrou ou de onde migrou, junto com a *tag* de histórico do projeto exigida. Eventos de migração podem [receber uma *tag*](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR#ProjectHistory-tag) e [ser restaurados](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR#ProjectHistory-restore).

        <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_migrate.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_migrate.png" /></span>

    -   **Deploy** (Implantação): Um evento de implantação, junto com a *tag* de histórico do projeto daquele evento, caso exista. Eventos de restauração podem [receber uma *tag*](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR#ProjectHistory-tag) e [ser restaurados](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR#ProjectHistory-restore).

        <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_deploy.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_deploy.png" /></span>

    -   **Restore** (Restauração): O nome do projeto na hora em que foi restaurado, junto com a *tag* de histórico do projeto daquele evento, caso exista. Eventos de restauração podem [receber uma *tag*](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR#ProjectHistory-tag) e [ser restaurados](https://success.jitterbit.com/display/CS/Project+History?showLanguage=pt_BR#ProjectHistory-restore).

        <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_restore.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_restore.png" /></span>


## Adicionando uma *Tag* ou um Comentário a um Evento

Eventos de migração, implantação e restauração podem receber uma *tag* e um comentário dados pelo usuário. O uso de *tags* é recomendado para auxiliar com a criação de versões.

Eventos de migração devem receber uma *tag* na [tela de migração de projeto](https://success.jitterbit.com/display/CS/Project+Migration?showLanguage=pt_BR) antes que o projeto seja migrado.

Requisitos de implantação para exigir uma *tag* e/ou um comentário na hora da implantação podem ser configurados para cada projeto durante a [criação e configuração do projeto](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration?showLanguage=pt_BR). Quando os requisitos de implantação são configurados, uma caixa de diálogo é mostrada para inserir a *tag* e/ou o comentário exigido quando o [projeto é implantado](https://success.jitterbit.com/display/CS/Project+Deployment?showLanguage=pt_BR).

Para adicionar uma *tag* ou um comentário a partir do painel do histórico do projeto, paire o mouse sobre qualquer evento de migração, implantação ou restauração e clique no ícone de detalhes de implantação <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/deploy-details.png" class="confluence-embedded-image confluence-external-resource" /></span> para mostrar uma caixa de diálogo para inserir as informações da *tag* e do comentário:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_tag_dialog.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_tag_dialog.png" /></span>

-   **Tag**: Coloque uma *tag* para ser usada para rotular o evento no histórico do projeto. A *tag* vai aparecer como uma etiqueta ou rótulo no histórico de eventos do projeto. Inserir uma *tag* única é recomendado mas não exigido.

-   **Comment** (Comentário): Insira um comentário a ser usado para descrever o evento no histórico do projeto.

-   **Save** (Salvar): Salve as informações da *tag* e do comentário e feche a caixa de diálogo.

-   **Cancel** (Cancelar): Feche a caixa de diálogo sem salvar.

Eventos com *tags* são exibidos no painel do histórico do projeto com a *tag* visível abaixo do evento:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_tags.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_tags.png" /></span>

Você pode clicar na *tag* ou no ícone de detalhes de implantação <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/deploy-details.png" class="confluence-embedded-image confluence-external-resource" /></span> para reabrir a caixa de diálogo com os detalhes de implantação e fazer as edições que achar necessárias nas *tags* ou nos comentários que você adicionou. Se outro usuário tiver adicionado uma *tag* ou um comentário, os detalhes são mostrados mas não podem ser editados.

Pairar o mouse sobre a *tag* mostra uma pequena dica com o *MD5 digest* do projeto armazenado e o **Comment** (Comentário), caso exista:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_tag_hover.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_tag_hover.png" /></span>


## Restaurando um Projeto

*Back-ups* do projeto são criados automaticamente quando você migra, implanta ou restaura um projeto. Estes *back-ups* do projeto ficam disponíveis para restauração, quando acessados pelo histórico do projeto.

Depois de migrar, implantar ou restaurar um projeto, paire o mouse sobre um evento de migração, implantação ou restauração e clique no ícone de restauração <span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/restore.png" class="confluence-embedded-image confluence-external-resource" /></span>:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_restore-this-version.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/project-history_restore-this-version.png" /></span>

Uma mensagem de confirmação pede que você confirme que quer restaurar para a versão selecionada:

<span class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/dialog/restore-this-version.png" class="confluence-embedded-image confluence-external-resource" data-image-src="https://docs-source.jitterbit.com/cs/dialog/restore-this-version.png" /></span>

Clique em **Restore** (Restaurar) para reverter o designer de projeto para a versão implantada anteriormente e sobrescrever o projeto atual. Repare que esta ação se aplica apenas ao designer de projeto e não afeta a versão implantada. Implante de novo para implantar o estado restaurado.
