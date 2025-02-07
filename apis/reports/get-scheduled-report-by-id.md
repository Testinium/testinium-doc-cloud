# Get Scheduled Report by ID

This endpoint retrieves the details of a specific scheduled report based on the report ID and company ID.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled/{id}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: `current-company-id: <your_company_id>`

***

### **Path Parameters**

| Parameter   | Type   | Required | Description                                 |
| ----------- | ------ | -------- | ------------------------------------------- |
| `id`        | `Long` | ✅        | The ID of the scheduled report.             |
| `companyId` | `Long` | ✅        | The company ID to which the report belongs. |

### **Request Example**

```json
{
    "id": 132,
    "report_name": "ScheduledReportDeneme",
    "content_mail": "<p>ScheduledReportDeneme success.</p>",
    "user_roles": [
        "ROLE_REPORT",
        "ROLE_NEW_USER",
        "ROLE_ADMIN",
        "ROLE_CHANGE_USER",
        "ROLE_USER",
        "ROLE_NEW_COMPANY_ADMIN",
        "ROLE_RUN_TEST",
        "ROLE_COMPANY_ADMIN",
        "ROLE_INTEGRATION"
    ],
    "enabled": true,
    "frequency": "DAILY",
    "created_user": "mehmetaksahin",
    "status": [
        "SUCCESS"
    ],
    "usage_gauge": false,
    "report_hour": "2025-02-06T12:51:07Z",
    "plan_id_list": [
        1445
    ],
    "start_date": "2025-02-06T12:51:07Z",
    "end_date": "2025-02-28T13:02:48Z",
    "email_list": [
        "selin.vural@testinium.com"
    ],
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

### **Response Fields**

| Field          | Type      | Description                                               |
| -------------- | --------- | --------------------------------------------------------- |
| `id`           | `Long`    | The unique ID of the scheduled report.                    |
| `report_name`  | `String`  | The name of the scheduled report.                         |
| `content_mail` | `String`  | The content of the report email (HTML format).            |
| `user_roles`   | `Array`   | List of roles that can access this report.                |
| `enabled`      | `Boolean` | Whether the report is enabled (`true` or `false`).        |
| `frequency`    | `String`  | The frequency of report execution (e.g., `DAILY`).        |
| `created_user` | `String`  | The user who created the report.                          |
| `status`       | `Array`   | The current status of the report (e.g., `SUCCESS`).       |
| `usage_gauge`  | `Boolean` | Whether the usage gauge is enabled.                       |
| `report_hour`  | `String`  | The scheduled execution time (ISO 8601 format).           |
| `plan_id_list` | `Array`   | List of test plan IDs included in the report.             |
| `start_date`   | `String`  | The start date of the scheduled report (ISO 8601 format). |
| `end_date`     | `String`  | The end date of the scheduled report (ISO 8601 format).   |
| `email_list`   | `Array`   | List of recipients for the report email.                  |
| `alerts`       | `Array`   | List of alert settings for the report.                    |

### **Alerts Fields**

| Field                         | Type      | Description                                           |
| ----------------------------- | --------- | ----------------------------------------------------- |
| `alert_type`                  | `String`  | The type of alert (e.g., `EMAIL`).                    |
| `alert_sending_status`        | `String`  | The sending status of the alert (e.g., `EVERY_TEST`). |
| `target`                      | `String`  | The email address receiving the alert.                |
| `enabled`                     | `Boolean` | Whether the alert is enabled (`true` or `false`).     |
| `unsubscribe_link_eliminated` | `Boolean` | Whether the unsubscribe link is removed.              |

***

### Error Responses

| HTTP Code | Error Message           | Description                                    |
| --------- | ----------------------- | ---------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors. |
| `401`     | `UNAUTHORIZED`          | Authentication is required.                    |
| `403`     | `ACCESS_DENIED`         | User lacks the necessary permissions.          |
| `404`     | `NOT_FOUND`             | The requested report was not found.            |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server.    |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled/132?companyId=5251' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
