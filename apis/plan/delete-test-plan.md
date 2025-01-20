# Delete Test Plan

This endpoint allows the deletion of a specified test plan. The user must have the necessary authority (`PLAN_DELETE`) to perform this action.

***

## Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/{planId}`
* **Method**: `DELETE`
* **Authentication**: Required (`Bearer Token`)

***

## Path Parameters

| Parameter | Type   | Required | Description                            |
| --------- | ------ | -------- | -------------------------------------- |
| `planId`  | `Long` | Yes      | The ID of the test plan to be deleted. |

***

## Request Body

This endpoint does not require a request body.

***

## Response Body

The response will return a `Boolean` indicating whether the test plan deletion was successful (`true` for success, `false` for failure).

***

## Error Codes

| HTTP Code | Error Code                         | Description                                                                |
| --------- | ---------------------------------- | -------------------------------------------------------------------------- |
| `400`     | `USER_NOT_FOUND`                   | The user is not valid or not authenticated.                                |
| `403`     | `ACCESS_DENIED`                    | The user does not have the required authority to delete the test plan.     |
| `404`     | `PLAN_NOT_FOUND`                   | The test plan with the specified ID does not exist.                        |
| `409`     | `SCHEDULED_REPORT_RELATION_EXISTS` | The test plan is associated with a scheduled report and cannot be deleted. |
| `500`     | `SYSTEM_INTERNAL_ERROR`            | An unexpected error occurred while deleting the test plan.                 |

***

## Example Request

```bash
curl --location --request DELETE "https://testinium.io/Testinium.RestApi/api/plans/{planId}" \
--header 'Authorization: Bearer <your_access_token>'
```
