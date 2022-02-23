[//]: # (Module 2 - Database to Complex XML)

## Introduction

Module 2 in the [Introduction to the Jitterbit Harmony Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio)
training course demonstrates querying data from multiple tables in a
PostgreSQL database and writing it to an SFTP server in a hierarchical
XML format.


## Prerequisites

This page assumes you have completed [Module 1 - Database to
Text](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text), where you configured
connections to Jitterbit's training PostgreSQL database and SFTP server.


## Summary

In this module, you will use the PostgreSQL database to connect to the
`OrderDetail` and `OrderHeader` tables. Once connected, you'll merge
that data and write it in a hierarchical format to the training SFTP
server.

The completed operation will look like this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_db-to-xml.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_db-to-xml.png" /></span>

This operation uses this transformation mapping:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-xml.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-xml.png" /></span>


## 1. Configure a Database Activity

For this module, you continue working within the same project and reuse
the same "Postgres Database" connection as in Module 1, but configure a
separate Query activity to retrieve different data from the database:

1.  Within the same project as Module 1, create a new workflow and name
    it "Module 2."

2.  From the component palette's **Connectivity** tab under the
    **Endpoints** filter, click the "Postgres Database" connection you
    created in Module 1 to show the connection's activity types:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png" /></span>

3.  Drag a Database Query activity type to the component drop zone on
    the design canvas to create an instance of a Database Query activity
    in a new operation.

4.  Rename the operation to "DB to XML."

5.  Double-click the Query activity within the operation to open its
    configuration.

6.  Configure the [Database Query
    activity](https://success.jitterbit.com/display/CS/Database+Query+Activity):  

    -   **Name:** "Query Order Header & Order Detail Tables"

    -   **Select Table(s):** Refresh the tables and select the
        `OrderDetail` and `OrderHeader` tables. Then within the
        `OrderDetail` row:

        -   **Parent:** Use the dropdown to select `OrderHeader`.

        -   **Link Keys:** Click **Assign**. In the popup, drag
            `OrderID` in the parent table to `OrderID` in the child
            table. Click **Finished**.

        -   **Join Type:** This field becomes available after assigning
            link keys. Use the dropdown to select **Zero or More**.
            Click **Next**.

    -   **Source: PostgreSQL:** Select the checkbox next to
        `OrderHeader` to include all fields in the query.

    -   **Data Schema:** Review the data schema and click **Finished**
        to return to the design canvas.

The final screen of activity configuration should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_order.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_order.png" /></span>


## 2. Configure an FTP Activity

In addition to reusing the Database connection, you can also reuse the
FTP connection from Module 1. In this step, you use the same connection
to the SFTP training server, but configure a separate Write activity:

1.  From the component palette's **Connectivity** tab under the
    **Endpoints** filter, click the "SFTP" connection you created in
    Module 1 to show the connection's activity types:  

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png" /></span>

2.  Drag an FTP Write activity type to a component drop zone on the
    right of the Database Query activity within the operation on the
    design canvas.

3.  Double-click the FTP Write activity within the operation to open its
    configuration.

4.  Configure the [FTP Write
    activity](https://success.jitterbit.com/display/CS/FTP+Write+Activity):  

    -   **Name:** "XML SFTP"

    -   **Path:** "/" (forward slash)

    -   **Filename(s):** "result\_\[date\]\_\[time\].xml". Click
        **Next**.

    -   **Data Schema:** Since you didn't provide a schema, there is
        nothing to review in the second screen. Click **Finished**.


## 3. Configure a Transformation

Next, you create a transformation to transform data from the database
source to the FTP target:

1.  On the design canvas, hover over the area between the Database Query
    activity and the FTP Write activity until a component drop zone
    appears.

2.  Click the drop zone and select **New Transformation**. A new
    transformation will open for you to configure:

    -   **Transformation Name:** "DB to XML"

    -   **Source:** The source schema is already provided (on the left).

    -   **Target:** You need to define the target schema (on the right).
        Click **Mirror Source Schema** to replicate the database
        structure in XML.

3.  Drag the `OrderHeader` source node to the `row` target node and
    select **Automap**.

    <div
    class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
    hasbody="true" macro-name="tip">

    <span
    class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **TIP:** The solid black lines that are displayed between the source
    and target nodes are called *iterator lines*. These lines indicate
    that the mapping supports multiple records (instances).

    </div>

    </div>

4.  Along the top of the transformation header, click the gray
    **Preview** button to begin the preview process for testing and
    validating the mappings. Click **Next** to deploy the components
    listed and then click **Finished**.

5.  The preview screen displays data populated from the source and
    mapped to the target. Click the right and left arrows to cycle
    through the imported data.

6.  After reviewing the data, click **Return to Workflow**. Clicking
    this button saves the work you did in the transformation.

The transformation preview should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-xml.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-xml.png" /></span>


## 4. Deploy and Run the Operation

Finally, with all operation steps configured, you deploy and run the
operation:

1.  In the top right of the operation, click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> and from the menu click **Deploy and
    Run**. The operation status is displayed in the lower left of the
    operation.

2.  Once the operation is successful, log in
    to <a href="https://learningsandbox.jitterbit.com/WebInterface/login.html"
    class="external-link" rel="nofollow">Jitterbit's training SFTP
    server</a> and view the file you generated.
