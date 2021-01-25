# Brightspace Test Data Setup

This Postman Collection provides a series of Brightspace API Requests which create Brightspace data for the purpose of testing Brightspace features. This Collections focus is on testing for the Brightspace Work To Do Widget.

There is no one correct way to setup test data. This Collection is meant to provide a guide on how to setup Brightspace testing data in general. This Postman Collection performs the following tasks:
- Creates two Learner User Accounts
- Creates a Department, a Semester and a Course Template
- Creates five Course Offerings
- Enrolls the two Users into each of the Course Offerings
- Creates Assignments, Quizzes, Discussions, Surveys, Content and Checklists in the Course Offerings
  - Pre-Req code in these requests define a variety of Due Date and End Date values
- Creates a series of Content Modules and Topics
  - The last request creates a Content Topic which is a Quicklink to a Quiz that was previously created

## Documentation
https://docs.valence.desire2learn.com/

## Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- Assignments - Add/Edit Assignment Submission Folders
- Checklist - Manage Checklists
- Content - Manage Content
- Content - Create and Edit Modules and Topics
- Discussions - Manage Discussions
- Discussions - Add Forums and Topics
- Manage Courses - Create Courses Offerings and Templates
- Org Unit Editor - Can Create and Edit Org Units
- Org Unit Type Editor - Can Create and Edit Org Unit Types
- Quizzes - Create Quizzes
- Survey - Can Create Surveys
- Users - Create a User in the Database
- Users - Enroll '{The Learner Role that you will be using}'

## OAuth 2.0 Scopes
Ensure that your OAuth2.0 app, and access token, have the following OAuth Scopes granted:
- core:*:*
- checklists:checklist:write
- content:topics:write
- dropbox:folders:write
- enrollment:orgunit:create
- orgunits:course:create
- orgunits:coursetemplate:create
- quizzing:quizzes:read
- quizzing:quizzes:create
- surveys:surveys:read
- surveys:surveys:create
- role:detail:read
- users:userdata:create

## API Recipe

#### Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with appropriate values for your Brightspace site.

- BrightspaceDomain
- accesstoken
- leversion
- lpversion
- learnerroleid - RoleId that will be used for creating users. You can use the provided Create Users --> Get Roles request to determine the list of roles available.

Place your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" and "WhoAmI" Collections.

Note: the lpversion variable is pre-set to 1.30, and the leversion variable is pre-set to 1.51 in this Collection. These values can be automatically set by running the API Setup Calls --> Get Latest Version requests.

## Step 2 - Perform the Postman Runner

* Choose the "Brightspace Test Data Setup" Collection
* In the "Run Order" section select the requests you want perfomed.
* Click the "Brightspace Test Data Setup" button

## Step 3 - Review the results

The Runner will execute each request in the Collection. The results of the Runner will inform you, per request, if the call was successful (green) or not (red). You can also view the Console (bottom of the Runner Results interface, to view console.log messages (e.g. the OrgDefinedId values for the Users that were created).

