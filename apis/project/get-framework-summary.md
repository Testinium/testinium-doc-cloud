# Get Framework Summary

This endpoint retrieves a summary of projects grouped by their test frameworks. Each group contains a list of active projects associated with the authenticated user's company.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/framework-summary`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Request Body

No request body is required for this endpoint.

***

### Response

The response is a list of frameworks, each containing its `title`, `value`, and associated projects.

```json
[
    {
        "title": "SELENIUM",
        "value": "SELENIUM",
        "children": [
            {
                "id": 123,
                "name": "project1"
            },
            {
                "id": 134,
                "name": "project2"
            }
        ]
    },
    {
        "title": "APPIUM",
        "value": "APPIUM",
        "children": [
            {
                "id": 145,
                "name": "project3"
            }
        ]
    },
    {
        "title": "SERVICE",
        "value": "SERVICE",
        "children": [
            {
                "id": 156,
                "name": "project4"
            },
            {
                "id": 167,
                "name": "project5"
            }
        ]
    }
]
```

#### Response Fields

| Field      | Type     | Description                                     |
| ---------- | -------- | ----------------------------------------------- |
| `title`    | `String` | The display name of the test framework.         |
| `value`    | `String` | The identifier of the test framework.           |
| `children` | `Array`  | List of projects associated with the framework. |
| `id`       | `Long`   | The unique ID of the project.                   |
| `name`     | `String` | The name of the project.                        |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `403`     | `ACCESS_DENIED`         | User lacks `PROJECT_VIEW` authority.             |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/projects/framework-summary" \
--header 'Authorization: Bearer <your_access_token>'
```
