# Create Mobile Project

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Create Mobile Project

Allows a user with the `PROJECT_CREATE` authority to create a new mobile project. It requires a user to provide a request payload containing project details.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***

### Request Body

{\`{ "project\_name": "appium13", "repository\_path": "appium13", "test\_file\_type": "APPIUM\_JAVA", "test\_framework": "APPIUM", "test\_runner\_tool": "MAVEN", "company\_id": 5267, "is\_signed": false } \`}

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

{\`{ "id": 1428, "project\_name": "appiumdeneme", "enabled": true, "types": \[ "ANDRIOD", "IOS" ], "repository\_path": "appiumdeneme", "test\_framework": "APPIUM", "test\_file\_type": "APPIUM\_JAVA", "test\_runner\_tool": "MAVEN", "created\_at": "2024-12-06T04:58:52Z", "updated\_at": "2024-12-06T04:58:52Z", "created\_by": "mehmetaksahin", "updated\_by": "mehmetaksahin", "branch\_name": "master", "testrail\_enabled": false, "jira\_enabled": false, "xray\_enabled": false, "ios\_mobile\_app": "Oliz-2.0.0\_306\_-983d7eac-098fd926.ipa", "android\_mobile\_app": "FLO\_v4.1.35\_apkpure.com-8d9da7ef.apk", "ios\_app\_hash": "4d54bde38ad152d970e3d9bc300b858d", "android\_app\_hash": "65300b98fc9bfa19c7d6a5e2415dbfba", "apk\_meta": { "package\_name": "com.flo.ayakkabi", "label": "FLO", "icon": "res/mipmap-mdpi-v4/ic\_launcher.png", "version\_name": "4.1.35", "version\_code": 41035, "min\_sdk\_version": "19", "target\_sdk\_version": "30", "gl\_es\_version": { "major": 2, "minor": 0, "required": false } }, "ios\_meta": { "bundle\_name": "Oliz", "bundle\_display\_name": "Oliz", "bundle\_version": "306", "bundle\_min\_os\_version": "14.0", "bundle\_development\_region": "tr", "bundle\_executable": "Runner", "bundle\_icon\_files": "", "bundle\_info\_dict\_version": "6.0", "bundle\_package\_type": "APPL", "bundle\_main\_story\_board\_file": "Main" }, "is\_signed": false }\`}

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
