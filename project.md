
# ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/core/images/project_color_16x16.png?raw=true "Project") lib_GoogleSheet

The Google Sheet Connector for Convertigo

<details><summary><span style="color:DarkGoldenRod"><i>References</i></span></summary><blockquote><p>


<details><summary><b>lib_ExtendedComponents_ui_ngx</b></summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/references/images/ProjectSchemaReference_16x16.png?raw=true "ProjectSchemaReference") lib_ExtendedComponents_ui_ngx


see [readme](https://github.com/convertigo/c8oprj-lib-extended-components-ui-ngx/tree/8.0.0#readme)
</p></blockquote></details>

<details><summary><b>lib_OAuth</b> : Used to get the Google OAuth token</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/references/images/ProjectSchemaReference_16x16.png?raw=true "ProjectSchemaReference") lib_OAuth

Used to get the Google OAuth token
see [readme](https://github.com/convertigo/c8oprj-lib-oauth/tree/8.0.0#readme)
</p></blockquote></details>

<details><summary><b>lib_UserManager</b></summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/references/images/ProjectSchemaReference_16x16.png?raw=true "ProjectSchemaReference") lib_UserManager


see [readme](https://github.com/convertigo/c8oprj-lib-user-manager/tree/7.9.0.1#readme)
</p></blockquote></details>
</p></blockquote></details>

<details><summary><span style="color:DarkGoldenRod"><i>Connectors</i></span></summary><blockquote><p>


<details><summary><b>GoogleOAuth</b></summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/connectors/images/httpconnector_color_16x16.png?raw=true "HttpConnector") GoogleOAuth



<details><summary><span style="color:DarkGoldenRod"><i>Transactions</i></span></summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/transactions/images/jsonhttptransaction_color_16x16.png?raw=true "JsonHttpTransaction") RefreshToken



<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableHttpVariable" >&nbsp;client_id
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableHttpVariable" >&nbsp;client_secret
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableHttpVariable" >&nbsp;grant_type
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableHttpVariable" >&nbsp;refresh_token
</td>
<td>

</td>
</tr>
</table>

</p></blockquote></details>
</p></blockquote></details>

<details><summary><b>void</b> : void connector, replace or don't use it</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/connectors/images/sqlconnector_color_16x16.png?raw=true "SqlConnector") void

void connector, replace or don't use it

<details><summary><span style="color:DarkGoldenRod"><i>Transactions</i></span></summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/transactions/images/sqltransaction_color_16x16.png?raw=true "SqlTransaction") void

does nothing
</p></blockquote></details>
</p></blockquote></details>
</p></blockquote></details>

<details><summary><span style="color:DarkGoldenRod"><i>Sequences</i></span></summary><blockquote><p>


<details><summary><b>checkAccessTokenGoogle</b> : Checks is a valid access token is held by the current user's session for Google</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") checkAccessTokenGoogle

Checks is a valid access token is held by the current user's session for Google. If the token is not present, will use the current Convertigo user profile to get the refresh_token and use it to regenerate a valid acess token.






</p></blockquote></details>

<details><summary><b>formssource_GetData</b> : Gets data from a GoogleSheet</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") formssource_GetData

Gets data from a GoogleSheet. 

<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;forms_Range
</td>
<td>
Configure here the data range you want to read from the Google Sheet.  This has to be such as 'Sheet1!A1:Z100' (Read data from Sheet1, starting from colon A1 to colon Z on 100 lines). Sheet is optional. If omitted, the data will be read from the first available sheet in the document
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;forms_SheetID
</td>
<td>
Configure here the Sheet ID you want to use as datasource.
</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>formssource_GetSelectData</b> : Returns data from a gogle sheet as a source for this list</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") formssource_GetSelectData

Returns data from a gogle sheet as a source for this list

<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;forms_colons
</td>
<td>
Name of the google sheet column separated by a comma to use to retrieve select data. For example A, B or AM. If one column is specified, data the select list will be filled by values coming from this column. If 2 columns are specified, the first one will hold the select list display values and the 2nd one the list values.
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;forms_filter
</td>
<td>
Used to filter data from the Goole Sheet
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;forms_Range
</td>
<td>
Configure here the data range you want to query from the Google Sheet.  This has to be such as 'Sheet1!A1:Z100' (Read data from Sheet1, starting from colon A1 to colon Z on 100 lines). Sheet is optional. If omitted, the data will be read from the first available sheet in the document
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;forms_SheetID
</td>
<td>
Configure here the Sheet ID you want to use as datasource.
</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>formssource_QueryTable</b> : Query table data from a GoogleSheet</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") formssource_QueryTable

Query table data from a GoogleSheet

