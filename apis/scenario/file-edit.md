# File Edit

This endpoint allows users to **edit File Content** within the project repository, commit the changes, and push them to the repository.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/vcs/{projectId}/fileEdit`
* **Method**: `POST`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter   | Type     | Required | Description                                              |
| ----------- | -------- | -------- | -------------------------------------------------------- |
| `projectId` | `String` | Yes      | The ID of the project for which the file will be edited. |

***

### Request Body

```json
{
  "path": "/specs/Works.spec",
  "branch": "master",
  "message": "file was updated from testinium web-ide : \"/specs/Works.spec\"",
  "content": "V29ya3MKPT09PT0KICAgICAKU2FkZWNlIEtheWRldAotLS0tLS0tLS0tLS0tCgp0YWdzOiBvbmx5U2F2ZQoqIEt1bGxhbsSxY8SxIGFkxLEgOiAiR0JBWUFDIiDFn2lmcmUgOiAiR0JBWUFDIiBpbGUgZ2lyacWfIHlhcAoqICIxIiBzYW5peWUgYmVrbGUKKiAiSG9tZV9Xb3Jrc19QYWdlIiBlbGVtZW50aW5lIHTEsWtsYQoqICIyIiBzYW5peWUgYmVrbGUKKiBCZWtsZXllbiBpxZ9sZXJkZSBpbGsgcGVyc29uZWxpbiBpc21pbmkga2F5ZGV0IHZlIHNpw6cKKiAiMSIgc2FuaXllIGJla2xlCiogIlBlcmZvcm1hbmNlX1BlcnNvbmFsX1F1ZXN0aW9uXzFfQW5zd2VyX0FfU2VsZWN0IiBlbGVtZW50aW5lIHTEsWtsYQoqICIxIiBzYW5peWUgYmVrbGUKKiAiUGVyZm"
}
```

***

### Response

The response will return a `true` value indicating that the file edit was successful and the changes were committed to the repository.

```json
true
```

***

### Error Codes

| HTTP Code | Error Message                  | Description                                                 |
| --------- | ------------------------------ | ----------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`              | The request body is invalid or missing the required fields. |
| `404`     | `PROJECT_NOT_FOUND`            | The specified `projectId` was not found.                    |
| `404`     | `FILE_NOT_FOUND`               | The specified file path was not found.                      |
| `500`     | `FILE_READ_ERROR`              | An error occurred while reading the file.                   |
| `500`     | `GIT_CONNECTION_ERROR`         | An error occurred while trying to connect to Git.           |
| `500`     | `PROJECT_REPOSITORY_NOT_FOUND` | The repository for the specified project was not found.     |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/vcs/{projectId}/fileEdit' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json' \
--data '{"path": "/specs/Works.spec","branch": "master","message": "file was updated from testinium web-ide : \"/specs/Works.spec\"","content": "V29ya3MKPT09PT0KICAgICAKU2FkZWNlIEtheWRldAotLS0tLS0tLS0tLS0tCgp0YWdzOiBvbmx5U2F2ZQoqIEt1bGxhbsSxY8SxIGFkxLEgOiAiR0JBWUFDIiDFn2lmcmUgOiAiR0JBWUFDIiBpbGUgZ2lyacWfIHlhcAoqICIxIiBzYW5peWUgYmVrbGUKKiAiSG9tZV9Xb3Jrc19QYWdlIiBlbGVtZW50aW5lIHTEsWtsYQoqICIyIiBzYW5peWUgYmVrbGUKKiBCZWtsZXllbiBpxZ9sZXJkZSBpbGsgcGVyc29uZWxpbiBpc21pbmkga2F5ZGV0IHZlIHNpw6cKKiAiMSIgc2FuaXllIGJla2xlCiogIlBlcmZvcm1hbmNlX1BlcnNvbmFsX1F1ZXN0aW9uXzFfQW5zd2VyX0FfU2VsZWN0IiBlbGVtZW50aW5lIHTEsWtsYQoqICIxIiBzYW5peWUgYmVrbGUKKiAiUGVyZm"}'
```
