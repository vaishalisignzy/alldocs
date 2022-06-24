# The Fund Object

The Fund Object is defined as below:&#x20;

| Field                    | Type            | Description                                                                                                                                                        | Mandatory |
| ------------------------ | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------- |
| id                       | string          | unique id of the fund                                                                                                                                              | Y         |
| amc\_name                | string          | name of the amc which has launched the fund                                                                                                                        | Y         |
| amc\_code                | string          | unique code of the amc which has launched the fund                                                                                                                 | Y         |
| fund\_name               | string          | name of the fund                                                                                                                                                   | Y         |
| fund\_code               | string          | unique code of the fund                                                                                                                                            | Y         |
| fund\_manager            | array of object | see [**fund manager object**](the-fund-manager-object.md)****                                                                                                      | Y         |
| fund\_type               | enum            | <p>type of the fund with possible values <br>- open-ended<br>- close-ended</p>                                                                                     | Y         |
| fund\_category           | enum            | <p>category of the fund with possible values<br>- large-cap<br>- mid-cap<br>- small-cap<br>and so on...</p>                                                        | Y         |
| fund\_plan               | enum            | <p>plan of the fund with possible values <br>- growth<br>- IDCW</p>                                                                                                | Y         |
| expense\_ratio           | string          | expense ratio of the fund                                                                                                                                          | Y         |
| cash\_holding            | string          | cash holding of the fund                                                                                                                                           | N         |
| entry\_load              | string          | entry load of the fund                                                                                                                                             | Y         |
| exit\_load               | string          | exit load of the fund                                                                                                                                              | Y         |
| fund\_benchmark          | string          | benchmark index of the fund                                                                                                                                        | Y         |
| fund\_document           | string          | scheme document of the fund                                                                                                                                        | Y         |
| risk\_classification     | enum            | <p>risk classification of the fund which can have following values -<br>- Low<br>- Low to moderate<br>- Moderate<br>- Moderately High<br>- High<br>- Very High</p> | Y         |
| aum                      | string          | size of the fund                                                                                                                                                   | Y         |
| sector\_holding-summary  | array of object | see **** [**fund holding object**](the-fund-holding-object.md)****                                                                                                 | Y         |
| company\_holding-summary | array of object | see **** [**fund holding object**](the-fund-holding-object.md)****                                                                                                 | Y         |
| created\_at              | string          | time at which the fund object was created                                                                                                                          | Y         |
| modified\_at             | string          | time at which the fund object was modified                                                                                                                         | Y         |
