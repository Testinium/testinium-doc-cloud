# Get Test Results of Execution by Scenario

This endpoint retrieves the test results for a specific scenario within a given execution. The user must have the `TEST_RESULT_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/results/execution/{executionId}/scenario/{scenarioId}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter     | Type   | Required | Description                          |
| ------------- | ------ | -------- | ------------------------------------ |
| `executionId` | `Long` | Yes      | The unique ID of the test execution. |
| `scenarioId`  | `Long` | Yes      | The unique ID of the test scenario.  |

***

### Request Parameters

No request body is required for this endpoint. The parameters `executionId` and `scenarioId` are provided as path parameters.

***

### Response

The response contains a list of test results for the specified execution and scenario.

```json
[
    {
        "id": 3571814,
        "level": "WAITING",
        "runtime": 0,
        "environment": {
            "id": 1188,
            "name": "Firefox",
            "operating_system": "WIN10",
            "browser_type": "FIREFOX",
            "environment_type": "firefox",
            "environment_version": "134",
            "enabled": true,
            "operating_system_clean_name": "Windows 10",
            "mobile": false
        },
        "session_id": "05755767628875375975",
        "message": "",
        "screenshots_enabled": false,
        "screen_shot_type": "NO",
        "video_enabled": false,
        "performance_data_enabled": false,
        "test_key": "TEST-C5267-P3362-E276081-S23057-ENV:1188-WIN10-firefox-134",
        "video_format": "FLV",
        "node_log_path": "https://testinium-dev-cloud.s3.amazonaws.com/5267/2025/01/23/05755767628875375975/node.log",
        "executor_log_path": "https://testinium-dev-cloud.s3.amazonaws.com/5267/2025/01/23/05755767628875375975/testResult.log",
        "screen_resolution": "1024x768",
        "user_id": 5322,
        "project_id": 1424,
        "plan_id": 3362,
        "scenario_id": 23057,
        "execution_id": 276081,
        "company_id": 5267,
        "user_info": {
            "id": 5322,
            "name": "Mehmet",
            "surname": "Aksahin",
            "username": "mehmetaksahin",
            "email": "mehmet.aksahin@testinium.com",
            "enabled": true,
            "account_non_expired": true,
            "account_non_locked": true,
            "credential_non_expired": true,
            "language": "ENGLISH",
            "time_zone": "UTC",
            "company": "mehmetaksahin",
            "company_id": 5267,
            "current_company": "mehmetaksahin",
            "current_company_id": 5267,
            "roles": [
                "ROLE_ADMIN",
                "ROLE_CHANGE_USER",
                "ROLE_USER",
                "ROLE_REPORT",
                "ROLE_INTEGRATION",
                "ROLE_RUN_TEST",
                "ROLE_COMPANY_ADMIN"
            ],
            "access_token": "b0fa2cca656533bb82e5978f677b4b4a"
        },
        "start_date": "2025-01-23T10:00:58Z"
    }
]
```

### Response Fields

| Field                      | Type               | Description                                                    |
| -------------------------- | ------------------ | -------------------------------------------------------------- |
| `id`                       | `Long`             | The unique ID of the test result.                              |
| `level`                    | `String`           | The current status of the test result (e.g., `WAITING`).       |
| `runtime`                  | `Int`              | The runtime duration of the test (in seconds).                 |
| `environment`              | `Object`           | Details of the environment where the test ran.                 |
| `session_id`               | `String`           | The unique session ID for the test.                            |
| `message`                  | `String`           | Additional messages or details related to the test result.     |
| `screenshots_enabled`      | `Boolean`          | Indicates if screenshots are enabled for the test.             |
| `screen_shot_type`         | `String`           | The type of screenshot (e.g., `NO`, `FULL`).                   |
| `video_enabled`            | `Boolean`          | Indicates if video recording is enabled for the test.          |
| `performance_data_enabled` | `Boolean`          | Indicates if performance data collection is enabled.           |
| `test_key`                 | `String`           | The unique key identifying the test.                           |
| `node_log_path`            | `String` (URL)     | The URL for downloading the node log.                          |
| `executor_log_path`        | `String` (URL)     | The URL for downloading the executor log.                      |
| `screen_resolution`        | `String`           | The screen resolution used during the test (e.g., `1024x768`). |
| `user_id`                  | `Long`             | The ID of the user who initiated the test.                     |
| `project_id`               | `Long`             | The ID of the associated project.                              |
| `plan_id`                  | `Long`             | The ID of the associated plan.                                 |
| `scenario_id`              | `Long`             | The ID of the associated scenario.                             |
| `execution_id`             | `Long`             | The ID of the associated execution.                            |
| `company_id`               | `Long`             | The ID of the associated company.                              |
| `user_info`                | `Object`           | Details of the user who initiated the test.                    |
| `start_date`               | `String` (ISO8601) | The start date and time of the test execution.                 |

***

### Error Codes

| HTTP Code | Error Message              | Description                                                |
| --------- | -------------------------- | ---------------------------------------------------------- |
| `401`     | `ACCESS_DENIED`            | The user lacks the `TEST_RESULT_VIEW` authority.           |
| `404`     | `EXECUTION_NOT_FOUND`      | No execution was found for the specified ID.               |
| `404`     | `TEST_SCENARIO_NOT_FOUND`  | No scenario was found for the specified ID.                |
| `500`     | `USERS_COMPANY_NOT_EXISTS` | The company associated with the user does not exist.       |
| `500`     | `SYSTEM_INTERNAL_ERROR`    | An unexpected error occurred while processing the request. |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/results/execution/{executionId}/scenario/{scenarioId}' \  
--header 'Authorization: Bearer <your_access_token>'  
```
