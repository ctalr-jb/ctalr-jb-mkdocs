[//]: # (Cloud Studio Permissions, Collaboration, and Saving)

## Introduction

This page provides basic information about working with Cloud Studio, including what access is granted by various
permissions, how collaboration works when editing projects simultaneously with other users, and how saving works.


## Project Permissions

Access to projects is restricted based on the combination of organization role permissions and environment access
levels as defined through the [Management Console](https://success.jitterbit.com/display/DOC/Management+Console). Organization role permissions
are set through the [Organizations](https://success.jitterbit.com/display/DOC/Organizations) page, while environment access levels are set
through the [Environments](https://success.jitterbit.com/display/DOC/Environments) page.

A user must be a member of an organization role with either *Read* or *Admin* permission in order to access Cloud
Studio. Both the *Read* and *Admin* permissions provide the same privileges within the Cloud Studio application. As
projects must be created within an environment, the areas of Cloud Studio that these members can view or edit
depends on the access levels that the role is granted at the environment level.

### Permission and Access Level Matrix for Cloud Studio and Related Pages

The table below details the combination of organization role permissions and environment access levels that are
needed in order to access, edit, and perform actions in Cloud Studio and related pages. Note that the differences
afforded by the *Read* and *Admin* permissions are the ability to access and edit other Harmony Portal pages and
applications (see [Jitterbit Harmony Permissions and
Access](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access)).

In addition, the *View Logs* access level does not provide access to Cloud Studio but instead provides access to
Cloud Studio operation logs within the Management Console.

<table class="relative-table wrapped confluenceTable"
style="width: 80.2568%;">
<colgroup>
<col style="width: 10%" />
<col style="width: 89%" />
</colgroup>
<tbody>
<tr class="odd">
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Environment Access
Level</strong></p></td>
<td class="highlight-grey confluenceTd"
data-highlight-colour="grey"><p><strong>Organization Role Permission of
<em>Read</em> or <em>Admin</em></strong></p></td>
</tr>
<tr class="even">
<td class="highlight-blue confluenceTd"
data-highlight-colour="blue"><strong>View Logs</strong></td>
<td class="confluenceTd"><p>Access to:</p>
<ul>
<li>Management Console <a
href="/display/DOC/Activities">Activities</a> page to view logs for
Cloud Studio operations that have been deployed and executed within the
environment.</li>
</ul></td>
</tr>
<tr class="odd">
<td class="highlight-blue confluenceTd"
data-highlight-colour="blue"><strong>Read</strong></td>
<td class="confluenceTd"><p>Access to:</p>
<ul>
<li>All areas in Cloud Studio. For example:<br />
<ul>
<li>View the list of projects from the project index.</li>
<li>Open projects to view within the project designer.</li>
<li>View project and component configuration screens (for example,
connection/activity, transformation, script).</li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td class="highlight-blue confluenceTd"
data-highlight-colour="blue"><strong>Execute</strong></td>
<td class="confluenceTd"><p>Ability to perform these actions:</p>
<ul>
<li>Execute Cloud Studio operations that have already been deployed (see
<a
href="/display/CS/Operation+Deployment+and+Execution#OperationDeploymentandExecution-manually">Executing
Manually</a> under <a
href="/display/CS/Operation+Deployment+and+Execution">Operation
Deployment and Execution</a>).</li>
<li>Actions in Design Studio (see <a
href="/display/DOC/Jitterbit+Harmony+Permissions+and+Access">Jitterbit
Harmony Permissions and Access</a>).</li>
</ul>
<p>Access to:</p>
<ul>
<li>All areas in Cloud Studio that are provided by the <em>Read</em>
access level.</li>
</ul></td>
</tr>
<tr class="odd">
<td class="highlight-blue confluenceTd"
data-highlight-colour="blue"><strong>Write</strong></td>
<td class="confluenceTd"><p><span>Access to and the ability to make
edits and perform all actions in Cloud Studio. For example:</span></p>
<ul>
<li>Open projects to view and edit within the project designer.</li>
<li>View and edit project and component configuration screens.</li>
<li>Create new workflows.</li>
<li>Add project components.</li>
<li>Deploy and migrate projects.</li>
</ul></td>
</tr>
</tbody>
</table>

### Troubleshooting

Users with only *Read* or *Execute* access in a specific environment are able to see the same options to perform
actions that are available to users with *Write* access. However, on attempting to perform such an action, an error
occurs, with text indicating the user is not permitted to perform the action.

If you receive an error message such as one of those shown below, contact an administrator of the Jitterbit Harmony
organization to ensure you are a member of the appropriate organization role and that your role has been granted the
appropriate access level in the environment (see [Jitterbit Harmony Permissions and
Access](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access)).

![](https://docs-source.jitterbit.com/cs/dialog/unable-to-import-project.png)

![](https://docs-source.jitterbit.com/cs/dialog/error-failed-to-authorize.png)


## <span id="CloudStudioPermissions,Collaboration,andSaving-collaboration" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Collaboration

Users who are a member of a role with *Write* access in an environment can edit integration projects concurrently
with other users — called project collaborators — as well as make edits to different parts of a project. Cloud
Studio automatically synchronizes workflows and components across multiple users.

### User Avatars

When multiple users have the same project open in the project designer, avatars of the other users are shown in the
[project toolbar](https://success.jitterbit.com/display/CS/Project+Toolbar).

### Automatic Synchronization

If a workflow is being edited by another user, those changes are reflected in real time on the design canvas. You
can also make workflow changes simultaneously, with your changes reflected in real time for other users. An audit
log of changes made by all users is provided in the [project history](https://success.jitterbit.com/display/CS/Project+History).

### Concurrent Editing

You may edit project components concurrently with other users, with any edits being autosaved and synchronized in
real time.

In the rare event that user A edits a component prior to receiving the latest changes from user B, user A's edit
will be rejected until the synchronization is completed. In this case, an error message indicates that a project
edit action conflicted with another user. Refresh the component to fetch the latest changes.

### Deployment

If edits by multiple project collaborators have not yet been deployed, all users' updates will be deployed when a
single user deploys.


## <span id="CloudStudioPermissions,Collaboration,andSaving-save-changes" class="confluence-anchor-link conf-macro output-inline" hasbody="false" macro-name="anchor"> </span>Saving

Changes you make to a project are either saved automatically with autosave, or saved manually with a command button
or keyboard shortcut on a configuration screen.

### Automatic Saving

While editing a project or project component, your changes are autosaved when you perform one of these actions:

-   Close a project component (transformation, script, etc.)

-   Close the project

-   Log out of the Harmony Portal

These include when the project or component is closed due to Harmony session timeout or navigating away from the
project.

In addition, some screens, such as the configuration screens for [scripts](https://success.jitterbit.com/display/CS/Scripts) and
[transformations](https://success.jitterbit.com/display/CS/Transformations), have an autosave component that applies only while that screen is
open.

### Manual Saving

Many configuration screens have explicit buttons that can be clicked to save an individual component configuration.
These buttons may be labeled in a variety of ways. For example: **Save Changes**, **Save & Exit**, **Finish**, or
**Finished**.

In addition, the script and transformation configuration screens support manual saving using `Control+S` (Windows or
Linux) or `Command+S` (macOS).

### Save Status

The save status on autosave screens is displayed along the top of each screen.

#### Design Canvas

The save status of a project is reflected within each workflow, on the far left of the design canvas header:

![](https://docs-source.jitterbit.com/cs/design-canvas/header.png)

#### Script

The save status for the script editor is displayed below the script name:

![](https://docs-source.jitterbit.com/cs/script/header.png)

#### Transformation

The save status for the transformation configuration screen is displayed to the right of the transformation name:

![](https://docs-source.jitterbit.com/cs/transformation/save-status_name_saved.png)

The presence of a red asterisk following the time indicates that the transformation has unsaved changes:

![](https://docs-source.jitterbit.com/cs/transformation/save-status_name_unsaved_annotated.png)
