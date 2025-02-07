# Get Package Price by Package, Period, and Currency

This endpoint retrieves the price definition for a specific product package based on the package ID, period, and currency. The user must ensure that the package exists and provide the correct parameters.

***

### Endpoint Information

* **URL**: `https://account.testinium.com/account/public/pricing/package_id/{package_id}/period/{period}/currency/{currency}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter    | Type     | Required | Description                                    |
| ------------ | -------- | -------- | ---------------------------------------------- |
| `package_id` | `Long`   | Yes      | The unique ID of the product package.          |
| `period`     | `String` | Yes      | The billing period (e.g., `A`, `B`, etc.).     |
| `currency`   | `String` | Yes      | The currency used for the price (e.g., `USD`). |

***

### Response

The response contains the price definition and associated details for the requested product package, period, and currency.

```json
{
  "entityId": 3130,
  "productPackage": {
    "entityId": 3129,
    "propertyValues": [
      {
        "entityId": 11024,
        "property": {
          "entityId": 3,
          "name": "maxParallel",
          "description": "Maximum Parallel Test Execution",
          "valueType": "I",
          "enabled": true
        },
        "value": "16"
      },
      {
        "entityId": 11025,
        "property": {
          "entityId": 10,
          "name": "maxTestMinutes",
          "description": "Maximum Test Minutes",
          "valueType": "I",
          "enabled": true
        },
        "value": "10000"
      },
      {
        "entityId": 11026,
        "property": {
          "entityId": 15,
          "name": "maxUser",
          "description": "Maximum Users",
          "valueType": "I",
          "enabled": true
        },
        "value": "10"
      }
    ],
    "packagePriceDefinitions": [
      {
        "entityId": 3130,
        "period": "A",
        "currency": "USD",
        "price": 0.00,
        "customizedDate": false
      }
    ],
    "name": "mehmetaksahinn",
    "description": "mehmetaksahin",
    "enabled": true,
    "customerId": 3393
  },
  "period": "A",
  "currency": "USD",
  "price": 0.00,
  "_links": {
    "self": {
      "href": "https://account-devcluster.testinium.io/account/api/v1/package_price_definitions/3130"
    },
    "delete": {
      "href": "https://account-devcluster.testinium.io/account/api/v1/package_price_definitions/3130"
    },
    "package": {
      "href": "https://account-devcluster.testinium.io/account/api/v1/packages/3129"
    }
  }
}
```

### Response Fields

| Field            | Type     | Description                                                        |
| ---------------- | -------- | ------------------------------------------------------------------ |
| `entityId`       | `Long`   | The unique ID of the package price definition.                     |
| `productPackage` | `Object` | Details of the product package (including properties and pricing). |
| `period`         | `String` | The billing period for the price.                                  |
| `currency`       | `String` | The currency used for the price.                                   |
| `price`          | `Double` | The price for the specified package, period, and currency.         |
| `customerId`     | `Long`   | The customer ID associated with the package.                       |
| `_links`         | `Object` | Links to related resources such as self and package.               |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `404`     | `PACKAGE_NOT_FOUND`     | No package was found for the specified ID.       |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location 'https://account.testinium.com/account/public/pricing/package_id/{package_id}/period/{period}/currency/{currency}' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
