# User API

The user API is a fundamental part of the GDS Platform and while every aspect of
the user account settings is managed by an GDS internal app, every third-party
application can request access to this data. The user data will be highly integrated
into a contact server, so it's possible to request quite sensitive data like an
adress or a telephone number.


## Auth

Every third party app has access to an authentication service that validates the
user account data.


| &nbsp;   | &nbsp;      |
| -------- | ----------- |
| Endpoint | /users/auth |
| Method   | POST        |


### Parameters

| Parameter  | Value Type | Optioanl |
| ---------- | ---------- | -------- |
| uuid       | String     | False    |
| password   | String     | False    |

#### Example

```json
{
  "uuid": "CrazyCatLady@arkhamasylum.com",
  "password": "CatLover12"
}
```

### Response

HTTP-Status: 200
```
{
  "auth": 1,
  "id": 12,
  "username": "CrazyCatLady",
  "email": "CrazyCatLady@arkhamasylum.com",
  "bio": "A cat a day keeps the doctor away"
}
```

HTTP-Status 401
```
{
  "auth": 0,
  "error": "Sorry this User/Password combination is unknown"
}
```