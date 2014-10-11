# Background Job API

Every app has to execute a time consuming task now and then.

## Adding a background job to the queue

| &nbsp;   | &nbsp;          |
| -------- | --------------- |
| Endpoint | /background_job |
| Method   | POST            |

### Parameters

| Parameter   | Type    | Optional |
| ----------- | ------- | -------- |
| path        | String  | False    |
| retry_count | Integer | True     |

#### Example

```json
{
  "path": "/usr/bin/rake test:db",
  "retry_count": 3
}
```

### Response
Status: 200
```json
{
  "id": 9120,
  "path": "/usr/bin/rake test:db",
  "retry_count": 3
}
```

## Removing a background job from the queue

| &nbsp;   | &nbsp;                  |
| -------- | ----------------------- |
| Endpoint | /background_job/:job_id |
| Method   | DELETE                  |

### Parameters

NONE

#### Example

```sh
$ curl -X DELETE http://localip/api/v1/background_job/1
```

## Response

Status: 204
