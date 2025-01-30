# Delete Multiple Scenarios

This endpoint allows the user to delete multiple test scenarios in one request. The user must have the appropriate authority (`SCENARIO_DELETE`) to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scenarios/deleteMultipleScenarios`
* **Method**: `DELETE`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`current-company-id: <your_company_id>`)

***

### Request Body

```json
[247461, 247462]
```

***

### Request Fields

| Field              | Type         | Description                                                                        |
| ------------------ | ------------ | ---------------------------------------------------------------------------------- |
| `listOfScenarioId` | `List<Long>` | List of scenario IDs to be deleted. Each ID should be a valid scenario identifier. |

### Response Body

The response confirms whether the scenarios were successfully deleted.

```json
true
```

***

### Response Fields

| Field  | Type      | Description                                                          |
| ------ | --------- | -------------------------------------------------------------------- |
| `true` | `Boolean` | Indicates whether the requested scenarios were successfully deleted. |

* **true**: The requested scenarios were successfully deleted.
* **false**: An error occurred while trying to delete the scenarios.

### Error Codes

| HTTP Code | Error Message         | Description                                                           |
| --------- | --------------------- | --------------------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`     | The request body is invalid or missing the required fields.           |
| `404`     | `SCENARIOS_NOT_FOUND` | One or more of the specified scenarios were not found.                |
| `403`     | `FORBIDDEN`           | The user does not have the necessary permissions to delete scenarios. |

***

### Example Request

```bash
curl --location --request DELETE 'https://testinium.io/Testinium.RestApi/api/scenarios/deleteMultipleScenarios' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json' \
--data '[247461, 247462]'
```
