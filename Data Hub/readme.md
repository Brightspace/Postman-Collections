# Data Hub

This Postman Collection outlines two key API routes which allow for the discovery and download of Brightspace Data Sets.

## Documentation
https://docs.valence.desire2learn.com/res/dataExport.html

## Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- Brightspace Data Sets - Can access Brightspace Data Sets

## OAuth 2.0 Scopes
- ensure that your OAuth2.0 app, and access token, have the following OAuth Scopes granted:
datahub:dataexports:download
datahub:dataexports:read

## API Recipe

#### Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with appropriate values for your Brightspace site.

- BrightspaceDomain
- accesstoken

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" and "WhoAmI" Collections.

Note: the lpversion variable is pre-set to 1.28 in this Collection.

#### Step 2 - Get your List of Data Sets

Run the Request "Get List of Data Set Plugins".

This request returns the list of Brightspace Data Sets that are enabled within your Brightspace's Data Hub.

This request contains JavaScript code in its Tests. This code scans through the list of data sets and grabs the PluginId values for specific data sets as defined in the code. The script stores plugin values for the following Data Sets:
- Organizational Units
- Users
- User Enrollments
- Organizational Units Differential
- Users Differential
- User Enrollments Differential

This script can be customize by adding your own "case" statement for each Data Set you want to download.

case "{Name of the Data Set}":
	pm.collectionVariables.set("{YourVariableName}", Item.PluginId);
	break;

#### Step 3 - Download your Data Sets

Run, in sequence, the remaining Requests. Note that there is one Request per Data Set Plugin defined in the Tests code from the previous step.

These requests return a File Stream of a zip file containing a Data Set. The easiest way to download this zip file is to NOT click the Postman Send button, but rather to click the down arrow beside the word "Send" and to instead select "Send and Download".