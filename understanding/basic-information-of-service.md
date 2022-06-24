---
description: >-
  The purpose of this document is to give a basic understanding of how to call
  the decision engine for the User data collected after the onboarding is
  completed successfully.
---

# Basic Information of Service

### **Basic Flow of calling Decision Engine :**

**Step 1: Backops User Login**

The user logs into the Backops portal with valid credentials given to him/her. Backops Portal is a platform where the auditor checks the applications basis different tests run on an application and takes a decision whether to accept or reject an application.

**Step 2:  Create a new merchant**

This API is used to create merchants who are to be onboarded. The user data collected after the onboarding is done is then pushed to the decision engine.

**Step 3:  Merchant User Login**

This API is used to get the authentication token of the particular merchant and other meta-data like basic details, and _landingPage_ array which will be required in further API calls

**Step 4: Decision Engine Configuration**

The integration takes place at the application level. The term "Check" is used in our decision engine which is multi level. The 0 level check is the one which directly runs on user data and gives the evaluation result. Higher level checks are n level checks which give the decision basis all the 0 to n-1 level checks. Higher level checks are basically the permutation and combinations of all the 0 to n-1 level checks.

**Step 5: Calling Decision Engine with user data**

After the user data is collected, it is pushed into our decision engine on which all the checks run which give the final output.

This endpoint runs the configured checks, decisions and stores results according to the merchant's data. This must be called after the merchant has finished onboarding.

**Step 6: Response**

After the data is pushed into our decision engine, checks run and we get the response. The response consist of the output we get each level up until the higher level checks. In addition to that the response also gives the details of the variable on which checks are being run.





****
