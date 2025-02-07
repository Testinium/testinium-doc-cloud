# 14Get Automated Apps for a Company

##

This endpoint retrieves the list of automated apps for a specific company.

***

### Endpoint Information

* **URL**: `https://devcluster.testinium.io/Testinium.RestApi/api/automated-apps/{companyId}`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                   |
| ----------- | ------ | -------- | ----------------------------- |
| `companyId` | `Long` | Yes      | The unique ID of the company. |

***

### Request Parameters

No request body is required. The `companyId` is provided via the URL path.

***

### Response

The response contains a list of automated apps associated with the specified company.

#### Response Format

```json
jsonKopyalaDüzenle[
    {
        "id": 15,
        "app_type": "android",
        "app_name": "DeFacto",
        "app_display_name": "DeFacto",
        "app_file_path": "https://testinium-dev-cloud-k8s.s3.amazonaws.com/5251/automated-upload/4.72.1-23ce18fe-0299a93d.apk",
        "app_version": "4.72.1",
        "app_package_name": "com.defacto.android",
        "company_id": 5251,
        "file_token": "77b9137a-2717-4ed8-9857-b268030c8413"
    },
    {
        "id": 16,
        "app_type": "ios",
        "app_name": "DeFacto",
        "app_display_name": "",
        "app_file_path": "https://testinium-dev-cloud-k8s.s3.amazonaws.com/5251/automated-upload/4.72.1-24feee8b-dfe2fc66.ipa",
        "app_version": "1085",
        "app_package_name": "APPL",
        "app_identifier": "com.defacto.iphone",
        "company_id": 5251,
        "file_token": "7294b8cf-ab67-45e4-852c-34bad0c3197e"
    }
]
```

***

#### Response Fields

| Field              | Type     | Description                                                               |
| ------------------ | -------- | ------------------------------------------------------------------------- |
| `id`               | `Long`   | The unique ID of the automated app.                                       |
| `app_type`         | `String` | The type of the app (e.g., `android`, `ios`).                             |
| `app_name`         | `String` | The name of the app.                                                      |
| `app_display_name` | `String` | The display name of the app. If not provided, it will be an empty string. |
| `app_file_path`    | `String` | The URL path to the app file (APK or IPA).                                |
| `app_version`      | `String` | The version of the app.                                                   |
| `app_package_name` | `String` | The package name for Android apps.                                        |
| `app_identifier`   | `String` | The app identifier for iOS apps.                                          |
| `company_id`       | `Long`   | The ID of the company that owns the app.                                  |
| `file_token`       | `String` | A unique token associated with the app file.                              |

***

### Error Codes

| HTTP Code | Error Message    | Description                                                     |
| --------- | ---------------- | --------------------------------------------------------------- |
| `401`     | `UNAUTHORIZED`   | The user is not authorized to access the resource.              |
| `403`     | `FORBIDDEN`      | The user does not have permission to access the resource.       |
| `404`     | `NOT_FOUND`      | No automated apps were found for the given company ID.          |
| `500`     | `INTERNAL_ERROR` | An internal server error occurred while processing the request. |

### Example Request

```bash
bashKopyalaDüzenlecurl --location 'https://devcluster.testinium.io/Testinium.RestApi/api/automated-apps/5251' \
--header 'Authorization: Bearer <your_access_token>' \
--header 'current-company-id: <your_company_id>'
```
