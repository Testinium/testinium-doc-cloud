# Force Run Test Plan

This endpoint triggers the execution of a specific test plan. The user must have the `PLAN_RUN` authority to access this endpoint. It allows the user to run a test plan either normally or with a forced run, depending on the value of the `forceRun` parameter.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/{planId}/run/{forceRun}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter  | Type      | Required | Description                                                                   |
| ---------- | --------- | -------- | ----------------------------------------------------------------------------- |
| `planId`   | `Long`    | Yes      | The unique ID of the test plan to be executed.                                |
| `forceRun` | `Boolean` | Yes      | Determines whether the test plan should be forced to run (`true` or `false`). |

***

### Request Parameters

| Parameter     | Type     | Required | Description                                                                         |
| ------------- | -------- | -------- | ----------------------------------------------------------------------------------- |
| `callbackUrl` | `String` | No       | The URL to send the callback upon completion.                                       |
| `isGroupRun`  | `String` | No       | A flag to indicate whether the test is a group run. It should be `true` or `false`. |

***

### Response

The response indicates the result of the test plan execution request. If successful, it returns the execution ID, the test plan ID, and any unavailable environments.

```json
{
    "execution_id": 276086,
    "unavailable_env_list": [],
    "test_plan_id": 3362,
    "successful": true,
    "already_running": false
}
```

#### Response Fields

| Field                  | Type      | Description                                                                       |
| ---------------------- | --------- | --------------------------------------------------------------------------------- |
| `execution_id`         | `Long`    | The unique ID of the test execution triggered by the test plan.                   |
| `unavailable_env_list` | `Array`   | A list of unavailable environments, if any, that prevented the test from running. |
| `test_plan_id`         | `Long`    | The unique ID of the test plan being executed.                                    |
| `successful`           | `Boolean` | Indicates whether the test plan execution was successful.                         |
| `already_running`      | `Boolean` | Indicates whether the test plan was already running at the time of the request.   |

***

### Error Codes

| HTTP Code | Error Message           | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `401`     | `ACCESS_DENIED`         | The user lacks the `PLAN_RUN` authority.                   |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.             |
| `404`     | `TEST_PLAN_NOT_FOUND`   | The specified test plan was not found.                     |
| `409`     | `ALREADY_RUNNING`       | The test plan is already running.                          |
| `500`     | `SYSTEM_INTERNAL_ERROR` | An unexpected error occurred while processing the request. |

***

### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://testinium.io/Testinium.RestApi/api/plans/{planId}/run/{forceRun}' \  
--header 'Authorization: Bearer <your_access_token>' \ 
--data-urlencode 'callbackUrl=<callback_url>' \  
--data-urlencode 'isGroupRun=false'  
```
