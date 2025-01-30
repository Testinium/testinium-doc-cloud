# Get Total Scenario Count by Filter

This endpoint retrieves the total number of scenarios that match the provided filters. The user must have the `SCENARIO_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scenarios/totalCountByfilter`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Request Parameters

| Parameter      | Type     | Required | Description                                       |
| -------------- | -------- | -------- | ------------------------------------------------- |
| `projectId`    | `Long`   | No       | The unique ID of the project to filter scenarios. |
| `planId`       | `Long`   | No       | The unique ID of the test plan to filter by.      |
| `scenarioText` | `String` | No       | A text snippet to filter scenarios by content.    |

***

### Response

The response returns the total count of scenarios that match the specified filters.

```json
713
```

### Response Fields

| Field        | Type   | Description                                         |
| ------------ | ------ | --------------------------------------------------- |
| `totalCount` | `Long` | The total number of scenarios matching the filters. |

***

### Error Codes

| HTTP Code | Error Message              | Description                                                |
| --------- | -------------------------- | ---------------------------------------------------------- |
| `403`     | `ACCESS_DENIED`            | User lacks `SCENARIO_VIEW` authority.                      |
| `400`     | `INVALID_REQUEST`          | The request was malformed or contained invalid parameters. |
| `404`     | `USERS_COMPANY_NOT_EXISTS` | No company was found for the current user.                 |
| `500`     | `SYSTEM_INTERNAL_ERROR`    | An unexpected error occurred on the server side.           |

***

### Example Request

```bash
curl --location --request GET 'https://testinium.io/Testinium.RestApi/api/scenarios/totalCountByfilter?projectId=123&planId=456&scenarioText=example' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
