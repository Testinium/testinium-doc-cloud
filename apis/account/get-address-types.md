# Get Address Types

The endpoint retrieves the list of address types. The user must have the appropriate authorization to access this endpoint.

***

### Endpoint Information

* **URL**: `https://account.testinium.com/account/api/v1/enums/address_types`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Response

The response contains a list of address types, each represented by a `key` and a `value`.

```json
[
    {
        "key": "H",
        "value": "Home"
    },
    {
        "key": "W",
        "value": "Work"
    },
    {
        "key": "O",
        "value": "Other"
    }
]
```

### Response Fields

| Field   | Type     | Description                                    |
| ------- | -------- | ---------------------------------------------- |
| `key`   | `String` | The unique code representing the address type. |
| `value` | `String` | The name/description of the address type.      |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `UNAUTHORIZED`          | Missing or invalid authentication token.         |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request GET 'https://account-devcluster.testinium.io/account/api/v1/enums/address_types' \
--header 'Authorization: Bearer <your_access_token>'\
--header 'current-company-id: <your_company_id>' \
```
