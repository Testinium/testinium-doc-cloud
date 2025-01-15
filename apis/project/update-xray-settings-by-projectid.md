# Update Xray Settings By ProjectID

This endpoint updates the Xray settings associated with a specified project. The user must have access to the project and be part of the associated company. The updated settings will include the Xray project key and configuration.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/xray`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                                               |
| ----------- | ------ | -------- | --------------------------------------------------------- |
| `projectId` | `Long` | Yes      | The unique ID of the project to update Xray settings for. |

***

### Query Parameters

This endpoint does not accept any query parameters.

***

### Request Body

The request body must include the Xray settings to be updated.

#### Example Request Body:

```json
{
  "project": [
    {
      "label": "xray_label1",
      "value": "xray_value1",
      "selected": true
    }
  ]
}
```

***

### Response

The response includes the updated Xray project details for the specified project.

#### Example Response:

```json
{
  "project": [
    {
      "label": "xray_label1",
      "value": "xray_value1",
      "selected": true
    },
    {
      "label": "xray_label2",
      "value": "xray_value2",
      "selected": false
    }
  ]
}
```

***

### Error Codes

| HTTP Code | Error Code              | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `400`     | `INVALID_PROJECT_ID`    | The provided project ID is invalid.                        |
| `403`     | `ACCESS_DENIED`         | The user does not have access to the specified project.    |
| `404`     | `PROJECT_NOT_FOUND`     | The project with the specified ID does not exist.          |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred while updating Xray settings. |

***

### Example Request

```bash
curl --location --request PUT "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/xray" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
  "project": [
    {
      "label": "xray_label1",
      "value": "xray_value1",
      "selected": true
    }
  ]
}'
```
