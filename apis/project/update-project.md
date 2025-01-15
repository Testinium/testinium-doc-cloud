# Update Project

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Update Project

This endpoint allows users to update a project with new information. The user must have the appropriate authority (`PROJECT_UPDATE`) to update the project. The API also handles updates to related Appium project files if necessary.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type     | Required | Description                                     |
| ----------- | -------- | -------- | ----------------------------------------------- |
| `projectId` | `String` | Yes      | The unique ID or name of the project to update. |

***

### Request Body

The request body must include the new project information. The fields that can be updated are specified in the `JsonNode` structure.

#### Example Request Body:

{\`{ "" }\`}

***

### Response

The response includes the updated project details.

#### Example Response:

{\`{ "" }\`}

***

### Error Codes

| HTTP Code | Error Code | Description |
| --------- | ---------- | ----------- |
| `400`     |            |             |
| `403`     |            |             |
| `404`     |            |             |
| `500`     |            |             |
| `500`     |            |             |

***

### Example Request

```bash
curl --location --request PUT "https://testinium.io/Testinium.RestApi/api/projects/{projectId}" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
""
}'
```
