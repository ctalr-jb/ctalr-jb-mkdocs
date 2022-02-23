[//]: # (Module 1 - Database to Text)

## Introduction

Module 1 in the [Introduction to the Jitterbit Harmony Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio)
training course demonstrates querying data from a single table in a
PostgreSQL database and writing it to an SFTP server as a flat text
file.


## Prerequisites

These modules assume you have registered for the Jitterbit Learning
Sandbox provided as part of the [Introduction to the Jitterbit Harmony
Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio)
training course. Registration for the Jitterbit Learning Sandbox
provides access to the Jitterbit Harmony training organization, complete
with two environments, as well as accounts on Jitterbit's training SFTP
server and PostgreSQL database.

If you do not have this access, see [Getting
Training](https://success.jitterbit.com/display/DOC/Getting+Training) to register for Jitterbit
University, then enroll in the [Introduction to the Jitterbit Harmony
Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio)
course. Learning Sandbox Registration is covered in Chapter 4 – Learning
Sandbox Registration.


## Summary

In this module, you will connect to the `customer` table from the
training PostgreSQL database, create a CSV file with similar fields, and
write that data to the training SFTP server.

The completed operation will look like this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_db-to-text.png" /></span> 

This operation uses this transformation mapping:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-text.png" /></span>


## 1. Create a New Project

All of the modules covered in this course are created in a single
project. Before beginning the first module, create a project:

1.  Log in to the [Jitterbit Harmony
    Portal](https://success.jitterbit.com/display/DOC/Jitterbit+Harmony+Portal) at
    <a href="https://login.jitterbit.com" class="external-link"
    rel="nofollow">https://login.jitterbit.com</a> and switch to the
    Jitterbit Learning Sandbox organization within the top right of the
    header.

2.  Click the Cloud Studio application card.

3.  From the project index, click **New Project**. Give the project a
    name, such as "Jitterbit University Examples," and select the
    environment.

4.  Once within the project, rename the workflow to "Module 1."

    <div
    class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
    hasbody="true" macro-name="tip">

    <span
    class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **TIP:** Adhering to an accepted naming convention within your
    organization for your workflows, operations, and components is a
    recommended best practice.

    </div>

    </div>


## 2. Configure a Database Connection

For this module, first you establish a connection to the PostgreSQL
training database:

1.  From the [design component
    palette](https://success.jitterbit.com/display/CS/Design+Component+Palette) **Connectivity** tab
    under the **Connectors** filter, click the Database connector:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_database.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_database.png" /></span>

2.  Configure the [Database
    connection](https://success.jitterbit.com/display/CS/Database+Connection):

    -   **Endpoint Name:** "Postgres Database"

    -   **Driver:** "PostgreSQL"

    -   **Server Name:**
        "<a href="http://learningsandbox.jitterbit.com" class="external-link"
        rel="nofollow">learningsandbox.jitterbit.com</a>"

    -   **Database Name**, **Login**, **Password:** These credentials
        are from the information you provided when completing the
        Learning Sandbox Registration form. This information can be
        found in the Learning Sandbox confirmation email.

    -   **Port:** No changes from defaults are needed.

    <div
    class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
    hasbody="true" macro-name="tip">

    <span
    class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **TIP:** Cloud Agents can use JDBC drivers only, while Private
    Agents can use JDBC or ODBC drivers.

    </div>

    </div>

3.  Click **Test** at the bottom of the configuration to verify
    connectivity.

4.  Once connected, click **Save Changes**. This returns you to the
    design canvas.

The "Postgres Database" connection should have a configuration similar
to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/database_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/database_connection.png" /></span>


## 3. Configure a Database Activity

Next, you configure an activity to query data from the PostgreSQL
database:

1.  From the component palette's **Connectivity** tab under the
    **Endpoints** filter, click the "Postgres Database" connection you
    have just created to show the connection's activity types:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_database_activities.png" /></span>

2.  Drag a Database Query activity type to the component drop zone on
    the design canvas to create an instance of a Database Query activity
    in a new operation.

3.  Rename the operation to "DB to Text."

4.  Double-click the Query activity within the operation to open its
    configuration.

5.  Configure the [Database Query
    activity](https://success.jitterbit.com/display/CS/Database+Query+Activity):  

    -   **Name:** "Query Customer Table"

    -   **Select Table(s):** Refresh the tables and select the
        `customer` table. Click **Next**.

    -   **Select Fields:** Select the `id` (Key), `company`, `address`,
        `city`, `state`, `zip`, `country`, `phone`, and `fax` fields.
        Click **Next**.

    -   **Data Schema:** Review the data schema and click **Finished**
        to return to the design canvas.

The final screen of activity configuration should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_customer.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/database_query_step-3_data-schema_customer.png" /></span>


## 4. Configure an FTP Connection

Next, you configure a connection to the training SFTP server:

1.  From the component palette's **Connectivity** tab under the
    **Connectors** filter, click the FTP connector:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_ftp.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_ftp.png" /></span>

2.  Configure the [FTP connection](https://success.jitterbit.com/display/CS/FTP+Connection):

    -   **Endpoint Name:** "SFTP"

    -   **Host:**

        "<a href="http://learningsandbox.jitterbit.com" class="external-link"
        rel="nofollow">learningsandbox.jitterbit.com</a>"

    -   **Username** and **Password:** These credentials are from the
        information you provided when completing the Learning Sandbox
        Registration form. This information can be found in the Learning
        Sandbox confirmation email.

3.  Click **Test** to verify connectivity and click **Save Changes**
    when done.

The FTP connection should have a configuration similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/ftp_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/ftp_connection.png" /></span>


## 5. Configure an FTP Activity

Once the FTP connection is configured, you configure an FTP Write
activity associated with that connection:

1.  From the component palette's **Connectivity** tab under the
    **Endpoints** filter, click the "SFTP" connection you have just
    created to show the connection's activity types:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png" /></span>

2.  Drag an FTP Write activity to a component drop zone on the right of
    the Database Query activity within the operation on the design
    canvas.

3.  Double-click the FTP Write activity within the operation to open its
    configuration.

4.  Configure the [FTP Write
    activity](https://success.jitterbit.com/display/CS/FTP+Write+Activity):

    -   **Name:** "Write Customer Records"

    -   **Path:** "/" (forward slash)

    -   **Filename(s):** "result\_\[date\]\_\[time\].csv". Click
        **Next**.

    -   **Data Schema:** Since you didn't provide a schema, there is
        nothing to review in the second screen. Click **Finished**.


## 6. Configure a Transformation

Next, you create a transformation to transform data from the database
source to the FTP target:

1.  On the design canvas, hover over the area between the Database Query
    activity and the FTP Write activity until a component drop zone
    appears.

2.  Click the drop zone and select **New Transformation**. A new
    transformation will open for you to configure:

    -   **Transformation Name:** "DB to Text"

    -   **Source:** The source schema is already provided (on the left).

    -   **Target:** You need to define the target schema (on the right).
        Click **Define Schema**, then select **Create Flat**. Configure
        the [custom flat schema](https://success.jitterbit.com/display/CS/Custom+Flat+Schema):

        -   **Schema Name:** "Customer CSV"

        -   **Add Field:** Use this button to add these fields: `id`,
            `Customer`, `Address`, `City`, `State`, `ZipCode`,
            `Country`, `Phone`, and `Fax`. Once the fields are added,
            click **Save Changes**.

3.  Along the top right of the target schema, click **Automap Exact
    Matches**.

4.  Manually map (drag and drop) the fields that weren't exact matches:
    map `company` to `Customer`, and `zip` to `ZipCode`.

5.  Along the top of the transformation header, click the gray
    **Preview** button to begin the preview process for testing and
    validating the mappings. Click **Next** to deploy the components
    listed and then click **Finished**.

6.  The preview screen displays data populated from the source and
    mapped to the target. Click the right and left arrows to cycle
    through the imported data.

7.  After reviewing the data, click **Return to Workflow**. Clicking
    this button saves the work you did in the transformation.

The custom flat schema configuration should look similar to this:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/schema/customer-csv.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/schema/customer-csv.png" /></span>

The transformation preview should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-text.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/db-to-text.png" /></span>


## 7. Deploy and Run the Operation

Finally, with all operation steps configured, you deploy and run the
operation:

1.  In the top right of the operation, click the actions menu icon <span
    class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img
    src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/common/icons/actions-menu_5.png"
    height="11" /></span> and from the menu click **Deploy and Run**.
    The operation status is displayed in the lower left of the
    operation.
2.  Once the operation is successful, log in
    to <a href="https://learningsandbox.jitterbit.com/WebInterface/login.html"
    class="external-link" rel="nofollow">Jitterbit's training SFTP
    server</a> and view the file you generated.
