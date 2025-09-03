# Check Test Plan Running Status

The endpoint checks whether a specific test plan is currently running. The user must have the `PLAN_RUN` authority to access this endpoint.

***

### Endpoint Information

* **URL**: [`https://gateway.testinium.io/plan/{id}/active`](https://gateway.testinium.io/plan/%7Bid%7D/active)
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter | Type   | Required | Description                     |
| --------- | ------ | -------- | ------------------------------- |
| i`d`      | `Long` | Yes      | The unique ID of the test plan. |

***

### Request Parameters

No request body is required for this endpoint. The parameter `id` is provided via the URL path.

***

### Response

The request was successful, and the `data` field indicates whether the test plan is currently running (`true`) or not (`false`).

```json
{
    "data": false,
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

### Response Fields

| Field          | Type    | Description                                                                                 |
| -------------- | ------- | ------------------------------------------------------------------------------------------- |
| data           | Object  | `data` field indicates whether the test plan is currently running (`true`) or not (`false`) |
| result         | Object  | Contains details about the outcome of the operation.                                        |
| result.code    | Integer | The result code (e.g., `0` indicates success).                                              |
| result.message | String  | A message describing the outcome (e.g., `"success"`).                                       |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***



### Example Request

```bash
curl 'https://gateway.testinium.io/plan/<planId>/active' \
  -H 'accept: application/json, text/plain, */*' \
  -H 'authorization: Bearer <token>'
```
