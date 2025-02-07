# Get Live Testing Parallel Limit

This endpoint retrieves the live testing parallel limit for a user's company. The user must have either the `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN` role to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/subscriptions/live-testing-parallel`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Response

On The response body is the integer value of the live testing parallel limit.

```json
200
```

***

### Error Handling

In case of an error, the following status code and messages may be returned:

| HTTP Code | Error Message           | Description                                                           |
| --------- | ----------------------- | --------------------------------------------------------------------- |
| `200`     | `LIVE_TESTING_LIMIT`    | Successfully retrieved live testing parallel limit.                   |
| `403`     | `FORBIDDEN`             | User lacks the required roles (`ROLE_ADMIN` or `ROLE_COMPANY_ADMIN`). |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred while retrieving the data.               |

***

### Example Request

```bash
curl --location --request GET 'https://testinium.io/Testinium.RestApi/api/subscriptions/live-testing-parallel' \
--header 'Authorization: Bearer <your_access_token>'\
--header 'current-company-id: <your_company_id>' \
```
