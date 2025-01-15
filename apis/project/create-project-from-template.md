# Create Project From Template

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Create Project From Template

This endpoint allows the creation of a new Selenium project using a predefined template. Users must have the `PROJECT_CREATE` authority to use this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/template`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***

### Request Body

The request body must be in JSON format and include the following fields:

| Parameter     | Type         | Required | Description                                                                       |
| ------------- | ------------ | -------- | --------------------------------------------------------------------------------- |
| `project_dto` | `ProjectDTO` | Yes      | The details of the project being created, including name, description, etc.       |
| `site_url`    | `String`     | No       | The site URL for the project, defaults to `https://www.testinium.com` if invalid. |

#### `ProjectDTO` Fields:

| Parameter          | Type           | Required | Description                                                                |
| ------------------ | -------------- | -------- | -------------------------------------------------------------------------- |
| `project_name`     | `String`       | Yes      | The name of the project.                                                   |
| `description`      | `String`       | No       | A brief description of the project.                                        |
| `enabled`          | `Boolean`      | Yes      | Specifies whether the project is enabled.                                  |
| `company_id`       | `Long`         | Yes      | The ID of the company to which the project belongs.                        |
| `types`            | `List<String>` | Yes      | A list of test types associated with the project (e.g., `IOS`, `ANDROID`). |
| `repository_path`  | `String`       | Yes      | The path to the project's repository.                                      |
| `test_framework`   | `String`       | Yes      | The testing framework used by the project (e.g., `SELENIUM`).              |
| `test_file_type`   | `String`       | Yes      | The type of test files used (e.g., `SELENIUM_JAVA`).                       |
| `test_runner_tool` | `String`       | Yes      | The tool used to run the tests (e.g., `MAVEN`).                            |
| `branch_name`      | `String`       | No       | The Git branch associated with the project.                                |
| `vcs_type`         | `String`       | No       | The version control system type (e.g., `SVN`, `GIT`).                      |
| `testrail_enabled` | `Boolean`      | No       | Indicates whether the project integrates with TestRail.                    |
| `jira_enabled`     | `Boolean`      | No       | Indicates whether the project integrates with Jira.                        |
| `xray_enabled`     | `Boolean`      | No       | Indicates whether the project integrates with Xray.                        |

Example JSON:

{\`{ "project\_name": "project\_name", "repository\_path": "repository\_path", "test\_file\_type": "SELENIUM\_JAVA", "test\_framework": "SELENIUM", "test\_runner\_tool": "MAVEN", "company\_id": company\_id, "site\_url": "https://www.siteurl.com/" }\`}

***

### Response

If the project is successfully created, the endpoint returns the created project details.

{\`{ "id": 1427, "project\_name": "project\_name", "enabled": true, "types": \[ "WEB" ], "repository\_path": "repository\_path", "test\_framework": "SELENIUM", "test\_file\_type": "SELENIUM\_JAVA", "test\_runner\_tool": "MAVEN", "created\_at": "2024-12-06T03:29:33Z", "updated\_at": "2024-12-06T03:29:33Z", "created\_by": "mehmetaksahin", "updated\_by": "mehmetaksahin", "branch\_name": "master", "testrail\_enabled": false, "jira\_enabled": false, "xray\_enabled": false }\`}

***

### Error Codes

| HTTP Code | Error Code               | Description                                            |
| --------- | ------------------------ | ------------------------------------------------------ |
| `400`     | `INVALID_REQUEST`        | The request body contains invalid or missing fields.   |
| `400`     | `MISSING_REQUIRED_FIELD` | The required field `project_dto` is missing.           |
| `403`     | `ACCESS_DENIED`          | The user does not have the `PROJECT_CREATE` authority. |
| `500`     | `INTERNAL_SERVER_ERROR`  | An unexpected error occurred during project creation.  |

***

### Example Request

```bash
curl --location --request POST "https://testinium.io/Testinium.RestApi/api/projects/template" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
  "project_name": "project_name",
  "repository_path": "repository_path",
  "test_file_type": "SELENIUM_JAVA",
  "test_framework": "SELENIUM",
  "test_runner_tool": "MAVEN",
  "company_id": company_id,
  "site_url": "https://www.siteurl.com/"
}'
```
