# Get All Projects By Company ID

This endpoint retrieves all projects associated with a specific company. Users must have the `ROLE_ADMIN` or `ROLE_INTEGRATION` role to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/company/{companyId}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                                            |
| ----------- | ------ | -------- | ------------------------------------------------------ |
| `companyId` | `Long` | Yes      | The unique ID of the company to retrieve projects for. |

***

### Query Parameters

No query parameters are required.

***

### Request Body

No request body is required for this endpoint.

***

### Response

The response contains a list of projects, each including various project details such as name, repository path, test framework, and iOS-specific metadata.

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
]
```

#### Response Fields

| Field              | Type      | Description                                                                        |
| ------------------ | --------- | ---------------------------------------------------------------------------------- |
| `id`               | `Long`    | The unique ID of the project.                                                      |
| `project_name`     | `String`  | The name of the project.                                                           |
| `enabled`          | `Boolean` | Indicates whether the project is enabled.                                          |
| `types`            | `Array`   | List of supported test types (e.g., `IOS`, `ANDROID`).                             |
| `repository_path`  | `String`  | The repository path of the project.                                                |
| `test_framework`   | `String`  | The test framework used (e.g., `APPIUM`).                                          |
| `test_file_type`   | `String`  | The type of test file used (e.g., `APPIUM_GAUGE`).                                 |
| `test_runner_tool` | `String`  | The test runner tool used (e.g., `MAVEN`).                                         |
| `created_at`       | `String`  | The date and time when the project was created in ISO 8601 format.                 |
| `updated_at`       | `String`  | The date and time when the project was last updated in ISO 8601 format.            |
| `created_by`       | `String`  | The username of the user who created the project.                                  |
| `updated_by`       | `String`  | The username of the user who last updated the project.                             |
| `branch_name`      | `String`  | The Git branch name associated with the project.                                   |
| `testrail_enabled` | `Boolean` | Indicates whether the project is connected to TestRail.                            |
| `jira_enabled`     | `Boolean` | Indicates whether the project is connected to Jira.                                |
| `xray_enabled`     | `Boolean` | Indicates whether the project is connected to Xray.                                |
| `ios_mobile_app`   | `String`  | The name of the iOS mobile application associated with the project.                |
| `ios_app_hash`     | `String`  | The hash of the iOS application file.                                              |
| `ios_meta`         | `Object`  | Metadata information about the iOS application (e.g., version, bundle name, etc.). |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `403`     | `ACCESS_DENIED`         | User lacks `PROJECT_VIEW` authority.             |
| `404`     | `PROJECT_NOT_FOUND`     | No project was found for the specified criteria. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/projects/company/{companyId}" \
--header 'Authorization: Bearer <your_access_token>'
```
