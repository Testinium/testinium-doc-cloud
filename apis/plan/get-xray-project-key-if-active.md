# Get Xray Project Key If Active

Retrieves the Xray project key for the given project if it is active. If the project is not active or doesn't have an Xray key, the request will not return a value.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/xray/{projectId}/key`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type     | Description                                               |
| ----------- | -------- | --------------------------------------------------------- |
| `projectId` | `Long`   | The ID of the project to retrieve the Xray key for.       |
| `user`      | `Object` | The user making the request, identified by their company. |

***

### Response

{\`"1"\`}

***

### Response Fields

| Field | Type  | Description                                                                                       |
| ----- | ----- | ------------------------------------------------------------------------------------------------- |
| `1`   | `int` | The Xray project key for the specified project if active. If inactive, no value will be returned. |

***

### Error Codes

| HTTP Status | Code             | Message                                                         |
| ----------- | ---------------- | --------------------------------------------------------------- |
| 400         | `BAD_REQUEST`    | Invalid request parameters.                                     |
| 401         | `UNAUTHORIZED`   | The user is not authorized to access this resource.             |
| 404         | `NOT_FOUND`      | The specified project does not exist or has no active Xray key. |
| 500         | `INTERNAL_ERROR` | An internal server error occurred while processing the request. |

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/xray/{projectId}/key" \
--header 'Authorization: Bearer <your_access_token>'
```
