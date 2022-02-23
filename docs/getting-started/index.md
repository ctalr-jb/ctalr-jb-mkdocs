[//]: # (Getting Started)

## Overview

The *Jitterbit Harmony API Integration Platform* (Harmony) is
Jitterbit's modern, multi-tenant, born-in-the-cloud API integration
platform that connects Software as a Service (SaaS), on-premises, cloud,
and legacy applications.

### <span id="GettingStarted-harmony-components" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Harmony Components

Harmony is powered by Jitterbit's iPaaS capabilities and consists of
these components:

-   **Harmony Agents (Cloud Agents and Private Agents):** Harmony Agents
    do the work at runtime, connecting to various endpoint systems,
    transforming data, etc. You can use Cloud Agents (serverless agents)
    and/or Private Agents (formerly known as Local Agents) with one of
    these deployment models:
    -   **Cloud (Serverless, Full Cloud, Multi-Tenant):** On the
        Jitterbit Harmony cloud, where the system and scale is
        completely managed by Jitterbit.
    -   **Private (On-Premises, Local):** Either an on-premises server
        or in a public/private cloud, where the system is self-hosted
        and/or self-managed.
    -   **Hybrid:** In a hybrid mode, where selected portions of the
        system are self-managed and the remainder is fully managed by
        Jitterbit.
-   **Harmony API Gateway:** Provides security, throttling, and
    validation of any and every incoming API that users publish via
    Jitterbit.
-   **Harmony Backend Services:** Include a notification engine, remote
    Private Agent management, and a number of other backend systems and
    services.
-   **Harmony Design Repository:** A secure and encrypted, centralized
    collection of the integration projects.
-   **Harmony Messaging Services:** Facilitate communication among
    various Harmony components, providing a reliable method for routing,
    tracking, and integration retry mechanisms.
-   **Harmony Transaction Logs:** Provide easy debugging capabilities
    and can be stored for a configurable period of time either locally
    or on the cloud.

### <span id="GettingStarted-harmony-applications" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Harmony Applications

The **[Jitterbit Harmony
Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal)** is the web-based
interface where you access the Harmony applications:

-   **Studio:** Jitterbit's project design application where you can
    design, test, and deploy your integration projects. Two versions are
    available:
    -   **[Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio):** Cloud Studio
        features a modern and collaborative user experience with a
        cloud-based UI.
    -   **[Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio):** Design Studio
        is a standalone thick client that can be installed on a Windows
        or macOS workstation.
-   **[API Manager](https://success.jitterbit.com/display/DOC/API+Manager):** Jitterbit's API
    management web interface where you can create and publish
    developer-friendly APIs and perform full API lifecycle management
    tasks.
-   **[Marketplace](https://success.jitterbit.com/display/DOC/Marketplace):** Jitterbit's resource
    for searching and retrieving Cloud Studio integration recipes and
    process templates to help you quickly create new Cloud Studio
    projects.
-   **[Management
    Console](https://success.jitterbit.com/display/DOC/Management+Console):** Jitterbit's web console
    where you can manage your integration projects and perform
    administrative functions related to your organization.
-   **[Citizen
    Integrator](https://success.jitterbit.com/display/DOC/Citizen+Integrator):** Jitterbit's
    click-and-run web application for non-technical users to quickly
    customize and deploy Design Studio integrations using pre-built
    Citizen Integrator recipes.
-   **[Data Loader](https://success.jitterbit.com/display/DOC/Data+Loader):** Jitterbit's free data
    migration tool that enables Salesforce administrators to quickly and
    easily automate the import and export of data between flat files,
    databases, and Salesforce.

For a graphical depiction and detailed description of Harmony
components, refer to the [Jitterbit Security and Architecture White
Paper](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper).


## Creating and Registering a Jitterbit Harmony Account

To get started with Jitterbit Harmony you will need to create and
register an account:

1.  <a
    href="https://info.jitterbit.com/Harmony-Trial_Request-your-Trial_smart.html"
    class="external-link" rel="nofollow">Request a free Harmony trial</a>.
2.  Register your account. The registration instructions depend on how
    you signed up or were invited:
    -   **I signed up for a trial:** If you signed up for a free trial,
        a Jitterbit sales representative will approve your request and
        send you a welcome email with further instructions. Use the link
        provided in that welcome email to complete the registration
        process.
    -   **I was invited to an organization:** If you were invited by
        another Jitterbit Harmony user, use the link provided within
        your welcome email to register your account.
    -   **I was invited to an organization using SSO:** If you were
        invited by another Jitterbit Harmony user to an organization
        configured for [single sign-on](https://success.jitterbit.com/display/DOC/Single+Sign-On),
        you will already be registered through your Identity Provider.
3.  Once registered, you are able to log in to the [Jitterbit Harmony
    Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal) at <a href="https://login.jitterbit.com./" class="external-link"
    rel="nofollow">https://login.jitterbit.com.</a>

If you are an administrator (user with *Admin* permission), follow
the [Jitterbit Admin Quick Start
Tutorial](https://success.jitterbit.com/display/DOC/Jitterbit+Admin+Quick+Start+Tutorial) to set up
an environment, agents and Agent Groups, and invite team members to your
organization.

To learn the basics of getting started with Cloud Studio, see the <a
href="https://success.jitterbit.comhttps://success.jitterbit.com/display/CS/Cloud+Studio+Quick+Start+Guide"
rel="nofollow">Cloud Studio Quick Start Guide</a>. If you are using
Design Studio, see the <a
href="https://success.jitterbit.comhttps://success.jitterbit.com/display/DOC/Design+Studio+Quick+Start+Guide"
rel="nofollow">Design Studio Quick Start Guide</a> to design your first
project.


## More Information

For more information for new users, refer to the pages within this
topic:

-   **[Getting Support](https://success.jitterbit.com/display/DOC/Getting+Support)  
    **<br>Running into a unique problem, or need help understanding what to
    do? Ask the Jitterbit community or submit a support case through
    the <a href="https://community.jitterbit.com/s/" class="external-link"
    rel="nofollow">Jitterbit Community</a> portal.
-   **[Getting Training](https://success.jitterbit.com/display/DOC/Getting+Training)**<br>
    Enroll in courses and test your knowledge through
    <a href="https://university.jitterbit.com/" class="external-link"
    rel="nofollow">Jitterbit University</a>, our self-paced online
    learning system.
-   **[Jitterbit Harmony
    Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal)**<br>
    After you have logged in to the
    <a href="https://login.jitterbit.com" class="external-link"
    rel="nofollow">Harmony Portal</a>, some elements are common across
    all Harmony applications, such as accessing your account information
    and changing your password.
-   **[Jitterbit Admin Quick Start
    Tutorial](https://success.jitterbit.com/display/DOC/Jitterbit+Admin+Quick+Start+Tutorial)**<br>
    If you're ready for hands-on interaction with Harmony, this guide
    starts you off in the Management Console to set up an environment
    and then walks you through creating your first project in either
    [Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio) or [Design
    Studio](https://success.jitterbit.com/display/DOC/Design+Studio).
-   **[Jitterbit Security](https://success.jitterbit.com/display/DOC/Jitterbit+Security)**<br>
    Security information is provided for server admins and operations
    staff to learn more about how we keep your data safe and secure at
    Jitterbit.
-   **[Supported Endpoints and
    Protocols](https://success.jitterbit.com/display/DOC/Supported+Endpoints+and+Protocols)  
    **<br>Jitterbit has connected with hundreds of applications and data
    sources. We're constantly building connections to new applications,
    so if you don't see your application listed,
    just <a href="https://www.jitterbit.com/contact/" class="external-link"
    rel="nofollow">contact us</a>.
-   **[System Requirements](https://success.jitterbit.com/display/DOC/System+Requirements)**<br>
    System requirements for all Harmony products in one place. Some of
    our products are browser-based, but for those that require
    installation, we provide detailed instructions to get you up and
    running.

In addition, refer to these resources for help getting started with
Jitterbit in general or for information on a specific endpoint:

-   **[Best Practices with
    Jitterbit](https://success.jitterbit.com/display/DOC/Best+Practices+with+Jitterbit)**<br>
    Once you're familiar with Harmony, learn how our own Jitterbit
    experts are able to introduce best practices into their own
    integrations.
-   **[Jitterpak Library](https://success.jitterbit.com/display/DOC/Jitterpak+Library)**<br>
    If you have a simple project or common use case, using an example
    can be the quickest way to begin. Download a Jitterpak example from
    here to get started on a project.
-   **[Video Library](https://success.jitterbit.com/display/DOC/Video+Library)**<br>
    Prefer to watch rather than read? We've got you covered with a
    variety of training topics and endpoint-specific demos.
