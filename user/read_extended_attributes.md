
# Read the users extended attributes

Required API Permissions:  User.Read.All

[Azure Documentation for this call](https://learn.microsoft.com/en-us/graph/extensibility-overview?context=graph%2Fapi%2F1.0&preserve-view=true&tabs=http)


| Environment Variable    | Description                                | 
|-------------------------|--------------------------------------------|
| USER_ID                 | The uuid of the user                       | 
| ACCESS_TOKEN            | A valid access token                       | 


```
curl --location --request PATCH "https://graph.microsoft.com/v1.0/users/$USER_ID" \
--header "Authorization: Bearer &ACCESS_TOKEN" \
--header 'Content-Type: application/json' \
--data-raw '{
    "onPremisesExtensionAttributes": {
        "extensionAttribute9": "test123"
     
    }
}'
```


## Response

The api call returns an 204 - No Content on success


## Error Response Example


```
{
    "error": {
        "code": "Request_ResourceNotFound",
        "message": "Resource '73b6134f-e647-4af1-8ccb-287be982da1' does not exist or one of its queried reference-property objects are not present.",
        "innerError": {
            "date": "2023-02-14T11:04:23",
            "request-id": "4a1926cd-569e-492d-aa94-104fa72d8621",
            "client-request-id": "4a1926cd-569e-492d-aa94-104fa72d8622"
        }
    }
}

```