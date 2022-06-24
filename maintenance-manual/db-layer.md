# DB Layer

![](<../.gitbook/assets/image (3).png>)

### How to see the collections of a particular database.

To check the collections for a particular database use the show collections command as described below.

```bash
> show dbs
indusInd          0.078GB
indusIndFinnacle  0.006GB
local             0.000GB
persist           0.000GB
> use indusInd
switched to db indusInd
> show collections
Manager
Morphon
Onboarding
Work
corporateAccountCreation
corporateAccountFetch
criteriaOfFv
fvEmail
greenChannelMatrix
ldapLogin
leadCreation
leadPushed
leadReassignment
leadStatus
masterOfBranch
masterOfCard
masterOfCustomerProfiler
masterOfDakpd
masterOfDeclaration
masterOfEmail
masterOfEntityDocument
masterOfFormField
masterOfFv
masterOfModeOfOperation
masterOfOtherDocument
masterOfPincode
masterOfProduct
masterOfRm
masterOfRmDeclaration
masterOfSubSegment
moveToAccountOpened
moveToInProcess
openCifCheckPan
panVerification
savedData
sessionTokens
talisma
test
>

```

### Read inside a collection using the **.find()** command

```bash
> db.Onboarding.find().pretty().limit(2)
{
        "_id" : ObjectId("5bafbb3fc2226072280392be"),
        "merchantId" : "5bafbb3dc9d31919f3128d34",
        "managerId" : ObjectId("5bdca2cbebb0376bedb9d9b4"),
        "createdAt" : ISODate("2018-09-29T17:49:51.153Z"),
        "merchantUsername" : "d9c9mr7pyq",
        "merchantPassword" : "5bafbb3dc9d31919f3128d34",
        "merchantAuthToken" : "fU8KEJOn86FRbiK6O0WrgJh8vljzV61CEcD0eioDPhuB2h7JVrMIEPCiL2NDhvKr",
        "status" : "incomplete",
        "signzyAppId" : 18111991
}
{
        "_id" : ObjectId("5bafbfafc2226072280392f3"),
        "merchantId" : "5bafbfadc9d31919f3128d38",
        "managerId" : ObjectId("5bdca2c4ebb0376bedb9d9b3"),
        "createdAt" : ISODate("2018-09-29T18:08:47.067Z"),
        "merchantUsername" : "lxchimwtvs",
        "merchantPassword" : "5bafbfadc9d31919f3128d38",
        "merchantAuthToken" : "uVh3YRs5OI6oI9mfe6VU1T8JOomvGKgTDGk4IJ8s2Dma8FiGGof1FYzEJ9HjdjGQ",
        "status" : "dropped",
        "signzyAppId" : 18111992
}
>

```

The above commands will show the structure of each of the database entries.
