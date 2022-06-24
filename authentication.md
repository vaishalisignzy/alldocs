# Authentication

## Login.py

It authenticates the user at login. The requested JSON contains the username and password that was entered on the login page.

If the JSON is empty then the logger will give an error message as “Login attempt failed due to invalid json.” and a response status of 400 Bad Request, and returns a JSON indicating an error with the message “invalid JSON syntax”, status “400” and name “Invalid JSON sent to /login”.

If any of the username or password fields are empty then the logger will give an error message as “Login attempt failed, username and password fields not present.” and a response status of 400 Bad Request, and returns a JSON indicating an error with the message “invalid JSON syntax”, status “400” and name “Invalid input parameters to /login”.

For a given username it will fetch the document containing all the details of that username if it exists in the collection “users”.

If the document is empty then the logger will give an error message “User login attempt failed due to wrong username: “ and a response status of 400 Bad Request, and returns a JSON indicating an error with the message “Username or password is incorrect.”, status “400” and name “Invalid Credentials”.

After verifying the username, it verifies the password and if password verification fails, the logger displays an error “User login attempt failed due to password mismatch: “ and a response status of 400 Bad Request and returns a JSON indicating an error with the message “Username or password is incorrect.”, status “400” and name “Invalid Credentials”.

After successful verification of the password, the logger displays a message “User Logged in: “ and creates the authorization token for that user.

If the token is empty then a response status of 500 Internal Server Error is generated and a JSON is returned indicating error with message “server error.”, status “500” and name “auth token generation error”.

If the token is successfully generated then it gets the name of the user and returns a response status 200 Ok and a JSON indicating “result" with the generated token, status as 200 and user's name.

## Authorization code

It will authenticate the user before every action.

It authenticates the user by verifying its authorisation token. If verification fails then the logger will give an error message displaying authentication failed for a particular action and a response status 401 Unauthorised, and returns a JSON indicating an error with message “Invalid Authentication.”, status “401” and name “Unauthorised request.”.

After successful verification user can perform its action.
