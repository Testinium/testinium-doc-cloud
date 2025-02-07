# Get Live Testing Parallel Limit

##

This endpoint retrieves the live testing parallel limit for a user's company. The user must have either the `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN` role to access this endpoint.

***

### Endpoint Information

* **URL**: `https://devcluster.testinium.io/Testinium.RestApi/api/subscriptions/live-testing-parallel`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Authorization**: Required roles: `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN`

***

### Request Parameters

No request body is required for this endpoint. The request will use the authenticated user's context to determine the current company.

***

### Response

On success, the response will contain the live testing parallel limit:

```json
jsonKopyalaDüzenle200 OK
```

The response body is the integer value of the live testing parallel limit (e.g., `5`).

#### Response Example

```json
jsonKopyalaDüzenle{
  "liveTestingParallelLimit": 5
}
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
bashKopyalaDüzenlecurl --location 'https://devcluster.testinium.io/Testinium.RestApi/api/subscriptions/live-testing-parallel' \
--request GET \
--header 'Authorization: Bearer <your_access_token>'
```
