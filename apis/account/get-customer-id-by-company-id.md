# Get Customer ID by Company ID

This endpoint retrieves the customer ID for a given company by its company ID. The user must have appropriate access to the company to retrieve the customer ID.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/companies/{companyId}/customerId`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                   |
| ----------- | ------ | -------- | ----------------------------- |
| `companyId` | `Long` | Yes      | The unique ID of the company. |

***

### Response

The response contains the customer ID associated with the provided company ID.

```json
{
  "customerId": 3393
}
```

#### Response Fields

| Field        | Type   | Description                                  |
| ------------ | ------ | -------------------------------------------- |
| `customerId` | `Long` | The customer ID associated with the company. |

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `404`     | `COMPANY_NOT_FOUND`     | No company was found for the specified ID.       |
| `403`     | `ACCESS_DENIED`         | User lacks access to the specified company.      |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location 'https://testinium.io/Testinium.RestApi/api/companies/{companyId}/customerId' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
