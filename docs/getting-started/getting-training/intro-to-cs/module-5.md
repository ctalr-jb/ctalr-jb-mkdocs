[//]: # (Module 5 - RESTful Web Service)

## Introduction

Module 5 in the [Introduction to the Jitterbit Harmony Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio)
training course demonstrates querying a REST web service and writing the
response to an SFTP server as a text file.


## Prerequisites

This page assumes you have completed [Module 1 - Database to
Text](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text), where you configured a
connection to Jitterbit's training SFTP server. It also requires
completion of [Module 4 - SOAP Web
Service](https://success.jitterbit.com/display/DOC/Module+4+-+SOAP+Web+Service), as it reuses several
project components from this module.


## Summary

In this module, you will query a RESTful web service for weather based
on zip code, and then write that data to the training SFTP server as a
text file.

The completed operation will look like this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-rest.png" /></span>

This operation uses this transformation mapping:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-rest-response.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-rest-response.png" /></span>


## 1. Configure an HTTP Connection

For this module, you continue working within the same project as in
Module 1, and create a new SOAP connection:

1.  Within the same project as Module 1, create a new workflow and name
    it "Module 5."

2.  From the component palette's **Connectivity** tab under the
    **Connectors** filter, click the HTTP connector:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_http_single.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_http_single.png" /></span>

3.  Configure the [HTTP connection](https://success.jitterbit.com/display/CS/HTTP+Connection):

    -   **Endpoint Name:** "Zip Code – REST"

    -   **Base URL:** Paste the base URL for this service: "<a
        href="https://trainingoptrial112860.jitterbit.net/TrainingOpsCloud/v1/REST_Service/"
        class="external-link"
        rel="nofollow">https://trainingoptrial112860.jitterbit.net/TrainingOpsCloud/v1/REST_Service/</a>".

4.  Click **Save Changes**.

The HTTP connection should have a configuration similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/http_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/http_connection.png" /></span>


## 2. Configure an HTTP Activity

Next, configure an activity associated with the HTTP connection to get
the data from the web service:

1.  From the component palette's **Connectivity** tab under the
    **Endpoints** filter, click the "Zip Code – REST" connection you
    just created:  

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_http_activities_zip-code-rest.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_http_activities_zip-code-rest.png" /></span>

2.  Drag an HTTP GET activity type to the component drop zone on the
    design canvas to create an instance of an HTTP GET activity in a new
    operation.

3.  Rename the operation to "Zip Code – REST."

4.  Double-click the HTTP GET activity within the operation to open its
    configuration.

5.  Configure the [HTTP activity](https://success.jitterbit.com/display/CS/HTTP+Activities):  

    -   **Name:** "Zip Code Details"

    -   **HTTP Verb:** "GET"

    -   **Path:** "zip"

    -   **Request Parameters:** Click **Add** to set a query parameter
        called "code" with a value of your zip code (for example,
        "94501"). Click **Next**.

    -   **Provide Request Schema:** As there is no need to provide a
        request schema (a standard GET request doesn't contain a body),
        click **Next** again.

    -   **Provide Response Schema:** Select **Yes, Provide New
        Schema**, provide a schema name of "Zip Code Detail," and then
        paste this expected JSON response structure into the lower text
        box:

        ```
        {
          "zip": 12345,
          "type": "",
          "primaryCity": "",
          "state": "",
          "county": "",
          "timeZone": "",
          "areaCodes": "",
          "latitude": "",
          "longitude": "",
          "country": "",
          "population": 123456
        }
        ```

        Click **Next**.

    -   **Data Schema:** Review the data schema and click **Finished**
        to return to the design canvas.

The final screen of the activity configuration should look similar to
this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/http_get_step-4_data-schema.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/http_get_step-4_data-schema.png" /></span>


## 3. Configure an FTP Activity

In this step, you reuse the FTP Write activity you created in Module 4:

1.  From the project pane's **Components** tab, expand **Endpoints** \>
    **FTP Endpoints** to locate the "SFTP" connection and "Zip Code
    Data" write activity you created as part of Module 4.
2.  Drag the "Zip Code Data" write activity to a drop zone on the right
    of the HTTP activity within the operation on the design canvas to
    reuse it in the operation.


## 4. Configure a Transformation

Next, you create a transformation to transform data from the HTTP source
to the FTP target:

1.  On the design canvas, hover over the area between the HTTP GET
    activity and the FTP Write activity until a component drop zone
    appears.

2.  Click the drop zone and select **New Transformation**. A new
    transformation will open for you to configure:

    -   **Transformation Name:** "Zip Code – REST Response"

    -   **Source:** The source schema is already provided (on the left)
        because you defined it in the GET activity.

    -   **Target:** You need to define the target schema (on the right).
        Click **Define Schema**, then select **Use Sample File**.
        Configure the [sample file
        schema](https://success.jitterbit.com/display/CS/Sample+File+Schema):

        -   **Provide Schema File:** Select **Use Saved Schema**.

        -   **Saved Schemas:** Use the dropdown to select the
            tab-delimited "Zip Code Data" schema that you defined as
            part of Module 4. Click **Finish**.

3.  Along the top right of the target schema, click **Automap Exact
    Matches**. Then click **Return to Workflow**.

The transformation mapping should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-rest-response.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-rest-response.png" /></span>


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
    to <a href="https://learningsandbox.jitterbit.com/WebInterface/login.html"
    class="external-link" rel="nofollow">Jitterbit's training SFTP
    server</a> and view the file you generated.
