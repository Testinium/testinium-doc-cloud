# Get Billings by Customer ID

##

This endpoint retrieves billing information for a specific customer by their `customerId`. The user must have sufficient permissions to access the customer's billing data.

***

### Endpoint Information

* **URL**: `https://account-devcluster.testinium.io/account/api/v1/billings/customer/{id}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)
* **Produces**: `HAL_JSON_VALUE`

***

### Path Parameters

| Parameter | Type   | Required | Description                    |
| --------- | ------ | -------- | ------------------------------ |
| `id`      | `Long` | Yes      | The unique ID of the customer. |

***

### Response

The response returns a list of billing details for the specified customer. Each billing object includes information about the subscription, product details, billing status, payment details, and more.

#### Example Response

```json
[
    {
        "entityId": 154,
        "subscription": {
            "entityId": null,
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
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "maxParallel",
                                    "description": "Maximum Parallel Test Execution",
                                    "order": 2,
                                    "valueType": "I",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1738897858076,
                                    "updatedDate": null,
                                    "links": []
                                },
                                "productPackage": null,
                                "value": "16",
                                "createdDate": 1738897858076,
                                "updatedDate": null,
                                "propertyValueDisplayName": "16",
                                "links": []
                            },
                            {
                                "entityId": 11025,
                                "property": {
                                    "entityId": 10,
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "maxTestMinutes",
                                    "description": "Maximum Test Minutes",
                                    "order": 8,
                                    "valueType": "I",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1738897858076,
                                    "updatedDate": null,
                                    "links": []
                                },
                                "productPackage": null,
                                "value": "10000",
                                "createdDate": 1738897858076,
                                "updatedDate": null,
                                "propertyValueDisplayName": "10000",
                                "links": []
                            },
                            {
                                "entityId": 11026,
                                "property": {
                                    "entityId": 15,
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "maxUser",
                                    "description": "Maximum Users",
                                    "order": 13,
                                    "valueType": "I",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1738897858076,
                                    "updatedDate": null,
                                    "links": []
                                },
                                "productPackage": null,
                                "value": "10",
                                "createdDate": 1738897858076,
                                "updatedDate": null,
                                "propertyValueDisplayName": "10",
                                "links": []
                            }
                        ],
                        "properties": null,
                        "packagePriceDefinitions": [],
                        "subscriptions": null,
                        "product": {
                            "entityId": 1,
                            "name": "Testinium",
                            "description": "Testinium Web App",
                            "serviceCode": "T01",
                            "serviceCodeDefinition": "Testinium Yazilim",
                            "createdDate": 1738897858076,
                            "updatedDate": null,
                            "links": []
                        },
                        "name": "mehmetaksahinn",
                        "description": "mehmetaksahin",
                        "enabled": true,
                        "personal": true,
                        "addons": null,
                        "plugins": null,
                        "packageType": "E",
                        "customerId": 3393,
                        "createdDate": 1738897858076,
                        "updatedDate": null,
                        "links": []
                    },
                    "createdDate": 1738897858076,
                    "quantity": 1,
                    "unitType": "P",
                    "period": "A",
                    "productId": 1,
                    "startDate": 1729770684000,
                    "endDate": 1761306684000,
                    "customizedDate": false,
                    "links": []
                }
            ],
            "packages": null,
            "billings": null,
            "isTrial": false,
            "enabled": null,
            "createdDate": 1738897858076,
            "links": [
                {
                    "rel": "self",
                    "href": "https://account-devcluster.testinium.io/account/api/v1/subscriptions/{id}"
                },
                {
                    "rel": "delete",
                    "href": "https://account-devcluster.testinium.io/account/api/v1/subscriptions/{id}"
                }
            ]
        },
        "billingItems": [],
        "payment": null,
        "companyName": "Mestiniumm",
        "product": "Testinium",
        "productPackage": "mehmetaksahinn",
        "subscriptionPeriod": "A",
        "startDate": 1729770684000,
        "endDate": 1761306684000,
        "isPaid": true,
        "createdDate": 1738897858076,
        "billingName": "Mehmett",
        "billingLastName": "Akşahinn",
        "billingCountry": "Turkey",
        "billingCity": null,
        "billingZipCode": null,
        "billingAddress": null,
        "taxRateDefinition": null,
        "paid": true,
        "links": [
            {
                "rel": "self",
                "href": "https://account-devcluster.testinium.io/account/api/v1/billings/154"
            },
            {
                "rel": "delete",
                "href": "https://account-devcluster.testinium.io/account/api/v1/billings/154"
            },
            {
                "rel": "subscriptions",
                "href": "https://account-devcluster.testinium.io/account/api/v1/subscriptions/{id}"
            }
        ]
    },
    {
        "entityId": 153,
        "subscription": {
            "entityId": null,
            "customer": null,
            "addonSubscriptionLogs": null,
            "pluginSubscriptionLogs": null,
            "productLogs": [
                {
                    "entityId": 6809,
                    "subscription": null,
                    "productPackage": {
                        "entityId": 3128,
                        "propertyValues": [
                            {
                                "entityId": 11021,
                                "property": {
                                    "entityId": 3,
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "maxParallel",
                                    "description": "Maximum Parallel Test Execution",
                                    "order": 2,
                                    "valueType": "I",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1738897858077,
                                    "updatedDate": null,
                                    "links": []
                                },
                                "productPackage": null,
                                "value": "16",
                                "createdDate": 1738897858077,
                                "updatedDate": null,
                                "propertyValueDisplayName": "16",
                                "links": []
                            },
                            {
                                "entityId": 11022,
                                "property": {
                                    "entityId": 15,
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "maxUser",
                                    "description": "Maximum Users",
                                    "order": 13,
                                    "valueType": "I",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1738897858077,
                                    "updatedDate": null,
                                    "links": []
                                },
                                "productPackage": null,
                                "value": "10",
                                "createdDate": 1738897858077,
                                "updatedDate": null,
                                "propertyValueDisplayName": "10",
                                "links": []
                            },
                            {
                                "entityId": 11023,
                                "property": {
                                    "entityId": 10,
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "maxTestMinutes",
                                    "description": "Maximum Test Minutes",
                                    "order": 8,
                                    "valueType": "I",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1738897858077,
                                    "updatedDate": null,
                                    "links": []
                                },
                                "productPackage": null,
                                "value": "20000",
                                "createdDate": 1738897858077,
                                "updatedDate": null,
                                "propertyValueDisplayName": "20000",
                                "links": []
                            }
                        ],
                        "properties": null,
                        "packagePriceDefinitions": [],
                        "subscriptions": null,
                        "product": {
                            "entityId": 1,
                            "name": "Testinium",
                            "description": "Testinium Web App",
                            "serviceCode": "T01",
                            "serviceCodeDefinition": "Testinium Yazilim",
                            "createdDate": 1738897858077,
                            "updatedDate": null,
                            "links": []
                        },
                        "name": "mehmetaksahin",
                        "description": "mehmetaksahin",
                        "enabled": true,
                        "personal": true,
                        "addons": null,
                        "plugins": null,
                        "packageType": "E",
                        "customerId": 3393,
                        "createdDate": 1738897858077,
                        "updatedDate": null,
                        "links": []
                    },
                    "createdDate": 1738897858077,
                    "quantity": 1,
                    "unitType": "P",
                    "period": "A",
                    "productId": 1,
                    "startDate": 1729546851000,
                    "endDate": 1761082851000,
                    "customizedDate": false,
                    "links": []
                }
            ],
            "packages": null,
            "billings": null,
            "isTrial": false,
            "enabled": null,
            "createdDate": 1738897858077,
            "links": [
                {
                    "rel": "self",
                    "href": "https://account-devcluster.testinium.io/account/api/v1/subscriptions/{id}"
                },
                {
                    "rel": "delete",
                    "href": "https://account-devcluster.testinium.io/account/api/v1/subscriptions/{id}"
                }
            ]
        },
        "billingItems": [],
        "payment": null,
        "companyName": "Mestiniumm",
        "product": "Testinium",
        "productPackage": "mehmetaksahin",
        "subscriptionPeriod": "A",
        "startDate": 1729546851000,
        "endDate": 1761082851000,
        "isPaid": true,
        "createdDate": 1738897858077,
        "billingName": "Mehmett",
        "billingLastName": "Akşahinn",
        "billingCountry": "Turkey",
        "billingCity": null,
        "billingZipCode": null,
        "billingAddress": null,
        "taxRateDefinition": null,
        "paid": true,
        "links": [
            {
                "rel": "self",
                "href": "https://account-devcluster.testinium.io/account/api/v1/billings/153"
            },
            {
                "rel": "delete",
                "href": "https://account-devcluster.testinium.io/account/api/v1/billings/153"
            },
            {
                "rel": "subscriptions",
                "href": "https://account-devcluster.testinium.io/account/api/v1/subscriptions/{id}"
            }
        ]
    }
]
```

***

### Error Codes

| HTTP Code | Error Message           | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.             |
| `403`     | `ACCESS_DENIED`         | The user does not have permission to access this resource. |
| `404`     | `NOT_FOUND`             | No billing information found for the specified customer.   |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.           |

***

### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://account-devcluster.testinium.io/account/api/v1/billings/customer/3393' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--request GET
```

4o mini
