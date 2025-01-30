# Delete Scenario

This API allows the deletion of a single test scenario identified by its `scenarioId`. The user must have the appropriate authority (`SCENARIO_DELETE`) to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/scenarios/{scenarioId}`
* **Method**: `DELETE`
* **Authentication**: Required (`Bearer Token`)
* **Headers**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter    | Type   | Description                                           |
| ------------ | ------ | ----------------------------------------------------- |
| `scenarioId` | `Long` | The ID of the test scenario that needs to be deleted. |

***

### Response

```json
true
```

### Response Fields

| Field  | Type      | Description                                           |
| ------ | --------- | ----------------------------------------------------- |
| `true` | `Boolean` | Indicates that the scenario was successfully deleted. |

* **true**: The scenario was successfully deleted.
* **false**: An error occurred while attempting to delete the scenario.

***

### Error Codes

| HTTP Code | Error Message           | Description                                                     |
| --------- | ----------------------- | --------------------------------------------------------------- |
| `400`     | `INVALID_REQUEST`       | The request is invalid (e.g., missing or malformed parameters). |
| `404`     | `SCENARIO_NOT_FOUND`    | The scenario with the specified ID does not exist.              |
| `403`     | `FORBIDDEN`             | The user does not have permission to delete the scenario.       |
| `500`     | `SYSTEM_INTERNAL_ERROR` | An internal system error occurred during the process.           |

***

### Example Request

```bash
curl --location --request DELETE 'https://testinium.io/Testinium.RestApi/api/scenarios/{scenarioId}' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--header 'Content-Type: application/json'
```
