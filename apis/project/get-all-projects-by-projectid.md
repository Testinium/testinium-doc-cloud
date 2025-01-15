# Get All Projects By ProjectID

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get Project By ProjectID

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

{\`\[ { "id": 390, "project\_name": "project1", "enabled": true, "types": \[ "IOS" ], "repository\_path": "project1", "test\_framework": "APPIUM", "test\_file\_type": "APPIUM\_GAUGE", "test\_runner\_tool": "MAVEN", "created\_at": "2023-02-15T08:28:00Z", "updated\_at": "2023-02-16T10:16:56Z", "created\_by": "user", "updated\_by": "user", "branch\_name": "refs/heads/master", "testrail\_enabled": false, "jira\_enabled": false, "xray\_enabled": false, "ios\_mobile\_app": "iosapp.ipa", "ios\_app\_hash": "02059ea989ebbb0a3c85aef4053c1b3b", "ios\_meta": { "bundle\_name": "Bundle", "bundle\_display\_name": "bundle\_display\_name", "bundle\_version": "123", "bundle\_min\_os\_version": "11.0", "bundle\_development\_region": "de", "bundle\_executable": "Bundle", "bundle\_icon\_files": "", "bundle\_info\_dict\_version": "6.0", "bundle\_package\_type": "APPL", "bundle\_main\_story\_board\_file": "" } } ]\`}

#### WEB Project Response

{\`\[ { "id": 1025, "project\_name": "web project", "enabled": true, "types": \[ "WEB" ], "repository\_path": "web-project", "test\_framework": "SELENIUM", "test\_file\_type": "SELENIUM\_GAUGE", "test\_runner\_tool": "MAVEN", "created\_at": "2023-02-09T16:51:04Z", "updated\_at": "2023-03-07T11:07:22Z", "created\_by": "mehmetaksahin", "updated\_by": "mehmetaksahin", "branch\_name": "master", "testrail\_enabled": false, "jira\_enabled": false, "xray\_enabled": false } ]\`}

#### Service Project Response

{\`\[ { "id": 1405, "project\_name": "karateprojesi", "enabled": true, "types": \[ "SERVICE" ], "repository\_path": "karateprojesi", "test\_framework": "SERVICE", "test\_file\_type": "KARATE", "test\_runner\_tool": "MAVEN", "created\_at": "2024-11-30T13:22:57Z", "updated\_at": "2024-12-01T04:55:28Z", "created\_by": "ali\_veli", "updated\_by": "ali\_veli", "branch\_name": "main", "testrail\_enabled": false, "jira\_enabled": true, "xray\_enabled": false } ]\`}

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
