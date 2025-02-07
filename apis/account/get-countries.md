# Get Countries

The endpoint retrieves a list of countries. The user must have the appropriate authorization to access this endpoint.

***

### Endpoint Information

* **URL**: `https://account.testinium.com/account/api/v1/enums/countries`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Response

The response contains a list of countries, each with the following fields:

```json
[
    {
        "entityId": 3,
        "provinces": null,
        "name": "Afghanistan",
        "code": "AF",
        "links": []
    },
    {
        "entityId": 247,
        "provinces": null,
        "name": "Zimbabwe",
        "code": "ZW",
        "links": []
    }
]
```

### Response Fields

| Field       | Type      | Description                                        |
| ----------- | --------- | -------------------------------------------------- |
| `entityId`  | `Integer` | The unique ID of the country.                      |
| `provinces` | `Object`  | A list of provinces in the country (if available). |
| `name`      | `String`  | The name of the country.                           |
| `code`      | `String`  | The ISO country code (e.g., "AF" for Afghanistan). |
| `links`     | `Array`   | A list of associated links (if any).               |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `401`     | `UNAUTHORIZED`          | Missing or invalid authentication token.         |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request GET 'https://account-devcluster.testinium.io/account/api/v1/enums/countries' \
--header 'Authorization: Bearer <your_access_token>'\
--header 'current-company-id: <your_company_id>' \
```
