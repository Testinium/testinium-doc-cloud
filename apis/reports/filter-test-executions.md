# Filter Test Executions

This endpoint allows authorized users to filter test executions based on various parameters such as project ID, plan ID, date range, status, and user email.

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/executions/filter`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter   | Type     | Required | Description                                                   |
| ----------- | -------- | -------- | ------------------------------------------------------------- |
| `projectId` | `Long`   | No       | The unique ID of the project.                                 |
| `planId`    | `Long`   | No       | The unique ID of the test plan.                               |
| `from`      | `Long`   | No       | Start timestamp (Unix time in milliseconds).                  |
| `to`        | `Long`   | No       | End timestamp (Unix time in milliseconds).                    |
| `status`    | `Enum`   | No       | Status of the test execution (e.g., `SUCCESS`, `ERROR`).      |
| `page`      | `int`    | Yes      | Page number (starting from 1).                                |
| `size`      | `int`    | Yes      | Number of records per page.                                   |
| `email`     | `String` | No       | Filter results by user email (must match authenticated user). |

***

### Response

The response is paginated and includes test execution details.

```json
{
    "current_page": 1,
    "total_count": 7,
    "page_count": 1,
    "next_page": "",
    "previous_page": "",
    "item_list": [
        {
            "id": 226310,
            "user_id": 5245,
            "username": "mehmetaksahin",
            "company_id": 5251,
            "project_id": 406,
            "project_name": "webtest",
            "plan_id": 1446,
            "plan_name": "webtestSelahattin",
            "test_results": [3274126],
            "runtime": 35557,
            "result_summary": {
                "SUCCESS": 1
            },
            "start_date": "2025-02-06T07:19:32Z",
            "end_date": "2025-02-06T07:20:14Z",
            "test_result_status_counts": "[SUCCESS, 1]"
        }
    ],
    "rest_api_url": "https://devcluster.testinium.io/Testinium.RestApi"
}
```

***

### Response Fields

| Field                      | Type     | Description                                             |
| -------------------------- | -------- | ------------------------------------------------------- |
| `current_page`             | `int`    | The current page number.                                |
| `total_count`              | `int`    | The total number of test executions found.              |
| `page_count`               | `int`    | The total number of pages available.                    |
| `next_page`                | `String` | URL for the next page (if available).                   |
| `previous_page`            | `String` | URL for the previous page (if available).               |
| `item_list`                | `Array`  | List of test executions.                                |
| `item_list.id`             | `Long`   | Unique ID of the test execution.                        |
| `item_list.user_id`        | `Long`   | ID of the user who executed the test.                   |
| `item_list.username`       | `String` | Username of the test executor.                          |
| `item_list.company_id`     | `Long`   | ID of the company the test belongs to.                  |
| `item_list.project_id`     | `Long`   | ID of the related project.                              |
| `item_list.project_name`   | `String` | Name of the project.                                    |
| `item_list.plan_id`        | `Long`   | ID of the related test plan.                            |
| `item_list.plan_name`      | `String` | Name of the test plan.                                  |
| `item_list.test_results`   | `Array`  | List of test result IDs.                                |
| `item_list.runtime`        | `Long`   | Duration of the test execution in milliseconds.         |
| `item_list.result_summary` | `Object` | Summary of test execution results (`SUCCESS`, `ERROR`). |
| `item_list.start_date`     | `String` | Test execution start time (ISO 8601 format).            |
| `item_list.end_date`       | `String` | Test execution end time (ISO 8601 format).              |
| `rest_api_url`             | `String` | Base URL of the API.                                    |

***

### Error Codes

| HTTP Code | Error Message              | Description                                               |
| --------- | -------------------------- | --------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`          | The request was malformed or contained errors.            |
| `403`     | `ACCESS_DENIED`            | User lacks `TEST_EXECUTION_VIEW` authority.               |
| `403`     | `UNAUTHORIZED_USER`        | The provided email does not match the authenticated user. |
| `404`     | `TEST_EXECUTION_NOT_FOUND` | No test executions were found with the given criteria.    |
| `500`     | `INTERNAL_SERVER_ERROR`    | An unexpected error occurred on the server side.          |

***

### Example Request

```bash
curl --location --request GET 'https://testinium.io/Testinium.RestApi/api/executions/filter?page=1&size=10' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
