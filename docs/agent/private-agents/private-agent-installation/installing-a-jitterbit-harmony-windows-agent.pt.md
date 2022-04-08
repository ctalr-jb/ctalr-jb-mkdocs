# Instalando um Jitterbit Harmony Windows Agent

[//]: # (This is a translation of Version 81, published on February 1, 2022.)

## Visão Geral

Esta página abrange os requisitos de sistema e as instruções para baixar, instalar, configurar, reiniciar, atualizar, recolher e desinstalar o Harmony Private Agent em um sistema Windows. Antes da instalação, nós recomendamos que você revise os seguintes recursos: [Alta Disponibilidade e Balanceamento de Carga de Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing) e [Tech Talk de Melhores Práticas com Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents+Best+Practices+Tech+Talk).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: A partir do lançamento do Jitterbit Harmony 10.34, Private Agents de 32 bits não estarão mais disponíveis para *download*. Se você estiver usando atualmente um agente de 32 bits e quiser seguir a nossa recomendação de permanecer sincronizado com o lançamento atual, baixe um agente de 64 bits e faça o *upgrade*. As instruções para [fazer o *upgrade* para um agente de 64 bits estão disponíveis](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-upgrade-agent). Esta mudança não afeta os Cloud Agents.

</div>

</div>


## Problemas Conhecidos

-   **Windows Private Agents: Não foi possível instalar o agente de 64 bits com Autenticação de Dois Fatores (TFA, sigla em inglês)**

    -   **Resumo**: Instalar um Windows Private Agent de 64 bits não dá certo se a TFA estiver ativa.

    -   **Informações adicionais**: O instalador mostra uma caixa de diálogo de erro.

    -   **Solução**: Desabilite temporariamente a TFA e instale o Windows Private Agent de 64 bits. Depois da instalação, habilite a TFA.

## Requisitos de Sistema

### Melhores Práticas

-   **Sistemas suportados**: Instale o Private Agent em um sistema testado e suportado conforme listado nesta página. Para os melhores resultados, nós recomendamos que você siga os seguintes pré-requisitos para o sistema operacional, o banco de dados PostgreSQL e o *hardware*.

-   **Alta disponibilidade e balanceamento de carga**: Antes da instalação, reveja as recomendações de alta disponibilidade (ativo/ativo) e balanceamento de carga conforme descritas no artigo [Alta Disponibilidade e Balanceamento de Carga de Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing).

-   **Instalação em servidor**: Para ambientes de produção, nós recomendamos que você instale o Private Agent em um servidor. A instalação de agentes numa máquina *desktop* é recomendada apenas para ambientes de desenvolvimento, controle de qualidade ou teste.

-   **Instalação limpa**: Não instale o Private Agent num servidor que já esteja executando outro banco de dados. O agente instala e executa seu próprio banco de dados PostgreSQL. Executar o agente num servidor que já esteja executando um banco de dados Oracle ou SQL Server pode causar problemas de performance.

-   **Mesmo fuso horário**: Nós recomendamos que todos os agentes em um Private Agent Group tenham o mesmo fuso horário. Como o fuso horário das agendas configuradas depende do fuso horário do Private Agent, as execuções agendadas podem se tornar imprevisíveis se os fusos horários forem diferentes.

-   **Desinstalando**: Antes de desinstalar, nós recomendamos que você copie os arquivos de configuração e certificados de segurança da sua instalação atual para o caso de você querer reinstalar com as mesmas configurações numa data posterior.

### Requisitos do Sistema Operacional

A versão para Windows do Jitterbit Harmony Private Agent requer um sistema operacional de 64 bits e é suportada para as seguintes versões:

-   Windows 8 e 8.1

-   Windows 10

-   Windows 11

-   Windows Server 2012 e 2012 R2

-   Windows Server 2016

-   Windows Server 2019

-   Windows Server 2022

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: A Jitterbit não testa nem suporta versões de *software* não mais suportadas pela Microsoft.

</div>

</div>

### Pré-requisitos de *Software*

A versão para Windows do Jitterbit Harmony Private Agent requer:

-   **Atualizações do Windows**: Instale todas as atualizações “críticas” e de segurança do Windows antes de instalar ou atualizar os Jitterbit Harmony Private Agents. Existem problemas conhecidos ao instalar em sistemas que não tem as atualizações mais recentes (tais como [KB2966870](https://support.microsoft.com/en-us/kb/2966870) e [KB3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1.1-and-tls-1.2-as-a-default-secure-protocols-in-winhttp-in-windows)).

-   **.NET**: Pode ser necessário ter Microsoft .NET Framework 4.5 ou superior.

-   **NTFS**: A partição de instalação deve ser formatada para NTFS.

-   **Compressão: *Não use compressão do Windows*** na pasta da Jitterbit, na pasta PostgreSQL ou na pasta temporária na máquina onde o Jitterbit Private Agent estiver instalado e executando. Usar a compressão do Windows vai reduzir drasticamente a velocidade do processamento das operações e *transformations* da Jitterbit.

<div class="confluence-information-macro confluence-information-macro-note conf-macro output-block" data-hasbody="true" data-macro-name="note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**CUIDADO**: A Jitterbit recomenda que um Administrador local Windows seja usado para instalar o Agent.

</div>

</div>

<div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**ALERTA**: Se for instalar um agente anterior à versão 10.3, por favor reveja o erro [Troubleshoot Error 1722](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-troubleshoot-postgresql-errorsTroubleshooting) antes de instalá-lo.

</div>

</div>

### Ambiente de Tempo de Execução Java

O pacote do Jitterbit Harmony Private Agent inclui uma versão de 64 bits do Java 8 Runtime Environment (Ambiente de Tempo de Execução Java 8, ou JRE, sigla em inglês) e não requer um tempo de execução Java separado. A Jitterbit instala automaticamente o Java Runtime Environment 8.x especificamente para ser usado pela Jitterbit para que ele não entre em conflito com outras instalações Java que podem já estar instaladas.

#### Requisito da Extensão Unlimited Strength Java Cryptography

Para que o agente se comunique de forma segura com recursos tais como servidores, o Ambiente de Tempo de Execução Java (JRE, sigla em inglês) usado pelo agente precisa estar usando a Extensão de Criptografia Java (JCE, sigla em inglês), com os arquivos Unlimited Strength Jurisdiction Policy. Se você estiver usando o JRE que é mandado junto com o agente, ele está usando a JCE com os arquivos Unlimited Strength Jurisdiction Policy.

Se você usar um JRE diferente no lugar do que foi enviado junto com o agente, você terá que substituir os arquivos de política inclusos com o JRE pelos arquivos Unlimited Strength Jurisdiction Policy, caso ele já não os esteja usando. Para instalar os arquivos:

1.  Vá até o [site do Oracle](https://www.oracle.com/technetwork/java/javase/downloads/jce-7-download-432124.html) para baixar o arquivo ZIP contendo os arquivos Unlimited Strength Jurisdiction Policy da Java Cryptography Extension (JCE).

2.  Abra o arquivo ZIP para extrair os arquivos `local_policy.jar` e `US_export_policy.jar`.

3.  Copie e substitua os arquivos JAR existentes encontrados em `<JITTERBIT_HOME>\jre\lib\security`, substituindo `<JITTERBIT_HOME>` com o caminho até o diretório raiz do seu Private Agent.

4.  Reinicie o Jitterbit Private Agent.

### Requisitos PostgreSQL

O PostgreSQL é instalado como parte da instalação do Harmony Private Agent. Esta instância do PostgreSQL é para uso somente com e pela Jitterbit.

-   ***Não instale*** o PostgreSQL separadamente antes de instalar a Jitterbit. A instalação da Jitterbit instala automaticamente a versão 9.6.11 de 64 *bits* do PostgreSQL com o *driver* PostgreSQL 9.3 ODBC. (*Upgrades* feitos aos Private Agents não atualizam uma versão já existente do PostgreSQL para esta versão; ela é deixada como está).

-   ***Não use*** um sinal de mais (`+`) como parte da senha do PostgreSQL ao instalar um Harmony Private Agent. O número máximo de caracteres para uma senha PostgreSQL é oito (8). Recomendamos que você não utilize caracteres com acentos (como “`é`”) nem nenhum dos caracteres a seguir na sua senha PostgreSQL: `+ @ $ % & [] {} () , ; ? ^ = £`

-   ***Não tenha*** nenhum outro banco de dados configurado ou executando na instância do Jitterbit PostgreSQL.

-   ***Não use*** o servidor ou o banco de dados Jitterbit PostgreSQL como parte de quaisquer operações ou *transformations* da Jitterbit.

-   ***Não use*** compressão do Windows na pasta da Jitterbit, na pasta PostgreSQL ou na pasta temporária na máquina onde a Jitterbit estiver instalada e executando. Usar a compressão do Windows vai reduzir drasticamente a velocidade do processamento das operações e *transformations* da Jitterbit.

-   O [`PgBouncer`](https://pgbouncer.github.io/) pode ser necessário para ambientes de altas cargas. O Jitterbit Harmony Linux Private Agent [versão 10.6](https://success.jitterbit.com/display/DOC/10.6) e posteriores e o Jitterbit Harmony Windows Agent [versões 8.21](https://success.jitterbit.com/display/DOC/8.21.0) e posteriores automaticamente instalam o `PgBouncer`. Se você já tiver uma instalação atual do `PgBouncer` e tiver problemas ao fazer *upgrade*, por favor [entre em contato com o suporte](https://success.jitterbit.com/display/DOC/Getting+Support) para receber ajuda.

### Requisitos de *Hardware*

Estes são os requisitos mínimos de *hardware* e de máquina virtual para os Jitterbit Harmony Private Agents:

-   Processador *quad-core*

-   8 GB de memória RAM

-   50 GB de espaço disponível no disco rígido; isto inclui espaço para o *software*, processamento paralelo e armazenamento temporário que pode ficar bem grande enquanto uma operação está sendo executada

-   Taxa de transferência mínima de 100 MB/s (*megabytes* por segundo) no disco rígido

-   Conexão à internet de alta velocidade

-   Uma instalação no *hardware* direta ou uma instalação em uma máquina virtual VMWare, VirtualBox, Amazon AWS ou Rackspace que esteja configurada para os requisitos específicos descritos acima

-   Configuração ideal do sistema e do ambiente de forma geral; se estes não estiverem em suas configurações ideais, problemas esporádicos e imprevisíveis podem resultar de I/O (entrada e saída) de disco ruim, memória limitada ou esgotada, espaço em disco limitado ou esgotado, falhas de energia e/ou reinícios de sistema repentinos

-   Acesso à porta de saída 443 (HTTPS) para se comunicar com o Harmony. A Porta 443 é normalmente permitida por *firewalls* de servidores corporativos.

-   O acesso a portas de entrada específicas conforme solicitado; geralmente, portas de entrada não precisam ser abertas

É recomendado que a plataforma de APIs da Jitterbit seja usada para mensagens ou dados que entram. Onde um Private Agent é usado para receber uma mensagem diretamente (como uma mensagem da Salesforce que esteja saindo) no lugar da plataforma de APIs da Jitterbit, então as portas de entrada 443 (com SSL) ou 46909 (HTTPS) podem ser abertas. Portas customizadas podem ser usadas para requisitos específicos se forem redefinidas na configuração do Private Agent e se forem permitidas por quaisquer *firewalls* de servidores corporativos.

## Baixando o Private Agent

As seguintes instruções para baixar um Windows Private Agent partem do pressuposto que você já criou um Agent Group e Private Agent(s) para a sua organização dentro do [Management Console](https://login.jitterbit.com/jitterbit-cloud-mgmt-console/login/loginform) (Console de Gerenciamento). Consulte os artigos [Agents \> Agent Groups](https://success.jitterbit.com/display/DOC/Agents+%3E+Agent+Groups) e [Agents \> Agents](https://success.jitterbit.com/display/DOC/Agents+%3E+Agents) para mais informações.

1.  Faça *login* no [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal) e vá até [Management Console](https://success.jitterbit.com/display/DOC/Management+Console) \> **Agents** \> **Agent Groups**.

2.  Na parte superior da tela, selecione a fileira Agent Group. A parte inferior da tela agora deverá estar mostrando os **Available Agents** (*Agents* Disponíveis) dentro do Agent Group (Grupo de *Agents*) selecionado.

3.  Na parte inferior da tela, selecione a fileira do agente. Daí clique no menu *dropdown* **Action** (Ação) na extrema direita e selecione **Download for Windows EXE** (*Download* para Windows EXE).

4.  O agente Windows executável pode ser baixado, armazenado localmente e reutilizado conforme necessário para quaisquer Private Agents adicionais à medida que forem adicionados.

## Instalando um Private Agent

Instalar mais de um agente em um Agent Group automaticamente permite alta disponibilidade. Instalar vários agentes em um Agent Group também automaticamente permite balanceamento de carga. Veja o artigo [Alta Disponibilidade e Balanceamento de Cargas de Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing) para informações adicionais. Antes de instalar, tenha certeza de que todos os [requisitos e avisos de *software*](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-prerequisite-software-requirements) foram atendidos.

Em cada agente dentro do Agent Group:

1.  Execute o arquivo do agente Windows executável que foi baixado e siga as instruções.

2.  Na instrução **Login Credentials** (Credenciais de *Login*), insira as suas credenciais Jitterbit Harmony (o endereço de e-mail e a senha que você usa para entrar no endereço <https://login.jitterbit.com>).

    <div class="confluence-information-macro confluence-information-macro-note conf-macro output-block" data-hasbody="true" data-macro-name="note">

    <span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **CUIDADO**: Se a sua organização e a sua conta usarem *single sign-on* (SSO), as suas credenciais SSO normais não vão funcionar. Você deve usar credenciais do Harmony para instalar Private Agent(s). Consulte as informações em [Instalando um Private Agent](https://success.jitterbit.com/display/DOC/Registering+and+Logging+In+Using+Jitterbit+Harmony+SSO#RegisteringandLoggingInUsingJitterbitHarmonySSO-local-agent-sso) no artigo [Como se Registrar e Fazer *Login* Usando o Jitterbit Harmony SSO](https://success.jitterbit.com/display/DOC/Registering+and+Logging+In+Using+Jitterbit+Harmony+SSO) para saber mais.

    </div>

    </div>

3.  Siga as instruções para selecionar a sua organização, agente, etc. As opções disponíveis são aquelas que você já configurou no [Management Console](https://login.jitterbit.com/jitterbit-cloud-mgmt-console/login/loginform).

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Você precisa ser membro de um papel de organização que tenha permissões do tipo *Admin* (Administrador\[a\]) ou *Agent-Install* (Instalação de Agent). Veja o artigo [Organizações](https://success.jitterbit.com/display/DOC/Organizations) e a seção [Gerenciando Permissões, Papéis e Membros](https://success.jitterbit.com/display/DOC/Organizations#Organizations-managing) para saber mais.

    </div>

    </div>

4.  Quando chegar à instrução **Select Install Mode** (Selecionar Modo de Instalação), escolha o modo dependendo de se você está instalando o PostgreSQL ou se já tem uma instalação existente do PostgreSQL que gostaria de usar:

    -   **Quick Install** (Instalação Rápida) (**Opção Recomendada**): Instala todos os componentes necessários para executar um Private Agent incluindo um banco de dados e um *driver* do agente PostgreSQL. Use esta opção se você nunca tiver instalado o PostgreSQL ou um Private Agent neste computador antes, ou se você tiver corretamente desinstalado todos os componentes seguindo as instruções do artigo [Desinstalando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-uninstall-agent).

        <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

        <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

        <div class="confluence-information-macro-body">

        **NOTA**: Quando for pedido que você determine sua senha PostgreSQL, note que a senha deve estar de acordo com as políticas do seu sistema concernentes ao seu tamanho e complexidade.

        </div>

        </div>

    -   **Advanced** (Avançado): Instala um Private Agent e configura um banco de dados de Private Agent para usar uma instalação existente do PostgreSQL. Você terá que fornecer as suas credenciais PostgreSQL. Você pode querer usar essa opção se quiser gerenciar suas senhas separadamente dentro de cada aplicação.

5.  Depois da instalação, o agente deverá iniciar automaticamente. Você pode verificar o *status* do agente no [Management Console](https://login.jitterbit.com/jitterbit-cloud-mgmt-console/login/loginform) (**Menu** \> **Agents**), e ele deverá ser “Running” (Executando).

    <div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **NOTA**: Pode demorar mais de um minuto para que o Jitterbit Harmony Agent inicie e seja registrado com o Jitterbit Harmony.

    </div>

    </div>

    <div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

    <span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

    <div class="confluence-information-macro-body">

    **ALERTA**: Se você se deparar com erros relacionados ao PostgreSQL, consulte a seção [Diagnosticando e Resolvendo Erros de PostgreSQL](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-troubleshoot-postgresql-errors). Se você se deparar com a mensagem Error 1722, consulte a seção [Diagnosticando e Resolvendo o Erro 1722](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-troubleshoot-postgresql-errors). Se você continuar tendo problemas durante a instalação, por favor [entre em contato com o suporte](https://success.jitterbit.com/display/DOC/Getting+Support).

    </div>

    </div>


## Reiniciando um Private Agent

Reiniciar os serviços do agente é necessário sempre que você tiver feito mudanças nas configurações do seu agente. Reiniciar o agente também pode ser um bom passo do processo de diagnóstico e resolução de erros caso você esteja com problemas, os quais talvez se resolvam apenas com o reinício.

Embora o agente possa ser interrompido e daí reiniciado diretamente da máquina onde o Private Agent está instalado, é melhor se ele for interrompido primeiro no [Management Console](https://success.jitterbit.com/display/DOC/Agents+%3E+Agents#Agents%3EAgents-stop-agent-or-download-agent-logs) usando o comando “Drain Stop”, daí reiniciado usando os comandos na própria máquina do Private Agent.

O comando “Drain Stop” vai esperar um período de tempo para completar operações existentes e se recusar a aceitar novas. Operações de execução longa podem ser canceladas em vez de completar.

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Quando uma paragem do tipo *drain stop* é iniciada, o agente vai esperar 180 segundos até que quaisquer APIs terminem de executar antes de completar a paragem. Para os Private Agents, o tempo de espera pode ser configurado dentro do arquivo `jitterbit-agent-config.properties` por igualar `agent.drainstop.api.wait` ao número de segundos desejado.

</div>

</div>

Uma vez parado, o agente só pode ser reiniciado manualmente diretamente a partir da máquina do Private Agent.

1.  No [Management Console](https://success.jitterbit.com/display/DOC/Agents+%3E+Agents#Agents%3EAgents-stop-agent-or-download-agent-logs), selecione “Drain Stop” do menu para o agente. O agente então vai parar.

2.  O agente pode então ser reiniciado na máquina onde o Private Agent está instalado, de uma das seguintes formas:

    -   Do Menu de Início do Windows: Execute “Start Jitterbit Serviced” para reiniciar o serviço; ou

    -   Do diretório de instalação do Private Agent: Execute `StartServices.bat` para reiniciar o serviço.

Uma vez que o Private Agent tenha sido iniciado com sucesso, o *status* do agente no [Management Console](https://login.jitterbit.com/jitterbit-cloud-mgmt-console/login/loginform) do Jitterbit Harmony (**Menu** \> **Agents**) será “Running” (Executando). Você também pode usar os Windows Services para verificar que os Jitterbit Services estão todos em execução:

<span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/77109833/Services.PNG?version=1&modificationDate=1529701745994&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/77109833/Services.PNG?version=1&modificationDate=1529701745994&api=v2" /></span>

Se — após reiniciar o agente — você notar que nem todos os serviços Jitterbit foram reiniciados, tente parar e reiniciar o Private Agent. Se uma segunda tentativa de reinício não resolver a situação, então você deve [entrar em contato com o suporte](https://success.jitterbit.com/display/DOC/Getting+Support).


## Atualizando um Private Agent

<div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**ALERTA: Atualizando de um Windows Private Agent de 32 bits para um de 64 bits**

-   As versões de agente de 32 bits existentes devem ser desinstaladas antes da atualização (consulte as instruções para a [Desinstalação](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-uninstall-agent) [no Windows](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-uninstall-agent)).

-   As instalações atuais do PostgreSQL ou de *drivers* PostgreSQL (psqlODBC ou pODBC) devem ser desinstaladas.

-   Os *drivers* ODBC de 32 bits existentes não são suportados.

**NOTA**: Se você estiver atualizando um agente com versão de 64 bits já existente para um agente de 64 bits com versão mais alta, você não precisa desinstalar o agente existente antes de atualizar.

</div>

</div>

Atualizar o Private Agent no Windows pode ser feito usando instruções similares àquelas para [Instalar um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-install-agent). Siga as instruções para atualizar a instalação do seu Private Agent. Você não precisa desinstalar um agente existente antes de atualizar.

Se você estiver atualizando um agente com versão de 64 bits existente para um agente com versão de 64 bits mais alta, você não precisa desinstalar o agente existente antes de atualizar.

Um Private Agent demora pouco tempo para atualizar — algo como três minutos — dependendo do servidor. Se uma possível queda for uma preocupação, você pode usar [alta disponibilidade](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing) (dois ou mais agentes) para não ter tempo perdido. Se a sua assinatura atual não tiver nenhum agente adicional disponível para isso, [entre em contato com o seu ou a sua Customer Success Manager](https://success.jitterbit.com/display/DOC/Getting+Support) (Gerente de Sucesso do Cliente, ou CSM, sigla em inglês).

1.  Faça *backup* dos arquivos de configuração e certificados de segurança (opcional; veja a seção [Desinstalando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-uninstall-agent) abaixo).

2.  Verifique se você precisa desinstalar o agente primeiro, baseado no tipo do agente instalado: é de 32 bits (localizado em `C:\Arquivos de Programas (x86)\Jitterbit Agent`) ou de 64 bits (localizado em `C:\Arquivos de Programas\Jitterbit Agent`)?

3.  Instale a nova versão do agente (veja a seção [Instalando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-install-agent) acima).

4.  Para ver os arquivos de *backup* (opcional):

    1.  Pare os serviços de agente (veja a seção [Reiniciando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-restart-agent) acima).

    2.  Coloque os arquivos de configuração e certificados de segurança salvos no diretório de instalação.

    3.  Comece os serviços de agente (veja a seção [Reiniciando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-restart-agent) acima).

<div class="confluence-information-macro confluence-information-macro-warning conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-error confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**ALERTA**: Se você se deparar com um erro relacionado ao PostgreSQL, veja a seção [Diagnosticando e Resolvendo Erros de PostgreSQL](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-troubleshoot-postgresql-errors). Se você se deparar com uma mensagem Error 1722, veja [Diagnosticando e Resolvendo o Erro 1722](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-troubleshoot-postgresql-errors). Se você ainda estiver tendo problemas durante a atualização, por favor [entre em contato com o suporte](https://success.jitterbit.com/display/DOC/Getting+Support).

</div>

</div>


## Recolhendo um Private Agent

Não é normal ser necessário reverter para uma versão anterior de um Private Agent. No entanto, caso essa necessidade surja em algum momento, estes são os passos:

1.  Faça *backup* dos seus arquivos de configuração e certificados de segurança (opcional, veja a seção [Desinstalando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-uninstall-agent) abaixo).

2.  Desinstale o agente (veja a seção [Desinstalando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-uninstall-agent) abaixo).

3.  Remova todos os arquivos relacionados à Jitterbit (veja a seção [Desinstalando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-uninstall-agent) abaixo).

4.  Instale a versão selecionada do agente (veja a seção [Instalando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-install-agent) acima).

5.  Para usar os seus arquivos de *backup* (opcional):

    1.  Pare os serviços do agente (veja a seção [Reiniciando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-restart-agent) acima).

    2.  Coloque os seus arquivos de configuração e certificados de segurança salvos no diretório de instalação.

    3.  Comece os serviços do agente (veja a seção [Reiniciando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-restart-agent) acima).


## Desinstalando um Private Agent

Antes de desinstalar, é recomendado que você copie os arquivos de segurança e certificados de segurança da sua instalação atual para o caso de você querer reinstalar com a mesma configuração no futuro. Estes arquivos normalmente ficam localizados em:

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;"><b>Arquivos</b></div><div class="codeContent panelContent pdl">
<div><div id="highlighter_2731" class="syntaxhighlighter sh-confluence nogutter  java"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Hint: double-click to select code"><div class="line number1 index0 alt2"><code class="java plain"># Agentes de </code><code class="java value">32</code><code class="java plain"> bits</code></div><div class="line number2 index1 alt1"><code class="java plain">C:\Arquivos de Programas (x86)\Jitterbit Agent\jitterbit.conf</code></div><div class="line number3 index2 alt2"><code class="java plain">C:\Arquivos de Programas (x86)\Jitterbit Agent\apache\conf\httpd.conf</code></div><div class="line number4 index3 alt1"><code class="java plain">C:\Arquivos de Programas (x86)\Jitterbit Agent\JdbcDrivers.conf</code></div><div class="line number5 index4 alt2"><code class="java plain">C:\Arquivos de Programas (x86)\Jitterbit Agent\Resources\jitterbit-agent-config.properties</code></div><div class="line number6 index5 alt1"><code class="java plain">C:\Arquivos de Programas (x86)\Jitterbit Agent\Resources\credentials.txt</code></div><div class="line number7 index6 alt2">&nbsp;</div><div class="line number8 index7 alt1"><code class="java plain"># Agentes de </code><code class="java value">64</code><code class="java plain"> bits</code></div><div class="line number9 index8 alt2"><code class="java plain">C:\Arquivos de Programas\Jitterbit Agent\jitterbit.conf</code></div><div class="line number10 index9 alt1"><code class="java plain">C:\Arquivos de Programas\Jitterbit Agent\apache\conf\httpd.conf</code></div><div class="line number11 index10 alt2"><code class="java plain">C:\Arquivos de Programas\Jitterbit Agent\JdbcDrivers.conf</code></div><div class="line number12 index11 alt1"><code class="java plain">C:\Arquivos de Programas\Jitterbit Agent\Resources\jitterbit-agent-config.properties</code></div><div class="line number13 index12 alt2"><code class="java plain">C:\Arquivos de Programas\Jitterbit Agent\Resources\credentials.txt</code></div></div></td></tr></tbody></table></div></div>
</div></div>

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;"><b>Diretórios</b></div><div class="codeContent panelContent pdl">
<div><div id="highlighter_560332" class="syntaxhighlighter sh-confluence nogutter  java"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Hint: double-click to select code"><div class="line number1 index0 alt2"><code class="java plain"># Agentes de </code><code class="java value">32</code><code class="java plain"> bits</code></div><div class="line number2 index1 alt1"><code class="java plain">C:\Arquivos de Programas (x86)\Jitterbit Agent\apache\conf\extra\</code></div><div class="line number3 index2 alt2"><code class="java plain">C:\Arquivos de Programas (x86)\Jitterbit Agent\apache\conf\ssl.crt\</code></div><div class="line number4 index3 alt1"><code class="java plain">C:\Arquivos de Programas (x86)\Jitterbit Agent\apache\conf\ssl.key\</code></div><div class="line number5 index4 alt2">&nbsp;</div><div class="line number6 index5 alt1"><code class="java plain"># Agentes de </code><code class="java value">64</code><code class="java plain"> bits</code></div><div class="line number7 index6 alt2"><code class="java plain">C:\Arquivos de Programas\Jitterbit Agent\apache\conf\extra\</code></div><div class="line number8 index7 alt1"><code class="java plain">C:\Arquivos de Programas\Jitterbit Agent\apache\conf\ssl.crt\</code></div><div class="line number9 index8 alt2"><code class="java plain">C:\Arquivos de Programas\Jitterbit Agent\apache\conf\ssl.key\</code></div></div></td></tr></tbody></table></div></div>
</div></div>

<div class="confluence-information-macro confluence-information-macro-note conf-macro output-block" data-hasbody="true" data-macro-name="note">

<span class="aui-icon aui-icon-small aui-iconfont-warning confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**CUIDADO**: Para poder usar os seus arquivos de *backup* numa instalação futura, você precisa deter os serviços enquanto move os arquivos, daí reiniciar os serviços quando tiver terminado (veja [Reiniciando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-restart-agent)).

</div>

</div>

Para desinstalar um Private Agent, os seguintes passos são recomendados para remover tanto o Private Agent quanto a instalação do PostgreSQL:

1.  Desinstale estas aplicações (isto pode ser feito a partir do seu Painel de Controle em **Programas e Recursos** \> **Desinstalar um programa**):

    -   Jitterbit Agent

    -   PostgreSQL (a versão pode variar em relação à mostrada abaixo)

    -   O *driver* PostgreSQL (pode ser chamado de *psqlODBC* ou *pODBC*; a versão pode variar em relação à mostrada abaixo)

        <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-55-23.png?version=1&modificationDate=1525207191841&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-55-23.png?version=1&modificationDate=1525207191841&api=v2" /></span>

2.  Delete o usuário Jitterbit PostgreSQL. Isto pode ser feito de várias maneiras:

    -   Abra a janela **Usuários e Grupos Locais** a partir do Painel de Controle em **Contas de Usuários** \> **Editar usuários e grupos locais** ou usando um Prompt de Comando e inserindo o comando `lusrmgr.msc`. Clique com o botão direito do *mouse* sobre o usuário *jitterbitpostgres* e selecione **Deletar**.

        <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-51-58.png?version=1&modificationDate=1525207191872&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-51-58.png?version=1&modificationDate=1525207191872&api=v2" /></span>

    -   Abra a janela **Contas de Usuários** usando um Prompt de Comando para inserir o comando `netplwiz`. Selecione o usuário *jitterbitpostgres* e clique em **Remover**.

    -   Use um Prompt de Comando para inserir o seguinte comando:

        ```
        net user jitterbitpostgres /delete
        ```

3.  Delete a pasta de usuário Windows para o usuário *jitterbitpostgres* da pasta *Usuários* do sistema de arquivos:

    <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-45-39.png?version=1&modificationDate=1525207191903&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-45-39.png?version=1&modificationDate=1525207191903&api=v2" /></span>

4.  Delete a pasta **PostgreSQL** da pasta *Arquivos de Programas* do sistema de arquivos:

    <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-49-21.png?version=1&modificationDate=1525207191887&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-49-21.png?version=1&modificationDate=1525207191887&api=v2" /></span>

5.  Delete a pasta **PostgreSQL** da pasta *Arquivos de Programas (x86)* do sistema de arquivos:

    <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-50-23.png?version=1&modificationDate=1525207191872&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/77109833/image2017-10-16_12-50-23.png?version=1&modificationDate=1525207191872&api=v2" /></span>


## Diagnosticando e Resolvendo Erros

### Erro 1722

Existem várias razões pelas quais a instalação do Private Agent pode falhar com a seguinte mensagem de erro:

```
Error 1722. There is a problem with this Windows Installer package. A program run as part of the setup did not finish as expected. Contact your support personnel or package vendor. ...
```

O motivo mais comum para esta falha é um conflito com uma versão já existente do Microsoft Visual C++ Redistributable.

### Microsoft Visual C++ Redistributables

Os Private Agents requerem que o [Microsoft Visual C++ Redistributable for Visual Studio 2015, 2017, 2019](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) esteja instalado antes de instalar um Private Agent. A Microsoft agora inclui os mesmos arquivos redistribuíveis para o Visual Studio C++ 2015, 2017 e 2019. Instale a versão apropriada para corresponder à sua versão do Windows:

-   Windows de 32 bits: Instale o arquivo `vc_redist.x86.exe`

-   Windows de 64 bits: Instale o arquivo `vc_redist.x64.exe`

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: Se você estiver instalando um Private Agent anterior à versão 10.3 e bibliotecas do Visual Studio tais como as versões anteriores do Visual Studio C++ Redistributable for Visual Studio 2017 ou mais altas já estiverem instaladas, a instalação irá falhar. Uma solução possível é baixar e instalar os arquivos apropriados disponíveis em [Microsoft Visual C++ Redistributable for Visual Studio 2015, 2017, 2019](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads) e daí instalar o Private Agent.

A partir da versão 10.3 do Jitterbit Harmony, isto foi consertado. A instalação numa máquina que já tem uma versão do Visual C++ Redistributable for Visual Studio acima da 2015 já ocorre com sucesso. Se você ainda estiver encontrando problemas, por favor [entre em contato com o suporte](https://success.jitterbit.com/display/DOC/Getting+Support).

</div>

</div>

### Erros de PostgreSQL

Em certos casos, depois de desinstalar um Windows Private Agent e em seguida tentar reinstalar o agente, os usuários podem encontrar um erro relacionado ao banco de dados PostgreSQL.

Foi observado que este erro ocorre em sistemas onde a instalação do PostgreSQL associada com o Private Agent não foi completamente removida.

Para resolver o erro, os usuários devem seguir os passos descritos acima na seção [Desinstalando um Private Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-uninstall-agent) para remover completamente a conta de usuário do Jitterbit PostgreSQL. As instruções para remover manualmente todos os arquivos do PostgreSQL estão nos passos 2 a 5.

Quando isto estiver feito, você deverá conseguir completar uma nova instalação de agente. Se você ainda estiver encontrando problemas, por favor [entre em contato com o suporte](https://success.jitterbit.com/display/DOC/Getting+Support).

### Windows Private Agents Instalados em um Servidor Azure

Ao usar um Windows Private Agent instalado em um servidor Microsoft Azure, você pode acabar tendo conexões perdidas. O Azure estabelece o *websocket idle timeout* para 4 minutos, enquanto o tempo padrão do Private Agent é de 5 minutos. Para resolver este problema, reduza o intervalo da batida do agente:

1.  Faça uma cópia de *backup* do arquivo `jitterbit-agent-config.properties` e salve-o em outro lugar. Este arquivo pode ser encontrado no diretório `\Arquivos de Programas (x86)\Jitterbit Agent\Resources` no Windows.

2.  Abra o arquivo `jitterbit-agent-config.properties` num editor de texto.

3.  Encontre a configuração `agent.heart.beat.interval`:

    ```
    #Agent heart beat interval (IN MINUTES)
    agent.heart.beat.interval=5
    ```

4.  Mude a configuração para `agent.heart.beat.interval=3`.

5.  Salve as mudanças e reinicie o agente.

### Problemas de IPv6

Alguns clientes já tiveram problemas quando o Internet Protocol version 6 (IPv6) está habilitado. Nestes casos, recomendamos que você desabilite o IPv6 e o IP Helper.

Para desabilitar o IPv6:

1.  No Windows, abra o **Painel de Controle** \> **Rede e Internet** \> **Central de Rede e Compartilhamento**.

2.  Abra as **Propriedades** de uma conexão.

3.  Desmarque a caixa de seleção do **Internet Protocol Version 6 (TCP/IPv6)**:

    <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/77109833/image2021-1-27_13-29-34.png?version=1&modificationDate=1612303267286&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/77109833/image2021-1-27_13-29-34.png?version=1&modificationDate=1612303267286&api=v2" /></span>

Para desabilitar o IP Helper:

1.  No Windows, abra **Serviços**.

2.  Localize **Auxiliar de IP** na lista de serviços. Daí clique com o botão direito sobre **Auxiliar de IP** e selecione **Propriedades**.

3.  Nas **Propriedades do Auxiliar de IP**, clique em **Parar** para deter o serviço, e mude o **Tipo de inicialização** para **Desabilitado**:

    <span class="confluence-embedded-file-wrapper"><img src="https://success.jitterbit.com/download/attachments/77109833/image2021-1-27_13-34-41.png?version=1&modificationDate=1612303267460&api=v2" class="confluence-embedded-image confluence-external-resource" data-image-src="https://success.jitterbit.com/download/attachments/77109833/image2021-1-27_13-34-41.png?version=1&modificationDate=1612303267460&api=v2" /></span>

### Erro de *Slot* de Conexão

Você pode receber um erro similar a este:

```
FATAL: remaining connection slots are reserved for non-replication superuser connections
```

Para resolver, consulte o artigo [Consertando Erros Causados pelas Configurações postgresql.conf com Windows Private Agents de 64 bits](https://success.jitterbit.com/display/DOC/Fixing+Errors+Caused+by+postgresql.conf+Settings+with+Windows+64-bit+Private+Agents).
