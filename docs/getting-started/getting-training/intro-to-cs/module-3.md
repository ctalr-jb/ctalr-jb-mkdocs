[//]: # (Module 3 - XML to Database)

## Introduction

Module 3 in the [Introduction to the Jitterbit Harmony Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio)
training course demonstrates reading XML data from an SFTP server and
upserting it to a PostgreSQL database.


## Prerequisites

This page assumes you have completed [Module 1 - Database to
Text](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text), where you configured
connections to Jitterbit's training PostgreSQL database and SFTP server.


## Summary

In this module, you will connect to the training SFTP server to pull
records from the `customer.xml` file and add them to the `customer`
table on the PostgreSQL database.

The completed operation will look like this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_xml-to-db.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_xml-to-db.png" /></span>

This operation uses this transformation mapping:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/xml-to-db.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/xml-to-db.png" /></span>


## 1. Download an XML Schema

First, download an XML file to provide as a schema in a later step:

1.  Log in
    to <a href="https://learningsandbox.jitterbit.com/WebInterface/login.html"
    class="external-link" rel="nofollow">Jitterbit's training SFTP
    server</a>.

2.  In the `DataSets` \> `Customer` directory, download the
    `customer.xml` file.


## 2. Configure an FTP Activity

For this module, you continue working within the same project and reuse
the same SFTP server connection as in Module 1, but configure a separate
FTP Read activity to pull the XML data from the server:

1.  Within the same project as Module 1, create a new workflow and name
    it "Module 3."

2.  From the component palette's **Connectivity** tab under the
    **Endpoints** filter, click the "SFTP" connection you created in
    Module 1 to show the connection's activity types:  

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png" /></span>

3.  Drag an FTP Read activity type to the component drop zone on the
    design canvas to create an instance of an FTP Read activity in a new
    operation.

4.  Rename the operation to "XML to DB."

5.  Double-click the FTP Read activity within the operation to open its
    configuration.

6.  Configure the [FTP Read activity](https://success.jitterbit.com/display/CS/FTP+Read+Activity):  

    -   **Name:** "XML SFTP"

    -   **Provide Response Schema:** Select **Yes, Provide New Schema**
        and click **Upload File** to browse to and upload the
        `customer.xml` file you downloaded from the training SFTP
        server.

    -   **Path:** Provide the path to the `customer.xml` file on the
        training SFTP server: "/DataSets/Customer"

    -   **Get Files:** "\*.xml". Click **Next**.

    -   **Data Schema:** Review the data schema and click **Finished**
        to return to the design canvas.

The final screen of activity configuration should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/ftp_read_step-2_data-schema.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/ftp_read_step-2_data-schema.png" /></span>


## 3. Configure a Database Activity

In this step, you use the same connection to the PostgreSQL database as
in Module 1, but configure a separate Upsert activity:

1.  From the component palette's **Connectivity** tab under the
    **Endpoints** filter, click the "Postgres Database" connection you
    created in Module 1 to show the connection's activity types:  

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png" /></span>

2.  Drag a Database Upsert activity to a component drop zone on the
    right of the FTP Read activity within the operation on the design
    canvas.

3.  Double-click the Database Upsert activity within the operation to
    open its configuration.

4.  Configure the [Database Upsert
    activity](https://success.jitterbit.com/display/CS/Database+Update+or+Upsert+Activity):  

    -   **Name:** "Upsert to Postgres DB"

    -   **Provide the Table Names Reference:** Refresh the tables and
        select the customer table. Click **Next**.

    -   **Select Update Keys:** Clear the `id` (Key) field, and select
        the `company` field. Click **Next**.

    -   **Data Schema:** Review the data schema and click **Finished**
        to return to the design canvas.

The final screen of activity configuration should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_customer.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_customer.png" /></span>


## 4. Configure a Transformation

Next, you create a transformation to transform data from the FTP source
to the database target:

1.  On the design canvas, hover over the area between the FTP Read
    activity and the Database Upsert activity until a component drop
    zone appears.

2.  Click the drop zone and select **New Transformation**. A new
    transformation will open for you to configure:

    -   **Transformation Name:** "XML to DB"

    -   **Source:** The source schema is already provided (on the left).

    -   **Target:** The target schema is already provided (on the
        right).

3.  Drag the `customer` source node to the `customer` target node and
    select **Automap**.

4.  Along the top of the transformation header, click the gray
    **Preview** button to begin the preview process for testing and
    validating the mappings. Click **Next** to deploy the components
    listed. On the next screen, select **Upload New File to Test** and
    provide the `customer.xml` file that you downloaded earlier.
    Click **Finished**.

5.  The preview screen displays data populated from the source and
    mapped to the target. Click the right and left arrows to cycle
    through the imported data.

6.  After reviewing the data, click **Return to Workflow**. Clicking
    this button saves the work you did in the transformation.

The transformation preview should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/preview-mode/xml-to-db.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/preview-mode/xml-to-db.png" /></span>


## 5. Deploy and Run the Operation

Finally, with all operation steps configured, you deploy and run the
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
    to <a href="https://training.jitterbit.com/DB/dbViewer.php"
    class="external-link" rel="nofollow">Jitterbit's PostgreSQL database</a> and
    view the additional records in the customer table.
