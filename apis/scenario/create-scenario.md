# Create Scenario

{% hint style="info" %}
This API is also provides adding sub scenario.
{% endhint %}

This endpoint is used to **create a new scenario in a specified project**.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/scenarios`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameter

| Parameter   | Type     | Required | Description                                               |
| ----------- | -------- | -------- | --------------------------------------------------------- |
| `projectId` | `String` | Yes      | The ID of the project where the scenario will be created. |

***

### Request Body

```json
{
    "project_id": 3986,
    "testrail_enabled": false,
    "jira_enabled": false,
    "xray_enabled": false,
    "source_file": "Works.spec",
    "scenario_name": "denemeScenario",
    "description": "Create Scenario",
    "parent": {
        "id": 247459,
        "type": "SELENIUM",
        "scenario_name": "deneme13",
        "description": "deneme123",
        "enabled": true,
        "deleted": false,
        "testrail_enabled": false,
        "execute_mode": "AUTOMATED",
        "project_id": 3986,
        "childs": [],
        "parameterized": false,
        "has_parameterized_class": false,
        "test_scenario_java_parameters": [],
        "group": true
    },
    "max_execution_time": 60,
    "java_test_methods": "@onlySave"
}
```

### Request Fields

| Field                | Type      | Required | Description                                               |
| -------------------- | --------- | -------- | --------------------------------------------------------- |
| `project_id`         | `Integer` | Yes      | The ID of the project where the scenario will be created. |
| `testrail_enabled`   | `Boolean` | No       | Indicates if TestRail integration is enabled.             |
| `jira_enabled`       | `Boolean` | No       | Indicates if Jira integration is enabled.                 |
| `xray_enabled`       | `Boolean` | No       | Indicates if Xray integration is enabled.                 |
| `source_file`        | `String`  | Yes      | The name of the source file for the scenario.             |
| `scenario_name`      | `String`  | Yes      | The name of the scenario.                                 |
| `description`        | `String`  | No       | A description of the scenario.                            |
| `parent`             | `Object`  | No       | Information about the parent scenario (if any).           |
| `max_execution_time` | `Integer` | No       | The maximum execution time for the scenario (in seconds). |
| `java_test_methods`  | `String`  | No       | The Java test methods for the scenario.                   |

***

### Response

A successful request returns the **details of the created scenario**.

```json
{
    "id": 247460,
    "type": "SELENIUM",
    "scenario_name": "denemeScenario",
    "description": "Create Scenario",
    "enabled": true,
    "deleted": false,
    "testrail_enabled": false,
    "parent": {
        "id": 247459,
        "type": "SELENIUM",
        "scenario_name": "deneme13",
        "description": "deneme123",
        "enabled": true,
        "deleted": false,
        "testrail_enabled": false,
        "execute_mode": "AUTOMATED",
        "project_id": 3986,
        "parameterized": false,
        "has_parameterized_class": false,
        "test_scenario_java_parameters": [],
        "group": true
    },
    "execute_mode": "AUTOMATED",
    "source_file": "Works.spec",
    "max_execution_time": 60,
    "project_id": 3986,
    "childs": [],
    "parameterized": false,
    "has_parameterized_class": false,
    "java_test_class": "Works",
    "java_test_methods": "@onlySave",
    "test_scenario_java_parameters": [],
    "group": false
}
```

### Response Fields

| Field                           | Type      | Description                                               |
| ------------------------------- | --------- | --------------------------------------------------------- |
| `id`                            | `Integer` | The unique ID of the created scenario.                    |
| `type`                          | `String`  | The type of the scenario (`SELENIUM`, `APITest`, etc.).   |
| `scenario_name`                 | `String`  | The name of the scenario.                                 |
| `description`                   | `String`  | The description of the scenario.                          |
| `enabled`                       | `Boolean` | Indicates whether the scenario is active.                 |
| `deleted`                       | `Boolean` | Indicates whether the scenario is deleted.                |
| `testrail_enabled`              | `Boolean` | Indicates if TestRail integration is enabled.             |
| `parent`                        | `Object`  | The parent scenario details (if any).                     |
| `execute_mode`                  | `String`  | The execution mode (`AUTOMATED`, `MANUAL`).               |
| `source_file`                   | `String`  | The source file associated with the scenario.             |
| `max_execution_time`            | `Integer` | The maximum execution time for the scenario (in seconds). |
| `project_id`                    | `Integer` | The ID of the project associated with the scenario.       |
| `childs`                        | `Array`   | List of child scenarios (empty if none).                  |
| `parameterized`                 | `Boolean` | Indicates if the scenario is parameterized.               |
| `has_parameterized_class`       | `Boolean` | Indicates if it contains a parameterized class.           |
| `java_test_class`               | `String`  | The Java test class associated with the scenario.         |
| `java_test_methods`             | `String`  | The Java test methods associated with the scenario.       |
| `test_scenario_java_parameters` | `Array`   | List of Java test parameters.                             |
| `group`                         | `Boolean` | Indicates if this is a group scenario.                    |

***

### Error Codes

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `404`     | `PROJECT_NOT_FOUND`     | The specified `projectId` was not found.                  |
| `401`     | `UNAUTHORIZED_USER`     | The user is unauthorized or the token is missing/invalid. |
| `400`     | `INVALID_SCENARIO_NAME` | The provided scenario name is invalid or already exists.  |
| `500`     | `INTERNAL_SERVER_ERROR` | A general server error occurred.                          |

***

### Example Request

```bash
curl --location --request POST 'https://testinium.io/Testinium.RestApi/api/projects/{projectId}/scenarios' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "project_id": 3986,
    "testrail_enabled": false,
    "jira_enabled": false,
    "xray_enabled": false,
    "source_file": "Works.spec",
    "scenario_name": "denemeScenario",
    "description": "Create Scenario",
    "parent": {
        "id": 247459,
        "type": "SELENIUM",
        "scenario_name": "deneme13",
        "description": "deneme123",
        "enabled": true,
        "deleted": false,
        "testrail_enabled": false,
        "execute_mode": "AUTOMATED",
        "project_id": 3986,
        "childs": [],
        "parameterized": false,
        "has_parameterized_class": false,
        "test_scenario_java_parameters": [],
        "group": true
    },
    "max_execution_time": 60,
    "java_test_methods": "@onlySave"
}'
```
