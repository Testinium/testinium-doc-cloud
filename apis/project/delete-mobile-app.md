# Delete Mobile App

The endpoint allows deleting a mobile application (APK for Android or IPA for iOS) from an existing Appium project. The user must have the necessary permissions to update the project.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/mobileApp/{mobileType}`
* **Method**: `DELETE`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter    | Type     | Required | Description                                              |
| ------------ | -------- | -------- | -------------------------------------------------------- |
| `projectId`  | `Long`   | Yes      | The unique ID of the project.                            |
| `mobileType` | `String` | Yes      | The type of the mobile application (`ios` or `android`). |

***

### Request Parameters

No request body is required for this endpoint. The parameters are provided via the URL path.

***

### Response

This endpoint returns a `200 OK` status if the mobile app is deleted successfully. No additional response body is returned.

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | Invalid or missing `mobileType`.                 |
| `404`     | `PROJECT_NOT_FOUND`     | No project was found with the specified ID.      |
| `404`     | `INVALID_PROJECT_TYPE`  | The project is not an Appium or Appium2 project. |
| `403`     | `ACCESS_DENIED`         | User lacks `PROJECT_UPDATE` authority.           |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request DELETE "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/mobileApp/{mobileType}' \
--header 'Authorization: Bearer <your_access_token>'
```
