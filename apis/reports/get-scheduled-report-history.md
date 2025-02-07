# Get Scheduled Report History

This endpoint retrieves the execution history of a specific scheduled report. The user must have the necessary permissions to access the report history.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled/history/{id}`
* **Method**: GET
* **Authentication**: Required (Bearer Token)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type | Required | Description                            |
| --------- | ---- | -------- | -------------------------------------- |
| id        | Long | Yes      | The unique ID of the scheduled report. |

***

### Response

The response contains the execution history of the scheduled report as a list of historical execution records.

```json
[
    {
        "id": 987,
        "scheduled_report_id": 132,
        "execution_time": "2025-02-05T14:30:00Z",
        "status": "SUCCESS",
        "generated_report_url": "https://devcluster.testinium.io/reports/987",
        "error_message": null
    },
    {
        "id": 986,
        "scheduled_report_id": 132,
        "execution_time": "2025-02-04T14:30:00Z",
        "status": "FAILED",
        "generated_report_url": null,
        "error_message": "Timeout while generating report"
    }
]
```

### Response Fields

| Field                  | Type   | Description                                                  |
| ---------------------- | ------ | ------------------------------------------------------------ |
| id                     | Long   | Unique ID of the report history record.                      |
| scheduled\_report\_id  | Long   | The ID of the scheduled report.                              |
| execution\_time        | String | The timestamp when the report was executed (UTC).            |
| status                 | String | The execution status (e.g., `SUCCESS`, `FAILED`).            |
| generated\_report\_url | String | The URL to download the generated report (if available).     |
| error\_message         | String | Error message in case of a failed execution (if applicable). |

***

### Error Codes

| HTTP Code | Error Message           | Description                                         |
| --------- | ----------------------- | --------------------------------------------------- |
| 400       | INVALID\_REQUEST        | The request was malformed or contained errors.      |
| 404       | REPORT\_NOT\_FOUND      | No scheduled report history found for the given ID. |
| 403       | ACCESS\_DENIED          | User lacks the necessary authority.                 |
| 500       | INTERNAL\_SERVER\_ERROR | An unexpected error occurred on the server side.    |

***

### Example Request&#x20;

```bash
curl --location --request GET 'https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled/history/132' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
