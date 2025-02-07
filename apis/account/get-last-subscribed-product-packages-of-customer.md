# Get Last Subscribed Product Packages of Customer

###

This endpoint retrieves the most recent product packages that a customer has subscribed to.

***

#### Endpoint Information

* **URL**: `https://account-devcluster.testinium.io/account/api/v1/customers/packages/last/{id}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

#### Path Parameters

| Parameter | Type   | Required | Description                    |
| --------- | ------ | -------- | ------------------------------ |
| `id`      | `Long` | Yes      | The unique ID of the customer. |

***

#### Request Parameters

This endpoint does not require a request body. The parameter `id` is provided as part of the URL path.

***

#### Response

The response contains the details of the customer's last subscribed product packages.

**Example Response**

```json
jsonKopyalaDüzenle[
  {
    "entityId": 6810,
    "subscription": {
      "entityId": 6789,
      "customer": null,
      "addonSubscriptionLogs": null,
      "pluginSubscriptionLogs": null,
      "productLogs": [
        {
          "entityId": 6810,
          "subscription": null,
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
                  "enabled": true,
                  "value": "16"
                },
                "value": "16",
                "createdDate": 1729770684000
              },
              {
                "entityId": 11025,
                "property": {
                  "entityId": 10,
                  "name": "maxTestMinutes",
                  "description": "Maximum Test Minutes",
                  "valueType": "I",
                  "enabled": true,
                  "value": "10000"
                },
                "value": "10000",
                "createdDate": 1729770684000
              },
              {
                "entityId": 11026,
                "property": {
                  "entityId": 15,
                  "name": "maxUser",
                  "description": "Maximum Users",
                  "valueType": "I",
                  "enabled": true,
                  "value": "10"
                },
                "value": "10",
                "createdDate": 1729770684000
              }
            ],
            "packagePriceDefinitions": [
              {
                "entityId": 3130,
                "currency": "USD",
                "price": 0.00,
                "period": "A"
              }
            ],
            "product": {
              "entityId": 1,
              "name": "Testinium",
              "description": "Testinium Web App"
            },
            "name": "mehmetaksahinn",
            "enabled": true,
            "personal": true,
            "customerId": 3393,
            "packageType": "E"
          },
          "createdDate": 1729770684000,
          "quantity": 1,
          "startDate": 1729770684000,
          "endDate": 1761306684000
        }
      ],
      "isTrial": false,
      "enabled": null,
      "createdDate": 1729770684000
    },
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
            "enabled": true,
            "value": "16"
          },
          "value": "16",
          "createdDate": 1729770684000
        },
        {
          "entityId": 11025,
          "property": {
            "entityId": 10,
            "name": "maxTestMinutes",
            "description": "Maximum Test Minutes",
            "valueType": "I",
            "enabled": true,
            "value": "10000"
          },
          "value": "10000",
          "createdDate": 1729770684000
        },
        {
          "entityId": 11026,
          "property": {
            "entityId": 15,
            "name": "maxUser",
            "description": "Maximum Users",
            "valueType": "I",
            "enabled": true,
            "value": "10"
          },
          "value": "10",
          "createdDate": 1729770684000
        }
      ],
      "packagePriceDefinitions": [
        {
          "entityId": 3130,
          "currency": "USD",
          "price": 0.00,
          "period": "A"
        }
      ],
      "product": {
        "entityId": 1,
        "name": "Testinium",
        "description": "Testinium Web App"
      },
      "name": "mehmetaksahinn",
      "enabled": true,
      "personal": true,
      "customerId": 3393,
      "packageType": "E"
    },
    "createdDate": 1729770684000,
    "quantity": 1,
    "period": "A",
    "productId": 1,
    "startDate": 1729770684000,
    "endDate": 1761306684000
  }
]
```

#### Response Fields

| Field            | Type      | Description                                           |
| ---------------- | --------- | ----------------------------------------------------- |
| `entityId`       | `Long`    | Unique identifier for the product package.            |
| `subscription`   | `Object`  | The subscription details associated with the package. |
| `productPackage` | `Object`  | The product package details.                          |
| `createdDate`    | `Long`    | Timestamp indicating when the package was created.    |
| `quantity`       | `Integer` | The quantity of the product package.                  |
| `startDate`      | `Long`    | The start date of the subscription.                   |
| `endDate`        | `Long`    | The end date of the subscription.                     |

***

#### Error Codes

| HTTP Code | Error Message           | Description                                                 |
| --------- | ----------------------- | ----------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.              |
| `404`     | `PACKAGE_NOT_FOUND`     | No product package found for the specified customer ID.     |
| `403`     | `ACCESS_DENIED`         | User lacks the required permission to access this resource. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.            |

***

#### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://account-devcluster.testinium.io/account/api/v1/customers/packages/last/{id}' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
