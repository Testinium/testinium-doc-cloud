# Get All Roles

###

Retrieves a list of roles associated with the authenticated user.

***

### Endpoint Information

* **URL**: `/api/roles`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Response

```json
jsonKopyalaDüzenle[
    {
        "entity_id": 1,
        "name": "ROLE_ADMIN",
        "clean_name": "ROLE ADMIN"
    },
    {
        "entity_id": 2,
        "name": "ROLE_USER",
        "clean_name": "ROLE USER"
    },
    {
        "entity_id": 3,
        "name": "ROLE_COMPANY_ADMIN",
        "clean_name": "ROLE COMPANY ADMIN"
    },
    {
        "entity_id": 4,
        "name": "ROLE_RUN_TEST",
        "clean_name": "ROLE RUN TEST"
    },
    {
        "entity_id": 5,
        "name": "ROLE_CHANGE_USER",
        "clean_name": "ROLE CHANGE USER"
    },
    {
        "entity_id": 11,
        "name": "ROLE_READ_ONLY",
        "clean_name": "ROLE READ ONLY"
    },
    {
        "entity_id": 12,
        "name": "ROLE_REPORT",
        "clean_name": "ROLE REPORT"
    }
]
```

***

#### Response Fields

| Field        | Type      | Description                                              |
| ------------ | --------- | -------------------------------------------------------- |
| `entity_id`  | `Integer` | The unique identifier for the role.                      |
| `name`       | `String`  | The name of the role (e.g., `ROLE_ADMIN`).               |
| `clean_name` | `String`  | A human-readable name for the role (e.g., `ROLE ADMIN`). |

***

### Example Request

```bash
bashKopyalaDüzenlecurl --location --request GET "https://devcluster.testinium.io/Testinium.RestApi/api/roles" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```

***

#### Error Codes

| HTTP Status | Code            | Message                     |
| ----------- | --------------- | --------------------------- |
| 400         | BAD\_REQUEST    | Invalid request parameters. |
| 401         | UNAUTHORIZED    | The user is not authorized. |
| 403         | FORBIDDEN       | Insufficient permissions.   |
| 404         | NOT\_FOUND      | Resource not found.         |
| 500         | INTERNAL\_ERROR | Server error.               |
