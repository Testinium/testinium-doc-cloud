# Get Scenario By ID

This endpoint retrieves a test scenario by its **ID**. The user must have the `SCENARIO_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scenarios/{scenarioId}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameter

| Parameter    | Type   | Required | Description                      |
| ------------ | ------ | -------- | -------------------------------- |
| `scenarioId` | `Long` | Yes      | The **ID** of the test scenario. |

***

### Response

The response returns the details of the requested test scenario.

```json
{
    "id": 104356,
    "type": "SELENIUM",
    "scenario_name": "getTestList",
    "enabled": true,
    "deleted": false,
    "testrail_enabled": false,
    "execute_mode": "AUTOMATED",
    "source_file": "com/example/exampleTest.java",
    "project_id": 3536,
    "plans": [
        15399
    ],
    "childs": [],
    "parameterized": false,
    "has_parameterized_class": false,
    "java_test_class": "com.example.exampleTest",
    "java_test_methods": "getTestList",
    "test_scenario_java_parameters": [],
    "group": false
}
```

***

### Response Fields

| Field                           | Type      | Description                                        |
| ------------------------------- | --------- | -------------------------------------------------- |
| `id`                            | `Long`    | Unique ID of the test scenario.                    |
| `type`                          | `String`  | The type of scenario (`SELENIUM`, `APPIUM`, etc.). |
| `scenario_name`                 | `String`  | Name of the test scenario.                         |
| `enabled`                       | `Boolean` | Whether the scenario is enabled.                   |
| `deleted`                       | `Boolean` | Whether the scenario has been deleted.             |
| `testrail_enabled`              | `Boolean` | Whether TestRail integration is enabled.           |
| `execute_mode`                  | `String`  | Execution mode (`AUTOMATED`, `MANUAL`).            |
| `source_file`                   | `String`  | The source file where the scenario is defined.     |
| `project_id`                    | `Long`    | The ID of the associated project.                  |
| `plans`                         | `Array`   | List of test plan IDs that include this scenario.  |
| `childs`                        | `Array`   | Child scenarios (if applicable).                   |
| `parameterized`                 | `Boolean` | Whether the scenario uses parameterization.        |
| `has_parameterized_class`       | `Boolean` | Whether it has a parameterized Java class.         |
| `java_test_class`               | `String`  | The Java test class used in execution.             |
| `java_test_methods`             | `String`  | The Java test method(s) executed in this scenario. |
| `test_scenario_java_parameters` | `Array`   | Java parameters used in the test scenario.         |
| `group`                         | `Boolean` | Whether this scenario belongs to a group.          |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `403`     | `ACCESS_DENIED`         | User lacks `SCENARIO_VIEW` authority.            |
| `404`     | `SCENARIO_NOT_FOUND`    | No scenario found with the given ID or name.     |
| `401`     | `UNAUTHORIZED_USER`     | Authentication token is missing or invalid.      |
| `500`     | `SYSTEM_INTERNAL_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request GET 'https://testinium.io/Testinium.RestApi/api/scenarios/{scenarioId}' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
