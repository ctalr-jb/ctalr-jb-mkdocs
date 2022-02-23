[//]: # (Jitterbit Harmony Permissions and Access)

## Introduction

Access to different areas within Jitterbit Harmony is based on a
combination of organization role permissions and environment access
levels. This page provides definitions of Jitterbit Harmony terms
related to permissions and access levels and provides a matrix to
determine what areas a member can access.


## Jitterbit Harmony Administrative Terminology

Organization administrators should be familiar with these Jitterbit
Harmony terms for organizations and environments:

-   **Organizations**

    -   **Organization:** A unique Jitterbit Harmony organization in
        which administrators have full control over membership and
        security. Settings made at the organization level (on the
        [Organizations](https://success.jitterbit.com/display/DOC/Organizations) page) are subject to
        and can be further defined at the environment level (on
        the [Environments](https://success.jitterbit.com/display/DOC/Environments) page). An
        organization may also be referred to as an org.

    -   **Member:** A Jitterbit Harmony user who has been added to an
        organization by an administrator (described under
        [Members](https://success.jitterbit.com/display/DOC/Organizations#Organizations-members) in [Organizations](https://success.jitterbit.com/display/DOC/Organizations)).

    -   **Administrator:** A member who is assigned to a role with
        *Admin* permission at the organization level, allowing access to
        all features and functions available in the [Management
        Console](https://success.jitterbit.com/display/DOC/Management+Console).

    -   **Role:** A group of members that is assigned one or more
        permissions at the organization level. Initially, when a
        Jitterbit Harmony organization is created, an *Administrator*
        role (with *Admin* permission) and a *User* role (with *Read*
        permission) are created by default. Administrators can create
        additional roles and add members to multiple roles (described
        under
        [Roles](https://success.jitterbit.com/display/DOC/Organizations#Organizations-roles) in [Organizations](https://success.jitterbit.com/display/DOC/Organizations)).

    -   **Permissions:** Permissions are assigned to a role at the
        organization level and limit an organization member's access to
        defined areas of an organization. Permissions include *Read*,
        *Admin*, *Agent Install*, and *ApiConsumer* (defined under
        [Permissions](https://success.jitterbit.com/display/DOC/Organizations#Organizations-permissions) in [Organizations](https://success.jitterbit.com/display/DOC/Organizations)).

-   **Environments**

    -    **Environment:** An environment is set up within an
        organization and is used to segregate different states of an
        integration project and its assets. For example, an organization
        might have three environments: *Development*, *Test*, and
        *Production*.

    -   **Access Levels:** Access levels are assigned to a role that has
        been granted access to an environment. They are used in
        combination with organization permissions to further the ability
        of administrators to control what members of a specific role can
        do in a specific environment. Access levels include *View Logs*,
        *Read*, *Execute*, and *Write* (defined under [Access
        Levels](https://success.jitterbit.com/display/DOC/Environments#Environments-access-levels) in
        [Environments](https://success.jitterbit.com/display/DOC/Environments)).

The areas that a Jitterbit Harmony member can access depend on the
combination of their organization role permissions and environment
access levels. Permissions and access levels are set independently and
are different from each other. For example:

-   A member of a role with *Read* permission at the organization level
    may still be able to make edits in an environment if *Write* access
    is granted to the role at the environment level.

-   A member of a role with *Admin* permission at the organization level
    but whose role has only *Read* access at the environment level is
    not able to deploy, execute, or edit projects in that environment.

-   A member of a role with *Admin* permission at the organization level
    but whose role has not been granted environment access is not able
    to access the environment at all.

-   A member of a role with *Read* permission at the organization level
    and whose role has been granted *Read* access in Environment A and
    *Write* access in Environment B is able to migrate a project from
    Environment A to Environment B.

In order to access an environment, roles (even roles with *Admin*
permission) must be granted access to an environment. This includes
being able to access areas of Jitterbit Harmony applications that
require an environment to be selected and being able to install [Private
Agents](https://success.jitterbit.com/display/DOC/Private+Agents) in an environment.
