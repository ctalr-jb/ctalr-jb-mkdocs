[//]: # (Project Pane Workflows Tab)

## Introduction

The project pane's **Workflows** tab is one of two tabs accessible in
the [project pane](https://success.jitterbit.com/display/CS/Project+Pane). (The other tab is the
[**Components** tab](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab)).

The **Workflows** tab displays a hierarchically organized tree view of
an open project's workflows, operations, and other components referenced
within each operation.

## Hierarchical Tree

In a project, workflows are at the highest hierarchical level, followed
by operations, and then by other components used as steps within an
operation (made up of activities, transformations, or scripts).

This structure is represented in an open project's **Workflows** tab,
where workflows appear at the top with a workflow icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/workflow.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/workflow.png"
height="15" /></span> to the left of the workflow. Workflows are
expandable to reveal operations indented below each workflow. Operations
are expandable to reveal the components referenced as steps within each
operation. Both workflows and operations are auto-assigned numbers to
represent their position in the tree:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/overview.png" /></span>

When each workflow and operation is expanded, all workflows, operations,
and operation steps are displayed.

## Searching

To search within the **Workflows** tab, use the search box to enter a
single keyword or keyword string. The hierarchical tree is automatically
expanded to show workflows and components where the keyword string
appears. The keyword string becomes bold (if not already) and purple
within the name of the workflow or component:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/search.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/search.png" /></span>

To clear the search, click the remove icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_11.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_11.png"
height="18" /></span>.

## Expanding and Selecting Items

To expand or collapse workflows or operations, click the disclosure
triangles <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/down-arrow_6.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/down-arrow_6.png"
height="9" /></span> <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/right-arrow_5.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/right-arrow_5.png"
height="12" /></span> next to the workflow or operation.

<span style="color: rgb(23,43,77);">As you work on projects, Cloud
Studio remembers the display states that a given user was last using for
a given project, including whether the items in the project pane are
expanded or collapsed.</span>

Click a workflow to select it and open it on the [design
canvas](https://success.jitterbit.com/display/CS/Design+Canvas). A selected workflow is displayed
with a purple name and gray background:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_selected.png" /></span>

When a workflow is expanded, click an operation within the workflow to
select it and auto-scroll to it on the [design
canvas](https://success.jitterbit.com/display/CS/Design+Canvas). A selected operation is displayed
with a gray background:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_expanded.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_expanded.png" /></span>

When an operation is expanded, click an operation step within the
operation to select it and auto-scroll to it on the [design
canvas](https://success.jitterbit.com/display/CS/Design+Canvas). A selected operation is displayed
with a gray background:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_expanded_operation-step.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_expanded_operation-step.png" /></span>


## Viewing Validity Errors

When using the **Highlight Invalid Items** option on the design canvas,
the names of invalid workflows, operations, and other components appear
in italics and the color red. When selected, an invalid workflow is
displayed with a pink background.

If the workflow or component is implicitly invalid, an error icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/error.png"
height="16" /></span> is also displayed:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_workflow.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/invalid_workflow.png" /></span>

You can view the validation errors associated with invalid workflows and
components as described in [Workflow
Validity](https://success.jitterbit.com/display/CS/Workflow+Validity), [Operation
Validity](https://success.jitterbit.com/display/CS/Operation+Validity), and [Component
Validity](https://success.jitterbit.com/display/CS/Component+Validity). 


## Actions Menus

To open a menu of actions to take on each workflow or component, do one
of these:

-   Right-click the item.
-   Hover over the item, and then click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_22.png"
    height="6" /></span>.

The actions available in each menu depend on the context and vary
according to the item.

### <span id="ProjectPaneWorkflowsTab-workflow-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Workflow Actions Menu

The workflow actions menu includes these actions:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/workflow_actions-menu.png" /></span>

<div class="table-wrap">

<table class="relative-table confluenceTable" style="width: 97.8058%;">
<colgroup>
<col style="width: 13%" />
<col style="width: 86%" />
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
src="https://docs-source.jitterbit.com/cs/menu-items/deploy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/deploy.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Deploy</strong> deploys the workflow
and any components it is dependent on <span>(see </span><a
href="https://success.jitterbit.com/display/CS/Workflow+Deployment">Workflow
Deployment</a><span>).</span></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/configurable-deploy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/configurable-deploy.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Configurable Deploy</strong> opens
the deployment screen, where you can select project components to
deploy (see <a href="https://success.jitterbit.com/display/CS/Workflow+Deployment">Workflow
Deployment</a>).</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><span
style="color: rgb(23,43,77);"><strong>Rename</strong> </span><span
style="color: rgb(23,43,77);">positions the cursor on the workflow name
for you to make any edits as necessary.</span></p></td>
</tr>
<tr class="even">
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
that the specific workflow is dependent on <span>(see </span><a
href="https://success.jitterbit.com/display/CS/Workflow+Dependencies+and+Deletion">Workflow
Dependencies and Deletion</a><span>).</span></p></td>
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
<td class="confluenceTd"><strong>View Logs</strong> opens the operation
log screen, which includes logs for any operations contained in the
workflow that have been deployed and executed, as well as any operations
linked from the workflow that have been deployed and executed (see <a
href="https://success.jitterbit.com/display/CS/Operation+Logs">Operation Logs</a><span>).</span></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Delete</strong> permanently deletes
the <span>workflow (see </span><a
href="https://success.jitterbit.com/display/CS/Workflow+Dependencies+and+Deletion">Workflow
Dependencies and Deletion</a><span>).</span></p></td>
</tr>
</tbody>
</table>

</div>

### <span id="ProjectPaneWorkflowsTab-component-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Component Actions Menu

Some actions are available only on certain types of components, as
detailed in the subsections below:

-   **[Operations](#ProjectPaneWorkflowsTab-operations):** The actions
    menu for operations (shown in the left image) has unique items such
    as **Settings**, **Run**, and **View Logs** and unique sub-menus for
    **Deploy**. It also includes common actions such as **Cut**,
    **Copy**, **Rename**, **View Dependencies**, **Delete**, and
    **Remove**.
-   **[Activities, Scripts, and
    Transformations](#ProjectPaneWorkflowsTab-share):** The actions
    menus for these components share the same actions,
    including **View/Edit**, **Cut**, **Copy**, **Deploy**, **Rename**,
    **View Dependencies**, **Delete**, and **Remove** (shown in an
    activity's actions menu in the right image).

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Operation Actions Menu**

**<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/operation_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/operation_actions-menu.png" /></span>**

</div>

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Activity Actions Menu**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/activity_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/activity_actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:5%;min-width:5%;max-width:5%;" hasbody="true"
macro-name="column">



</div>

</div>

</div>

</div>

#### <span id="ProjectPaneWorkflowsTab-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operations

These items are available in an operation's actions menu:

<div class="table-wrap">

<table class="confluenceTable">
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
<tr class="odd">
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
<tr class="even">
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
<tr class="odd">
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
<tr class="even">
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

#### <span id="ProjectPaneWorkflowsTab-share" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Activities, Scripts, and Transformations

The actions menus for these components share the same actions:

<div class="table-wrap">

<table class="relative-table confluenceTable">
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
src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/rename.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><span
style="color: rgb(23,43,77);"><strong>Rename</strong> </span><span
style="color: rgb(23,43,77);">positions the cursor on the component name
for you to make any edits as necessary. </span>You can also double-click
a component name to enter rename mode.</p></td>
</tr>
<tr class="even">
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
that the specific component is dependent on (see <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Component
Dependencies, Deletion, and Removal</a><span>).</span></p></td>
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
<td class="confluenceTd"><p><strong>Delete</strong> permanently deletes
the component (see <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Component
Dependencies, Deletion, and Removal</a>).</p></td>
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
<td class="confluenceTd"><p><strong>Remove</strong> removes references
to the component from the design canvas (see <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Component
Dependencies, Deletion, and Removal</a>).</p></td>
</tr>
</tbody>
</table>

</div>

## Reordering Workflows and Operations

Workflows and operations can be reordered by dragging and dropping them
in the project tree.

### <span id="ProjectPaneWorkflowsTab-reorder-a-workflow" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span><span style="color: rgb(85,46,155);">Reordering Workflows</span>

To reorder workflows, drag a workflow to another location in the project
tree:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/reorder-workflow.gif"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/reorder-workflow.gif" /></span>

This action has a cascading effect of renumbering both the workflows and
the operations contained within each workflow.

### <span id="ProjectPaneWorkflowsTab-reorder-an-operation" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Reordering Operations

To reorder operations, drag an operation name to another location within
or between workflows in the project tree:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/reorder-operation.gif"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/reorder-operation.gif" /></span>

This action has a cascading effect of renumbering the operations above
or below it in the tree.
