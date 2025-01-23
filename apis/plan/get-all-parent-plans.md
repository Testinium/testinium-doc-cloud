# Get All Parent Plans

Retrieves all parent plans associated with a specific project. A parent plan is a test plan that is not a child of any other plan.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/parentPlans`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type     | Description                                               |
| ----------- | -------- | --------------------------------------------------------- |
| `projectId` | `Long`   | The ID of the project for which to retrieve parent plans. |
| `user`      | `Object` | The user making the request, identified by their company. |

***

### Response

{\`\[ { "id": 3363, "type": "SELENIUM", "project\_id": 1424, "project\_name": "selinkaratedene", "company\_id": 5267, "plan\_name": "gropplan", "period": { "period\_type": "MANUAL", "days\_of\_week": "", "scheduled\_days\_of\_week": \[], "repeat\_period": 60 }, "alerts": \[], "enabled": true, "group\_plan": false, "plan\_parallel\_test\_limit": 0, "failed\_test\_retry\_count": 0, "alerts\_enabled\_result": false, "project\_enabled": true, "test\_run\_type": "CROSS", "created\_at": "2025-01-23T06:16:59Z", "updated\_at": "2025-01-23T06:16:59Z", "created\_by": "mehmetaksahin", "updated\_by": "mehmetaksahin", "xray\_enabled": false, "test\_rail\_enabled": false, "test\_rail\_any\_mismatch": false, "is\_parent": true, "childs": \[ { "id": 3364, "type": "SELENIUM", "project\_id": 1424, "project\_name": "selinkaratedene", "company\_id": 5267, "plan\_name": "deneme1234", "scenarios": \[ 23057 ], "period": { "period\_type": "MANUAL", "days\_of\_week": "", "scheduled\_days\_of\_week": \[], "repeat\_period": 60 }, "alerts": \[], "enabled": true, "group\_plan": false, "plan\_parallel\_test\_limit": 24, "failed\_test\_retry\_count": 0, "alerts\_enabled\_result": false, "project\_enabled": true, "test\_run\_type": "CROSS", "created\_at": "2025-01-23T06:17:31Z", "updated\_at": "2025-01-23T06:17:31Z", "created\_by": "mehmetaksahin", "updated\_by": "mehmetaksahin", "xray\_enabled": false, "test\_rail\_enabled": false, "test\_rail\_any\_mismatch": false, "parent\_id": 3363, "is\_parent": false, "childs": \[], "screen\_shot\_type": "YES", "video\_enabled": true, "environment\_resolutions": \[ { "environment": { "id": 1192, "name": "Firefox", "operating\_system": "WIN10", "browser\_type": "FIREFOX", "environment\_type": "firefox", "environment\_version": "131", "enabled": true, "operating\_system\_clean\_name": "Windows 10", "mobile": false }, "resolution": { "resolution\_name": "FHD", "resolution\_width": 1920, "resolution\_height": 1080 } } ], "test\_plan\_java\_parameters": \[], "performance\_data\_enabled": false, "file\_download\_path": "" } ], "screen\_shot\_type": "YES", "video\_enabled": true, "environment\_resolutions": \[], "test\_plan\_java\_parameters": \[], "performance\_data\_enabled": false, "file\_download\_path": "" } ]\`}

***

### Response Fields

| Field                       | Type      | Description                                          |
| --------------------------- | --------- | ---------------------------------------------------- |
| `id`                        | `int`     | The ID of the parent plan.                           |
| `type`                      | `string`  | The type of the test plan, e.g., "SELENIUM".         |
| `project_id`                | `int`     | The project ID that the plan belongs to.             |
| `plan_name`                 | `string`  | The name of the parent test plan.                    |
| `childs`                    | `Array`   | List of child plans associated with the parent plan. |
| `enabled`                   | `boolean` | Whether the plan is enabled.                         |
| `period`                    | `object`  | The schedule for the plan.                           |
| `created_at`                | `string`  | The creation timestamp of the plan.                  |
| `updated_at`                | `string`  | The last update timestamp of the plan.               |
| `screen_shot_type`          | `string`  | Defines if screenshots are enabled for the plan.     |
| `video_enabled`             | `boolean` | Whether video is enabled for the plan.               |
| `test_plan_java_parameters` | `Array`   | Java parameters for the test plan.                   |

***

### Error Codes

| HTTP Status | Code             | Message                                                         |
| ----------- | ---------------- | --------------------------------------------------------------- |
| 400         | `BAD_REQUEST`    | Invalid request parameters.                                     |
| 401         | `UNAUTHORIZED`   | The user is not authorized to access this resource.             |
| 404         | `NOT_FOUND`      | The specified project does not exist or has no parent plans.    |
| 500         | `INTERNAL_ERROR` | An internal server error occurred while processing the request. |

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/parentPlans" \
--header 'Authorization: Bearer <your_access_token>'
```
