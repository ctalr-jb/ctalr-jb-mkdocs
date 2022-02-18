[//]: # (Cloud Studio Quick Start Guide)

## Introduction

This guide is intended for new users of [Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio), Jitterbit's web-based project
design application. This guide covers the basics of getting started by creating a new project from scratch and
provides an overview of project design concepts.

For a comprehensive guide and step-by-step walkthrough, take the [Introduction to Jitterbit Harmony Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio) course on [Jitterbit
University](https://success.jitterbit.com/display/DOC/Getting+Training). As part of this course, you can also reference the supplemental [Lab
Training Manual for Hands-On
Modules](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio#IntroductiontotheJitterbitHarmonyCloudStudio-manual)
covering a variety of use cases to help get you started.

[Jitterbit Marketplace](https://success.jitterbit.com/display/DOC/Marketplace) also provides hundreds of pre-built projects by offering [Cloud
Studio Integration Recipes](https://success.jitterbit.com/display/CS/Cloud+Studio+Integration+Recipes) and [Cloud Studio Process
Templates](https://success.jitterbit.com/display/CS/Cloud+Studio+Process+Templates). To get started with an existing recipe or template, see
[Starting a Recipe or Template Project](https://success.jitterbit.com/display/DOC/Starting+a+Recipe+or+Template+Project).

<div class="confluence-information-macro confluence-information-macro-information conf-macro output-block" data-hasbody="true" data-macro-name="info">
  <span class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon"> </span>
  <div class="confluence-information-macro-body">
    <strong>NOTE:</strong> Before designing a project, you should have already registered for Jitterbit Harmony and
    set up an environment and Agent Group, as described in the <a
    href="/display/DOC/Jitterbit+Admin+Quick+Start+Tutorial">Jitterbit Admin Quick Start Tutorial</a>.
  </div>
</div>


## <span id="CloudStudioQuickStartGuide-access-cloud-studio" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Accessing Cloud Studio

Cloud Studio is accessed directly through the [Jitterbit Harmony Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal).

From the Harmony Portal landing page, click the **Cloud Studio** application card:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/hp/landing/card_cloud-studio.png"
class="confluence-embedded-image confluence-external-resource"></span>

Cloud Studio opens on the project index, where you can create your first project, next.


## Creating a Project

The project index shows a repository of all your Cloud Studio projects. The first time you access Cloud Studio, this
screen is blank. Click **New Project** to get started:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-index/no-projects.png"
class="confluence-embedded-image confluence-external-resource"></span>

Fill out basic information for your project and then click **Start Designing** to open the project designer.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/project_new_start.png"
class="confluence-embedded-image confluence-external-resource"></span>


## <span id="CloudStudioQuickStartGuide-design-your-project" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Designing a Project

The project designer is the interface where you design a project. The project designer includes the project toolbar,
project pane, design canvas, and a component palette, as well as the configuration screens for each component, such
as those for transformations, scripts, connections, and activities.

On opening a project, these parts of the project designer are displayed, as shown in the example below for a project
that has already been designed:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/project-designer_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"></span>

Generally, you design workflows — or collections of operations grouped for the convenience of the user — within the
design canvas using the tools provided in the component palette, project pane, and on the design canvas itself.

The next sections walk through the basic design process:

1.  [Establishing Connectivity](#CloudStudioQuickStartGuide-establish-connectivity)

2.  [Creating Operation Steps](#CloudStudioQuickStartGuide-create-operation-steps)

3.  [Chaining Operations Together Using Operation Actions](#CloudStudioQuickStartGuide-chain-operations)

4.  [Deploying and Running Operations](#CloudStudioQuickStartGuide-deploy-and-run)

### <span id="CloudStudioQuickStartGuide-establish-connectivity" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Establishing Connectivity

The [design component palette](https://success.jitterbit.com/display/CS/Design+Component+Palette) provides access to connectivity resources.
Here, *connectors* provide the interface entering user-provided input such as credentials to create a connection.
Within the component palette, the **Connectors** filter shows the types of connectors that can be configured:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/connectors_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"></span>

Each connector is represented by a connector folder icon, beneath which is the connector name. Click a connector to
open a configuration screen to create a new connection for access to a particular data resource:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_http_multiple.png"
class="confluence-embedded-image confluence-external-resource"></span>

For detailed instructions on configuring a connection, see the specific connection under
[Connectors](https://success.jitterbit.com/display/CS/Connectors). Each time you create a new connection, you must do so from the connector
folder icons accessible in the **Connectors** filter.

Once you have created a connection, it is shown in the **Endpoints** filter. Click a connection to reveal the types
of activities — interactions with an endpoint — that can be configured for that connection.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_http_activities.png"
class="confluence-embedded-image confluence-external-resource"></span>

An endpoint refers to a specific connection and its activities, which are configured as sources (to provide data) or
targets (to consume data) in a project. For reference, this diagram shows the relationship between connectors,
connections, activities, and endpoints:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/connectivity-terms_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"></span>

### <span id="CloudStudioQuickStartGuide-create-operation-steps" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Creating Operation Steps

Operations that define what the integration should do are created by adding and configuring operation steps — made
up of activities, transformations, and/or scripts — on the design canvas.

The section [Establishing Connectivity](#CloudStudioQuickStartGuide-establish-connectivity) above showed how to
create a connection and see its activity types.

To create an instance of an activity, place an activity type on the design canvas by dragging it or copying it to an
operation or component drop zone:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/create-activity-instance.gif"
class="confluence-embedded-image confluence-external-resource"></span>

Once an activity is created, you can double-click it to configure it as described for each specific activity under
[Connectors](https://success.jitterbit.com/display/CS/Connectors).

To add additional activities, place them on another drop zone. Additional operation drop zones are shown by hovering
above an existing operation. Component drop zones in existing operations are shown by hovering to the left or right
of existing operation steps. A common configuration is to configure one activity as the source of data, and a second
activity to its right as the target of data.

You may also want to add transformations or scripts to an operation. Transformations are used when you want to
transform data prior to reaching its target. Scripts can be used within transformations on target fields and nodes
to apply specified logic or conditions to the data. Scripts can also be used as optional steps within an operation
for a variety of purposes, such as error handling or looping through data records.

To add a new transformation or script directly to an operation, right-click or click the actions menu on a drop zone
and select **New Script** or **New Transformation**:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"></span>

When you add a script or transformation, its configuration screen opens automatically. For details on configuration,
see [Transformations](https://success.jitterbit.com/display/CS/Transformations) and [Scripts](https://success.jitterbit.com/display/CS/Scripts), respectively.

### span id="CloudStudioQuickStartGuide-chain-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Chaining Operations Together Using Operation Actions

After more than one operation is created, you can configure operation actions to trigger other operations to run,
send emails, or write messages to the log after an operation succeeds or fails.

To configure these actions, click the actions menu icon
<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/common/icons/actions-menu_21.png"
class="confluence-embedded-image confluence-external-resource"></span> in the top right of an operation and select
**Settings**:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_settings.png"
class="confluence-embedded-image confluence-external-resource"></span>

On the **Actions** tab of the settings, select the condition that should trigger the action, what action should be
taken, and any additional parameters such as what other operation should be configured to run. For details, see
[Operation Actions](https://success.jitterbit.com/display/CS/Operation+Actions).

Once these actions are configured, lines appear on the design canvas to visually indicate any actions that are
configured to run on success (green lines) or on failure (red lines) of the operation. An operation being kicked off
based on operation actions is said to be downstream of an upstream operation before it.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script.png"
class="confluence-embedded-image confluence-external-resource"></span>

### <span id="CloudStudioQuickStartGuide-deploy-and-run" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Deploying and Running Operations

After you have developed a chain of operations, you deploy it to a Harmony Agent and execute it. To deploy and run
an operation, click the deploy-and-run icon <span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/common/icons/deploy-and-run.png"
class="confluence-embedded-image confluence-external-resource"></span>
in the top right of an operation:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_deploy-and-run.png"
class="confluence-embedded-image confluence-external-resource"></span>

Any operations that are downstream of the operation being deployed and executed are also included.

Instead of manual execution, you can also configure operations to run on a schedule or an API trigger. For more
information, see [Operation Deployment and Execution](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution).

After the operations are executed, you can validate proper behavior by viewing logs. To view logs for a particular
operation and downstream operations, click the actions menu icon
<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/common/icons/actions-menu_21.png"
class="confluence-embedded-image confluence-external-resource"></span> in the top right of an operation and select
**View Logs**. For more information see [Operation Logs](https://success.jitterbit.com/display/CS/Operation+Logs).


## Additional Resources

While you design a project, refer to the in-depth information organized by topic under [Cloud
Studio](https://success.jitterbit.com/display/CS/Cloud+Studio):

-   **[Projects](https://success.jitterbit.com/display/CS/Projects):** Learn basics about project permissions, collaboration, and saving, and
    about how to create, configure, deploy, migrate, export, import, and delete projects.

-   **[Project Components](https://success.jitterbit.com/display/CS/Project+Components):** Browse information about what project components exist
    and what shared actions you can take with each component.

-   **[Workflows](https://success.jitterbit.com/display/CS/Workflows):** Find information about creating, deploying, and deleting workflows,
    dependencies, and what makes a workflow valid.

-   **[Operations](https://success.jitterbit.com/display/CS/Operations):** Reference details on creating operations; configuring operation
    settings such as actions, options, and schedules; viewing operation logs; deploying and executing operations;
    viewing dependencies and deleting operations; and what makes an operation valid.

-   **[Connectors](https://success.jitterbit.com/display/CS/Connectors):** Refer to endpoint-specific documentation on configuring connections
    and activities to connect to and interact with a specific endpoint.

-   **[Transformations](https://success.jitterbit.com/display/CS/Transformations):** Read up on the basics and learn the intricacies of mapping
    data inputs to the desired target output.

-   **[Schemas](https://success.jitterbit.com/display/CS/Schemas):** Get introduced to the various types of schemas and learn how to tell when to
    use them.

-   **[Scripts](https://success.jitterbit.com/display/CS/Scripts):** Discover the flexibility and power of scripts to transform data, perform
    calculations, or perform logic validation within operations or transformations.

-   **[Functions](https://success.jitterbit.com/display/CS/Functions):** Look up descriptions and examples of functions that are able to be used
    in scripts to enhance and refine data processes.

-   **[Variables](https://success.jitterbit.com/display/CS/Variables):** Check out the different types of variables and how they can help you be
    more efficient in designing a project.

-   **[Notifications](https://success.jitterbit.com/display/CS/Notifications):** See how to customize email messages that can be triggered on
    success or failure of an operation or called from a script.

-   **[Plugins](https://success.jitterbit.com/display/CS/Plugins):** Educate yourself on how you can extend Harmony's native capabilities using
    Jitterbit- or user-provided plugins.

Advanced users may also be interested in creating their own connectors for Cloud Studio using Jitterbit's [Connector
Builder](https://success.jitterbit.com/display/CS/Connector+Builder) or [Connector SDK](https://developer.jitterbit.com/connector-sdk/)
