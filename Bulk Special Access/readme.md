# Bulk Special Access

This Collection supports the creation of Special Access rules for provided Users across provided Quizzes, Assignments and Surveys. This Collection can be used in a Runner to apply Special Access rules in bulk.

## Documentation
#### Official API Documentation for this Collection:
* https://docs.valence.desire2learn.com/res/quiz.html#put--d2l-api-le-(version)-(orgUnitId)-quizzes-(quizId)-specialaccess-(userId)
* https://docs.valence.desire2learn.com/res/dropbox.html#put--d2l-api-le-(version)-(orgUnitId)-dropbox-folders-(folderId)-specialaccess-(userId)
* https://docs.valence.desire2learn.com/res/survey.html#put--d2l-api-le-(version)-(orgUnitId)-surveys-(surveyId)-specialaccess-(userId)

## Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
* Dropbox
  * See and Manage Dropbox
  * Add/Edit Folders
  * Set Special Access on Dropbox Folders
* Quizzes
  * Edit Quiz Properties
  * Add Special Access
* Surveys
  * Manage the Surveys Tool
  * Edit Survey Properties
  * Add Special Access

## OAuth 2.0 Scopes
- ensure that your OAuth2.0 app, and access token, have the following OAuth Scopes granted:
quizzing:quizzes:write
dropbox:folders:write
surveys:surveys:update

## Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with appropriate values for your Brightspace site.

- BrightspaceDomain
- accesstoken

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" and "WhoAmI" Collections.

Note: the leversion variable is pre-set to 1.48 in this Collection.

#### Define your Special Access Date Values
Special Access rules vary slightly between Quizzes, Assignments and Surveys. The Brightspace API supports these variances. For simplicity, this Collection is setup to only support the setting of Due Date, Start Date, and End Date values (which are the most commonly used Special Access settings). Please modify the Collection to match your specific requirements.

There are three variables in the Collection which you need to set:
* StartDate
* EndDate
* DueDate

These values support either a value of null or a UTC Date Time value (e.g. "2020-10-03T17:47:00.000Z"). Example values are included in the Collection. 

Note: If you are using date values, ensure you have double quotation marks at the beginning and end of the value. For a null value, just use null (with no quotation marks).

## Step 2 - Modify the input.csv file

Edit the provided input.csv file.

The first row contains the Iteration Variable names. This should not be modified. For this example, the first row is: ActivityType,OrgUnitId,ActivityId,UserId

* ActivityType = This value must be one of these supported values: Quiz, Assignment, or Survey
* OrgUnitId = The identifier for the Org Unit the Learning Activity is in
* ActivityId = The identifier of the specific Learning Activity
* UserId = The identifier of the user the Special Access rules will be applied to

Each subsequent row in the file contains four values that define the specific Learning Activity (Quiz, Assignment, or Survey) in the specific course that the Special Access rules will be applied to. Special Access is applied to a User, so a UserId is also required.

Modify the rows in the input.csv file so they contain values relevant to your Brightspace site.

## Step 3 - Perform the Postman Runner

* Choose the "Bulk Special Access" Collection
* In the "Run Order" section, make sure you select the following requests:
  * Pull in the Input Data
  * Quiz Special Access
  * Assignment Special Access
  * Survey Special Access
* Click the "Data - Select File" button
* Find and select the CSV file with your input data
* Click the "Preview" button to confirm the formatting of your input data
* Click the "Run Bulk Special Access" button

## Step 4 - Review the results

The Runner will execute each row (iteration) in the CSV file. The results of the Runner will inform you, per iteration, if the call was successful (green) or not (red).
