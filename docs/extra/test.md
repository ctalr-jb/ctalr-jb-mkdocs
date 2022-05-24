# Jitterbit App Builder Query Activity


## Introduction

A Jitterbit App Builder **Query** activity, using its [Jitterbit App Builder connection](./connection.md), retrieves objects from a specified [module](https://success.jitterbit.com/display/APP/Modules) within an [App Builder](https://success.jitterbit.com/display/APP/App+Builder) app and is intended to be used as a source to provide data in an operation.


## Creating a Jitterbit App Builder Query Activity

An instance of a Jitterbit App Builder **Query** activity is created from a [Jitterbit App Builder connection](./connection.md) using its **Query** activity type.

To create an instance of an activity, drag the activity type to the design canvas or copy the activity type and paste it on the design canvas. For details, see [Creating an Activity Instance](https://success.jitterbit.com/display/CS/Component+Reuse#ComponentReuse-creating-an-activity-instance) in [Component Reuse](https://success.jitterbit.com/display/CS/Component+Reuse).

An existing Jitterbit App Builder **Query** activity can be edited from these locations:

- The design component palette's **Connectivity** tab (see [Endpoints](https://success.jitterbit.com/display/CS/Design+Component+Palette#DesignComponentPalette-endpoints) in [Design Component Palette](https://success.jitterbit.com/display/CS/Design+Component+Palette)).
- The project pane's **Components** tab (see [Component Actions Menu](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab#ProjectPaneComponentsTab-component-actions-menu) in [Project Pane Components Tab](https://success.jitterbit.com/display/CS/Project+Pane+Components+Tab)).


## Configuring a Jitterbit App Builder Query Activity

Follow these steps to configure a Jitterbit App Builder **Query** activity:

- [Step 1: Enter a Name and Select an Object](#step-1-enter-a-name-and-select-an-object)<br>
Provide a name for the activity and select an object.

- [Step 2: Select an Operation](#step-2-select-an-operation)<br>
Select the operation to be performed on the selected object.

- [Step 3: Select a Module](#step-3-select-a-module)<br>
Select the module containing the object to be queried.

- [Step 4: Review the Data Schemas](#step-4-review-the-data-schemas)<br>
Any request or response schemas generated from the endpoint are displayed.

### Step 1: Enter a Name and Select an Object

In this step, provide a name for the activity and select an object. Each user interface element of this step is described below.

![Jitterbit App Builder Query Activity Configuration Step 1](./assets/jitterbit_app_builder-query-activity-1.png)

**TIP:** Fields with a variable icon ![Variable icon](./assets/variable-icon.png) support using [global variables](https://success.jitterbit.com/display/CS/Global+Variables), [project variables](https://success.jitterbit.com/display/CS/Project+Variables), and [Jitterbit variables](https://success.jitterbit.com/display/CS/Jitterbit+Variables). Begin either by typing an open square bracket `[` into the field or by clicking the variable icon to display a list of the existing variables to choose from.

- **Name:** Enter a name to identify the activity. The name must be unique for each Jitterbit App Builder **Query** activity and must not contain forward slashes (`/`) or colons (`:`).

- **Select an Object:** This section displays objects available in the Jitterbit App Builder endpoint. When reopening an existing activity configuration, only the selected object is displayed instead of reloading the entire object list.

  - **Selected Jitterbit App Builder Object:** After an object is selected, it is listed here.

  - **Search:** Enter any part of the object name into the search box to filter the list of objects. The search is not case-sensitive. If objects are already displayed within the table, the table results are filtered in real time with each keystroke. To reload objects from the endpoint when searching, enter search criteria and then refresh, as described below.

  - **Refresh:** Click the refresh icon ![Refresh icon](./assets/refresh-icon.png) or the word **Refresh** to reload objects from the Jitterbit App Builder endpoint. This may be useful if objects have been added to App Builder. This action refreshes all metadata used to build the table of objects displayed in the configuration.

  - **Selecting an Object:** Within the table, click anywhere on a row to select an object. Only one object can be selected. The information available for each object is fetched from the App Builder endpoint:

    - **Name:** The object name from App Builder.

    - **Description:** The object description from App Builder.

  **TIP:** If the table does not populate with available objects, the [Jitterbit App Builder connection](./connection.md) may not be successful. Ensure you are connected by reopening the connection and retesting the credentials.

- **Advanced HTTP Properties:** Click the add icon ![add icon](./assets/add-icon.png) to add a row to the table below and enter a key-value pair for each request parameter.

  To save the row, click the submit icon ![submit icon](./assets/submit-icon.png) in the rightmost column.

  To edit or delete a single row, hover over the rightmost column and use the edit icon
  ![edit icon](./assets/edit-icon.png) or delete icon ![delete icon](./assets/delete-icon.png).

  To delete all rows, click **Clear All**.

- **Save & Exit:** If enabled, click to save the configuration for this step and close the activity configuration.

- **Next:** Click to temporarily store the configuration for this step and continue to the next step. The configuration will not be saved until you click the **Finished** button on the last step.

- **Discard Changes:** After making changes, click to close the configuration without saving changes made to any step. A message asks you to confirm that you want to discard changes.

### Step 2: Select an Operation

In this step, select the operation to be performed on the selected object. Each user interface element of this step is described below.

![Jitterbit App Builder Query Activity Configuration Step 2](./assets/jitterbit_app_builder-query-activity-2.png)

- **Select an Operation:** This section displays operations available in the Jitterbit App Builder endpoint. When reopening an existing activity configuration, only the selected operation is displayed instead of reloading the entire operation list.

  - **Selected Jitterbit App Builder Object:** The object selected in the previous step is listed here.

  - **Select Jitterbit App Builder Operation:** After an operation is selected, it is listed here.

  - **Search:** Enter any part of the operation name into the search box to filter the list of operations. The search is not case-sensitive. If operations are already displayed within the table, the table results are filtered in real time with each keystroke. To reload operations from the endpoint when searching, enter search criteria and then refresh, as described below.

  - **Refresh:** Click the refresh icon ![Refresh icon](./assets/refresh-icon.png) or the word **Refresh** to reload operations from the Jitterbit App Builder endpoint. This may be useful if operations have been added to App Builder. This action refreshes all metadata used to build the table of operations displayed in the configuration.

  - **Selecting an Operation:** Within the table, click anywhere on a row to select an operation. Only one operation can be selected. The information available for each operation is fetched from the App Builder endpoint:

    - **Name:** The operation name from App Builder.

    - **Description:** The operation description from App Builder.

  **TIP:** If the table does not populate with available operations, the [Jitterbit App Builder connection](./connection.md) may not be successful. Ensure you are connected by reopening the connection and retesting the credentials.

- **Back:** Click to temporarily store the configuration for this step and return to the previous step.

- **Next:** Click to temporarily store the configuration for this step and continue to the next step. The configuration will not be saved until you click the **Finished** button on the last step.

- **Discard Changes:** After making changes, click to close the configuration without saving changes made to any step. A message asks you to confirm that you want to discard changes.

### Step 3: Select a Module

In this step, select the module containing the object to be queried. Each user interface element of this step is described below.

![Jitterbit App Builder Query Activity Configuration Step 3](./assets/jitterbit_app_builder-query-activity-3.png)

- **Select Module:** This section displays modules available in the Jitterbit App Builder endpoint. When reopening an existing activity configuration, only the selected module is displayed instead of reloading the entire module list.

  - **Selected Object:** The object selected in the previous step is listed here.

  - **Select Module:** After a module is selected, it is listed here.

  - **Search:** Enter any part of the module name into the search box to filter the list of modules. The search is not case-sensitive. If modules are already displayed within the table, the table results are filtered in real time with each keystroke. To reload modules from the endpoint when searching, enter search criteria and then refresh, as described below.

  - **Refresh:** Click the refresh icon ![Refresh icon](./assets/refresh-icon.png) or the word **Refresh** to reload modules from the Jitterbit App Builder endpoint. This may be useful if modules have been added to App Builder. This action refreshes all metadata used to build the table of modules displayed in the configuration.

  - **Selecting A Module:** Within the table, click anywhere on a row to select a module. Only one module can be selected. The information available for each module is fetched from the App Builder endpoint:

    - **Name:** The module name from App Builder.

    - **Description:** The module description from App Builder.

  **TIP:** If the table does not populate with available modules, the [Jitterbit App Builder connection](./connection.md) may not be successful. Ensure you are connected by reopening the connection and retesting the credentials.

- **Back:** Click to temporarily store the configuration for this step and return to the previous step.

- **Next:** Click to temporarily store the configuration for this step and continue to the next step. The configuration will not be saved until you click the **Finished** button on the last step.

- **Discard Changes:** After making changes, click to close the configuration without saving changes made to any step. A message asks you to confirm that you want to discard changes.

### Step 4: Review the Data Schemas

Any request or response schemas generated from the endpoint are displayed. Each user interface element of this step is described below.

![Jitterbit App Builder Query Activity Configuration Step 4](./assets/jitterbit_app_builder-query-activity-4.png)

- **Data Schemas:** These data schemas are inherited by adjacent transformations and are displayed again during [transformation mapping](https://success.jitterbit.com/display/CS/Transformation+Mapping).

  **NOTE:** Data supplied in a transformation takes precedence over the activity configuration.

  The Jitterbit App Builder connector uses the [Jitterbit App Builder API v1](https://connector.eu3.primeapps.app/swagger/index.html). Refer to the API documentation for information on the schema nodes and fields.

  The request data schema consists of these nodes and fields:

  - **Request:**

    | Request Schema Node/Field   | Field Type | Required/Optional                 | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
    | --------------------------- | ---------- | --------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
    | **deleted**                 | `boolean`  | optional                          | Used when deleted records are also required in the query response. The accepted values are `True` or `False`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
    | **fields**                  | `array`    | optional                          | Used in cases where only certain fields are needed instead of all fields in the queried module. All fields in the module are transferred in the query response when nothing is set here. For example: `[name, birthdate]`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
    | **filters**                 | `array`    | optional                          | Allows the records in modules to be filtered by one or more conditions. Each item in the array provided is treated as a filter object. The fields for arrays accepted here are summarized in the table below.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
    | **filter_logic**            | `string`   | optional                          | Allows the criteria added to `filters` to be expressed as a condition with query operators. For example: `((1 or 2) and 3)`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
    | **filter_lookup_type**      | `string`   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
    | **group_by**                | `string`   | optional                          | The name of the field to group query results by. Grouping can be made according to all field types except `MultiselectLookup` and `MultiSelectDropdown`. For example: `approval_status`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
    | **group_field_date_type**   | `string`   | Required if `group_by` is defined | <p>If a group_by definition is made for a date type field in the created request, grouping by date feature can be used. The date field has 5 different grouping options:</p><ul><li><strong>0</strong> (NotSet): Allows the field with a type other than `Date`, `Datetime`, and `Time` to be grouped.</li><li><strong>1</strong> (All): Allows the date field to be grouped by the entire date up to the time.</li><li><strong>2</strong> (Year): Allows the date field to be grouped by year.</li><li><strong>3</strong> (Ym): Allows the date field to be grouped by year and month.</li><li><strong>4</strong> (Ymd): Allows the date field to be grouped by year, month and day.</li></ul> |
    | **group_field_date_type2**  | `string`   | Required if `group_by` is defined | <p>If a group_by definition is made for a date type field in the created request, grouping by date feature can be used. The date field has 5 different grouping options:</p><ul><li><strong>0</strong> (NotSet): Allows the field with a type other than `Date`, `Datetime`, and `Time` to be grouped.</li><li><strong>1</strong> (All): Allows the date field to be grouped by the entire date up to the time.</li><li><strong>2</strong> (Year): Allows the date field to be grouped by year.</li><li><strong>3</strong> (Ym): Allows the date field to be grouped by year and month.</li><li><strong>4</strong> (Ymd): Allows the date field to be grouped by year, month and day.</li></ul> |
    | **is_lookup_find_id**       | `boolean`  | optional                          | Deprecated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
    | **limit**                   | `integer`  | optional                          | Refers to the number of records that are requested to be transmitted in the query response. For example: When `100` is set here, only the first 100 records found in the query result are transmitted.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
    | **locale**                  | `string`   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
    | **logic_type**              | `string`   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
    | **many_to_many**            | `string`   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
    | **many_to_many_table_name** | `string`   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
    | **module**                  | `string`   | required                          | The system name of the module to be queried. For example: `p_employees_d` for the **Employees** module.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
    | **offset**                  | `integer`  | optional                          | Deprecated.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
    | **sort_direction**          | `string`   | optional                          | Allows the `sort_field` field to be sorted in ascending or descending order. The accepted values are `asc` or `desc` respectively.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
    | **sort_direction_alt_type** | `string`   | optional                          | Allows the `sort_field2` field to be sorted in ascending or descending order. The accepted values are `asc` or `desc` respectively.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
    | **sort_field**              | `string`   | optional                          | Ensures that the queried records are sorted in order based on the field defined here. For example: `created_at`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
    | **sort_field2**             | `string`   | optional                          | Ensures that the queried records are sorted in order based on the field defined here. For example: `created_at`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
    | **sort_field_type**         | `string`   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
    | **sort_field_type2**        | `string`   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
    | **timezoneOffset**          | `string`   |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
    | **two_way**                 | `boolean`  |                                   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

    - **Array Structure for the `filters` Field:**

      | Array Field Name    | Field Type | Required/Optional | Description                                                                                                                                                                                                       |
      | ------------------- | ---------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
      | **no**              | `integer`  | Required          | The number manually assigned to conditions added by the user. It is recommended to increase it for each condition added in order, starting from `1`. This number is used in the Filter Logic operation.           |
      | **field**           | `string`   | Required          | The system name of the field where the condition will be added.                                                                                                                                                   |
      | **value**           | `string`   | Required          | The condition value of the field to be filtered. If dropdown fields are queried, the system name of the dropdown item should be used. Text Field Example: `John`. Dropdown Example: `p_approved`.                 |
      | **operator**        | `string`   | Required          | The query operator to be used on values in the filtered field. Operator selections differ depending on the type of field being queried based on the table below. For example: `equals`, `contains`, `start_with`. |
      | **document_search** | `boolean`  | Required          |                                                                                                                                                                                                                   |

    - **Available Query Operators:**

      | Operator      | Supported App Field Types                                                                                                                                                                                                                                                                                                                                                          | Description                                                                                                                                                                            |
      | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
      | **is**            | <ul><li>Text (Single Line)</li><li>Text (Multi Line)</li><li>Email</li><li>Drop List</li><li>Multi Select</li><li>Multi Select Droplist</li><li>Document</li><li>Url</li><li>Location</li><li>Image</li><li>Tag</li><li>Multi Select Lookup</li></ul>                                                                                                                              | Finds records with a field value that matches a specified value. For example: `Approval Status is Approved` returns records marked as `Approved`.                                      |
      | **is_not**        | <ul><li>Text (Single Line)</li><li>Text (Multi Line)</li><li>Email</li><li>Drop List</li><li>Multi Select</li><li>Multi Select Droplist</li><li>Document</li><li>Url</li><li>Location</li><li>Image</li><li>Tag</li><li>Multi Select Lookup</li></ul>                                                                                                                              | Finds records with a field value that does not match a specified value. For example: `Approval Status is_not Approved` returns records that are not marked as `Approved`.              |
      | **contains**      | <ul><li>Text (Single Line)</li><li>Text (Multi Line)</li><li>Email</li><li>Multi Select</li><li>Multi Select Droplist</li><li>Url</li><li>Location</li><li>Image</li><li>Tag</li><li>Multi Select Lookup</li></ul>                                                                                                                                                                 | Finds records with a field value that contains a specified value. For example: `Full Name contains John` returns records with `John` in Full Name.                                     |
      | **not_contain**   | <ul><li>Text (Single Line)</li><li>Text (Multi Line)</li><li>Email</li><li>Multi Select</li><li>Multi Select Droplist</li><li>Url</li><li>Location</li><li>Image</li><li>Tag</li><li>Multi Select Lookup</li></ul>                                                                                                                                                                 | Finds records with a field value that does not contain a specified value. For example: `Full Name not_contain John` returns records without `John` in Full Name.                       |
      | **starts_with**   | <ul><li>Text (Single Line)</li><li>Text (Multi Line)</li><li>Email</li><li>Document</li><li>Url</li><li>Location</li><li>Image</li></ul>                                                                                                                                                                                                                                           | Finds records with a field value that starts with a specified value. For example: `Email starts_with test` returns records with email addresses in Email that start with `test`.       |
      | **ends_with**     | <ul><li>Text (Single Line)</li><li>Text (Multi Line)</li><li>Email</li><li>Document</li><li>Url</li><li>Location</li><li>Image</li></ul>                                                                                                                                                                                                                                           | Finds records with a field value that ends with a specified value. For example: `Email ends_with @gmail.com` returns records with email addresses in Email that end with `@gmail.com`. |
      | **empty**         | <ul><li>Text (Single Line)</li><li>Text (Multi Line)</li><li>Number (Auto)</li><li>Number (Decimal)</li><li>Currency</li><li>Date</li><li>Date / Time</li><li>Time</li><li>Email</li><li>Drop List</li><li>Multi Select</li><li>Multi Select Droplist</li><li>Document</li><li>Url</li><li>Location</li><li>Image</li><li>Rating</li><li>Tag</li><li>Multi Select Lookup</li></ul> | Find records with an empty field value. For example: `Email empty` returns records with an empty Email field.                                                                          |
      | **not_empty**     | <ul><li>Text (Single Line)</li><li>Text (Multi Line)</li><li>Number (Auto)</li><li>Number (Decimal)</li><li>Currency</li><li>Date</li><li>Date / Time</li><li>Time</li><li>Email</li><li>Drop List</li><li>Multi Select</li><li>Multi Select Droplist</li><li>Document</li><li>Url</li><li>Location</li><li>Image</li><li>Rating</li><li>Tag</li><li>Multi Select Lookup</li></ul> | Find records without an empty field value. For example: `Email not_empty` returns records with values in their Email fields.                                                           |
      | **equals**        | <ul><li>Number</li><li>Number (Auto)</li><li>Number (Decimal)</li><li>Currency</li><li>Date</li><li>Date / Time</li><li>Time</li><li>Check Box</li><li>Rating</li></ul>                                                                                                                                                                                                            | Finds records with numeric or boolean field values that equal a specified value. For example: `Price equals 100` returns records with a Price value of `100`.                          |
      | **not_equal**     | <ul><li>Number</li><li>Number (Auto)</li><li>Number (Decimal)</li><li>Currency</li><li>Date</li><li>Date / Time</li><li>Time</li><li>Check Box</li><li>Rating</li></ul>                                                                                                                                                                                                            | Finds records with numeric or boolean field values that do not equal a specified value. For example: `Price not_equal 100` returns records without a Price value of `100`.             |
      | **greater**       | <ul><li>Number</li><li>Number (Auto)</li><li>Number (Decimal)</li><li>Currency</li><li>Date</li><li>Date / Time</li><li>Time</li><li>Rating</li></ul>                                                                                                                                                                                                                              | Finds records with numeric field values that are greater than a specified value. For example: `Age greater 20` returns records with an Age value above, but not including `20`.        |
      | **greater_equal** | <ul><li>Number</li><li>Number (Auto)</li><li>Number (Decimal)</li><li>Currency</li><li>Date</li><li>Date / Time</li><li>Time</li><li>Rating</li></ul>                                                                                                                                                                                                                              | Finds records with numeric field values that are greater than or equal a specified value. For example: `Age greater_equal 20` returns records with an Age value '20' and above.        |
      | **less**          | <ul><li>Number</li><li>Number (Auto)</li><li>Number (Decimal)</li><li>Currency</li><li>Date</li><li>Date / Time</li><li>Time</li><li>Rating</li></ul>                                                                                                                                                                                                                              | Finds records with numeric field values that are greater than a specified value. For example: `Age less 20` returns records with an Age value below, but not including `20`.           |
      | **less_equal**    | <ul><li>Number</li><li>Number (Auto)</li><li>Number (Decimal)</li><li>Currency</li><li>Date</li><li>Date / Time</li><li>Time</li><li>Rating</li></ul>                                                                                                                                                                                                                              | Finds records with numeric field values that are greater than or equal a specified value. For example: `Age less_equal 20` returns records with an Age value '20' and below.           |

- **Refresh:** Click the refresh icon ![Refresh icon](./assets/refresh-icon.png) or the word **Refresh** to regenerate schemas from the Jitterbit App Builder endpoint. This action also regenerates a schema in other locations throughout the project where the same schema is referenced, such as in an adjacent transformation.

- **Back:** Click to temporarily store the configuration for this step and return to the previous step.

- **Finished:** Click to save the configuration for all steps and close the activity configuration.

- **Discard Changes:** After making changes, click to close the configuration without saving changes made to any step. A message asks you to confirm that you want to discard changes.


## Next Steps

After configuring a Jitterbit App Builder **Query** activity, complete the configuration of the operation by adding and configuring other activities, transformations, or scripts as operation steps. You can also configure the operation settings, which include the ability to chain operations together that are in the same or different workflows.

Menu actions for an activity are accessible from the project pane and the design canvas. For details, see [Activity Actions Menu](https://success.jitterbit.com/display/CS/Connector+Basics#ConnectorBasics-actions-menu) in [Connector Basics](https://success.jitterbit.com/display/CS/Connector+Basics#ConnectorBasics).

Jitterbit App Builder **Query** activities can be used as a source with these [operation patterns](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-valid-operation-patterns):

- [_Transformation Pattern_](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-transformation-pattern)
- [_Two-Target Archive Pattern_](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-two-target-archive-pattern) (as the first source only)
- [_Two-Transformation Pattern_](https://success.jitterbit.com/display/CS/Operation+Validity#OperationValidity-two-transformation-pattern) (as the first or second source)

A typical use case is to use a Jitterbit App Builder **Query** activity in the _Two-Transformation Pattern_. In this example, the first transformation (_Query Request_) creates a request structure that is passed to the Jitterbit App Builder **Query** activity. The second transformation (_Query Response_) receives the response structure, which is then written to a variable by a Variable **Write** activity (_Write Query Response_) and a message is then logged by the _Write to Operation Log_ script:

![Jitterbit App Builder Query operation](./assets/jitterbit_app_builder-query-activity-operation.png)

To use the activity with scripting functions, write the data to a temporary location and then use that temporary location in the scripting function.

When ready, [deploy and run](https://success.jitterbit.com/display/CS/Operation+Deployment+and+Execution) the operation and validate behavior by checking the [operation logs](https://success.jitterbit.com/display/CS/Operation+Logs).
