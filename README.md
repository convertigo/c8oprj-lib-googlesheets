


# lib_GoogleSheet

This is the Google Sheet connector for Convertigo platform. Install this library to enable writing and reading from Google Sheets for your Convertigo applications

## Configuring your Google OAuth and API Keys

This connector uses the OAuth authentication protocol to exchange data with Google Sheets. You must configure this in your Google APIs Console:

* Connect to https://console.developers.google.com/apis/dashboard
* Create a New Project and select it
* Click **ENABLE APIS AND SERVICES** button
* Search for *Google Sheets API* and *Google Picker API* and enable them
* Click on **Credentials** from Google left menu
* Click on **CREATE CREDENTIALS** button and select **API key**
* Copy this API key and paste it in **lib_GoogleSheet.picker.apikey.secret** symbol value via Convertigo Administration Console
* Click on **CREATE CREDENTIALS** button and select **OAuth client ID** (Configure consent screen if asked)
* Choose **Web application** in drop-down list
* In **Authorised JavaScript origins**, add **http://localhost:18080** and **http://localhost:8100** URIs (Convertigo Studio dev/test mode) and **https://\<your site\>.convertigo.net** (Convertigo Server prod mode)
* In **Authorised redirect URIs**, add https://c8ocloud.convertigo.net/convertigo/projects/lib_OAuth/getTokenGoogle.html
* Click **CREATE** button
* Copy the *Client ID* key and paste it in **lib_oauth.google.clientid** symbol value via Convertigo Administration Console
* Copy the *Client Secret* key and paste it in **lib_oauth.google.keysecret.secret** symbol value via Convertigo Administration Console

## Configuring Convertigo Symbols

__lib_GoogleSheet__ needs some symbols to be configured. You configure them trough the Web Console: https://&lt;your site&gt;.convertigo.net/admin, hit the ___symbols___ button to get to the symbol configuration page.


Symbol  | value
------| ------
lib_oauth.google.clientid | The **client ID** value you copied in the previous step
lib_oauth.google.keysecret.secret | the **Client Secret** value you copied in the previous step.
lib_GoogleSheet.picker.apikey.secret | the **API Key** value you copied in the previous Step.

## Sample Application

You will find in this project a sample application using the Google Sheet Library, Use this as a reference and tutorial about using the library. This demonstrates :
- Use of the DisplayPicker Shared Action
- use of the SheetAddRow Sequence
- use of the SheetGetRange Sequence

## Using in a Backend only environment.

If you want to run the Sequences headless (by APIs or within a scheduled job) then the connector will need to authenticate to Google with no end user Interaction.

This can be done in the following way :

*  The connector will have to store a Refresh Token in a Convertigo user profile. To do this it will use the **lib_UserManager** to store the refresh token as an User attribute. This implies that a Convertigo user account must be created. You can do this by executing the **AddUser** Sequence in **lib_UserManager**
* When the Shared Action **DisplayGoogleDrivePicker** is executed, it will check if the current Convertigo session is Authenticated (If the Step **SetAuthenticatedSession** has been executed for this session). If it is, the Google Refresh Token will be persisted as an attribute to the current Authenticated User. **Caution!** This will only occur the first time a User asks access to the Google resources causing the Google Consent Screen to be displayed.
* If you want to run a Sequence such as **SheetGetRange** headless (from an API of from a Scheduled job): 

    * Make sure that a Convertigo Account exists and that the Google refresh token for this user is set up for this account. (See previous step). 
    * Authenticate with this user by having the **SetAuthenticatedUser** step called.
    * Have the **SheetXXX** sequences called. The connector will automatically retrieve the refresh token from the authenticated user account, refresh the access token from google and perform the operation.


For more technical informations : [documentation](./project.md)

