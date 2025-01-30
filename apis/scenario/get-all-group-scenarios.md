# Get All Group Scenarios

This endpoint is used to **retrieve all group scenarios** for a specific project in the system.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/groupScenarios`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter   | Type     | Required | Description                                            |
| ----------- | -------- | -------- | ------------------------------------------------------ |
| `projectId` | `String` | Yes      | The ID of the project to retrieve group scenarios for. |

***

### Response

The response will contain a list of **group scenarios** and their associated child scenarios.

```json
[
    {
        "id": 247459,
        "type": "SELENIUM",
        "scenario_name": "deneme13",
        "description": "deneme123",
        "enabled": true,
        "deleted": false,
        "testrail_enabled": false,
        "execute_mode": "AUTOMATED",
        "project_id": 3986,
        "childs": [
            {
                "id": 247460,
                "type": "SELENIUM",
                "scenario_name": "denemeScenario",
                "description": "",
                "enabled": true,
                "deleted": false,
                "testrail_enabled": false,
                "execute_mode": "AUTOMATED",
                "source_file": "Works.spec",
                "max_execution_time": 60,
                "project_id": 3986,
                "parameterized": false,
                "has_parameterized_class": false,
                "java_test_class": "Works",
                "java_test_methods": "@saveAndSendWithNotConfirm",
                "test_scenario_java_parameters": [],
                "group": false
            },
            {
                "id": 247461,
                "type": "SELENIUM",
                "scenario_name": "subScenario",
                "description": "Add Sub Scenario",
                "enabled": true,
                "deleted": false,
                "testrail_enabled": false,
                "execute_mode": "AUTOMATED",
                "source_file": "Settings.spec",
                "project_id": 3986,
                "parameterized": false,
                "has_parameterized_class": false,
                "java_test_class": "Settings",
                "java_test_methods": "@changeLanguage",
                "test_scenario_java_parameters": [],
                "group": false
            }
        ],
        "parameterized": false,
        "has_parameterized_class": false,
        "test_scenario_java_parameters": [],
        "group": true
    }
]
```

### Response Fields

| Field                           | Type      | Description                                               |
| ------------------------------- | --------- | --------------------------------------------------------- |
| `id`                            | `Integer` | The unique identifier of the group scenario.              |
| `type`                          | `String`  | The type of scenario (e.g., "SELENIUM").                  |
| `scenario_name`                 | `String`  | The name of the scenario.                                 |
| `description`                   | `String`  | A description of the scenario.                            |
| `enabled`                       | `Boolean` | Whether the scenario is enabled or not.                   |
| `deleted`                       | `Boolean` | Whether the scenario is deleted or not.                   |
| `testrail_enabled`              | `Boolean` | Whether the scenario is enabled for TestRail integration. |
| `execute_mode`                  | `String`  | The execution mode (e.g., "AUTOMATED").                   |
| `project_id`                    | `Integer` | The project ID to which the scenario belongs.             |
| `childs`                        | `Array`   | A list of child scenarios (if any).                       |
| `parameterized`                 | `Boolean` | Whether the scenario is parameterized.                    |
| `has_parameterized_class`       | `Boolean` | Whether the scenario has parameterized classes.           |
| `test_scenario_java_parameters` | `Array`   | A list of Java test parameters (if any).                  |
| `group`                         | `Boolean` | Whether the scenario is a group scenario.                 |

***

### Error Codes

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `404`     | `PROJECT_NOT_FOUND`     | The specified `projectId` was not found.                  |
| `401`     | `UNAUTHORIZED_USER`     | The user is unauthorized or the token is missing/invalid. |
| `500`     | `INTERNAL_SERVER_ERROR` | A general server error occurred.                          |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/projects/{projectId}/groupScenarios' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json'
```
