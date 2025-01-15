# Get Branch List By ProjectID

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get Branch List By ProjectID

Retrieves the list of branches for a specific project. The user must have the necessary permissions to access this endpoint.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/vcs/{projectId}/branches`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type     | Required | Description                                         |
| ----------- | -------- | -------- | --------------------------------------------------- |
| `projectId` | `String` | Yes      | The unique ID of the project to fetch branches for. |

***

### Response

{\`\[ "master" ]\`}

#### Response Fields

| Field        | Type    | Description                                         |
| ------------ | ------- | --------------------------------------------------- |
| `branchList` | `Array` | A list of branch names associated with the project. |

***

### Error Codes

| HTTP Code | Error Message       | Description                                        |
| --------- | ------------------- | -------------------------------------------------- |
| `400`     | `INVALID_REQUEST`   | The request was malformed or contained errors.     |
| `404`     | `PROJECT_NOT_FOUND` | No project was found for the specified project ID. |
| `404`     | `EMPTY_BRANCH`      | No branches were found for the specified project.  |

***

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/vcs/{projectId}/branches" \
--header 'Authorization: Bearer <your_access_token>'
```
