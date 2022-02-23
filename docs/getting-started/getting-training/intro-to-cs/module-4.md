[//]: # (Module 4 - SOAP Web Service)

## Introduction

Module 4 in the [Introduction to the Jitterbit Harmony Cloud
Studio](https://success.jitterbit.com/display/DOC/Introduction+to+the+Jitterbit+Harmony+Cloud+Studio)
training course demonstrates querying a SOAP web service and writing the
response to an SFTP server as a text file.


## Prerequisites

This page assumes you have completed [Module 1 - Database to
Text](https://success.jitterbit.com/display/DOC/Module+1+-+Database+to+Text), where you configured a
connection to Jitterbit's training SFTP server.


## Summary

In this module, you will perform a SOAP call using a provided WSDL to
query a weather service based on zip code, and then write that data to
the training SFTP server as a text file.

The completed operation will look like this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-soap.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/design-canvas/operation_zip-code-soap.png" /></span>

This operation uses these request and response transformation mappings:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-request.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-request.png" /></span>

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-response.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-response.png" /></span>


## 1. Configure a SOAP Connection and Activity

For this module, you continue working within the same project as in
Module 1, and create a new SOAP connection and activity:

1.  Within the same project as Module 1, create a new workflow and name
    it "Module 4."

2.  From the component palette's **Connectivity** tab under the
    **Connectors** filter, click the SOAP connector:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_soap.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/connectors_soap.png" /></span>

    <div
    class="confluence-information-macro confluence-information-macro-tip conf-macro output-block"
    hasbody="true" macro-name="tip">

    <span
    class="aui-icon aui-icon-small aui-iconfont-approve confluence-information-macro-icon">
    </span>
    <div class="confluence-information-macro-body">

    **TIP:** SOAP, or Simple Object Access Protocol, is a
    well-established standards-based protocol for accessing web
    services.

    </div>

    </div>

3.  Configure the [SOAP connection](https://success.jitterbit.com/display/CS/SOAP+Connection):

    -   **Endpoint Name:** "Zip Code – SOAP"

    -   **Upload URL:** Paste the URL to this Web Service Definition
        Language (WSDL) file: "<a
        href="https://trainingoptrial112860.jitterbit.net/TrainingOpsCloud/v1/SOAP_Service/?WSDL"
        class="external-link"
        rel="nofollow">https://trainingoptrial112860.jitterbit.net/TrainingOpsCloud/v1/SOAP_Service/?WSDL</a>".
        Click **Upload**.

    -   **Port:** Select "ZipCodeSoap".

    -   **Web Service URL:** This is automatically populated from the
        uploaded WSDL.

    -   **Select Methods:** Select "ZipCode". Click **Save Changes**.

4.  From the component palette's **Connectivity** tab under the
    **Endpoints** filter, click the "Zip Code – SOAP" connection you
    just created. This shows the SOAP activity type for the method you
    selected while configuring the SOAP connection:

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_soap_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_soap_activities.png" /></span>

5.  Drag the SOAP activity type to a component drop zone on the design
    canvas to create an instance of a SOAP activity in a new operation.

6.  Rename the operation "Zip Code – SOAP." You don't need to open the
    SOAP activity to configure it because it already automatically
    configured with all required information.

The SOAP connection should have a configuration similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/connector/soap_connection.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/connector/soap_connection.png" /></span>


## 2. Configure an FTP Activity

In this step, you use the same connection to the SFTP server as in
Module 1, but configure a separate FTP Write activity:

1.  From the component palette's **Connectivity** tab under the
    **Endpoints** filter, click the "SFTP" connection you created in
    Module 1 to show the connection's activity types:  

    <span class="confluence-embedded-file-wrapper"><img
    src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png"
    class="confluence-embedded-image confluence-external-resource"
    data-image-src="https://docs-source.jitterbit.com/cs/component-palette/connectivity/endpoints_ftp_activities.png" /></span>

2.  Drag an FTP Write activity to a component drop zone on the right of
    the SOAP activity within the operation on the design canvas.

3.  Double-click the FTP Write activity within the operation to open its
    configuration.

4.  Configure the [FTP Write
    activity](https://success.jitterbit.com/display/CS/FTP+Write+Activity):

    -   **Name:** "Zip Code Data"

    -   **Filename(s):** "zipCode.txt"

    -   **Use FTP Rename:** Clear this selection. Click **Next**.

    -   **Data Schema:** Since you didn't provide a schema, there is
        nothing to review in the second screen. Click **Finished**.


## 3. Configure a Request Transformation

Next, you create a transformation for the SOAP web service request:

1.  On the design canvas, hover over the area to the left of the SOAP
    activity until a component drop zone appears.

2.  Click the drop zone and select **New Transformation**. A new
    transformation will open for you to configure:

    -   **Transformation Name:** "Zip Code – SOAP Request"

    -   **Source:** Leave the source schema undefined (on the left).

    -   **Target:** Within the target schema (on the right), hover over
        the `ZipCode` field and click the add icon <span
        class="confluence-embedded-file-wrapper confluence-embedded-manual-size"><img src="https://docs-source.jitterbit.com/common/icons/add_2.png"
        class="confluence-embedded-image confluence-external-resource"
        data-image-src="https://docs-source.jitterbit.com/common/icons/add_2.png"
        height="24" /></span>. From the menu, click **Add Custom
        Value**. Then enter a zip code into the text area. Click
        **Return to Workflow**.

The request transformation should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-request.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-request.png" /></span>


## 4. Configure a Response Transformation

Next, you create a transformation to write the SOAP web service response
to the FTP target:

1.  On the design canvas, hover over the area between the SOAP activity
    and the FTP Write activity until a component drop zone appears.

2.  Click the drop zone and select **New Transformation**. A new
    transformation will open for you to configure:

    -   **Transformation Name:** "Zip Code – SOAP Response"

    -   **Source:** The source schema is already provided (on the left).

    -   **Target:** You need to define the target schema (on the right).
        Click **Define Schema**, then select **Create Flat**. Configure
        the [custom flat schema](https://success.jitterbit.com/display/CS/Custom+Flat+Schema):

        -   **Schema Name:** "Zip Code Data"

        -   **Options:** Change the **Delimiter** from a comma to a tab
            by entering "\\t".

        -   **Add Field:** Use this button to add these fields: `zip`,
            type, state, primaryCity, county, timeZone, areaCodes,
            country, and population. Once the fields are added, click
            **Save Changes**.

3.  Drag the `zipCodeResponse` source node to the `__flat__` target node
    and select **Automap**. Then click **Return to Workflow**.

The custom flat schema configuration should look similar to this:

<span
class="confluence-embedded-file-wrapper"><img src="https://docs-source.jitterbit.com/cs/schema/zip-code-data.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/schema/zip-code-data.png" /></span>

The request transformation should look similar to this:

<span class="confluence-embedded-file-wrapper"><img
src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-response.png"
class="confluence-embedded-image confluence-external-resource"
data-image-src="https://docs-source.jitterbit.com/cs/transformation/mapping-mode/zip-code-soap-response.png" /></span>


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
