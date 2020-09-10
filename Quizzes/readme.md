# Quizzes

This collection is not an API recipe. The Quizzes Collection provides examples of some of the most commonly used Quiz API routes.

## Documentation
https://docs.valence.desire2learn.com/res/quiz.html

## Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- Quizzes
  - View Quizzes
  - Create Quizzes
  - Edit Quiz Properties
  - Add Special Access

## OAuth 2.0 Scopes
- ensure that your OAuth2.0 app, and access token, have the following OAuth Scopes granted:
core:*:*
quizzing:quizzes:read
quizzing:access:read
quizzing:quizzes:create
quizzing:quizzes:write
quizzing:attempts:read

## Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with appropriate values for your Brightspace site.

- BrightspaceDomain
- accesstoken
- courseid - the orgunitid value of the course offering your quizzes are in
- learnerid - the userid value of the user you will provide "Special Access" to

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" and "WhoAmI" Collections.

Note: the leversion variable is pre-set to 1.48 in this Collection. The Special Access API routes require version 1.48+.

## Step 2 - Run the Requests in the Collection

This collection is not a recipe. It provides examples of some of the most commonly used Quiz API routes.

Note that the terms "Access" and "Special Access" are not refering to the same Brightspace concept. The "See which Users have Access to a Quiz" request informs us of which users will be able to gain access to the provided quiz. The "See who has Special Access to the Quiz" request provides a list of users that have a Special Access record defined. The Brightspace Special Access feature an Instructor or Admin can:
– Give selected learners a different due, start, and/or end date for the quiz.
– Assign special time limits, grace periods, or attempts allowed for the quiz.

## GET Answers Route is only available upon request

At the time this Collection is published please note that the "Get all of the Answers for a Quiz Attempt" route is only available to D2L customers upon request. Please contact the Developer Group within the Brightspace Developer Community to request access to this API route. We do plan to make this route generally available, but we don't yet have a specific timeframe for when this will occur.