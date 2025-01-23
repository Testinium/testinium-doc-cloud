# Get All Desktop Environments

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get All Desktop Environments

Retrieves a list of all desktop environments available in the system, based on the list of operating systems considered as "desktop."

***

### Endpoint Information

* **URL**: `/api/environments/desktop`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Response

{\`\[ { "environment\_id": 1, "name": "Windows 10", "type": "desktop", "os": "Windows", "version": "10", "enabled": true }, { "environment\_id": 2, "name": "macOS", "type": "desktop", "os": "macOS", "version": "Big Sur", "enabled": true }, { "environment\_id": 3, "name": "Ubuntu", "type": "desktop", "os": "Linux", "version": "20.04", "enabled": true } ]\`}

***

#### Key Response Fields

| Field            | Type      | Description                                                     |
| ---------------- | --------- | --------------------------------------------------------------- |
| `environment_id` | `Long`    | The unique identifier of the environment.                       |
| `name`           | `String`  | The name of the operating system (e.g., Windows 10, macOS).     |
| `type`           | `String`  | The type of the environment (always "desktop" in this case).    |
| `os`             | `String`  | The operating system name (e.g., Windows, macOS, Linux).        |
| `version`        | `String`  | The version of the operating system (e.g., 10, Big Sur, 20.04). |
| `enabled`        | `Boolean` | Indicates whether the environment is enabled for use.           |

***

#### Example Request

```bash
curl --location --request GET "https://api.example.com/api/environments/desktop" \
--header 'Authorization: Bearer <your_access_token>'
```
