# Create a Course, a User, and an Enrollment

This Postman Collection provides a recipe for creating a new Course Offering, and a new Brightspace User. Lastly, it enrolls the new User into the new Course Offering.

## Documentation
#### Official API Documentation for this Collection:
https://docs.valence.desire2learn.com/res/course.html#post--d2l-api-lp-(version)-courses-
https://docs.valence.desire2learn.com/res/user.html#post--d2l-api-lp-(version)-users-
https://docs.valence.desire2learn.com/res/enroll.html#post--d2l-api-lp-(version)-enrollments-

## Permissions
For this Collection your Brightspace user account will require the following Brightspace Permission(s):
- Manage Courses - Has Access to the Manage Courses tool
- Manage Courses - Create Courses Offerings and Templates
- Users - Create a User in the Database
- Users - Enroll '{The role you plan to use}'

## OAuth 2.0 Scopes
- ensure that your OAuth2.0 app, and access token, have the following OAuth Scopes granted:
core:*:*
users:userdata:create
enrollment:orgunit:create

## API Recipe
#### Step 1 - Populate Collection Variables

Edit this Collection, and update the Collection Variable values with appropriate values for your Brightspace site.

- BrightspaceDomain
- accesstoken
- refreshtoken

It is recommended to paste your values in the "Current Value" field of each Collection Variable.

Note: accesstoken and refreshtoken retrieval is explained in the "Get Initial Token" Collection. If you need to get a new Access Token then run the "Request a New Access Token and Refresh Token" request provided in this collection.

Note: the lpversion variable is pre-set to 1.28 in this Collection.


#### Step 2 - Prepare to Create a Course Offering

A Brightspace Course Offering is an Org Unit which requires a Parent Course Template org unit. It does not require, but it is recommended to have, a Parent Semester org unit. This example does not require a Semester parent.

Determine the OrgUnitId of the Course Template org unit that will be the parent for your new Course Offering. Place its OrgUnitId value in the following Collection variable:
- CourseTemplateId

Note: The Brightspace Org Unit Editor may be required to determine the above information.

Note: You should explore (and update if you want) the input JSON Body for this call. The input JSON needs to align with this documentation: https://docs.valence.desire2learn.com/res/course.html#Course.CourseOffering

#### Step 3 - Create a New Course Offering

Run the Create a Course Offering request. 

You should get a 200 OK, plus a JSON block detailing your new Course Offering.

This Request stores the OrgUnitId of the new Course Offering in the CourseOfferingId collection varibale.

#### Step 4 - Prepare to Create a New User

When a Brightspace User is created a RoleId value is required. This RoleId value is used to enroll the new user into the Organization Org Unit.

Determine the RoleId that you want to assign to this User. Place this RoleId value in the following Collection variable:
- RoleId

Note: The Brightspace Roles and Permissions tool may be required to determine this value.

Note: You should explore (and update if you want) the input JSON Body for this call. The input JSON needs to align with this documentation: https://docs.valence.desire2learn.com/res/user.html#User.CreateUserData

#### Step 5 - Create a New User

Run the Create a User request. 

You should get a 200 OK, plus a JSON block detailing your new User.

This Request stores the UserId of the new User in the UserId collection varibale.

#### Step 6 - Enroll your User into your Course

Run the Enroll User into the Course Offering request.

You should get a 200 OK, plus a JSON response confirming the Enrollment data.
