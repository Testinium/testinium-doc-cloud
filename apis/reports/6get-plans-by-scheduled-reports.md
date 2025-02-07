# 6Get Plans By Scheduled Reports

###

This endpoint retrieves all active plans and their associated projects for the currently authenticated company.

***

#### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/plans/createScheduledReport`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

#### Request

No request parameters are required for this endpoint. The request will use the authenticated user's company context.

***

#### Response

The response contains a list of active plans and their associated projects for the user's company.

```json
jsonKopyalaDüzenle[
  {
    "id": 1341,
    "project_id": 368,
    "project_name": "dev_deneme1",
    "plan_name": "goToSozcu tekli"
  },
  {
    "id": 1342,
    "project_id": 368,
    "project_name": "dev_deneme1",
    "plan_name": "pln_data_driven"
  },
  {
    "id": 1551,
    "project_id": 464,
    "project_name": "ClusterGratis",
    "plan_name": "SwipeIOS"
  }
]
```

**Response Fields**

| Field          | Type     | Description                                            |
| -------------- | -------- | ------------------------------------------------------ |
| `id`           | `Long`   | The unique ID of the test plan.                        |
| `project_id`   | `Long`   | The unique ID of the associated project.               |
| `project_name` | `String` | The name of the project associated with the test plan. |
| `plan_name`    | `String` | The name of the test plan.                             |

***

#### Error Codes

| HTTP Code | Error Message           | Description                                                  |
| --------- | ----------------------- | ------------------------------------------------------------ |
| `400`     | `INVALID_REQUEST`       | The request was malformed or contained errors.               |
| `401`     | `UNAUTHORIZED`          | The request lacks proper authentication.                     |
| `403`     | `ACCESS_DENIED`         | User lacks the necessary permissions to access the resource. |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred on the server side.             |

***

#### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://testinium.io/Testinium.RestApi/api/plans/createScheduledReport' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```

4o mini
