# Get Browsers

Retrieves a list of supported browsers with their respective codes.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/enums/browsers`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter | Type     | Description                                               |
| --------- | -------- | --------------------------------------------------------- |
| `user`    | `Object` | The user making the request, identified by their company. |

***

### Response

```json
[
    {
        "code": "firefox",
        "name": "Firefox"
    },
    {
        "code": "chrome",
        "name": "Chrome"
    },
    {
        "code": "internet explorer",
        "name": "Internet Explorer"
    },
    {
        "code": "safari",
        "name": "Safari"
    },
    {
        "code": "operablink",
        "name": "Opera"
    },
    {
        "code": "MicrosoftEdge",
        "name": "Microsoft Edge"
    }
]
```

***

### Response Fields

| Field  | Type     | Description                            |
| ------ | -------- | -------------------------------------- |
| `code` | `string` | The unique identifier for the browser. |
| `name` | `string` | The name of the browser.               |

***

### Error Codes

| HTTP Status | Code             | Message                                                         |
| ----------- | ---------------- | --------------------------------------------------------------- |
| 400         | `BAD_REQUEST`    | Invalid request parameters.                                     |
| 401         | `UNAUTHORIZED`   | The user is not authorized to access this resource.             |
| 500         | `INTERNAL_ERROR` | An internal server error occurred while processing the request. |

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/enums/browsers" \
--header 'Authorization: Bearer <your_access_token>'
```
