# 13Get Public Report Link

###

This endpoint retrieves a publicly accessible link for a specific test result. The user must have the `TEST_RESULT_VIEW`authority to access this endpoint.

***

### Endpoint Information

*   **URL**:

    ```
    bashKopyalaDüzenlehttps://devcluster.testinium.io/Testinium.RestApi/api/results/{resultId}/publicReportLink
    ```
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter  | Type   | Required | Description                       |
| ---------- | ------ | -------- | --------------------------------- |
| `resultId` | `Long` | Yes      | The unique ID of the test result. |

***

### Request Parameters

No request body is required for this endpoint. The parameter `resultId` is provided via the URL path.

***

### Response

The response contains the public report URL path.

\<CodeBlock language="json"> {\`"/public/report/ab21e60b-354a-45c5-ae28-5f7899b12e13/5251"\`} \</CodeBlock>&#x20;

#### Response Fields

| Field    | Type     | Description                 |
| -------- | -------- | --------------------------- |
| `result` | `String` | The public report URL path. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `404`     | `RESULT_NOT_FOUND`      | No test result found for the given ID.           |
| `403`     | `ACCESS_DENIED`         | User lacks `TEST_RESULT_VIEW` authority.         |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
bashKopyalaDüzenlecurl --location --request GET 'https://devcluster.testinium.io/Testinium.RestApi/api/results/3274073/publicReportLink' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
