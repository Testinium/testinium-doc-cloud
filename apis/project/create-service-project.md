# Create Service Project

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Create Service Project

Allows a user with the `PROJECT_CREATE` authority to create a new service project. It requires a user to provide a request payload containing project details.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***

### Request Body

{\`{ "company\_id": 5267, "is\_signed": false, "project\_name": "deneme14", "repository\_path": "deneme14", "test\_file\_type": "SERVICE\_KARATE", "test\_framework": "SERVICE", "test\_runner\_tool": "MAVEN" }\`}

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

{\`{ "id": 1426, "project\_name": "deneme14", "enabled": true, "types": \[ "SERVICE" ], "repository\_path": "deneme14", "test\_framework": "SERVICE", "test\_file\_type": "SERVICE\_KARATE", "test\_runner\_tool": "MAVEN", "created\_at": "2024-12-06T02:45:43Z", "updated\_at": "2024-12-06T02:45:43Z", "created\_by": "mehmetaksahin", "updated\_by": "mehmetaksahin", "branch\_name": "master", "testrail\_enabled": false, "jira\_enabled": false, "xray\_enabled": false }\`}

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
  "company_id": company_id,
  "is_signed": false,
  "project_name": "project_name",
  "repository_path": "repository_path",
  "test_file_type": "SERVICE_KARATE",
  "test_framework": "SERVICE",
  "test_runner_tool": "MAVEN"
}
```
