# Run Test Plan

The endpoint starts the execution of a specific test plan. The user must have the `PLAN_RUN` authority to access this endpoint.

***

### Endpoint Information

* **URL**: [https://gateway.testinium.io/queue](https://gateway.testinium.io/queue)
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***

### Request Body

```
{
  "planId": 12345,
  "userId": 67890
}
```

***

### Request Body Parameters

| Parameter | Type   | Required | Description                                |
| --------- | ------ | -------- | ------------------------------------------ |
| `planId`  | `Long` | Yes      | The unique ID of the test plan to execute. |
| `userId`  | `Long` | Yes      | The unique ID of the user who runs plan.   |

***

### Response

This response indicates that the operation was completed successfully, with no additional data returned.

```
{
    "data": null,
    "result": {
        "code": 0,
        "message": "success"
    }
}
```

#### Response Fields

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

***

### Application Error Codes

<table><thead><tr><th>Code</th><th>Error Message</th></tr></thead><tbody><tr><td><pre><code><strong>10000
</strong></code></pre></td><td><pre><code>"Plan not found!"
</code></pre></td></tr><tr><td><pre><code>10002
</code></pre></td><td><pre><code>User not found!
</code></pre></td></tr></tbody></table>

### Example Request

<pre class="language-bash"><code class="lang-bash"><strong>curl 'https://gateway.testinium.io/queue' \
</strong>  -H 'accept: application/json, text/plain, */*' \
  -H 'authorization: Bearer &#x3C;your_access_token>' \
  -H 'content-type: application/json' \
  --data-raw '{"planId":&#x3C;plan_id>,"userId":&#x3C;user_id>}'
</code></pre>
