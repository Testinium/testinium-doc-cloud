# Get Users of a Customer

Retrieves the list of users associated with a specific customer. The user must have `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN`authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://account.testinium.com/account/api/v1/customers/{customerId}/users/`
* **Method**: `GET`
* **Authentication**: Required (Bearer Token)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type | Required | Description                    |
| --------- | ---- | -------- | ------------------------------ |
| id        | Long | Yes      | The unique ID of the customer. |

***

### Response

A list of user objects related to the specified customer.

```json
[
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
        "accessToken": "afbe7d859ad86b5149f75077c52035e3",
        "companyName": "Mestiniumm",
        "enabled": true,
        "accountNonExpired": true,
        "accountNonLocked": true,
        "credentialNonExpired": true,
        "createdDate": 1567664649000,
        "customer": 3393,
        "lastPasswordResetDate": null,
        "authorities": [
            {
                "entityId": 1,
                "name": "ROLE_ADMIN",
                "cleanName": null
            },
            {
                "entityId": 2,
                "name": "ROLE_COMPANY_ADMIN",
                "cleanName": null
            },
            {
                "entityId": 3,
                "name": "ROLE_USER",
                "cleanName": null
            }
        ],
        "vcsPassword": "EBgdEMJkfw0dTqmVeCm7hQ=="
    },
    {
        "userType": null,
        "verificationToken": null,
        "resetPasswordToken": null,
        "entityId": 6850,
        "name": "Sander Yazıcıoğluu",
        "surname": "SY",
        "username": "dscan",
        "email": "dscan@gmail.com",
        "password": null,
        "newPassword": null,
        "accessToken": "ef7aa1189f51ce4b08c761a97c54fcaa",
        "companyName": "Mestiniumm",
        "enabled": false,
        "accountNonExpired": true,
        "accountNonLocked": true,
        "credentialNonExpired": true,
        "createdDate": 1638348417000,
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
    },
    {
        "userType": null,
        "verificationToken": null,
        "resetPasswordToken": null,
        "entityId": 6851,
        "name": "Sander",
        "surname": "gfddfd",
        "username": "daasfafaanman",
        "email": "daasfafaanman@gmail.com",
        "password": null,
        "newPassword": null,
        "accessToken": "c3414cf20e3d453727d38999e4637ba7",
        "companyName": "Mestiniumm",
        "enabled": false,
        "accountNonExpired": true,
        "accountNonLocked": true,
        "credentialNonExpired": true,
        "createdDate": 1638348461000,
        "customer": 3393,
        "lastPasswordResetDate": null,
        "authorities": [
            {
                "entityId": 1,
                "name": "ROLE_ADMIN",
                "cleanName": null
            },
            {
                "entityId": 2,
                "name": "ROLE_COMPANY_ADMIN",
                "cleanName": null
            },
            {
                "entityId": 3,
                "name": "ROLE_USER",
                "cleanName": null
            }
        ],
        "vcsPassword": null
    },
    {
        "userType": null,
        "verificationToken": null,
        "resetPasswordToken": null,
        "entityId": 6855,
        "name": "selahattin",
        "surname": "unlu",
        "username": "selahattinunlu",
        "email": "selahattin.unlu@testinium.com",
        "password": null,
        "newPassword": null,
        "accessToken": "a082ac5ae152b3a7d1244275789e3230",
        "companyName": "Mestiniumm",
        "enabled": true,
        "accountNonExpired": true,
        "accountNonLocked": true,
        "credentialNonExpired": true,
        "createdDate": 1729545892000,
        "customer": 3393,
        "lastPasswordResetDate": null,
        "authorities": [
            {
                "entityId": 2,
                "name": "ROLE_COMPANY_ADMIN",
                "cleanName": null
            },
            {
                "entityId": 3,
                "name": "ROLE_USER",
                "cleanName": null
            }
        ],
        "vcsPassword": "1KpujXwbibnOcPGVD0AzDw=="
    },
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
        "companyName": "Mestiniumm",
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
]
```

***

### Error Codes

| HTTP Code | Error Message           | Description                                |
| --------- | ----------------------- | ------------------------------------------ |
| 400       | INVALID\_REQUEST        | The request is malformed.                  |
| 404       | CUSTOMER\_NOT\_FOUND    | The specified customer does not exist.     |
| 403       | ACCESS\_DENIED          | User does not have the required authority. |
| 500       | INTERNAL\_SERVER\_ERROR | Unexpected server error.                   |

***

### Example Request

```bash
curl --location 'https://account.testinium.com/account/api/v1/customers/{customerId}/users/' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json'\
--header 'current-company-id: <your_company_id>'
```
