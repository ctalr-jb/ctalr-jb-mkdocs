[//]: # (Jitterbit Security)

## Overview

Jitterbit Harmony delivers powerful integration tools and services
through Jitterbit’s multi-tenant cloud integration platform, called
Jitterbit Harmony. Previous versions of Jitterbit required organizations
to deploy and manage Jitterbit software and integration projects on
internal network infrastructure or dedicated private clouds. With
Harmony, Jitterbit can now assume any or all of these responsibilities.

These pages are included in this topic:

-   **[Jitterbit Security and Architecture White
    Paper](https://success.jitterbit.com/display/DOC/Jitterbit+Security+and+Architecture+White+Paper)**<br>
    Review the details of Jitterbit's logical, physical, and
    organization security.

-   **[Jitterbit Security
    Features](https://success.jitterbit.com/display/DOC/Jitterbit+Security+Features)**<br>
    See a summary of security features for the Jitterbit Harmony
    cloud, data centers, and network.

-   **[Jitterbit Password
    Controls](https://success.jitterbit.com/display/DOC/Jitterbit+Password+Controls)**<br>
    Learn about how Jitterbit controls access to your organization via
    administration through the Management Console.

-   **[Jitterbit Harmony Permissions and
    Access](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Permissions+and+Access)**  
    Use a matrix of organization
    role permissions and environment access levels to determine what
    areas of Jitterbit Harmony a member can access.

-   **[Whitelist Information](https://success.jitterbit.com/display/DOC/Whitelist+Information)**  
    Find out how to use whitelisting with [Agents](https://success.jitterbit.com/display/DOC/Agents)
    and [Design Studio](https://success.jitterbit.com/display/DOC/Design+Studio).

-   **[ISO 27001 and ISO 27017
    Certification](https://success.jitterbit.com/display/DOC/ISO+27001+and+ISO+27017+Certification)**
    Read about the ISO certification of Jitterbit's Information Security
    Management System.
    
-   **[Security Best Practices for Administrators, Project Builders, and
    Integration
    Specialists](https://success.jitterbit.com/display/DOC/Security+Best+Practices+for+Administrators%2C+Project+Builders%2C+and+Integration+Specialists)**  
    See recommendations and the best practices for security.

These additional resources related to security are also available:

-   **<a href="https://www.jitterbit.com/privacy-policy/"
    class="external-link" rel="nofollow">Jitterbit Privacy Policy</a>**<br>
    Gain awareness of what personal data Jitterbit collects and
    how it is used.

-   **<a href="https://trust.jitterbit.com/" class="external-link"
    rel="nofollow">Jitterbit Trust Site</a>**<br>
    Check real-time information on Jitterbit system performance through
    our <a href="https://trust.jitterbit.com/" class="external-link"
    rel="nofollow">Trust site</a>. You can also [subscribe to
    updates](https://success.jitterbit.com/display/DOC/System+Status+Notifications) to receive
    notifications by email, text, or webhook.

-   **[Harmony API Security](https://success.jitterbit.com/display/DOC/Harmony+API+Security)**<br>
    Learn to apply various levels of security for use with Jitterbit's
    Harmony API platform.

## Frequently Asked Questions

**Q:** *What auditing is in place for the Jitterbit Harmony Portal?*

**A:** Deployment audit is available. Jitterbit has an extremely robust
logging mechanism that exposes everything along the integration path.
These logs can be freely inspected by authorized users or used by a
Jitterbit operation to highlight what is of interest.
<br>
<br>

**Q:** *Do you provide message encryption?*

**A:** Yes, two-way SSL support is provided by Jitterbit. Jitterbit also
provides AES support. Additionally, Jitterbit has a PGP encryption
plugin that can be used to encrypt messages.
<br>
<br>

**Q:** *Is transport-level security with certificate validation supported?*

**A:** Yes. This can be done via SSL.
<br>
<br>

**Q:** *Can user authentication be performed using domain authorization,
or must it be through the internal user database?*

**A:** Jitterbit does provide domain authorization for file
source/target and for database access. User authentication can be made
via domain auth to access database endpoints. Domain auth cannot be used
to access Jitterbit Private Agents. It is possible to do an LDAP
transformation to disable users, but the password cannot be set from the
operation if it is a “create” (we use our private key).
<br>
<br>

**Q:** *What password controls are in place?*

**A:** Passwords for Jitterbit Harmony are controlled within the
**Organizations** page of the Management Console. The password control
features are set for each individual organization separately. Only an
Administrator for the organization has access to revise the password
controls. See [Organizations](https://success.jitterbit.com/display/DOC/Organizations) for specific
details on password controls.

<div
class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
hasbody="true" macro-name="info">

<span
class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
</span>

<div class="confluence-information-macro-body">

**NOTE:** Password controls for organizations using [single
sign-on](https://success.jitterbit.com/display/DOC/Single+Sign-On) are managed through the Identity
Provider.

</div>

</div>
