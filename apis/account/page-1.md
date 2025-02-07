# Get User Details by Customer ID and User ID

This API endpoint retrieves the details of a specific user associated with a given customer ID. The requesting user must have appropriate access permissions.

***

### Endpoint Information

* **URL**:\
  `https://account.testinium.com/account/api/v1/customers/{customerId}/users/{userId}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter    | Type   | Required | Description                                   |
| ------------ | ------ | -------- | --------------------------------------------- |
| `customerId` | `Long` | Yes      | The ID of the customer.                       |
| `userId`     | `Long` | Yes      | The ID of the user within the given customer. |

***

### Response

The response contains detailed information about the user.

```json
{
    "userType": null,
    "verificationToken": null,
    "resetPasswordToken": null,
    "entityId": 6835,
    "name": "",
    "surname": "",
    "username": "mehmetaksahin",
    "email": "mehmet.aksahin@testinium.com",
    "password": null,
    "newPassword": null,
    "accessToken": "xxx",
    "companyName": null,
    "enabled": true,
    "accountNonExpired": true,
    "accountNonLocked": true,
    "credentialNonExpired": true,
    "createdDate": 1567664649000,
    "customer": 3393,
    "lastPasswordResetDate": null,
    "authorities": [
        {
            "entityId": null,
            "name": "ROLE_COMPANY_ADMIN",
            "cleanName": null
        },
        {
            "entityId": null,
            "name": "ROLE_INTEGRATION",
            "cleanName": null
        },
        {
            "entityId": null,
            "name": "ROLE_REPORT",
            "cleanName": null
        },
        {
            "entityId": null,
            "name": "ROLE_RUN_TEST",
            "cleanName": null
        },
        {
            "entityId": null,
            "name": "ROLE_NEW_USER",
            "cleanName": null
        },
        {
            "entityId": null,
            "name": "ROLE_ADMIN",
            "cleanName": null
        },
        {
            "entityId": null,
            "name": "ROLE_CHANGE_USER",
            "cleanName": null
        },
        {
            "entityId": null,
            "name": "ROLE_NEW_COMPANY_ADMIN",
            "cleanName": null
        },
        {
            "entityId": null,
            "name": "ROLE_USER",
            "cleanName": null
        }
    ],
    "vcsPassword": "xxx"
}
```

***

### Response Fields

| Field                  | Type      | Description                                      |
| ---------------------- | --------- | ------------------------------------------------ |
| `entityId`             | `Long`    | The unique ID of the user.                       |
| `username`             | `String`  | The username of the user.                        |
| `email`                | `String`  | The user's email address.                        |
| `enabled`              | `Boolean` | Whether the user account is active.              |
| `accountNonExpired`    | `Boolean` | Whether the account is expired.                  |
| `accountNonLocked`     | `Boolean` | Whether the account is locked.                   |
| `credentialNonExpired` | `Boolean` | Whether credentials are expired.                 |
| `createdDate`          | `Long`    | The timestamp when the user was created.         |
| `customer`             | `Long`    | The ID of the customer associated with the user. |
| `authorities`          | `Array`   | The list of roles assigned to the user.          |

***

### Error Codes

| HTTP Code | Error Message           | Description                                       |
| --------- | ----------------------- | ------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.    |
| `403`     | `UNAUTHORIZED_ACCESS`   | The user does not have permission to access data. |
| `404`     | `USER_NOT_FOUND`        | No user was found for the specified `userId`.     |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.  |

***

### Example Request

```bash
curl --location 'https://account.testinium.com/account/api/v1/customers/{customerId}/users/{userId}' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
