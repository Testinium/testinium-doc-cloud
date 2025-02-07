# Get Users of a Customer

##

Retrieves the list of users associated with a specific customer. The user must have `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN`authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://account-devcluster.testinium.io/account/api/v1/customers/{id}/users/`
* **Method**: `GET`
* **Authentication**: Required (Bearer Token)
* **Headers**:
  * `Authorization: Bearer <your_access_token>`
  * `Content-Type: application/json`

***

### Path Parameters

| Parameter | Type | Required | Description                    |
| --------- | ---- | -------- | ------------------------------ |
| id        | Long | Yes      | The unique ID of the customer. |

***

### Request Parameters

No request body is required for this endpoint. The `id` parameter is provided via the URL path.

***

### Response

A list of user objects related to the specified customer.

#### Example Response

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

#### Response Fields

| Field       | Type    | Description                                  |
| ----------- | ------- | -------------------------------------------- |
| entityId    | Long    | Unique identifier for the user.              |
| username    | String  | The username of the user.                    |
| email       | String  | The email address of the user.               |
| companyName | String  | The name of the company the user belongs to. |
| enabled     | Boolean | Indicates if the user account is active.     |
| customer    | Long    | The associated customer ID.                  |
| createdDate | Long    | Timestamp of when the user was created.      |
| authorities | Array   | List of roles assigned to the user.          |

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
bashKopyalaDüzenlecurl --location 'https://account-devcluster.testinium.io/account/api/v1/customers/3393/users/' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json'
```
