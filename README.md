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

## Shared Actions

In order to authenticate with Google and browse the availables documents in a Google Drive, the library provides a Shared Action you can use in your client apps.

Shared Action  | Usage
------| ------
DisplayGoogleDrivePicker   | This will display a Google Driver Picker widget in your Mobile or desktop app. If you are not already authenticated to Google, a Google Login will be displayed followed by a consent page. When all pages are filled by the user, the Google Driver picker will appear. When the user selects a document and hits the ok button, the SharedAction will return in the __out__ object the ID of the document picked. You can use this __out__ bound to the __SheetID__ variable when calling the SheetXXXX sequences. 


## Sample Application

You will find in this project a sample application using the Google Sheet Library, Use this as a reference and tutorial about using the library. This demonstrates :
- Use of the DisplayPicker Shared Action
- use of the SheetAddRow Sequence
- use of the SheetGetRange Sequence

