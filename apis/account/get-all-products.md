# Get All Products

This endpoint retrieves all products. The user must have `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN` to access this endpoint.

***

### Endpoint Information

* **URL**: `https://account.testinium.com/account/api/v1/products/`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Response

The response contains a list of products, with each product including links to related actions.

```json
[
    {
        "entityId": 1,
        "name": "Testinium",
        "description": "Testinium Web App",
        "serviceCode": "T01",
        "serviceCodeDefinition": "Testinium Yazilim",
        "createdDate": 1506412759000,
        "updatedDate": null,
        "links": [
            {
                "rel": "self",
                "href": "https://account-devcluster.testinium.io/account/api/v1/products/1"
            },
            {
                "rel": "delete",
                "href": "https://account-devcluster.testinium.io/account/api/v1/products/1"
            }
        ]
    }
]
```

### Response Fields

| Field                   | Type     | Description                                                              |
| ----------------------- | -------- | ------------------------------------------------------------------------ |
| `entityId`              | `Long`   | The unique ID of the product.                                            |
| `name`                  | `String` | The name of the product.                                                 |
| `description`           | `String` | A description of the product.                                            |
| `serviceCode`           | `String` | A code identifying the service associated with the product.              |
| `serviceCodeDefinition` | `String` | A description of the service code.                                       |
| `createdDate`           | `Long`   | The timestamp when the product was created.                              |
| `updatedDate`           | `Long`   | The timestamp when the product was last updated (nullable).              |
| `links`                 | `Array`  | An array of links related to the product, such as self and delete links. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `403`     | `ACCESS_DENIED`         | User lacks `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN` authority. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.           |

***

### Example Request

```bash
curl --location 'https://account.testinium.com/account/api/v1/products/' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
