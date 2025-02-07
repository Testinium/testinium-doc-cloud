# 4Graph Prioritization

###

This endpoint retrieves data for the graph prioritization of test plans, including execution data and failure information for a given project.

***

#### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/zeroExecution`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

#### Path Parameters

| Parameter   | Type   | Required | Description                   |
| ----------- | ------ | -------- | ----------------------------- |
| `projectId` | `Long` | Yes      | The unique ID of the project. |

***

#### Request Parameters

| Parameter         | Type         | Required | Description                                                            |
| ----------------- | ------------ | -------- | ---------------------------------------------------------------------- |
| `isAllExecutions` | `Boolean`    | No       | Flag to indicate whether to include all executions (default: `false`). |
| `testPlans`       | `List<Long>` | No       | A list of test plan IDs to filter by.                                  |
| `size`            | `Integer`    | No       | The size limit for the results (optional).                             |
| `ignoredCount`    | `Integer`    | No       | The number of ignored results (default: `0`).                          |

***

#### Response

The response contains a list of test plans with their execution details.

```json
jsonKopyalaDüzenle[
  {
    "total_failure": 0,
    "total_run_time": 15278,
    "plan_name": "Mac1",
    "plan_id": 1447,
    "project_name": "Ber Gratis Test",
    "project_id": 408,
    "make_red": false,
    "faults_divide_time": 0.0
  },
  {
    "total_failure": 0,
    "total_run_time": 1568,
    "plan_name": "Android",
    "plan_id": 1448,
    "project_name": "Ber Gratis Test",
    "project_id": 408,
    "make_red": false,
    "faults_divide_time": 0.0
  },
  ...
]
```

**Response Fields**

| Field                | Type      | Description                                                                   |
| -------------------- | --------- | ----------------------------------------------------------------------------- |
| `total_failure`      | `Integer` | The total number of failures for the test plan.                               |
| `total_run_time`     | `Integer` | The total run time for the test plan, in milliseconds.                        |
| `plan_name`          | `String`  | The name of the test plan.                                                    |
| `plan_id`            | `Long`    | The unique ID of the test plan.                                               |
| `project_name`       | `String`  | The name of the project associated with the test plan.                        |
| `project_id`         | `Long`    | The unique ID of the project.                                                 |
| `make_red`           | `Boolean` | Flag indicating whether to make the test plan red in the graph visualization. |
| `faults_divide_time` | `Double`  | The ratio of fault divide time for the test plan.                             |

***

#### Error Codes

| HTTP Code | Error Message           | Description                                                           |
| --------- | ----------------------- | --------------------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.                        |
| `401`     | `UNAUTHORIZED`          | The request lacks proper authentication.                              |
| `403`     | `ACCESS_DENIED`         | User lacks the necessary permissions to access the resource.          |
| `404`     | `PROJECT_NOT_FOUND`     | The project specified by the `projectId` was not found.               |
| `404`     | `PLAN_NOT_FOUND`        | One or more test plans from the `testPlans` parameter were not found. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.                      |

***

#### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://testinium.io/Testinium.RestApi/api/plans/zeroExecution' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--data 'testPlans=1447,1448,1450,1485,1486,1487,1489,1490,1491,1492&isAllExecutions=true&size=0&ignoredCount=0'
```

4o mini
