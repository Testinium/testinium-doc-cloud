# Get Jira Settings By ProjectID

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get Jira Settings By ProjectID

This endpoint retrieves the Jira issue settings associated with a specified project. The user must have access to the project and be part of the associated company. The endpoint returns the Jira settings for the project, including information about issue types, fields, and project-related details.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/jira`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                                            |
| ----------- | ------ | -------- | ------------------------------------------------------ |
| `projectId` | `Long` | Yes      | The ID of the project to retrieve Jira issue settings. |

***

### Response

The response includes the Jira issue settings for the specified project.

#### Example Response:

{\`{ "project": \[ { "label": "Jira1", "value": "BER", "selected": false }, { "label": "Jira2", "value": "KAR", "selected": false }, { "label": "Jira3", "value": "SEN", "selected": false } ], "issue\_type": \[], "issue\_tracker\_fields": { "fields": \[], "selected\_fields": \[] } }\`}

***

### Error Codes

| HTTP Code | Error Code              | Description                                                  |
| --------- | ----------------------- | ------------------------------------------------------------ |
| `400`     | `INVALID_PROJECT_ID`    | The provided project ID is invalid.                          |
| `403`     | `ACCESS_DENIED`         | The user does not have access to the specified project.      |
| `404`     | `PROJECT_NOT_FOUND`     | The project with the specified ID does not exist.            |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred while retrieving Jira settings. |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/jira" \
--header 'Authorization: Bearer <your_access_token>'
```
