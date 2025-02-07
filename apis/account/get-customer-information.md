# Get Customer Information

##

The endpoint retrieves customer details based on the given customer ID. The user must have the appropriate access rights to view the requested customer information.

***

### Endpoint Information

* **URL**: `https://account-devcluster.testinium.io/account/api/v1/customers/{id}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`Authorization`, `current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type   | Required | Description                    |
| --------- | ------ | -------- | ------------------------------ |
| `id`      | `Long` | Yes      | The unique ID of the customer. |

***

### Request Parameters

No request body is required for this endpoint. The parameter `id` is provided via the URL path.

***

### Response

The response contains details about the customer.

```json
{
    "entityId": 3393,
    "newCustomer": null,
    "newAccountVerificationToken": null,
    "billingName": null,
    "billingLastName": null,
    "billingAddress": null,
    "subscriptions": [
        {
            "entityId": 6781,
            "customer": null,
            "addonSubscriptionLogs": null,
            "pluginSubscriptionLogs": null,
            "productLogs": [
                {
                    "entityId": 6807,
                    "subscription": null,
                    "productPackage": {
                        "entityId": 1,
                        "propertyValues": [
                            {
                                "entityId": 1,
                                "property": {
                                    "entityId": 14,
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "hosted",
                                    "description": "Hosted",
                                    "order": 12,
                                    "valueType": "S",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "Cloud",
                                "createdDate": 1506412759000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "Cloud"
                            },
                            {
                                "entityId": 2,
                                "property": {
                                    "entityId": 4,
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "maxRealDevices",
                                    "description": "Maximum Real Devices",
                                    "order": 3,
                                    "valueType": "I",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "5",
                                "createdDate": 1506412759000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "5 Real Devices"
                            },
                            {
                                "entityId": 3,
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
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "1",
                                "createdDate": 1506412759000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "1 User"
                            },
                            {
                                "entityId": 4,
                                "property": {
                                    "entityId": 11,
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "supportChannels",
                                    "description": "Support Channels",
                                    "order": 9,
                                    "valueType": "S",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "Working day hours support",
                                "createdDate": 1506412759000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "Working day hours support"
                            },
                            {
                                "entityId": 5,
                                "property": {
                                    "entityId": 16,
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "remoteManualTest",
                                    "description": "Remote Manual Tests",
                                    "order": 14,
                                    "valueType": "S",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "Remote Manual Test",
                                "createdDate": 1506412759000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "Remote Manual Test"
                            },
                            {
                                "entityId": 6,
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
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "2",
                                "createdDate": 1506412759000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "2 Parallel Testing"
                            },
                            {
                                "entityId": 7,
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
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "200",
                                "createdDate": 1506412759000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "200 min"
                            }
                        ],
                        "properties": null,
                        "packagePriceDefinitions": [
                            {
                                "entityId": 2,
                                "productPackage": null,
                                "period": "A",
                                "currency": "USD",
                                "price": 0.00,
                                "createdDate": 1506412759000,
                                "updatedDate": null,
                                "startDate": null,
                                "endDate": null,
                                "customizedDate": false
                            },
                            {
                                "entityId": 1,
                                "productPackage": null,
                                "period": "M",
                                "currency": "USD",
                                "price": 0.00,
                                "createdDate": 1506412759000,
                                "updatedDate": null,
                                "startDate": null,
                                "endDate": null,
                                "customizedDate": false
                            }
                        ],
                        "subscriptions": null,
                        "product": {
                            "entityId": 1,
                            "name": "Testinium",
                            "description": "Testinium Web App",
                            "serviceCode": "T01",
                            "serviceCodeDefinition": "Testinium Yazilim",
                            "createdDate": 1506412759000,
                            "updatedDate": null
                        },
                        "name": "TRIAL",
                        "description": "Test Automation Solution for Mobile, Web & Web Service",
                        "enabled": true,
                        "personal": false,
                        "addons": null,
                        "plugins": null,
                        "packageType": "F",
                        "customerId": null,
                        "createdDate": 1506412759000,
                        "updatedDate": null
                    },
                    "createdDate": 1638427516000,
                    "quantity": 1,
                    "unitType": "P",
                    "period": "F",
                    "productId": 1,
                    "startDate": 1638427531000,
                    "endDate": 1701499538000,
                    "customizedDate": false
                }
            ],
            "packages": null,
            "billings": null,
            "isTrial": true,
            "enabled": true,
            "createdDate": 1354349796000
        },
        {
            "entityId": 6788,
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
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "16",
                                "createdDate": 1729546754000,
                                "updatedDate": 1729546851000,
                                "propertyValueDisplayName": "16"
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
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "10",
                                "createdDate": 1729546754000,
                                "updatedDate": 1729546851000,
                                "propertyValueDisplayName": "10"
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
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "20000",
                                "createdDate": 1729546754000,
                                "updatedDate": 1729546851000,
                                "propertyValueDisplayName": "20000"
                            }
                        ],
                        "properties": null,
                        "packagePriceDefinitions": [
                            {
                                "entityId": 3129,
                                "productPackage": null,
                                "period": "A",
                                "currency": "USD",
                                "price": 0.00,
                                "createdDate": 1729546754000,
                                "updatedDate": 1729546851000,
                                "startDate": null,
                                "endDate": null,
                                "customizedDate": false
                            }
                        ],
                        "subscriptions": null,
                        "product": {
                            "entityId": 1,
                            "name": "Testinium",
                            "description": "Testinium Web App",
                            "serviceCode": "T01",
                            "serviceCodeDefinition": "Testinium Yazilim",
                            "createdDate": 1506412759000,
                            "updatedDate": null
                        },
                        "name": "mehmetaksahin",
                        "description": "mehmetaksahin",
                        "enabled": true,
                        "personal": true,
                        "addons": null,
                        "plugins": null,
                        "packageType": "E",
                        "customerId": 3393,
                        "createdDate": 1729546754000,
                        "updatedDate": 1729546851000
                    },
                    "createdDate": 1729546851000,
                    "quantity": 1,
                    "unitType": "P",
                    "period": "A",
                    "productId": 1,
                    "startDate": 1729546851000,
                    "endDate": 1761082851000,
                    "customizedDate": false
                }
            ],
            "packages": null,
            "billings": null,
            "isTrial": false,
            "enabled": null,
            "createdDate": 1729546851000
        },
        {
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
                                    "packages": null,
                                    "propertyValues": null,
                                    "name": "maxParallel",
                                    "description": "Maximum Parallel Test Execution",
                                    "order": 2,
                                    "valueType": "I",
                                    "enabled": true,
                                    "isPrivate": false,
                                    "customerId": null,
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "16",
                                "createdDate": 1729770684000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "16"
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
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "10000",
                                "createdDate": 1729770684000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "10000"
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
                                    "createdDate": 1506412759000,
                                    "updatedDate": null
                                },
                                "productPackage": null,
                                "value": "10",
                                "createdDate": 1729770684000,
                                "updatedDate": null,
                                "propertyValueDisplayName": "10"
                            }
                        ],
                        "properties": null,
                        "packagePriceDefinitions": [
                            {
                                "entityId": 3130,
                                "productPackage": null,
                                "period": "A",
                                "currency": "USD",
                                "price": 0.00,
                                "createdDate": 1729770684000,
                                "updatedDate": null,
                                "startDate": null,
                                "endDate": null,
                                "customizedDate": false
                            }
                        ],
                        "subscriptions": null,
                        "product": {
                            "entityId": 1,
                            "name": "Testinium",
                            "description": "Testinium Web App",
                            "serviceCode": "T01",
                            "serviceCodeDefinition": "Testinium Yazilim",
                            "createdDate": 1506412759000,
                            "updatedDate": null
                        },
                        "name": "mehmetaksahinn",
                        "description": "mehmetaksahin",
                        "enabled": true,
                        "personal": true,
                        "addons": null,
                        "plugins": null,
                        "packageType": "E",
                        "customerId": 3393,
                        "createdDate": 1729770684000,
                        "updatedDate": null
                    },
                    "createdDate": 1729770684000,
                    "quantity": 1,
                    "unitType": "P",
                    "period": "A",
                    "productId": 1,
                    "startDate": 1729770684000,
                    "endDate": 1761306684000,
                    "customizedDate": false
                }
            ],
            "packages": null,
            "billings": null,
            "isTrial": false,
            "enabled": null,
            "createdDate": 1729770684000
        }
    ],
    "emails": [],
    "phoneNumbers": [],
    "addresses": [],
    "users": null,
    "name": "Mehmett",
    "surname": "Akşahinn",
    "email": "mehmet.aksahin@testinium.com",
    "companyName": "Mestiniumm",
    "companySize": "3",
    "country": "Turkey",
    "phoneNumber": "11111111111",
    "createdDate": 1534252798000,
    "updatedDate": 1729770685000,
    "testiniumIntegration": true,
    "loadiumIntegration": null,
    "applicationType": null,
    "applicationUrl": null,
    "testFileType": null,
    "_links": {
        "self": {
            "href": "https://account-devcluster.testinium.io/account/api/v1/customers/3393"
        },
        "delete": {
            "href": "https://account-devcluster.testinium.io/account/api/v1/customers/3393"
        }
    }
}
```

***

### Error Codes

| HTTP Code | Error Message           | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `403`     | `ACCESS_DENIED`         | The user does not have permission to access this customer. |
| `404`     | `CUSTOMER_NOT_FOUND`    | No customer was found with the specified ID.               |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred.                              |

***

### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://account-devcluster.testinium.io/account/api/v1/customers/3393' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
