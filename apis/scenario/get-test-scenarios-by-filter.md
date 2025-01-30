# Get Test Scenarios By Filter

This endpoint retrieves a paginated list of test scenarios based on optional filtering criteria such as project ID, test plan ID, and scenario text. The user must have the `PLAN_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scenarios/filter`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Request Parameters

| Parameter      | Type      | Required | Default | Description                                                |
| -------------- | --------- | -------- | ------- | ---------------------------------------------------------- |
| `page`         | `Integer` | Yes      | -       | The page number to retrieve (pagination).                  |
| `size`         | `Integer` | Yes      | -       | Number of items per page.                                  |
| `projectId`    | `Long`    | No       | `null`  | Filters scenarios by the specified project ID.             |
| `planId`       | `Long`    | No       | `null`  | Filters scenarios by the specified test plan ID.           |
| `scenarioText` | `String`  | No       | `null`  | Filters scenarios based on scenario name or description.   |
| `email`        | `String`  | No       | `null`  | Filters scenarios for the specified user email (optional). |

***

### Response

The response is a **paginated** list of test scenarios.

```json
{
  "current_page": 1,
  "total_count": 1712,
  "page_count": 86,
  "next_page": "https://testinium.io/Testinium.RestApi/api/scenarios/filter/pages/2",
  "previous_page": "",
  "item_list": [
    {
      "id": 55883,
      "type": "SELENIUM",
      "scenario_name": "Urgent Call Insertion And Deletion",
      "description": "",
      "enabled": true,
      "deleted": false,
      "testrail_enabled": false,
      "execute_mode": "AUTOMATED",
      "source_file": "HealthCardTests.spec",
      "project_id": 5431,
      "plans": [18996],
      "childs": [],
      "parameterized": false,
      "has_parameterized_class": false,
      "java_test_class": "HealthCardTests",
      "java_test_methods": "@UrgentCallInsertion",
      "test_scenario_java_parameters": [],
      "group": false
    },
    {
      "id": 55884,
      "type": "SELENIUM",
      "scenario_name": "Operation Insertion And Deletion",
      "description": "",
      "enabled": true,
      "deleted": false,
      "testrail_enabled": false,
      "execute_mode": "AUTOMATED",
      "source_file": "HealthCardTests.spec",
      "project_id": 5431,
      "plans": [18996],
      "childs": [],
      "parameterized": false,
      "has_parameterized_class": false,
      "java_test_class": "HealthCardTests",
      "java_test_methods": "@OperationInsertion",
      "test_scenario_java_parameters": [],
      "group": false
    }
  ],
  "rest_api_url": "https://testinium.io/Testinium.RestApi"
}
```

***

### Response Fields

| Field                           | Type      | Description                                             |
| ------------------------------- | --------- | ------------------------------------------------------- |
| `current_page`                  | `Integer` | The current page number.                                |
| `total_count`                   | `Integer` | Total number of scenarios matching the filter criteria. |
| `page_count`                    | `Integer` | Total number of pages available.                        |
| `next_page`                     | `String`  | URL for the next page (if available).                   |
| `previous_page`                 | `String`  | URL for the previous page (if available).               |
| `item_list`                     | `Array`   | List of test scenarios on the current page.             |
| `id`                            | `Long`    | Unique ID of the test scenario.                         |
| `type`                          | `String`  | The type of scenario (`SELENIUM`, `APPIUM`, etc.).      |
| `scenario_name`                 | `String`  | Name of the test scenario.                              |
| `description`                   | `String`  | Description of the scenario (if any).                   |
| `enabled`                       | `Boolean` | Whether the scenario is enabled.                        |
| `deleted`                       | `Boolean` | Whether the scenario has been deleted.                  |
| `testrail_enabled`              | `Boolean` | Whether TestRail integration is enabled.                |
| `execute_mode`                  | `String`  | Execution mode (`AUTOMATED`, `MANUAL`).                 |
| `source_file`                   | `String`  | The source file where the scenario is defined.          |
| `project_id`                    | `Long`    | The ID of the associated project.                       |
| `plans`                         | `Array`   | List of test plan IDs that include this scenario.       |
| `childs`                        | `Array`   | Child scenarios (if applicable).                        |
| `parameterized`                 | `Boolean` | Whether the scenario uses parameterization.             |
| `has_parameterized_class`       | `Boolean` | Whether it has a parameterized Java class.              |
| `java_test_class`               | `String`  | The Java test class used in execution.                  |
| `java_test_methods`             | `String`  | The Java test method(s) executed in this scenario.      |
| `test_scenario_java_parameters` | `Array`   | Java parameters used in the test scenario.              |
| `group`                         | `Boolean` | Whether this scenario belongs to a group.               |

***

### Error Codes

| HTTP Code | Error Message           | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `403`     | `ACCESS_DENIED`         | User lacks `PLAN_VIEW` authority.                          |
| `401`     | `UNAUTHORIZED_USER`     | User email does not match the `email` parameter.           |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained invalid parameters. |
| `500`     | `SYSTEM_INTERNAL_ERROR` | An unexpected error occurred on the server side.           |

***

### Example Request

```bash
curl --location --request GET 'https://testinium.io/Testinium.RestApi/api/scenarios/filter?page=1&size=20email=kullanici@email.com' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
