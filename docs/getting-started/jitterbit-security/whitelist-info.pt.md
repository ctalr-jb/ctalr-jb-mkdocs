[//]: # (Informações Sobre *Whitelists*)
[//]: # (This is a translation of Version 39, published on August 31, 2021.)

## Introdução

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTA:** As informações sobre *whitelists* são aplicáveis aos
[Agents](https://success.jitterbit.com/display/DOC/Agent?showLanguage=pt_BR) e ao [Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio?showLanguage=pt_BR). Estas informações não são
aplicáveis às aplicações Harmony baseadas na nuvem que são acessadas por
meio do [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal?showLanguage=pt_BR).

</div>

</div>

Em muitas situações, nenhuma configuração de *firewall* ou de rede é
necessária para que os Private Agents ou o Design Studio consigam se
comunicar com o Jitterbit Harmony. No entanto, se a sua rede estiver
atrás de um *firewall* que bloqueia o acesso a todo tipo de tráfego
exceto para domínios, URLs ou endereços IP específicos, você precisa
configurar a rede para conseguir se comunicar com o Jitterbit Harmony.
Há dois cenários principais para considerar:

-   Você deseja usar os Jitterbit Harmony Cloud Agents para acessar
    recursos internos que estão atrás de um *firewall*

-   Você deseja instalar um Jitterbit Harmony Private Agent ou o Design
    Studio dentro da sua rede e permitir que o agente ou o Design
    Studio se comuniquem apenas com os serviços estritamente
    necessários

Por favor, revise as informações abaixo para determinar quais endereços
IP e URLs Jitterbit precisam estar na *whitelist* (lista de permissões)
para o cenário específico dentro da sua organização.


## Determine a Sua Região

Os endereços IP ou URLs específicos que precisam ser postos na
*whitelist* são determinados pela região do Jitterbit Harmony que
hospeda a sua organização.

A Jitterbit usa servidores em regiões separadas para a NA (América do
Norte), EMEA (Europa, Oriente Médio e África/Ásia/Austrália) e APAC
(Ásia-Pacífico). A região é atada a uma [organização](https://success.jitterbit.com/display/DOC/Organizations?showLanguage=pt_BR) Harmony em
vez de a um usuário específico. Um usuário pode ser parte de várias
organizações, desde que as organizações estejam todas na mesma região.

Para encontrar a região atada a uma organização específica, faça *login*
no <a href="https://login.jitterbit.com/" class="external-link"
rel="nofollow">Harmony Portal</a>. Depois de fazer isso, você verá que a URL
mudou para incluir a região associada à organização que você está
acessando, e que ela começa com "`apps.na`", "`apps.emea`" ou "`apps.apac`".

-   **NA**: Se a URL começar com "`apps.`**`na`**", então a sua organização
    está localizada na América do Norte (NA).

-   **EMEA**: Se a URL começar com "`apps.`**`emea`**", então a sua
    organização está localizada na região EMEA (Europa, Oriente Médio
    ou África/Ásia/Austrália).

-   **APAC**: Se a URL começar com "`apps.`**`apac`**", então a sua
    organização está localizada na região APAC (Ásia-Pacífico).

Se você tem acesso a várias organizações, você pode alternar entre elas
usando o menu *dropdown* de organizações na barra de menus. A URL
mostrada na barra de endereços vai refletir a região associada com a
organização atual que você está acessando.


## Permitir que os Jitterbit Harmony Cloud Agents Acessem Recursos Internos

Se você usa os Jitterbit Harmony Cloud Agents e precisa poder se
conectar com *endpoints* dentro da sua rede (tais como um banco de dados
local (*on-premises*) ou um banco de dados SQL no Azure), você precisa
colocar estes endereços IP na *whitelist* para a sua região dentro do
seu *firewall*. Nós vamos mandar um aviso se mudarmos estes endereços IP
específicos:

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="odd">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Região NA</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Região EMEA</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Região APAC</strong></p></td>
</tr>
<tr>
<td class="confluenceTd"><code>35.166.153.63</code><br />
<td class="confluenceTd"><code>18.185.13.223</code><br />
<td class="confluenceTd"><code>3.0.141.187</code><br />
</tr>
<tr>
<td class="confluenceTd"><code>52.36.120.247</code><br />
<td class="confluenceTd"><code>35.157.28.131</code><br />
<td class="confluenceTd"><code>13.54.178.57</code><br />
</tr>
<tr>
<td class="confluenceTd"><code>52.45.79.49</code><br />
<td class="confluenceTd"><code>52.17.134.164</code><br />
<td class="confluenceTd"><code>13.55.214.95</code><br />
</tr>
<tr>
<td class="confluenceTd"><code>54.69.5.5</code><br />
<td class="confluenceTd"><code>54.93.40.43</code><br />
<td class="confluenceTd"><code>13.237.242.120</code><br />
</tr>
<tr>
<td class="confluenceTd"><code>54.208.19.13</code><br />
<td class="confluenceTd"><code>54.229.49.142</code><br />
<td class="confluenceTd"><code>13.251.231.2</code><br />
</tr>
<tr>
<td class="confluenceTd"><code>54.208.19.24</code><br />
<td class="confluenceTd"><code>54.229.49.156</code><br />
<td class="confluenceTd"><code>52.220.155.2</code><br />
</tr>
</tbody>
</table>

</div>


## <span id="WhitelistInformation-static-ips" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Permitir que os Jitterbit Harmony Private Agents ou o Design Studio se Comuniquem com Serviços

Para restringir as comunicações que saem de uma instalação de Private
Agent ou do Design Studio que está dentro da sua rede, há várias URLs
com as quais a instalação de agente ou do Design Studio deve poder se
comunicar. Por favor, coloque estas URLs/IPs na *whitelist* na sua
região caso você restrinja o tráfego que sai da porta 443 no seu
*firewall*. Nós vamos mandar um aviso se mudarmos os endereços IP
específicos listados abaixo.

### Região NA

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="odd">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Região NA</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Endereços IP Estáticos</strong></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><span class="nolink"><span
class="nolink">https://apps.na-east.jitterbit.com</span></span></td>
<td class="confluenceTd"><code>76.223.1.89</code><br />
<code>13.248.156.39</code></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p><span
class="nolink">https://na-east.jitterbit.com<br />
<span class="nolink">https://login.jitterbit.com</span><br />
</span></p></td>
<td class="confluenceTd"><p><code>13.248.138.21</code><br />
<code>76.223.11.73</code></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p><span
class="nolink">https://as-p-e.jitterbit.com</span></p></td>
<td
class="confluenceTd"><p><code>75.2.90.2</code><code>99.83.173.76</code></p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p><span
class="nolink">https://citizen.jitterbit.net</span></p></td>
<td class="confluenceTd"><p><code>13.248.138.20</code><br />
<code>76.223.12.78</code></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p><span
class="nolink">https://services.jitterbit.net</span></p></td>
<td
class="confluenceTd"><p><code>13.248.156.5976.223.17.99</code></p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p><span
class="nolink">https://jitterbitsysservice.jitterbit.net</span></p></td>
<td class="confluenceTd"><p><code>13.248.156.59</code><br />
<code>76.223.17.99</code></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p>*.jitterbit.net <em>(or your specific API
URL)</em></p></td>
<td class="confluenceTd"><p><code>13.248.156.59</code><br />
<code>76.223.17.99</code></p></td>
</tr>
</tbody>
</table>

</div>

### Região EMEA

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="odd">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Região EMEA</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Endereços IP Estáticos</strong></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><span
class="nolink">https://apps.emea-west.jitterbit.com</span></td>
<td class="confluenceTd"><code>13.248.156.26</code><br />
<code>76.223.21.99</code></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p><span
class="nolink">https://emea-west.jitterbit.com<br />
<span class="nolink">https://login.jitterbit.com</span><br />
</span></p></td>
<td class="confluenceTd"><p><code>13.248.147.55</code><br />
<code>76.223.24.75</code></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p><span
class="nolink">https://as-p-emea.jitterbit.com</span></p></td>
<td class="confluenceTd"><p><code>75.2.73.5299.83.137.93</code></p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p><span class="nolink"><span
class="nolink">https://citizen.jitterbit.eu</span></span></p></td>
<td class="confluenceTd"><p><code>13.248.155.43</code><br />
<code>76.223.31.67</code></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p><span
class="nolink">https://services.jitterbit.eu</span></p></td>
<td class="confluenceTd"><p><code>13.248.131.7</code><br />
<code>76.223.7.87</code></p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p><span
class="nolink">https://jitterbitsysservice.jitterbit.eu</span></p></td>
<td class="confluenceTd"><p><code>13.248.131.7</code><br />
<code>76.223.7.87</code></p></td>
</tr>
<tr class="even">
<td class="confluenceTd">*.jitterbit.eu <em>(or your specific API
URL)</em></td>
<td class="confluenceTd"><p><code>13.248.131.7</code><br />
<code>76.223.7.87</code></p></td>
</tr>
</tbody>
</table>

</div>

### Região APAC

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="odd">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Região APAC</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Endereços IP Estáticos</strong></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><span class="nolink"><span
class="nolink">https://apps.apac-southeast.jitterbit.com</span></span></td>
<td class="confluenceTd"><code>13.248.152.476.223.21.122</code></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p><span class="nolink"><span
class="nolink">https://apac-southeast.jitterbit.com<br />
<span class="nolink">https://login.jitterbit.com</span><br />
</span></span></p></td>
<td class="confluenceTd"><p><code>13.248.158.29</code><br />
<code>76.223.24.122</code></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p><span class="nolink"><span
class="nolink">https://as-p-apac.jitterbit.com</span></span></p></td>
<td
class="confluenceTd"><p><code>75.2.111.5499.83.176.87</code></p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p><span class="nolink"><span
class="nolink">https://citizen.jitterbit.cc</span></span></p></td>
<td
class="confluenceTd"><p><code>13.248.149.3376.223.29.111</code></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><p><span class="nolink"><span
class="nolink">https://services.jitterbit.cc</span></span></p></td>
<td
class="confluenceTd"><p><code>13.248.139.1876.223.11.118</code></p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><p><span class="nolink"><span
class="nolink">https://jitterbitsysservice.jitterbit.cc</span></span></p></td>
<td
class="confluenceTd"><p><code>13.248.139.1876.223.11.118</code></p></td>
</tr>
<tr class="even">
<td class="confluenceTd">*.jitterbit.cc <em>(or your specific API
URL)</em></td>
<td class="confluenceTd"><code>13.248.139.1876.223.11.118</code></td>
</tr>
</tbody>
</table>

</div>
