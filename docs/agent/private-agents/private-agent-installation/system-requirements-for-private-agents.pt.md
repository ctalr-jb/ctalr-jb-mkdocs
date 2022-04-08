# Requisitos de Sistema para Private Agents

[//]: # (This is a translation of Version 91, published on January 14, 2022.)

## Introdução

Estes requisitos de sistema aplicam-se aos Jitterbit Harmony Private Agents. Estes requisitos também são descritos nos guias de instalação dos Private Agents em sistemas [Linux](https://success.jitterbit.com/display/DOC/Downloading+and+Installing+a+Harmony+Linux+Agent) e [Windows](https://success.jitterbit.com/display/DOC/Downloading+and+Installing+a+Harmony+Windows+Agent).


## Considerações sobre o Sistema Operacional e Melhores Práticas

Antes da instalação, reveja o artigo [Alta Disponibilidade e Balanceamento de Cargas de Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing) e as seguintes considerações sobre o sistema operacional e melhores práticas.

### Considerações sobre o Sistema Operacional

Quando for decidir sobre instalar um Private Agent em um sistema operacional [Linux](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Linux+Agent) ou [Windows](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent), reveja as seguintes considerações:

-   **Versão**: Todos os Private Agents em um Agent Group específico devem ser instalados em máquinas usando o mesmo sistema operacional e a mesma versão do sistema operacional.

-   **APIs**: Os Agents do Linux podem aceitar uma carga de API mais alta (mais solicitações por minuto) do que Agents do Windows em máquinas idênticas ao usar APIs configuradas por meio do [API Manager](https://success.jitterbit.com/display/DOC/API+Manager).

-   **Bancos de Dados**: A autenticação do Windows com o Microsoft SQL Server é suportada apenas nos Private Agents do Windows.

-   ***File Shares***: A versão 2 do Server Message Block (SMBv2) usando os [conectores File Share do Cloud Studio](https://success.jitterbit.com/display/CS/File+Share) ou do [Design Studio](https://success.jitterbit.com/display/DOC/File+Share) está disponível apenas nos Private Agents do Windows.

-   **Microsoft Dynamics**: Os conectores da Microsoft Dynamics (tais como o [conector Microsoft Dynamics CRM](https://success.jitterbit.com/display/CS/Microsoft+Dynamics+CRM) para o Cloud Studio e os conectores [Microsoft Dynamics AX](https://success.jitterbit.com/display/DOC/Microsoft+Dynamics+AX+Connector), [CRM](https://success.jitterbit.com/display/DOC/Microsoft+Dynamics+CRM+Connector) e [GP](https://success.jitterbit.com/display/DOC/Microsoft+Dynamics+GP+Connector) para o Design Studio) exigem Private Agents do Windows.

### Melhores Práticas

Nós recomendamos seguir as seguintes boas práticas:

-   **Sistemas suportados**: Instale o Private Agent em um sistema testado e suportado conforme listado nesta página. Para obter os melhores resultados, recomendamos que você siga estes pré-requisitos para o sistema operacional, o banco de dados PostgreSQL e o *hardware*.

-   **Alta disponibilidade e balanceamento de carga**: Antes da instalação, reveja as recomendações sobre alta disponibilidade (ativo/ativo) e balanceamento de carga que estão descritas no artigo [Alta Disponibilidade e Balanceamento de Carga nos Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing).

-   **Instalação de servidor**: Para os ambientes de produção, recomendamos que o Private Agent seja instalado num servidor. A instalação de um agente numa máquina *desktop* é recomendada apenas para os ambientes de desenvolvimento, controle de qualidade ou teste.

-   **Instalação limpa**: Não instale o Private Agent num servidor que já esteja executando outro banco de dados. O agente instala e executa seu próprio banco de dados PostgreSQL. Executar o agente num servidor que já está executando um banco de dados Oracle ou SQL Server pode causar problemas de performance.

-   **Mesmo fuso horário**: Recomendamos que todos os agentes em um Private Agent Group tenham o mesmo fuso horário. Como o fuso horário de agendas configuradas depende do fuso horário do Private Agent, as execuções de agenda podem se tornar imprevisíveis se os fusos horários forem diferentes.

-   **Desinstalando**: Antes de desinstalar, nós recomendamos que você copie os arquivos de configuração e os certificados de segurança da sua instalação atual para o caso de que você queira reinstalar com as mesmas configurações em um momento posterior.


## Requisitos de Sistema Operacional

A Jitterbit requer que os sistemas operacionais usados para os Jitterbit Harmony Private Agents atendam às seguintes especificações:

### Linux

A versão do Linux do Jitterbit Harmony Private Agent requer um sistema operacional de 64 bits. Ela é suportada para as seguintes distribuições derivadas do Debian Linux e do Red Hat Enterprise Linux para *hardware* da Intel:

-   Debian 8.10 (“jessie”), 9.4 (“stretch”) e 10.6 (“buster”)

-   Ubuntu 14.04 LTS, 16.04 LTS, 18.04 LTS e 20.04 LTS

-   Red Hat Enterprise Linux (CentOS) 6, 7 e 8

-   [Amazon Linux AMI](https://aws.amazon.com/amazon-linux-ami/) e [Amazon Linux AMI 2](https://aws.amazon.com/amazon-linux-2/)

O Harmony Private Agent não foi certificado para outras distribuições similares derivadas das distribuições Debian e Red Hat. A [Amazon Linux](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/amazon-linux-ami-basics.html) oferece várias versões Linux, das quais apenas a [Amazon Linux AMI](https://aws.amazon.com/amazon-linux-ami/) e a [Amazon Linux AMI 2](https://aws.amazon.com/amazon-linux-2/) foram certificadas.

### Windows

A versão do Windows do Jitterbit Harmony Private Agent requer um sistema operacional de 64 bits e é suportada para as seguintes versões:

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

**NOTA**: A Jitterbit não testa nem suporta versões de* software *que não são mais suportadas pela Microsoft.

</div>

</div>

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**NOTA**: A partir do lançamento do Jitterbit Harmony 10.34, os Private Agents de 32 bits não estarão mais disponíveis para* download*. Se você estiver usando um agente de 32 bits atualmente e quiser seguir as nossas recomendações para continuar no lançamento atual, por favor baixe um agente de 64 bits e faça um* upgrade*. As instruções sobre como fazer o* upgrade *para um agente de 64 bits estão disponíveis tanto para Private Agents do [Linux](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Linux+Agent#InstallingaJitterbitHarmonyLinuxAgent-upgrade-agent) quanto do [Windows](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-upgrade-agent). Esta mudança não afeta os Cloud Agents.

</div>

</div>


## Pré-requisitos de *Software*

### Versão Exigida do Java

O pacote do Jitterbit Harmony Private Agent inclui uma versão de 64 bits do Java 8 Runtime Environment (Ambiente de Tempo de Execução Java 8, ou JRE, sigla em inglês) e não requer um tempo de execução Java separado. A Jitterbit instala automaticamente o Ambiente de Tempo de Execução Java exigido especificamente para ser usado pela Jitterbit para que ele não entre em conflito com outras instalações Java que podem já estar instaladas. A partir do Harmony 9.8, a versão do Java enviada com o Agent é o [AdoptOpenJDK JRE](https://adoptopenjdk.net/). A licença deste JRE é descrita no [*site* do OpenJDK](https://openjdk.java.net/legal/gplv2+ce.html).

#### Requisito da Extensão Unlimited Strength Java Cryptography

Para que o agente se comunique de forma segura com recursos tais como servidores, o Ambiente de Tempo de Execução Java (JRE, sigla em inglês) usado pelo agente precisa estar usando a Extensão de Criptografia Java (JCE, sigla em inglês), com os arquivos Unlimited Strength Jurisdiction Policy. Se você estiver usando o JRE que é mandado junto com o agente, ele está usando a JCE com os arquivos Unlimited Strength Jurisdiction Policy.

Se você usar um JRE diferente no lugar do que foi enviado junto com o agente, você terá que substituir os arquivos de política inclusos com o JRE pelos arquivos Unlimited Strength Jurisdiction Policy, caso ele já não os esteja usando. Para instalar os arquivos:

1.  Vá até o [site do Oracle](https://www.oracle.com/technetwork/java/javase/downloads/jce-7-download-432124.html) para baixar o arquivo ZIP contendo os arquivos Unlimited Strength Jurisdiction Policy da Java Cryptography Extension (JCE).

2.  Abra o arquivo ZIP para extrair os arquivos `local_policy.jar` e `US_export_policy.jar`.

3.  Copie e substitua os arquivos JAR existentes encontrados em `<JITTERBIT_HOME>\jre\lib\security`, substituindo `<JITTERBIT_HOME>` com o caminho até o diretório raiz do seu Private Agent.

4.  Reinicie o Jitterbit Private Agent.

### Linux

Os pré-requisitos para Linux são detalhados no artigo [Instalando um Jitterbit Harmony Linux Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Linux+Agent). Em resumo, as seguintes coisas são exigidas para a instalação de um Private Agent em um sistema Linux:

-   **Comandos**: Os seguintes comandos devem estar disponíveis: `python`, `sed`, `sudo`, `tar`, `unixodbc`, `unzip`.

-   **Bibliotecas**: Embora um Private Agent precise ser executado num sistema operacional de 64 bits, ele exige certas bibliotecas de 32 bits conforme especificado na seção [Pré-requisitos](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Linux+Agent#InstallingaJitterbitHarmonyLinuxAgent-prerequisites) do artigo [Instalando um Jitterbit Harmony Linux Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Linux+Agent).

### Windows

A versão para Windows do Jitterbit Harmony Private Agent requer:

-   **Atualizações do Windows**: Instale todas as atualizações “críticas” e de segurança do Windows antes de instalar ou fazer *upgrade* de Jitterbit Harmony Private Agents. Existem problemas conhecidos com a Microsoft quando se tenta instalar em sistemas que não têm as atualizações mais recentes (tais como [KB2966870](https://support.microsoft.com/en-us/kb/2966870) e [KB3140245](https://support.microsoft.com/en-us/help/3140245/update-to-enable-tls-1.1-and-tls-1.2-as-a-default-secure-protocols-in-winhttp-in-windows)).

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

<span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>

<div class="confluence-information-macro-body">

**ALERTA**: Se for instalar um agente anterior à versão 10.3, por favor reveja o erro [Troubleshoot Error 1722](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent#InstallingaJitterbitHarmonyWindowsAgent-troubleshoot-postgresql-errorsTroubleshooting) antes de instalá-lo.

</div>

</div>


## Requisitos de PostgreSQL

O PostgreSQL é instalado como parte da instalação do Harmony Private Agent. Esta instância do PostgreSQL é para uso somente com e pela Jitterbit.

-   ***Não instale*** o PostgreSQL separadamente antes de instalar a Jitterbit. A instalação da Jitterbit instala automaticamente a versão 9.6.11 de 64 *bits* do PostgreSQL com o *driver* PostgreSQL 9.3 ODBC. (*Upgrades* feitos aos Private Agents não atualizam uma versão já existente do PostgreSQL para esta versão; ela é deixada como está).

-   ***Não use*** um sinal de mais (`+`) como parte da senha do PostgreSQL ao instalar um Harmony Private Agent. O número máximo de caracteres para uma senha PostgreSQL é oito (8). Recomendamos que você não utilize caracteres com acentos (como “`é`”) nem nenhum dos caracteres a seguir na sua senha PostgreSQL: `+ @ $ % & [] {} () , ; ? ^ = £`

-   ***Não tenha*** nenhum outro banco de dados configurado ou executando na instância do Jitterbit PostgreSQL.

-   ***Não use*** o servidor ou o banco de dados Jitterbit PostgreSQL como parte de quaisquer operações ou *transformations* da Jitterbit.

-   ***Não use*** compressão do Windows na pasta da Jitterbit, na pasta PostgreSQL ou na pasta temporária na máquina onde o Jitterbit Private Agent estiver instalado e executando. Usar a compressão do Windows vai reduzir drasticamente a velocidade do processamento das operações e *transformations* da Jitterbit.

-   O [`PgBouncer`](https://pgbouncer.github.io/) pode ser necessário para ambientes de altas cargas. O Jitterbit Harmony Linux Private Agent [versão 10.6](https://success.jitterbit.com/display/DOC/10.6) e posteriores e o Jitterbit Harmony Windows Agent [versões 8.21](https://success.jitterbit.com/display/DOC/8.21.0) e posteriores automaticamente instalam o `PgBouncer`. Se você já tiver uma instalação atual do `PgBouncer` e tiver problemas ao fazer *upgrade*, por favor [entre em contato com o suporte](https://success.jitterbit.com/display/DOC/Getting+Support) para receber ajuda.

## Requisitos de *Hardware*

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
