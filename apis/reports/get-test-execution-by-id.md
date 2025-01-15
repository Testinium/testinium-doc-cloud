# Get Test Execution By ID

The endpoint allows users to retrieve detailed information about a specific test execution by its ID.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/executions/{execId}`
* **Method**: `GET`
* **Authentication**: Requires `Bearer Token`
* **Content-Type**: `application/json`
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Variables

| Parameter | Type     | Required | Description                   |
| --------- | -------- | -------- | ----------------------------- |
| `execId`  | `Object` | Yes      | The ID of the test execution. |

***

### Response Body

Upon a successful request, the API returns the test execution details in JSON format.

```json
{
    "id": 268108,
    "user_id": 5377,
    "username": "user",
    "company_id": 5288,
    "project_id": 1399,
    "project_name": "project1",
    "plan_id": 3255,
    "plan_name": "Demo",
    "test_results": [
        3492344
    ],
    "runtime": 17690,
    "result_summary": {
        "ERROR": 1
    },
    "start_date": "2024-11-28T20:11:46Z",
    "end_date": "2024-11-28T20:12:10Z",
    "test_result_status_counts": "[ERROR, 1]"
}
```

| Field                       | Type      | Description                                                         |
| --------------------------- | --------- | ------------------------------------------------------------------- |
| `id`                        | `integer` | The unique ID of the test execution.                                |
| `user_id`                   | `integer` | The ID of the user who initiated the execution.                     |
| `username`                  | `string`  | The username of the user who initiated the execution.               |
| `company_id`                | `integer` | The ID of the company associated with the execution.                |
| `project_id`                | `integer` | The ID of the associated project.                                   |
| `project_name`              | `string`  | The name of the associated project.                                 |
| `plan_id`                   | `integer` | The ID of the associated test plan.                                 |
| `plan_name`                 | `string`  | The name of the associated test plan.                               |
| `test_results`              | `array`   | List of test result IDs related to this execution.                  |
| `runtime`                   | `integer` | The execution runtime in milliseconds.                              |
| `result_summary`            | `object`  | Summary of execution results.                                       |
| `start_date`                | `string`  | The start date and time of the test execution.                      |
| `end_date`                  | `string`  | The end date and time of the test execution.                        |
| `test_result_status_counts` | `string`  | A string representation of the counts of test result statuses.      |
| `error_code`                | `string`  | The error code, if any, returned by the execution.                  |
| `error_definition`          | `string`  | A description of the error, if any, that occurred during execution. |

***

### Error Codes

Possible error codes and their explanations during the operation:

| HTTP Code | Error Message           | Description                                                      |
| --------- | ----------------------- | ---------------------------------------------------------------- |
| `401`     | `Unauthorized`          | Authorization failed. User is not logged in.                     |
| `403`     | `Forbidden`             | User does not have permission to access the specified execution. |
| `404`     | `Execution not found`   | The specified test execution was not found.                      |
| `500`     | `Internal Server Error` | An unexpected error occurred on the server.                      |

***

### Example Request

```bash
curl -X GET "https://testinium.io/Testinium.RestApi/api/executions/{execId}" \
-H "Authorization: Bearer <your_access_token>" \
-H "Accept: application/json"\
-H 'current-company-id: <your_company_id>'
```
