# Get ERD

Returns a list of URLs for the ERDs of each customization attached to a Change Request.

## Request

__Name__

URL
:   https://<account id xxx>.restlets.api.netsuite.com/app/site/hosting/restlet.nl?script=customscript\_flo\_int\_change\_request\_api&deploy=1&actionType=getERD

HTTP Method
:   GET

### URL Parameters

__Name__ / __Value__

externalId
:   <external\_ticket\_id>

URL parameters are case sensitive and mandatory.

### Sample Request URL

```
https://tstdrv1715311.restlets.api.netsuite.com/app/site/hosting/restlet.nl?  
script=customscript_flo_int_change_request_api&deploy=1&actionType=getERD
```

### Request Headers

This API uses OAuth 1.0 type for its request headers and Token Based Authentication for user credentials. Header tokens should be encoded in HMAC SHA256.

### Format

Authorization: <_encoded authentication code_>

### Sample Request Header

```Authorization: OAuth oauth_consumer_key="xxx", oauth_nonce="xxx", oauth_signature="xxx", oauth_signature_method="HMAC-SHA256", oauth_timestamp="1698722057", oauth_token="xxx", oauth_version="1.0",realm="xxx"```

## Response

Returns a JSON format string.

### Object Definition

__Name__ / __Type__

status
:   string

message
:   string

data
:   Array of JSON object

### Data Object Definition

__Name__ / __Type__

id
:   string

name
:   string

scriptId
:   string

erdLink
:   string

### Response JSON Object

```
{  
    "status": success or failed,  
    "message": Server response message,  
    "data":[  
        {  
            "id": <customization id>,  
            "scriptId": <customization script id>,  
            "name": <customization name>,  
            "erdLink": <erd link>  
        }  
    ]  
}
```

### Response Messages

__Message__

"ERD retrieved successfully."
:   Successfully pulled a list of customizations and associated ERD links.

### Error Messages

__Message__

"Unable to load Change Request. External ID: xxxx"
:   There is an error with the change request.

Error messages are returned if any exceptions are encountered.

### Sample Response

```
{  
    "status": "success",  
    "message": "ERD retrieved successfully",  
    "data":[  
        {  
            "id": "75073",  
            "scriptId": "customdeploy1",  
            "name": "Another M/R 0 (Deployment)",  
            "erdLink": "https://tstdrv1715311.app.netsuite.com/c.TSTDRV1715311/suitebundle294336/  
            FLODocs%20Enterprise/FLOEntryScreens.html?STAGE=custframe&customizationid=75073"  
        }  
    ]  
}
```

## Development

The Change Request API is developed using a RESTlet with API version 2.1.

Script Name
:   Strongpoint Int Change Request API

Script ID
:   customscript\_flo\_int\_change\_request\_api

Filename
:   StrongpointIntegrationChangeRequestAPI.js
