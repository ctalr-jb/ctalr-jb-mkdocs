[//]: # (Design Component Palette)

## Introduction

The design component palette is one of the two types of component
palettes. (The other type is the [script component
palette](https://success.jitterbit.com/display/CS/Script+Component+Palette).)

The design component palette is displayed next to the design canvas and
provides access to create connections and activities using connectors in
its **Connectivity** tab:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_amazon-s3_activities.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_amazon-s3_activities.png" /></span>

For definitions and an annotated diagram identifying connectivity
resources, see
[Connectivity](https://success.jitterbit.com/display/CS/Cloud+Studio+Terminology#CloudStudioTerminology-connectivity)
in [Cloud Studio Terminology](https://success.jitterbit.com/display/CS/Cloud+Studio+Terminology).

## Collapsing and Expanding

To collapse the component palette to provide for more screen real estate
on the design canvas, click the collapse icon in the top right:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/collapse_2.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/collapse_2.png" /></span>

To expand the component palette, click the **Connectivity** tab icon:

<span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/common/icons/tab_connectivity.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/tab_connectivity.png"
height="40" /></span>

## Filtering and Searching

Along the top of the **Connectivity** tab, you can filter and search to
limit the connectivity resources displayed in the palette.

### Filtering

To filter what is displayed in the **Connectivity** tab, use the
**Show** dropdown:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/show.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/show.png" /></span>

-   **Endpoints:** Displays connections. The connections can be clicked
    to display activity types for each connection. For details, see
    [Endpoints](#DesignComponentPalette-endpoints) later on this page.
-   **Connectors:** Displays connectors. For details, see
    [Connectors](#DesignComponentPalette-connectors) later on this page.
-   **All:** Displays both connections and connectors as described
    above.

### Searching

To search within the **Connectivity** tab using the selected filter, use
the search box to enter a single keyword or keyword string:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_amazon_search.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_amazon_search.png" /></span>

To clear the search, click the remove icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/close_10.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_10.png"
height="18" /></span>.


## <span id="DesignComponentPalette-connectors" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Connectors

A connector provides the interface for entering user-provided input such
as credentials to create a connection. The **Connectors** filter shows
the available connectors.

To open the configuration screen for a connection, click a connector:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_amazon-s3.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_amazon-s3.png" /></span>

For configuration details, see the documentation for the endpoint
connection under [Connectors](https://success.jitterbit.com/display/CS/Connectors).

## <span id="DesignComponentPalette-endpoints" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Endpoints

An endpoint refers to a specific connection and its activities. The
**Endpoints** filter shows the connections.

To select a connection and reveal its activity types, click the
connection:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_amazon-s3_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_amazon-s3_connection.png" /></span>

A selected connection is displayed with a white and purple border. The
activity types are displayed below the connection:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_amazon-s3_activities.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_amazon-s3_activities.png" /></span>

To position your cursor for renaming a connection, click the connection
name or click an already selected connection.

To create an instance of an activity that can be configured, drag an
activity type to the design canvas or copy the activity type and paste
it on the design canvas (see [Creating an Activity
Instance](https://success.jitterbit.com/display/CS/Component+Reuse#ComponentReuse-creating-an-activity-instance)
in [Component Reuse](https://success.jitterbit.com/display/CS/Component+Reuse)). For configuration
details, see the documentation for the endpoint activity under
[Connectors](https://success.jitterbit.com/display/CS/Connectors).

The actions menu for connections is described in the next section,
[Actions Menus](#DesignComponentPalette-actions-menus).


## <span id="DesignComponentPalette-actions-menus" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Actions Menus

To open a menu of actions to take on a connection or activity type, do
one of these:

-   Right-click the connection or activity type.
-   Hover over the connection or activity type, and then click the
    actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_24.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_24.png"
    height="18" /></span>.

### <span id="DesignComponentPalette-connection-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Connection Actions Menu

A connection's actions menu includes these actions:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connection_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connection_actions-menu.png" /></span>

<div class="table-wrap">

<table class="relative-table confluenceTable" style="width: 87.7076%;">
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
<tr class="odd">
<td class="confluenceTd"><div class="content-wrapper">
<p><span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/duplicate.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><strong>Duplicate</strong> creates a new,
unreferenced connection using the same configuration as the original
connection (see <a href="https://success.jitterbit.com/display/CS/Component+Reuse">Component
Reuse</a>).</td>
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
<td class="confluenceTd"><strong>Delete</strong> permanently deletes the
connection (see <a
href="https://success.jitterbit.com/display/CS/Component+Dependencies%2C+Deletion%2C+and+Removal">Component
Dependencies, Deletion, and Removal</a>).</td>
</tr>
</tbody>
</table>

</div>

### <span id="DesignComponentPalette-activity-type-actions-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Activity Type Actions Menu

An activity type's actions menu includes this action:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/activity-type_actions-menu.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/activity-type_actions-menu.png" /></span>

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
src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/menu-items/copy.png"
height="33" /></span></p>
</div></td>
<td class="confluenceTd"><p><strong>Copy</strong> p<span>laces a copy of
the activity type on your clipboard to be used to create an activity
instance (see </span><a href="https://success.jitterbit.com/display/CS/Component+Reuse">Component
Reuse</a><span>).</span></p></td>
</tr>
</tbody>
</table>

</div>
