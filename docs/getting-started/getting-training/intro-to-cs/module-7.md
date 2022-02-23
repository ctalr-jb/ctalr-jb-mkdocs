[//]: # (Module 7 - Creating an Email Notification)

## Introduction

Module 7 in the [Introduction to the Jitterbit Harmony Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio)
training course demonstrates creating a an email notification that
triggers upon failure of an operation.


## Prerequisites

The operation created in [Module 1 - Database to
Text](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text) is used as an
example. However, an email notification may be configured on any
operation.


## Summary

In this module, you will add an email notification to the operation
created in [Module 1 - Database to
Text](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text).

The completed operation will look like this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_db-to-text.png" /></span>


## 1. Create and Add an Email Notification to an Operation

For this module, you continue working within the same workflow as Module
1 and add an email notification to the operation:

1.  In the top right of the operation, click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> and from the menu select **Settings**.

2.  Within the **Actions** tab, use the **Action** dropdown to select
    "Send Email Notification," then click **Create New Email
    Notification**.

3.  Configure the [email notification](https://success.jitterbit.com/display/CS/Email+Notifications):

    -   **Email Notification Name:** "Operation Failure"

    -   **SMTP Email Server(s):** Enter your own SMTP mail server.

        <div
        class="confluence-information-macro confluence-information-macro-information conf-macro output-block"
        hasbody="true" macro-name="info">

        <span
        class="aui-icon aui-icon-small aui-iconfont-info confluence-information-macro-icon">
        </span>
        <div class="confluence-information-macro-body">

        **NOTE:** If you're not familiar with this information, please
        reach out to your organization's internal administrator for
        details.

        </div>

        </div>

    -   **To Email Address(es):** Enter any email addresses, separated
        by a comma, that you want the email to be sent to.

    -   **From Email Address:** Enter the email address that you want
        the email to be sent from.

    -   **Subject:** Enter "`[jitterbit.operation.name] Failure`" to
        leverage a Jitterbit variable that dynamically reports a failed
        operation's name.

    -   **Message:** Enter the following message, again using Jitterbit
        variables that dynamically report information on the operation
        name and the specific error:

        > There's been an operation failure within:  
        > \[jitterbit.operation.name\]
        >   
        > The error was:  
        > \[jitterbit.operation.error\]
        >   
        > Please check the logs within Cloud Studio or Management
        > Console for further details.

4.  Click **Save** to return to the **Actions** tab and configure the
    [operation action](https://success.jitterbit.com/display/CS/Operation+Actions):

    -   Make these dropdown selections:

        -   **Condition:** "On Fail"
        -   **Action:** "Send Email Notification"

        -   **Email Notification:** "Operation Failure"

    -   Click **Add Action**. The email notification will be shown in a
        table at the bottom of the configuration. Then close the
        operation settings.

The email notification should have a configuration similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/notification/email_operation-failure.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/notification/email_operation-failure.png" /></span>

The failure notification is graphically depicted on the design canvas:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_chain_db-to-text.png" /></span>


## 2. Deploy the Operation

Next, you re-deploy the operation so that the configured operation
action will take effect:

1.  In the top right of the operation, click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> and from the menu click **Deploy**. If the
    operation runs and fails, the email notification will be sent.

## 3. Remove or Edit an Email Notification

You can also remove the email notification as an operation action:

1.  On the design canvas, click the email notification and from the menu
    select **View/Edit** to reopen the notification configuration, or
    select **Remove** to remove the notification from the operation.
