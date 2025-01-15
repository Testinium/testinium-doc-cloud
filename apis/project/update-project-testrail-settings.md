# Update Project TestRail Settings

This endpoint allows users to update TestRail settings for a specific project. It requires the `PROJECT_UPDATE` authority and a valid `projectId`. The request body should contain the `TestRailProjectModel` with the necessary details.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/testrail`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                             |
| ----------- | ------ | -------- | --------------------------------------- |
| `projectId` | `Long` | Yes      | The unique ID of the project to update. |

***

### Request Body

The request body should contain the `TestRailProjectModel` which consists of the `id` and `name` of the TestRail project to associate with the current project.

| Field  | Type      | Required | Description                                  |
| ------ | --------- | -------- | -------------------------------------------- |
| `id`   | `Integer` | Yes      | The ID of the TestRail project to associate. |
| `name` | `String`  | Yes      | The name of the TestRail project.            |

***

### Response

Upon successful execution, the server responds with a status of `200 OK` and updates the project's TestRail settings.

```json
[
  "1"
]
```

#### Response Fields

| Field     | Type     | Description                                  |
| --------- | -------- | -------------------------------------------- |
| `status`  | `String` | The status of the request (e.g., `success`). |
| `message` | `String` | A descriptive message about the update.      |

***

### Error Codes

| HTTP Code | Error Message           | Description                                       |
| --------- | ----------------------- | ------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.    |
| `403`     | `ACCESS_DENIED`         | User lacks `PROJECT_UPDATE` authority.            |
| `404`     | `PROJECT_NOT_FOUND`     | The project with the specified ID does not exist. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.  |

***

### Example Request

```bash
curl --location --request PUT "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/testrail" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
  "id": 1234,
  "name": "TestRail Project Example"
}'
```
