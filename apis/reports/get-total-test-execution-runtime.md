# Get Total Test Execution Runtime

This endpoint retrieves the total execution runtime of test results for a specified company, project, or test plan within a given date range.

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.Reporter/api/test-results/total-runtime`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                                      |
| ----------- | ------ | -------- | ------------------------------------------------ |
| `companyId` | `Long` | Yes      | The unique ID of the company.                    |
| `projectId` | `Long` | No       | The unique ID of the project (optional).         |
| `planId`    | `Long` | No       | The unique ID of the test plan (optional).       |
| `startDate` | `Date` | Yes      | Start date for filtering (format: `YYYY-MM-DD`). |
| `endDate`   | `Date` | Yes      | End date for filtering (format: `YYYY-MM-DD`).   |

***

### Response

The response contains the total test execution runtime in milliseconds.

```json
139533
```

***

### Response Fields

| Field        | Type   | Description                                       |
| ------------ | ------ | ------------------------------------------------- |
| **Response** | `Long` | Total runtime of test executions in milliseconds. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                           |
| --------- | ----------------------- | ----------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.        |
| `403`     | `ACCESS_DENIED`         | User lacks `TEST_RESULT_VIEW` authority.              |
| `404`     | `NO_RESULTS_FOUND`      | No test executions were found for the given criteria. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.      |

***

### Example Request

```bash
curl --location --request GET 'https://testinium.io/Testinium.Reporter/api/test-results/total-runtime?companyId=1234&startDate=2024-01-01&endDate=2024-01-31' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
