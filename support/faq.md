# FAQ

### ANDROID:

#### Q1. Not able to create on-boardings or getting error like ‘model instance not valid’

Ans. Try logout from the application and sign in again

#### Q2. Application / Camera is lagging

Ans. Retry capturing the image. Rebooting the device can help sometimes.

#### Q3. Data saving at slow speeds / takes long duration

Ans. Check the Internet speed; [https://fast.com/](https://fast.com/). It depends on the internet speed. It works fine for speed >= 500kbps

#### Q4. Image taking long duration for uploading

Ans. Check the Internet speed; [https://fast.com/](https://fast.com/). It depends on the internet speed. It works fine for speed >= 500kbps

#### Q5. Contract page shows \`Problem with: \<message>\`

Ans. Either \`branch code\` from branch master or \`sub segment code\` from Subsegment masters have been altered post creating the on-boarding.&#x20;

#### Q6. Sometimes \`IP Cheque Details\` screen is visible and sometime not

Ans. The visibility depends on the subsegment masters.

**Q7. Getting the error "Please wait for a While" while generating the contract.**

Ans. App is not able  to capture location using google maps API. Please connect with the IT team.&#x20;

**Q7. Getting the error "RM ID doesn't exists" while creating the lead.**&#x20;

Ans. RM **** ID doesn't exist in LMS system, please connect with IT team.\


### BACKEND:

#### Q1. Where can I find logs for particular Application ID?

Ans. They can be found under a folder called log\_debug > \*onboarding id\*.txt, which is located in the backend application structure.

Onboarding Id are different from Signzy Application Id and can be easily found in the mongoDB or using the forever logs.\


#### Q2. How can I find the current server logs?

Ans. 1. Run the command

$ forever list

2\. Copy the logs location for the running application

3\. Run the command

$ tail  -f /path/to/the/log/file.log --lines 100

#### Q3. How can I take dump of mongo databases?

Ans. Run the command

$ mkdir dump\_directory

To create directory to dump databases.

$ mongodump --db indusInd -o path\_to\_dump\_directory/

$ mongodump --db indusIndFinnacle -o path\_to\_dump\_directory/ &#x20;

To dump databases in dump\_directory

#### Q4. How can I restore mongo databases?

Ans. First go to database by running

$ mongo

then select database indusind using below command

$ use indusInd

Then drop the DB using below command in order to restore new database.

$ db.dropDatabase()

Same you have to do for the other database also, run below commands

$ use indusIndFinnacle

$ db.dropDatabase()

Now go to the folder in much you have the mongoDB dump, make sure indusIndFinnacle and indusInd directories are present on the place where you run the below commands.

$ mongorestore --db indusIndFinnacle indusIndFinnacle

$ mongorestore --db indusInd indusInd.



### Application Flow:&#x20;

Q**1 :** Application not moving to In-process Section.

Ans:  Either of the following APIs would throw an error.

* Finnacle APIs
* Iworks API
* CRILC API
* Clari5 API
* SMS API
* E-Mail API
* Also, if all the AS's may not have signed the application.

Q2: How to change the frequency of reminder E-mails

* Use the Master of Email API and change the frequency and interval as per the requirement

#### Q3. At what stages e-mails are sent to Customer&#x20;

| S.No. | Current Subject                       | Subject to be sent                                                                           |
| ----- | ------------------------------------- | -------------------------------------------------------------------------------------------- |
| 1     | “Reminder Email 11 AM”                | Your IndusInd Current A/C application is awaiting approval from other Authorised Signatories |
| 2     | “Reminder Email For Signing Contract” | Reminder - Authorise your Current A/C opening application with IndusInd Bank                 |
| 3     | “ALL AS Signed Email”                 | Your IndusInd Current A/C application is forwarded for verification                          |
| 4     | "Web Link E-mail"                     | Authorise your Current A/C opening application with IndusInd Bank                            |
| 5     | “Account Opening E-mail” (Non-Tatkal) | Your IndusInd Current A/C \<No> is open and active for use                                   |
| 6     | “Account Opening E-mail” (Tatkal)     | Your IndusInd Current A/C \<No> is open and active for use                                   |

Q4. At what stages SMSs are sent to customer.

| **Contents**                                                     |
| ---------------------------------------------------------------- |
| **Contract Signing-Pending (Reminder)**                          |
| **Contract Signing- Approved by one but pending with other AUS** |
| **Contract Signing- Signed by all AUS**                          |
| **Opening of Current A/C post DVU approval**                     |

\
