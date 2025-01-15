# Get All Projects By ProjectID

This endpoint retrieves the project associated with the user's current company. Users must have the `PROJECT_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectid}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Query Parameters

| Parameter | Type     | Required | Description                                                                                                  |
| --------- | -------- | -------- | ------------------------------------------------------------------------------------------------------------ |
| `email`   | `String` | No       | The email address of the user to filter projects. If provided, it must match the authenticated user's email. |

***

### Request Body

No request body is required. The `email` parameter can be passed as a query parameter.

***

### Response

The response contains a list of projects, including details such as the project name, test configurations, and other metadata.

#### Mobile Project Response

```json
[
    {
    "id": 390,
    "project_name": "project1",
    "enabled": true,
    "types": [
        "IOS"
    ],
    "repository_path": "project1",
    "test_framework": "APPIUM",
    "test_file_type": "APPIUM_GAUGE",
    "test_runner_tool": "MAVEN",
    "created_at": "2023-02-15T08:28:00Z",
    "updated_at": "2023-02-16T10:16:56Z",
    "created_by": "user",
    "updated_by": "user",
    "branch_name": "refs/heads/master",
    "testrail_enabled": false,
    "jira_enabled": false,
    "xray_enabled": false,
    "ios_mobile_app": "iosapp.ipa",
    "ios_app_hash": "02059ea989ebbb0a3c85aef4053c1b3b",
    "ios_meta": {
        "bundle_name": "Bundle",
        "bundle_display_name": "bundle_display_name",
        "bundle_version": "123",
        "bundle_min_os_version": "11.0",
        "bundle_development_region": "de",
        "bundle_executable": "Bundle",
        "bundle_icon_files": "",
        "bundle_info_dict_version": "6.0",
        "bundle_package_type": "APPL",
        "bundle_main_story_board_file": ""
    }
    }
]
```

#### WEB Project Response

```json
[
        {
        "id": 1025,
        "project_name": "web project",
        "enabled": true,
        "types": [
            "WEB"
        ],
        "repository_path": "web-project",
        "test_framework": "SELENIUM",
        "test_file_type": "SELENIUM_GAUGE",
        "test_runner_tool": "MAVEN",
        "created_at": "2023-02-09T16:51:04Z",
        "updated_at": "2023-03-07T11:07:22Z",
        "created_by": "mehmetaksahin",
        "updated_by": "mehmetaksahin",
        "branch_name": "master",
        "testrail_enabled": false,
        "jira_enabled": false,
        "xray_enabled": false
    }
]
```

#### Service Project Response

```json
[
    {
        "id": 1405,
        "project_name": "karateprojesi",
        "enabled": true,
        "types": [
            "SERVICE"
        ],
        "repository_path": "karateprojesi",
        "test_framework": "SERVICE",
        "test_file_type": "KARATE",
        "test_runner_tool": "MAVEN",
        "created_at": "2024-11-30T13:22:57Z",
        "updated_at": "2024-12-01T04:55:28Z",
        "created_by": "ali_veli",
        "updated_by": "ali_veli",
        "branch_name": "main",
        "testrail_enabled": false,
        "jira_enabled": true,
        "xray_enabled": false
    }
]
```

#### Response Fields

| Field                | Type      | Description                                                                    |
| -------------------- | --------- | ------------------------------------------------------------------------------ |
| `id`                 | `Long`    | The unique ID of the project.                                                  |
| `project_name`       | `String`  | The name of the project.                                                       |
| `enabled`            | `Boolean` | Indicates whether the project is enabled.                                      |
| `types`              | `Array`   | List of supported test types (e.g., `ANDROID`, `IOS`, `WEB`, `SERVICE`).       |
| `repository_path`    | `String`  | The repository path of the project.                                            |
| `test_framework`     | `String`  | The test framework used (e.g., `APPIUM`, `SELENIUM`, `SERVICE`).               |
| `test_file_type`     | `String`  | The type of test file used (e.g., `APPIUM_GAUGE`, `SELENIUM_GAUGE`, `KARATE`). |
| `test_runner_tool`   | `String`  | The test runner tool used (e.g., `MAVEN`).                                     |
| `created_at`         | `String`  | The date and time when the project was created in ISO 8601 format.             |
| `updated_at`         | `String`  | The date and time when the project was last updated in ISO 8601 format.        |
| `created_by`         | `String`  | The username of the user who created the project.                              |
| `updated_by`         | `String`  | The username of the user who last updated the project.                         |
| `branch_name`        | `String`  | The Git branch name associated with the project.                               |
| `testrail_enabled`   | `Boolean` | Indicates whether the project is connected to TestRail.                        |
| `jira_enabled`       | `Boolean` | Indicates whether the project is connected to Jira.                            |
| `xray_enabled`       | `Boolean` | Indicates whether the project is connected to Xray.                            |
| `ios_mobile_app`     | `String`  | The name of the iOS mobile application associated with the project.            |
| `android_mobile_app` | `String`  | The name of the Android mobile application associated with the project.        |
| `ios_app_hash`       | `String`  | The hash of the iOS application file.                                          |
| `android_app_hash`   | `String`  | The hash of the Android application file.                                      |
| `apk_meta`           | `Object`  | Metadata information about the Android application.                            |
| `ios_meta`           | `Object`  | Metadata information about the iOS application.                                |

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `PROJECT_NOT_FOUND`     | No project found with the given ID.              |
| `401`     | `UNAUTHORIZED_ACCESS`   | User authentication failed or token is missing.  |
| `403`     | `ACCESS_DENIED`         | User lacks `PROJECT_VIEW` authority.             |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/projects/{projectid}" \
--header 'Authorization: Bearer <your_access_token>'

```
