
# Write users extended attributes

Required API Permissions:  User.ReadWrite.All


[Azure Documentation for this call](https://learn.microsoft.com/en-us/graph/extensibility-overview?context=graph%2Fapi%2F1.0&preserve-view=true&tabs=http)


| Environment Variable    | Description                                | 
|-------------------------|--------------------------------------------|
| USER_ID                 | The uuid of the user                       | 
| ACCESS_TOKEN            | A valid access token                       | 


```
curl --location --request GET "https://graph.microsoft.com/v1.0/users/$USER_ID?$select=id,displayName,onPremisesExtensionAttributes" \
--header 'Authorization: Bearer $ACCESS_TOKEN' \
```


## Response

```
{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users(id,displayName,onPremisesExtensionAttributes)/$entity",
    "id": "63f6124c-e647-4ab1-8ccb-287be982da02",
    "displayName": "unknown",
    "onPremisesExtensionAttributes": {
        "extensionAttribute1": "TESTVALUE-1234",
        "extensionAttribute2": "TESTVALUE-1234",
        "extensionAttribute3": null,
        "extensionAttribute4": null,
        "extensionAttribute5": null,
        "extensionAttribute6": null,
        "extensionAttribute7": null,
        "extensionAttribute8": null,
        "extensionAttribute9": "ok-test",
        "extensionAttribute10": null,
        "extensionAttribute11": null,
        "extensionAttribute12": null,
        "extensionAttribute13": null,
        "extensionAttribute14": null,
        "extensionAttribute15": null
    }
}
```


## Error Response Example


```
{
    "error": {
        "code": "Request_ResourceNotFound",
        "message": "Resource '73f6134c-e647-4ab1-8ccb-287be982da02' does not exist or one of its queried reference-property objects are not present.",
        "innerError": {
            "date": "2023-02-14T11:10:50",
            "request-id": "c6bde806-1a0d-4d39-a3f1-1b666b092737",
            "client-request-id": "c6bde806-2a0d-4d39-a3f1-2b666b092737"
        }
    }
}

```