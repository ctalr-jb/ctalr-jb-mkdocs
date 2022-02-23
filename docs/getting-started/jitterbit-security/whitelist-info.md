[//]: # (Whitelist Information)

## Introduction

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE:** Whitelist information is applicable for
[Agents]( https://success.jitterbit.com/display/DOC/Agent) and<span
style="color: rgb(40,40,40);"> [Design
Studio]( https://success.jitterbit.com/display/DOC/Design+Studio). This information is not applicable
for cloud-based Harmony applications accessed through the [Jitterbit
Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal).</span>

</div>

</div>

<span style="color: rgb(40,40,40);">In many situations, no network or
firewall configurations are necessary for Private Agents<span
style="color: rgb(40,40,40);"> or Design Studio</span> to be able to
communicate with Jitterbit Harmony. </span>However, if your network is
behind a firewall that blocks access to all traffic except for specified
domains, URLs, or IP addresses,<span style="color: rgb(40,40,40);"> you
need to configure the network to </span>be able to communicate with
Jitterbit Harmony. There are two main scenarios to consider:

-   You wish to use the Jitterbit Harmony Cloud Agents to access
    internal resources that are behind a firewall
-   You wish to install a Jitterbit Harmony Private Agent or Design
    Studio within your network and allow the agent or Design Studio to
    communicate only with services that are absolutely necessary

Please review the information provided below to determine which
Jitterbit IP addresses and URLs need to be whitelisted for the specific
scenario within your organization.


## Determine Your Region

The specific IP addresses or URLs that require whitelisting are
determined by the Jitterbit Harmony region that hosts your organization.

<span class="conf-macro output-inline" hasbody="false"
macro-name="multiexcerpt-include">Jitterbit uses servers in separate
regions for NA (North America), EMEA (Europe, the Middle East, and
Africa/Asia/Australia), and APAC (Asia-Pacific). The region is tied to a
Harmony [organization](https://success.jitterbit.com/display/DOC/Organizations) rather than a
specific user. A user can be part of multiple organizations, as long as
the organizations are all in the same region.</span>

<span class="conf-macro output-inline" hasbody="false"
macro-name="multiexcerpt-include"></span>

To find the region tied to a specific organization, log in to
the <a href="https://login.jitterbit.com/" class="external-link"
rel="nofollow">Harmony Portal</a>. After you log in, you will find the
web address URL has changed to include the region associated with the
organization you are accessing, and begins with either "`apps.``na`",
"`apps.emea`", or "`apps.apac`".

-   **NA:** If the URL begins with "`apps.`**`na`**", then your
    organization is located in North America (NA).
-   **EMEA:** If the URL begins with "`apps.emea`", then your
    organization is located in EMEA (Europe, the Middle East, and
    Africa/Asia/Australia).
-   **APAC:** If the URL begins with "`apps.apac`", then your
    organization is located in APAC (Asia-Pacific).

If you have access to multiple organizations, you can switch between
them using the organization dropdown in the menu bar. The URL shown in
the address bar will reflect the region associated with the current
organization you are accessing.


## Allow Jitterbit Harmony Cloud Agents to Access Internal Resources

If you use the Jitterbit Harmony Cloud Agents and need to be able to
connect to endpoints within your network (such as an on-premises
database or a SQL database at Azure), you must whitelist these IP
addresses for your region within your firewall. We will send out a
notice if we change these specific IP addresses:

<div class="table-wrap">

|  **NA Region**  |  **EMEA Region**  |  **APAC Region**  |
| --------------- | ----------------- | ----------------- |
| `35.166.153.63` | `18.185.13.223`   | `3.0.141.187`     |
| `52.36.120.247` | `35.157.28.131`   | `13.54.178.57`    |
| `52.45.79.49`   | `52.17.134.164`   | `13.55.214.95`    |
| `54.69.5.5`     | `54.93.40.43`     | `13.237.242.120`  |
| `54.208.19.13`  | `54.229.49.142`   | `13.251.231.2`    |
| `54.208.19.24`  | `54.229.49.156`   | `52.220.155.2`    |

</div>


## <span id="WhitelistInformation-static-ips" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Allow Jitterbit Harmony Private Agent or Design Studio to Communicate with Services

To restrict the outgoing communication from a Private Agent or Design
Studio installation that is within your network, there are several URLs
with which the agent or Design Studio installation must be able to
communicate. Please whitelist these URLs/IPs for your region if you
restrict outbound traffic on port 443 on your firewall. We will send out
a notice if we change the specific IP addresses listed below.

### NA Region

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="odd">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>NA Region</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Static IP
Addresses</strong></p></td>
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

### EMEA Region

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="odd">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>EMEA Region</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Static IP
Addresses</strong></p></td>
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

### APAC Region

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="odd">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>APAC Region</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Static IP
Addresses</strong></p></td>
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
