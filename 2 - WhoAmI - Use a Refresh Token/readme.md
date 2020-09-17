# WhoAmI

The purpose of this Collection is to provide a basic introduction on how to retrieve a new OAuth 2.0 Access Token based on a valid Refresh Token. Once this is done, the collection shows how you can use the Access Token to perform the Brightspace API WhoAmI call.

## Documentation
Official API Documentation for this Collection:
https://docs.valence.desire2learn.com/basic/oauth2.html
https://docs.valence.desire2learn.com/res/user.html?highlight=whoami#get--d2l-api-lp-(version)-users-whoami

## Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- n/a (you just need an Access Token, Refresh Token, and a Brightspace User account)

## API Recipe
#### Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with the credentials of your new OAuth 2.0 App.

- BrightspaceDomain
- accesstoken
- refreshtoken
- clientid
- clientsecret
- oauth2scope

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" Collection.

Note: the lpversion variable is pre-set to 1.28 in this Collection.

#### Step 2 - Request a New Access Token and Refresh Token

Run the Request a New Access Token and Refresh Token request. This request takes an existing valid Refresh Token and uses it to retrieve a new Access Token and a new Refresh Token. The Access Token can then be used to perform Brightspace API calls for the next 4,800 seconds. The new Refresh Token is then stored and used for the next time you call this request.

This Request stores the Access Token and the Refresh Token in collection varibales.

#### Step 3 - Call Get WhoAmI

Run the Request "Get WhoAmI". You should receive a 200 OK message with a WhoAmIUser JSON response informing you about your Brightspace User account.

