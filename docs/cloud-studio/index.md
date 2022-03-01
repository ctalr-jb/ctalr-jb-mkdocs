# Jitterbit Harmony Cloud Studio

## Overview

*Jitterbit Harmony Cloud Studio* (Cloud Studio) is the web-based version
of Jitterbit's project design application.

Accessible directly through the [Jitterbit Harmony
Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal), Cloud Studio offers a
modern design experience optimized for ease-of-use and ease-of-access
by integration designers.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/overview_workflows-tab.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/overview_workflows-tab.png" /></span>

## Prerequisites

Cloud Studio is accessed through the Harmony Portal and does not require
any additional hardware or software installation. The only requirements
are browser and Jitterbit Harmony Agent version requirements.

### Browser Requirements

These major browsers are supported:

-   Chrome

-   Firefox

-   Safari (macOS only)

In order to communicate with the Harmony cloud and access the Harmony
Portal, JavaScript needs to be enabled and outbound port 443 (HTTPS)
needs to be open. This port is normally allowed by corporate server
firewalls.

### Agent Requirements

The minimum Jitterbit Harmony Agent version supported with Cloud Studio
overall is version 9.4.2.

Certain Cloud Studio features require later agent versions, including
these:

-   Custom connectors built with [Connector
    Builder](https://success.jitterbit.com/display/CS/Connector+Builder) require an agent version
    10.0 or later.

-   Custom connectors built with the
    <a href="https://developer.jitterbit.com/connector-sdk/"
    class="external-link" rel="nofollow">Connector SDK</a> require an
    agent version 10.0 or later.

-   [Application
    connectors](https://success.jitterbit.com/display/CS/Connector+Classifications#ConnectorClassifications-application) —
    except for custom connectors as noted above — require an agent
    version 10.1 or later.

-   The NetSuite connector has different [agent version
    prerequisites](https://success.jitterbit.com/display/CS/NetSuite+Prerequisites) for specific
    NetSuite WSDL versions.

-   The [**Try Again**
    button](https://success.jitterbit.com/display/CS/Operation+Logs#OperationLogs-operation-retry)
    available in operation logs requires an agent version 10.1 or later.

-   The
    [`SendEmail` function](https://success.jitterbit.com/display/CS/Email+Functions#EmailFunctions-SendEmail)
    requires an agent version 10.1 or higher to use multi-byte
    characters.

-   The [**Retry**
    setting](https://success.jitterbit.com/display/CS/HTTP+Connection#HTTPConnection-retry) available
    in the configuration of an HTTP connection requires a Private Agent
    version 10.22 or later.

-   The [**Retry on Recoverable Exception**
    setting](https://success.jitterbit.com/display/CS/NetSuite+Connection#NetSuiteConnection-retry)
    available in the configuring of a NetSuite connection requires a
    Private Agent version 10.24 or later.

-   The [**Retry**
    setting](https://success.jitterbit.com/display/CS/SOAP+Connection#SOAPConnection-retry) available
    in the configuration of a SOAP connection requires a Private Agent
    version 10.29 or later.

The above list is not exhaustive; features that require later agent
versions are noted in the documentation on each feature.

## Reference

Cloud Studio reference documentation is organized into sections by
topic:

-   **[Introduction](https://success.jitterbit.com/display/CS/Introduction):** This section includes
    a quick start guide and tutorials, description of the user
    interface, and terminology and definitions.

-   **[Projects](https://success.jitterbit.com/display/CS/Projects):** A project is a collection of
    one or more workflows that comprise and execute an integration use
    case.

-   **[Project Components](https://success.jitterbit.com/display/CS/Project+Components):** Project
    components are the discrete building blocks of a project.

-   **[Workflows](https://success.jitterbit.com/display/CS/Workflows):** A workflow is a collection
    of operations used as a tool for your convenience to help segregate
    different parts of the project.

-   **[Operations](https://success.jitterbit.com/display/CS/Operations):** An operation is the
    smallest unit that is independently executed on an agent and
    recorded by Harmony. Operations are used to define what an
    integration should do and when it should be done.

-   **[Connectors](https://success.jitterbit.com/display/CS/Connectors):** Connectors provide the
    interface for entering user-provided input such as credentials to
    create an authorized connection. Activities associated with those
    connections can then be added to operations on the design canvas and
    configured as sources or targets. An endpoint refers to a specific
    connection and its activities.

-   **[Schemas](https://success.jitterbit.com/display/CS/Schemas):** Source and target schemas
    represent the request and response structures for interaction with a
    data resource in an operation. These schemas can be either defined
    within the transformation or provided by an adjacent activity.

-   **[Transformations](https://success.jitterbit.com/display/CS/Transformations):** Transformations
    are used as steps in an operation to map or *transform* inputs to a
    resulting output by moving data, cleaning data, or applying business
    logic. A transformation consists of source and target schemas that
    have been defined in the transformation and the transformation
    mapping that generates the output.

-   **[Scripts](https://success.jitterbit.com/display/CS/Scripts):** Scripts provide the flexibility
    and power to transform data, perform calculations, or perform logic
    validation beyond simple field mapping. Scripts can be used both as
    steps of an operation as well as within transformations to apply
    specified logic or conditions to the data.

-   **[Functions](https://success.jitterbit.com/display/CS/Functions):** Functions are used within
    scripts in operations and transformations to enhance and refine data
    processes.

-   **[Variables](https://success.jitterbit.com/display/CS/Variables):** Variables are used to allow
    for the dynamic configuration of endpoints, to support passing of
    data between operations, and to drive detailed integration logic
    within transformation scripts.

-   **[Notifications](https://success.jitterbit.com/display/CS/Notifications):** Notifications that
    send a customized email can be triggered on success or failure of an
    operation or called from a script.

-   **[Plugins](https://success.jitterbit.com/display/CS/Plugins):** Plugins are Jitterbit- or
    user-provided applications that extend Harmony's native
    capabilities. Jitterbit provides a selection of plugins or you can
    create your own using Jitterbit's Plugin SDK.
    
-   **[Recipes and
    Templates](https://success.jitterbit.com/display/CS/Recipes+and+Templates):** <span
    style="color: rgb(23,43,77);text-decoration: none;">A Cloud Studio
    integration recipe is a single, pre-built integration project that
    moves data in one direction between objects across two applications
    or systems. A Cloud Studio process template is a group of pre-built
    integration use cases that accelerates the execution of a specific
    business process using numerous objects across multiple applications
    or systems. Integration recipes and process templates are both
    accessed through [Jitterbit
    Marketplace](https://success.jitterbit.com/display/DOC/Marketplace).</span>
