# Quick Run Test Plan

This endpoint triggers a "fast run" for a specific test plan, allowing the execution of selected scenarios in specific environments. The user must have the `PLAN_RUN` authority to access this endpoint.

***

### Endpoint Information

* **URL**: [`https://gateway.testinium.io/queue/quickRun`](https://gateway.testinium.io/queue/quickRun)
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***

### Request Body

The request body specifies the test plan (`planId`) to be executed by a given user (`userId`). It also contains a list of `scenarioEnvironmentPairs`, where each pair defines a specific scenario and the environment in which it should run.

```json
{
  "planId": 12345,
  "userId": 67890,
  "scenarioEnvironmentPairs": [
    {
      "scenarioId": 111,
      "environmentId": 222
    },
    {
      "scenarioId": 333,
      "environmentId": 444
    }
  ]
}
```

### Request Fields

| Field           | Type   | Description                                                    |
| --------------- | ------ | -------------------------------------------------------------- |
| plan`Id`        | `Long` | The  ID of the test plan to execute.                           |
| user`Id`        | `Long` | The ID of the user who triggers plan.                          |
| `scenarioId`    | `Long` | The ID of the scenario to execute.                             |
| `environmentId` | `List` | The ID of the environment where the scenario will be executed. |

***

### Response

This response indicates that the operation was completed successfully, with no additional data returned.

```json
{
    "data": null,
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

### Response Fields

| Field          | Type    | Description                                                                       |
| -------------- | ------- | --------------------------------------------------------------------------------- |
| data           | Object  | The payload of the response. In this case `null` since no extra data is returned. |
| result         | Object  | Contains details about the outcome of the operation.                              |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                    |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                             |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |
|           |                         |                                                  |

***

### Application Error Codes

<table><thead><tr><th>Code</th><th>Error Message</th></tr></thead><tbody><tr><td><pre><code><strong>10000
</strong></code></pre></td><td><pre><code>"Plan not found!"
</code></pre></td></tr><tr><td><pre><code>10002
</code></pre></td><td><pre><code>User not found!
</code></pre></td></tr></tbody></table>

### Example Request

```bash
curl 'https://gateway.testinium.io/queue/quickRun' \
  -H 'accept: application/json, text/plain, */*' \
  -H 'authorization: Bearer <token>' \
  -H 'content-type: application/json' \
  --data-raw '{"planId":<planId>,"userId":<userId>,"scenarioEnvironmentPairs":[{"scenarioId":<scenarioId>,"environmentId":<environmentId>},{"scenarioId":<scenarioId>,"environmentId":<environmentId>}]}' 
```
