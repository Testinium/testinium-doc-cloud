# Get All Plans By Project ID

The **Get All Plans** API retrieves all test plans associated with a specific project. The user must have the `PLAN_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plans`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type     | Required | Description                                  |
| ----------- | -------- | -------- | -------------------------------------------- |
| `projectId` | `Object` | Yes      | The unique ID of the project to fetch plans. |

***

### Response

```json
[
  {
    "id": 3273,
    "type": "APPIUM",
    "project_id": 1418,
    "project_name": "BerGratisTest",
    "company_id": 5267,
    "plan_name": "OpenApp",
    "scenarios": [23055],
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
    "last_execution": {
      "id": 268131,
      "user_id": 5322,
      "username": "mehmetaksahin",
      "company_id": 5267,
      "project_id": 1418,
      "project_name": "BerGratisTest",
      "plan_id": 3273,
      "plan_name": "OpenApp",
      "test_results": [3498140],
      "runtime": 1000,
      "result_summary": {
        "ERROR": 1
      },
      "start_date": "2024-12-04T15:07:52Z",
      "end_date": "2024-12-04T15:08:23Z",
      "test_result_status_counts": "[ERROR, 1]"
    },
    "failed_test_retry_count": 0,
    "alerts_enabled_result": false,
    "project_enabled": true,
    "test_run_type": "CROSS",
    "created_at": "2024-12-04T15:07:48Z",
    "updated_at": "2024-12-04T15:07:48Z",
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
          "id": 1177,
          "name": "Galaxy Note 20",
          "operating_system": "ANDROID",
          "environment_type": "Galaxy_Note20",
          "environment_version": "13",
          "device": {
            "model": {
              "manufacturer": {
                "code": "SAMSUNG",
                "name": "SAMSUNG"
              },
              "device_type": "PHONE",
              "code": "Galaxy_Note20",
              "name": "Galaxy Note 20",
              "operating_system": "ANDROID"
            },
            "udid": "RF8N82182PN"
          },
          "device_model_name": "Galaxy Note 20",
          "enabled": true,
          "operating_system_clean_name": "Android",
          "mobile": true
        }
      }
    ],
    "test_plan_java_parameters": [],
    "clear_app_data": false,
    "uninstall_app_after_test": false,
    "fetch_app_files": []
  }
]
```

#### Response Fields

| Field                       | Type      | Description                                                               |
| --------------------------- | --------- | ------------------------------------------------------------------------- |
| `id`                        | `Long`    | Unique ID of the test plan.                                               |
| `type`                      | `String`  | Type of the test plan (e.g., `APPIUM`).                                   |
| `plan_name`                 | `String`  | Name of the test plan.                                                    |
| `project_id`                | `Long`    | ID of the project the test plan belongs to.                               |
| `project_name`              | `String`  | Name of the project associated with the test plan.                        |
| `company_id`                | `Long`    | The ID of the company that owns the project.                              |
| `scenarios`                 | `Array`   | List of scenario IDs associated with the test plan.                       |
| `period`                    | `Object`  | Period configuration for the test plan (e.g., `MANUAL`, repeat interval). |
| `alerts`                    | `Array`   | List of alerts associated with the test plan.                             |
| `enabled`                   | `Boolean` | Whether the test plan is enabled.                                         |
| `group_plan`                | `Boolean` | Indicates whether this is a group plan.                                   |
| `plan_parallel_test_limit`  | `Integer` | The maximum number of parallel tests allowed for this plan.               |
| `last_execution`            | `Object`  | Details of the last execution of the test plan.                           |
| `failed_test_retry_count`   | `Integer` | Number of retries for failed tests.                                       |
| `alerts_enabled_result`     | `Boolean` | Whether alerts are enabled for the test result.                           |
| `project_enabled`           | `Boolean` | Whether the associated project is enabled.                                |
| `test_run_type`             | `String`  | The type of the test run (e.g., `CROSS`).                                 |
| `created_at`                | `String`  | Timestamp when the test plan was created.                                 |
| `updated_at`                | `String`  | Timestamp when the test plan was last updated.                            |
| `created_by`                | `String`  | The user who created the test plan.                                       |
| `updated_by`                | `String`  | The user who last updated the test plan.                                  |
| `xray_enabled`              | `Boolean` | Whether XRay integration is enabled for the test plan.                    |
| `test_rail_enabled`         | `Boolean` | Whether TestRail integration is enabled.                                  |
| `test_rail_any_mismatch`    | `Boolean` | Whether TestRail any mismatch is allowed.                                 |
| `is_parent`                 | `Boolean` | Whether the test plan is a parent plan.                                   |
| `childs`                    | `Array`   | List of child test plans associated with the parent plan.                 |
| `screen_shot_type`          | `String`  | Type of screenshot captured (e.g., `YES` for screenshot enabled).         |
| `video_enabled`             | `Boolean` | Whether video recording is enabled for the test plan.                     |
| `environment_resolutions`   | `Array`   | List of environment resolution details.                                   |
| `test_plan_java_parameters` | `Array`   | Java parameters used by the test plan.                                    |
| `clear_app_data`            | `Boolean` | Whether app data should be cleared before running the test.               |
| `uninstall_app_after_test`  | `Boolean` | Whether the app should be uninstalled after the test.                     |
| `fetch_app_files`           | `Array`   | List of app files to be fetched before the test.                          |

***

### Error Codes

| HTTP Code | Error Message     | Description                                          |
| --------- | ----------------- | ---------------------------------------------------- |
| `400`     | `INVALID_REQUEST` | The request was malformed or contained errors.       |
| `404`     | `PLAN_NOT_FOUND`  | No test plan was found for the specified project ID. |
| `403`     | `ACCESS_DENIED`   | User lacks `PLAN_VIEW` authority.                    |
| `500`     | `INTERNAL_ERROR`  | An unexpected error occurred on the server side.     |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plans" \
--header 'Authorization: Bearer <your_access_token>'
```
