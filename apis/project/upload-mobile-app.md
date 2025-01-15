# Upload Mobile App

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Upload Mobile App

The endpoint allows uploading a mobile application file (APK for Android or IPA for iOS) to an existing Appium project. The user must have the necessary permissions to update the project.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/mobileApp/{mobileType}`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter    | Type     | Required | Description                                              |
| ------------ | -------- | -------- | -------------------------------------------------------- |
| `projectId`  | `Long`   | Yes      | The unique ID of the project.                            |
| `mobileType` | `String` | Yes      | The type of the mobile application (`ios` or `android`). |

***

### Request Parameters

| Parameter | Type            | Required | Description                              |
| --------- | --------------- | -------- | ---------------------------------------- |
| `file`    | `MultipartFile` | Yes      | The mobile app file (APK/IPA) to upload. |

***

### Response

This endpoint returns a `200 OK` status if the file is uploaded and processed successfully. There is no additional response body.

***

### Error Codes

| HTTP Code | Error Code              | Description                                 |
| --------- | ----------------------- | ------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | Invalid or missing `mobileType`.            |
| `400`     | `FILE_NOT_FOUND`        | The uploaded file is empty or missing.      |
| `404`     | `PROJECT_NOT_FOUND`     | No project was found with the specified ID. |
| `400`     | `INVALID_PROJECT_TYPE`  | The project is not an Appium project.       |
| `403`     | `ACCESS_DENIED`         | User lacks `PROJECT_UPDATE` authority.      |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred.               |

***

### Example Request

```bash
curl --location --request POST "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/mobileApp/android" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'\
--header 'Content-Type: multipart/form-data' \
--form 'file=@/path/to/your-app.apk'
```
