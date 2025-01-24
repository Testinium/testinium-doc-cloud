# Get Detailed Test Result

This endpoint retrieves detailed information about a test result, including paginated test commands. The user must have the `TEST_RESULT_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/results/{resultId}/detailed/filter`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter  | Type   | Required | Description                       |
| ---------- | ------ | -------- | --------------------------------- |
| `resultId` | `Long` | Yes      | The unique ID of the test result. |

***

### Query Parameters

| Parameter | Type      | Required | Description                                                                |
| --------- | --------- | -------- | -------------------------------------------------------------------------- |
| `page`    | `Integer` | Yes      | The page number for paginated test commands.                               |
| `size`    | `Integer` | Yes      | The number of test commands per page.                                      |
| `isDesc`  | `Boolean` | No       | Determines whether the test commands should be sorted in descending order. |

***

### Response

The response includes detailed information about the test result, along with a paginated list of test commands.

```json
{
    "id": 3272281,
    "level": "ERROR",
    "runtime": 2778,
    "environment": {
        "id": 666,
        "name": "IPHONE 6S",
        "operating_system": "IOS",
        "environment_type": "IPHONE 6S",
        "environment_version": "15.7.5",
        "device": {
            "model": {
                "manufacturer": {
                    "code": "APPLE",
                    "name": "APPLE"
                },
                "device_type": "PHONE",
                "code": "IPHONE 6S",
                "name": "IPHONE 6S",
                "operating_system": "IOS"
            },
            "udid": "33e67c137457ee479aae6f5c47b59f57c849a025"
        },
        "device_model_name": "IPHONE 6S",
        "enabled": true,
        "operating_system_clean_name": "iOS",
        "mobile": true
    },
    "session_id": "43362366701150800012",
    "message": "Test report could not be found. Please check your executor log.",
    "screenshots_enabled": false,
    "screen_shot_type": "NO",
    "video_enabled": false,
    "performance_data_enabled": false,
    "test_key": "TEST-C5251-P1440-E225704-S9988",
    "video_format": "FLV",
    "node_log_path": "https://testinium-dev-cloud-k8s.s3.amazonaws.com/5251/2025/01/23/43362366701150800012/node.log",
    "executor_log_path": "https://testinium-dev-cloud-k8s.s3.amazonaws.com/5251/2025/01/23/43362366701150800012/testResult.log",
    "screen_resolution": "1024x768",
    "user_id": 5245,
    "project_id": 401,
    "plan_id": 1440,
    "scenario_id": 9988,
    "execution_id": 225704,
    "company_id": 5251,
    "test_result_commands": [],
    "test_result_commands_paginated_result": {
        "current_page": 1,
        "total_count": 0,
        "page_count": 0,
        "next_page": "",
        "previous_page": "",
        "item_list": [],
        "rest_api_url": "https://devcluster.testinium.io/Testinium.RestApi"
    },
    "user_info": {
        "id": 5245,
        "name": "Mehmet",
        "surname": "Akşahin",
        "username": "mehmetaksahin",
        "email": "mehmet.aksahin@testinium.com",
        "enabled": true,
        "account_non_expired": true,
        "account_non_locked": true,
        "credential_non_expired": true,
        "language": "ENGLISH",
        "time_zone": "UTC",
        "company": "saha",
        "company_id": 5251,
        "current_company": "saha",
        "current_company_id": 5251,
        "roles": [
            "ROLE_CHANGE_USER",
            "ROLE_COMPANY_ADMIN",
            "ROLE_ADMIN",
            "ROLE_RUN_TEST",
            "ROLE_USER",
            "ROLE_INTEGRATION",
            "ROLE_NEW_USER",
            "ROLE_NEW_COMPANY_ADMIN",
            "ROLE_REPORT"
        ],
        "access_token": "afbe7d859ad86b5149f75077c52035e3"
    },
    "start_date": "2025-01-23T14:25:21Z",
    "end_date": "2025-01-23T14:25:24Z",
    "project": {
        "id": 401,
        "project_name": "abb-install-app",
        "enabled": true,
        "types": [
            "IOS"
        ],
        "repository_path": "abb-install-app",
        "test_framework": "APPIUM",
        "test_file_type": "APPIUM_JAVA",
        "test_runner_tool": "MAVEN",
        "created_at": "2023-05-20T12:49:05Z",
        "updated_at": "2023-05-20T13:00:21Z",
        "created_by": "mehmetaksahin",
        "updated_by": "mehmetaksahin",
        "branch_name": "refs/heads/master",
        "testrail_enabled": false,
        "jira_enabled": false,
        "xray_enabled": false,
        "ios_mobile_app": "app-23c33ff3.ipa",
        "ios_app_hash": "a18e09f6ff847020ed057bff784e771d",
        "ios_meta": {
            "bundle_name": "ABB Mobile Test",
            "bundle_display_name": "",
            "bundle_version": "1",
            "bundle_min_os_version": "13.0",
            "bundle_development_region": "en",
            "bundle_executable": "ABB Mobile Test",
            "bundle_icon_files": "",
            "bundle_info_dict_version": "6.0",
            "bundle_package_type": "APPL",
            "bundle_main_story_board_file": ""
        },
        "is_signed": false
    },
    "plan": {
        "id": 1440,
        "type": "APPIUM",
        "project_id": 401,
        "project_name": "abb-install-app",
        "company_id": 5251,
        "plan_name": "openApp",
        "scenarios": [
            9988
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
        "last_execution": {
            "id": 225704,
            "user_id": 5245,
            "username": "mehmetaksahin",
            "company_id": 5251,
            "project_id": 401,
            "project_name": "abb-install-app",
            "plan_id": 1440,
            "plan_name": "openApp",
            "test_results": [
                3272281
            ],
            "runtime": 2778,
            "result_summary": {
                "ERROR": 1
            },
            "start_date": "2025-01-23T14:25:08Z",
            "end_date": "2025-01-23T14:25:25Z",
            "test_result_status_counts": "[ERROR, 1]"
        },
        "failed_test_retry_count": 0,
        "alerts_enabled_result": false,
        "project_enabled": true,
        "test_run_type": "SEQUENCE",
        "created_at": "2023-05-20T12:50:13Z",
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
                    "id": 666,
                    "name": "IPHONE 6S",
                    "operating_system": "IOS",
                    "environment_type": "IPHONE 6S",
                    "environment_version": "15.7.5",
                    "device": {
                        "model": {
                            "manufacturer": {
                                "code": "APPLE",
                                "name": "APPLE"
                            },
                            "device_type": "PHONE",
                            "code": "IPHONE 6S",
                            "name": "IPHONE 6S",
                            "operating_system": "IOS"
                        },
                        "udid": "33e67c137457ee479aae6f5c47b59f57c849a025"
                    },
                    "device_model_name": "IPHONE 6S",
                    "enabled": true,
                    "operating_system_clean_name": "iOS",
                    "mobile": true
                }
            },
            {
                "environment": {
                    "id": 668,
                    "name": "IPHONE 8",
                    "operating_system": "IOS",
                    "environment_type": "IPHONE 8",
                    "environment_version": "16.1.1",
                    "device": {
                        "model": {
                            "manufacturer": {
                                "code": "APPLE",
                                "name": "APPLE"
                            },
                            "device_type": "PHONE",
                            "code": "IPHONE 8",
                            "name": "IPHONE 8",
                            "operating_system": "IOS"
                        },
                        "udid": "b302996742bf15bfdd80b05b9cf99e80cbded70f"
                    },
                    "device_model_name": "IPHONE 8",
                    "enabled": true,
                    "operating_system_clean_name": "iOS",
                    "mobile": true
                }
            },
            {
                "environment": {
                    "id": 660,
                    "name": "IPHONE 6S",
                    "operating_system": "IOS",
                    "environment_type": "IPHONE 6S",
                    "environment_version": "13.6.1",
                    "device": {
                        "model": {
                            "manufacturer": {
                                "code": "APPLE",
                                "name": "APPLE"
                            },
                            "device_type": "PHONE",
                            "code": "IPHONE 6S",
                            "name": "IPHONE 6S",
                            "operating_system": "IOS"
                        },
                        "udid": "16c25ac125cf1ab8c197fbb1cea64a31c9039df9"
                    },
                    "device_model_name": "IPHONE 6S",
                    "enabled": true,
                    "operating_system_clean_name": "iOS",
                    "mobile": true
                }
            }
        ],
        "test_plan_java_parameters": [],
        "clear_app_data": false,
        "uninstall_app_after_test": false,
        "fetch_app_files": []
    },
    "scenario": {
        "id": 9988,
        "type": "APPIUM",
        "scenario_name": "openApp",
        "enabled": true,
        "deleted": false,
        "project_test_rail_enabled": false,
        "execute_mode": "AUTOMATED",
        "source_file": "com/saha/test/BaseTest.java",
        "project_id": 401,
        "plans": [
            1440
        ],
        "childs": [],
        "parameterized": false,
        "has_parameterized_class": false,
        "java_test_class": "com.saha.test.BaseTest",
        "java_test_methods": "openMobileApp",
        "test_scenario_java_parameters": [],
        "group": false
    },
    "fetched_file_list": []
}
```

