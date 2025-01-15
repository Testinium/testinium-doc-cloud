# Run Test Plan

The endpoint starts the execution of a specific test plan. The user must have the `PLAN_RUN` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/{planId}/run`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type   | Required | Description                                |
| --------- | ------ | -------- | ------------------------------------------ |
| `planId`  | `Long` | Yes      | The unique ID of the test plan to execute. |

***

### Query Parameters

| Parameter     | Type     | Required | Description                                                  |
| ------------- | -------- | -------- | ------------------------------------------------------------ |
| `callbackUrl` | `String` | No       | URL to be called upon test execution completion.             |
| `isGroupRun`  | `String` | No       | Indicates if the test is part of a group run (`true/false`). |

***

### Request Body

No request body is required for this endpoint. Parameters are passed via the URL path and query.

***

### Response

The response contains details about the started test plan execution.

```
{
    "execution_id": 268089,
    "unavailable_env_list": [],
    "test_plan_id": 3269,
    "successful": true,
    "already_running": false
}
```

#### Response Fields

| Field         | Type     | Description                                        |
| ------------- | -------- | -------------------------------------------------- |
| `status`      | `String` | Status of the API call (e.g., `SUCCESS`).          |
| `executionId` | `Long`   | The ID of the test plan execution.                 |
| `message`     | `String` | A message indicating the outcome of the operation. |

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
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/plans/{planId}/run" \
--header 'Authorization: Bearer <your_access_token>'
--header 'current-company-id: <your_company_id>'
```
