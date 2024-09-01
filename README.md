# User Management Service 

## Responsibilities:

Authentication: Validate user credentials and generate authentication tokens.
Authorization: Control access to resources based on user roles.
Profile Management: Handle user details, including personal information and preferences.
Password Management: Support password resets and updates.

## APIs:

POST /users/register
Description: Register a new user.
Request Body: { "username": "string", "password": "string", "email": "string" }
Response: { "userId": "string", "message": "Registration successful" }

POST /users/login
Description: Authenticate a user and provide a token.
Request Body: { "username": "string", "password": "string" }
Response: { "token": "string", "expiresIn": "number" }

POST /users/logout
Description: Log out the user and invalidate the token.
Request Body: { "token": "string" }
Response: { "message": "Logout successful" }

GET /users/{userId}
Description: Retrieve user profile information.
Response: { "userId": "string", "username": "string", "email": "string", "roles": ["string"] }

PUT /users/{userId}
Description: Update user profile information.
Request Body: { "email": "string", "roles": ["string"] }
Response: { "message": "Profile updated" }

POST /users/password/reset
Description: Request a password reset link.
Request Body: { "email": "string" }
Response: { "message": "Reset link sent" }
