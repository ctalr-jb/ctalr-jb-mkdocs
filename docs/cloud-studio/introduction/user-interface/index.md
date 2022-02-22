[//]: # (Cloud Studio User Interface)

## Introduction

[Cloud Studio](https://success.jitterbit.com/display/CS/Cloud+Studio) is Jitterbit's web-based
project design application, accessible through the [Jitterbit Harmony
Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal).

When you access Cloud Studio, you arrive at the project index, which
contains a repository of all your projects, or you can switch to the
Connector Builder index to see custom connectors created with Connector
Builder.

After opening a project, you design it using the tools provided in the
project designer. The project designer includes the project toolbar,
project pane, design canvas, and component palette, as well as the
configuration screens for each component, such as those for
transformations, scripts, connections, and activities.

<span style="color: rgb(23,43,77);">As you work on projects, Cloud
Studio remembers the display states that you were last using for a given
project the next time you open it.</span>

## <span id="CloudStudioUserInterface-project-index" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Project Index

The [project index](https://success.jitterbit.com/display/CS/Project+Index), displayed using the **My
Projects** dropdown, provides a listing of all your Cloud Studio
projects, and is where you create a new project or import an existing
project. Existing projects can be displayed as index cards that can be
flipped over to reveal additional information about the project, or can
be displayed in a list view. From either view, you can also open the
project, project logs, or project variables list; export the project; or
delete the project.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-index/card-view_flip.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-index/card-view_flip.png" /></span>

Creating a new project (**New Project**), importing a project
(**Import**), or viewing/editing an existing project (**View/Edit**)
opens the project and displays the [project
designer](#CloudStudioUserInterface-project-designer) interface.

## <span id="CloudStudioUserInterface-connector-builder-index" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Connector Builder Index

The [Connector Builder index](https://success.jitterbit.com/display/CS/Connector+Builder+Index),
displayed using the **Connector Builder** dropdown, provides a listing
of custom connectors created with [Connector
Builder](https://success.jitterbit.com/display/CS/Connector+Builder). Existing connectors can be
displayed as cards or in list view, similar to projects. From either
view, you can create a new connector, import a connector, or edit,
delete, or export an existing connector.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector-builder/index_card-view_flip.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector-builder/index_card-view_flip.png" /></span>

The Connector Builder user interface is covered in a separate section of
the documentation, under [Connector
Builder](https://success.jitterbit.com/display/CS/Connector+Builder).

## <span id="CloudStudioUserInterface-project-designer" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Project Designer

The project designer is the interface where you design a project. The
project designer includes the [project
toolbar](#CloudStudioUserInterface-project-toolbar), [project
pane](#CloudStudioUserInterface-project-menu), [design
canvas](#CloudStudioUserInterface-design-canvas), and a [component
palette](#CloudStudioUserInterface-component-palette), as well as the
[configuration screens](#CloudStudioUserInterface-configuration-screens)
for each component, such as those for transformations, scripts,
connections, and activities.

On opening a project, these parts of the project designer are displayed:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project/project-designer_annotated_pp.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project/project-designer_annotated_pp.png" /></span>

### <span id="CloudStudioUserInterface-project-toolbar" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Project Toolbar

The [project toolbar](https://success.jitterbit.com/display/CS/Project+Toolbar) is the bar below the
Harmony Portal header where you can access project actions, see project
information, and navigate to recent projects:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-toolbar/project-toolbar_annotated.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-toolbar/project-toolbar_annotated.png" /></span>

The project toolbar persists on all screens as you use Cloud Studio to
access an individual project.

### <span id="CloudStudioUserInterface-project-menu" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Project Pane

The [project pane](https://success.jitterbit.com/display/CS/Project+Pane) is the panel on the left
when you open a project where you can view and manage workflows and
project components. The project pane has two views, accessed by tabs
along the top:

-   **Workflows:** This tab focuses on individual workflows,
    their operations, and the steps used to execute those operations
    (see [Project Pane Workflows
    Tab](https://success.jitterbit.com/display/CS/Project+Pane+Workflows+Tab)).
-   **Components:** This tab shows all project components and identifies
    whether they are used in support of an operation (see [Project Pane
    Components Tab](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab)).

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:33%;min-width:33%;max-width:33%;" hasbody="true"
macro-name="column">

#### Workflows

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/workflows/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/workflows/overview.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:33%;min-width:33%;max-width:33%;" hasbody="true"
macro-name="column">

#### Components

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/project-pane/components/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/project-pane/components/overview.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:33%;min-width:33%;max-width:33%;" hasbody="true"
macro-name="column">



</div>

</div>

</div>

</div>

### <span id="CloudStudioUserInterface-design-canvas" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Design Canvas

The [design canvas](https://success.jitterbit.com/display/CS/Design+Canvas) is the central area when
you open a project that serves as the primary workspace where you
visually design integrations. Within the design canvas, you can create
multiple workflows, accessed in tabs along the top of the design canvas.
You then design workflows within the canvas by creating an
linking operations using the tools provided in the component
palette, project pane, and design canvas itself.

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_script.png" /></span>

### <span id="CloudStudioUserInterface-component-palette" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Component Palette

The two types of [component palettes](https://success.jitterbit.com/display/CS/Component+Palette)
each provide access to components that can be used within the project:

-   **[Design Component
    Palette](https://success.jitterbit.com/display/CS/Design+Component+Palette):** The design
    component palette is the collapsible panel on the right when you
    open a project that provides access to project components that can
    be used on the design canvas. Within the **Connectivity** tab of the
    design palette, connectors are first configured to
    create connections. Activity types associated with those connections
    are then available for creating instances of an activity in a
    project.
-   **[Script Component
    Palette](https://success.jitterbit.com/display/CS/Script+Component+Palette):** The script
    component palette is the collapsible panel on the right of the
    script and script mode transformation configuration screens that
    provides access to project components that can be used
    within scripts. Each component within the **Source
    Objects** (present only
    for transformations), **Functions**, **Variables**, **Plugins**, **Operations**, **Notifications**, **Scripts**,
    and **Endpoints** tabs can be used in a script.

<div class="sectionColumnWrapper conf-macro output-block" hasbody="true"
macro-name="section">

<div class="sectionMacro">

<div class="sectionMacroRow">

<div class="columnMacro conf-macro output-block"
style="width:50%;min-width:50%;max-width:50%;" hasbody="true"
macro-name="column">

#### Design Component Palette

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_http_activities.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/all_http_activities.png" /></span>

</div>

<div class="columnMacro conf-macro output-block"
style="width:50%;min-width:50%;max-width:50%;" hasbody="true"
macro-name="column">

#### Script Component Palette

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/component-palette/source-objects_items.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/component-palette/source-objects_items.png" /></span>

</div>

</div>

</div>

</div>

### <span id="CloudStudioUserInterface-configuration-screens" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Configuration Screens

Many types of project components and other areas of the user interface
require configuration with user-provided input.

The interface where you provide this input is often referred to as the
configuration screen or editor for the specific type of component or
area of configuration.

Activities and connections are typically referred to as having activity
configuration screens and connection configuration screens,
respectively. Here are some additional examples of how the configuration
screen for other components may be referred to:

-   If you add a script to an operation, you would then configure the
    script using the script configuration screen, which is also called
    the script editor.
-   After creating a transformation, you may define a schema manually,
    using the file schema editor.
-   You may later add a schedule to an operation, which you configure
    from the schedule configuration screen or schedule editor.

In this section, the File Share Read activity is used as an example to
illustrate a typical activity configuration screen. The transformation
configuration screen is unique in that it can be accessed in several
display modes: [Mapping Mode](https://success.jitterbit.com/display/CS/Mapping+Mode), [Script
Mode](https://success.jitterbit.com/display/CS/Script+Mode), or [Preview
Mode](https://success.jitterbit.com/display/CS/Preview+Mode), as covered below.

#### Activity Configuration Screen Example

Component configuration screens are unique to each type of component. As
an example, after creating an instance of a File Share activity, you
open its activity configuration screen and provide information such as
the files you want to interact with and optional file schemas. Some
editors may be made up of multiple steps, requiring the user to step
through the configuration, such the File Share activity editor:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_variable.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_variable.png" /></span>

<div
class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
hasbody="true" macro-name="tip">

<span
class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**TIP:** If you are experiencing issues with names and passwords
auto-populating in configuration fields, try adjusting your browser
settings (by clearing the cache and disabling autofill) or disabling any
password managers. 

</div>

</div>

At the top of each activity configuration screen is a link to the
configuration of the connection with which the activity is associated.
To navigate to the connection configuration, click the name of the
associated connection:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_activity_link.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_activity_link.png" /></span>

Many screens also include the name the component you are configuring.
Depending on the component you are configuring, the displayed name may
automatically update based on the user-provided name for the component
or associated operation. For other components, such as activities, the
name may be static and indicate a specific type of component, such as
Read for a File Share Read activity:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_title.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_title.png" /></span>

On screens that have multiple configuration steps, the step numbers are
displayed, with the current step number enlarged with a dark background:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_step-1_steps.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_step-1_steps.png" /></span>

Once a step is configured, you can navigate to that step by clicking the
step number. Steps that are navigable show an orange background when you
hover over them and are clickable:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_step-3_steps.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_step-3_steps.png" /></span>

On initial creation, steps must be configured in sequence to fully
configure and save the component using the **Finished** button on the
last step.

On initial creation and subsequent editing, you can navigate back to any
configured step using the step number or the **Back** link at the bottom
of each configuration screen. However, making changes to a configuration
of a previous step requires you to reconfigure or acknowledge each step
in sequence again.

Steps that must be configured or reconfigured must be accessed using the
**Next** button at the bottom of each configuration screen.

The full configuration of a component is saved or discarded on exiting
the configuration screen.

The **Next** button and other buttons and links shown at the bottom of
the screen are covered in the documentation of each component.

Many configuration screens have a close icon in the upper right that is
used to close out of the configuration screen:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/common/icons/close_2.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/close_2.png" /></span>

When using this method of closing a configuration screen, user input is
not saved on configuration screens that use buttons to manually save
input, as is the case with activity configuration screens. Other types
of configuration screens, such as those for scripts and transformations,
use auto-save, as indicated by the save status being listed along the
top of the screen. For more information about manual save and auto-save,
see
[Saving](https://success.jitterbit.com/display/CS/Cloud+Studio+Permissions%2C+Collaboration%2C+and+Saving#CloudStudioPermissions,Collaboration,andSaving-save-changes)
in [Cloud Studio Permissions, Collaboration, and
Saving](https://success.jitterbit.com/display/CS/Cloud+Studio+Permissions%2C+Collaboration%2C+and+Saving).

After closing a configured component that uses steps, when you reopen
the component you are brought to the last step of configuration. The
last step is often a review step, which enables you to review the
existing configuration without needing to resubmit the configurations
made in previous steps.

Within each configuration screen, required fields are indicated by a red
asterisk following the field name:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_required.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_required.png" /></span>

The absence of the red asterisk indicates the field is optional and is
not required to be filled out.

Depending on the field type, a field can be completed in different ways,
including by selecting a radio button, using a dropdown, or entering
input.

Fields that show a variable icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/variable.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/variable.png"
height="16" /></span> support using [global
variables](https://success.jitterbit.com/display/CS/Global+Variables), [project
variables](https://success.jitterbit.com/display/CS/Project+Variables), or [Jitterbit
variables](https://success.jitterbit.com/display/CS/Jitterbit+Variables). Begin typing an open square
bracket `[` into the field or click the variable icon <span
class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/variable.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/common/icons/variable.png"
height="16" /></span> to display existing variables to choose from. Once
inserted, variables are displayed in a pill format in line with other
text input, if present:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/file-share_read_variable-field.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/file-share_read_variable-field.png" /></span>

#### <span id="CloudStudioUserInterface-mapping-mode" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Mapping Mode

[Mapping mode](https://success.jitterbit.com/display/CS/Mapping+Mode) provides an overview of the
mapping and the basic tools to perform the mapping:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/overview.png" /></span>

#### <span id="CloudStudioUserInterface-script-mode" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Script Mode

[Script mode](https://success.jitterbit.com/display/CS/Script+Mode) provides detailed views of fields
and advanced tools for adding scripts to the mapping:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/script-mode/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/script-mode/overview.png" /></span>

#### <span id="CloudStudioUserInterface-preview-mode" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Preview Mode

[Preview mode](https://success.jitterbit.com/display/CS/Preview+Mode) allows you to use sample data
to test how the transformation will process the data:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/preview-mode/overview.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/preview-mode/overview.png" /></span>