<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;forms_Query
</td>
<td>
Write here the Query you would like to be execute on the range. Queries are based on the Google Sheet Query language; for example : SELECT  * WHERE A LIKE '%mike%'   would select all the line from the range  where colon 'A' contains the string 'mike'. More details on the Query language can be found  here : https://developers.google.com/chart/interactive/docs/querylanguage
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;forms_Range
</td>
<td>
Configure here the data range you want to query from the Google Sheet.  This has to be such as 'Sheet1!A1:Z100' (Read data from Sheet1, starting from colon A1 to colon Z on 100 lines). Sheet is optional. If omitted, the data will be read from the first available sheet in the document
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;forms_SheetID
</td>
<td>
Configure here the Sheet ID you want to use as datasource.
</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>getApiKey</b> : Utility to get from the server the Googler Drive picker api key</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") getApiKey

Utility to get from the server the Googler Drive picker api key
</p></blockquote></details>

<details><summary><b>loginGoogleWithCode</b> : Perform the OAuth flow for Google</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") loginGoogleWithCode

Perform the OAuth flow for Google

If the token is valid, it will be stored in the user's session to be used when calling Google APIs.

If a refresh_token is found, (This is the case when a First OAuth flow is performed and Google pops the Consent sreen.. )  this token is saved in the user profile so that the checkAcessTokenGoogle sequence can use it to regenerate a new acess Token.



<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;client_id
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;code
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;keySecret
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;redirect_uri
</td>
<td>

</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>SheetAddRow</b> : Add a row of cells to a Google Sheet</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") SheetAddRow

Add a row of cells to a Google Sheet.

<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/multivaluedvariable_color_16x16.png?raw=true "  alt="RequestableMultiValuedVariable" >&nbsp;dataRow
</td>
<td>
The data to be added 
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Range
</td>
<td>
The Cell range to read. (examples, A1:D7 or  Class Data!A2:E)
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;SheetID
</td>
<td>
The Sheet id as found in the google  sheet URL
</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>SheetGetRange</b> : Get a range of cells from a Google Sheet</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") SheetGetRange

Get a range of cells from a Google Sheet.

<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;FirstRowHeader
</td>
<td>
Set this to true if the first row a header
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;formssourceMode
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Range
</td>
<td>
The Cell range to read. (examples, A1:D7 or  Sheet!A2:E). leave empty to return all the sheet data
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;SheetID
</td>
<td>
The Sheet id as found in the google  sheet URL
</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>SheetQueryTable</b> : Get a range of cells from a Google Sheet</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") SheetQueryTable

Get a range of cells from a Google Sheet.

<span style="color:DarkGoldenRod">Variables</span>

<table>
<tr>
<th>
name
</th>
<th>
comment
</th>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;FirstRowHeader
</td>
<td>
Set this to true if the first row a header
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;formssourceMode
</td>
<td>

</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Query
</td>
<td>
The Cell range to read. (examples, A1:D7 or  Sheet!A2:E). leave empty to return all the sheet data
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;Range
</td>
<td>
The Cell range to read. (examples, A1:D7 or  Sheet!A2:E). leave empty to return all the sheet data
</td>
</tr>
<tr>
<td>
<img src="https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/variables/images/variable_color_16x16.png?raw=true "  alt="RequestableVariable" >&nbsp;SheetID
</td>
<td>
The Sheet id as found in the google  sheet URL
</td>
</tr>
</table>

</p></blockquote></details>

<details><summary><b>TestLogin</b> : This only to have the test application logged in to be able to add Attributes to user accounts</summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/sequences/images/genericsequence_color_16x16.png?raw=true "GenericSequence") TestLogin

This only to have the test application logged in to be able to add Attributes to user accounts
</p></blockquote></details>
</p></blockquote></details>

<details><summary><span style="color:DarkGoldenRod"><i>Mobile Application</i></span></summary><blockquote><p>


## ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/core/images/mobileapplication_color_16x16.png?raw=true "MobileApplication") MobileApplication

Test and demo app to show Google Sheet capacities

<details><summary><span style="color:DarkGoldenRod"><i>Pages</i></span></summary><blockquote><p>


<details><summary><b>Configure</b> : The configuration page is called by Forms when the users clicks on the "Configure" Button</summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/pagecomponent_color_16x16.png?raw=true "PageComponent") Configure

The configuration page is called by Forms when the users clicks on the "Configure" Button. This is supposed to be held in a IFRAME
</p></blockquote></details>

<details><summary><b>DemoPage</b> : Just a demo page, not used</summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/pagecomponent_color_16x16.png?raw=true "PageComponent") DemoPage

Just a demo page, not used
</p></blockquote></details>
</p></blockquote></details>

<details><summary><span style="color:DarkGoldenRod"><i>Shared Actions</i></span></summary><blockquote><p>


### ![](https://github.com/convertigo/convertigo/blob/develop/engine/src/com/twinsoft/convertigo/beans/ngx/components/images/uiactionstack_color_16x16.png?raw=true "UIActionStack") DisplayGoogleDrivePicker

Displays the Google Drive fille picker to browse available spread sheets
This needs an API key to be configured in the symbols :

ib_GoogleSheet.picker.apikey.secret

The Api key can be found at : 

https://console.developers.google.com/apis/credentials?organizationId=22050485893&project=convertigo-form-builder



</p></blockquote></details>
</p></blockquote></details>
