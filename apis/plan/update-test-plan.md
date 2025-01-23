# Update Test Plan

Updates an existing test plan with new configurations, such as modifying the plan's name, scenarios, and environment settings.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plans/{planId}`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)

***

### Request

{\`{ "id": 3362, "type": "SELENIUM", "project\_id": 1424, "project\_name": "selinkaratedene", "company\_id": 5267, "plan\_name": "deneme122", "scenarios": \[23057], "period": { "period\_type": "MANUAL", "days\_of\_week": "", "scheduled\_days\_of\_week": \[], "repeat\_period": 60 }, "alerts": \[], "enabled": true, "group\_plan": false, "plan\_parallel\_test\_limit": 24, "failed\_test\_retry\_count": 0, "alerts\_enabled\_result": false, "project\_enabled": true, "test\_run\_type": "CROSS", "created\_at": "2025-01-23T04:26:40Z", "updated\_at": "2025-01-23T04:26:40Z", "created\_by": "mehmetaksahin", "updated\_by": "mehmetaksahin", "xray\_enabled": false, "test\_rail\_enabled": false, "test\_rail\_any\_mismatch": false, "is\_parent": false, "childs": \[], "screen\_shot\_type": "YES", "video\_enabled": true, "environment\_resolutions": \[ { "environment": { "id": 1188 }, "resolution": { "resolution\_name": "FHD", "resolution\_width": 1920, "resolution\_height": 1080 }, "resolutionValue": "1920x1080" } ], "test\_plan\_java\_parameters": \[], "performance\_data\_enabled": false, "file\_download\_path": "" }\`}

***

#### Request Parameters

| Parameter                   | Type      | Description                                                      |
| --------------------------- | --------- | ---------------------------------------------------------------- |
| `id`                        | `Integer` | The unique ID of the test plan to update.                        |
| `type`                      | `String`  | The type of the test plan (e.g., `SELENIUM`).                    |
| `project_id`                | `Integer` | ID of the project associated with the test plan.                 |
| `plan_name`                 | `String`  | The name of the test plan.                                       |
| `scenarios`                 | `Array`   | List of scenario IDs associated with the test plan.              |
| `period`                    | `Object`  | Information about the execution period of the test plan.         |
| `alerts`                    | `Array`   | List of alerts configured for the test plan (currently empty).   |
| `enabled`                   | `Boolean` | Whether the test plan is enabled.                                |
| `group_plan`                | `Boolean` | Whether the test plan is a group plan or not.                    |
| `plan_parallel_test_limit`  | `Integer` | The parallel test limit for the test plan.                       |
| `failed_test_retry_count`   | `Integer` | The number of retries in case a test fails.                      |
| `alerts_enabled_result`     | `Boolean` | Whether the alerts are enabled for the test plan.                |
| `project_enabled`           | `Boolean` | Whether the project associated with the test plan is enabled.    |
| `test_run_type`             | `String`  | The type of test run (e.g., `CROSS`).                            |
| `test_rail_enabled`         | `Boolean` | Whether TestRail integration is enabled.                         |
| `test_rail_any_mismatch`    | `Boolean` | Whether any mismatch in TestRail should be handled.              |
| `test_plan_java_parameters` | `Array`   | Java parameters associated with the test plan (currently empty). |
| `performance_data_enabled`  | `Boolean` | Whether performance data collection is enabled.                  |
| `file_download_path`        | `String`  | The file download path associated with the test plan.            |
| `environment_resolutions`   | `Array`   | List of environment resolutions associated with the test plan.   |

***

### Response

{\`{ "id": 3362, "type": "SELENIUM", "project\_id": 1424, "project\_name": "selinkaratedene", "company\_id": 5267, "plan\_name": "deneme122", "scenarios": \[23057], "period": { "period\_type": "MANUAL", "days\_of\_week": "", "scheduled\_days\_of\_week": \[], "repeat\_period": 60 }, "alerts": \[], "enabled": true, "group\_plan": false, "plan\_parallel\_test\_limit": 24, "failed\_test\_retry\_count": 0, "alerts\_enabled\_result": false, "project\_enabled": true, "test\_run\_type": "CROSS", "created\_at": "2025-01-23T04:26:40Z", "updated\_at": "2025-01-23T05:32:51Z", "created\_by": "mehmetaksahin", "updated\_by": "mehmetaksahin", "xray\_enabled": false, "test\_rail\_enabled": false, "test\_rail\_any\_mismatch": false, "is\_parent": false, "childs": \[], "screen\_shot\_type": "YES", "video\_enabled": true, "environment\_resolutions": \[ { "environment": { "id": 1188, "name": "Firefox", "operating\_system": "WIN10", "browser\_type": "FIREFOX", "environment\_type": "firefox", "environment\_version": "134", "enabled": true, "operating\_system\_clean\_name": "Windows 10", "mobile": false }, "resolution": { "resolution\_name": "FHD", "resolution\_width": 1920, "resolution\_height": 1080 } } ], "test\_plan\_java\_parameters": \[], "performance\_data\_enabled": false, "file\_download\_path": "" }\`}

***

#### Key Response Fields

| Field                      | Type      | Description                                                    |
| -------------------------- | --------- | -------------------------------------------------------------- |
| `id`                       | `Integer` | Unique ID of the test plan.                                    |
| `plan_name`                | `String`  | The name of the test plan.                                     |
| `scenarios`                | `Array`   | List of scenario IDs associated with the test plan.            |
| `period`                   | `Object`  | Information about the test plan's execution period.            |
| `enabled`                  | `Boolean` | Whether the test plan is enabled.                              |
| `group_plan`               | `Boolean` | Whether the test plan is a group plan or not.                  |
| `plan_parallel_test_limit` | `Integer` | The parallel test limit for the test plan.                     |
| `failed_test_retry_count`  | `Integer` | The number of retries in case a test fails.                    |
| `alerts_enabled_result`    | `Boolean` | Whether alerts are enabled for the test plan.                  |
| `project_enabled`          | `Boolean` | Whether the project associated with the test plan is enabled.  |
| `test_run_type`            | `String`  | The type of test run (e.g., `CROSS`).                          |
| `updated_at`               | `String`  | The last update timestamp of the test plan.                    |
| `environment_resolutions`  | `Array`   | List of environment resolutions associated with the test plan. |

***

### Error Codes

| HTTP Status | Code             | Message                                                               |
| ----------- | ---------------- | --------------------------------------------------------------------- |
| 400         | `BAD_REQUEST`    | Invalid request parameters.                                           |
| 401         | `UNAUTHORIZED`   | The user is not authorized to access this resource.                   |
| 403         | `FORBIDDEN`      | The user does not have sufficient permissions to access the resource. |
| 404         | `NOT_FOUND`      | The specified test plan or project was not found.                     |
| 500         | `INTERNAL_ERROR` | An internal server error occurred while processing the request.       |

### Example Request

```bash
curl --location --request PUT "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plans/{planId}" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
  "id": 3362,
  "type": "SELENIUM",
  "project_id": 1424,
  "project_name": "selinkaratedene",
  "company_id": 5267,
  "plan_name": "deneme122",
  "scenarios": [23057],
  "period": {
    "period_type": "MANUAL",
    "days_of_week": "",
    "scheduled_days_of_week": [],
    "repeat_period": 60
  },
  "alerts": [],
  "enabled": true,
  "group_plan": false,
  "plan_parallel_test_limit": 24,
  "failed_test_retry_count": 0,
  "alerts_enabled_result": false,
  "project_enabled": true,
  "test_run_type": "CROSS",
  "created_at": "2025-01-23T04:26:40Z",
  "updated_at": "2025-01-23T04:26:40Z",
  "created_by": "mehmetaksahin",
  "updated_by": "mehmetaksahin",
  "xray_enabled": false,
  "test_rail_enabled": false,
  "test_rail_any_mismatch": false,
  "is_parent": false,
  "childs": [],
  "screen_shot_type": "YES",
  "video_enabled": true,
  "environment_resolutions": [
    {
      "environment": {
        "id": 1188
      },
      "resolution": {
        "resolution_name": "FHD",
        "resolution_width": 1920,
        "resolution_height": 1080
      },
      "resolutionValue": "1920x1080"
    }
  ],
  "test_plan_java_parameters": [],
  "performance_data_enabled": false,
  "file_download_path": ""
}'
```
