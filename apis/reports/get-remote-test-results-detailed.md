# Get Remote Test Results Detailed

This endpoint retrieves remote test results with detailed information, including the environment, message, and runtime.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/results/remote/{page}/{size}`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)
* **Request Body**: JSON data with filter parameters

***

### Path Parameters

| Parameter | Type      | Required | Description                     |
| --------- | --------- | -------- | ------------------------------- |
| `page`    | `Integer` | Yes      | The page number for pagination. |
| `size`    | `Integer` | Yes      | The number of results per page. |

***

### Response

The response contains a list of remote test results.

```json
{
    "result": [
        {
            "id": 3249220,
            "level": "ERROR",
            "runtime": 31474,
            "environment": {
                "id": 308,
                "name": "Chrome",
                "operating_system": "MAC",
                "browser_type": "CHROME",
                "environment_version": "LATEST",
                "mobile": false
            },
            "message": "",
            "start_date": "2023-03-21T05:35:10Z",
            "username": "mehmetaksahin"
        },
        {
            "id": 3249219,
            "level": "ERROR",
            "runtime": 31578,
            "environment": {
                "id": 308,
                "name": "Chrome",
                "operating_system": "MAC",
                "browser_type": "CHROME",
                "environment_version": "LATEST",
                "mobile": false
            },
            "message": "",
            "start_date": "2023-03-21T05:32:13Z",
            "username": "mehmetaksahin"
        },
        {
            "id": 3249216,
            "level": "SUCCESS",
            "runtime": 95151,
            "environment": {
                "id": 308,
                "name": "Chrome",
                "operating_system": "MAC",
                "browser_type": "CHROME",
                "environment_version": "LATEST",
                "mobile": false
            },
            "message": "",
            "start_date": "2023-03-20T19:22:23Z",
            "username": "mehmetaksahin"
        },
        {
            "id": 3249215,
            "level": "ERROR",
            "runtime": 36425,
            "environment": {
                "id": 308,
                "name": "Chrome",
                "operating_system": "MAC",
                "browser_type": "CHROME",
                "environment_version": "LATEST",
                "mobile": false
            },
            "message": "",
            "start_date": "2023-03-20T14:35:40Z",
            "username": "mehmetaksahin"
        }
    ],
    "total_result_count": 450,
    "start": 0,
    "end": 0
}
```

***

### Response Fields

| Field                             | Type      | Description                                                  |
| --------------------------------- | --------- | ------------------------------------------------------------ |
| `result`                          | `Array`   | An array of test result objects.                             |
| `id`                              | `Long`    | The unique ID of the test result.                            |
| `level`                           | `String`  | The level of the result (e.g., `ERROR`, `SUCCESS`).          |
| `runtime`                         | `Integer` | The runtime of the test result in milliseconds.              |
| `environment`                     | `Object`  | Information about the environment in which the test was run. |
| `environment.id`                  | `Long`    | The ID of the environment.                                   |
| `environment.name`                | `String`  | The name of the environment (e.g., `Chrome`).                |
| `environment.operating_system`    | `String`  | The operating system of the environment.                     |
| `environment.browser_type`        | `String`  | The browser type (e.g., `CHROME`).                           |
| `environment.environment_version` | `String`  | The version of the environment.                              |
| `environment.mobile`              | `Boolean` | Whether the environment is mobile.                           |
| `message`                         | `String`  | Any additional message or error related to the test.         |
| `start_date`                      | `String`  | The start date of the test in ISO 8601 format.               |
| `username`                        | `String`  | The username of the person who initiated the test.           |
| `total_result_count`              | `Integer` | Total number of results available.                           |
| `start`                           | `Integer` | The start index of the current page of results.              |
| `end`                             | `Integer` | The end index of the current page of results.                |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `UNAUTHORIZED`          | User is not authorized to access the resource.   |
| `403`     | `FORBIDDEN`             | User lacks permission to access this resource.   |
| `400`     | `INVALID_REQUEST`       | Invalid request or malformed data.               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request POST 'https://testinium.io/Testinium.RestApi/api/results/remote/1/15' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' 
```
