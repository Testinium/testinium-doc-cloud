# Create Mobile Project

Allows a user with the `PROJECT_CREATE` authority to create a new mobile project. It requires a user to provide a request payload containing project details.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***

### Request Body

```json
{
  "project_name": "appium13",
  "repository_path": "appium13",
  "test_file_type": "APPIUM_JAVA",
  "test_framework": "APPIUM",
  "test_runner_tool": "MAVEN",
  "company_id": 5267,
  "is_signed": false
}
```

| Field            | Type      | Required | Description                                               |
| ---------------- | --------- | -------- | --------------------------------------------------------- |
| `companyId`      | `Long`    | Yes      | The ID of the company that the project belongs to.        |
| `isSigned`       | `Boolean` | No       | Indicates whether the project is signed.                  |
| `projectName`    | `String`  | Yes      | The name of the project being created.                    |
| `repositoryPath` | `String`  | Yes      | The path to the project's repository.                     |
| `testFileType`   | `String`  | Yes      | The type of test file (e.g., `SERVICE_JAVA`).             |
| `testFramework`  | `String`  | Yes      | The test framework used by the project (e.g., `SERVICE`). |
| `testRunnerTool` | `String`  | Yes      | The tool used to run tests (e.g., `MAVEN`).               |

***

### Response

The response will contain the details of the created project.

```json
{
    "id": 1428,
    "project_name": "appiumdeneme",
    "enabled": true,
    "types": [
        "ANDRIOD",
        "IOS"
    ],
    "repository_path": "appiumdeneme",
    "test_framework": "APPIUM",
    "test_file_type": "APPIUM_JAVA",
    "test_runner_tool": "MAVEN",
    "created_at": "2024-12-06T04:58:52Z",
    "updated_at": "2024-12-06T04:58:52Z",
    "created_by": "mehmetaksahin",
    "updated_by": "mehmetaksahin",
    "branch_name": "master",
    "testrail_enabled": false,
    "jira_enabled": false,
    "xray_enabled": false,
    "ios_mobile_app": "Oliz-2.0.0_306_-983d7eac-098fd926.ipa",
    "android_mobile_app": "FLO_v4.1.35_apkpure.com-8d9da7ef.apk",
    "ios_app_hash": "4d54bde38ad152d970e3d9bc300b858d",
    "android_app_hash": "65300b98fc9bfa19c7d6a5e2415dbfba",
    "apk_meta": {
        "package_name": "com.flo.ayakkabi",
        "label": "FLO",
        "icon": "res/mipmap-mdpi-v4/ic_launcher.png",
        "version_name": "4.1.35",
        "version_code": 41035,
        "min_sdk_version": "19",
        "target_sdk_version": "30",
        "gl_es_version": {
            "major": 2,
            "minor": 0,
            "required": false
        }
    },
    "ios_meta": {
        "bundle_name": "Oliz",
        "bundle_display_name": "Oliz",
        "bundle_version": "306",
        "bundle_min_os_version": "14.0",
        "bundle_development_region": "tr",
        "bundle_executable": "Runner",
        "bundle_icon_files": "",
        "bundle_info_dict_version": "6.0",
        "bundle_package_type": "APPL",
        "bundle_main_story_board_file": "Main"
    },
    "is_signed": false
}
```

#### Response Fields

| Field              | Type      | Description                                        |
| ------------------ | --------- | -------------------------------------------------- |
| `id`               | `Long`    | Unique ID of the created project.                  |
| `company_id`       | `Long`    | The ID of the company associated with the project. |
| `project_name`     | `String`  | The name of the created project.                   |
| `repository_path`  | `String`  | The repository path for the project.               |
| `test_file_type`   | `String`  | The type of test file associated with the project. |
| `test_framework`   | `String`  | The test framework used for the project.           |
| `test_runner_tool` | `String`  | The tool used to run tests for the project.        |
| `is_signed`        | `Boolean` | Whether the project is signed or not.              |
| `created_at`       | `String`  | Timestamp when the project was created.            |
| `updated_at`       | `String`  | Timestamp when the project was last updated.       |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `403`     | `ACCESS_DENIED`         | User lacks `PROJECT_CREATE` authority.           |
| `404`     | `COMPANY_NOT_FOUND`     | The company with the provided ID does not exist. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request POST "https://testinium.io/Testinium.RestApi/api/projects/" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data '{
  "project_name": "appium13",
  "repository_path": "appium13",
  "test_file_type": "APPIUM_JAVA",
  "test_framework": "APPIUM",
  "test_runner_tool": "MAVEN",
  "company_id": 5267,
  "is_signed": false
}
```
