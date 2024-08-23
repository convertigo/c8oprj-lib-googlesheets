


# lib_GoogleSheet

This is the Google Sheet Connector for Convertigo. use this library to connect to your no code apps to Google Sheets


For more technical informations : [documentation](./project.md)

- [Installation](#installation)
- [Sequences](#sequences)
    - [checkAccessTokenGoogle](#checkaccesstokengoogle)
    - [forms_AddRow](#forms_addrow)
    - [formssource_GetTableData](#formssource_gettabledata)
    - [getApiKey](#getapikey)
    - [getRefreshToken](#getrefreshtoken)
    - [loginGoogleWithCode](#logingooglewithcode)
    - [SheetAddRow](#sheetaddrow)
    - [SheetGetRange](#sheetgetrange)
    - [TestLogin](#testlogin)
- [Mobile Library](#mobile-library)
    - [Shared Actions](#shared-actions)
        - [DisplayGoogleDrivePicker](#displaygoogledrivepicker)


## Installation

1. In your Convertigo Studio click on ![](https://github.com/convertigo/convertigo/blob/develop/eclipse-plugin-studio/icons/studio/project_import.gif?raw=true "Import a project in treeview") to import a project in the treeview
2. In the import wizard

   ![](https://github.com/convertigo/convertigo/blob/develop/eclipse-plugin-studio/tomcat/webapps/convertigo/templates/ftl/project_import_wzd.png?raw=true "Import Project")
   
   paste the text below into the `Project remote URL` field:
   <table>
     <tr><td>Usage</td><td>Click the copy button at the end of the line</td></tr>
     <tr><td>To contribute</td><td>

     ```
     lib_GoogleSheet=https://github.com/convertigo/c8oprj-lib-googlesheets.git:branch=8.3.0
     ```
     </td></tr>
     <tr><td>To simply use</td><td>

     ```
     lib_GoogleSheet=https://github.com/convertigo/c8oprj-lib-googlesheets/archive/8.3.0.zip
     ```
     </td></tr>
    </table>
3. Click the `Finish` button. This will automatically import the __lib_GoogleSheet__ project


## Sequences

### checkAccessTokenGoogle

Checks is a valid access token is held by the current users' session for Google

This as to be called by client apps to decide whenever or not they have to display an OAuth login screen



### forms_AddRow

Add a row to a table in a Google Sheet. Each column of the table must have the same name as the technicalID <br>of a field on the form. <br><br>This action can also be used to update some data in a table. In this case, set <br>the <b>Where Clause</b> variable to a condition and set the <b>Update</b> variable to the columns you want to update.

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>doc</td><td></td>
</tr>
<tr>
<td>forms_config</td><td>Creates a row in a table with a given configuration</td>
</tr>
<tr>
<td>forms_update</td><td>Will be use only if the WHERE clause is not empty. Give here separated by commas the fields = value to define the columns to be updated by the given values. The fields must be the technical identifiers of the fields of your form. For example: <br><br><i>inputText1 = value1, inputText2 = value2</i>. <br><br>Of course values can be dragged and dropped from the list of fields.</td>
</tr>
<tr>
<td>forms_where</td><td>If this field is not empty, the action will use the WHERE clause to filter the record to update. The WHERE clause must be a valid 'SQL like' WHERE clause without the WHERE keyword. A Where clause can be for example : <br><br><i>inputText1 = 'value1' </i></br></br>Google Sheet connector only supports the = operator and one item. Values must be surrounded by single quotes '</td>
</tr>
<tr>
<td>originalDoc</td><td></td>
</tr>
</table>

### formssource_GetTableData

Get data from a Google sheet table for a data grid. Each column of the Google Sheet  will be displayed as the same column in the data grid

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>forms_config</td><td>Returns the rows of the table with a given configuration</td>
</tr>
<tr>
<td>forms_tableFilter</td><td>Filters
</td>
</tr>
<tr>
<td>model</td><td>If true, just return one line of data so that No Code studio can compte the table model</td>
</tr>
</table>

### getApiKey

Utility to get from the server the Googler Drive picker api key

### getRefreshToken

Gets the google oAuth refresh token previsously stored in user profile. Used  to get the rToken  to be stored in the  Forms data source configuration 

### loginGoogleWithCode

Perform the OAuth flow for Google

If the token is valid, it will be stored in the user's session to be used when calling Microsoft APIs.

Also if the token is valid, setAuthenticatedUser step is executed to flag this session as authenticated.


**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>client_id</td><td></td>
</tr>
<tr>
<td>code</td><td></td>
</tr>
<tr>
<td>keySecret</td><td></td>
</tr>
<tr>
<td>redirect_uri</td><td></td>
</tr>
</table>

### SheetAddRow

Add a row of cells to a Google Sheet.

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>dataRow</td><td>The data to be added </td>
</tr>
<tr>
<td>Range</td><td>The Cell range to read. (examples, A1:D7 or  Class Data!A2:E)</td>
</tr>
<tr>
<td>SheetID</td><td>The Sheet id as found in the google  sheet URL</td>
</tr>
<tr>
<td>update</td><td>a JSON array of field, values</td>
</tr>
<tr>
<td>where</td><td>A Google Sheet Where clause</td>
</tr>
</table>

### SheetGetRange

Get a range of cells from a Google Sheet.

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>FirstRowHeader</td><td>Set this to true if the first row a header</td>
</tr>
<tr>
<td>Query</td><td>A Query in google Query language Syntax such as SELECT * WHERE  A contains('this pattern')
</td>
</tr>
<tr>
<td>Range</td><td>The Cell range to read. (examples, A1:D7 or  Sheet!A2:E). leave empty to return all the sheet data</td>
</tr>
<tr>
<td>SheetID</td><td>The Sheet id as found in the google  sheet URL</td>
</tr>
</table>

### TestLogin

This only to have the test application logged in to be able to add Attributes to user accounts

## Mobile Library

Test and demo app to show Google Sheet capacities 

### Shared Actions

#### DisplayGoogleDrivePicker

Displays the Google Drive fille picker to browse available spread sheets
This needs an API key to be configured in the symbols :

lib_GoogleSheet.picker.apikey.secret

The Api key can be found at : 

https://console.developers.google.com/apis/credentials?organizationId=22050485893&project=convertigo-form-builder






