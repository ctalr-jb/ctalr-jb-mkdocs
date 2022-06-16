<h2 id="introduction">Introduction</h2>

This page provides data schemas for these [Jitterbit App Builder connector](https://success.jitterbit.com/display/CS/Jitterbit+App+Builder) activities:

- **[Update Activity](https://success.jitterbit.com/display/CS/Jitterbit+App+Builder+Data+Schemas#heading-UpdateActivity)**
- **[Delete Activity](https://success.jitterbit.com/display/CS/Jitterbit+App+Builder+Data+Schemas#heading-DeleteActivity)**
- **[Create Activity](https://success.jitterbit.com/display/CS/Jitterbit+App+Builder+Data+Schemas#heading-CreateActivity)**
- **[Query Activity](https://success.jitterbit.com/display/CS/Jitterbit+App+Builder+Data+Schemas#heading-QueryActivity)**


<h2 id="update-activity">Update Activity</h2>

<h3 id="update-activity-request-schema">Update Activity Request Schema</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid"><thead><tr role="row"><th class="confluenceTh">Request Schema Node/Field</th><th class="confluenceTh">Description</th></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr></thead><tbody aria-live="polite" aria-relevant="all"><tr role="row"><td class="confluenceTd"><strong><code>updateRecordsRequest</code></strong></td><td class="confluenceTd">The request to update records in App Builder.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>request</code></strong></td><td class="confluenceTd">The node representing the request.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>schemaRequest</code></strong></td><td class="confluenceTd">The node representing the schema request.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>record</code></strong></td><td class="confluenceTd">A dynamic object containing the fields that can be updated for an existing record. The fields listed here are system fields present in every module that will <strong>not</strong> be updated in App Builder directly by this request.</td></tr><tr role="row"><td class="confluenceTd"><code>id</code></td><td class="confluenceTd">The ID of the record.</td></tr><tr role="row"><td class="confluenceTd"><code>owner</code></td><td class="confluenceTd">The ID of the owner of the item.</td></tr><tr role="row"><td class="confluenceTd"><code>deleted</code></td><td class="confluenceTd">A flag indicating whether or not the item is deleted.</td></tr><tr role="row"><td class="confluenceTd"><code>created_at</code></td><td class="confluenceTd">When the item was created.</td></tr><tr role="row"><td class="confluenceTd"><code>created_by</code></td><td class="confluenceTd">The ID of the creator of the item.</td></tr><tr role="row"><td class="confluenceTd"><code>updated_at</code></td><td class="confluenceTd">When the item was last updated.</td></tr><tr role="row"><td class="confluenceTd"><code>updated_by</code></td><td class="confluenceTd">The ID of the last user who updated the item.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><code>ids</code></td><td class="confluenceTd">An array of the IDs of the records to be updated. Bulk updates can be done in a single query if more than one ID is present.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><code>module</code></td><td class="confluenceTd">The system name of the module for records to be updated in. For example: <code>p_employees_d</code> for the <strong>Employees</strong> module.</td></tr><tr role="row"><td class="confluenceTd"><code>runWorkflows</code></td><td class="confluenceTd">Whether or not microflows associated with the module should run after the records are updated.</td></tr></tbody></table>

<h3 id="update-activity-response-schema">Update Activity Response Schema</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid"><thead><tr role="row"><th class="confluenceTh">Response Schema Node/Field</th><th class="confluenceTh">Description</th></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr></thead><tbody aria-live="polite" aria-relevant="all"><tr role="row"><td class="confluenceTd"><strong><code>updateRecordsResponse</code></strong></td><td class="confluenceTd">The response from updating records in App Builder.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>response</code></strong></td><td class="confluenceTd">The node representing the response.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>schemaResponse</code></strong></td><td class="confluenceTd">The node representing the schema response.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>item</code></strong></td><td class="confluenceTd">The node containing response messages.</td></tr><tr role="row"><td class="confluenceTd"><code>status_code</code></td><td class="confluenceTd">A code associated with the response.</td></tr><tr role="row"><td class="confluenceTd"><code>isUpdated</code></td><td class="confluenceTd">A boolean indicating if the update request was successful.</td></tr><tr role="row"><td class="confluenceTd"><code>message</code></td><td class="confluenceTd">A message associated with the response.</td></tr></tbody></table>

<h2 id="delete-activity">Delete Activity</h2>

<h3 id="delete-activity-request-schema">Delete Activity Request Schema</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid"><thead><tr role="row"><th class="confluenceTh">Request Schema Node/Field</th><th class="confluenceTh">Description</th></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr></thead><tbody aria-live="polite" aria-relevant="all"><tr role="row"><td class="confluenceTd"><strong><code>deleteRecordsRequest</code></strong></td><td class="confluenceTd">The request to delete records from App Builder.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>request</code></strong></td><td class="confluenceTd">The node representing the request.</td></tr><tr role="row"><td class="confluenceTd"><code>ids</code></td><td class="confluenceTd">The IDs of the records to be deleted.</td></tr><tr role="row"><td class="confluenceTd"><code>module</code></td><td class="confluenceTd">The system name of the module for records to be deleted from. For example: <code>p_employees_d</code> for the <strong>Employees</strong> module.</td></tr></tbody></table>

<h3 id="delete-activity-response-schema">Delete Activity Response Schema</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid"><thead><tr role="row"><th class="confluenceTh">Response Schema Node/Field</th><th class="confluenceTh">Description</th></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr></thead><tbody aria-live="polite" aria-relevant="all"><tr role="row"><td class="confluenceTd"><strong><code>deleteRecordsResponse</code></strong></td><td class="confluenceTd">The response from deleting records in App Builder.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>response</code></strong></td><td class="confluenceTd">The node representing the response.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>schemaResponse</code></strong></td><td class="confluenceTd">The node representing the schema response.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>item</code></strong></td><td class="confluenceTd">The node containing response messages.</td></tr><tr role="row"><td class="confluenceTd"><code>status_code</code></td><td class="confluenceTd">A code associated with the response.</td></tr><tr role="row"><td class="confluenceTd"><code>isDeleted</code></td><td class="confluenceTd">A boolean indicating if the delete request was successful.</td></tr><tr role="row"><td class="confluenceTd"><code>message</code></td><td class="confluenceTd">A message associated with the response.</td></tr></tbody></table>

<h2 id="create-activity">Create Activity</h2>

<h3 id="create-activity-request-schema">Create Activity Request Schema</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid"><thead><tr role="row"><th class="confluenceTh">Request Schema Node/Field</th><th class="confluenceTh">Description</th></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr></thead><tbody aria-live="polite" aria-relevant="all"><tr role="row"><td class="confluenceTd"><strong><code>createRecordsRequest</code></strong></td><td class="confluenceTd">The request to create records in App Builder.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>request</code></strong></td><td class="confluenceTd">The node representing the request.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>schemaRequest</code></strong></td><td class="confluenceTd">The node representing the schema request.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>item</code></strong></td><td class="confluenceTd">A dynamic object containing the fields that can entered for a new record. The fields listed here are system fields present in every module that will <strong>not</strong> be added in App Builder directly by this request.</td></tr><tr role="row"><td class="confluenceTd"><code>id</code></td><td class="confluenceTd">The ID of the item to be added as a record.</td></tr><tr role="row"><td class="confluenceTd"><code>owner</code></td><td class="confluenceTd">The ID of the owner of the item.</td></tr><tr role="row"><td class="confluenceTd"><code>deleted</code></td><td class="confluenceTd">Whether or not the item is deleted.</td></tr><tr role="row"><td class="confluenceTd"><code>created_at</code></td><td class="confluenceTd">When the item was created.</td></tr><tr role="row"><td class="confluenceTd"><code>created_by</code></td><td class="confluenceTd">The ID of the creator of the item.</td></tr><tr role="row"><td class="confluenceTd"><code>updated_at</code></td><td class="confluenceTd">When the item was last updated.</td></tr><tr role="row"><td class="confluenceTd"><code>updated_by</code></td><td class="confluenceTd">The ID of the last user who updated the item.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><code>module</code></td><td class="confluenceTd">The system name of the module for records to be created in. For example: <code>p_employees_d</code> for the <strong>Employees</strong> module.</td></tr><tr role="row"><td class="confluenceTd"><code>runWorkflows</code></td><td class="confluenceTd">Whether or not microflows associated with the module should run after the records are created.</td></tr></tbody></table>

<h3 id="create-activity-response-schema">Create Activity Response Schema</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid"><thead><tr role="row"><th class="confluenceTh">Response Schema Node/Field</th><th class="confluenceTh">Description</th></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr></thead><tbody aria-live="polite" aria-relevant="all"><tr role="row"><td class="confluenceTd"><strong><code>createRecordsResponse</code></strong></td><td class="confluenceTd">The response from creating records in App Builder.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>response</code></strong></td><td class="confluenceTd">The node representing the response.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>schemaResponse</code></strong></td><td class="confluenceTd">The node representing the schema response.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>item</code></strong></td><td class="confluenceTd">The node containing each created record.</td></tr><tr role="row"><td class="confluenceTd"><code>...</code></td><td class="confluenceTd">A dynamic list of fields associated with the module.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>errors</code></strong></td><td class="confluenceTd">The node representing response errors.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>item</code></strong></td><td class="confluenceTd">The node containing response error messages.</td></tr><tr role="row"><td class="confluenceTd"><code>errorMessage</code></td><td class="confluenceTd">A message associated with the error.</td></tr><tr role="row"><td class="confluenceTd"><code>errorCode</code></td><td class="confluenceTd">A code assosciated with the error.</td></tr></tbody></table>

<h2 id="query-activity">Query Activity</h2>

<h3 id="query-activity-request-schema">Query Activity Request Schema</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid"><thead><tr role="row"><th class="confluenceTh">Request Schema Node/Field</th><th class="confluenceTh">Description</th></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr></thead><tbody aria-live="polite" aria-relevant="all"><tr role="row"><td class="confluenceTd"><strong><code>queryRecordsRequest</code></strong></td><td class="confluenceTd">The request to query records from App Builder.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>request</code></strong></td><td class="confluenceTd">The node representing the request.</td></tr><tr role="row"><td class="confluenceTd"><code>deleted</code></td><td class="confluenceTd">Allows deleted records to appear in the query response when set to <code>True</code>. The accepted values are <code>True</code> or <code>False</code>.</td></tr><tr role="row"><td class="confluenceTd"><code>fields</code></td><td class="confluenceTd">Limits the query response to the fields specified. All fields in the module are returned in the query response when nothing is set here. For example: <code>[name, birthdate]</code>.</td></tr><tr role="row"><td class="confluenceTd"><code>filters</code></td><td class="confluenceTd">Allows the records in modules to be filtered by one or more conditions. Each item in the array provided is treated as a filter object. The fields for arrays accepted here are summarized in the <a href="#array-structure-for-the-filters-field">Array Structure for the <code>filters</code> Field</a> table below.</td></tr><tr role="row"><td class="confluenceTd"><code>filter_logic</code></td><td class="confluenceTd">Allows the criteria added to <code>filters</code> to be expressed as a condition with query operators. For example: <code>((1 or 2) and 3)</code>. If this field is left empty, the criteria in <code>filters</code> will be automatically connected based on <code>logic_type</code>. All available query operators are listed in the <a href="#query-operators-for-the-filter_logic-field">Query Operators for the <code>filter_logic</code> Field</a> table below.</td></tr><tr role="row"><td class="confluenceTd"><code>filter_lookup_type</code></td><td class="confluenceTd">Allows lookups in the modules to be filtered against <code>1</code> (all records) or by <code>2</code> (<strong>Organization</strong> in the <strong>Employees</strong> module). <code>2</code> is set by default. This helps keeps lookup information relevant.</td></tr><tr role="row"><td class="confluenceTd"><code>group_by</code></td><td class="confluenceTd">The system name of the field to group query results by. All field types can be grouped except <code>MultiselectLookup</code> and <code>MultiSelectDropdown</code>. For example: <code>approval_status</code>.</td></tr><tr role="row"><td class="confluenceTd"><code>group_field_date_type</code></td><td class="confluenceTd"><p>Required if <code>group_by</code> is defined. If a <code>group_by</code> definition is made for a <code>Date</code> type field in the request, this field must be used. One of five different grouping options must be chosen:</p><ul><li><code>0</code> (Not Set): Allows the field with a type other than <code>Date</code>, <code>Datetime</code>, and <code>Time</code> to be grouped.</li><li><code>1</code> (All): Allows the date field to be grouped by the entire date up to the time.</li><li><code>2</code> (Year): Allows the date field to be grouped by year.</li><li><code>3</code> (Year and Month): Allows the date field to be grouped by year and month.</li><li><code>4</code> (Year, Month, and Day): Allows the date field to be grouped by year, month and day.</li></ul></td></tr><tr role="row"><td class="confluenceTd"><code>group_field_date_type2</code></td><td class="confluenceTd"><p>Required if <code>group_by</code> is defined. If a <code>group_by</code> definition is made for a <code>Date</code> type field in the request, this field must be used. One of five different grouping options must be chosen:</p><ul><li><code>0</code> (Not Set): Allows the field with a type other than <code>Date</code>, <code>Datetime</code>, and <code>Time</code> to be grouped.</li><li><code>1</code> (All): Allows the date field to be grouped by the entire date up to the time.</li><li><code>2</code> (Year): Allows the date field to be grouped by year.</li><li><code>3</code> (Year and Month): Allows the date field to be grouped by year and month.</li><li><code>4</code> (Year, Month, and Day): Allows the date field to be grouped by year, month and day.</li></ul></td></tr><tr role="row"><td class="confluenceTd"><code>is_lookup_find_id</code></td><td class="confluenceTd"><em>Deprecated.</em></td></tr><tr role="row"><td class="confluenceTd"><code>limit</code></td><td class="confluenceTd">Limits the query response to a specific number of records. For example: When <code>100</code> is set here, only the first 100 records found in the query result are transmitted.</td></tr><tr role="row"><td class="confluenceTd"><code>locale</code></td><td class="confluenceTd">Specifies which format and language <code>Date</code>, <code>Datetime</code> and <code>Dropdown</code> items will appear as. <code>Dropdown</code> item translations are configured in the Globalization page in App Builder. <code>Date</code> and <code>Datetime</code> formats by language are shown in the <a href="#language-codes-and-datetime-formats-for-the-locale-field">Language Codes and <code>Datetime</code> Formats for the <code>locale</code> Field</a> table below.</td></tr><tr role="row"><td class="confluenceTd"><code>logic_type</code></td><td class="confluenceTd">If the <code>filter_logic</code> field is left empty, the criteria in <code>filters</code> will be automatically connected based on this field. The accepted values are <code>1</code> (and) or <code>2</code> (or). <code>1</code> is set by default.</td></tr><tr role="row"><td class="confluenceTd"><code>many_to_many</code></td><td class="confluenceTd">The system name of a module connected to the one defined in <code>module</code> using an App Builder Relation. For example: <code>p_equipment_d</code>. If defined, the query will pull additional information from this module based on its connection to <code>module</code>, similar to a <code>JOIN</code> in SQL.</td></tr><tr role="row"><td class="confluenceTd"><code>many_to_many_table_name</code></td><td class="confluenceTd">The name of the intermediate table created between the <code>module</code> and <code>many_to_many</code> modules (if defined) through an App Builder Relation. This table is not a module and is not visible in the App Builder interface. The name of this table is the combination of the lowecase names of the two related modules with an underscore in between them. For example: <code>module1name_module2name</code>.</td></tr><tr role="row"><td class="confluenceTd"><code>module</code></td><td class="confluenceTd">The system name of the module to query. For example: <code>p_employees_d</code> for the <strong>Employees</strong> module.</td></tr><tr role="row"><td class="confluenceTd"><code>offset</code></td><td class="confluenceTd"><em>Deprecated.</em></td></tr><tr role="row"><td class="confluenceTd"><code>sort_direction</code></td><td class="confluenceTd">Allows the <code>sort_field</code> field to be sorted in ascending or descending order. The accepted values are <code>asc</code> or <code>desc</code> respectively.</td></tr><tr role="row"><td class="confluenceTd"><code>sort_direction_alt_type</code></td><td class="confluenceTd">Allows the <code>sort_field2</code> field to be sorted in ascending or descending order. The accepted values are <code>asc</code> or <code>desc</code> respectively.</td></tr><tr role="row"><td class="confluenceTd"><code>sort_field</code></td><td class="confluenceTd">The system name of the field to sort the queried records by. For example: <code>created_at</code>.</td></tr><tr role="row"><td class="confluenceTd"><code>sort_field2</code></td><td class="confluenceTd">The system name of the field to sort the queried records by after they have been sorted with <code>sort_field</code>. For example: <code>created_at</code>.</td></tr><tr role="row"><td class="confluenceTd"><code>sort_field_type</code></td><td class="confluenceTd">The system name of the field to sort the queried records based on the grouping settings defined in <code>group_by</code> and <code>group_field_date_type</code>. For example: <code>approval_status</code>.</td></tr><tr role="row"><td class="confluenceTd"><code>sort_field_type2</code></td><td class="confluenceTd">The system name of the field to sort the queried records based on the grouping settings defined in <code>group_by</code> and <code>group_field_date_type2</code>. For example: <code>approval_status</code>.</td></tr><tr role="row"><td class="confluenceTd"><code>timezoneOffset</code></td><td class="confluenceTd">Offsets times in the query response from Coordinated Universal Time (UTC) by the number of minutes defined here. For example: <code>180</code> or <code>-240</code>.</td></tr><tr role="row"><td class="confluenceTd"><code>two_way</code></td><td class="confluenceTd">Required if <code>many_to_many</code> is defined. Used as part of validating an App Builder Relation. Its value should always be <code>false</code>.</td></tr></tbody></table>

<h3 id="query-activity-response-schema">Query Activity Response Schema</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid"><thead><tr role="row"><th class="confluenceTh">Response Schema Node/Field</th><th class="confluenceTh">Description</th></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr></thead><tbody aria-live="polite" aria-relevant="all"><tr role="row"><td class="confluenceTd"><strong><code>queryRecordsResponse</code></strong></td><td class="confluenceTd">The response from querying records in App Builder.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>response</code></strong></td><td class="confluenceTd">The node representing the response.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>schemaResponse</code></strong></td><td class="confluenceTd">The node representing the schema response.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>item</code></strong></td><td class="confluenceTd">The node containing each record returned from the query.</td></tr><tr role="row"><td class="confluenceTd"><code>...</code></td><td class="confluenceTd">A dynamic list of fields associated with the module.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>errors</code></strong></td><td class="confluenceTd">The node representing response errors.</td></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr><tr role="row"><td class="confluenceTd"><strong><code>item</code></strong></td><td class="confluenceTd">The node containing response error messages.</td></tr><tr role="row"><td class="confluenceTd"><code>errorMessage</code></td><td class="confluenceTd">A message associated with the error.</td></tr><tr role="row"><td class="confluenceTd"><code>errorCode</code></td><td class="confluenceTd">A code assosciated with the error.</td></tr></tbody></table>

<h3 id="array-structure-for-the-filters-field">Array Structure for the <code>filters</code> Field</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid"><thead><tr role="row"><th class="confluenceTh">Array Field Name</th><th class="confluenceTh">Description</th></tr><tr role="row"><td class="confluenceTd" colspan="2"></td></tr></thead><tbody aria-live="polite" aria-relevant="all"><tr role="row"><td class="confluenceTd"><strong><code>no</code></strong></td><td class="confluenceTd">The integer manually assigned to conditions added by the user. It is recommended to increase the number for each condition added in order, starting from <code>1</code>. This number is used with the <code>filter_logic</code> field.</td></tr><tr role="row"><td class="confluenceTd"><strong><code>field</code></strong></td><td class="confluenceTd">The system name of the field where the condition will be added.</td></tr><tr role="row"><td class="confluenceTd"><strong><code>value</code></strong></td><td class="confluenceTd">The condition value of the field to be filtered. If dropdown fields are queried, the system name of the dropdown item should be used. Text field example: <code>John</code>. Dropdown example: <code>p_approved</code>.</td></tr><tr role="row"><td class="confluenceTd"><strong><code>operator</code></strong></td><td class="confluenceTd">The query operator to be used on values in the filtered field. Operator selections differ depending on the type of field being queried based on the <a href="#query-operators-for-the-filter_logic-field">Query Operators for the <code>filter_logic</code> Field</a> table below. For example: <code>equals</code>, <code>contains</code>, <code>start_with</code>.</td></tr><tr role="row"><td class="confluenceTd"><strong><code>document_search</code></strong></td><td class="confluenceTd"><em>Deprecated.</em></td></tr></tbody></table>

<h3 id="query-operators-for-the-filter_logic-field">Query Operators for the <code>filter_logic</code> Field</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid" resolved="">
<thead>
<tr role="row">
<th class="confluenceTh">Operator</th>
<th class="confluenceTh">Description</th>
<th class="confluenceTh">Supported App Builder Fields</th>
</tr>
</thead>
<tbody aria-live="polite" aria-relevant="all">
<tr role="row">
<td class="confluenceTd"><strong><code>is</code></strong></td>
<td class="confluenceTd">Finds records with a field value that matches a specified value. For example: <code>Approval Status is Approved</code> returns records marked as <code>Approved</code> in their <strong>Approval Status</strong> field.</td>
<td class="confluenceTd" rowspan="2"><ul><li>Text (single-line)</li><li>Text (multi-line)</li><li>Email</li><li>Dropdown</li><li>Multiselect</li><li>Multiselect dropdown</li><li>Document</li><li>URL</li><li>Location</li><li>Image</li><li>Tag</li><li>Multiselect lookup</li></ul></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>is_not</code></strong></td>
<td class="confluenceTd">Finds records with a field value that does not match a specified value. For example: <code>Approval Status is_not Approved</code> returns records that are not marked as <code>Approved</code> in their <strong>Approval Status</strong> field.</td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>contains</code></strong></td>
<td class="confluenceTd">Finds records with a field value that contains a specified value. For example: <code>Full Name contains John</code> returns records with <code>John</code> in their <strong>Full Name</strong> field.</td>
<td class="confluenceTd" rowspan="2"><ul><li>Text (single-line)</li><li>Text (multi-line)</li><li>Email</li><li>Multiselect</li><li>Multiselect dropdown</li><li>URL</li><li>Location</li><li>Image</li><li>Tag</li><li>Multiselect lookup</li></ul></td>
</tr>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>not_contain</code></strong></td>
<td class="confluenceTd">Finds records with a field value that does not contain a specified value. For example: <code>Full Name not_contain John</code> returns records without <code>John</code> in their <strong>Full Name</strong> field.</td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>starts_with</code></strong></td>
<td class="confluenceTd">Finds records with a field value that starts with a specified value. For example: <code>Email starts_with test</code> returns records with email addresses in their <strong>Email</strong> field that start with <code>test</code>.</td>
<td class="confluenceTd" rowspan="2"><ul><li>Text (single-line)</li><li>Text (multi-line)</li><li>Email</li><li>Document</li><li>URL</li><li>Location</li><li>Image</li></ul></td>
</tr>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>ends_with</code></strong></td>
<td class="confluenceTd">Finds records with a field value that ends with a specified value. For example: <code>Email ends_with @gmail.com</code> returns records with email addresses in their <strong>Email</strong> field that end with <code>@gmail.com</code>.</td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>empty</code></strong></td>
<td class="confluenceTd">Find records with an empty field value. For example: <code>Email empty</code> returns records with an empty <strong>Email</strong> field.</td>
<td class="confluenceTd" rowspan="2"><ul><li>Text (single-line)</li><li>Text (multi-line)</li><li>Number (auto)</li><li>Number (decimal)</li><li>Currency</li><li>Date</li><li>Date / time</li><li>Time</li><li>Email</li><li>Dropdown</li><li>Multiselect</li><li>Multiselect dropdown</li><li>Document</li><li>URL</li><li>Location</li><li>Image</li><li>Rating</li><li>Tag</li><li>Multiselect lookup</li></ul></td>
</tr>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>not_empty</code></strong></td>
<td class="confluenceTd">Find records without an empty field value. For example: <code>Email not_empty</code> returns records with values in their <strong>Email</strong> field.</td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>equals</code></strong></td>
<td class="confluenceTd">Finds records with numeric or boolean field values that equal a specified value. For example: <code>Price equals 100</code> returns records with a <strong>Price</strong> field value of <code>100</code>.</td>
<td class="confluenceTd" rowspan="2"><ul><li>Number</li><li>Number (auto)</li><li>Number (decimal)</li><li>Currency</li><li>Date</li><li>Date / time</li><li>Time</li><li>Checkbox</li><li>Rating</li></ul></td>
</tr>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>not_equal</code></strong></td>
<td class="confluenceTd">Finds records with numeric or boolean field values that do not equal a specified value. For example: <code>Price not_equal 100</code> returns records without a <strong>Price</strong> field value of <code>100</code>.</td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>greater</code></strong></td>
<td class="confluenceTd">Finds records with numeric field values that are greater than a specified value. For example: <code>Age greater 20</code> returns records with an <strong>Age</strong> field value above, but not including <code>20</code>.</td>
<td class="confluenceTd" rowspan="4"><ul><li>Number</li><li>Number (auto)</li><li>Number (decimal)</li><li>Currency</li><li>Date</li><li>Date / time</li><li>Time</li><li>Rating</li></ul></td>
</tr>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>greater_equal</code></strong></td>
<td class="confluenceTd">Finds records with numeric field values that are greater than or equal a specified value. For example: <code>Age greater_equal 20</code> returns records with an <strong>Age</strong> field value <code>20</code> and above.</td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>less</code></strong></td>
<td class="confluenceTd">Finds records with numeric field values that are greater than a specified value. For example: <code>Age less 20</code> returns records with an <strong>Age</strong> field value below, but not including <code>20</code>.</td>
</tr>
</tr>
<tr role="row">
<td class="confluenceTd"><strong><code>less_equal</code></strong></td>
<td class="confluenceTd">Finds records with numeric field values that are greater than or equal a specified value. For example: <code>Age less_equal 20</code> returns records with an <strong>Age</strong> field value <code>20</code> and below.</td>
</tr>
</tbody>
</table>

<h3 id="language-codes-and-datetime-formats-for-the-locale-field">Language Codes and <code>Datetime</code> Formats for the <code>locale</code> Field</h3>

<table style="text-decoration: none;text-align: left;" class="confluenceTable" role="grid" resolved="">
<thead>
<tr role="row">
<th class="confluenceTh">Language</th>
<th class="confluenceTh">Language Code</th>
<th class="confluenceTh"><code>Datetime</code> Format</th>
</tr>
</thead>
<tbody aria-live="polite" aria-relevant="all">
<tr role="row">
<td class="confluenceTd"><strong>Afrikaans</strong></td>
<td class="confluenceTd"><code>AF</code></td>
<td class="confluenceTd"><code>yyyy-MM-dd HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Albanian</strong></td>
<td class="confluenceTd"><code>SQ</code></td>
<td class="confluenceTd"><code>d.M.yyyy h:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Arabic</strong></td>
<td class="confluenceTd"><code>AR</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy hh:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Azerbaijani</strong></td>
<td class="confluenceTd"><code>AZ</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Basque</strong></td>
<td class="confluenceTd"><code>EU</code></td>
<td class="confluenceTd"><code>yyyy/M/d HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Belarusian</strong></td>
<td class="confluenceTd"><code>BE</code></td>
<td class="confluenceTd"><code>dd.MM.yy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Bengali</strong></td>
<td class="confluenceTd"><code>BN</code></td>
<td class="confluenceTd"><code>d/M/yyyy h:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Bulgarian</strong></td>
<td class="confluenceTd"><code>BG</code></td>
<td class="confluenceTd"><code>d.M.yyyy H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Catalan</strong></td>
<td class="confluenceTd"><code>CA</code></td>
<td class="confluenceTd"><code>d/M/yyyy H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Chinese</strong></td>
<td class="confluenceTd"><code>ZH</code></td>
<td class="confluenceTd"><code>yyyy/M/d H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Croatian</strong></td>
<td class="confluenceTd"><code>HR</code></td>
<td class="confluenceTd"><code>d.M.yyyy. H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Czech</strong></td>
<td class="confluenceTd"><code>CS</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Danish</strong></td>
<td class="confluenceTd"><code>DA</code></td>
<td class="confluenceTd"><code>dd-MM-yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Dutch</strong></td>
<td class="confluenceTd"><code>NL</code></td>
<td class="confluenceTd"><code>dd-MM-yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>English</strong></td>
<td class="confluenceTd"><code>EN</code></td>
<td class="confluenceTd"><code>M/d/yyyy h:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Esperanto</strong></td>
<td class="confluenceTd"><code>EO</code></td>
<td class="confluenceTd"><code>yyyy-MM-dd HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Estonian</strong></td>
<td class="confluenceTd"><code>ET</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Filipino</strong></td>
<td class="confluenceTd"><code>TI</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy h:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Finnish</strong></td>
<td class="confluenceTd"><code>FI</code></td>
<td class="confluenceTd"><code>d.M.yyyy H.mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>French</strong></td>
<td class="confluenceTd"><code>FR</code></td>
<td class="confluenceTd"><code>dd-MM-yy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Galician</strong></td>
<td class="confluenceTd"><code>GL</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Georgian</strong></td>
<td class="confluenceTd"><code>KA</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>German</strong></td>
<td class="confluenceTd"><code>DE</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Gujarati</strong></td>
<td class="confluenceTd"><code>GU</code></td>
<td class="confluenceTd"><code>dd-MM-yy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Greek</strong></td>
<td class="confluenceTd"><code>EL</code></td>
<td class="confluenceTd"><code>d/M/yyyy h:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Hindi</strong></td>
<td class="confluenceTd"><code>HI</code></td>
<td class="confluenceTd"><code>dd-MM-yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Hungarian</strong></td>
<td class="confluenceTd"><code>HU</code></td>
<td class="confluenceTd"><code>yyyy.MM.dd. H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Icelandic</strong></td>
<td class="confluenceTd"><code>IS</code></td>
<td class="confluenceTd"><code>d.M.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Indonesian</strong></td>
<td class="confluenceTd"><code>ID</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy HH.mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Irish</strong></td>
<td class="confluenceTd"><code>GA</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Italian</strong></td>
<td class="confluenceTd"><code>IT</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Japanese</strong></td>
<td class="confluenceTd"><code>JA</code></td>
<td class="confluenceTd"><code>yyyy/MM/dd H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Kannada</strong></td>
<td class="confluenceTd"><code>KN</code></td>
<td class="confluenceTd"><code>dd-MM-yy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Khmer</strong></td>
<td class="confluenceTd"><code>KM</code></td>
<td class="confluenceTd"><code>dd/MM/yy H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Korean</strong></td>
<td class="confluenceTd"><code>KO</code></td>
<td class="confluenceTd"><code>yyyy.M.d. tt h:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Lao</strong></td>
<td class="confluenceTd"><code>LO</code></td>
<td class="confluenceTd"><code>d/M/yyyy H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Latvian</strong></td>
<td class="confluenceTd"><code>LV</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Lithuanian</strong></td>
<td class="confluenceTd"><code>LT</code></td>
<td class="confluenceTd"><code>yyyy-MM-dd HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Macedonian</strong></td>
<td class="confluenceTd"><code>MK</code></td>
<td class="confluenceTd"><code>dd.M.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Malay</strong></td>
<td class="confluenceTd"><code>MS</code></td>
<td class="confluenceTd"><code>d/MM/yyyy h:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Maltese</strong></td>
<td class="confluenceTd"><code>MT</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Marathi</strong></td>
<td class="confluenceTd"><code>MR</code></td>
<td class="confluenceTd"><code>dd-MM-yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Norwegian</strong></td>
<td class="confluenceTd"><code>NO</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Persian</strong></td>
<td class="confluenceTd"><code>FA</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy hh:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Polish</strong></td>
<td class="confluenceTd"><code>PL</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Portuguese</strong></td>
<td class="confluenceTd"><code>PT</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Romanian</strong></td>
<td class="confluenceTd"><code>RO</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Russian</strong></td>
<td class="confluenceTd"><code>RU</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Slovak</strong></td>
<td class="confluenceTd"><code>SK</code></td>
<td class="confluenceTd"><code>d.M.yyyy H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Slovenian</strong></td>
<td class="confluenceTd"><code>SL</code></td>
<td class="confluenceTd"><code>d.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Spanish</strong></td>
<td class="confluenceTd"><code>ES</code></td>
<td class="confluenceTd"><code>d/M/yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Swahili</strong></td>
<td class="confluenceTd"><code>SW</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Swedish</strong></td>
<td class="confluenceTd"><code>SV</code></td>
<td class="confluenceTd"><code>yyyy-MM-dd HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Tamil</strong></td>
<td class="confluenceTd"><code>TA</code></td>
<td class="confluenceTd"><code>dd-MM-yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Telugu</strong></td>
<td class="confluenceTd"><code>TE</code></td>
<td class="confluenceTd"><code>dd-MM-yy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Thai</strong></td>
<td class="confluenceTd"><code>TH</code></td>
<td class="confluenceTd"><code>d/M/yyyy H:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Turkish</strong></td>
<td class="confluenceTd"><code>TR</code></td>
<td class="confluenceTd"><code>dd.MM.yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Urdu</strong></td>
<td class="confluenceTd"><code>UR</code></td>
<td class="confluenceTd"><code>d/M/yy h:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Vietnamese</strong></td>
<td class="confluenceTd"><code>VI</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy h:mm tt</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Welsh</strong></td>
<td class="confluenceTd"><code>CY</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy HH:mm</code></td>
</tr>
<tr role="row">
<td class="confluenceTd"><strong>Yiddish</strong></td>
<td class="confluenceTd"><code>YI</code></td>
<td class="confluenceTd"><code>dd/MM/yyyy HH:mm</code></td>
</tr>
</tbody>
</table>
