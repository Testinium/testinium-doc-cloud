---
hidden: true
---

# Delete Customer API

This endpoint allows an authorized user to delete a specific customer. The user must have either the `ROLE_ADMIN` or `ROLE_COMPANY_ADMIN` authority to access this endpoint.

***

### Endpoint Information

* **URL**: https://account.testinium.com/api/v1/customers`/{customerId}`
* **Method**: `DELETE`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter | Type   | Required | Description                    |
| --------- | ------ | -------- | ------------------------------ |
| `id`      | `Long` | Yes      | The unique ID of the customer. |

***

### Response

If the request is successful, the response will return an HTTP `200 OK` status with no content.

***

### Error Codes

| HTTP Code | Error Message           | Description                                      |
| --------- | ----------------------- | ------------------------------------------------ |
| `403`     | `ACCESS_DENIED`         | User lacks the required admin authority.         |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.   |
| `404`     | `CUSTOMER_NOT_FOUND`    | No customer was found for the specified ID.      |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side. |

***

### Example Request

```bash
curl --location --request DELETE 'https://https://account.testinium.com/api/v1/customers/{customerId}' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
