[//]: # (System Requirements)

## Introduction

Jitterbit Harmony is Jitterbit's modern, multi-tenant, born-in-the-cloud
integration and API platform. This page provides system requirements and
installation instructions for Jitterbit Harmony products.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE:** For system requirements for other Jitterbit products not
included with Harmony, see [Data Loader](https://success.jitterbit.com/display/DOC/Data+Loader) and
[Legacy Version 5.x](https://success.jitterbit.com/display/DOC/Legacy+Version+5.x).

</div>

</div>


## Jitterbit Harmony Portal

The [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal) is
accessible
at <a href="https://login.jitterbit.com/" class="external-link"
rel="nofollow">https://login.jitterbit.com</a> and does not require any
additional hardware or software installation. The Harmony Portal
provides web-based access to these Jitterbit Harmony products:

-   **[Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio):** Design, test, and
    deploy integration projects.
-   **[API Manager](https://success.jitterbit.com/display/DOC/API+Manager):** Create, publish, and
    manage developer-friendly APIs.
-   **[Marketplace](https://success.jitterbit.com/display/DOC/Marketplace):** Use integration recipes
    and process templates to quickly create new projects.
-   **[Management Console](https://success.jitterbit.com/display/DOC/Management+Console): **Manage
    and monitor your integration projects.
-   **[Citizen Integrator](https://success.jitterbit.com/display/DOC/Citizen+Integrator): **Configure
    and manage pre-built Citizen Integrator recipes to quickly connect
    apps.

These major browsers are supported:

-   Chrome
-   Firefox
-   Safari (macOS only)

In order to communicate with the Harmony cloud and run the Harmony
Portal, JavaScript needs to be enabled and outbound port 443 (HTTPS)
needs to be open. This port is normally allowed by corporate server
firewalls.


## <span id="SystemRequirements-design-studio" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Jitterbit Harmony Design Studio

[Jitterbit Harmony Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio) is
Jitterbit Harmony's desktop project design application where you can
design, test, and deploy your integration projects. The system
requirements and installation instructions provided below apply to
Design Studio versions 7.x – 10.x. See also [System Requirements for
Design Studio](https://success.jitterbit.com/display/DOC/System+Requirements+for+Design+Studio).

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE:** Another option for project design is to use [Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio), our next-generation project designer
featuring a modern and collaborative user experience with a cloud-based
UI.

</div>

</div>

<span class="conf-macro output-inline" hasbody="false"
macro-name="multiexcerpt-include"></span>

### Windows

The Windows version of Design Studio is supported for these Windows OS
versions:

-   Windows 8, 8.1
-   Windows 10
-   Windows 11
-   Windows Server 2012 R2
-   Windows Server 2016
-   Windows Server 2019
-   Windows Server 2022

See [Installing Jitterbit Design Studio on
Windows](https://success.jitterbit.com/display/DOC/Installing+Jitterbit+Design+Studio+on+Windows).

### macOS

<span style="color: rgb(23,43,77);">The macOS (Apple's Mac operating
system) version of Jitterbit Design Studio is supported on these macOS
versions:  </span>

-   <span style="color: rgb(23,43,77);">10.13.6 through 10.14
    (Mojave)</span>
-   <span style="color: rgb(23,43,77);">11 (Big Sur)</span>
-   <span style="color: rgb(23,43,77);">12 (Monterey)</span>

<span style="color: rgb(23,43,77);">Design Studio is currently not
certified on macOS 10.15 (Catalina).</span>

See [Installing Jitterbit Design Studio on
macOS](https://success.jitterbit.com/display/DOC/Installing+Jitterbit+Design+Studio+on+macOS).

## Jitterbit Harmony Private Agents

[Jitterbit Harmony Private Agents](https://success.jitterbit.com/display/DOC/Private+Agents) use an
on-premises server or private cloud to enable connectivity to your data.
Private Agents allow you to choose where your integration runs and
control which network your data travels and resides in. These system
requirements and installation instructions apply to Jitterbit Private
Agents through versions 10.x. See also [System Requirements for Private
Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents).

<span class="conf-macro output-inline" hasbody="false"
macro-name="multiexcerpt-include"></span>

### Linux

<span class="conf-macro output-inline" hasbody="false"
macro-name="multiexcerpt-include"></span>

The Linux version of the Jitterbit Harmony Private Agent requires a
64-bit OS. It is supported for these distributions derived from Debian
Linux and Red Hat Enterprise Linux for Intel hardware:

-   Debian 8.10 ("jessie"), 9.4 ("stretch"), and 10.6 ("buster")

-   Ubuntu 14.04 LTS, 16.04 LTS, 18.04 LTS, and 20.04 LTS

-   Red Hat Enterprise Linux (CentOS) 6, 7, and 8

-   <a href="https://aws.amazon.com/amazon-linux-ami/" class="external-link"
    rel="nofollow">Amazon Linux AMI</a>  and
    <a href="https://aws.amazon.com/amazon-linux-2/" class="external-link"
    rel="nofollow">Amazon Linux AMI 2</a>

The Harmony Private Agent has not been certified against other similar
distributions with Debian or RPM package distributions derived from the
Debian and Red Hat distributions. <a
href="https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/amazon-linux-ami-basics.html"
class="external-link" rel="nofollow">Amazon Linux</a> provides multiple
Linux versions, of which only
<a href="https://aws.amazon.com/amazon-linux-ami/" class="external-link"
rel="nofollow">Amazon Linux AMI</a> and
<a href="https://aws.amazon.com/amazon-linux-2/" class="external-link"
rel="nofollow">Amazon Linux AMI 2</a> have been certified.

### Windows

<span class="conf-macro output-inline" hasbody="false"
macro-name="multiexcerpt-include"></span>

The Windows version of the Jitterbit Harmony Private Agent requires a
64-bit OS and is supported for these versions:

-   Windows 8 and 8.1
-   Windows 10
-   Windows 11
-   Windows Server 2012 and 2012 R2
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

**NOTE:**<span style="color: rgb(51,51,51);">** **Jitterbit does not
test against or support software versions no longer supported by
Microsoft.</span>

</div>

</div>

### Installation Instructions

Prior to installing Private Agent(s), see [Agent Groups High
Availability and Load
Balancing](https://success.jitterbit.com/display/DOC/Agent+Groups+High+Availability+and+Load+Balancing) for
recommendations that allow for high availability (active/active) and
load balancing.

#### Windows

Installation on a Windows system is covered in [Installing a Jitterbit
Harmony Windows
Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Windows+Agent).

#### Linux

Installation on a Linux system is covered in [Installing a Jitterbit
Harmony Linux
Agent](https://success.jitterbit.com/display/DOC/Installing+a+Jitterbit+Harmony+Linux+Agent).
