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
- courseid - the orgunitid value of the course offering you want the API requests to interact with. This Collection will create Share an LTI Tool Provider with this course, create an LTI Link in this course, and create a content link to your LTI Link in this course.

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" and "WhoAmI" Collections.

Note: the leversion variable is pre-set to 1.48 in this Collection.

Note: the lpversion variable is pre-set to 1.23 in this Collection.

## Step 2 - Run the Requests in the Collection

The Requests in this Collection have been seperated into two folders:

#### Organization Tool Provider

1. Retrieve your Organization Id - Run this request to retrieve your Organization Id value. It will get stored in a Collection Variable named orgid.
2. Create an Organization Tool Provider - Running this request will create a new LTI Tool Provider in your Organization Org Unit. Review the Body of the request and modify it to your needs.
3. Share the Tool Provider to your Course - This route will make your Organization Tool Provider available for use in your course (that you defined with your courseid value).

#### Place an LTI Link into Content

1. Create a LTI Link - Run this request to create a new LTI Link in your course. Review the Body of the request and modify it to your needs.
2. Create a Quicklink for your LTI Link - Brightspace uses Quicklinks as a way of defining an LTI Link in a single URL. A Quicklink is required if you want to place your LTI Link in a location (a Content topic being the most common scenario) where learners can launch it. The outcome of this request is that the Quicklink value will be stored in a Collection Variable named "publicurl".
3. Create a Content Module - This request creates a new Content Module in your Course. If you already know the Module you want your LTI link placed within, then you don't need to run this request. Instead, place that module's id into a Collection Variable named "ltimoduleid".
4. Create a Content Topic with the LTI Quicklink - Running this request will place a new Content Topic in your Content Module using your Quicklink value as the topic's URL value.