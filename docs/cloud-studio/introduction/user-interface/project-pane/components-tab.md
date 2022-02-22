[//]: # (Project Pane Components Tab)

## Introduction

The project pane's **Components** tab is one of two tabs accessible in
the [project pane](https://success.jitterbit.com/display/CS/Project+Pane). (The other tab is the
[**Workflows** tab](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab)).

The **Components** tab displays all of the components in the open
project grouped by component category.

## <span id="ProjectPaneComponentsTab-categories" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Component Categories

Each of these top-level categories is displayed, regardless of whether
it contains any components:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/categories.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/categories.png" /></span>

-   **Custom Groups:** Custom groups are an organizational tool to help
    organize project components (see [Component
    Groups](https://success.jitterbit.com/display/CS/Component+Groups)). After creating a custom
    group, its user-defined name is displayed as a subcategory under
    **Custom Groups**. Under each custom group, any components contained
    within the custom group are listed.

-   **Files:** All file schemas are listed
    (see [Schemas](https://success.jitterbit.com/display/CS/Schemas)).

-   **Endpoints:** An endpoint refers to a specific connection and its
    activities, created using connectors (see
    [Connectors](https://success.jitterbit.com/display/CS/Connectors)).

    After creating an activity instance associated with a connection,
    the endpoint type is displayed as a subcategory under **Endpoints**,
    followed by the number of endpoints of that type in parentheses. For
    example, **Database Endpoints (2)**. Connections are not displayed
    or counted unless at least one activity has been created from them.

    The user-defined connection name is displayed as an additional
    subcategory under the endpoint type, followed by the number of
    activity instances that have been created from each connection in
    parentheses. For example, **Oracle (4)**.

    Under each connection, the name of each activity instance is
    preceded by square brackets containing the type of interaction with
    the data resource that is specific to the activity type. On the same
    line, this is followed by the user-defined activity name. For
    example, **\[Database_Insert\]** **Insert Customers**.

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/project-pane/components/endpoints.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/endpoints.png" /></span>

-   **Operations:** All operations are listed
    (see [Operations](https://success.jitterbit.com/display/CS/Operations)).

-   **Scripts:** All project component scripts are listed
    (see [Scripts](https://success.jitterbit.com/display/CS/Scripts)). Scripts created on target
    fields or nodes in a transformation are not project components, as
    they are considered part of the transformation component.

-   **Transformations:** All transformations are listed
    (see [Transformations](https://success.jitterbit.com/display/CS/Transformations)).

-   **Project Variables:** All project variables are listed
    (see [Project Variables](https://success.jitterbit.com/display/CS/Project+Variables)).

-   **Global Variables:** All global variables are listed (see [Global
    Variables](https://success.jitterbit.com/display/CS/Global+Variables)).

-   **Emails:** All email notifications are listed (see [Email
    Notifications](https://success.jitterbit.com/display/CS/Email+Notifications)).

-   **Schedules:** All operation schedules are listed (see [Operation
    Schedules](https://success.jitterbit.com/display/CS/Operation+Schedules)).


## Searching and Filtering

Along the top of the **Components** tab, you can search and filter
components to limit those displayed in this tab.

### Searching

To search within the **Components** tab, use the search box to enter a
single keyword or keyword string. The categories are automatically
expanded to show components where the keyword string appears. The
keyword string becomes bold and purple within the name of the component:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/search.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/search.png" /></span>

To clear the search, click the remove icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_11.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_11.png"
height="18" /></span>.

### <span id="ProjectPaneComponentsTab-orphaned" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Filtering

To filter by project component, use the filter icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/filter.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/filter.png"
height="16" /></span> dropdown to select from one of these filter
options:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/filter.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/filter.png" /></span>

-   **All:** Show all components in the current project.

-   **Undeployed:** Show only components in the current project that
    have not yet been deployed or have been modified after they have
    been deployed.

-   **Orphaned:** Show only components that are not referenced by other
    components or workflows in the current project. Orphaned components
    are displayed with an unreferenced (broken link) icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
    height="14" /></span> regardless of whether this filter is selected.
    Orphaned components are also referred to as unreferenced or unused
    components.

    <div
    class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
    hasbody="true" macro-name="info">

    <span
    class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **NOTE:** The orphaned classification is based on the project as it
    currently exists in the Cloud Studio project designer and doesn't
    take into account whether components have been deployed to Harmony.

    </div>

    </div>

-   **Invalid:** Show only components in the current project that are
    invalid. Invalid components are not able to be deployed. Validation
    criteria are described in [Component
    Validity](https://success.jitterbit.com/display/CS/Component+Validity). This filter may be useful
    to identify invalid components that are also orphaned in case you
    want to delete the unreferenced component instead of resolving
    errors.

Once a filter is applied, a filter label is displayed below the filter
icon:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/filter_label.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/filter_label.png" /></span>

To return to the **All** view, click the remove icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_12.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_12.png"
height="14" /></span> next to the filter label.

## Expanding and Selecting Items

To expand or collapse all categories at once, double-click the category
name or the disclosure triangles <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/down-arrow_6.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/down-arrow_6.png"
height="9" /></span> <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/right-arrow_5.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/right-arrow_5.png"
height="12" /></span> next to the category. To expand or collapse
individual categories, use a single click.

<span style="color: rgb(23,43,77);">As you work on projects, Cloud
Studio remembers the display states that a given user was last using for
a given project, including whether the categories in the project pane
are expanded or collapsed.</span>

<span style="color: rgb(23,43,77);">When a category is expanded, click a
component within the category to select it. A selected component is
displayed with a gray background:</span>

<span style="color: rgb(23,43,77);"><span
class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/activity_selected.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/activity_selected.png" /></span></span>

<span style="color: rgb(23,43,77);">If the component is also referenced
on the design canvas, the first instance of it is scrolled into
view.</span>

<span style="color: rgb(23,43,77);">Categories themselves cannot be
selected.</span>

## Viewing Validity Errors and References

Visual indications of component validity and the number of other
components that reference a component are displayed as described below.

### Validity Errors

When using the **Highlight Invalid Items** option on the design canvas
or when filtering on **Invalid** items, an error icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/error.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/error.png"
height="16" /></span> is displayed next to invalid components, whose
names appear in italics and the color red:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/transformations_invalid.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/transformations_invalid.png" /></span>

You can view the validation errors associated with invalid components as
described in [Component Validity](https://success.jitterbit.com/display/CS/Component+Validity)
and [Operation Validity](https://success.jitterbit.com/display/CS/Operation+Validity).

### References

A component can be referenced by other components or workflows
throughout the project.

The number of components that reference the component is indicated by
the presence or absence of icons to the left of the component name:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_references.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_references.png" /></span>

-   A component that is not referenced by any other components or
    workflows in the project is known as an orphaned component, and is
    displayed with an unreferenced (broken link) icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
    height="14" /></span>.
-   A component that is referenced by only one other component or
    workflow is displayed without any visual indicator.
-   A component that is referenced by multiple components — or an
    operation that is referenced by component(s) and a workflow, or by
    multiple components — has the number of components it is referenced
    by displayed inside a circle <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/reference-count.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/reference-count.png"
    height="18" /></span>.

Further details are provided in [Component
Reuse](https://success.jitterbit.com/display/CS/Component+Reuse) and [Operation
Reuse](https://success.jitterbit.com/display/CS/Operation+Reuse).


## Actions Menus

To open a menu of actions to take on each component category or
component, do one of these:

-   Right-click the category or component.
-   Hover over the category or component, and then click the actions
    menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_2.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_2.png"
    height="8" /></span>.

The actions available in each menu depend on the context and vary
according to the category or component.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE:** The **Custom Groups** category and components displayed within
them are covered in [Component Groups](https://success.jitterbit.com/display/CS/Component+Groups).

</div>

</div>

### <span id="ProjectPaneComponentsTab-category-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Category Actions Menu

Some actions are available only on certain categories, as detailed
below. The images below display the actions menus for the **Scripts**
category (left image) and for the **Endpoints** category (right image):

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Scripts Category Actions Menu**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_category-actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_category-actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:45%;min-width:45%;max-width:45%;" hasbody="true"
macro-name="column">

**Endpoints Category Actions Menu**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/endpoints_category-actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/endpoints_category-actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:5%;min-width:5%;max-width:5%;" hasbody="true"
macro-name="column">



</div>

</div>

</div>

</div>

<div class="table-wrap">

<table class="wrapped confluenceTable">
<tbody>
<tr class="header">
<th class="confluenceTh">Menu Item</th>
<th class="confluenceTh">Description</th>
</tr>

<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/create-new.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/create-new.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Create New</strong> c<span>reates a
new, unreferenced component of the respective type in the
category.</span></p>
<p>This action is available on the categories <strong>Scripts</strong>,
<strong>Transformations</strong>, <strong>Project Variables</strong>,
<strong>Emails</strong>, and <strong>Schedules</strong>.</p>
<p>On creating the component, the component configuration screen opens
for you to configure the component.</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/paste-script.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/paste-script.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Paste <em>Component
Type</em>:</strong> Places the cut or copied component that is on your
clipboard, thereby creating a duplicate of the component as a new,
unreferenced component (see <a
href="https://success.jitterbit.com/display/CS/Component+Reuse">Component Reuse</a>).</p>
<p>This action is available on <strong>Files</strong>,
<strong>Endpoints</strong>, <strong>Operations</strong>,
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong>, <strong>Emails</strong>, and
<strong>Schedules</strong>. It is enabled only when you have a component
of the corresponding type on your clipboard.</p>
<p>On creating the component duplicate, your cursor is positioned on the
component name for renaming.</p></td>
</tr>
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/delete-unused.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/delete-unused.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><div class="content-wrapper">
<p><strong>Delete Unused </strong><span>permanently deletes components
in the category that aren't referenced by any other components in the
current project (see </span><a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Component
Dependencies, Deletion, and Removal</a><span>).</span></p>
<p>This action is available on <strong>Files</strong>,
<strong>Endpoints</strong>, <strong>Operations</strong>,
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong>, <strong>Global
Variables</strong>, <strong>Emails</strong>, and
<strong>Schedules</strong>. It is enabled only when the category
contains unreferenced components, displayed with an unreferenced (broken
link) icon <span><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/unreferenced.png"
height="14" /></span></span><span>.</span></p>
</div></td>
</tr>
</tbody>
</table>

</div>

### <span id="ProjectPaneComponentsTab-component-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Component Actions Menu

Some actions are available only on certain types of components, as
detailed in the subsections below:

-   **[Operations](#ProjectPaneComponentsTab-operations): **The actions
    menu for operations (shown in the left image) has unique items such
    as **Settings**, **Run**, and **View Logs** and unique sub-menus for
    **Duplicate** and **Deploy**. It also includes common actions such
    as **Cut**, **Copy**, **Rename**, **View Dependencies**, **Add to
    Group**, **Delete**, and **Remove**.
-   **[Files, Activities, Scripts, Transformations, Project Variables,
    Global Variables, Emails, and
    Schedules](#ProjectPaneComponentsTab-share): **The actions menus for
    these components share many of the same actions, such as
    **View/Edit**, **Cut**, **Copy**, **Duplicate**, **Deploy**,
    **Rename**, **View Dependencies**, **Add to Group**, **Delete**, and
    **Remove**. A script's actions menu (shown in the middle image)
    shows all available actions. Some of these actions are not available
    on all components, as described in this section.
-   **[Connections](#ProjectPaneComponentsTab-connections): **The
    actions menu for a connection (shown in the right image) has the
    **View/Edit** and **Test** actions.

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:30%;min-width:30%;max-width:30%;" hasbody="true"
macro-name="column">

**Operation Actions Menu**

**<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/operations_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/operations_actions-menu.png" /></span>**

</div>

<div class="columnMacro conf-macro output-block"
style="width:30%;min-width:30%;max-width:30%;" hasbody="true"
macro-name="column">

**Script Actions Menu**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/scripts_actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:30%;min-width:30%;max-width:30%;" hasbody="true"
macro-name="column">

**Connection Actions Menu**

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/connection_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/connection_actions-menu.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:5%;min-width:5%;max-width:5%;" hasbody="true"
macro-name="column">



</div>

</div>

</div>

</div>

#### <span id="ProjectPaneComponentsTab-operations" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Operations

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

#### <span id="ProjectPaneComponentsTab-share" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Files, Activities, Scripts, Transformations, Project Variables, Global Variables, Emails, and Schedules

The actions menus for these components share many of the same actions:

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
configuration screen for activities listed in an endpoint type
subcategory under <strong>Endpoints</strong>, and components in
the <strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong>, <strong>Emails</strong>, and
<strong>Schedules</strong> categories. (This action is not available for
components in the <strong>Files</strong> or <strong>Global
Variables</strong> categories.)</p>
<p>The component configuration screen can also be opened by
double-clicking a component name.</p>
<p>For details on configuration, <span>refer to the respective component
under</span> <a href="https://success.jitterbit.com/display/CS/Connectors">Connectors</a>, <a
href="https://success.jitterbit.com/display/CS/Scripts">Scripts</a>,<span> <a
href="https://success.jitterbit.com/display/CS/Project+Variables">Project Variables</a>,</span> <a
href="https://success.jitterbit.com/display/CS/Transformations">Transformations</a>,<span> </span> <a
href="https://success.jitterbit.com/display/CS/Notifications">Notifications</a>,<span> or <a
href="https://success.jitterbit.com/display/CS/Operation+Schedules">Operation
Schedules</a>.</span></p></td>
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
project (see <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Component Reuse</a>).
This action is available for activities listed in an endpoint type
subcategory under <strong>Endpoints</strong>, and components in the
<strong>Files</strong>, <strong>Scripts</strong>,
<strong>Transformations</strong>, <strong>Project
Variables</strong>, <strong>Emails</strong>, and
<strong>Schedules</strong> categories. (This action is not available in
the <strong>Global Variables</strong> category.)</p></td>
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
href="https://success.jitterbit.com/display/CS/Component+Reuse">Component Reuse</a>). This action is
available for activities listed in an endpoint type subcategory under
<strong>Endpoints</strong>, and components in the
<strong>Files</strong>, <strong>Scripts</strong>,
<strong>Transformations</strong>, <strong>Project
Variables</strong>, <strong>Emails</strong>, and
<strong>Schedules</strong> categories. (This action is not available in
the <strong>Global Variables</strong> category.)</p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Duplicate</strong> creates a new,
unreferenced component using the same configuration as the original
component (see <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Component
Reuse</a>). This action is available for activities listed in an
endpoint type subcategory under <strong>Endpoints</strong>, and
components in the <strong>Scripts</strong>, <strong>Project
Variables</strong>, <strong>Emails</strong>, and
<strong>Schedules</strong> categories. (This action is not available
for components in the <strong>Files</strong>,
<strong>Transformations</strong>, or <strong>Global Variables</strong>
categories.)</p></td>
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
style="color: rgb(23,43,77);"><strong>Rename</strong> </span><span
style="color: rgb(23,43,77);">positions the cursor on the component name
for you to make any edits as necessary. This action is available
for </span><span>activities listed in an endpoint type subcategory under
</span><strong>Endpoints</strong><span>, and components in the
</span><strong>Files</strong><span>, </span><strong>Scripts</strong><span>,
</span><strong>Transformations</strong><span>, </span><strong>Project
Variables</strong><span>, </span><strong>Emails</strong><span>, and
</span><strong>Schedules</strong><span> categories. (This action is not
available in the </span><strong>Global Variables</strong><span>
category.)</span></p></td>
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
that the specific component is dependent on (see <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Component
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
<td class="confluenceTd"><p><strong>Delete</strong> permanently deletes
the component (see <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Component
Dependencies, Deletion, and Removal</a>). <span
style="color: rgb(23,43,77);">This action is available
for </span>activities listed in an endpoint type subcategory under
<strong>Endpoints</strong>, and components in the
<strong>Files</strong>, <strong>Scripts</strong>,
<strong>Transformations</strong>, <strong>Project
Variables</strong>, <strong>Emails</strong>, and
<strong>Schedules</strong> categories. (This action is not available in
the <strong>Global Variables</strong> category.)</p></td>
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
to the component from the design canvas. This action is available
for activities listed in an endpoint type subcategory under
<strong>Endpoints</strong>, and components in the
<strong>Scripts</strong>, <strong>Transformations</strong>,
<strong>Project Variables</strong>, <strong>Emails</strong>, and
<strong>Schedules</strong> categories. (This action is not available for
components in the <strong>Files</strong> or <strong>Global
Variables</strong> categories.) It is functional only when used on an
activity, transformation, or script that is referenced as a step in an
operation, or when used on an email notification that is configured with
an operation action (see <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Component
Dependencies, Deletion, and Removal</a>).</p></td>
</tr>
</tbody>
</table>

</div>

#### <span id="ProjectPaneComponentsTab-connections" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Connections

Connections are listed in an endpoint type subcategory under
**Endpoints**. The actions menu for a connection has the **View/Edit**
and **Test** actions:

<div class="table-wrap">

<table class="relative-table wrapped confluenceTable"
style="width: 87.7076%;">
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
configuration screen for the connection (see documentation on <span>the
specific endpoint connection under</span><span> </span><a
href="https://success.jitterbit.com/display/CS/Connectors">Connectors</a>)<span>.</span></p></td>
</tr>
<tr class="even">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/test.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/test.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Test</strong> tests the connection.
This action is the same as clicking the <strong>Test</strong><span>
button available in a connection configuration screen (see documentation
on the specific endpoint connection </span><span>under</span><span>
</span><a
href="https://success.jitterbit.com/display/CS/Connectors">Connectors</a><span>).</span></p></td>
</tr>
</tbody>
</table>

</div>

<div class="conf-macro output-block" hasbody="false"
macro-name="easy-heading-free">

<div class="easy-heading-free">

</div>

<div class="easy-heading-free-end">

</div>

</div>

<div class="conf-macro output-block" hasbody="false"
macro-name="hideelements-macro">

</div>
