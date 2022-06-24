# Delete Verification Data

## [Entity Onboarding Delete Request](https://docs-preproduction.signzy.tech/entity-onboarding-delete#right-to-left-support) <a href="#right-to-left-support" id="right-to-left-support"></a>

You will need to [login](https://docs-preproduction.signzy.tech/) before sending request. You are required to pass the access token received from the login call, as authorization header in the Entity Onboarding DELETE Request request along with essentials and task

Use the following exchange parameters for Entity Onboarding Delete Request

```

// Data exchange
For Test Credentials
// POST :: https://preproduction.signzy.tech/api/v2/patrons/..your-patron-id../entityonboardings
For Production Credentials
// POST :: https://signzy.tech/api/v2/patrons/...patronID.../entityonboardings

// patron ID is returned as userId parameter of login request.
// Headers
{
'Authorization': '...access token (returned as id field of login request)...',
'Content-type': 'application/json'
}

// Request data
{
	"task": "deleteRequest",
	"essentials": {
        "requestId": "..requestId...."
    }
}

// Output response
{
    "result": {
        "message" : "User with that RequestId is deleted",
        "statusCode" : 200
    }
}

                  
```

[![Run in Postman](https://run.pstmn.io/button.svg)](https://www.getpostman.com/run-collection/1f2f9ccbe8bba3c21971)

Code samples corresponding to the above example for creating a request for Entity Onboarding DELETE Request\
