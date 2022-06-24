# Logging Out

To logout you simply need to call the logout route with the access token in 'access\_token' query parameter or as 'Authorization' header.

POST :: /api/backopsusers/logout?access\_token=:access-token-to-delete

// Response is 204 status code with no content, indicating the Access-token has been deleted.
