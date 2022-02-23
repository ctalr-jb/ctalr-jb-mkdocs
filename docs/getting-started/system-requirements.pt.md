[//]: # (Requisitos de Sistema)
[//]: # (This is a translation of Version 53, published on July 16, 2021.)

## Introdução

O Jitterbit Harmony é a plataforma de integração de APIs moderna,
*multi-tenant* e nascida na nuvem da Jitterbit. Esta página diz quais
são os requisitos de sistema e instruções de instalação para os produtos
Jitterbit Harmony.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Para ver os requisitos de sistema de outros produtos
Jitterbit não incluídos com o Harmony, veja [Data Loader](https://success.jitterbit.com/display/DOC/Data+Loader?showLanguage=pt_BR) e
[Legacy Version 5.x](https://success.jitterbit.com/display/DOC/Legacy+Version+5.x?showLanguage=pt_BR).

</div>

</div>


## Jitterbit Harmony Portal

O [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR) é acessível em
[https://login.jitterbit.com](https://login.jitterbit.com/) e não requer
a instalação de nenhum *software* ou *hardware* adicional. O Harmony
Portal oferece acesso baseado na Web aos seguintes produtos Jitterbit
Harmony:

-   **[Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR)**: Faça o *design*, os testes e a implantação
    dos seus projetos de integração.

-   **[API Manager](https://success.jitterbit.com/display/DOC/API+Manager?showLanguage=pt_BR)**: Crie, publique e gerencie APIs feitas para
    desenvolvedores.

-   **[Marketplace](https://success.jitterbit.com/display/DOC/Marketplace?showLanguage=pt_BR)**: Use protótipos de integração e *templates*
    de processo para criar novos projetos rapidamente.

-   **[Management Console](https://success.jitterbit.com/display/DOC/Management+Console?showLanguage=pt_BR)**: Administre e monitore os seus
    projetos de integração.

-   **[Citizen Integrator](https://success.jitterbit.com/display/DOC/Citizen+Integrator?showLanguage=pt_BR)**: Configure e gerencie protótipos
    pré-construídos do Citizen Integrator para conectar aplicações
    rapidamente.

Três navegadores comuns são suportados:

-   Chrome
-   Firefox
-   Safari (somente macOS)

Para que possa haver comunicação com a nuvem do Harmony e executar o
Harmony Portal, o JavaScript precisa estar habilitado e a porta de saída
443 (HTTPS) precisa estar aberta. Esta porta é normalmente permitida por
*firewalls* de servidores corporativos.


## <span id="SystemRequirements-design-studio" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Jitterbit Harmony Design Studio

O [Jitterbit Harmony Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR) é a aplicação de *design* de
projetos para *desktop* do Jitterbit Harmony onde você pode fazer o
*design*, testar e implantar os seus projetos de integração. Os
requisitos de sistema e as instruções de instalação dados abaixo
aplicam-se ao Design Studio versões de 7.x a 10.x. Veja também
[Requisitos de Sistema para o Design Studio](https://success.jitterbit.com/display/DOC/System+Requirements+for+Design+Studio?showLanguage=pt_BR).

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** Uma outra opção para o *design* de projetos é usar o [Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio?showLanguage=pt_BR), nossa próxima geração de *designer* de projetos com uma
experiência de usuário moderna e colaborativa baseado na nuvem.

</div>

</div>

### Windows

A versão para Windows do Design Studio é suportada para as seguintes
versões do sistema operacional Windows:

-   Windows 8, 8.1
-   Windows 10
-   Windows 11
-   Windows Server 2012 R2
-   Windows Server 2016
-   Windows Server 2019
-   Windows Server 2022

Veja [Como Instalar o Jitterbit Design Studio no Windows](https://success.jitterbit.com/display/DOC/Installing+Jitterbit+Design+Studio+on+Windows?showLanguage=pt_BR).

### macOS

A versão para macOS (o sistema operacional do Apple Mac) do Jitterbit
Design Studio é suportada nas seguintes versões do macOS:

-   10.13.6 até 10.14 (Mojave)
-   11 (Big Sur)
-   12 (Monterey)

O Design Studio atualmente não é certificado no macOS 10.15 (Catalina).

Veja [Como Instalar o Jitterbit Design Studio no macOS](https://success.jitterbit.com/display/DOC/Installing+Jitterbit+Design+Studio+on+macOS?showLanguage=pt_BR).


## Jitterbit Harmony Private Agents

Os [Jitterbit Harmony Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents?showLanguage=pt_BR) usam um servidor local
(*on-premises*) ou uma nuvem privada para habilitar a conectividade aos
seus dados. Os Private Agents permitem que você escolha onde a sua
integração executa e controle em qual rede seus dados transitam e
residem. Estes requisitos de sistema e instruções de instalação
aplicam-se aos Jitterbit Private Agents até as versões 10.x. Veja também
[Requisitos de Sistema para Private Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents?showLanguage=pt_BR).

### Linux

A versão para Linux do Jitterbit Harmony Private Agent requer um sistema
operacional de 64 bits. Ela é suportada para as seguintes distribuições
derivadas do Debian Linux e Red Hat Enterprise Linux para equipamentos
Intel:

-   Debian 8.10 (“jessie”), 9.4 (“stretch”) e 10.6 (“buster”)
-   Ubuntu 14.04 LTS, 16.04 LTS, 18.04 LTS e 20.04 LTS
-   Red Hat Enterprise Linux (CentOS) 6, 7 e 8
-   <a href="https://aws.amazon.com/amazon-linux-ami/" class="external-link"
    rel="nofollow">Amazon Linux AMI</a> e <a href="https://aws.amazon.com/amazon-linux-2/" class="external-link"
    rel="nofollow">Amazon Linux AMI 2</a>

O Harmony Private Agent não foi certificado para outras distribuições
similares com distribuições de pacotes Debian ou RPM derivadas das
distribuições Debian e Red Hat. O <a
href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/amazon-linux-ami-basics.html"
class="external-link" rel="nofollow">Amazon Linux</a> oferece várias
versões do Linux, das quais apenas a <a href="https://aws.amazon.com/amazon-linux-ami/" class="external-link"
rel="nofollow">Amazon Linux AMI</a> e a
<a href="https://aws.amazon.com/amazon-linux-2/" class="external-link"
rel="nofollow">Amazon Linux AMI 2</a> foram certificadas.

### Windows

A versão para Windows do Jitterbit Harmony Private Agent requer um
sistema operacional de 64 bits e é suportada para as seguintes versões:

-   Windows 8 e 8.1
-   Windows 10
-   Windows 11
-   Windows Server 2012 e 2012 R2
-   Windows Server 2016
-   Windows Server 2019
-   Windows Server 2022

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** A Jitterbit não testa nem suporta versões de *software* que
não são mais suportadas pela Microsoft.

</div>

</div>

### Instruções de Instalação

Antes de instalar Private Agent(s), consulte a página [Alta
Disponibilidade e Balanceamento de Cargas de Agent Groups](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing?showLanguage=pt_BR) para ver
recomendações sobre a alta disponibilidade (ativa/ativa) e balanceamento
de cargas.

#### Windows

A instalação num sistema Windows é descrita em [Instalando um
Jitterbit Harmony Agent no Windows](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent?showLanguage=pt_BR).

#### Linux

A instalação num sistema Linux é descrita em [Instalando um Jitterbit
Harmony Agent no Linux](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Linux+Agent?showLanguage=pt_BR).
