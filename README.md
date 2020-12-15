# lib_GoogleSheet
This is the Google Sheet connector for Convertigo platform. Install this library to enable writing and reading from Google Sheets for your Convertigo applications

# Installation

* In your Convertigo Studio use File->Import->Convertigo->Convertigo Project and hit the 'Next' button

* In the Dialog 'Project remote URL' field Paste :

        lib_GoogleSheet=https://github.com/convertigo/c8oprj-lib-googlesheets.git

* And click the 'Finish' button

# Usage

## Configuring your Google OAuth and API Keys

This connector uses the OAuth authentication protocol to exchange data with Google Sheets. You must configure this in your Google API Portal:

* Connect to https://developers.google.com/sheets/api/quickstart/js
* Click on "Enable the google Sheet API", enter a project name and click Next
* Copy the Client ID and the Client Secret values as you will have to configure them in symbols later.
* Close this Dialog, and then click  on the "Create API Key" Button
* Again enter a project name (The same of course..) and click Next.
* Copy the API key as you will have to configure it n symbols later.

## Configuring Convertigo Symbols

__lib_GoogleSheet__ needs some symbols to be configured. You configure them trough the Web Console: https://&lt;your site&gt;.convertigo.net/admin, hit the ___symbols___ button to get to the symbol configuration page.


Symbol  | value
------| ------
lib_oauth.google.clientid | The client ID value you copied in the previous step
lib_oauth.google.keysecret.secret | the Client Secret value you copied in the previous step.
lib_GoogleSheet.picker.apikey.secret | the API Key value you copied in the previous Step.

## Sequences

__lib_GoogleSheets__ provides sequences you can call in your projects

Sequence  | Action
------| ------
SheetAddRow   | Add a row of cells to a google Sheet
SheetGetRange | Read a Range of values form a Google Sheet

These sequences will only work if you performed a OAuth Authentication to Google first. To help you with this, the library provides a Shared action you can use in your Apps. 

## Shared Acion

.....

## Sample Application

You will find in this project a sample application using the ....

