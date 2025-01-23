# Get All Mobile Environments

import Tabs from '@theme/Tabs'; import TabItem from '@theme/TabItem'; import CodeBlock from '@theme/CodeBlock';

## Get All Mobile Environments

Retrieves a list of all mobile environments available in the system, based on the mobile operating systems and their respective manufacturers and devices.

***

### Endpoint Information

* **URL**: `/api/environments/mobile`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Request Parameters

| Name   | Type   | Description                                |
| ------ | ------ | ------------------------------------------ |
| `user` | `User` | The authenticated user making the request. |

***

### Response

{\`\[ { "operating\_system": { "code": "IOS", "platform": "Mobile", "clean\_name": "iOS", "screen\_resolutions": \[ { "resolution\_name": "WXGA", "resolution\_width": 1280, "resolution\_height": 800 }, { "resolution\_name": "WXGA\_P", "resolution\_width": 1440, "resolution\_height": 900 } ], "mobile": true }, "manufacturers": \[ { "code": "APPLE", "name": "APPLE", "devices": \[ { "code": "iphone6", "name": "iPhone 6", "details": \[ { "environment\_id": 1103, "version": "12.5.5", "enabled": true } ] } ] } ], "browsers": \[], "enabled": false }, { "operating\_system": { "code": "ANDROID", "platform": "Mobile", "clean\_name": "Android", "screen\_resolutions": \[ { "resolution\_name": "FHD", "resolution\_width": 1920, "resolution\_height": 1080 } ], "mobile": true }, "manufacturers": \[ { "code": "LG", "name": "LG", "devices": \[ { "code": "G4", "name": "G4", "details": \[ { "environment\_id": 1212, "version": "1.2.3", "enabled": true } ] } ] } ], "browsers": \[], "enabled": false } ]\`}

***

#### Key Response Fields

| Field                | Type      | Description                                                                      |
| -------------------- | --------- | -------------------------------------------------------------------------------- |
| `operating_system`   | `Object`  | Contains information about the operating system.                                 |
| `code`               | `String`  | The code representing the operating system (e.g., `IOS`, `ANDROID`).             |
| `platform`           | `String`  | The platform type, which is `Mobile` in this case.                               |
| `clean_name`         | `String`  | The clean name of the operating system (e.g., `iOS`, `Android`).                 |
| `screen_resolutions` | `Array`   | List of screen resolutions supported by the operating system.                    |
| `manufacturers`      | `Array`   | List of manufacturers and their devices supported on the given operating system. |
| `code`               | `String`  | The code of the manufacturer (e.g., `APPLE`, `SAMSUNG`).                         |
| `name`               | `String`  | The name of the manufacturer.                                                    |
| `devices`            | `Array`   | List of devices from the manufacturer with their respective versions.            |
| `details`            | `Array`   | List of environment details such as `environment_id`, `version`, and `enabled`.  |
| `enabled`            | `Boolean` | Indicates whether the environment is enabled.                                    |
| `browsers`           | `Array`   | List of browsers available for the operating system (empty in this case).        |
| `enabled`            | `Boolean` | Indicates whether the operating system is enabled for use.                       |

***

Error Codes HTTP Status Code Message 400 BAD\_REQUEST Invalid request parameters. 401 UNAUTHORIZED The user is not authorized to access this resource. 403 FORBIDDEN The user does not have sufficient permissions to access the resource. 500 INTERNAL\_ERROR An internal server error occurred while processing the request.

#### Example Request

```bash
curl --location --request GET "https://api.example.com/api/environments/mobile" \
--header 'Authorization: Bearer <your_access_token>'
```
