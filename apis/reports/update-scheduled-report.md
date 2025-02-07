# Update Scheduled Report

The endpoint updates an existing scheduled report. The user must have the necessary permissions to modify scheduled reports.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled/{id}`
* **Method**: PUT
* **Authentication**: Required (Bearer Token)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type | Required | Description                            |
| --------- | ---- | -------- | -------------------------------------- |
| id        | Long | Yes      | The unique ID of the scheduled report. |

***

### Request&#x20;

The request body should contain the updated scheduled report details.

```json
{
    "id": 132,
    "report_name": "ScheduledReportDeneme1",
    "content_mail": "<p>ScheduledReportDeneme success.</p>",
    "user_roles": [
        "ROLE_CHANGE_USER",
        "ROLE_ADMIN",
        "ROLE_USER",
        "ROLE_INTEGRATION",
        "ROLE_NEW_USER",
        "ROLE_RUN_TEST",
        "ROLE_NEW_COMPANY_ADMIN",
        "ROLE_REPORT",
        "ROLE_COMPANY_ADMIN"
    ],
    "enabled": true,
    "frequency": "DAILY",
    "created_user": "mehmetaksahin",
    "status": ["SUCCESS"],
    "usage_gauge": false,
    "report_hour": "2025-02-06T12:51:07Z",
    "plan_id_list": [1445],
    "start_date": "2025-02-06T12:51:07Z",
    "end_date": "2025-02-28T13:02:48Z",
    "email_list": ["selin.vural@testinium.com"],
    "alerts": [
        {
            "alert_type": "EMAIL",
            "alert_sending_status": "EVERY_TEST",
            "target": "selin.vural@testinium.com",
            "enabled": true,
            "unsubscribe_link_eliminated": false
        }
    ]
}
```

***

### Response

The response contains the updated scheduled report details.

```json
{
    "id": 132,
    "report_name": "ScheduledReportDeneme1",
    "content_mail": "<p>ScheduledReportDeneme success.</p>",
    "user_roles": [
        "ROLE_CHANGE_USER",
        "ROLE_ADMIN",
        "ROLE_USER",
        "ROLE_INTEGRATION",
        "ROLE_NEW_USER",
        "ROLE_RUN_TEST",
        "ROLE_NEW_COMPANY_ADMIN",
        "ROLE_REPORT",
        "ROLE_COMPANY_ADMIN"
    ],
    "enabled": true,
    "frequency": "DAILY",
    "created_user": "mehmetaksahin",
    "status": ["SUCCESS"],
    "usage_gauge": false,
    "report_hour": "2025-02-06T12:51:07Z",
    "plan_id_list": [1445],
    "start_date": "2025-02-06T12:51:07Z",
    "end_date": "2025-02-28T13:02:48Z",
    "email_list": ["selin.vural@testinium.com"],
    "alerts": [
        {
            "alert_type": "EMAIL",
            "alert_sending_status": "EVERY_TEST",
            "target": "selin.vural@testinium.com",
            "enabled": true,
            "unsubscribe_link_eliminated": false
        }
    ]
}
```

### Response Fields

| Field                                | Type    | Description                                           |
| ------------------------------------ | ------- | ----------------------------------------------------- |
| id                                   | Long    | Unique ID of the scheduled report.                    |
| report\_name                         | String  | Name of the scheduled report.                         |
| content\_mail                        | String  | Email content of the report.                          |
| user\_roles                          | List    | List of user roles that have access.                  |
| enabled                              | Boolean | Indicates if the scheduled report is active.          |
| frequency                            | String  | Frequency of the report (e.g., DAILY, WEEKLY).        |
| created\_user                        | String  | Username of the person who created the report.        |
| status                               | List    | Status of the scheduled report.                       |
| usage\_gauge                         | Boolean | Indicates if usage gauge is enabled.                  |
| report\_hour                         | String  | The scheduled time for the report execution (UTC).    |
| plan\_id\_list                       | List    | List of test plan IDs linked to the report.           |
| start\_date                          | String  | Start date of the scheduled report (ISO format).      |
| end\_date                            | String  | End date of the scheduled report (ISO format).        |
| email\_list                          | List    | List of recipient email addresses.                    |
| alerts                               | List    | List of alert configurations.                         |
| alerts.alert\_type                   | String  | Type of alert (e.g., EMAIL).                          |
| alerts.alert\_sending\_status        | String  | Defines when alerts will be sent (e.g., EVERY\_TEST). |
| alerts.target                        | String  | Target email for alerts.                              |
| alerts.enabled                       | Boolean | Indicates if the alert is enabled.                    |
| alerts.unsubscribe\_link\_eliminated | Boolean | Indicates if the unsubscribe link is removed.         |

***

### Error Codes

| HTTP Code | Error Message           | Description                                         |
| --------- | ----------------------- | --------------------------------------------------- |
| 400       | INVALID\_REQUEST        | The request was malformed or contained errors.      |
| 404       | REPORT\_NOT\_FOUND      | No scheduled report was found for the specified ID. |
| 403       | ACCESS\_DENIED          | User lacks the necessary authority.                 |
| 500       | INTERNAL\_SERVER\_ERROR | An unexpected error occurred on the server side.    |

***

### Example Request&#x20;

```bash
curl --location --request PUT 'https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled/132?companyId=5251' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json' \
--data-raw '{
    "id": 132,
    "report_name": "ScheduledReportDeneme1",
    "content_mail": "<p>ScheduledReportDeneme success.</p>",
    "user_roles": ["ROLE_ADMIN", "ROLE_USER"],
    "enabled": true,
    "frequency": "DAILY",
    "created_user": "mehmetaksahin",
    "status": ["SUCCESS"],
    "usage_gauge": false,
    "report_hour": "2025-02-06T12:51:07Z",
    "plan_id_list": [1445],
    "start_date": "2025-02-06T12:51:07Z",
    "end_date": "2025-02-28T13:02:48Z",
    "email_list": ["selin.vural@testinium.com"],
    "alerts": [
        {
            "alert_type": "EMAIL",
            "alert_sending_status": "EVERY_TEST",
            "target": "selin.vural@testinium.com",
            "enabled": true,
            "unsubscribe_link_eliminated": false
        }
    ]
}'
```
