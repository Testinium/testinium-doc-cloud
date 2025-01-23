# Get Total Plan Count by Filter

The endpoint retrieves the total count of test plans based on the specified filters. The user must have the `PLAN_VIEW`authority to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/totalCountByfilter`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Request Parameters

The following query parameters can be included to filter the test plans:

| Parameter   | Type                    | Required | Description                                                                      |
| ----------- | ----------------------- | -------- | -------------------------------------------------------------------------------- |
| `projectId` | `Long`                  | No       | The ID of the project to filter test plans by.                                   |
| `mobile`    | `List<OperatingSystem>` | No       | A list of operating systems to filter mobile-specific test plans.                |
| `browser`   | `List<BrowserType>`     | No       | A list of browsers to filter test plans for specific browser types.              |
| `service`   | `boolean`               | No       | Include service test plans (`true` for service-related plans, `false`otherwise). |
| `planText`  | `String`                | No       | A text string to search for in the test plan names.                              |

***

### Response

The response is a simple numerical value representing the total count of test plans that match the specified filters.

```json
401
```

### Response Field

| Field | Type   | Description                                              |
| ----- | ------ | -------------------------------------------------------- |
| `456` | `Long` | Total number of test plans matching the filter criteria. |

***

### Error Codes

| HTTP Code | Error Message              | Description                                                |
| --------- | -------------------------- | ---------------------------------------------------------- |
| `401`     | `ACCESS_DENIED`            | The user lacks the `PLAN_VIEW` authority.                  |
| `500`     | `USERS_COMPANY_NOT_EXISTS` | The company associated with the user does not exist.       |
| `500`     | `SYSTEM_INTERNAL_ERROR`    | An unexpected error occurred while processing the request. |

***

### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://testinium.io/Testinium.RestApi/api/plans/totalCountByfilter?projectId=1424&service=true&planText=deneme' \  
--header 'Authorization: Bearer <your_access_token>' \  
--header 'current-company-id: <your_company_id>'  
```
