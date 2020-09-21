# External Learning Tools - LTI 1.1

## Documentation
https://docs.valence.desire2learn.com/res/lti.html

## Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- External Learning Tools
  - Manage External Learning Tools Configuration
  - Manage and Delete External Learning Tool Links
  - Manage External Learning Tool Providers
  - Create Quicklinks from available External Learning Tools links
- Content
  - View Course Content
  - Manage Content
  - Create and Edit Modules and Topics

## OAuth 2.0 Scopes
- ensure that your OAuth2.0 app, and access token, have the following OAuth Scopes granted:
core:*:*
content:modules:read

## Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with appropriate values for your Brightspace site.

- BrightspaceDomain
- accesstoken
- courseid - the orgunitid value of the course offering your quizzes are in

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" and "WhoAmI" Collections.

Note: the leversion variable is pre-set to 1.48 in this Collection.

Note: the lpversion variable is pre-set to 1.23 in this Collection.

## Step 2 - Run the Requests in the Collection