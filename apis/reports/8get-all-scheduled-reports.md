# 8Get All Scheduled Reports

###

This endpoint is used to retrieve a paginated list of scheduled reports for a specific company. You can filter and paginate the results based on the provided parameters.

***

#### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)
* **Path Parameters**:
  * `companyId`: The ID of the company for which to retrieve the scheduled reports.

***

#### Request

**Request Parameters**

| Parameter    | Type     | Description                                                          |
| ------------ | -------- | -------------------------------------------------------------------- |
| `companyId`  | `Long`   | The ID of the company for which the scheduled reports are retrieved. |
| `page`       | `int`    | The page number to retrieve (0-indexed).                             |
| `size`       | `int`    | The number of items per page.                                        |
| `filterText` | `String` | (Optional) A filter string to search reports by name or content.     |

**Request Example**

```bash
bashKopyalaDüzenlecurl --location 'https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled?companyId=5251&page=1&size=20' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```

***

#### Response

The response contains a paginated result with a list of scheduled reports. It includes metadata such as the current page, total count of reports, and page count.

**Response Example**

```json
jsonKopyalaDüzenle{
    "current_page": 1,
    "total_count": 1,
    "page_count": 1,
    "next_page": "",
    "previous_page": "",
    "item_list": [
        {
            "id": 132,
            "report_name": "ScheduledReportDeneme",
            "content_mail": "<p>ScheduledReportDeneme success.</p>",
            "user_roles": [
                "ROLE_INTEGRATION",
                "ROLE_RUN_TEST",
                "ROLE_CHANGE_USER",
                "ROLE_COMPANY_ADMIN",
                "ROLE_NEW_COMPANY_ADMIN",
                "ROLE_ADMIN",
                "ROLE_USER",
                "ROLE_REPORT",
                "ROLE_NEW_USER"
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
    ],
    "rest_api_url": "https://devcluster.testinium.io/Testinium.RestApi"
}
```

**Response Fields**

| Field           | Type     | Description                                         |
| --------------- | -------- | --------------------------------------------------- |
| `current_page`  | `int`    | The current page number (0-indexed).                |
| `total_count`   | `int`    | The total number of scheduled reports available.    |
| `page_count`    | `int`    | The total number of pages.                          |
| `next_page`     | `String` | The URL to the next page (if applicable).           |
| `previous_page` | `String` | The URL to the previous page (if applicable).       |
| `item_list`     | `Array`  | The list of scheduled reports for the current page. |
| `rest_api_url`  | `String` | The base URL for the REST API.                      |

**Item List Fields**

| Field          | Type      | Description                                             |
| -------------- | --------- | ------------------------------------------------------- |
| `id`           | `Long`    | The ID of the scheduled report.                         |
| `report_name`  | `String`  | The name of the scheduled report.                       |
| `content_mail` | `String`  | The content of the report email in HTML format.         |
| `user_roles`   | `Array`   | List of roles that have access to the scheduled report. |
| `enabled`      | `Boolean` | Whether the report is enabled (`true` or `false`).      |
| `frequency`    | `String`  | The frequency of the report (e.g., `DAILY`).            |
| `created_user` | `String`  | The user who created the scheduled report.              |
| `status`       | `Array`   | The status of the report (e.g., `SUCCESS`).             |
| `usage_gauge`  | `Boolean` | Whether the usage gauge is enabled.                     |
| `report_hour`  | `String`  | The scheduled time for the report (ISO 8601 format).    |
| `plan_id_list` | `Array`   | List of plan IDs included in the report.                |
| `start_date`   | `String`  | The start date for the scheduled report.                |
| `end_date`     | `String`  | The end date for the scheduled report.                  |
| `email_list`   | `Array`   | List of email addresses to receive the report.          |
| `alerts`       | `Array`   | List of alert configurations for the report.            |

**Alerts Fields**

| Field                         | Type      | Description                                           |
| ----------------------------- | --------- | ----------------------------------------------------- |
| `alert_type`                  | `String`  | The type of alert (e.g., `EMAIL`).                    |
| `alert_sending_status`        | `String`  | The sending status of the alert (e.g., `EVERY_TEST`). |
| `target`                      | `String`  | The target recipient of the alert.                    |
| `enabled`                     | `Boolean` | Whether the alert is enabled (`true` or `false`).     |
| `unsubscribe_link_eliminated` | `Boolean` | Whether the unsubscribe link has been removed.        |

***

#### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://testinium.io/Testinium.RestApi/api/scheduled-reports/scheduled?companyId=5251&page=1&size=20' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```

***

#### Error Codes

| HTTP Code | Error Message           | Description                                                  |
| --------- | ----------------------- | ------------------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.               |
| `401`     | `UNAUTHORIZED`          | The request lacks proper authentication.                     |
| `403`     | `ACCESS_DENIED`         | User lacks the necessary permissions to access the resource. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.             |
