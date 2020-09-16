# Bulk Enrollments

The purpose of this Collection is to provide a simple example of how to use the Postman Runner feature.

## Documentation
#### Official API Documentation for this Collection:
https://docs.valence.desire2learn.com/res/enroll.html#post--d2l-api-lp-(version)-enrollments-

## Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- Users - Enroll '{The role you plan to use}' <-- needed for each RoleId in your input file

## OAuth 2.0 Scopes
- ensure that your OAuth2.0 app, and access token, have the following OAuth Scopes granted:
enrollment:orgunit:create

## API Recipe
#### Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with appropriate values for your Brightspace site.

- BrightspaceDomain
- accesstoken

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" and "WhoAmI" Collections.

Note: the lpversion variable is pre-set to 1.28 in this Collection.

#### Step 2 - Modify the input.csv file

Edit the provided input.csv file.

The first row contains the Iteration Variable names. This should not be modified. For this example, the first row is: OrgUnitId,UserId,RoleId

Each subsequent row in the file contains three unique identifiers which are needed to create a Brightspace Enrollment. Modify the rows in the input.csv file so they contain values relevant to your Brightspace site.

#### Step 3 - Perform the Postman Runner

* Choose the Bulk Enrollments Collection
* In the "Run Order" section, make sure you only have "Post Create an Enrollment" selected (checked)
* Click the "Data - Select File" button
* Find and select the CSV file with your input data
* Click the "Preview" button to confirm the formatting of your input data
* Click the "Run Bulk Enrollments" button

#### Step 4 - Review the results

The Runner will execute each row (iteration) in the CSV file. The results of the Runner will inform you, per iteration, if the call was successful (green) or not (red).
