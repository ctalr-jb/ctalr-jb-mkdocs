# Instalando um Jitterbit Harmony Linux Agent

[//]: # (This is a translation of Version 104, published on January 26, 2022.)

## Visão Geral

Estes são os requisitos de sistema para instalar o Harmony Private Agent num sistema Linux. Antes da instalação, nós recomendamos que você reveja os seguintes recursos: [Alta Disponibilidade e Balanceamento de Cargas de Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing) e [Tech Talk de Melhores Práticas com Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents+Best+Practices+Tech+Talk).

Para instruções sobre como baixar, instalar, configurar, reiniciar, atualizar, recolher e desinstalar um Linux Private Agent, veja a página apropriada para as distribuições suportadas:

-   [Instalando um Linux Private Agent no Debian](https://success.jitterbit.com/display/DOC/Installing+a+Linux+Private+Agent+on+Debian)

-   [Instalando um Linux Private Agent no RPM](https://success.jitterbit.com/display/DOC/Installing+a+Linux+Private+Agent+on+RPM)

-   [Configurando um Linux Private Agent](https://success.jitterbit.com/display/DOC/Configuring+a+Linux+Private+Agent)

-   [Reiniciando um Linux Private Agent](https://success.jitterbit.com/display/DOC/Restarting+a+Linux+Private+Agent)

-   [Atualizando ou Desinstalando um Linux Private Agent](https://success.jitterbit.com/display/DOC/Upgrading+or+Uninstalling+a+Linux+Private+Agent)


## Problemas Conhecidos

A versão 10.38 do Linux Private Agent tem o seguinte problema conhecido:

-   **O banco de dados PostgreSQL é reinicializado quando se faz o *upgrade* da versão 10.37 para a 10.38**

    -   **Contexto**: Quando se atualiza um Linux Private Agent de uma versão anterior à 10.37 para uma versão que é a 10.37 ou uma posterior, o banco de dados PostgreSQL será reinicializado, já que ele é atualizado para a versão 9.6. Esta atualização irá recriar o banco de dados no seu Private Agent e os seus dados irão ser recuperados durante este processo de *upgrade*. Depois dele, quaisquer *backups* criados usando uma versão anterior do PostgreSQL não serão compatíveis. O processo de *upgrade* pode demorar mais de 30 minutos dependendo do número de projetos e do tamanho dos ambientes associados com o seu Private Agent Group. Quaisquer tarefas pendentes serão postas numa fila de tarefas em aberto a serem executadas depois que o *upgrade* estiver completo. Este *upgrade* não envolve o Windows Private Agent.

    -   **Problema Conhecido**: É um problema conhecido que ao atualizar um Linux Private Agent da versão 10.37 para a 10.38, o banco de dados PostgreSQL é reinicializado.

    -   **Solução**: Faça *upgrade* para um Linux Private Agent que seja versão 10.39 ou posterior.


## Requisitos de Sistema

### Melhores Práticas

-   **Sistemas suportados**: Instale o Private Agent num sistema testado e suportado conforme listados nesta página. Para obter os melhores resultados, nós recomendamos que você obedeça aos seguintes pré-requisitos para o sistema operacional, para o banco de dados PostgreSQL e para o *hardware*.

-   **Alta disponibilidade e balanceamento de carga**: Antes da instalação, reveja as recomendações para alta disponibilidade (ativo/ativo) e balanceamento de carga conforme descritas no artigo [Alta Disponibilidade e Balanceamento de Cargas de Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing).

-   **Instalação em servidor**: Para ambientes de produção, nós recomendamos que você instale o Private Agent num servidor. A instalação de um agente numa máquina *desktop* é recomendada somente para ambientes de desenvolvimento, controle de qualidade e teste.

-   **Instalação limpa**: Não instale o Private Agent num servidor que já esteja executando outro banco de dados. O agente instala e executa seu próprio banco de dados PostgreSQL. Executar o agente num servidor que já esteja executando um banco de dados Oracle ou SQL Server pode causar problemas de performance.

-   **Mesmo fuso horário**: Nós recomendamos que todos os agentes em um Private Agent Group tenham o mesmo fuso horário. Como o fuso horário de agendas configuradas depende do fuso horário do Private Agent, as execuções agendas podem se tornar imprevisíveis se os fusos horários forem diferentes.

-   **Desinstalando**: Antes de desinstalar, nós recomendamos que você copie os arquivos de configuração e certificados de segurança da sua instalação atual para o caso de você querer reinstalar com a mesma configuração numa data futura.

### Requisitos de Sistema Operacional

A versão Linux do Jitterbit Harmony Private Agent exige um sistema operacional de 64 bits. Ela é suportada para as seguintes distribuições derivadas do Debian Linux e do Red Hat Enterprise Linux para *hardware* da Intel:

-   Debian 8.10 (“jessie”), 9.4 (“stretch”) e 10.6 (“buster”)

-   Ubuntu 14.04 LTS, 16.04 LTS, 18.04 LTS e 20.04 LTS

-   Red Hat Enterprise Linux (CentOS) 6, 7 e 8

-   [Amazon Linux AMI](https://aws.amazon.com/amazon-linux-ami/) e [Amazon Linux AMI 2](https://aws.amazon.com/amazon-linux-2/)

O Harmony Private Agent não foi certificado para outras distribuições similares derivadas das distribuições Debian e Red Hat. A [<u>Amazon Linux</u>](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/amazon-linux-ami-basics.html) oferece várias versões Linux, das quais apenas a [<u>Amazon Linux AMI</u>](https://aws.amazon.com/amazon-linux-ami/) e a [<u>Amazon Linux AMI 2</u>](https://aws.amazon.com/amazon-linux-2/) foram certificadas.

### Pré-requisitos de *Software*

#### Comandos Exigidos

O pacote `jitterbit-agent` pode ser instalado em muitas versões das distribuições Linux; ele tem poucas dependências de pacotes explícitas. No entando, os seguintes comandos devem estar disponíveis:

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;"><b>Comandos Exigido</b></div><div class="codeContent panelContent pdl">
<div><div id="highlighter_135958" class="syntaxhighlighter sh-confluence nogutter  java"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Hint: double-click to select code"><div class="line number1 index0 alt2"><code class="java plain">python</code></div><div class="line number2 index1 alt1"><code class="java plain">sed</code></div><div class="line number3 index2 alt2"><code class="java plain">sudo</code></div><div class="line number4 index3 alt1"><code class="java plain">tar</code></div><div class="line number5 index4 alt2"><code class="java plain">unixodbc</code></div><div class="line number6 index5 alt1"><code class="java plain">unzip</code></div></div></td></tr></tbody></table></div></div>
</div></div>

Você pode testar a disponibilidade de um comando executando o comando `which`.

#### Bibliotecas Exigidas

Embora os Jitterbit Harmony Private Agentes não sejam construídos nativamente para executar em modo 64 bits em distribuições 64 bits, a Jitterbit requer que o agente seja executado num sistema operacional de 64 bits com as bibliotecas de 32 bits exigidas instaladas.

Você vai precisar das seguintes bibliotecas de 32 bits (é provável que elas venham junto como parte até mesmo de uma instalação mínima de qualquer distribuição suportada; estes pacotes podem ter nomes diferentes dependendo da distribuição):

<div class="code panel pdl conf-macro output-block" style="border-width: 1px;" data-hasbody="true" data-macro-name="code"><div class="codeHeader panelHeader pdl" style="border-bottom-width: 1px;"><b>Bibliotecas de 32 bits</b></div><div class="codeContent panelContent pdl">
<div><div id="highlighter_994234" class="syntaxhighlighter sh-confluence nogutter  bash"><div class="toolbar"><span><a href="#" class="toolbar_item command_help help">?</a></span></div><table border="0" cellpadding="0" cellspacing="0"><tbody><tr><td class="code"><div class="container" title="Hint: double-click to select code"><div class="line number1 index0 alt2"><code class="bash plain">libc.so.6</code></div><div class="line number2 index1 alt1"><code class="bash plain">libgcc_s.so.1</code></div><div class="line number3 index2 alt2"><code class="bash plain">libm.so.6</code></div><div class="line number4 index3 alt1"><code class="bash plain">librt.so.1</code></div><div class="line number5 index4 alt2"><code class="bash plain">libstdc++.so.6</code></div><div class="line number6 index5 alt1"><code class="bash plain">libuuid.so.1</code></div><div class="line number7 index6 alt2"><code class="bash plain">libz.so.1</code></div></div></td></tr></tbody></table></div></div>
</div></div>

Para instruções detalhadas sobre a instalação das bibliotecas exigidas, veja a página apropriada para a sua distribuição:

-   [Instalando um Linux Private Agent no Debian](https://success.jitterbit.com/display/DOC/Installing+a+Linux+Private+Agent+on+Debian)

-   [Instalando um Linux Private Agent no RPM](https://success.jitterbit.com/display/DOC/Installing+a+Linux+Private+Agent+on+RPM)

#### Versão Exigida do Java

O pacote do Jitterbit Harmony Private Agent inclui uma versão de 64 bits do Java 8 Runtime Environment (Ambiente de Tempo de Execução Java 8, ou JRE, sigla em inglês) e não requer um tempo de execução Java separado. A Jitterbit instala automaticamente o Ambiente de Tempo de Execução Java exigido especificamente para ser usado pela Jitterbit para que ele não entre em conflito com outras instalações Java que podem já estar instaladas. A partir do Harmony 9.8, a versão do Java enviada com o Agent é o [<u>AdoptOpenJDK</u> <u>JRE</u>](https://adoptopenjdk.net/). A licença deste JRE é descrita no [*<u>site</u>* <u>do OpenJDK</u>](https://openjdk.java.net/legal/gplv2+ce.html).

A Jitterbit pode ser configurada para usar um JRE externo. A versão mínima é a 1.8 (Java 8). Para mudar o tempo de execução Java usado pelo Jitterbit Harmony Private Agent, edite o arquivo `/etc/sysconfig/jitterbit` para usar a versão apropriada do tempo de execução Java e reiniciar todos os serviços Jitterbit.

#### Requisito da Extensão Unlimited Strength Java Cryptography

Para que o agente se comunique de forma segura com recursos tais como servidores, o Ambiente de Tempo de Execução Java (JRE, sigla em inglês) usado pelo agente precisa estar usando a Extensão de Criptografia Java (JCE, sigla em inglês), com os arquivos Unlimited Strength Jurisdiction Policy. Se você estiver usando o JRE que é mandado junto com o agente, ele está usando a JCE com os arquivos Unlimited Strength Jurisdiction Policy.

Se você usar um JRE diferente no lugar do que foi enviado junto com o agente, você terá que substituir os arquivos de política inclusos com o JRE pelos arquivos Unlimited Strength Jurisdiction Policy, caso ele já não os esteja usando. Para instalar os arquivos:

1.  Vá até o [<u>site do Oracle</u>](https://www.oracle.com/technetwork/java/javase/downloads/jce-7-download-432124.html) para baixar o arquivo ZIP contendo os arquivos Unlimited Strength Jurisdiction Policy da Java Cryptography Extension (JCE).

2.  Abra o arquivo ZIP para extrair os arquivos `local_policy.jar` e `US_export_policy.jar`.

3.  Copie e substitua os arquivos JAR existentes encontrados em `<JITTERBIT_HOME>\jre\lib\security`, substituindo `<JITTERBIT_HOME>` com o caminho até o diretório raiz do seu Private Agent.

4.  Reinicie o Jitterbit Private Agent.

### Requisitos de PostgreSQL

O PostgreSQL é instalado como parte da instalação do Harmony Private Agent. Esta instância do PostgreSQL é para uso somente com e pela Jitterbit.

-   ***Não instale*** o PostgreSQL separadamente antes de instalar a Jitterbit. A instalação da Jitterbit instala automaticamente a versão 9.6.11 de 64 *bits* do PostgreSQL com o *driver* PostgreSQL 9.3 ODBC. (*Upgrades* feitos aos Private Agents não atualizam uma versão já existente do PostgreSQL para esta versão; ela é deixada como está).

-   ***Não use*** um sinal de mais (`+`) como parte da senha do PostgreSQL ao instalar um Harmony Private Agent. O número máximo de caracteres para uma senha PostgreSQL é oito (8). Recomendamos que você não utilize caracteres com acentos (como “`é`”) nem nenhum dos caracteres a seguir na sua senha PostgreSQL: `+ @ $ % & [] {} () , ; ? ^ = £`

-   ***Não tenha*** nenhum outro banco de dados configurado ou executando na instância do Jitterbit PostgreSQL.

-   ***Não use*** o servidor ou o banco de dados Jitterbit PostgreSQL como parte de quaisquer operações ou *transformations* da Jitterbit.

-   ***Não use*** compressão do Windows na pasta da Jitterbit, na pasta PostgreSQL ou na pasta temporária na máquina onde o Jitterbit Private Agent estiver instalado e executando. Usar a compressão do Windows vai reduzir drasticamente a velocidade do processamento das operações e *transformations* da Jitterbit.

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


## Próximos Passos

Para mais instruções sobre como baixar, instalar, configurar, reiniciar, atualizar, recolher e desinstalar um Linux Private Agent, veja a página apropriada para a sua distribuição:

-   [Instalando um Linux Private Agent no Debian](https://success.jitterbit.com/display/DOC/Installing+a+Linux+Private+Agent+on+Debian)

-   [Instalando um Linux Private Agent no RPM](https://success.jitterbit.com/display/DOC/Installing+a+Linux+Private+Agent+on+RPM)

-   [Configurando um Linux Private Agent](https://success.jitterbit.com/display/DOC/Configuring+a+Linux+Private+Agent)

-   [Reiniciando um Linux Private Agent](https://success.jitterbit.com/display/DOC/Restarting+a+Linux+Private+Agent)

-   [Atualizando ou Desinstalando um Linux Private Agent](https://success.jitterbit.com/display/DOC/Upgrading+or+Uninstalling+a+Linux+Private+Agent)
