# Get Phone Types

##

The endpoint retrieves the list of phone types. The user must have the appropriate authorization to access this endpoint.

***

### Endpoint Information

* **URL**: `https://account-devcluster.testinium.io/account/api/v1/enums/phone_types`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Request Parameters

No request body is required for this endpoint. The request is made with a simple GET request to retrieve the phone types.

***

### Response

The response contains a list of phone types, each represented by a `key` and a `value`.

```json
jsonKopyalaDüzenle[
    {
        "key": "H",
        "value": "Home"
    },
    {
        "key": "W",
        "value": "Work"
    },
    {
        "key": "G",
        "value": "GSM"
    }
]
```

#### Response Fields

| Field   | Type     | Description                                  |
| ------- | -------- | -------------------------------------------- |
| `key`   | `String` | The unique code representing the phone type. |
| `value` | `String` | The name/description of the phone type.      |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `UNAUTHORIZED`          | Missing or invalid authentication token.         |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://account-devcluster.testinium.io/account/api/v1/enums/phone_types' \
--request GET \
--header 'Authorization: Bearer <your_access_token>'
```
