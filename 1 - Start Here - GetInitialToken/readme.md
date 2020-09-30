# Get Initial Token Collection

The purpose of this collection is to provide a guide for generating an initial OAuth 2.0 Access Token and Refresh Token.

## Documentation
Official API Documentation for this collection is available here - https://docs.valence.desire2learn.com/basic/oauth2.html

## Brightspace Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- Manage Extensibility - Can Manage Extensibility

## API Recipe

#### Step 1 - Register your Brightspace OAuth 2.0 Application

In order to perform Brightspace API calls you require an API App. Follow these instructions to create an OAuth 2.0 API Application:

https://docs.valence.desire2learn.com/basic/oauth2.html#register-your-application

A video example is also available in this repository (Register an OAuth2 App.mp4).

#### Step 2 - Copy OAuth 2.0 Credentials to Postman

Edit this Collection, and update the Collection Variable values with the credentials of your new OAuth 2.0 App.

- callbackurl
- clientid
- clientsecret
- oauth2scope

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

#### Step 3 - Authenticate and get your Tokens.

1) While still Editing the Collection, select the Authorization tab.
2) Click the "Get New Access Token" button.
3) Click the "Request Token" button.
4) Login to Brightspace. (NOTE 1)
5) Copy and store the generated Access Token and refresh_token values. (NOTE 2)

A video example is also available in this repository (Get Initial Tokens.mp4).

NOTE 1 

There are some cases where you will need to redirect Postman to a Brightspace Login page that is not the default. To do so, follow these steps:
- Click "View"
- Click "Developer"
- Click "Show DevTools(Current Shell)". Doing so will pop up a Console tab.
- In the Console enter the following: window.location.href="{web address of the Brightspace Login page you require}"
  - e.g. window.location.href="https://learning.brightspace.com/d2l/login?noredirect=1"

NOTE 2

It is suggested that you store the Access Token and Refresh Token in either a Global or Environment variable in Postman so you can use them across multiple Postman Collections and Requests.
