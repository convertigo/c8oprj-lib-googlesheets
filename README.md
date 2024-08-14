


# lib_GoogleSheet

The Google Sheet Connector for Convertigo


For more technical informations : [documentation](./project.md)

- [Installation](#installation)
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


## Mobile Library

Test and demo app to show Google Sheet capacities

### Shared Actions

#### DisplayGoogleDrivePicker

Displays the Google Drive fille picker to browse available spread sheets
This needs an API key to be configured in the symbols :

lib_GoogleSheet.picker.apikey.secret

The Api key can be found at : 

https://console.developers.google.com/apis/credentials?organizationId=22050485893&project=convertigo-form-builder






