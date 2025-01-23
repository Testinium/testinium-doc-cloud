# Create Test Plan

Creates a new test plan for a project, with specified configurations such as environment, test run type, and scenarios.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plans`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***

### Request

```json
{
    "group_plan": false,
    "environment_resolutions": [
        {
            "editable": true,
            "environment": {
                "id": 1188
            },
            "resolutionValue": "1920x1080",
            "resolution": {
                "resolution_name": "FHD",
                "resolution_width": 1920,
                "resolution_height": 1080
            }
        }
    ],
    "project_id": 1424,
    "test_run_type": "CROSS",
    "test_dispatch_method_type": "ALL_IN_ONE",
    "plan_name": "deneme123",
    "company_id": 5267,
    "scenarios": [23057]
}

```

***

### Request Parameters

| Parameter                   | Type      | Description                                                      |
| --------------------------- | --------- | ---------------------------------------------------------------- |
| `group_plan`                | `Boolean` | Whether the test plan is a group plan or not.                    |
| `environment_resolutions`   | `Array`   | A list of environment resolutions associated with the test plan. |
| `project_id`                | `Integer` | ID of the project the test plan belongs to.                      |
| `test_run_type`             | `String`  | Type of test run (e.g., `CROSS`).                                |
| `test_dispatch_method_type` | `String`  | Test dispatch method type (e.g., `ALL_IN_ONE`).                  |
| `plan_name`                 | `String`  | The name of the test plan.                                       |
| `company_id`                | `Integer` | The ID of the company creating the test plan.                    |
| `scenarios`                 | `Array`   | List of scenario IDs associated with the test plan.              |

***

### Response

```json
{
    "id": 3362,
    "type": "SELENIUM",
    "project_id": 1424,
    "project_name": "selinkaratedene",
    "company_id": 5267,
    "plan_name": "deneme123",
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
            "resolution": {
                "resolution_name": "FHD",
                "resolution_width": 1920,
                "resolution_height": 1080
            }
        }
    ],
    "test_plan_java_parameters": [],
    "performance_data_enabled": false,
    "file_download_path": ""
}

```

***

### Response Fields

| Field                       | Type      | Description                                                       |
| --------------------------- | --------- | ----------------------------------------------------------------- |
| `id`                        | `Integer` | Unique ID of the test plan.                                       |
| `type`                      | `String`  | The type of the test plan (e.g., `SELENIUM`).                     |
| `project_id`                | `Integer` | The ID of the project associated with the test plan.              |
| `company_id`                | `Integer` | The ID of the company that created the test plan.                 |
| `plan_name`                 | `String`  | The name of the test plan.                                        |
| `scenarios`                 | `Array`   | List of scenario IDs associated with the test plan.               |
| `period`                    | `Object`  | Information about the test plan's execution period.               |
| `enabled`                   | `Boolean` | Whether the test plan is enabled.                                 |
| `alerts`                    | `Array`   | List of alerts configured for the test plan (currently empty).    |
| `test_run_type`             | `String`  | The type of test run (e.g., `CROSS`).                             |
| `created_at`                | `String`  | The creation timestamp of the test plan.                          |
| `updated_at`                | `String`  | The last update timestamp of the test plan.                       |
| `screen_shot_type`          | `String`  | The screenshot type for the test plan (e.g., `YES`).              |
| `video_enabled`             | `Boolean` | Whether video recording is enabled for the test plan.             |
| `environment_resolutions`   | `Array`   | List of environment resolutions associated with the test plan.    |
| `test_plan_java_parameters` | `Array`   | Java parameters associated with the test plan (currently empty).  |
| `performance_data_enabled`  | `Boolean` | Whether performance data collection is enabled for the test plan. |
| `file_download_path`        | `String`  | The file download path associated with the test plan.             |

***

### Example Request

```bash
curl --location --request POST "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plans" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
  "group_plan": false,
  "environment_resolutions": [
    {
      "editable": true,
      "environment": {
        "id": 1188
      },
      "resolutionValue": "1920x1080",
      "resolution": {
        "resolution_name": "FHD",
        "resolution_width": 1920,
        "resolution_height": 1080
      }
    }
  ],
  "project_id": 1424,
  "test_run_type": "CROSS",
  "test_dispatch_method_type": "ALL_IN_ONE",
  "plan_name": "deneme123",
  "company_id": 5267,
  "scenarios": [23057]
}'
```
