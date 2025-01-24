# Get Files of a Test Plan

This endpoint retrieves a list of files associated with a specific test plan. The user must have the `PLAN_UPDATE` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/{planId}/planFile`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type   | Required | Description                     |
| --------- | ------ | -------- | ------------------------------- |
| `planId`  | `Long` | Yes      | The unique ID of the test plan. |

***

### Response

The response contains a list of files associated with the specified test plan. If the company does not have the `FILE_UPLOAD` plugin enabled, the response will return an empty list.

```
[]
```

#### Response Fields

| Field | Type   | Description                |
| ----- | ------ | -------------------------- |
| `id`  | `Long` | The unique ID of the file. |

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `404`     | `PLAN_NOT_FOUND`        | The specified test plan ID was not found.        |
| `403`     | `ACCESS_DENIED`         | User lacks `PLAN_UPDATE` authority.              |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/plans/{planId}/planFile' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