### Response Fields

| Field                               | Type           | Description                                            |
| ----------------------------------- | -------------- | ------------------------------------------------------ |
| `id`                                | `Long`         | The unique ID of the test result.                      |
| `level`                             | `String`       | The severity level of the test result (e.g., `ERROR`). |
| `runtime`                           | `Integer`      | The execution time of the test in milliseconds.        |
| `environment`                       | `Object`       | Details about the testing environment.                 |
| `scenario`                          | `Object`       | Detailed information about the test scenario.          |
| `fetched_file_list`                 | `List<String>` | List of files fetched during the test execution.       |
| `testResultCommandsPaginatedResult` | `Object`       | Paginated results of detailed test commands.           |

***

#### Environment

| Field Name                    | Type    | Description                                                                        |
| ----------------------------- | ------- | ---------------------------------------------------------------------------------- |
| `id`                          | Integer | A unique identifier for the environment.                                           |
| `name`                        | String  | The name of the environment (e.g., `IPHONE 6S`).                                   |
| `operating_system`            | String  | The operating system used in the environment (e.g., `IOS`).                        |
| `environment_type`            | String  | The type of environment (e.g., `PHONE`, `TABLET`).                                 |
| `environment_version`         | String  | The version of the environment.                                                    |
| `device`                      | Object  | Details about the device used in the environment. See **Device** for more details. |
| `device_model_name`           | String  | The name of the device model (e.g., `IPHONE 6S`).                                  |
| `enabled`                     | Boolean | Indicates whether the environment is active.                                       |
| `operating_system_clean_name` | String  | The clean name of the operating system (e.g., `iOS`).                              |
| `mobile`                      | Boolean | Indicates whether the device is mobile.                                            |

