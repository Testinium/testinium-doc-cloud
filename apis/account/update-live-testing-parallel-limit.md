# Update Live Testing Parallel Limit

This endpoint updates the live testing parallel limit for a user's company. The user must have either the `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN` role to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/subscriptions/live-testing-parallel`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Request Body

The request body should contain an integer value for the new live testing parallel limit.

```json
195
```

***

### Response

The response will indicate whether the update was successful or not.

#### Success

```json
"Live testing parallel limit successfully updated"
```

#### Error

If the requested parallel limit exceeds the available limit, the response will return:

```json
"You don't have enough parallel limit"
```

***

### Error Codes

In case of an error, the following status code and messages may be returned:

| HTTP Code | Error Message           | Description                                                                                                 |
| --------- | ----------------------- | ----------------------------------------------------------------------------------------------------------- |
| `403`     | `FORBIDDEN`             | User lacks the required roles (`ROLE_ADMIN` or `ROLE_COMPANY_ADMIN`) or doesn't have enough parallel limit. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred while updating the live testing parallel limit.                                |

***

### Example Request

```bash
curl --location --request PUT 'https://devcluster.testinium.io/Testinium.RestApi/api/subscriptions/live-testing-parallel' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--header 'current-company-id: <your_company_id>'\
--data '195'
```
