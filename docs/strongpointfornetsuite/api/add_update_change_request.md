# Add/Update Customizations in a Change Request

Add or update customizations and proposed customizations in a Change Request.

## Request

__Name__

URL
:   `https://<account id xxx>.restlets.api.netsuite.com/app/site/hosting/restlet.nl?script=customscript_flo_int_change_request_api&deploy=1`

HTTP Method
:   POST

### Request Body Object Definition

__Name__ / __Type__

actionType
:   string

externalId
:   string

customizations
:   Array of strings

proposedCustomizations
:   Array of strings

Request body names are case sensitive and mandatory. For the __actionType__ parameter, it is always a constant value, in this case __addCustomization__.

### Request Body Object

```
{  
    "actionType": "addCustomization",  
    "externalId": <external_ticket_id>,  
    "customizations": <array of customization internal ids>,  
    "proposedCustomizations": <array of proposed customization script ids>  
}
```

### Sample Request Body

```
{  
    "actionType": "addCustomization",  
    "externalId": "41df83f9db43001088391fc768961953",  
    "customizations": ["12345","23456"],  
    "proposedCustomizations": ["custrecord_test3","custrecord_test34"]  
} 
```

### Request Headers

This API uses OAuth 1.0 type for its request headers and Token Based Authentication for user credentials. Header tokens should be encoded in HMAC SHA256.

### Format

Authorization: `<_encoded authentication code_>`

### Sample Request Header

`Authorization: OAuth oauth_consumer_key="xxx", oauth_nonce="xxx", oauth_signature="xxx", oauth_signature_method="HMAC-SHA256", oauth_timestamp="1698722057", oauth_token="xxx", oauth_version="1.0",realm="xxx"`

## Response

Returns a JSON format string.

### Object Definition

__Name__ / __Type__

status
:   string

message
:   string

data
:   JSON object

### Data Object Definition

__Name__ / __Type__

customizations
:   Array of JSON objects

proposedCustomizations
:   Array of strings

### Customizations JSON Object

__Name__ / __Type__

internalId
:   string

scriptId
:   string

name
:   string

### Response JSON Object

```
{  
    "status": <response status>,  
    "message": <response message>,  
    "data": {  
        "customizations": [  
            <array of customization objects>  
        ],  
        "proposedCustomizations": [  
            <array of proposed customization script ids>  
        ]  
    }  
}
```

### Response Messages

__Message__

"Customizations / proposed customizations added successfully."
:   Successfully added or updated customizations and/or proposed customizations to the change request.

"No change detected."
:   Customizations/Proposed Customizations are already attached to the change request(for duplicate additions/updates).

### Error Messages

__Message__

"Unable to load Change Request. External ID: xxxx"
:   There is an error with the change request.

"Change Request update prohibited. Change Request status is xxxx"
:   The change request can not be modified because of the current status.

Error messages are returned if any exceptions are encountered.

### Sample Response

```
{  
    "status": "success",  
    "message": "Customizations / proposed customizations added successfully.",  
    "data": {  
        "customizations": [  
            {  
                "internalId": "510",  
                "scriptId": "custentity_fmt_customer_credit_on_hold",  
                "name": "Customer Credit On Hold (Entity Field)"  
            },  
            {  
                "internalId": "15305",  
                "scriptId": "custbody_cseg1",  
                "name": "QA 1491 final Custom Segment Respider (Body Field)"  
            },  
            {  
                "internalId": "6567",  
                "scriptId": "customscript_tax_bundle_maintenance",  
                "name": "Tax Bundle Maintenance (Scheduled Script)"  
            }  
        ],  
        "proposedCustomizations": [  
            "customer",  
            "custrecord_test3",  
            "custrecord_maria",  
            "custrecord_maria2",  
            "custrecord_test34"  
        ]  
    }  
} 
```

## Development

The Change Request API is developed using a RESTlet with API version 2.1.

Script Name
:   Strongpoint Int Change Request API

Script ID
:   customscript_flo_int_change_request_api

Filename
:   StrongpointIntegrationChangeRequestAPI.js
