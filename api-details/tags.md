# Tags

## Create Tags

#### Input headers <a href="#input-headers" id="input-headers"></a>

| Property      | Value                                     |
| ------------- | ----------------------------------------- |
| Content-type  | application/json                          |
| Authorisation | Authorization header as per login request |

```
{
  "email": "Merchant's valid Email-Id",
  "phone": "Merchant's valid Phone Number",
  "name": "Merchant's Name",
  "tagType": ["Accepted Tag types"]
}
```

#### Input for Create Tags <a href="#input-for-create-tags" id="input-for-create-tags"></a>

Post request to: **/engine/merchants/:merchantId/tags**

Below table describes all the properties available in the request body.

| Property | Accepted values/format | Description                                                                           |
| -------- | ---------------------- | ------------------------------------------------------------------------------------- |
| email    | Email (String)         | A valid email to represent the Merchant                                               |
| phone    | String                 | Phone number of the Merchant                                                          |
| name     | String                 | Name of the Merchant. This can be an individual's or an entity's name                 |
| tagType  | Array of Strings       | This is an array that can be used to identify the relation of the Tag to the Merchant |

_Tag types will be validated against a pre-defined list_

_The default list is COMPANY, LIMITED LIABILITY PARTNERSHIP, ONE PERSON COMPANY, INDIVIDUAL, AUTHORISED SIGNATORY, DIRECTOR, OWNER, PARTNER, PROPRIETOR, REGISTERED PARTNER, UNREGISTERED PARTNER_

#### Expected Response <a href="#expected-response" id="expected-response"></a>

```
{
  "email": "Merchant's valid Email-Id",
  "phone": "Merchant's valid Phone Number",
  "name": "Merchant's Name",
  "tagType": ["Accepted Tag types"],
  "id": "Tag's id",
  "merchantId": "Merchant's id"
}
```

| Property   | Accepted values/format | Description                                                                           |
| ---------- | ---------------------- | ------------------------------------------------------------------------------------- |
| email      | Email (String)         | A valid email to represent the Merchant                                               |
| phone      | String                 | Phone number of the Merchant                                                          |
| name       | String                 | Name of the Merchant. This can be an individual's or an entity's name                 |
| tagType    | Array of Strings       | This is an array that can be used to identify the relation of the Tag to the Merchant |
| id         | String                 | An alphanumeric unique indentifier for Tag                                            |
| merchantId | String                 | The id of the Merchant, the tag belongs to                                            |
