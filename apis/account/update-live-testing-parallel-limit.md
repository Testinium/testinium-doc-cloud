# Update Live Testing Parallel Limit

##

This endpoint updates the live testing parallel limit for a user's company. The user must have either the `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN` role to access this endpoint.

***

### Endpoint Information

* **URL**: `https://devcluster.testinium.io/Testinium.RestApi/api/subscriptions/live-testing-parallel`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)
* **Authorization**: Required roles: `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN`

***

### Request Body

The request body should contain an integer value for the new live testing parallel limit.

#### Example Request Body

```json
jsonKopyalaDüzenle195
```

***

### Response

The response will indicate whether the update was successful or not.

#### Success

```json
jsonKopyalaDüzenle"Live testing parallel limit successfully updated"
```

#### Error

If the requested parallel limit exceeds the available limit, the response will return:

```json
jsonKopyalaDüzenle"You don't have enough parallel limit"
```

#### HTTP Status Codes

| HTTP Code | Status Description                                                    |
| --------- | --------------------------------------------------------------------- |
| `200`     | Successfully updated live testing parallel limit.                     |
| `403`     | User does not have sufficient parallel limit or lacks required roles. |

***

### Error Handling

In case of an error, the following status code and messages may be returned:

| HTTP Code | Error Message           | Description                                                                                                 |
| --------- | ----------------------- | ----------------------------------------------------------------------------------------------------------- |
| `403`     | `FORBIDDEN`             | User lacks the required roles (`ROLE_ADMIN` or `ROLE_COMPANY_ADMIN`) or doesn't have enough parallel limit. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred while updating the live testing parallel limit.                                |

***

### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://devcluster.testinium.io/Testinium.RestApi/api/subscriptions/live-testing-parallel' \
--request PUT \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data '195'
```
