# Get Plan By Plan ID

Retrieves detailed information about a specific test plan by its ID, including scenarios, execution details, alerts, and configurations.

***

## Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/{planId}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

## Path Parameters

| Parameter | Type   | Required | Description                             |
| --------- | ------ | -------- | --------------------------------------- |
| `planId`  | `Long` | Yes      | The unique identifier of the test plan. |

***

## Response

```json
{
    "id": 3353,
    "type": "SELENIUM",
    "project_id": 1453,
    "project_name": "PegasusRunTimeElleme",
    "company_id": 5267,
    "plan_name": "PegasusWebApi",
    "scenarios": [
        23526,
        23527,
        23528,
        23529,
        23530,
        23531,
        23532,
        23533
    ],
    "period": {
        "period_type": "MANUAL",
        "scheduled_days_of_week": [],
        "repeat_period": 60
    },
    "alerts": [
        {
            "alert_type": "EMAIL",
            "alert_sending_status": "EVERY_TEST",
            "target": "furkan.kartal@testinium.com",
            "plan_id": 3353,
            "enabled": true,
            "unsubscribe_link_eliminated": false
        }
    ],
    "enabled": true,
    "group_plan": false,
    "plan_parallel_test_limit": 24,
    "last_execution": {
        "id": 274063,
        "user_id": 5322,
        "username": "mehmetaksahin",
        "company_id": 5267,
        "project_id": 1453,
        "project_name": "PegasusRunTimeElleme",
        "plan_id": 3353,
        "plan_name": "PegasusWebApi",
        "test_results": [
            3545263,
            3545264,
            3545265,
            3545266,
            3545267,
            3545268,
            3545269,
            3545270
        ],
        "runtime": 61000,
        "result_summary": {
            "ERROR": 8
        },
        "start_date": "2025-01-13T08:54:41Z",
        "end_date": "2025-01-13T08:55:42Z",
        "test_result_status_counts": "[ERROR, 8]"
    },
    "failed_test_retry_count": 0,
    "alerts_enabled_result": false,
    "project_enabled": true,
    "test_run_type": "CROSS",
    "created_at": "2025-01-13T08:19:12Z",
    "updated_at": "2025-01-13T08:19:13Z",
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

| Field                      | Type      | Description                                                                  |
| -------------------------- | --------- | ---------------------------------------------------------------------------- |
| `id`                       | `Long`    | The unique identifier of the test plan.                                      |
| `type`                     | `String`  | The type of test plan (e.g., SELENIUM).                                      |
| `project_id`               | `Long`    | The unique identifier of the associated project.                             |
| `project_name`             | `String`  | The name of the associated project.                                          |
| `company_id`               | `Long`    | The unique identifier of the company.                                        |
| `plan_name`                | `String`  | The name of the test plan.                                                   |
| `scenarios`                | `Array`   | A list of scenario IDs associated with the test plan.                        |
| `period`                   | `Object`  | Details about the plan's schedule and repeat period.                         |
| `alerts`                   | `Array`   | A list of alerts configured for the plan.                                    |
| `enabled`                  | `Boolean` | Whether the test plan is enabled.                                            |
| `group_plan`               | `Boolean` | Indicates if the plan is part of a group plan.                               |
| `plan_parallel_test_limit` | `Integer` | The maximum number of parallel tests allowed for the plan.                   |
| `last_execution`           | `Object`  | Details about the most recent execution of the test plan.                    |
| `created_at`               | `String`  | The timestamp of when the plan was created.                                  |
| `updated_at`               | `String`  | The timestamp of when the plan was last updated.                             |
| `created_by`               | `String`  | The username of the user who created the plan.                               |
| `updated_by`               | `String`  | The username of the user who last updated the plan.                          |
| `screen_shot_type`         | `String`  | Indicates whether screenshots are enabled for the test plan (e.g., "YES").   |
| `video_enabled`            | `Boolean` | Indicates if video recording is enabled for test executions.                 |
| `environment_resolutions`  | `Array`   | A list of environments and their associated screen resolutions for the plan. |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/plans/{planId}" \
--header 'Authorization: Bearer <your_access_token>'
```
