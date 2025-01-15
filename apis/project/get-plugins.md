# Get Plugins

The **Get Company Plugins** API retrieves the list of plugins associated with a company. Depending on the user's resource access, detailed or basic plugin information is returned. The user must be authenticated to access this endpoint.

***

### Endpoint Information

* **URL**: `https://clouddev.testinium.io/Testinium.RestApi/api/companies/plugins`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Response

The response contains a list of plugins associated with the user's current company.

```json
[
  {
    "company_id": 5267,
    "enabled": true,
    "plugin_type": "TUNNEL",
    "clean_name": "Tunnel",
    "configurable": false
  },
  {
    "company_id": 5267,
    "enabled": true,
    "plugin_type": "FILE_UPLOAD",
    "clean_name": "File Upload",
    "configurable": false
  },
  {
    "company_id": 5267,
    "enabled": true,
    "plugin_type": "TESTRAIL",
    "clean_name": "Test Rail",
    "configurable": true,
    "testrail_url": "https://testinium.testrail.net/",
    "testrail_username": "onur@testinium.com",
    "testrail_password": "Testinium.2014+"
  },
  {
    "company_id": 5267,
    "enabled": true,
    "plugin_type": "XRAY",
    "clean_name": "Xray",
    "configurable": true,
    "xray_server_url": "https://digiport.arcelik.com/",
    "xray_username": "api.user",
    "xray_api_key": "Digiport123"
  },
  {
    "company_id": 5267,
    "enabled": true,
    "plugin_type": "LIVE_TESTING",
    "clean_name": "Live Testing",
    "configurable": false
  },
  {
    "company_id": 5267,
    "enabled": true,
    "plugin_type": "JIRA",
    "clean_name": "Jira",
    "configurable": true,
    "jira_server_url": "https://kartalproject.atlassian.net",
    "jira_username": "fkartal47@gmail.com",
    "jira_password": "ATATT3xFfGF0EQBrkXOXKsgNYtzb2eb_kk24roIFvn8CHhZi6M9izqoLUzp7Xs3KYmBxXhazIVpZMIgBn4ObAZ9ihojgW81rcfExaCCvpIhxFB2uZdZNpSsXpGwwEIvBl043C1GRtz-9imhcD0Kt77RqmIIZPabFltuH3rwVDvJBIYjYw1N37jg=1A695405"
  },
  {
    "company_id": 5267,
    "enabled": true,
    "plugin_type": "SLACK",
    "clean_name": "Slack",
    "configurable": true
  }
]
```

#### Response Fields

| Field               | Type      | Description                                              |
| ------------------- | --------- | -------------------------------------------------------- |
| `company_id`        | `Long`    | ID of the company to which the plugin belongs.           |
| `enabled`           | `Boolean` | Whether the plugin is enabled or not.                    |
| `plugin_type`       | `String`  | The type of the plugin (e.g., `TUNNEL`, `JIRA`).         |
| `clean_name`        | `String`  | The name of the plugin.                                  |
| `configurable`      | `Boolean` | Whether the plugin is configurable by the user.          |
| `testrail_url`      | `String`  | URL for TestRail plugin configuration (if configurable). |
| `testrail_username` | `String`  | Username for TestRail plugin (if configurable).          |
| `testrail_password` | `String`  | Password for TestRail plugin (if configurable).          |
| `xray_server_url`   | `String`  | URL for Xray plugin configuration (if configurable).     |
| `xray_username`     | `String`  | Username for Xray plugin (if configurable).              |
| `xray_api_key`      | `String`  | API Key for Xray plugin (if configurable).               |
| `jira_server_url`   | `String`  | URL for Jira plugin configuration (if configurable).     |
| `jira_username`     | `String`  | Username for Jira plugin (if configurable).              |
| `jira_password`     | `String`  | Password for Jira plugin (if configurable).              |

***

### Error Codes

| HTTP Code | Error Message    | Description                                                   |
| --------- | ---------------- | ------------------------------------------------------------- |
| `403`     | `ACCESS_DENIED`  | User does not have the necessary permissions to view plugins. |
| `500`     | `INTERNAL_ERROR` | An unexpected error occurred on the server side.              |

***

### Example Request

```bash
curl --location --request GET "https://clouddev.testinium.io/Testinium.RestApi/api/companies/plugins" \
--header 'Authorization: Bearer <your_access_token>'
```
