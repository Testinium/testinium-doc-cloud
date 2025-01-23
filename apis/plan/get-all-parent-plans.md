# Get All Parent Plans

Retrieves all parent plans associated with a specific project. A parent plan is a test plan that is not a child of any other plan.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/parentPlans`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type     | Description                                               |
| ----------- | -------- | --------------------------------------------------------- |
| `projectId` | `Long`   | The ID of the project for which to retrieve parent plans. |
| `user`      | `Object` | The user making the request, identified by their company. |

***

### Response

```json
[
    {
        "id": 3363,
        "type": "SELENIUM",
        "project_id": 1424,
        "project_name": "selinkaratedene",
        "company_id": 5267,
        "plan_name": "gropplan",
        "period": {
            "period_type": "MANUAL",
            "days_of_week": "",
            "scheduled_days_of_week": [],
            "repeat_period": 60
        },
        "alerts": [],
        "enabled": true,
        "group_plan": false,
        "plan_parallel_test_limit": 0,
        "failed_test_retry_count": 0,
        "alerts_enabled_result": false,
        "project_enabled": true,
        "test_run_type": "CROSS",
        "created_at": "2025-01-23T06:16:59Z",
        "updated_at": "2025-01-23T06:16:59Z",
        "created_by": "mehmetaksahin",
        "updated_by": "mehmetaksahin",
        "xray_enabled": false,
        "test_rail_enabled": false,
        "test_rail_any_mismatch": false,
        "is_parent": true,
        "childs": [
            {
                "id": 3364,
                "type": "SELENIUM",
                "project_id": 1424,
                "project_name": "selinkaratedene",
                "company_id": 5267,
                "plan_name": "deneme1234",
                "scenarios": [
                    23057
                ],
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
                "created_at": "2025-01-23T06:17:31Z",
                "updated_at": "2025-01-23T06:17:31Z",
                "created_by": "mehmetaksahin",
                "updated_by": "mehmetaksahin",
                "xray_enabled": false,
                "test_rail_enabled": false,
                "test_rail_any_mismatch": false,
                "parent_id": 3363,
                "is_parent": false,
                "childs": [],
                "screen_shot_type": "YES",
                "video_enabled": true,
                "environment_resolutions": [
                    {
                        "environment": {
                            "id": 1192,
                            "name": "Firefox",
                            "operating_system": "WIN10",
                            "browser_type": "FIREFOX",
                            "environment_type": "firefox",
                            "environment_version": "131",
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
        ],
        "screen_shot_type": "YES",
        "video_enabled": true,
        "environment_resolutions": [],
        "test_plan_java_parameters": [],
        "performance_data_enabled": false,
        "file_download_path": ""
    }
]
```

***

### Response Fields

| Field                       | Type      | Description                                          |
| --------------------------- | --------- | ---------------------------------------------------- |
| `id`                        | `int`     | The ID of the parent plan.                           |
| `type`                      | `string`  | The type of the test plan, e.g., "SELENIUM".         |
| `project_id`                | `int`     | The project ID that the plan belongs to.             |
| `plan_name`                 | `string`  | The name of the parent test plan.                    |
| `childs`                    | `Array`   | List of child plans associated with the parent plan. |
| `enabled`                   | `boolean` | Whether the plan is enabled.                         |
| `period`                    | `object`  | The schedule for the plan.                           |
| `created_at`                | `string`  | The creation timestamp of the plan.                  |
| `updated_at`                | `string`  | The last update timestamp of the plan.               |
| `screen_shot_type`          | `string`  | Defines if screenshots are enabled for the plan.     |
| `video_enabled`             | `boolean` | Whether video is enabled for the plan.               |
| `test_plan_java_parameters` | `Array`   | Java parameters for the test plan.                   |

***

### Error Codes

| HTTP Status | Code             | Message                                                         |
| ----------- | ---------------- | --------------------------------------------------------------- |
| 400         | `BAD_REQUEST`    | Invalid request parameters.                                     |
| 401         | `UNAUTHORIZED`   | The user is not authorized to access this resource.             |
| 404         | `NOT_FOUND`      | The specified project does not exist or has no parent plans.    |
| 500         | `INTERNAL_ERROR` | An internal server error occurred while processing the request. |

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/parentPlans" \
--header 'Authorization: Bearer <your_access_token>'
```
