[//]: # (Design Canvas)

## Introduction

The design canvas is the central area when you open a project that
serves as the primary workspace where you visually design
integrations. This page covers elements of the user interface that are
present on the design canvas, as well as key concepts to understand
while working on the design canvas.

To access the design canvas, first [open a
project](https://success.jitterbit.com/display/CS/Project+Creation+and+Configuration). In an open
project, the design canvas is the central area located to the right of
the [project pane](https://success.jitterbit.com/display/CS/Project+Pane) and to the left of
the [component palette](https://success.jitterbit.com/display/CS/Component+Palette), below the
[project toolbar](https://success.jitterbit.com/display/CS/Project+Toolbar):

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/project-designer_design-canvas_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/project-designer_design-canvas_annotated_pp.png" /></span>

## Design Canvas Header

These elements are present along the top of the design canvas:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/design-canvas/header.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/header.png" /></span>

-   **Workflow Tabs:** Workflows are accessed from tabs along the top of
    the design canvas. Additional workflows can be created by clicking
    the new workflow icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/add_4.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/add_4.png"
    height="16" /></span>. The new workflow opens in a new tab within
    the design canvas. Workflows are numbered sequentially in the order
    they are created, as 1.0, 2.0, 3.0, etc. If you reorder workflows,
    this numeric sequence adjusts accordingly (see [Reordering
    Workflows](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design#WorkflowCreationandDesign-reordering-workflows)
    in [Workflow Creation and
    Design](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design)).

-   **Save Status:** The auto-save status is displayed in the top left
    of the design canvas. These statuses are available:

    -   **Saved:** All project items are saved as currently configured.

    -   **Saving:** The project is currently being saved. This status
        occurs only after changes have been made.

-   **Last Deployed:** The date and time that any part of the project
    was last deployed is displayed. If no parts of the project have yet
    been deployed, nothing is displayed here.

-   **Collapse All Operations** or **Expand All Operations:** Toggles
    the display of all operations within the current workflow to a
    condensed or expanded view (see [Expanding or Collapsing
    Operations](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration#OperationCreationandConfiguration-expanding-or-collapsing)
    in [Operation Creation and
    Configuration](https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration)).

-   **Highlight Invalid Items:** Toggles the display of invalid
    items (see [Workflow
    Validity](https://success.jitterbit.com/display/CS/Workflow+Validity), [Operation
    Validity](https://success.jitterbit.com/display/CS/Operation+Validity), or [Component
    Validity](https://success.jitterbit.com/display/CS/Component+Validity), respectively).

-   **Actions:** Click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_18.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_18.png"
    height="8" /></span> to open the design canvas actions menu (see
    [Design Canvas Actions
    Menu](#DesignCanvas-deploy-migrate-actions-menu) later on this
    page).

## <span id="DesignCanvas-design-canvas-elements" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Design Canvas Elements

The primary function of the design canvas is to have a workspace where
you visually design workflows. Each workflow is made up of a collection
of operations that is used as a tool for your convenience to help
segregate different parts of the project.

Workflows are designed by placing and configuring operations on the
design canvas. Design canvas elements are the items that visually appear
on the design canvas to help you design a workflow, including these:

-   [Drop zones](#DesignCanvas-drop-zones) for operations and for other
    components used as operation steps
-   [Operations](#DesignCanvas-operations) and the components used as
    operation steps within them
-   [Notifications](#DesignCanvas-notifications) that are linked from
    operations
-   [Operation references](#DesignCanvas-external-operations) that are
    outside of the current workflow and linked from an operation in the
    current workflow
-   [Lines](#DesignCanvas-lines) that connect linked operations,
    scripts, and notifications

Each of those design canvas elements is covered below. For additional
information on designing workflows, see [Workflow Creation and
Design](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design).

### <span id="DesignCanvas-drop-zones" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Drop Zones

A drop zone is a visual representation of where an operation or other
component can be placed on the design canvas. There are two types of
drop zones, operation drop zones and component drop zones:

-   **Operation drop zone:** Operation drop zones indicate where an
    operation can be placed. An operation drop zone is permanently
    displayed at the bottom of the design canvas after the last
    operation. To show additional operation drop zones, hover above the
    existing operations. When you click to select an operation drop
    zone, it is displayed with a purple border outlining the drop zone
    and is selected until you change focus:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_operation.gif"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_operation.gif" /></span>

-   **Component drop zone:** Component drop zones indicate where other
    components that can be used as operation steps can be placed in an
    existing operation. To show a component drop zone, hover to the left
    or right of an operation step in an existing operation on the design
    canvas. When you click to select a component drop zone, it is
    displayed with a purple border outlining the drop zone and is
    selected until you change focus:  

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component.gif"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component.gif" /></span>

An actions menu is available on each drop zone. Both operation drop
zones and the drop zones for other components show the same menu items,
as described in [Drop Zone Actions
Menu](#DesignCanvas-component-drop-zone-actions-menu) later on this
page.

### <span id="DesignCanvas-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span id="DesignCanvas-operation-toolbar" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operations

Operations are visually represented on the design canvas by a dynamic
rectangular area with a gray background:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_magento.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_magento.png" /></span>

-   **Operation Title:** The operation title appears in the top left of
    an operation and consists of the operation number and operation
    name:

    -   **Operation Number:** A unique number that is automatically
        assigned depending on where the operation appears in a workflow.
        Workflows are automatically numbered sequentially beginning with
        the number `1.0` and increasing by `1.0` for each subsequent
        workflow (`1.0`, `2.0`, `3.0`, etc.). Within a workflow,
        operations are further automatically designated with a decimal
        number, beginning with `.0` and increasing by `.1` for each
        subsequent operation. For examples, see [Designing a
        Workflow](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design#WorkflowCreationandDesign-designing-a-workflow)
        in [Workflow Creation and
        Design](https://success.jitterbit.com/display/CS/Workflow+Creation+and+Design).

    -   **Operation Name:** The user-provided name of the operation.
        When you create a new operation, its default name is *New
        Operation*. Subsequent new operations with default names are
        appended with an incremented number in parentheses. Operation
        names must be unique and must not contain forward slashes (`/`)
        or colons (`:`) to be valid. To rename an operation,
        see [Renaming Workflows, Operations, and Operation
        Steps](#DesignCanvas-renaming) later on this page.

-   **Operation Toolbar:** The operation toolbar appears in the top
    right of an operation and consists of this set of icons:

    <div class="table-wrap">

    <table class="wrapped confluenceTable">
    <tbody>
    <tr class="header">
    <th class="confluenceTh">Icon</th>
    <th class="confluenceTh">Description</th>
    </tr>

    <tr class="odd">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/schedules.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/schedules.png" /></span></p>
    </div></td>
    <td class="confluenceTd"><p>Opens the <strong>Schedules</strong> tab of
    the operation settings (see <a
    href="https://success.jitterbit.com/display/CS/Operation+Schedules">Operation Schedules</a>).</p>
    <p>This icon is displayed only when an operation already has an assigned
    schedule.</p></td>
    </tr>
    <tr class="even">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/deploy.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/deploy.png" /></span></p>
    </div></td>
    <td class="confluenceTd"><p>Deploys the operation and any components it
    is dependent on (see <a
    href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution#OperationDeploymentandExecution-deploy">Deploying</a>
    in <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Operation
    Deployment and Execution</a>).</p></td>
    </tr>
    <tr class="odd">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/deploy-and-run.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/deploy-and-run.png" /></span></p>
    </div></td>
    <td class="confluenceTd"><p>Opens the deployment screen, where you can
    select project components to deploy (see <a
    href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution#OperationDeploymentandExecution-deploy">Deploying</a>
    in <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Operation
    Deployment and Execution</a>).</p></td>
    </tr>
    <tr class="even">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/collapse.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/collapse.png" /></span></p>
    </div></td>
    <td class="confluenceTd"><p>Collapses the operation into a smaller,
    condensed view (see <a
    href="https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration#OperationCreationandConfiguration-expanding-or-collapsing">Expanding
    or Collapsing Operations</a> in <a
    href="https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration">Operation
    Creation and Configuration</a>).</p>
    <p>This icon is displayed only when the operation is expanded.</p></td>
    </tr>
    <tr class="odd">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper"><img
    src="https://docs-source.jitterbit.com/common/icons/expand.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/expand.png" /></span></p>
    </div></td>
    <td class="confluenceTd"><p>Expands the operation into the standard
    view (see <a
    href="https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration#OperationCreationandConfiguration-expanding-or-collapsing">Expanding
    or Collapsing Operations</a> in <a
    href="https://success.jitterbit.com/display/CS/Operation+Creation+and+Configuration">Operation
    Creation and Configuration</a>).</p>
    <p>This icon is displayed only when the operation is collapsed.</p></td>
    </tr>
    <tr class="even">
    <td class="confluenceTd"><div class="content-wrapper">
    <p><span
    class="confluence-embedded-file-wrapper image-center-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    class="confluence-embedded-image confluence-external-resource image-center"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    height="6" /></span></p>
    </div></td>
    <td class="confluenceTd">Opens the <a
    href="#DesignCanvas-operation-actions-menu">operation actions menu</a>,
    described later on this page.</td>
    </tr>
    </tbody>
    </table>

    </div>

-   **Operation Steps:** Each operation that has already been configured
    with operation steps includes a visual representation of those
    steps. Each step is represented by a square showing an icon
    representing the component, beneath which is the component name.

    -   **Actions Menu:** Each operation step has an actions menu that
        is accessible by right-clicking the operation step or by using
        the actions menu icon <span
        class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
        src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
        class="confluence-embedded-image confluence-external-resource"
        data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
        height="18" /></span>. Each menu item is described in [Component
        Actions Menu](#DesignCanvas-component-actions-menu) later on
        this page.

    -   **Plugin Icon:** Activities that have been configured with a
        plugin that runs on execution of the operation display a plugin
        icon <span
        class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/plugin.png"
        class="confluence-embedded-image confluence-external-resource"
        data-image-src="https://docs-source.jitterbit.com/common/icons/plugin.png"
        height="24" /></span> in the top right of the operation step.
        For more information, see [Plugins Added to an
        Activity](https://success.jitterbit.com/display/CS/Plugins+Added+to+an+Activity).

-   **Operation Status:** After an operation has been successfully
    submitted to the operation queue, the real-time operation status is
    reported in the lower left of an operation. For details, see
    [Operation
    Status](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution#OperationDeploymentandExecution-operation-status)
    in [Operation Deployment and
    Execution](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution).

#### Selecting Operations and Operation Steps

To select an operation, click the background of the operation. A
selected operation is displayed with a purple border outlining the
operation. In this example, the entire *Upsert Postgres Products*
operation has been selected:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_selected.png" /></span>

To select an operation step, click the visual representation of the
step. A selected operation step is displayed with a purple border
outlining the component. In this example, the *Magento Products to
Postgres* transformation is selected:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_selected.png" /></span>

### <span id="DesignCanvas-notifications" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Notifications

A visual representation of a notification appears automatically on the
design canvas when you link an email notification using the **Send Email
Notification** [operation action](https://success.jitterbit.com/display/CS/Operation+Actions).
Additional information about the visual display of links is provided
below under [Lines](#DesignCanvas-lines).

The email notification is displayed with a gray background. Within the
background area, the email notification is represented by a square
showing an icon, beneath which is the email notification name. To select
an email notification, click the visual representation of it. A selected
email notification is displayed with a purple border outlining the
component:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/notification_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/notification_selected.png" /></span>

For menu actions available on an email notification, see [Component
Actions Menu](#DesignCanvas-component-actions-menu) later on this page.

### <span id="DesignCanvas-external-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operation References

Operations that exist outside of the current workflow can be referenced
from an operation in the current workflow. When such an operation is
linked, a visual representation of the outside operation automatically
appears on the design canvas in the current workflow. Additional
information about the visual display of links is provided below under
[Lines](#DesignCanvas-lines).

The operation reference is displayed with a gray background and contains
shape icons that serve as a general representation of operation steps.

An operation that does not exist in another workflow is displayed with
the name of the operation only:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_reference.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_reference.png" /></span>

An operation that exists in another workflow is displayed with the name
of the workflow, followed by the operation name. Click the words to open
the workflow in which the operation exists:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_reference_workflow.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_reference_workflow.png" /></span>

### <span id="DesignCanvas-lines" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Lines

Lines that connect linked operations, scripts, and notifications
automatically appear on the design canvas. The links can be created
either using [operation actions](https://success.jitterbit.com/display/CS/Operation+Actions) or using
the `RunOperation` function.

The color and position of the lines indicate their meaning. Examples of
these lines are provided following these descriptions:

-   **Green:** Green lines are displayed for an **On Success** condition
    and appear on the left of linked operations or emails.
-   **Red:** Red lines are displayed for an **On Fail** condition and
    appear on the right of linked operations or emails.
-   **Orange:** Orange lines are displayed for an **On SOAP
    Fault** condition and appear on the right of linked operations or
    emails.
-   **Gray:** Gray lines are displayed for an operation called from a
    script using the `RunOperation` function.

#### On Success Condition

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain.png" /></span>

#### On Fail Condition

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_email.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_email.png" /></span>

#### On SOAP Fault Condition

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_soap-fault.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_soap-fault.png" /></span>

#### `RunOperation` Function

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_runoperation.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_runoperation.png" /></span>


## Actions Menus

Actions menus accessible from the design canvas include those for the
design canvas, components, and drop zones.

### <span id="DesignCanvas-deploy-migrate-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Design Canvas Actions Menu

Click the actions menu icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/actions-menu_18.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_18.png"
height="8" /></span> in the top right of the design canvas to open a
menu with these actions:

<div class="table-wrap">

<table class="relative-table wrapped confluenceTable">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
</colgroup>
<tbody>
<tr class="header">
<th class="confluenceTh">Menu Item</th>
<th class="confluenceTh">Description</th>
</tr>

<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/undo.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/undo.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Undo</strong> reverses your last
action.</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/redo.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/redo.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Redo</strong> reverses your last
<strong>Undo</strong> action.</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
height="67" /></span></p>
<p><br />
</p>
</div></td>
<td class="confluenceTd"><p><strong>Deploy</strong> shows these menu
actions:</p>
<ul>
<li><strong>Deploy:</strong> Deploys the entire project (see <a
href="https://success.jitterbit.com/display/CS/Project+Deployment">Project Deployment</a>).</li>
<li><strong>Configurable Deploy:</strong> Opens the project deployment
screen, where you can select components to deploy (see <a
href="https://success.jitterbit.com/display/CS/Project+Deployment">Project Deployment</a>).</li>
</ul></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/migrate.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/migrate.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Migrate</strong> opens the project
migration screen, where you can choose the target environment (see <a
href="https://success.jitterbit.com/display/CS/Project+Migration">Project
Migration</a><span>).</span></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/project-history.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/project-history.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Project History</strong> opens a panel
on the right side of the project designer where you can view project
history events, tag events, and restore projects (see <a
href="https://success.jitterbit.com/display/CS/Project+History">Project
History</a><span>).</span></td>
</tr>
</tbody>
</table>

</div>

### <span id="DesignCanvas-component-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Component Actions Menu

To open an operation's actions menu, do one of these:

-   Right-click anywhere on the [operation
    toolbar](#DesignCanvas-operation-toolbar).
-   Click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    height="6" /></span> in the top right of an operation.

To open the actions menu for another component on the design canvas,
including operation steps (activities, transformations, or scripts) and
email notifications, do one of these:

-   Right-click the operation step or email notification.
-   Hover over the operation step or email notification, and then click
    the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
    height="15" /></span>.

Some actions are available only on certain types of components, as
detailed in the subsections below:

-   **[Operations](#DesignCanvas-operations):** The actions menu for
    operations (shown in the left image) has unique items such as
    **Settings**, **Duplicate**, **Run**, **View Logs**, **Rename**,
    **View Dependencies**, **Add to Group**, and **Delete**, and unique
    sub-menus for **Deploy**. It also includes common actions such
    as **Cut**, **Copy**, and **Remove**.
-   **[Activities, Scripts, Transformations, and Email
    Notifications](#DesignCanvas-share):** The actions menus for these
    components share the same actions, including **View/Edit**, **Cut**,
    **Copy**, **Deploy**, and **Remove** (shown in an activity's actions
    menu in the right image).

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Operation Actions Menu**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Activity Actions Menu**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:5%;min-width:5%;max-width:5%;" hasbody="true"
macro-name="column">



</div>

</div>

</div>

</div>

#### <span id="DesignCanvas-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operations

These items are available in an operation's actions menu:

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="header">
<th class="confluenceTh">Menu Item</th>
<th class="confluenceTh">Description</th>
</tr>

<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><strong><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/settings.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/settings.png"
height="33" /></span></strong></p>
</div></td>
<td class="confluenceTd"><p><strong>Settings</strong> opens the
operation settings, containing three tabs:</p>
<ul>
<li><strong>Schedules:</strong> Create and apply schedules to
automatically run operations (see <a
href="https://success.jitterbit.com/display/CS/Operation+Schedules">Operation Schedules</a>).</li>
<li><strong>Actions:</strong> Configure actions to take on success or
failure of the operation (see <a
href="https://success.jitterbit.com/display/CS/Operation+Actions">Operation Actions</a>).</li>
<li><strong>Options:</strong> Set options such as when the operation
will time out, what to log and the timeframe for logging, when the
operation will run, or whether to use chunking (see <a
href="https://success.jitterbit.com/display/CS/Operation+Options">Operation Options</a>).</li>
</ul></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><strong><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
height="33" /></span></strong></p>
</div></td>
<td class="confluenceTd"><p><strong>Cut</strong> places a copy of the
operation on your clipboard and deletes the original operation from the
project (see <a href="https://success.jitterbit.com/display/CS/Operation+Reuse">Operation
Reuse</a>).</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Copy</strong> places a copy of the
operation on your clipboard (see <a
href="https://success.jitterbit.com/display/CS/Operation+Reuse">Operation Reuse</a>).</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu.png"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu_with-step-references_with-step-copies.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate_menu_with-step-references_with-step-copies.png"
height="67" /></span></p>
<p><br />
</p>
<p><br />
</p>
</div></td>
<td class="confluenceTd"><p><strong>Duplicate</strong> shows these menu
actions (see <a href="https://success.jitterbit.com/display/CS/Operation+Reuse">Operation
Reuse</a>):</p>
<ul>
<li><strong>With Step References:</strong> Duplicates the operation
only. The duplicate operation contains references to each of the
original operation steps. </li>
<li><strong>With Step Copies:</strong> Duplicates the operation and
components referenced as operation steps. New components are created for
each operation step and are referenced by the duplicated operation.</li>
</ul></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_deploy-and-run_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_deploy-and-run_configurable-deploy.png"
height="101" /></span></p>
<p><br />
</p>
</div></td>
<td class="confluenceTd"><p><strong>Deploy</strong> shows these menu
actions:</p>
<ul>
<li><strong>Deploy:</strong> Deploys the operation and any components it
is dependent on (see <a
href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Operation
Deployment and Execution</a>).</li>
<li><strong>Deploy and Run:</strong> Deploys and runs the operation and
any downstream (linked) operations (see <a
href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Operation
Deployment and Execution</a>).</li>
<li><strong>Configurable Deploy:</strong> Opens the deployment screen,
where you can select components to deploy (see <a
href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Operation
Deployment and Execution</a>).</li>
</ul></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/run.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/run.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Run</strong> runs an
already-deployed operation and any downstream (linked) operations
(see <a href="https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution">Operation
Deployment and Execution</a>).</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-logs.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>View Logs</strong> opens the
operation log screen, which includes logs for this operation and any
child operations that have been deployed and executed (see <a
href="https://success.jitterbit.com/display/CS/Operation+Logs">Operation Logs</a>).</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><span
style="color: rgb(23,43,77);"><strong>Rename</strong> positions the
cursor on the operation name for you to make any edits as
necessary.</span></p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-dependencies.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>View Dependencies</strong> changes
the view in the project pane to display any other parts of the project
that the specific operation is dependent on (see <a
href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Operation
Dependencies, Deletion, and Removal</a><span>).</span></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/add-to-group.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/add-to-group.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Add to Group</strong> opens a dialog
to create a new custom group or to add the component to an existing
group (see <a href="https://success.jitterbit.com/display/CS/Component+Groups">Component
Groups</a>).</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Delete</strong> permanently deletes
the component (see <a
href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Operation
Dependencies, Deletion, and Removal</a><span>).</span></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Remove</strong> removes references
to the component from the design canvas. This action is functional only
when used on an operation that is in a workflow (see <a
href="https://success.jitterbit.com/display/CS/Operation+Dependencies%2C+Deletion%2C+and+Removal">Operation
Dependencies, Deletion, and Removal</a><span>).</span></p></td>
</tr>
</tbody>
</table>

</div>

#### <span id="DesignCanvas-share" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Activities, Scripts, Transformations, and Email Notifications

The actions menus for these components share the same actions:

<div class="table-wrap">

<table class="relative-table wrapped confluenceTable"
style="width: 88.0399%;">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
</colgroup>
<tbody>
<tr class="header">
<th class="confluenceTh">Menu Item</th>
<th class="confluenceTh">Description</th>
</tr>

<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/view-edit.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/view-edit.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>View/Edit</strong> opens the
configuration screen for the component. For details on
configuration, <span>refer to the respective component under</span> <a
href="https://success.jitterbit.com/display/CS/Connectors">Connectors</a>, <a
href="https://success.jitterbit.com/display/CS/Scripts">Scripts</a>, or <a
href="https://success.jitterbit.com/display/CS/Transformations">Transformations</a><span>.</span></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/cut.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Cut</strong> places a copy of the
component on your clipboard and deletes the original component from the
project (see <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Component
Reuse</a>).</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Copy</strong> places a copy of the
component on your clipboard (see <a
href="https://success.jitterbit.com/display/CS/Component+Reuse">Component Reuse</a>).</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu.png"
height="33" /></span></p>
<p><span
class="confluence-embedded-file-wrapper image-right-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource image-right"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy_menu_deploy_configurable-deploy.png"
height="67" /></span></p>
<p><br />
</p>
</div></td>
<td class="confluenceTd"><p><strong>Deploy</strong> shows these menu
actions:</p>
<ul>
<li><strong>Deploy:</strong> Deploys the component and any components it
is dependent on (see <a
href="https://success.jitterbit.com/display/CS/Component+Deployment">Component Deployment</a>).</li>
<li><strong>Configurable Deploy:</strong> Opens the deployment screen,
where you can select components to deploy (see <a
href="https://success.jitterbit.com/display/CS/Component+Deployment">Component Deployment</a>).</li>
</ul></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/remove.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Remove</strong> removes references
to the component from the design canvas (see <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Component
Dependencies, Deletion, and Removal</a>).</p></td>
</tr>
</tbody>
</table>

</div>

### <span id="DesignCanvas-component-drop-zone-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Drop Zone Actions Menu

Operation drop zones are always visible on the design canvas. To show
the drop zone for a component that can be used as an operation step,
hover to the left or right of an operation step in an existing operation
on the design canvas.

To open the actions menu for either type of drop zone, do one of these:

-   Right-click the drop zone.
-   Hover over the drop zone, and then click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_6.png"
    height="15" /></span><span style="letter-spacing: 0.0px;">.</span>

Both operation drop zones and the drop zones for other components show
the same menu items:

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Operation Drop Zone Actions Menu**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_operation_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_operation_actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Component Drop Zone Actions Menu**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/drop-zone_component_actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:5%;min-width:5%;max-width:5%;" hasbody="true"
macro-name="column">



</div>

</div>

</div>

</div>

<div class="table-wrap">

<table class="relative-table wrapped confluenceTable"
style="width: 86.5449%;">
<colgroup>
<col style="width: 15%" />
<col style="width: 84%" />
</colgroup>
<tbody>
<tr class="header">
<th class="confluenceTh">Menu Item</th>
<th class="confluenceTh">Description</th>
</tr>

<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/new-script.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/new-script.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>New Script</strong> <span>creates a
new script as a step in a new or existing operation (see </span><a
href="https://success.jitterbit.com/display/CS/Script+Types+and+Creation">Script Types and
Creation</a><span>). When used on an operation drop zone, a new
operation is also created.</span></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/new-transformation.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/new-transformation.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>New
Transformation </strong><span>creates a new transformation as a step in
a new or existing operation (see </span><a
href="https://success.jitterbit.com/display/CS/Transformation+Creation+and+Configuration">Transformation
Creation and Configuration</a><span>). When used on an operation drop
zone, a new operation is also created.</span></p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/paste.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/paste.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Paste</strong> <span>creates a
duplicate of an activity, script, operation, or email notification that
is on your clipboard as a new component referenced by a new or existing
operation (see </span><a href="https://success.jitterbit.com/display/CS/Component+Reuse">Component
Reuse</a><span>). When used on an operation drop zone, a new operation
is also created.</span></p>
<p>The default name of the new component uses the name of the original
component appended with <em>- Copy</em>. Subsequent duplicates are
further appended with an incremented number in parentheses.</p></td>
</tr>
</tbody>
</table>

</div>

## <span id="DesignCanvas-renaming" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Renaming Workflows, Operations, and Operation Steps

<span style="color: rgb(23,43,77);">To rename a workflow from the design
canvas, double-click the name in the workflow tab along the top of the
design canvas:</span>

<span style="color: rgb(23,43,77);"><span
class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/workflow-tab_rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/workflow-tab_rename.png" /></span></span>

<span style="color: rgb(23,43,77);">To rename an operation from the
design canvas, click the name in the operation:</span>

<span style="color: rgb(23,43,77);"><span
class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_rename.png" /></span></span>

<span style="color: rgb(23,43,77);">To rename steps within an operation
from the design canvas, click the name in the operation:</span>

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation-step_rename.png" /></span>

## <span id="DesignCanvas-reordering-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Reordering Operations

Operations in the same workflow can be reordered by dragging and
dropping them on the design canvas.

Click and hold anywhere on an operation to pick it up and drag it above
or below other operations within the workflow:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/move-operation.gif"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/move-operation.gif" /></span>

This action has a cascading effect of renumbering the operations above
or below it in the project tree.
