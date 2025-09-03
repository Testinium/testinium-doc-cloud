# Get Active Test Plans

This endpoint retrieves active test plans based on the provided company ID and optional filters such as project ID. The user must have the `PLAN_VIEW` authority to access this endpoint.

***

### Endpoint Details

* **URL**: [https://gateway.testinium.io/plan/active](https://gateway.testinium.io/plan/active)
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Query Parameters

| Name        | Type     | Required | Description                                                                   |
| ----------- | -------- | -------- | ----------------------------------------------------------------------------- |
| `companyId` | `Long`   | Yes      | The unique ID of the company for which active test plans are to be retrieved. |
| `projectId` | `Long`   | No       | The unique ID of the project to filter active test plans.                     |
| pageable    | Pageable | No       | Pagination information (page number, size) for retrieving results.            |

***

***

### Example Response

```json
{
    "data": {
        "content": [
            {
                "id": 1659,
                "planName": "Ber-Mobil-Gratis",
                "projectName": "BER Mobil Deneme"
            },
            {
                "id": 1672,
                "planName": "cloudReport",
                "projectName": "cloudtesti"
            }
        ],
        "page": {
            "size": 10,
            "number": 0,
            "totalElements": 2,
            "totalPages": 1
        }
    },
    "result": {
        "code": 0,
        "message": "success"
    }
}


```

***

### Response Fields

| Field         | Type     | Description                         |
| ------------- | -------- | ----------------------------------- |
| `id`          | `Long`   | The unique ID of the test plan.     |
| `projectName` | `String` | The name of the associated project. |
| `planName`    | `String` | The name of the test plan.          |

***

### Error Codes

<table><thead><tr><th width="134.03125">HTTP Code</th><th>Description</th></tr></thead><tbody><tr><td><code>401</code></td><td><pre><code>Full authentication is required to access this resource
</code></pre></td></tr><tr><td><code>400</code></td><td>One or more required parameters are missing or invalid.</td></tr><tr><td><code>500</code></td><td>An unexpected error occurred.</td></tr></tbody></table>

### Example Request

```bash
curl --location --request GET 'https://gateway.testinium.io/plan/active?companyId=<companyId>&projectId=<projectId>&size=10&page=0' \
--header 'accept: application/json, text/plain, */*' \
--header 'authorization: Bearer <your_access_token>'
```
