
## Aquire an access token with clientId and clientSecret

### Azure Oauth2 Client Credentials Grant

[Azure Documentation for this call](https://learn.microsoft.com/en-us/azure/active-directory/develop/v2-oauth2-client-creds-grant-flow)

| Environment Variable    | Description                                | 
|-------------------------|--------------------------------------------|
| AZ_TENANT               | The Azure tenant                           | 
| AZ_CLIENT_ID            | The client id of the app registration      | 
| AZ_CLIENT_SECRET        | The client secret of the app registration  | 


```
curl --location --request POST "https://login.microsoftonline.com/$AZ_TENANT/oauth2/v2.0/token" \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode "client_id=$AZ_CLIENT_ID" \
--data-urlencode "client_secret=$AZ_CLIENT_SECRET" \
--data-urlencode 'scope=https://graph.microsoft.com/.default' \
--data-urlencode 'grant_type=client_credentials'
```

## Response

```
{
    "token_type": "Bearer",
    "expires_in": 3599,
    "ext_expires_in": 3599,
    "access_token": "eyJ0eXAiOiJKV1QiLCJub25jZSI6Imw5NUpkUU5LaXNlSEY5bm5KRU9mekU0aElZNWJFZHRKSWZUTEp0VkVKYU0iLCJhbGciOiJSUzI1NiIsIng1dCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiJodHRwczovL2dyYXBoLm1pY3Jvc29mdC5jb20iLCJpc3MiOiJodHRwczovL3N0cy53aW5kb3dzLm5ldC82MmM3YmFlYS04MGJkLTRlNmMtOGYyNy0wNjZmOTNkM2VkYTEvIiwiaWF0IjoxNjc2MzY3NzM3LCJuYmYiOjE2NzYzNjc3MzcsImV4cCI6MTY3NjM3MTYzNywiYWlvIjoiRTJaZ1lOakp5ZGltcXpoN2wwTGhoN25zQ2k2ekFRPT0iLCJhcHBfZGlzcGxheW5hbWUiOiJVcGRhdGVVc2VyV2l0aEpXVCIsImFwcGlkIjoiNGU0YzlkNjAtMzM1Ni00MGJlLTk0YTUtZWQ4YjU1NTg3NjE5IiwiYXBwaWRhY3IiOiIxIiwiaWRwIjoiaHR0cHM6Ly9zdHMud2luZG93cy5uZXQvNjJjN2JhZWEtODBiZC00ZTZjLThmMjctMDY2ZjkzZDNlZGExLyIsImlkdHlwIjoiYXBwIiwib2lkIjoiYzFhNTUwOWUtZDVhOS00OTYxLTg4OGEtODI1MWYyOTllYTNhIiwicmgiOiIwLkFTUUE2cnJIWXIyQWJFNlBKd1p2azlQdG9RTUFBQUFBQUFBQXdBQUFBQUFBQUFBa0FBQS4iLCJyb2xlcyI6WyJVc2VyLlJlYWRXcml0ZS5BbGwiXSwic3ViIjoiYzFhNTUwOWUtZDVhOS00OTYxLTg4OGEtODI1MWYyOTllYTNhIiwidGVuYW50X3JlZ2lvbl9zY29wZSI6IkVVIiwidGlkIjoiNjJjN2JhZWEtODBiZC00ZTZjLThmMjctMDY2ZjkzZDNlZGExIiwidXRpIjoiTXFQejRmZ0dYMHlPdU9lczNWWVdBQSIsInZlciI6IjEuMCIsIndpZHMiOlsiMDk5n2ExZDAtMGQxZC00YWNiLWI0MDgtZDVjYTczMTIxZTkwIl0sInhtc190Y2R0IjoxNjc0NTY4MjE3LCJ4bXNfdGRiciI6IkVVIn0.UjysdHGN87eB2gPrDr3QERt_4b58x1Aw6Uuv9PV2ypDOC8WuSSbASMPuWQ1ewv_wT0bfRuSv6snhFLyqTP0mGef1b_sD4GcqnU-XkQyFaYZNaVD0pVFXP6a4YmH2JMVIdaWwNWa8PxwnK8WkU2u3X1AysQGpLxfgXGXRYdbYfyS97hEd9OWtlCwT9FIMv8bINVwC4bvHLsO3fB55yqMpQyHysC4-6_JXUzMH2DSMZzJ8YRhUE0Blidwiz8Z2Tc2VEzjFqXU83U2Qp7KvxvjzVZY8lDEcle8_49hm7KGXifRINupEZGaJDaJfLguuzeU6R5RbDqObBv-Fgt6ZVX1ISg"
}
```

## Error Response Example

```
{
    "error": "invalid_scope",
    "error_description": "AADSTS1002012: The provided value for scope https://graph.microsoft.com/.defaultd is not valid. Client credential flows must have a scope value with /.default suffixed to the resource identifier (application ID URI).\r\nTrace ID: 79168b0f-cc19-4f7f-8859-623628460a00\r\nCorrelation ID: 493c3c50-0a91-42f3-8fb4-c8b7a393ba24\r\nTimestamp: 2023-02-14 10:16:14Z",
    "error_codes": [
        1002012
    ],
    "timestamp": "2023-02-14 10:16:14Z",
    "trace_id": "74168b0f-cc19-4f7f-8859-623628460a00",
    "correlation_id": "493c3c50-0a91-42f3-8fb4-c7b8a393ba24"
}
```
