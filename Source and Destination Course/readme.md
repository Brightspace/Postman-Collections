# Source and Destination Course

This Collection takes a Course Template as input. It then shows how to create "Source" course and "Destination" course children for the provided course template. Lastly, it initiates a Course Copy process to copy the components from the Source to the Destination.

## Official API Documentation for this Collection:
https://docs.valence.desire2learn.com/res/orgunit.html#structure
https://docs.valence.desire2learn.com/res/course.html#post--d2l-api-lp-(version)-courses-
https://docs.valence.desire2learn.com/res/course.html#post--d2l-api-le-(version)-import-(orgUnitId)-copy-

For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- Org Unit Editor - Has Access to the Manage Courses tool
- Manage Courses - Create Courses Offerings and Templates
- Import/Export/Copy Components - Copy Course Offering and Template Components
  - The calling user must be enrolled in both the Source and the Destination course.

#### OAuth 2.0 Scopes
- ensure that your OAuth2.0 app, and access token, have the following OAuth Scopes granted:
organizations:organization:read
orgunits:course:create
core:*:*

## API Recipe

#### Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with appropriate values for your Brightspace site.

- accesstoken - Your Brightspace OAuth2.0 Access Token
- BrightspaceDomain - Your Brightspace Domain address (e.g. https://devcop.brightspace.com)

- templatecode - the OrgUnitCode value for your Course Template
- semestercode - the OrgUnitCode value for your Semester (if you don't have one then enter NULL)

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" and "WhoAmI" Collections. 
Note: the lpversion variable is pre-set to 1.28 in this Collection.
Note: the leversion variable is pre-set to 1.46 in this Collection.

#### Step 2 - Get the Template and Semester OrgUnitId values

The Brightspace API typically relies on Id values. The assumption made in this recipe is that the OrgUnitCode values are known. The following calls allow you to get an OrgUnitId value from an OrgUnitCode value.

Call "Locate your Course Template by OrgUnitCode" to populate the templateid value.

Call "Locate your Semester by OrgUnitCode" to populate the semesterid value.

#### Step 3 - Create the Course Offerings

Run the "Create a Source Course Offering"
Run the "Create a Destination Course Offering"

#### Step 4 - Perform the Copy Process

Run the "Copy Content from Source to Destination"

This call, when successful, will return a Job Token value. The Copy process is a back-end service which, depending on the amount of content in the Source, may take some time. 

The returned Job Token can be used to check the status of the Copy. Check the Related Routes folder.
