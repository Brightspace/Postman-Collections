# Distribute an Announcement
Create a News Announcement in each Org Unit provided in a CSV input file of OrgUnitId values.

## Documentation
https://docs.valence.desire2learn.com/res/news.html#post--d2l-api-le-(version)-(orgUnitId)-news-

## Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- News
  - See News
  - Add/Edit/Delete News
  - Change Display Author Information Setting

The API user must be enrolled in every Org Unit defined in the input file. This is most easily accomplished by having the API user's role to be "cascading".

## OAuth 2.0 Scopes
- ensure that your OAuth2.0 app, and access token, have the following OAuth Scopes granted:
core:*:*

## Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with appropriate values for your Brightspace site.

- BrightspaceDomain
- accesstoken

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" and "WhoAmI" Collections.

Note: the leversion variable is pre-set to 1.48 in this Collection.

## Step 2 - Gather the Data for your Announcement

The input data for the Announcement will be pulled from the following Collection Variables"
- Title
- BodyText or BodyHtml
- StartDate
- EndDate

There are two ways that you can populate these Collection Variables"

1. Manually enter your data in the Current Value field for each variable. Note that sample values are provided in the Initial Value field for each variable.
2. Pull the data from an existing News Item. Run the "Use an existing News Item as your Data Source" request. Prior to running this request you will need to update the OrgUnitId and NewsId Collection Variables to that of your source News Item.

## Step 3 - Modify the input.csv file

Edit the provided input.csv file.

The first row contains the Iteration Variable names. This should not be modified. For this example, the first row is: OrgUnitId

Each subsequent row in the file contains the unique OrgUnitId values which identify the Org Units the News Announcement should be created within. Modify the rows in the input.csv file so they contain values relevant to your Brightspace site.

## Step 4 - Perform the Postman Runner

When creating a News Item you have the option of including either basic text for the Body of the Announcement, or html content. This Collection contains a request for each option. Make sure you select the appropriate request (just run one of them... not both).

* Choose the Distribute an Announcement
* In the "Run Order" section, make sure you only have "Create a News Announcement - {Text or Html} Body" selected (checked)
* Click the "Data - Select File" button
* Find and select the CSV file with your input data
* Click the "Preview" button to confirm the formatting of your input data
* Click the "Run Distribute an Announcement" button

## Step 5 - Review the results

The Runner will execute each row (iteration) in the CSV file. The results of the Runner will inform you, per iteration, if the call was successful (green) or not (red).
