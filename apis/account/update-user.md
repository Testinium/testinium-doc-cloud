# Update User

This endpoint allows you to update the user information for a specific user within a customer account. The request requires the `userId` and `customerId` to be provided. The user must have appropriate permissions to update user details.

***

### Endpoint Information

* **URL**: `https://account.testinium.com/account/api/v1/customers/{id}/users/{userId}`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type   | Required | Description                          |
| --------- | ------ | -------- | ------------------------------------ |
| `id`      | `Long` | Yes      | The unique ID of the customer.       |
| `userId`  | `Long` | Yes      | The unique ID of the user to update. |

***

### Request

The request body should contain the updated information for the user. You can update fields such as `name`, `surname`, `username`, `email`, and other user-related properties.

```json
{
  "userType": null,
  "verificationToken": null,
  "resetPasswordToken": null,
  "entityId": 6860,
  "name": "Denemee",
  "surname": "User",
  "username": "selinvural",
  "email": "selin.vural@testinium.com",
  "password": null,
  "newPassword": null,
  "accessToken": "827058a5cee9c47278b68028b2d0959c",
  "companyName": null,
  "enabled": false,
  "accountNonExpired": true,
  "accountNonLocked": true,
  "credentialNonExpired": true,
  "createdDate": 1738809864000,
  "customer": 3393,
  "lastPasswordResetDate": null,
  "authorities": [
    {
      "entityId": 2,
      "name": "ROLE_USER",
      "cleanName": "ROLE USER",
      "checked": true,
      "disabled": true
    }
  ],
  "vcsPassword": null
}
```

***

### Response

The response returns the updated information of the user.

```json
{
  "userType": null,
  "verificationToken": null,
  "resetPasswordToken": null,
  "entityId": 6860,
  "name": "Denemee",
  "surname": "User",
  "username": "selinvural",
  "email": "selin.vural@testinium.com",
  "password": null,
  "newPassword": null,
  "accessToken": "827058a5cee9c47278b68028b2d0959c",
  "companyName": null,
  "enabled": false,
  "accountNonExpired": true,
  "accountNonLocked": true,
  "credentialNonExpired": true,
  "createdDate": 1738809864000,
  "customer": 3393,
  "lastPasswordResetDate": null,
  "authorities": [
    {
      "entityId": 3,
      "name": "ROLE_USER",
      "cleanName": null
    }
  ],
  "vcsPassword": null
}
```

***

### Error Codes

| HTTP Code | Error Message           | Description                                           |
| --------- | ----------------------- | ----------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.        |
| `403`     | `ACCESS_DENIED`         | The user lacks permission to update this information. |
| `404`     | `USER_NOT_FOUND`        | No user was found for the specified `userId`.         |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.      |

***

### Example Request

```bash
curl --location --request PUT 'https://account.testinium.com/account/api/v1/customers/{customerId}/users/{userId}' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--data '{"name":"Denemee","surname":"User","username":"selinvural","email":"selin.vural@testinium.com","enabled":false,"accountNonExpired":true,"accountNonLocked":true,"credentialNonExpired":true,"authorities":[{"entityId":2,"name":"ROLE_USER","cleanName":"ROLE USER"}]}'
```

4o mini
