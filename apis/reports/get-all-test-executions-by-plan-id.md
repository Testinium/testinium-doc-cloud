# Get All Test Executions By Plan ID

This endpoint retrieves all test execution records for a specific test plan. Users must have the `TEST_EXECUTION_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/{planId}/executions`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter | Type   | Required | Description                                                          |
| --------- | ------ | -------- | -------------------------------------------------------------------- |
| `planId`  | `Long` | Yes      | The unique ID of the test plan whose executions are being retrieved. |

***

### Request Body

No request body is required. The required parameter (`planId`) is passed in the URL path.

***

### Response

The response contains paginated data of test execution records.

```json
{
    "current_page": 1,
    "total_count": 10,
    "page_count": 1,
    "next_page": "",
    "previous_page": "",
    "item_list": [
        {
            "id": 123456,
            "user_id": 1234,
            "username": "user",
            "company_id": 5678,
            "project_id": 6789,
            "project_name": "AmazonSeleniumGauge",
            "plan_id": 4567,
            "plan_name": "Go to",
            "test_results": [1234567],
            "runtime": 1000,
            "result_summary": {"ERROR": 1},
            "start_date": "2024-11-21T10:43:09Z",
            "end_date": "2024-11-21T10:43:13Z",
            "test_result_status_counts": "[ERROR, 1]"
        }
    ],
    "rest_api_url": "https://clouddev.testinium.io/Testinium.RestApi"
}
```

#### Response Fields

| Field                       | Type      | Description                                                               |
| --------------------------- | --------- | ------------------------------------------------------------------------- |
| `current_page`              | `Integer` | The current page number in the paginated result.                          |
| `total_count`               | `Integer` | The total number of test executions available.                            |
| `page_count`                | `Integer` | The total number of pages available.                                      |
| `item_list`                 | `Array`   | List of test executions. Each item contains details as described below.   |
| `rest_api_url`              | `String`  | The base URL for this API.                                                |
| `id`                        | `Long`    | The unique ID of the test execution.                                      |
| `user_id`                   | `Long`    | ID of the user who executed the test.                                     |
| `username`                  | `String`  | Username of the executor.                                                 |
| `company_id`                | `Long`    | The company ID of the user.                                               |
| `project_id`                | `Long`    | ID of the project associated with the test plan.                          |
| `project_name`              | `String`  | Name of the project.                                                      |
| `plan_id`                   | `Long`    | ID of the test plan.                                                      |
| `plan_name`                 | `String`  | Name of the test plan.                                                    |
| `test_results`              | `Array`   | IDs of the individual test results.                                       |
| `runtime`                   | `Integer` | Runtime of the execution in milliseconds.                                 |
| `result_summary`            | `Object`  | Summary of test results, including statuses like `ERROR`, `SUCCESS`, etc. |
| `start_date`                | `String`  | Start date and time of the execution in ISO 8601 format.                  |
| `end_date`                  | `String`  | End date and time of the execution in ISO 8601 format.                    |
| `test_result_status_counts` | `String`  | Status counts for the test results, such as `[ERROR, 1]`.                 |

***

### Error Codes

| HTTP Code | Error Message           | Description                                        |
| --------- | ----------------------- | -------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.     |
| `403`     | `ACCESS_DENIED`         | User lacks `TEST_EXECUTION_VIEW` authority.        |
| `404`     | `PLAN_NOT_FOUND`        | No test plan was found for the specified `planId`. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.   |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/plans/{planId}/executions" \
--header 'Authorization: Bearer <your_access_token>'
```
