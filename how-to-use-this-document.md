---
description: Must read before exploring further
---

# How to use this document

1. Signzy will provide you a login credential to access the below mentioned API's. You need to provide the below-mentioned details to create your account with Signzy - \
   \
   a. Customer Name\
   b. Name\
   c. Email ID\
   d. Password\

2. Post receiving your credentials, refer to the "Authentication" Section to create your access token via using the Login API. You need to pass this authentication token in the request header in all API's\

3. You would need to create users (Users are customers of your product or service) using Create a User API which is mentioned in the "User Section". You can perform other CRUD functionalities using the APIs mentioned in the section. There are other supporting CRUD functionalities like "View User Details", "Delete a User" & "Update a User", refer "User" section under "User Management" for more details.\

4. Post creating a user, you need to "Enroll the User" using his face. You need to refer to "Enroll face" in the "Actions" tab in "USER MANAGEMENT". \

5.  As you have the user's face signature stored with you in your DB, you can perform authentication via face, search via face functionalities & update face functionalities whenever a user tries to use your service or product using a face biometric check. You need to refer to "Authenticate Face" in the "Actions" tab in "USER MANAGEMENT" or need to refer to "Search Face" in the "Actions" tab in "USER MANAGEMENT" as per your use case.\
    \
    Note - Authentication & Searching are very different functionalities. Authentication is done for the user when you are aware that this face belongs to this "username" while doing the authentication which results in a 1:1 match as the user is known beforehand. Refer request body of "Authenticate Face" in the "Actions" tab in "USER MANAGEMENT"

    \
    Search is done just on the basis of a face. During the search, you get to know that this face belongs to the database or not and you get a username in the response. The User is not known beforehand which results in a 1:N face match.\

6.  To check logs of the status of enrollment, search, update & authentication, refer to "Logs" under the "Event" section to understand the status in detail.\
    \
    \


    \
    \
    &#x20;
