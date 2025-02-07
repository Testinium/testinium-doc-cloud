# Delete Scheduled Report

This endpoint deletes a scheduled report. The user must have the necessary permissions to delete scheduled reports.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled/{id}`
* **Method**: DELETE
* **Authentication**: Required (Bearer Token)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type | Required | Description                            |
| --------- | ---- | -------- | -------------------------------------- |
| id        | Long | Yes      | The unique ID of the scheduled report. |

***

### Response

If the report is successfully deleted, the response returns `true`.

```json
true
```

### Response Fields

| Field  | Type    | Description                                    |
| ------ | ------- | ---------------------------------------------- |
| result | Boolean | `true` if the report was successfully deleted. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| 400       | INVALID\_REQUEST        | The request was malformed or contained errors.   |
| 404       | REPORT\_NOT\_FOUND      | No scheduled report found for the given ID.      |
| 403       | ACCESS\_DENIED          | User lacks the necessary authority.              |
| 500       | INTERNAL\_SERVER\_ERROR | An unexpected error occurred on the server side. |

***

### Example Request&#x20;

```bash
curl --location --request DELETE 'https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled/132?companyId=5251' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
