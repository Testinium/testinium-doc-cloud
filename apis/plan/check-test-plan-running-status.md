# Check Test Plan Running Status

The endpoint checks whether a specific test plan is currently running. The user must have the `PLAN_RUN` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/{planId}/checkIsRunning`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type   | Required | Description                     |
| --------- | ------ | -------- | ------------------------------- |
| `planId`  | `Long` | Yes      | The unique ID of the test plan. |

***

### Request Parameters

No request body is required for this endpoint. The parameter `planId` is provided via the URL path.

***

### Response

The response contains the status of the test plan, indicating whether it is currently running.

```json
{
  "status": "SUCCESS",
  "running": false
}
```

#### Response Fields

| Field     | Type      | Description                                      |
| --------- | --------- | ------------------------------------------------ |
| `status`  | `String`  | Status of the API call (e.g., `SUCCESS`).        |
| `running` | `Boolean` | Indicates if the test plan is currently running. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `404`     | `PLAN_NOT_FOUND`        | No test plan was found for the specified ID.     |
| `403`     | `ACCESS_DENIED`         | User lacks `PLAN_RUN` authority.                 |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/plans/{planId}/checkIsRunning' \
--header 'Authorization: Bearer <your_access_token>'\
--header 'current-company-id: <your_company_id>'
```
