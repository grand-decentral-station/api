# Permissions API

## Available Permissions Requests

- Email
- Contacts
- Calendar

These are the standard permissions. Every App that wants to provide an internal
API to its data can create its own permissions, e.g. your finances app can add a
»Finance Data Access Permission«**

## Internal API Communication

Data shared between apps internally has to be proxied through a GDS API.
The Proxy only validates the permissions. It does not validate the data
itself.

| &nbsp;   | &nbsp;                                       |
| -------- | -------------------------------------------- |
| Endpoint | /api_communication/:app1/:app2/:api_endpoint |
| Method   | GET, POST, PUT, DELTE                        |

### Parameters

### Parameters

| Parameter      | Value Type | Optioanl |
| -------------  | ---------- | -------- |
| permission_key | String     | False    |
| payload        | Array      | True     |


#### Example
```json
{
  "permission_key": "1a2b3c"
  "payload": ["whatever your api recieves"]
}
```

### Response
If the permission check fails:

HTTP-Status: 401

Otherwise the response of the App API will be returned
