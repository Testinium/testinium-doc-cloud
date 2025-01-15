# Delete Project

This endpoint allows the deletion of a specified project. The user must have the necessary authority (`PROJECT_DELETE`) to perform this action. The project will be removed from the system, and any associated test plans will be unscheduled. If the project is related to any test plans or scenarios, the deletion will not be allowed.

***

## Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}`
* **Method**: `DELETE`
* **Authentication**: Required (`Bearer Token`)

***

## Path Parameters

| Parameter   | Type   | Required | Description                          |
| ----------- | ------ | -------- | ------------------------------------ |
| `projectId` | `Long` | Yes      | The ID of the project to be deleted. |

***

## Request Parameters

This endpoint does not require a request body.

***

## Response

The response will return a `Boolean` indicating whether the project deletion was successful (`true` for success, `false` for failure).

***

## Error Codes

| HTTP Code | Error Code                     | Description                                                          |
| --------- | ------------------------------ | -------------------------------------------------------------------- |
| `400`     | `INVALID_USER`                 | The user is not valid or not authenticated.                          |
| `403`     | `ACCESS_DENIED`                | The user does not have the required authority to delete the project. |
| `404`     | `PROJECT_NOT_FOUND`            | The project with the specified ID does not exist.                    |
| `409`     | `PROJECT_HAS_ASSOCIATED_TESTS` | The project has existing scenarios or plans and cannot be deleted.   |
| `500`     | `SYSTEM_INTERNAL_ERROR`        | An unexpected error occurred while deleting the project.             |

***

## Example Request

```bash
curl --location --request DELETE "https://testinium.io/Testinium.RestApi/api/projects/{projectId}" \
--header 'Authorization: Bearer <your_access_token>'
```
