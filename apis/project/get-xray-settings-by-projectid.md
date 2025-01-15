# Get Xray Settings By ProjectID

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get Xray Settings By ProjectID

This endpoint retrieves Xray settings associated with a specified project. The user must have access to the project and be part of the associated company. The endpoint returns the Xray project details, including project ID, name, and associated Xray issues.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/xray`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                                                 |
| ----------- | ------ | -------- | ----------------------------------------------------------- |
| `projectId` | `Long` | Yes      | The unique ID of the project to retrieve Xray settings for. |

***

### Query Parameters

This endpoint does not accept any query parameters.

***

### Request Body

No request body is required for this endpoint.

### Response

The response includes Xray project details for the specified project.

#### Example Response:

{\`{ "project": \[ { "label": "AeroDryFilter", "value": "CRD24009S1", "selected": false } ] }\`}

***

### Error Codes

| HTTP Code | Error Code              | Description                                                  |
| --------- | ----------------------- | ------------------------------------------------------------ |
| `400`     | `INVALID_PROJECT_ID`    | The provided project ID is invalid.                          |
| `403`     | `ACCESS_DENIED`         | The user does not have access to the specified project.      |
| `404`     | `PROJECT_NOT_FOUND`     | The project with the specified ID does not exist.            |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred while retrieving Xray settings. |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/xray" \
--header 'Authorization: Bearer <your_access_token>'
```
