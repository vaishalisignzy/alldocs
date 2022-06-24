# The Fund Manager Object

The Fund Manager object is defined as below:

| Field                      | Type   | Description                                                         | Mandatory |
| -------------------------- | ------ | ------------------------------------------------------------------- | --------- |
| manager\_name              | string | name of the fund manager                                            | Y         |
| amc\_name                  | string | name of the AMC to which the fund manager belongs                   | Y         |
| amc\_code                  | string | code of the AMC to which the fund manager belongs                   | Y         |
| total\_years-of-experience | string | total number of years of experience of the fund manager             | O         |
| total\_schemes             | string | total number of schemes which are being managed by the fund manager | O         |
| total\_aum                 | string | total size of the AUM which is being managed by the fund manager    | O         |
| about\_me                  | string | a brief description about the fund manager                          | M         |
| created\_at                | string | time at which the fund manager object was created                   | Y         |
| modified\_at               | string | time at which the fund manager object was modified                  | Y         |
