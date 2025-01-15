# Enable Project

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Enable Project

This endpoint enables a specified project by setting its `enabled` field to `true`. The endpoint requires the user to have the `PROJECT_UPDATE` authority.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/enable`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                          |
| ----------- | ------ | -------- | ------------------------------------ |
| `projectId` | `Long` | Yes      | The ID of the project to be enabled. |

***

### Request Body

No request body is required for this endpoint.

***

### Response

On success, the endpoint returns an HTTP status code of `200 OK`.

#### Example Response:

{\`"OK"\`}

***

### Error Codes

| HTTP Code | Error Code              | Description                                              |
| --------- | ----------------------- | -------------------------------------------------------- |
| `400`     | `INVALID_PROJECT_ID`    | The provided project ID is invalid.                      |
| `403`     | `ACCESS_DENIED`         | The user does not have the `PROJECT_UPDATE` authority.   |
| `404`     | `PROJECT_NOT_FOUND`     | The project with the specified ID does not exist.        |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred while enabling the project. |

***

### Example Request

```bash
curl --location --request PUT "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/enable" \
--header 'Authorization: Bearer <your_access_token>'
```
