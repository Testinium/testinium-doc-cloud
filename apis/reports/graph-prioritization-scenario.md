# Graph Prioritization Scenario

This endpoint retrieves data for the graph prioritization of test scenarios, including execution data and failure information for a given project.

***

#### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/reports/graphPrioritizationScenario/{projectId}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                   |
| ----------- | ------ | -------- | ----------------------------- |
| `projectId` | `Long` | Yes      | The unique ID of the project. |

***

### Request Parameters

| Parameter         | Type         | Required | Description                                                            |
| ----------------- | ------------ | -------- | ---------------------------------------------------------------------- |
| `isAllExecutions` | `Boolean`    | No       | Flag to indicate whether to include all executions (default: `false`). |
| `testPlans`       | `List<Long>` | No       | A list of test plan IDs to filter by.                                  |
| `size`            | `Integer`    | No       | The size limit for the results (optional).                             |
| `ignoredCount`    | `Integer`    | No       | The number of ignored results (default: `0`).                          |

***

### Response

The response contains a list of test scenarios with their execution details.

```json
[
  {
    "total_failure": 20,
    "total_run_time": 37869,
    "scenario_name": "Ber Gratis",
    "scenario_id": 9993,
    "project_name": "Ber Gratis Test",
    "project_id": 408,
    "make_red": false,
    "faults_divide_time": 0.0317
  }
]
```

### **Response Fields**

| Field                | Type      | Description                                                                       |
| -------------------- | --------- | --------------------------------------------------------------------------------- |
| `total_failure`      | `Integer` | The total number of failures for the test scenario.                               |
| `total_run_time`     | `Integer` | The total run time for the test scenario, in milliseconds.                        |
| `scenario_name`      | `String`  | The name of the test scenario.                                                    |
| `scenario_id`        | `Long`    | The unique ID of the test scenario.                                               |
| `project_name`       | `String`  | The name of the project associated with the test scenario.                        |
| `project_id`         | `Long`    | The unique ID of the project.                                                     |
| `make_red`           | `Boolean` | Flag indicating whether to make the test scenario red in the graph visualization. |
| `faults_divide_time` | `Double`  | The ratio of fault divide time for the test scenario.                             |

***

### Error Codes

| HTTP Code | Error Message           | Description                                                           |
| --------- | ----------------------- | --------------------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                        |
| `401`     | `UNAUTHORIZED`          | The request lacks proper authentication.                              |
| `403`     | `ACCESS_DENIED`         | User lacks the necessary permissions to access the resource.          |
| `404`     | `PROJECT_NOT_FOUND`     | The project specified by the `projectId` was not found.               |
| `404`     | `PLAN_NOT_FOUND`        | One or more test plans from the `testPlans` parameter were not found. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                      |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/reports/graphPrioritizationScenario/{projectId}' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--data 'testPlans=1447,1448,1450,1485,1486,1487,1489,1490,1491,1492&isAllExecutions=true&size=0&ignoredCount=0'
```

4o mini
