# Get Maximum Execution Times

Retrieves the list of maximum execution time options available in the system. These options can be used for configuring test execution limits.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/enums/maxExecutionTimes`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Response Body

{% code overflow="wrap" fullWidth="false" %}
```json
[
    {
        "max_execution_minute": 15,
        "max_execution_name": "15 Minutes"
    },
    {
        "max_execution_minute": 30,
        "max_execution_name": "30 Minutes"
    },
    {
        "max_execution_minute": 60,
        "max_execution_name": "1 Hour"
    },
    {
        "max_execution_minute": 120,
        "max_execution_name": "2 Hours (Default)"
    },
    {
        "max_execution_minute": 240,
        "max_execution_name": "4 Hours"
    },
    {
        "max_execution_minute": 360,
        "max_execution_name": "6 Hours"
    },
    {
        "max_execution_minute": 480,
        "max_execution_name": "8 Hours"
    },
    {
        "max_execution_minute": 720,
        "max_execution_name": "12 Hours"
    }
]

```
{% endcode %}

### Response Parameters

| Field                  | Type      | Description                                    |
| ---------------------- | --------- | ---------------------------------------------- |
| `max_execution_minute` | `Integer` | The maximum execution time in minutes.         |
| `max_execution_name`   | `String`  | The name of the maximum execution time option. |

### Error Codes

| HTTP Code | Error Message           | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.             |
| `500`     | `SYSTEM_INTERNAL_ERROR` | An unexpected error occurred while processing the request. |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/enums/maxExecutionTimes" \
--header 'Authorization: Bearer <your_access_token>'
```
