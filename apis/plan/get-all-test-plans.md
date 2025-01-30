# Get All Test Plans

This endpoint retrieves all test plans for the authenticated user's company, optionally filtering by project ID and active status. The user must have the `PLAN_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/lazy`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Request Parameters

| Parameter   | Type      | Required | Default | Description                                        |
| ----------- | --------- | -------- | ------- | -------------------------------------------------- |
| `projectId` | `Long`    | No       | `null`  | The unique ID of the project to filter test plans. |
| `active`    | `Boolean` | No       | `true`  | Whether to fetch only active test plans.           |

***

### Response

The response is a list of test plans with detailed information.

```json
{
        "id": 11695,
        "type": "SELENIUM",
        "project_id": 5876,
        "project_name": "InTicket Test Project",
        "company_id": 2760,
        "plan_name": "Emergency Warnings Test Plan",
        "scenarios": [
            70024,
            70026
        ],
        "alerts": [
            {
                "alert_type": "EMAIL",
                "alert_sending_status": "EVERY_TEST",
                "target": "atetestteam@acibadem.com",
                "plan_id": 11695,
                "enabled": true,
                "unsubscribe_link_eliminated": false
            }
        ],
        "enabled": true,
        "group_plan": false,
        "plan_parallel_test_limit": 1,
        "failed_test_retry_count": 1,
        "alerts_enabled_result": false,
        "project_enabled": true,
        "test_run_type": "CROSS",
        "created_at": "2021-09-13T05:57:43Z",
        "updated_at": "2022-07-18T14:32:32Z",
        "created_by": "acibadem",
        "updated_by": "onurhanozcan",
        "xray_enabled": false,
        "screen_shot_type": "YES",
        "video_enabled": true,
        "test_plan_java_parameters": [],
        "performance_data_enabled": false,
        "file_download_path": ""
    },
    {
        "id": 11706,
        "type": "APPIUM",
        "project_id": 5927,
        "project_name": "Patient Online Android Project",
        "company_id": 2760,
        "plan_name": "Measurements Test Plan",
        "scenarios": [
            70043
        ],
        "alerts": [],
        "enabled": true,
        "group_plan": false,
        "plan_parallel_test_limit": 10,
        "failed_test_retry_count": 0,
        "alerts_enabled_result": false,
        "project_enabled": true,
        "test_run_type": "CROSS",
        "created_at": "2021-09-13T10:49:32Z",
        "created_by": "acibadem",
        "updated_by": "acibadem",
        "xray_enabled": false,
        "screen_shot_type": "YES",
        "video_enabled": true,
        "test_plan_java_parameters": [],
        "clear_app_data": false,
        "uninstall_app_after_test": false
    },
```

### Response Fields

| Field                       | Type      | Description                                                       |
| --------------------------- | --------- | ----------------------------------------------------------------- |
| `id`                        | `Long`    | Unique ID of the test plan.                                       |
| `type`                      | `String`  | The type of test plan (e.g., `SELENIUM`, `APPIUM`).               |
| `project_id`                | `Long`    | ID of the associated project.                                     |
| `project_name`              | `String`  | Name of the associated project.                                   |
| `company_id`                | `Long`    | ID of the company that owns the test plan.                        |
| `plan_name`                 | `String`  | Name of the test plan.                                            |
| `scenarios`                 | `Array`   | List of scenario IDs linked to the test plan.                     |
| `alerts`                    | `Array`   | List of alerts associated with the test plan.                     |
| `enabled`                   | `Boolean` | Whether the test plan is enabled.                                 |
| `group_plan`                | `Boolean` | Whether the test plan is a group plan.                            |
| `plan_parallel_test_limit`  | `Integer` | Maximum parallel tests allowed.                                   |
| `failed_test_retry_count`   | `Integer` | Number of retries for failed tests.                               |
| `alerts_enabled_result`     | `Boolean` | Whether alerts are enabled for this plan.                         |
| `project_enabled`           | `Boolean` | Whether the associated project is enabled.                        |
| `test_run_type`             | `String`  | The type of test execution (e.g., `CROSS`).                       |
| `created_at`                | `String`  | Timestamp of when the test plan was created.                      |
| `updated_at`                | `String`  | Timestamp of when the test plan was last updated.                 |
| `created_by`                | `String`  | Username of the creator of the test plan.                         |
| `updated_by`                | `String`  | Username of the last updater of the test plan.                    |
| `xray_enabled`              | `Boolean` | Whether Xray integration is enabled.                              |
| `screen_shot_type`          | `String`  | Whether screenshots are taken (`YES`, `NO`).                      |
| `video_enabled`             | `Boolean` | Whether video recording is enabled.                               |
| `test_plan_java_parameters` | `Array`   | Java parameters used in the test plan.                            |
| `performance_data_enabled`  | `Boolean` | Whether performance data collection is enabled.                   |
| `file_download_path`        | `String`  | File download path if applicable.                                 |
| `clear_app_data`            | `Boolean` | (For mobile tests) Whether app data is cleared.                   |
| `uninstall_app_after_test`  | `Boolean` | (For mobile tests) Whether the app is uninstalled after the test. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `403`     | `ACCESS_DENIED`         | User lacks `PLAN_VIEW` authority.                          |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained invalid parameters. |
| `500`     | `SYSTEM_INTERNAL_ERROR` | An unexpected error occurred on the server side.           |

***

### Example Request

```bash
curl --location --request GET 'https://testinium.io/Testinium.RestApi/api/plans/lazy?projectId=5876&active=true' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
