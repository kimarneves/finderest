# finderest
This is a repository for CPSC 2261 Project in Summer 2015 (Langara College)

This is a simple project to demonstrate how Node.js can be used to implement a REST API and Angular.JS + Bootstrap to implement a F/E application. Technologies in use: Node.js, Angular.JS, Bootstrap and Mongo DB.

This project implements an application where user can register and create groups or find groups with activities in similar interests. Although B/E has a list of functionalities that were not used by F/E, the application concentrates in using the following REST API routes:
- PUT /create/users: create new users in the system.
- POST /user/login: establishes a session for an existing user
- GET /user/:email (Existing user): retrieve profile of an existing user by providing the user e-mail registered.
- GET /group/:group-id/name: retrieve the name of an existing group based on its id.
- POST /user/session/validate: validate a session by check if its token is registered in the Mongo DB database.
- GET /user/:email/groups: retrieve all user for a given user.
- GET /groups: retrieves all groups registered in the system.
- GET /group/:group-id: retrieves the information about an specific group based on its group id.
- POST /update/user/:email: updates the information of an existing user.
- PUT /create/groups: create a new group in the system.
- POST /update/group/:group-id: updates the information regarding a group in the system.
- DELETE /user/:email: delete an user from the system. (Not implemented in F/E)
- DELETE /group/:group-id: delete a group from the system. (Not implemented in F/E)
- GET /group/by_owner/:email: retrieves all groups owned by an user
- POST /user/logout: removes an existing session token from the list of valid entries in the server.

Project structure:
+ Backend: contain a node.js file that implements the RESTful API.
+ Frontend: contain the Angular.JS application F/E files.
+ Jmeter: contains the jmx jMeter files testing the happy tree and common scenarios for the RESTful API usage.
+ Documentation: scratch of the documentation used during development.

Limitations:
- B/E error validation is very limited and close to non-existing and needs to be improved. Some basic validation is missing so B/E crashes when trying to do some operations like retrieving information of a non-existing user.
- The session authentications is limited and in order to correctly implement additional security the messages should be modified to include the token in the header and REST implementation should check this token for every transaction (like it is done by IMGUR RESTful API).
- The implementation of a session token and its validation was done in a pretty basic way just to test the possibility by the development team.
- All B/E response messages need to be reformatted to follow a common pattern, e.g. { "status":"success|fail", "data": ...}