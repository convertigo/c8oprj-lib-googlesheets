# lib_GoogleSheet
This is the Google Sheet connector for Convertigo platform. Install this library to enable writing and reading from Google Sheets for your Convertigo applications

# Installation

* In your Convertigo Studio use File->Import->Convertigo->Convertigo Project and hit the 'Next' button

* In the Dialog 'Project remote URL' field Paste :

        lib_GoogleSheet=https://github.com/convertigo/c8oprj-lib-googlesheets.git

* And click the 'Finish' button
* This will also automatically import the lib_OAuth project
* Create all 'Undefined Global Symbols' when prompted

# Usage

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

## Sequences

__lib_GoogleSheets__ provides sequences you can call in your projects

Sequence  | Action
------| ------
SheetAddRow   | Add a row of cells to a google Sheet
SheetGetRange | Read a Range of values form a Google Sheet

These sequences will only work if you performed a OAuth Authentication to Google first. To help you with this, the library provides a Shared action you can use in your Apps. 

## Using in a Backend only environment.

If you want to run the Sequences headless (by APIs or within a scheduled job) then the connector will need to authenticate to Google with no end user Interaction.

This can be done in the following way :

*  The connector will have to store a Refresh Token in a Convertigo user profile. To do this it will use the **lib_UserManager** to store the refresh token as an User attribute. This implies that a Convertigo user account must be created. You can do this by executing the **AddUser** Sequence in **lib_UserManager**
* When the Shared Action **DisplayGoogleDrivePicker** is executed, it will check if the current Convertigo session is Authenticated (If the Step **SetAuthenticatedSession** has been executed for this session). If it is, the Google Refresh Token will be persisted as an attribute to the current Authenticated User. **Caution!** This will only occur the first time a User asks access to the Google resources causing the Google Consent Screen to be displayed.
* If you want to run a Sequence such as **SheetGetRange** headless (from an API of from a Scheduled job): 

    * Make sure that a Convertigo Account exists and that the Google refresh token for this user is set up for this account. (See previous step). 
    * Authenticate with this user by having the **SetAuthenticatedUser** step called.
    * Have the **SheetXXX** sequences called. The connector will automatically retrieve the refresh token from the authenticated user account, refresh the access token from google and perform the operation.
