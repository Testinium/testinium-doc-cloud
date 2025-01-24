# Get Active Test Plans

This endpoint retrieves active test plans based on the provided company ID and optional filters such as project ID and active test statuses. The user must have the `PLAN_VIEW` authority to access this endpoint.

***

### Endpoint Details

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/active`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Name                 | Type   | Required | Description                                                                      |
| -------------------- | ------ | -------- | -------------------------------------------------------------------------------- |
| `companyId`          | `Long` | Yes      | The unique ID of the company for which active test plans are to be retrieved.    |
| `projectId`          | `Long` | No       | The unique ID of the project to filter active test plans.                        |
| `activeTestStatuses` | `List` | No       | A list of statuses to filter test plans (e.g., `WAITING`, `RUNNING`, `SUCCESS`). |

***

***

### Example Response

```json
[
    {
        "id": 1460,
        "type": "SELENIUM",
        "project_id": 427,
        "project_name": "YukTesti",
        "company_id": 5251,
        "plan_name": "YüktestiNode",
        "scenarios": [10062, 10063, 10567],
        "period": {
            "period_type": "MANUAL",
            "days_of_week": "",
            "scheduled_days_of_week": [],
            "repeat_period": 60
        },
        "alerts": [],
        "enabled": true,
        "group_plan": false,
        "plan_parallel_test_limit": 200,
        "last_execution": {
            "id": 225699,
            "user_id": 5245,
            "username": "mehmetaksahin",
            "company_id": 5251,
            "project_id": 427,
            "project_name": "YukTesti",
            "plan_id": 1460,
            "plan_name": "YüktestiNode",
            "test_results": [3271768, 3271769, 3272272, 3272273],
            "runtime": 4215000,
            "result_summary": {
                "ERROR": 67,
                "FAILURE": 4,
                "WAITING": 393,
                "SUCCESS": 42
            },
            "start_date": "2025-01-23T14:05:43Z"
        },
        "failed_test_retry_count": 0,
        "alerts_enabled_result": false,
        "max_execution_time": 120,
        "project_enabled": true,
        "test_run_type": "CROSS",
        "created_at": "2024-11-06T12:18:48Z",
        "updated_at": "2024-11-06T12:56:25Z",
        "created_by": "mehmetaksahin",
        "updated_by": "mehmetaksahin",
        "xray_enabled": false,
        "test_rail_enabled": true,
        "test_rail_project_id": 34,
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
]

```

***

### Response Fields

| Field                     | Type         | Description                                                                   |
| ------------------------- | ------------ | ----------------------------------------------------------------------------- |
| `id`                      | `Long`       | The unique ID of the test plan.                                               |
| `type`                    | `String`     | The type of the test plan (e.g., `SELENIUM`).                                 |
| `project_id`              | `Long`       | The unique ID of the associated project.                                      |
| `project_name`            | `String`     | The name of the associated project.                                           |
| `company_id`              | `Long`       | The unique ID of the associated company.                                      |
| `plan_name`               | `String`     | The name of the test plan.                                                    |
| `scenarios`               | `List<Long>` | A list of scenario IDs associated with the test plan.                         |
| `last_execution`          | `Object`     | The details of the last execution for the test plan.                          |
| `result_summary`          | `Object`     | A summary of the results for the last execution (e.g., `WAITING`, `SUCCESS`). |
| `environment_resolutions` | `List`       | A list of environments and their resolutions used for testing.                |

***

### Error Codes

| HTTP Code | Error Message           | Description                                             |
| --------- | ----------------------- | ------------------------------------------------------- |
| `401`     | `ACCESS_DENIED`         | The user lacks the `PLAN_VIEW` authority.               |
| `400`     | `INVALID_REQUEST`       | One or more required parameters are missing or invalid. |
| `404`     | `COMPANY_NOT_FOUND`     | The specified company was not found.                    |
| `404`     | `PROJECT_NOT_FOUND`     | The specified project was not found.                    |
| `500`     | `SYSTEM_INTERNAL_ERROR` | An unexpected error occurred.                           |

### Example Request

```bash
curl --location --request GET 'https://testinium.io/Testinium.RestApi/api/plans/active?companyId=5251&activeTestStatuses=WAITING' \
--header 'Authorization: Bearer <your_access_token>' \
```