***

#### Device

| Field Name | Type   | Description                                                     |
| ---------- | ------ | --------------------------------------------------------------- |
| `model`    | Object | Details about the device model. See **Model** for more details. |
| `udid`     | String | The Unique Device Identifier (UDID) of the device.              |

***

#### Model

| Field Name         | Type   | Description                                                                       |
| ------------------ | ------ | --------------------------------------------------------------------------------- |
| `manufacturer`     | Object | Information about the device manufacturer. See **Manufacturer** for more details. |
| `device_type`      | String | The type of device (e.g., `PHONE`, `TABLET`).                                     |
| `code`             | String | The code representing the device (e.g., `IPHONE 6S`).                             |
| `name`             | String | The name of the device.                                                           |
| `operating_system` | String | The operating system of the device.                                               |

***

#### Manufacturer

| Field Name | Type   | Description                              |
| ---------- | ------ | ---------------------------------------- |
| `code`     | String | The manufacturer's code (e.g., `APPLE`). |
| `name`     | String | The manufacturer's name (e.g., `Apple`). |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `404`     | `TEST_RESULT_NOT_FOUND` | The specified test result ID was not found.      |
| `403`     | `ACCESS_DENIED`         | User lacks `TEST_RESULT_VIEW` authority.         |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/results/{resultId}/detailed/filter?page=1&size=10&isDesc=true' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
