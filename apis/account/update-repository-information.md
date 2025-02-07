# Update Repository Information

This endpoint updates the repository information for a company. The user must be authenticated and have the appropriate role to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/companies/repository`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)
* **Header**: Required (`current-company-id: <your_company_id>`)

***

### Request Body

The request body must contain a `CompanyDTO` object with the repository details to be updated.

```json
{
  "id": 5251,
  "repository_url": "https://github.com/GitUser",
  "repository_user": "GitUser",
  "repository_pass": "xxx",
  "internal_repository_url": "https://dev-git.testinium.io/_repouser",
  "internal_repository_user": "repouser",
  "internal_repository_pass": "xxx",
  "external_repository": true,
  "vcs_type": "GIT"
}
```

***

### Response

The response contains the updated company information, including the repository details.

```json
{
  "id": 5251,
  "company_name": "mehmet_aksahin",
  "short_name": "mehmetaksahin",
  "email": "mehmet.aksahin@testinium.com",
  "subscription": {
    "id": 5345,
    "subscription_name": "mehmetaksahin",
    "minute": 200000,
    "max_user": 10,
    "max_real_devices": 0,
    "parallel_test_limit": 200,
    "live_testing_parallel_limit": 195,
    "start_date": "2024-10-21T21:40:51Z",
    "end_date": "2025-10-21T21:40:51Z"
  },
  "used_minute": 8265,
  "repository_url": "https://github.com/GitUser",
  "repository_user": "GitUser",
  "repository_pass": "xxx",
  "internal_repository_url": "https://dev-git.testinium.io/_repouser",
  "internal_repository_user": "repouser",
  "internal_repository_pass": "xxx",
  "vcs_type": "GIT",
  "external_repository": true,
  "external_executor": true,
  "executor_ip": "executor.example.com",
  "executor_port": 22,
  "executor_user": "operasyon",
  "executor_pass": "xxx",
  "executor_workspace": "/home/workspace",
  "internal_executor_ip": "127.0.0.1",
  "internal_executor_port": 22,
  "internal_executor_user": "testinium",
  "internal_executor_pass": "xxx",
  "internal_executor_workspace": "/Users/workspace",
  "enabled": true,
  "customer_id": 3393,
  "company_accessible_plugins": [],
  "boarding": false
}
```

***

### Response Fields

| Field                                      | Type      | Description                                                 |
| ------------------------------------------ | --------- | ----------------------------------------------------------- |
| `id`                                       | `Integer` | The unique identifier of the company.                       |
| `company_name`                             | `String`  | The name of the company.                                    |
| `short_name`                               | `String`  | The short name of the company.                              |
| `email`                                    | `String`  | The email address associated with the company.              |
| `subscription`                             | `Object`  | Subscription information for the company.                   |
| `subscription.id`                          | `Integer` | The unique ID of the subscription.                          |
| `subscription.subscription_name`           | `String`  | The name of the subscription.                               |
| `subscription.minute`                      | `Integer` | The total available minutes for the subscription.           |
| `subscription.max_user`                    | `Integer` | The maximum number of users allowed under the subscription. |
| `subscription.max_real_devices`            | `Integer` | The maximum number of real devices available.               |
| `subscription.parallel_test_limit`         | `Integer` | The parallel test limit for the subscription.               |
| `subscription.live_testing_parallel_limit` | `Integer` | The live testing parallel limit for the subscription.       |
| `subscription.start_date`                  | `String`  | The start date of the subscription.                         |
| `subscription.end_date`                    | `String`  | The end date of the subscription.                           |
| `used_minute`                              | `Integer` | The number of minutes used by the company.                  |
| `repository_url`                           | `String`  | The URL of the repository.                                  |
| `repository_user`                          | `String`  | The username for the repository.                            |
| `repository_pass`                          | `String`  | The password for the repository.                            |
| `internal_repository_url`                  | `String`  | The internal repository URL.                                |
| `internal_repository_user`                 | `String`  | The username for the internal repository.                   |
| `internal_repository_pass`                 | `String`  | The password for the internal repository.                   |
| `vcs_type`                                 | `String`  | The type of version control system (e.g., `GIT`).           |
| `external_repository`                      | `Boolean` | Whether the repository is external.                         |
| `external_executor`                        | `Boolean` | Whether the external executor is enabled.                   |
| `executor_ip`                              | `String`  | The IP address of the executor.                             |
| `executor_port`                            | `Integer` | The port number of the executor.                            |
| `executor_user`                            | `String`  | The username for the executor.                              |
| `executor_pass`                            | `String`  | The password for the executor.                              |
| `executor_workspace`                       | `String`  | The workspace path for the executor.                        |
| `internal_executor_ip`                     | `String`  | The IP address of the internal executor.                    |
| `internal_executor_port`                   | `Integer` | The port number of the internal executor.                   |
| `internal_executor_user`                   | `String`  | The username for the internal executor.                     |
| `internal_executor_pass`                   | `String`  | The password for the internal executor.                     |
| `internal_executor_workspace`              | `String`  | The workspace path for the internal executor.               |
| `enabled`                                  | `Boolean` | Whether the company is enabled.                             |
| `customer_id`                              | `Integer` | The customer ID associated with the company.                |
| `company_accessible_plugins`               | `Array`   | A list of plugins accessible to the company.                |
| `boarding`                                 | `Boolean` | Whether the company is in the boarding process.             |

### Error Codes

| HTTP Code | Error Message                         | Description                                                         |
| --------- | ------------------------------------- | ------------------------------------------------------------------- |
| `400`     | `BAD_REQUEST`                         | The request body is malformed or missing required fields.           |
| `403`     | `FORBIDDEN`                           | The user lacks required roles or permissions.                       |
| `404`     | `COMPANY_NOT_FOUND`                   | The company specified by `id` was not found.                        |
| `404`     | `NOT_HAVING_EXTERNAL_REPOSITORY`      | The company does not have an external repository.                   |
| `404`     | `REPOSITORY_URL_NOT_FOUND`            | The repository URL was not found or invalid.                        |
| `404`     | `REPOSITORY_USER_NOT_FOUND`           | The repository user was not found or invalid.                       |
| `404`     | `REPOSITORY_USERS_PASSWORD_NOT_FOUND` | The repository user's password was not found or invalid.            |
| `404`     | `REPOSITORY_NOT_VALID`                | The repository is not valid.                                        |
| `500`     | `SYSTEM_INTERNAL_ERROR`               | A server-side error occurred while updating repository information. |

***

### Example Request

<pre class="language-bash"><code class="lang-bash">curl --location --request PUT 'https://testinium.io/Testinium.RestApi/api/companies/repository' \
<strong>--header 'Authorization: Bearer &#x3C;your_access_token>' \
</strong>--header 'Content-Type: application/json' \
--header 'current-company-id: &#x3C;your_company_id>'\
--data '{
  "id": 5251,
  "repository_url": "https://github.com/FurkanKartalTSTNM",
  "repository_user": "FurkanKartalTSTNm",
  "repository_pass": "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",
  "internal_repository_url": "https://dev-git.testinium.io/_mehmetaksahin",
  "internal_repository_user": "mehmetaksahin",
  "internal_repository_pass": "Testo8651",
  "external_repository": true,
  "vcs_type": "GIT"
}'
</code></pre>
