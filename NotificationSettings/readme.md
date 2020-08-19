# Notification Settings

This Collection allows the API update of Brightspace Notification Settings by a Service Account.

## Documentation
Official API Documentation for this collection is available here - https://docs.valence.desire2learn.com/res/user.html#user-notifications

## Permissions
The Role of the user calling these routes must have the following Brightspace Permission(s):
- Notifications -- Manage Other Users Notification Settings (API Only)

## API Recipe
#### Step 1 - Instantiate Collection Variables

To perform requests in this collection you need to update the following Collection Variables:

- accesstoken - Your Brightspace OAuth2.0 Access Token
- refreshtoken - Your Brightspace OAuth2.0 Refresh Token
- BrightspaceDomain - Your Brightspace Domain address (e.g. https://devcop.brightspace.com)

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" Collection. If you need to get a new Access Token then run the "Request a New Access Token and Refresh Token" request provided in this collection.

Note: the lpversion variable is pre-set to 1.28 in this Collection.

#### Step 2 - Run SETUP

Run, in sequence, the API Requests in this Collection's Setup folder.
- Get LP Version - this request will create a new Collection Variable, named lpversion, and will set it to the most up-to-date API version for the Brightspace LP domain
- Get SMS adn Email Carrier ID's - this request will retrieve the Brightspace Identifiers used to differentiate Notification methods. This call retrieves the Id's for SMS and Email and places them in Collection variables (SMSCarrierID & EmailCarrierID)

#### Step 3 - Create an Input CSV file
- This Collection takes in a Postman CSV input file, containing a list of UserNames, as input. A sample file is included in this package.
- The CSV file contains a single column. The first row is a header row which *must* contain the word "UserName". Each subsequent row must contain a single Brightspace UserName that you want the Collection to process.

#### Step 4 - Perform a Runner on the "Update Notification Settings for a User" folder.
- Use your CSV file as input for the Runner
