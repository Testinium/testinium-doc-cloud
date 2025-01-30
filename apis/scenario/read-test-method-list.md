# Read Test Method List

This endpoint is used to **retrieve a list of test methods** from a specified file in the project's source code.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/vcs/{projectId}/methods`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter   | Type     | Required | Description                                    |
| ----------- | -------- | -------- | ---------------------------------------------- |
| `projectId` | `String` | Yes      | The ID of the project to retrieve methods for. |

***

### Request Body

```json
{
  "path": "TestFile.spec"
}
```

***

### Response

The response will contain a list of **test methods** extracted from the specified file.

```json
[
    "@testMethod1",
    "@testMethod2",
    "@testMethod3"
]
```

### Response Fields

| Field        | Type    | Description                                                 |
| ------------ | ------- | ----------------------------------------------------------- |
| `methodList` | `Array` | A list of test methods in the file specified by the `path`. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                                 |
| --------- | ----------------------- | ----------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request body is invalid or missing the required fields. |
| `404`     | `PROJECT_NOT_FOUND`     | The specified `projectId` was not found.                    |
| `404`     | `FILE_NOT_FOUND`        | The specified file path was not found.                      |
| `401`     | `UNAUTHORIZED_USER`     | The user is unauthorized or the token is missing/invalid.   |
| `500`     | `INTERNAL_SERVER_ERROR` | A general server error occurred.                            |
| `500`     | `GIT_CONNECTION_ERROR`  | An error occurred while trying to connect to Git.           |

***

### Example Request

```bash
curl --location --request POST 'https://testinium.io/Testinium.RestApi/api/vcs/{projectId}/methods' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json' \
--data '{"path": "TestFile.spec"}'
```
