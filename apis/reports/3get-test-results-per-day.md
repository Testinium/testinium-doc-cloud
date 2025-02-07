# 3Get Test Results Per Day

###

This endpoint retrieves the test result counts per day for a specified time range.

#### Endpoint Information

* **URL**: `https://testinium.io/Testinium.Reporter/api/test-results/results-per-day`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

#### Request Parameters

| Parameter   | Type   | Required | Description                                          |
| ----------- | ------ | -------- | ---------------------------------------------------- |
| `companyId` | `Long` | Yes      | The unique ID of the company.                        |
| `startDate` | `Date` | Yes      | The start date of the report (format: `yyyy-MM-dd`). |
| `endDate`   | `Date` | Yes      | The end date of the report (format: `yyyy-MM-dd`).   |
| `projectId` | `Long` | No       | The unique ID of the project (optional).             |
| `planId`    | `Long` | No       | The unique ID of the test plan (optional).           |

***

#### Response

```json
jsonKopyalaDüzenle{
  "companyId": 5251,
  "projectId": null,
  "planId": null,
  "startDate": "2025-02-05T21:00:00.000+00:00",
  "endDate": "2025-02-05T21:00:00.000+00:00",
  "testResultCountPerDaysList": [
    {
      "day": "2025-02-06",
      "successCount": 1,
      "warningCount": 0,
      "failureCount": 0,
      "errorCount": 5
    }
  ]
}
```

**Response Fields**

| Field                        | Type     | Description                                   |
| ---------------------------- | -------- | --------------------------------------------- |
| `companyId`                  | `Long`   | The company ID.                               |
| `projectId`                  | `Long`   | The project ID (if specified).                |
| `planId`                     | `Long`   | The test plan ID (if specified).              |
| `startDate`                  | `String` | The start date of the report.                 |
| `endDate`                    | `String` | The end date of the report.                   |
| `testResultCountPerDaysList` | `Array`  | A list of results for each day in the report. |

***

#### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://testinium.io/Testinium.Reporter/api/test-results/results-per-day' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>' \
--data 'companyId=5251&startDate=2025-02-06&endDate=2025-02-06'
```

4o mini
