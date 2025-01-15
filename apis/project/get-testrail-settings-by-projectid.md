# Get TestRail Settings By ProjectID

This endpoint retrieves the TestRail settings associated with a specified project. The user must have access to the project and be part of the associated company. The endpoint returns the TestRail project details, including information such as project ID, name, announcement visibility, suite mode, and users associated with the project.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/testrail`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                                                     |
| ----------- | ------ | -------- | --------------------------------------------------------------- |
| `projectId` | `Long` | Yes      | The unique ID of the project to retrieve TestRail settings for. |

***

### Query Parameters

| Parameter | Type      | Default | Description                                      |
| --------- | --------- | ------- | ------------------------------------------------ |
| `offset`  | `Integer` | `0`     | The offset for pagination, default is `0`.       |
| `limit`   | `Integer` | `250`   | The number of items to return, default is `250`. |

***

### Request Body

No request body is required for this endpoint.

### Response

The response includes TestRail project details for the specified project.

#### Example Response:

```json
{
  "offset": 0,
  "limit": 250,
  "size": 20,
  "entities": [
    {
      "id": 1,
      "name": "Testinium",
      "show_announcement": false,
      "is_completed": false,
      "suite_mode": 1,
      "url": "https://testinium.testrail.net/index.php?/projects/overview/1",
      "users": [],
      "groups": []
    },
    {
      "id": 8,
      "name": "TestiniumSuite- Planner",
      "show_announcement": false,
      "is_completed": false,
      "suite_mode": 1,
      "url": "https://testinium.testrail.net/index.php?/projects/overview/8",
      "users": [],
      "groups": []
    },
    {
      "id": 9,
      "name": "TestiniumSuite- Core Logic",
      "show_announcement": false,
      "is_completed": false,
      "suite_mode": 1,
      "url": "https://testinium.testrail.net/index.php?/projects/overview/9",
      "users": [],
      "groups": []
    },
    {
      "id": 12,
      "name": "Loadium (OLD)",
      "show_announcement": false,
      "is_completed": false,
      "suite_mode": 1,
      "url": "https://testinium.testrail.net/index.php?/projects/overview/12",
      "users": [],
      "groups": []
    },
    {
      "id": 13,
      "name": "Enterprice-Testinium",
      "show_announcement": false,
      "is_completed": false,
      "suite_mode": 1,
      "url": "https://testinium.testrail.net/index.php?/projects/overview/13",
      "users": [],
      "groups": []
    },
    {
      "id": 16,
      "name": "Digitürk Testinium",
      "show_announcement": false,
      "is_completed": false,
      "suite_mode": 1,
      "url": "https://testinium.testrail.net/index.php?/projects/overview/16",
      "users": [
        {
          "user_id": 1,
          "global_role_id": 1,
          "global_role": "Lead",
          "project_role_id": 1,
          "project_role": "Lead"
        }
      ],
      "groups": []
    }
  ],
  "_links": {}
}
```

***

### Error Codes

| HTTP Code | Error Code              | Description                                                      |
| --------- | ----------------------- | ---------------------------------------------------------------- |
| `400`     | `INVALID_PROJECT_ID`    | The provided project ID is invalid.                              |
| `403`     | `ACCESS_DENIED`         | The user does not have access to the specified project.          |
| `404`     | `PROJECT_NOT_FOUND`     | The project with the specified ID does not exist.                |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred while retrieving TestRail settings. |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/testrail?offset=0&limit=10" \
--header 'Authorization: Bearer <your_access_token>'
```
