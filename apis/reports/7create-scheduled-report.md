# 7Create Scheduled Report

###

This endpoint allows the creation of a scheduled report, which can be used to automatically generate and send reports based on specified parameters such as frequency, user roles, and email recipients.

***

#### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)
* **Path Parameters**:
  * `companyId`: The ID of the company to which the report belongs.

***

#### Request

The request body should be a JSON object containing the details of the scheduled report.

**Request Body Example**

```json
jsonKopyalaDüzenle{
    "report_name": "ScheduledReportDeneme",
    "content_mail": "<p>ScheduledReportDeneme success.</p>",
    "user_roles": [
        "ROLE_CHANGE_USER", "ROLE_ADMIN", "ROLE_USER", 
        "ROLE_INTEGRATION", "ROLE_NEW_USER", "ROLE_RUN_TEST", 
        "ROLE_NEW_COMPANY_ADMIN", "ROLE_REPORT", "ROLE_COMPANY_ADMIN"
    ],
    "frequency": "DAILY",
    "created_user": "mehmetaksahin",
    "status": ["SUCCESS"],
    "report_hour": "2025-02-06T12:51:07.317Z",
    "project_id_list": [405],
    "plan_id_list": [1445],
    "start_date": "2025-02-06T12:51:07.317Z",
    "enabled": true,
    "email_list": ["selin.vural@testinium.com"],
    "usage_gauge": false,
    "end_date": "2025-02-28T13:02:47.520Z"
}
```

**Request Fields**

| Field             | Type      | Description                                             |
| ----------------- | --------- | ------------------------------------------------------- |
| `report_name`     | `String`  | The name of the scheduled report.                       |
| `content_mail`    | `String`  | The content of the report email, in HTML format.        |
| `user_roles`      | `Array`   | List of roles that have access to the scheduled report. |
| `frequency`       | `String`  | The frequency of the report (e.g., `DAILY`).            |
| `created_user`    | `String`  | The user who created the scheduled report.              |
| `status`          | `Array`   | The status of the report (e.g., `SUCCESS`).             |
| `report_hour`     | `String`  | The scheduled time for the report (ISO 8601 format).    |
| `project_id_list` | `Array`   | List of project IDs included in the report.             |
| `plan_id_list`    | `Array`   | List of plan IDs included in the report.                |
| `start_date`      | `String`  | The start date for the scheduled report.                |
| `enabled`         | `Boolean` | Whether the report is enabled (`true` or `false`).      |
| `email_list`      | `Array`   | List of email addresses to receive the report.          |
| `usage_gauge`     | `Boolean` | Indicates whether the usage gauge is enabled.           |
| `end_date`        | `String`  | The end date for the scheduled report.                  |

***

#### Response

The response contains the details of the created scheduled report.

**Response Example**

```json
jsonKopyalaDüzenle{
    "report_name": "ScheduledReportDeneme",
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
    "status": [
        "SUCCESS"
    ],
    "usage_gauge": false,
    "report_hour": "2025-02-06T12:51:07Z",
    "plan_id_list": [
        1445
    ],
    "start_date": "2025-02-06T12:51:07Z",
    "end_date": "2025-02-28T13:02:47Z",
    "email_list": [
        "selin.vural@testinium.com"
    ]
}
```

**Response Fields**

| Field          | Type      | Description                                             |
| -------------- | --------- | ------------------------------------------------------- |
| `report_name`  | `String`  | The name of the scheduled report.                       |
| `content_mail` | `String`  | The content of the report email, in HTML format.        |
| `user_roles`   | `Array`   | List of roles that have access to the scheduled report. |
| `enabled`      | `Boolean` | Whether the report is enabled (`true` or `false`).      |
| `frequency`    | `String`  | The frequency of the report (e.g., `DAILY`).            |
| `created_user` | `String`  | The user who created the scheduled report.              |
| `status`       | `Array`   | The status of the report (e.g., `SUCCESS`).             |
| `usage_gauge`  | `Boolean` | Indicates whether the usage gauge is enabled.           |
| `report_hour`  | `String`  | The scheduled time for the report (ISO 8601 format).    |
| `plan_id_list` | `Array`   | List of plan IDs included in the report.                |
| `start_date`   | `String`  | The start date for the scheduled report.                |
| `end_date`     | `String`  | The end date for the scheduled report.                  |
| `email_list`   | `Array`   | List of email addresses to receive the report.          |

***

#### Error Codes

| HTTP Code | Error Message           | Description                                                  |
| --------- | ----------------------- | ------------------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.               |
| `401`     | `UNAUTHORIZED`          | The request lacks proper authentication.                     |
| `403`     | `ACCESS_DENIED`         | User lacks the necessary permissions to access the resource. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.             |

***

#### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled?companyId=5251' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json' \
--data '{
  "report_name": "ScheduledReportDeneme",
  "content_mail": "<p>ScheduledReportDeneme success.</p>",
  "user_roles": [
    "ROLE_CHANGE_USER", "ROLE_ADMIN", "ROLE_USER", 
    "ROLE_INTEGRATION", "ROLE_NEW_USER", "ROLE_RUN_TEST", 
    "ROLE_NEW_COMPANY_ADMIN", "ROLE_REPORT", "ROLE_COMPANY_ADMIN"
  ],
  "frequency": "DAILY",
  "created_user": "mehmetaksahin",
  "status": ["SUCCESS"],
  "report_hour": "2025-02-06T12:51:07.317Z",
  "project_id_list": [405],
  "plan_id_list": [1445],
  "start_date": "2025-02-06T12:51:07.317Z",
  "enabled": true,
  "email_list": ["selin.vural@testinium.com"],
  "usage_gauge": false,
  "end_date": "2025-02-28T13:02:47.520Z"
}'
```
