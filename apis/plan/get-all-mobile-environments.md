# Get All Mobile Environments

Retrieves a list of all mobile environments available in the system, based on the mobile operating systems and their respective manufacturers and devices.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/environments/mobile`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Name   | Type   | Description                                |
| ------ | ------ | ------------------------------------------ |
| `user` | `User` | The authenticated user making the request. |

***

### Response

```json
[
    {
        "operating_system": {
            "code": "IOS",
            "platform": "Mobile",
            "clean_name": "iOS",
            "screen_resolutions": [
                {
                    "resolution_name": "WXGA",
                    "resolution_width": 1280,
                    "resolution_height": 800
                },
                {
                    "resolution_name": "WXGA_P",
                    "resolution_width": 1440,
                    "resolution_height": 900
                },
                {
                    "resolution_name": "XGA",
                    "resolution_width": 1024,
                    "resolution_height": 768
                }
            ],
            "mobile": true
        },
        "manufacturers": [
            {
                "code": "APPLE",
                "name": "APPLE",
                "devices": [
                    {
                        "code": "iphone6",
                        "name": "iPhone 6",
                        "details": [
                            {
                                "environment_id": 1103,
                                "version": "12.5.5",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "iPhone_7",
                        "name": "iPhone 7",
                        "details": [
                            {
                                "environment_id": 1101,
                                "version": "15.7.6",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "iPhone6s",
                        "name": "iPhone 6S",
                        "details": [
                            {
                                "environment_id": 1104,
                                "version": "15.7.5",
                                "enabled": true
                            },
                            {
                                "environment_id": 1181,
                                "version": "15.7.9",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "iPhone_XR",
                        "name": "iPhone XR",
                        "details": [
                            {
                                "environment_id": 1174,
                                "version": "12.4.1",
                                "enabled": true
                            },
                            {
                                "environment_id": 1119,
                                "version": "17.1",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "iPhone_X",
                        "name": "iPhone X",
                        "details": [
                            {
                                "environment_id": 1172,
                                "version": "16.7.7",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "IPHONE_14_PLUS",
                        "name": "IPHONE 14 PLUS",
                        "details": [
                            {
                                "environment_id": 1202,
                                "version": "18.1.1",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "IPHONE_13",
                        "name": "IPHONE 13",
                        "details": [
                            {
                                "environment_id": 1204,
                                "version": "18.1.1",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "IPHONE_13_PRO_MAX",
                        "name": "IPHONE 13 PRO MAX",
                        "details": [
                            {
                                "environment_id": 1208,
                                "version": "17.7",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "device create code",
                        "name": "device create name",
                        "details": [
                            {
                                "environment_id": 1214,
                                "version": "13.0",
                                "enabled": true
                            }
                        ]
                    }
                ]
            },
            {
                "code": "LG",
                "name": "LG",
                "devices": [
                    {
                        "code": "G4",
                        "name": "G4",
                        "details": [
                            {
                                "environment_id": 1212,
                                "version": "1.2.3",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "LG_G6",
                        "name": "LG G6",
                        "details": [
                            {
                                "environment_id": 1106,
                                "version": "8.0.0",
                                "enabled": true
                            }
                        ]
                    }
                ]
            },
            {
                "code": "SAMSUNG",
                "name": "SAMSUNG",
                "devices": [
                    {
                        "code": "Galaxy_Note20",
                        "name": "Galaxy Note 20",
                        "details": [
                            {
                                "environment_id": 1177,
                                "version": "13",
                                "enabled": true
                            }
                        ]
                    }
                ]
            }
        ],
        "browsers": [],
        "enabled": false
    },
    {
        "operating_system": {
            "code": "ANDROID",
            "platform": "Mobile",
            "clean_name": "Android",
            "screen_resolutions": [
                {
                    "resolution_name": "FHD",
                    "resolution_width": 1920,
                    "resolution_height": 1080
                },
                {
                    "resolution_name": "SVGA",
                    "resolution_width": 800,
                    "resolution_height": 600
                }
            ],
            "mobile": true
        },
        "manufacturers": [
            {
                "code": "LG",
                "name": "LG",
                "devices": [
                    {
                        "code": "G4",
                        "name": "G4",
                        "details": [
                            {
                                "environment_id": 1212,
                                "version": "1.2.3",
                                "enabled": true
                            }
                        ]
                    },
                    {
                        "code": "LG_G6",
                        "name": "LG G6",
                        "details": [
                            {
                                "environment_id": 1106,
                                "version": "8.0.0",
                                "enabled": true
                            }
                        ]
                    }
                ]
            },
            {
                "code": "Oppo",
                "name": "Oppo",
                "devices": [
                    {
                        "code": "Oppo_A91",
                        "name": "Oppo A91",
                        "details": [
                            {
                                "environment_id": 1210,
                                "version": "11",
                                "enabled": true
                            }
                        ]
                    }
                ]
            },
            {
                "code": "SAMSUNG",
                "name": "SAMSUNG",
                "devices": [
                    {
                        "code": "Galaxy_Note20",
                        "name": "Galaxy Note 20",
                        "details": [
                            {
                                "environment_id": 1177,
                                "version": "13",
                                "enabled": true
                            }
                        ]
                    }
                ]
            }
        ],
        "browsers": [],
        "enabled": false
    }
]
```

***

### Response Fields

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

### Error Codes

| HTTP Status | Code             | Message                                                               |
| ----------- | ---------------- | --------------------------------------------------------------------- |
| 400         | `BAD_REQUEST`    | Invalid request parameters.                                           |
| 401         | `UNAUTHORIZED`   | The user is not authorized to access this resource.                   |
| 403         | `FORBIDDEN`      | The user does not have sufficient permissions to access the resource. |
| 500         | `INTERNAL_ERROR` | An internal server error occurred while processing the request.       |

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/environments/mobile" \
--header 'Authorization: Bearer <your_access_token>'
```
