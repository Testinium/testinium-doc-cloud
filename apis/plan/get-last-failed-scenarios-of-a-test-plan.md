# Get Last Failed Scenarios of a Test Plan

This endpoint retrieves the last failed scenarios and their test results for a specific test plan. The user must have the necessary `TEST_RESULT_VIEW` authority to access this endpoint.

***

## Endpoint Information

* **URL**:`https://testinium.io/Testinium.RestApi/api/plans/{planId}/lastFailedScenarios`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

## Path Parameters

| Parameter | Type   | Required | Description                                                            |
| --------- | ------ | -------- | ---------------------------------------------------------------------- |
| `planId`  | `Long` | Yes      | The unique ID of the test plan to fetch the last failed scenarios for. |

***

## Response Body

```json
[
    {
        "scenario": {
            "id": 23526,
            "type": "SELENIUM",
            "scenario_name": "@ApiOwNoCon",
            "enabled": true,
            "deleted": false,
            "execute_mode": "AUTOMATED",
            "source_file": "ServisAkislari/apiTest.spec",
            "project_id": 1453,
            "plans": [3353],
            "parameterized": false,
            "has_parameterized_class": false,
            "created_at": "2025-01-13T08:18:00Z",
            "updated_at": "2025-01-13T08:18:00Z",
            "created_by": "mehmetaksahin",
            "updated_by": "mehmetaksahin",
            "java_test_class": "ServisAkislari.apiTest",
            "java_test_methods": "@ApiOwNoCon",
            "test_scenario_java_parameters": [],
            "group": false
        },
        "test_results": [
            {
                "id": 3545263,
                "level": "ERROR",
                "runtime": 3835,
                "environment": {
                    "id": 440,
                    "name": "Chrome",
                    "operating_system": "WIN10",
                    "browser_type": "CHROME",
                    "environment_type": "chrome",
                    "environment_version": "LATEST",
                    "enabled": true,
                    "operating_system_clean_name": "Windows 10",
                    "mobile": false
                },
                "session_id": "41504966335910929810",
                "message": "Test report could not be found. Please check your executor log.",
                "screenshots_enabled": false,
                "screen_shot_type": "NO",
                "video_enabled": false,
                "performance_data_enabled": false,
                "issue_tracker_key": "BCB-2",
                "test_key": "TEST-C5267-P3353-E274063-S23526-ENV:440-WIN10-chrome-LATEST",
                "video_format": "FLV",
                "node_log_path": "https://testinium-dev-cloud.s3.amazonaws.com/5267/2025/01/13/41504966335910929810/node.log",
                "executor_log_path": "https://testinium-dev-cloud.s3.amazonaws.com/5267/2025/01/13/41504966335910929810/testResult.log",
                "screen_resolution": "1024x768",
                "user_id": 5322,
                "project_id": 1453,
                "plan_id": 3353,
                "scenario_id": 23526,
                "execution_id": 274063,
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
                        "ROLE_USER",
                        "ROLE_RUN_TEST",
                        "ROLE_ADMIN",
                        "ROLE_COMPANY_ADMIN",
                        "ROLE_REPORT",
                        "ROLE_INTEGRATION",
                        "ROLE_CHANGE_USER"
                    ],
                    "access_token": "b0fa2cca656533bb82e5978f677b4b4a"
                },
                "start_date": "2025-01-13T08:54:49Z",
                "end_date": "2025-01-13T08:54:53Z"
            }
        ]
    },
    {
        "scenario": {
            "id": 23527,
            "type": "SELENIUM",
            "scenario_name": "@ApiRtNoCon",
            "enabled": true,
            "deleted": false,
            "execute_mode": "AUTOMATED",
            "source_file": "ServisAkislari/apiTest.spec",
            "project_id": 1453,
            "plans": [3353],
            "parameterized": false,
            "has_parameterized_class": false,
            "created_at": "2025-01-13T08:18:00Z",
            "updated_at": "2025-01-13T08:18:00Z",
            "created_by": "mehmetaksahin",
            "updated_by": "mehmetaksahin",
            "java_test_class": "ServisAkislari.apiTest",
            "java_test_methods": "@ApiRtNoCon",
            "test_scenario_java_parameters": [],
            "group": false
        },
        "test_results": [
            {
                "id": 3545264,
                "level": "ERROR",
                "runtime": 3921,
                "environment": {
                    "id": 440,
                    "name": "Chrome",
                    "operating_system": "WIN10",
                    "browser_type": "CHROME",
                    "environment_type": "chrome",
                    "environment_version": "LATEST",
                    "enabled": true,
                    "operating_system_clean_name": "Windows 10",
                    "mobile": false
                },
                "session_id": "51862876213391696727",
                "message": "Test report could not be found. Please check your executor log.",
                "screenshots_enabled": false,
                "screen_shot_type": "NO",
                "video_enabled": false,
                "performance_data_enabled": false,
                "test_key": "TEST-C5267-P3353-E274063-S23527-ENV:440-WIN10-chrome-LATEST",
                "video_format": "FLV",
                "node_log_path": "https://testinium-dev-cloud.s3.amazonaws.com/5267/2025/01/13/51862876213391696727/node.log",
                "executor_log_path": "https://testinium-dev-cloud.s3.amazonaws.com/5267/2025/01/13/51862876213391696727/testResult.log",
                "screen_resolution": "1024x768",
                "user_id": 5322,
                "project_id": 1453,
                "plan_id": 3353,
                "scenario_id": 23527,
                "execution_id": 274063,
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
                        "ROLE_USER",
                        "ROLE_RUN_TEST",
                        "ROLE_ADMIN",
                        "ROLE_COMPANY_ADMIN",
                        "ROLE_REPORT",
                        "ROLE_INTEGRATION",
                        "ROLE_CHANGE_USER"
                    ],
                    "access_token": "b0fa2cca656533bb82e5978f677b4b4a"
                },
                "start_date": "2025-01-13T08:54:58Z",
                "end_date": "2025-01-13T08:55:02Z"
            }
        ]
    }
]

```

