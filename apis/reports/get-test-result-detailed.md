# Get Test Result Detailed

Fetches detailed test results along with test command results, paginated based on the given parameters.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/results/{resultId}/detailed/filter`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`

### Path Parameters

| Parameter  | Type      | Description                                                           |
| ---------- | --------- | --------------------------------------------------------------------- |
| `resultId` | `Long`    | The unique ID of the test result to fetch detailed information.       |
| `page`     | `Integer` | The page number for paginated results.                                |
| `size`     | `Integer` | The number of results per page.                                       |
| `isDesc`   | `Boolean` | Whether the results should be ordered in descending order (optional). |

***

### Response

```json
{
  "id": 3249220,
  "level": "ERROR",
  "runtime": 31474,
  "environment": {
    "id": 308,
    "name": "Chrome",
    "operating_system": "MAC",
    "browser_type": "CHROME",
    "environment_type": "chrome",
    "environment_version": "LATEST",
    "enabled": false,
    "operating_system_clean_name": "Mac",
    "mobile": false
  },
  "session_id": "8cf0106d-cba3-40bd-a4ec-2bac4b8f68cd",
  "message": "",
  "screenshots_enabled": false,
  "screen_shot_type": "ONLY_FAILURE",
  "video_enabled": false,
  "performance_data_enabled": false,
  "video_format": "FLV",
  "node_log_path": "https://testinium-dev-cloud-k8s.s3.amazonaws.com/5251/2023/03/21/8cf0106d-cba3-40bd-a4ec-2bac4b8f68cd/node.log",
  "executor_log_path": "https://testinium-dev-cloud-k8s.s3.amazonaws.com/5251/2023/03/21/8cf0106d-cba3-40bd-a4ec-2bac4b8f68cd/testResult.log",
  "screen_resolution": "1024x768",
  "user_id": 5245,
  "company_id": 5251,
  "test_result_commands": [],
  "test_result_commands_paginated_result": {
    "current_page": 1,
    "total_count": 0,
    "page_count": 0,
    "next_page": "",
    "previous_page": "",
    "item_list": [],
    "rest_api_url": "https://devcluster.testinium.io/Testinium.RestApi"
  },
  "user_info": {
    "id": 5245,
    "name": "Mehmet",
    "surname": "Akşahin",
    "username": "mehmetaksahin",
    "email": "mehmet.aksahin@testinium.com",
    "enabled": true,
    "account_non_expired": true,
    "account_non_locked": true,
    "credential_non_expired": true,
    "language": "ENGLISH",
    "time_zone": "Europe/Istanbul",
    "company": "mehmetaksahin",
    "company_id": 5251,
    "current_company": "mehmetaksahin",
    "current_company_id": 5251,
    "roles": [
      "ROLE_NEW_COMPANY_ADMIN",
      "ROLE_NEW_USER",
      "ROLE_REPORT",
      "ROLE_INTEGRATION",
      "ROLE_CHANGE_USER",
      "ROLE_RUN_TEST",
      "ROLE_ADMIN",
      "ROLE_COMPANY_ADMIN",
      "ROLE_USER"
    ],
    "access_token": "1bd246e48f2f7871f8191442f567b41b"
  },
  "start_date": "2023-03-21T05:35:10Z",
  "end_date": "2023-03-21T05:35:42Z",
  "fetched_file_list": []
}
```

### Response Fields

| Field                                   | Type      | Description                                                          |
| --------------------------------------- | --------- | -------------------------------------------------------------------- |
| `id`                                    | `Integer` | Unique ID of the test result.                                        |
| `level`                                 | `String`  | The level of the test result (e.g., `ERROR`).                        |
| `runtime`                               | `Integer` | The runtime of the test in milliseconds.                             |
| `environment`                           | `Object`  | Details about the environment used during the test.                  |
| `session_id`                            | `String`  | The session ID for the test result.                                  |
| `message`                               | `String`  | Any message related to the test result.                              |
| `screenshots_enabled`                   | `Boolean` | Whether screenshots are enabled for the test result.                 |
| `screen_shot_type`                      | `String`  | The type of screenshot capture (e.g., `ONLY_FAILURE`).               |
| `video_enabled`                         | `Boolean` | Whether video recording is enabled for the test result.              |
| `node_log_path`                         | `String`  | The URL path to the node log for the test.                           |
| `executor_log_path`                     | `String`  | The URL path to the executor log for the test.                       |
| `screen_resolution`                     | `String`  | The screen resolution used during the test.                          |
| `user_info`                             | `Object`  | Information about the user who ran the test.                         |
| `start_date`                            | `String`  | The start date of the test result.                                   |
| `end_date`                              | `String`  | The end date of the test result.                                     |
| `test_result_commands`                  | `Array`   | A list of commands associated with the test result.                  |
| `test_result_commands_paginated_result` | `Object`  | A paginated result of test commands associated with the test result. |

***

#### Error Codes

| HTTP Status Code | Error Code       | Message                                                               |
| ---------------- | ---------------- | --------------------------------------------------------------------- |
| 400              | `BAD_REQUEST`    | Invalid request parameters.                                           |
| 401              | `UNAUTHORIZED`   | The user is not authorized to access this resource.                   |
| 403              | `FORBIDDEN`      | The user does not have sufficient permissions to access the resource. |
| 404              | `NOT_FOUND`      | The specified test result was not found.                              |
| 500              | `INTERNAL_ERROR` | An internal server error occurred while processing the request.       |

***

#### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/results/{resultId}/detailed/filter?page=1&size=10" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
