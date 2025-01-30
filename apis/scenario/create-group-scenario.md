# Create Group Scenario

This endpoint is used to **create a new group scenario in a specified project**.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/groupScenarios`
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
    "scenario_name": "testScenario",
    "description": "Create group scenario"
}
```

### Request Fields

| Field           | Type      | Required | Description                                               |
| --------------- | --------- | -------- | --------------------------------------------------------- |
| `project_id`    | `Integer` | Yes      | The ID of the project where the scenario will be created. |
| `scenario_name` | `String`  | Yes      | The name of the group scenario.                           |
| `description`   | `String`  | No       | A description of the scenario.                            |

***

### Response

A successful request returns the **details of the created group scenario**.

```json
{
    "id": 247459,
    "type": "SELENIUM",
    "scenario_name": "testScenario",
    "description": "test description",
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
}
```

### Response Fields

| Field                           | Type      | Description                                             |
| ------------------------------- | --------- | ------------------------------------------------------- |
| `id`                            | `Integer` | The unique ID of the created scenario.                  |
| `type`                          | `String`  | The type of the scenario (`SELENIUM`, `APITest`, etc.). |
| `scenario_name`                 | `String`  | The name of the scenario.                               |
| `description`                   | `String`  | The description of the scenario.                        |
| `enabled`                       | `Boolean` | Indicates whether the scenario is active.               |
| `deleted`                       | `Boolean` | Indicates whether the scenario is deleted.              |
| `testrail_enabled`              | `Boolean` | Indicates if TestRail integration is enabled.           |
| `execute_mode`                  | `String`  | The execution mode (`AUTOMATED`, `MANUAL`).             |
| `project_id`                    | `Integer` | The ID of the project associated with the scenario.     |
| `childs`                        | `Array`   | List of child scenarios (empty if none).                |
| `parameterized`                 | `Boolean` | Indicates if the scenario is parameterized.             |
| `has_parameterized_class`       | `Boolean` | Indicates if it contains a parameterized class.         |
| `test_scenario_java_parameters` | `Array`   | List of Java test parameters.                           |
| `group`                         | `Boolean` | Indicates if this is a group scenario.                  |

***

### Error Codes

| HTTP Code | Error Message                 | Description                                               |
| --------- | ----------------------------- | --------------------------------------------------------- |
| `404`     | `PROJECT_NOT_FOUND`           | The specified `projectId` was not found.                  |
| `401`     | `UNAUTHORIZED_USER`           | The user is unauthorized or the token is missing/invalid. |
| `400`     | `SCENARIO_NAME_ALREADY_EXIST` | A scenario with the same name already exists.             |
| `500`     | `INTERNAL_SERVER_ERROR`       | A general server error occurred.                          |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/projects/{projectId}/groupScenarios' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "project_id": 3986,
    "scenario_name": "testScenario",
    "description": "Create group scenario"
}'
```
