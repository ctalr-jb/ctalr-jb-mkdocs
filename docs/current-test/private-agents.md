# Private Agents
[//]: # (This is a translation of Version 68, published on February 22, 2022.)


## Visão Geral

Quando você executa uma integração, a conectividade com os seus dados é habilitada através do(s) agente(s) que você configurou. Existem dois tipos de Jitterbit Agent Groups: *Cloud* (na nuvem) e *Private* (privados).

-   **Cloud**: O Jitterbit Cloud Agent Group consiste de um conjunto de Jitterbit Agents que são mantidos e gerenciados pela Jitterbit. Esta opção permite que você execute todas as suas integrações na nuvem com um Agent Group escalável, *multi-tenant* e tolerante a erros. O caso de uso mais comum é integração nuvem para nuvem. Para mais detalhes, veja o artigo [Cloud Agent Groups](https://success.jitterbit.com/display/DOC/Cloud+Agent+Groups).

-   **Private**: Você também pode fornecer e gerenciar os seus próprios Agents como Private Agent(s) e Private Agent Groups, como por exemplo nos seus próprios servidores, atrás de um *firewall* corporativo, ou em nuvens privadas virtuais. Esta opção permite que você escolha onde o seu ambiente de tempo de execução de integração opera e também que controle em qual rede seus dados transitam e residem. Os Private Agents permitem que você use arquivos locais como fontes ou alvos, adicione *plugins* customizados ou use *drivers* ODBC. Estas opções não estão disponíveis com os Cloud Agents.

Você escolhe qual Agent Group deseja usar no [Management Console](https://login.jitterbit.com/) (Console de Gerenciamento), conforme descrito em [Agents \> Agent Groups](https://success.jitterbit.com/display/DOC/Agents+%3E+Agent+Groups).

Estas páginas descrevem os Private Agents, bem como seus requisitos de sistema, instalação e administração:

-   **Requisitos de Sistema**<br/>
    Revise os [Requisitos de Sistema para Private Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents) para ter certeza de que você satisfaz os pré-requisitos de sistema operacional, banco de dados PostgreSQL e *hardware*.

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: A partir do lançamento 10.34 do Jitterbit Harmony, Private Agents de 32 bits não estarão mais disponíveis para *download*. Se você estiver atualmente usando um agente de 32 bits e quiser seguir a nossa recomendação de se manter atualizado com o lançamento mais recente, baixe um agente de 64 bits e faça um *upgrade*. Instruções sobre [como atualizar para um agente de 64 bits estão disponíveis](https://success.jitterbit.com/display/DOC/Private+Agents?hideelements=false#PrivateAgents-upgrade-agent). Esta mudança não afeta os Cloud Agents.

    </div>

    </div>

-   **Recomendações**<br/>
    Antes de instalar um Private Agent, consulte o artigo [Alta Disponibilidade e Balanceamento de Cargas de Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing) para ver recomendações que permitem alta disponibilidade e balanceamento de cargas. Além disso, veja também o [Tech Talk de Melhores Práticas com Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents+Best+Practices+Tech+Talk).

-   **Instruções de Instalação**<br/>
    Depois de revisar estes requisitos de sistema e recomendações, veja as instruções de instalação para o seu sistema operacional:

    -   **Linux**: [Instalando um Jitterbit Harmony Linux Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Linux+Agent) ([Debian](https://success.jitterbit.com/display/DOC/Installing+a+Linux+Private+Agent+on+Debian) ou [RPM](https://success.jitterbit.com/display/DOC/Installing+a+Linux+Private+Agent+on+RPM))

    -   **Windows**: [Instalando um Jitterbit Harmony Windows Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent)

    -   **Docker**: [Instalando um Jitterbit Harmony Docker Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Docker+Agent)

-   **Administração e Diagnóstico e Resolução de Problemas**<br/>
    Usar um Private Agent fornece a oportunidade para configurações adicionais que não estão disponíveis com o Cloud Agent Group. Por exemplo, você pode controlar a configuração do agente, usar arquivos locais como fontes ou alvos, e definir suas próprias variáveis Jitterbit. As páginas restantes desta seção descrevem a configuração bem como o diagnóstico e resolução de problemas com documentos para administradores de Private Agents, certificados de segurança, configurações de *proxy* e registros de depuração.

    Se você está administrando grupos de Private Agents, veja as seguintes páginas específicas:

    -   [Registro e Auto-escala Automática de Agentes](https://success.jitterbit.com/display/DOC/Agent+Automatic+Registration+and+Autoscaling)

    -   [Tutorial para Registro Automático de Docker Agents](https://success.jitterbit.com/display/DOC/Docker+Agent+Automatic+Registration+Tutorial)

    -   [Private Agents e Kubernetes](https://success.jitterbit.com/display/DOC/Private+Agents+and+Kubernetes)

    -   [Registros Detalhados para Conectores](https://success.jitterbit.com/display/DOC/Verbose+Logging+for+Connectors)

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" hasbody="true" macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Os Private Agents eram antes conhecidos como Local Agents.

</div>

</div>


## Fuso Horário

O fuso horário usado para as agendas é o mesmo do agente que está executando a operação, a menos que a configuração **Override Schedule Agent Time Zone** esteja habilitada nas [políticas da sua organização](https://success.jitterbit.com/display/DOC/Organizations#Organizations-organization-policies). Os fusos horários dos Private Agents são determinados pelo fuso horário do sistema operacional do Private Agent. É altamente recomendável que todos os agentes em um Private Agent Group estejam executando no mesmo fuso horário, ou então as horas em que uma agenda configurada inicia a operação podem se tornar imprevisíveis dependendo do agente específico que estiver sendo usado.
