# Download Execution Report by ID

This endpoint allows users to download the execution report for a specific test execution by providing its unique ID. The user must have the `TEST_EXECUTION_VIEW` authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/executions/{executionId}/download`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter     | Type   | Required | Description                          |
| ------------- | ------ | -------- | ------------------------------------ |
| `executionId` | `Long` | Yes      | The unique ID of the test execution. |

***

### Response

The response contains the Base64-encoded file content and the file's MIME type.

```json
{
    "file": "<Base64_encoded_file_content>",
    "mime_type": "application/pdf"
}
```

### Response Fields

| Field       | Type     | Description                                                     |
| ----------- | -------- | --------------------------------------------------------------- |
| `file`      | `String` | The Base64-encoded content of the downloaded file.              |
| `mime_type` | `String` | The MIME type of the downloaded file (e.g., `application/pdf`). |

***

### Error Codes

| HTTP Code | Error Message                              | Description                                      |
| --------- | ------------------------------------------ | ------------------------------------------------ |
| `404`     | `USERS_COMPANY_NOT_EXISTS`                 | The user's current company does not exist.       |
| `404`     | `EXECUTION_NOT_FOUND`                      | The specified execution ID was not found.        |
| `400`     | `FILE_DOWNLOAD_OPERATION_IS_NOT_SUCESSFUL` | The file download operation was unsuccessful.    |
| `500`     | `SYSTEM_INTERNAL_ERROR`                    | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/executions/{executionId}/download' \
--header 'Authorization: Bearer <your_access_token>' \
```
