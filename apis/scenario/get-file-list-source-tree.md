# Get File List (Source Tree)

This endpoint retrieves the **source tree structure** of a given project, including **directories and files**.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/vcs/{projectId}/sourceTree`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameter

| Parameter   | Type     | Required | Description                |
| ----------- | -------- | -------- | -------------------------- |
| `projectId` | `String` | Yes      | The **ID** of the project. |

***

### Query Parameter

| Parameter  | Type      | Required | Default | Description                         |
| ---------- | --------- | -------- | ------- | ----------------------------------- |
| `fullPath` | `Boolean` | No       | `false` | If `true`, returns full file paths. |

***

### Response

The response provides the hierarchical **file and directory structure** for the project.

```json
{
    "vcs_node": {
        "name": "ROOT",
        "node_type": "DIR"
    },
    "children": [
        {
            "vcs_node": {
                "name": "com",
                "node_type": "DIR"
            },
            "children": [
                {
                    "vcs_node": {
                        "name": "acibadem",
                        "node_type": "DIR"
                    },
                    "children": [
                        {
                            "vcs_node": {
                                "name": "Appointment.java",
                                "node_type": "FILE"
                            },
                            "children": [],
                            "base_path": "com/acibadem/Appointment.java",
                            "mime_type": "text/x-java-source"
                        },
                        {
                            "vcs_node": {
                                "name": "General.java",
                                "node_type": "FILE"
                            },
                            "children": [],
                            "base_path": "com/acibadem/General.java",
                            "mime_type": "text/x-java-source"
                        }
                    ],
                    "base_path": "com/acibadem",
                    "mime_type": "application/octet-stream"
                }
            ],
            "base_path": "com",
            "mime_type": "application/octet-stream"
        }
    ],
    "base_path": "/src/test/java"
}
```

***

### Response Fields

| Field                | Type     | Description                                             |
| -------------------- | -------- | ------------------------------------------------------- |
| `vcs_node`           | `Object` | Root node of the **Version Control System (VCS)** tree. |
| `vcs_node.name`      | `String` | Name of the node (file/folder).                         |
| `vcs_node.node_type` | `String` | Type of node (`DIR` for folders, `FILE` for files).     |
| `children`           | `Array`  | List of child directories or files.                     |
| `base_path`          | `String` | Full path of the file/directory.                        |
| `mime_type`          | `String` | MIME type of the file.                                  |

***

### Error Codes

| HTTP Code | Error Message          | Description                                    |
| --------- | ---------------------- | ---------------------------------------------- |
| `404`     | `PROJECT_NOT_FOUND`    | No project found with the given ID.            |
| `401`     | `UNAUTHORIZED_USER`    | Authentication token is missing or invalid.    |
| `500`     | `GIT_CONNECTION_ERROR` | Unable to fetch files from the Git repository. |
| `500`     | `FILE_READ_ERROR`      | An error occurred while reading the files.     |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/vcs/3536/sourceTree?fullPath=true' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
