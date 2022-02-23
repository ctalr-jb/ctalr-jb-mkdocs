[//]: # (Module 6 - Creating a Schedule)

## Introduction

Module 6 in the [Introduction to the Jitterbit Harmony Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio)
training course demonstrates creating a custom schedule to run the
operation automatically on that schedule.


## Prerequisites

The operation created in [Module 5 - RESTful Web
Service](https://success.jitterbit.com/display/DOC/Module+5+-+RESTful+Web+Service) is used as an
example. However, a schedule may be applied on any operation.


## Summary

In this module, you will add a schedule to the operation created in
[Module 5 - RESTful Web
Service](https://success.jitterbit.com/display/DOC/Module+5+-+RESTful+Web+Service).

The completed operation will look like this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest_schedule.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest_schedule.png" /></span>


## 1. Create and Assign a Schedule

For this module, you continue working within the same workflow as Module
5 and add a schedule to the operation:

1.  In the top right of the operation, click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> and from the menu select **Settings**.

2.  Within the **Schedules** tab, click **Create New Schedule**.

3.  Configure the [operation schedule](https://success.jitterbit.com/display/CS/Operation+Schedules):
    -   **Name:** "Monthly"

    -   **Occurrence:** Select **Monthly**, then select the second radio
        button and configure the schedule for the **4th** **Sunday** of
        every **1** month.

    -   **Frequency:** Select **Occurs once at** and **01:00 AM**. Click
        **Save**.

4.  Within the **Schedules** tab, use the first dropdown to select **On
    Schedule**. Under **Available Schedule**, select the "Monthly"
    schedule you just created. Click **Assign**. Then close the
    operation settings.

The schedule should have a configuration similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/operation/schedule_monthly.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/operation/schedule_monthly.png" /></span>

When a schedule is assigned to an operation, a schedule icon appears in
the top right of the operation:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest_schedule.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest_schedule.png" /></span>


## 2. Deploy the Operation

Next, you re-deploy the operation so that the assigned schedule will
take effect:

1.  In the top right of the operation, click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> and from the menu click **Deploy**. The
    operation will now run on the assigned schedule.


## 3. Remove or Edit a Schedule

You can also remove or edit the schedule:

1.  In the top right of the operation, click the schedule icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/schedules.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/schedules.png"
    height="25" /></span>.
    
2.  Under **Assigned Schedule**, click the edit icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/edit_3.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/edit_3.png"
    height="14" /></span> to reopen the schedule configuration or click
    the remove icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/delete_3.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/delete_3.png"
    height="12" /></span> to unassign the schedule from the operation.

3.  After making changes or removing a schedule, remember to redeploy
    for the changes to take effect.

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

<span style="color: rgb(192,192,192);"> </span>
