# Quick Run Test Plan

This endpoint triggers a "fast run" for a specific test plan, allowing the execution of selected scenarios in specific environments. The user must have the `PLAN_RUN` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/{planId}/fastRun`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter | Type   | Required | Description                                 |
| --------- | ------ | -------- | ------------------------------------------- |
| `planId`  | `Long` | Yes      | The unique ID of the test plan to fast run. |

***

### Request Body

The request body contains a list of scenarios and their associated environment IDs to be executed.

```json
[
    {
        "scenario_id": 9988,
        "environment_ids": [666]
    }
]

```

### Request Fields

| Field             | Type   | Description                                                    |
| ----------------- | ------ | -------------------------------------------------------------- |
| `scenario_id`     | `Long` | The ID of the scenario to execute.                             |
| `environment_ids` | `List` | A list of environment IDs where the scenario will be executed. |

***

### Response

The response returns a boolean value indicating whether the fast run request was successfully triggered.

```json
true
```

### Response Fields

| Field  | Type      | Description                                 |
| ------ | --------- | ------------------------------------------- |
| `true` | `Boolean` | Indicates that the fast run was successful. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `401`     | `ACCESS_DENIED`         | The user lacks the `PLAN_RUN` authority.                   |
| `400`     | `INVALID_REQUEST`       | The request body was malformed or contained errors.        |
| `404`     | `TEST_PLAN_NOT_FOUND`   | The specified test plan was not found.                     |
| `500`     | `SYSTEM_INTERNAL_ERROR` | An unexpected error occurred while processing the request. |

***

### Example Request

```bash
bashKopyalaDüzenlecurl --location --request POST 'https://testinium.io/Testinium.RestApi/api/plans/{planId}/fastRun' \  
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \  
--data-raw '[  
    {  
        "scenario_id": 9988,  
        "environment_ids": [666]  
    }  
]'  
```
