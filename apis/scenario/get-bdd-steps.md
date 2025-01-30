# Get BDD Steps

This endpoint is used to **retrieve the BDD steps** for a specific project in the system.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/vcs/{projectId}/bddSteps`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter   | Type     | Required | Description                                      |
| ----------- | -------- | -------- | ------------------------------------------------ |
| `projectId` | `String` | Yes      | The ID of the project to retrieve BDD steps for. |

***

### Response

The response will contain a list of BDD steps categorized into **concepts** and **steps**.

```json
{
    "concepts": [
        "Scenario concept1",
        "Scenario concept2"
    ],
    "steps": [
        "Scenario step1",
        "Scenario step2",
        "Scenario step3",
    ]
}
```

### Response Fields

| Field      | Type    | Description                                                                                                   |
| ---------- | ------- | ------------------------------------------------------------------------------------------------------------- |
| `concepts` | `Array` | A list of concept-based steps (e.g., "Log in with username and password").                                    |
| `steps`    | `Array` | A list of action-based steps (e.g., "Check if the filtering by title shows the correct number of personnel"). |

***

### Error Codes

| HTTP Code | Error Message           | Description                                               |
| --------- | ----------------------- | --------------------------------------------------------- |
| `404`     | `PROJECT_NOT_FOUND`     | The specified `projectId` was not found.                  |
| `401`     | `UNAUTHORIZED_USER`     | The user is unauthorized or the token is missing/invalid. |
| `500`     | `INTERNAL_SERVER_ERROR` | A general server error occurred.                          |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/vcs/{projectId}/bddSteps' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json'
```