- [Installation](#installation)
- [Sequences](#sequences)
    - [checkAccessTokenGoogle](#checkaccesstokengoogle)
    - [formssource_GetData](#formssource_getdata)
    - [formssource_GetSelectData](#formssource_getselectdata)
    - [formssource_QueryTable](#formssource_querytable)
    - [getApiKey](#getapikey)
    - [loginGoogleWithCode](#logingooglewithcode)
    - [SheetAddRow](#sheetaddrow)
    - [SheetGetRange](#sheetgetrange)
    - [SheetQueryTable](#sheetquerytable)
    - [TestLogin](#testlogin)
- [Mobile Library](#mobile-library)
    - [Shared Actions](#shared-actions)
        - [DisplayGoogleDrivePicker](#displaygoogledrivepicker)


## Installation

1. In your Convertigo Studio use `File->Import->Convertigo->Convertigo Project` and hit the `Next` button
2. In the dialog `Project remote URL` field, paste the text below:
   <table>
     <tr><td>Usage</td><td>Click the copy button</td></tr>
     <tr><td>To contribute</td><td>

     ```
     lib_GoogleSheet=https://github.com/convertigo/c8oprj-lib-googlesheets.git:branch=develop
     ```
     </td></tr>
     <tr><td>To simply use</td><td>

     ```
     lib_GoogleSheet=https://github.com/convertigo/c8oprj-lib-googlesheets/archive/develop.zip
     ```
     </td></tr>
    </table>
3. Click the `Finish` button. This will automatically import the __lib_GoogleSheet__ project


## Sequences

### checkAccessTokenGoogle

Checks is a valid access token is held by the current user's session for Google. If the token is not present, will use the current Convertigo user profile to get the refresh_token and use it to regenerate a valid acess token.







### formssource_GetData

Gets data from a GoogleSheet. 

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>forms_Range</td><td>Configure here the data range you want to read from the Google Sheet.  This has to be such as 'Sheet1!A1:Z100' (Read data from Sheet1, starting from colon A1 to colon Z on 100 lines). Sheet is optional. If omitted, the data will be read from the first available sheet in the document</td>
</tr>
<tr>
<td>forms_SheetID</td><td>Configure here the Sheet ID you want to use as datasource.</td>
</tr>
</table>

### formssource_GetSelectData

Returns data from a gogle sheet as a source for this list

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>forms_colons</td><td>Name of the google sheet column separated by a comma to use to retrieve select data. For example A, B or AM. If one column is specified, data the select list will be filled by values coming from this column. If 2 columns are specified, the first one will hold the select list display values and the 2nd one the list values.</td>
</tr>
<tr>
<td>forms_filter</td><td>Used to filter data from the Goole Sheet</td>
</tr>
<tr>
<td>forms_Range</td><td>Configure here the data range you want to query from the Google Sheet.  This has to be such as 'Sheet1!A1:Z100' (Read data from Sheet1, starting from colon A1 to colon Z on 100 lines). Sheet is optional. If omitted, the data will be read from the first available sheet in the document</td>
</tr>
<tr>
<td>forms_SheetID</td><td>Configure here the Sheet ID you want to use as datasource.</td>
</tr>
</table>

### formssource_QueryTable

Query table data from a GoogleSheet

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>forms_Query</td><td>Write here the Query you would like to be execute on the range. Queries are based on the Google Sheet Query language; for example : SELECT  * WHERE A LIKE '%mike%'   would select all the line from the range  where colon 'A' contains the string 'mike'. More details on the Query language can be found  here : https://developers.google.com/chart/interactive/docs/querylanguage</td>
</tr>
<tr>
<td>forms_Range</td><td>Configure here the data range you want to query from the Google Sheet.  This has to be such as 'Sheet1!A1:Z100' (Read data from Sheet1, starting from colon A1 to colon Z on 100 lines). Sheet is optional. If omitted, the data will be read from the first available sheet in the document</td>
</tr>
<tr>
<td>forms_SheetID</td><td>Configure here the Sheet ID you want to use as datasource.</td>
</tr>
</table>

### getApiKey

Utility to get from the server the Googler Drive picker api key

### loginGoogleWithCode

Perform the OAuth flow for Google

If the token is valid, it will be stored in the user's session to be used when calling Google APIs.

If a refresh_token is found, (This is the case when a First OAuth flow is performed and Google pops the Consent sreen.. )  this token is saved in the user profile so that the checkAcessTokenGoogle sequence can use it to regenerate a new acess Token.



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
<td>formssourceMode</td><td></td>
</tr>
<tr>
<td>Range</td><td>The Cell range to read. (examples, A1:D7 or  Sheet!A2:E). leave empty to return all the sheet data</td>
</tr>
<tr>
<td>SheetID</td><td>The Sheet id as found in the google  sheet URL</td>
</tr>
</table>

### SheetQueryTable

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
<td>formssourceMode</td><td></td>
</tr>
<tr>
<td>Query</td><td>The Cell range to read. (examples, A1:D7 or  Sheet!A2:E). leave empty to return all the sheet data</td>
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

ib_GoogleSheet.picker.apikey.secret

The Api key can be found at : 

https://console.developers.google.com/apis/credentials?organizationId=22050485893&project=convertigo-form-builder