### Response Field Tables

#### Scenario Object

| Field               | Type      | Description                                    |
| ------------------- | --------- | ---------------------------------------------- |
| `id`                | `Long`    | The unique ID of the scenario.                 |
| `type`              | `String`  | The type of the scenario (e.g., `SELENIUM`).   |
| `scenario_name`     | `String`  | The name of the scenario.                      |
| `enabled`           | `Boolean` | Indicates if the scenario is active.           |
| `deleted`           | `Boolean` | Indicates if the scenario is deleted.          |
| `execute_mode`      | `String`  | The execution mode (e.g., `AUTOMATED`).        |
| `source_file`       | `String`  | The source file associated with the scenario.  |
| `project_id`        | `Long`    | The ID of the project containing the scenario. |
| `plans`             | `Array`   | List of associated plan IDs.                   |
| `created_at`        | `String`  | The creation timestamp of the scenario.        |
| `updated_at`        | `String`  | The last update timestamp of the scenario.     |
| `created_by`        | `String`  | The user who created the scenario.             |
| `java_test_class`   | `String`  | The associated Java test class.                |
| `java_test_methods` | `String`  | The associated Java test methods.              |

#### Test Results Object

| Field                          | Type      | Description                                   |
| ------------------------------ | --------- | --------------------------------------------- |
| `id`                           | `Long`    | The unique ID of the test result.             |
| `level`                        | `String`  | The severity level (e.g., `ERROR`).           |
| `runtime`                      | `Integer` | The execution runtime in milliseconds.        |
| `environment.id`               | `Long`    | The ID of the execution environment.          |
| `environment.name`             | `String`  | The name of the environment (e.g., `Chrome`). |
| `environment.operating_system` | `String`  | The operating system of the environment.      |
| `message`                      | `String`  | The error message from the test result.       |
| `node_log_path`                | `String`  | URL to the node log file.                     |
| `executor_log_path`            | `String`  | URL to the executor log file.                 |
| `start_date`                   | `String`  | The start timestamp of the test execution.    |
| `end_date`                     | `String`  | The end timestamp of the test execution.      |

***

## Error Codes

| HTTP Code | Error Message           | Description                                                          |
| --------- | ----------------------- | -------------------------------------------------------------------- |
| `400`     | `BAD_REQUEST`           | Test Plan not found !                                                |
| `403`     | `ACCESS_DENIED`         | The user does not have the necessary authority to view test results. |
| `500`     | `SYSTEM_INTERNAL_ERROR` | An unexpected error occurred while processing the request.           |

***

## Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/plans/{planId}/lastFailedScenarios" \
--header 'Authorization: Bearer <your_access_token>'
```
