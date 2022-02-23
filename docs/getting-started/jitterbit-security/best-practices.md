[//]: # (Security Best Practices for Administrators, Project Builders, and Integration Specialists)

## Introduction

This document is for administrators, project builders, and integration
specialists who <span class="inline-comment-marker"
ref="ff05d6e9-a4fc-4ba0-8a97-85995bee6b8d">integrate Jitterbit with
other products, such as Salesforce, NetSuite, and other
endpoints</span>. When working with your projects, build with security
foremost.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE: **[Integration Project
Methodology](https://success.jitterbit.com/display/DOC/Integration+Project+Methodology) contains
useful information for an integration project PM. 

</div>

</div>

Before deploying projects, you should have completed a recent audit of
your company’s security infrastructure and procedures. A security audit
is a structured, validated evaluation of your company’s information
<span class="inline-comment-marker"
ref="05e95ff4-400d-48c4-bfb2-99a5117039d8">system</span> security. The
security audit measures how your company‘s security conforms to a set of
established, <span class="inline-comment-marker"
ref="293edd22-a054-48a3-a43e-5a694fc7c4bf">industry-standard criteria,
which include</span> policies, procedures and requirements. 

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

Security audit and compliance information:

-   <a href="https://www.praxiom.com/iso-19011.htm" class="external-link"
    rel="nofollow">ISO 19011 Auditing Definitions Translated into Plain
    English</a>

-   <a
    href="https://www.hhs.gov/hipaa/for-professionals/security/guidance/cybersecurity/index.html"
    class="external-link" rel="nofollow">Cyber Security Guidance from
    HHS.gov</a>

-   <a
    href="https://www.aicpa.org/interestareas/frc/assuranceadvisoryservices/aicpacybersecurityinitiative.html"
    class="external-link" rel="nofollow">SOC for Cybersecurity from
    AICPA.org</a>

This is not a complete list. Other resources may be available through
your organization's security and compliance specialist.

</div>

</div>

If you operate under any regulatory requirements, such as US FAA or FDA,
ensure your security setup is in compliance with these requirements. 

### <span id="SecurityBestPracticesforAdministrators,ProjectBuilders,andIntegrationSpecialists-SecurityDataProtectionRegs" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Security and Data Protection Regulations

There are important governmental regulations you may be subject to,
depending on where you operate your business or where your customers
live and work. These regulations deal with data privacy for which you,
along with Jitterbit are responsible. 

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

The following regulations require Jitterbit, its technology partners,
and you to implement and maintain reasonable or appropriate
administrative, physical, and technical safeguards. These laws and
regulations afford specific privacy rights that you must adhere to. In
addition, each has specific reporting timeframes and requirements. 

</div>

</div>

#### United States of America State and Federal regulations:

-   <a href="https://www.hhs.gov/hipaa/for-professionals/index.html"
    class="external-link" rel="nofollow">HIPAA (Health Insurance Portability
    and Accountability Act)</a> and <a
    href="https://www.hhs.gov/hipaa/for-professionals/special-topics/hitech-act-enforcement-interim-final-rule/index.html"
    class="external-link" rel="nofollow">HITECH (Health Insurance Technology
    for Clinical Heath Act)</a> <span
    style="color: rgb(23,23,23);">establishes requirements for the use,
    disclosure, and safeguarding of PHI (Private Health Information).
    These laws apply to covered entities such as health providers as
    well as cloud services and IT providers. </span>
-   <span
    style="color: rgb(23,23,23);"><a href="https://www.oag.ca.gov/privacy/ccpa" class="external-link"
    rel="nofollow">CCPA (California Consumer Privacy Act)</a> enhances
    consumer rights and privacy protections for residents of California.
    It deals with any business that collects consumers personal data
    doing business in California. </span>

#### European Union and European Economic Activity Zone Regulations:

-   <span
    style="color: rgb(23,23,23);"><a href="https://gdpr.eu/" class="external-link" rel="nofollow">GDPR
    (General Data Protection Regulation)</a> gives control to
    individuals in the EU (European Union) and EEA (European Economic
    Area). It requires businesses to ensure that their processes that
    handle personal data must be designed and implemented with
    safeguards to protect data. These businesses must also disclose
    their data collection, use, and retention policies. </span>

## Cloud Agents and Private Agents

<span style="color: rgb(23,43,77);">When you run an integration,
Jitterbit connects your data through the agents you configured. Agents
can be [Cloud Agents](https://success.jitterbit.com/display/DOC/Cloud+Agent+Groups) or [Private
Agents](https://success.jitterbit.com/display/DOC/Private+Agents) and Agents exist in Groups. <span
style="color: rgb(255,102,0);"><span style="color: rgb(0,0,0);">Groups
</span></span>are sets of Agents in the same Environment, which
provide <span style="color: rgb(0,0,0);">high availability. This means
that if one group goes down and is unavailable, another can take its
place and continue with your work. </span><span
class="inline-comment-marker"
ref="59a1a1d8-14a3-4877-b7d2-7fa1508a36e4">Cloud Agent Group</span> is a
set of agents maintained and managed by Jitterbit in the cloud. Private
Agent Groups are maintained and managed by you, using your own <span
class="inline-comment-marker"
ref="2ccb5b7d-d1b7-4b1b-bf60-b38e2026d90a">servers</span> or instances
within your firewall or hosted virtually on private clouds. By running
Private Agents, your <span class="inline-comment-marker"
ref="9f3bb237-e3d3-4b53-af4c-add1b8bc4230">sensitive business
data</span> will remain within your managed networks<span
class="inline-comment-marker"
ref="9302d412-e62f-4922-a7db-16aef07f34b4">.</span></span>

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

**Which Agent Type to Use?**

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

-   Use Cloud Agent Groups when you want to run your integration in the
    cloud and you need the scalability that Cloud Agent Groups offer. 

-   Use Private Agent Groups when you want to – or must – run
    integrations on your premises.

</div>

</div>

### Cloud Agent Groups

Cloud Agents are maintained and managed by Jitterbit. Jitterbit Cloud
Agents are multi-tenant and are locked down. Data that flows through is
transient and only remains on the agent to complete processing. You
<span class="inline-comment-marker"
ref="33242b99-b2ff-4227-a2d4-8330dcc07425">can't</span> control or
configure the Jitterbit Cloud Agent Group or its agents as you can with
your Private Agent Groups. 

When the Jitterbit Cloud Agent Group performs an integration, it
connects directly with the application that requires data integration.
It then reads and posts data to these applications. <span
class="inline-comment-marker"
ref="c65ac1f3-69ea-4583-afc7-27184ea97a35">If you use persistent storage
as part of your project, it will remain on the agent for 24 hours. Data
persisting in the Jitterbit Cloud Agent Group is stored in encrypted
Amazon S3 buckets that are not directly user accessible</span>. Each
integration stores data in its environment’s bucket. For detailed
information on Amazon S3 network security and best practices, see
<a href="https://docs.aws.amazon.com/AmazonS3/latest/dev/security.html"
class="external-link" rel="nofollow">Amazon S3 Security</a>. 

<span style="color: rgb(23,43,77);">If you have a regulatory requirement
that restricts data from residing in the cloud or outside geographic
boundaries, <span class="inline-comment-marker"
ref="d77448d1-e218-4662-bbad-b9a4264e9b0c">use a Private Agent Group
instead.</span> </span>

### Private Agent Groups

<span style="color: rgb(23,43,77);">Because you manage and control
Private Agents, <span class="inline-comment-marker"
ref="24381c05-06a9-498b-9bc9-ffdd5deadaf0">you control their
security.</span> When you use Private Agents, data doesn't leave your
servers. If you use a private cloud, </span>you <span
class="inline-comment-marker"
ref="4ad4eb20-c215-479d-8af7-7fb3e3f6d6c3">choose </span><span
class="inline-comment-marker"
ref="10c5da2c-8f66-4fd8-bb01-5e9a7e04e8b0">where</span> your integration
runtime environment operates and you control which network your business
data travels and resides in. 

Private Agents authenticate and communicate with Jitterbit Harmony over
HTTPS. Private Agents deployed behind corporate firewalls can be
configured to communicate via a corporate proxy server. There are no
additional networking requirements, such as opening ports within
corporate firewalls. Security is your responsibility when using Private
Agents. 

Jitterbit provides advice and best practice recommendations for hosting
Private Agent code in [System Requirements for Private
Agents](https://success.jitterbit.com/display/DOC/System+Requirements+for+Private+Agents).

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE**: If you are using private agent groups, review the information
under [Security and Data Protection
Regulations](#SecurityBestPracticesforAdministrators,ProjectBuilders,andIntegrationSpecialists-SecurityDataProtectionRegs).

</div>

</div>

### Securing Endpoints with Private Agents

There are <span class="inline-comment-marker"
ref="b10efdc1-ddf5-4520-8e33-1826fdd6d4d0">many methods</span> you can
use to secure endpoints including:

-   Use a VPN (Virtual Private Network) along with encryption.

-   Network whitelists can control who is allowed access to your
    network. To use whitelisting with Private Agents, see [Whitelist
    Information](https://success.jitterbit.com/display/DOC/Whitelist+Information).

-   Make sure any drivers and plugins you use are up to date and
    tested. 


## Organizations and Environments

Different users and groups will need different access levels to access
your [Organizations](https://success.jitterbit.com/display/DOC/Organizations) and
[Environments](https://success.jitterbit.com/display/DOC/Environments).  A <span
class="inline-comment-marker"
ref="b60d5b95-25dd-4724-b36a-35f6a3982ca9">user</span> doesn't need the
same access level as a developer or an administrator. For example, a
developer in your organization may need Execute and Write permissions to
the [API Manager](https://success.jitterbit.com/display/DOC/API+Manager) to create and edit security
profiles, create and edit APIs, and access certain functionality in
Management Console. The day-to-day user doesn't require these elevated
permissions. Think about users and groups and what they do. Limit access
so that users can only use what they need to perform their tasks. 

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE**: For information on the different access roles, such as User,
Administrator, and Developer, and how to define them, see [Managing Role
Access to Environments](https://success.jitterbit.com/display/DOC/Organizations) on the
[Environments](https://success.jitterbit.com/display/DOC/Environments) page. 

</div>

</div>

Apply hardware and software patches. <span class="inline-comment-marker"
ref="68e8c2bc-99b1-4a1c-be82-ac986afd989e">For Cloud Agent Groups,
Jitterbit is responsible for code changes</span>. If you are using
Private Agent Groups, monitor updates and patches to your OS and
application <span class="inline-comment-marker"
ref="5558fee4-9e43-422a-a732-31cdd464cf73">software</span>, drivers, and
plug-ins, and apply them when appropriate.

Providing secure authentication
using <a href="https://oauth.net/" class="external-link"
rel="nofollow">OAuth</a> and multi-factor authentication, such as 2FA
(two-factor authentication) is critical. OAuth is discussed
under [Security Profiles](https://success.jitterbit.com/display/DOC/Security+Profiles) in the [API
Manager](https://success.jitterbit.com/display/DOC/API+Manager). 2FA is discussed in [Jitterbit
Password Controls](https://success.jitterbit.com/display/DOC/Jitterbit+Password+Controls).

<span class="inline-comment-marker"
ref="3186f6d9-e105-4b8f-9d3e-d591d4026b82">Keep development and testing
accounts separate from production. This includes separate </span>IDs and
passwords. <span class="inline-comment-marker"
ref="41ab2312-315f-4910-b463-c80528c35e34">Remove these development and
testing IDs and passwords before migrating code to
production.</span> Instead, use [project
variables](https://success.jitterbit.com/display/CS/Project+Variables) to store information such as
IDs and passwords. As a best practice, maintain separate development,
testing, and production environments. You should also ensure that
Personal Identifiable Information (PII) is not used in testing. 

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE:** If you are in a regulated industry, such as health care, or if
you are subject to government regulations concerning data and data
movement, review those requirements as part of your security planning.

</div>

</div>


## API Security

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE:** For an in-depth discussion on the Harmony API and Security,
see [Harmony API Security](https://success.jitterbit.com/display/DOC/Harmony+API+Security).

</div>

</div>

The Harmony API Manager supports <a
href="https://success.jitterbit.com/download/attachments/108167629/offsite-link-icon-4.png?version=1&amp;modificationDate=1580763471552&amp;api=v2"
data-linked-resource-id="108167623" data-linked-resource-version="1"
data-linked-resource-type="attachment"
data-linked-resource-default-alias="offsite-link-icon-4.png"
data-nice-type="Image" data-linked-resource-content-type="image/png"
data-linked-resource-container-id="108167629"
data-linked-resource-container-version="10">OAuth 2.0</a> authentication
with [Google](https://success.jitterbit.com/display/DOC/Google+OAuth+2.0+API+Security+Profile),
[Okta](https://success.jitterbit.com/display/DOC/Okta+3-Legged+OAuth+2.0+API+Security+Profile), and
[Salesforce](https://success.jitterbit.com/display/DOC/Salesforce+OAuth+2.0+API+Security+Profile) as
Identity Providers. NetSuite now enforces token-based authentication
(TBA) for Administrator, Full Access, and other highly privileged roles
<span class="inline-comment-marker"
ref="722ed11b-0a18-4c3e-89ae-6ccb5caf8818">as of their</span> 2018.2
release. See [NetSuite 2018.2 Token-Based
Authentication](https://success.jitterbit.com/display/DOC/NetSuite+2018.2+Token-Based+Authentication)
for more information and instructions. API Keys and API Secrets can be
used to authenticate users with the Harmony API. 

## Certificates

Jitterbit can authenticate with external resources with [SSL
client](https://success.jitterbit.com/display/DOC/SSL+Client+Certificates)
[certificates](https://success.jitterbit.com/display/DOC/Customizations+%3E+Client+Certificates) when
connecting to [HTTP](https://success.jitterbit.com/display/CS/HTTP) or [SOAP](https://success.jitterbit.com/display/CS/SOAP)
endpoints in Cloud Studio, and with HTTP endpoints or [Web
Services](https://success.jitterbit.com/display/DOC/Creating+a+Web+Service+Method) in Design Studio.
Client Certificates settings can be accessed in the [Jitterbit Harmony
Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal) on the **Management
Console \> Customizations \> Client Certificates** page. 

### Adding Certificates to a Keystore 

Jitterbit applications that are installed locally include a trusted
keystore that contains the certificates needed for secure communication
via HTTPS. For example, <span class="inline-comment-marker"
ref="1b400f4c-ba24-47e2-921a-ab8a5fad447f">you would add a new</span>
certificate to the Jitterbit Java keystore if you use a proxy server and
need to allow the Jitterbit local client to securely communicate through
the proxy server. You can add new certificates as needed. You will also
need to replace or renew certificates if they are changed. Information
and instructions on adding certificates to a keystore can be found on
these pages:

-   [Adding Certificates to Keystore for Data
    Loader](https://success.jitterbit.com/display/DOC/Adding+Certificates+to+Keystore+for+Data+Loader)

-   [Adding Certificates to Keystore for Design
    Studio](https://success.jitterbit.com/display/DOC/Adding+Certificates+to+Keystore+for+Design+Studio)

-   [Adding Certificates to Keystore for Private
    Agents](https://success.jitterbit.com/display/DOC/Adding+Certificates+to+Keystore+for+Private+Agents)


## Connector Security

When migrating your project to another environment, you want to avoid
sharing private information. Start with these connector security
features:

-   **<span class="inline-comment-marker"
    ref="e1254802-8caf-4601-a195-82fee6d13dab">Project
    Variables:</span>** When working with Connectors, [project
    variables](https://success.jitterbit.com/display/CS/Project+Variables) can provide additional
    security. If you're creating scripts or transformations, use project
    variables for private information such as login or user IDs,
    passwords, access keys, and other information that must be kept
    secure. See <a
    href="https://success.jitterbit.com/display/CS/Project+Variables#ProjectVariables-use-project-variablesUsingProjectVariablesinScriptsorTransformations"
    rel="nofollow">Using Project Variables in Scripts or Transformations</a>
    for information and procedures. 

-   **Configuration:** Unencrypted user names and passwords are required
    at runtime. Use keystores and pull this information from a database
    stored off the agent and not called until runtime. 

-   **<span class="inline-comment-marker"
    ref="3374c492-c733-4963-8289-9b14656aca17">Third-party
    Vaults</span>:**<span style="letter-spacing: 0.0px;"> Secure,
    digital online vaults are designed to protect the privacy of your
    data. Using data encryption, strong user authentication, and
    redundant storage, these vaults allow cloud storage with data
    security. The specific features, pricing, and instructions depend on
    the provider you choose. </span>

-   **IP Whitelists**: In most situations you don't need to make any
    special network or firewall changes when Private Agents or Design
    Studio communicate with Jitterbit Harmony. What if your network is
    behind a firewall? In that case, configure your network to
    communicate with Jitterbit Harmony and use a whitelist to allow this
    communication. Jitterbit provides whitelisted IP addresses for each
    region. See <a
    href="https://success.jitterbit.com/display/DOC/Whitelist+Information"
    style="letter-spacing: 0.0px;" rel="nofollow">Whitelist Information</a><span
    style="letter-spacing: 0.0px;"> for more information. </span>


## Log Security

When thinking about logging and security, examine your business
requirements. Decide on what level of logging you need and what risks
are acceptable to you based on your security requirements. Jitterbit
generates logs for different functions such as [operations
logs](https://success.jitterbit.com/display/CS/Operation+Logs), [Windows or Linux event
logs](https://success.jitterbit.com/display/DOC/Log+File+Locations), and [API
logs](https://success.jitterbit.com/display/DOC/API+Logs). Most customers use cloud logging in the
Jitterbit cloud. Log data is encrypted for security. You can disable
cloud logging if required.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE**: If you disable cloud logging, application logs are not
written. 

</div>

</div>

### Cloud Agents

When a Cloud Agent Group runs an integration operation, it creates an
activity log that is stored in the cloud. You view logs from the
[Activities](https://success.jitterbit.com/display/DOC/Activities) page of the [Management
Console](https://success.jitterbit.com/display/DOC/Management+Console). These records and their
details are retained for 30 days. Jitterbit supplies [logging and error
functions](https://success.jitterbit.com/display/CS/Logging+and+Error+Functions) to help you create
and debug scripting. `WriteToOpereationLog()` can be used to write
sensitive data to logs, but we strongly recommend against this as it can
create a security issue. 

Jitterbit provides a Jitterpak with an API you can use to download your
logs. This Jitterpak is available from Jitterbit Support by <a
href="https://community.jitterbit.com/s/login/?startURL=%2Fs%2Fsupport&amp;src=sidebar"
class="external-link" rel="nofollow">submitting a support case</a> and requesting
the Jitterpak with the Download Logs API. See [Getting
Support](https://success.jitterbit.com/display/DOC/Getting+Support) for details on contacting
Jitterbit Support. Contact Jitterbit Support for information on the
retention schedule for log data. 

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE:** Though Jitterbit does not provide native support for sharing
operation logs using tools such as ELK, Splunk, or Loggly, many log
monitoring tools have agents that can be deployed on the same machine as
the Private Agent. These agents then collect data based on defined rules
and ingest data to the log monitoring tool. 

</div>

</div>

### Private Agents

Using a Private Agent Group keeps all your information within your
organization and on your own servers. Disable cloud logging, to avoid
sending logs to Harmony. At the end of each operation, you can use a
script to send log data locally. Debug logs, transformation logs, error
logs, endpoint call error logs, and more are available, and can be set
in the `jitterbit.conf` file.  See [Editing the Configuration File -
`jitterbit.conf`](https://success.jitterbit.com/display/DOC/Editing+the+Configuration+File+-+jitterbit.conf)
for settings and values. 
