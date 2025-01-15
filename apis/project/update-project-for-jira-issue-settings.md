# Update Project For Jira Issue Settings

This endpoint updates the Jira issue settings associated with a specified project. The user must have access to the project and be part of the associated company. The Jira settings are updated based on the provided input model.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/jira`
* **Method**: `PUT`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter   | Type   | Required | Description                                          |
| ----------- | ------ | -------- | ---------------------------------------------------- |
| `projectId` | `Long` | Yes      | The ID of the project to update Jira issue settings. |

***

### Request Body

The request body should contain a `DetailedJiraIssueModel` with updated Jira issue settings for the project.

#### Request Body Structure

| Field                                  | Type            | Required | Description                                    |
| -------------------------------------- | --------------- | -------- | ---------------------------------------------- |
| `assignee`                             | `Object`        | Yes      | The assignee information for the Jira project. |
| `assignee.label`                       | `String`        | Yes      | The label of the assignee.                     |
| `assignee.value`                       | `String`        | Yes      | The value (ID) of the assignee.                |
| `issue_tracker_fields`                 | `Object`        | Yes      | The Jira fields to be configured.              |
| `issue_tracker_fields.fields`          | `Array<Object>` | Yes      | Fields that are available for selection.       |
| `issue_tracker_fields.selected_fields` | `Array<Object>` | Yes      | Fields that are selected.                      |
| `issue_type`                           | `Array<Object>` | Yes      | The issue types for Jira.                      |
| `project`                              | `Array<Object>` | Yes      | The project settings to be configured.         |

#### Example Request Body:

```json
{
  "assignee": {
    "label": "furkan kartal",
    "value": "62108f3a2fd2470071cc1e79"
  },
  "issue_tracker_fields": {
    "fields": [
      {
        "field_name": "description",
        "required": false,
        "predefined": false,
        "display_name": "Description",
        "field_type": 1,
        "schema_type": "string",
        "schema_system": "description",
        "component_type": "INPUT_TEXT_AREA"
      },
      {
        "field_name": "customfield_10021",
        "required": false,
        "predefined": false,
        "display_name": "Flagged",
        "field_type": 2,
        "schema_type": "array",
        "schema_items": "option",
        "component_type": "SELECT_MANY_MENU",
        "allowed_values": [
          {
            "label": "Impediment",
            "value": "10019"
          }
        ]
      },
      {
        "field_name": "labels",
        "required": false,
        "predefined": false,
        "display_name": "Labels",
        "field_type": 2,
        "schema_type": "array",
        "schema_system": "labels",
        "schema_items": "string",
        "component_type": "AUTO_COMPLETE_MANY"
      }
    ],
    "selected_fields": [
      {
        "field_name": "summary",
        "required": true,
        "predefined": false,
        "display_name": "Summary",
        "field_type": 1,
        "schema_type": "string",
        "schema_system": "summary",
        "component_type": "INPUT_TEXT"
      },
      {
        "field_name": "reporter",
        "required": true,
        "predefined": false,
        "display_name": "Reporter",
        "field_type": 1,
        "schema_type": "user",
        "schema_system": "reporter",
        "component_type": "AUTO_COMPLETE_SINGLE"
      }
    ]
  },
  "issue_type": [
    {
      "label": "Story",
      "selected": true,
      "value": "10001"
    },
    {
      "label": "Task",
      "selected": false,
      "value": "10002"
    },
    {
      "label": "Bug",
      "selected": false,
      "value": "10003"
    },
    {
      "label": "Epik",
      "selected": false,
      "value": "10004"
    }
  ],
  "project": [
    {
      "label": "BernaPO",
      "value": "BER",
      "selected": false
    },
    {
      "label": "Kartal",
      "value": "KAR",
      "selected": true
    },
    {
      "label": "SenaEroğlu",
      "value": "SEN",
      "selected": false
    }
  ]
}
```

***

### Response

The response will contain the updated Jira issue settings for the project.

#### Example Response:

```json
{
  "assignee": {
    "label": "furkan kartal",
    "value": "62108f3a2fd2470071cc1e79"
  },
  "issue_tracker_fields": {
    "fields": [
      {
        "field_name": "description",
        "required": false,
        "predefined": false,
        "display_name": "Description",
        "field_type": 1,
        "schema_type": "string",
        "schema_system": "description",
        "component_type": "INPUT_TEXT_AREA"
      },
      {
        "field_name": "customfield_10021",
        "required": false,
        "predefined": false,
        "display_name": "Flagged",
        "field_type": 2,
        "schema_type": "array",
        "schema_items": "option",
        "component_type": "SELECT_MANY_MENU",
        "allowed_values": [
          {
            "label": "Impediment",
            "value": "10019"
          }
        ]
      },
      {
        "field_name": "labels",
        "required": false,
        "predefined": false,
        "display_name": "Labels",
        "field_type": 2,
        "schema_type": "array",
        "schema_system": "labels",
        "schema_items": "string",
        "component_type": "AUTO_COMPLETE_MANY"
      }
    ],
    "selected_fields": [
      {
        "field_name": "summary",
        "required": true,
        "predefined": false,
        "display_name": "Summary",
        "field_type": 1,
        "schema_type": "string",
        "schema_system": "summary",
        "component_type": "INPUT_TEXT"
      },
      {
        "field_name": "reporter",
        "required": true,
        "predefined": false,
        "display_name": "Reporter",
        "field_type": 1,
        "schema_type": "user",
        "schema_system": "reporter",
        "component_type": "AUTO_COMPLETE_SINGLE"
      }
    ]
  },
  "issue_type": [
    {
      "label": "Story",
      "selected": true,
      "value": "10001"
    },
    {
      "label": "Task",
      "selected": false,
      "value": "10002"
    },
    {
      "label": "Bug",
      "selected": false,
      "value": "10003"
    },
    {
      "label": "Epik",
      "selected": false,
      "value": "10004"
    }
  ],
  "project": [
    {
      "label": "BernaPO",
      "value": "BER",
      "selected": false
    },
    {
      "label": "Kartal",
      "value": "KAR",
      "selected": true
    },
    {
      "label": "SenaEroğlu",
      "value": "SEN",
      "selected": false
    }
  ]
}
```

***

### Error Codes

| HTTP Code | Error Code              | Description                                                |
| --------- | ----------------------- | ---------------------------------------------------------- |
| `400`     | `INVALID_PROJECT_ID`    | The provided project ID is invalid.                        |
| `403`     | `ACCESS_DENIED`         | The user does not have access to the specified project.    |
| `404`     | `PROJECT_NOT_FOUND`     | The project with the specified ID does not exist.          |
| `500`     | `INTERNAL_SERVER_ERROR` | An unexpected error occurred while updating Jira settings. |

***

### Example Request

#### cURL Example

```bash
curl --location --request PUT "https://testinium.io/Testinium.RestApi/api/projects/{projectId}/plugins/jira" \
--header 'Authorization: Bearer <your_access_token>' \
--header 'Content-Type: application/json' \
--data-raw '{
  "assignee": {
    "label": "furkan kartal",
    "value": "62108f3a2fd2470071cc1e79"
  },
  "issue_tracker_fields": {
    "fields": [
      {
        "field_name": "description",
        "required": false,
        "predefined": false,
        "display_name": "Description",
        "field_type": 1,
        "schema_type": "string",
        "schema_system": "description",
        "component_type": "INPUT_TEXT_AREA"
      },
      {
        "field_name": "customfield_10021",
        "required": false,
        "predefined": false,
        "display_name": "Flagged",
        "field_type": 2,
        "schema_type": "array",
        "schema_items": "option",
        "component_type": "SELECT_MANY_MENU",
        "allowed_values": [
          {
            "label": "Impediment",
            "value": "10019"
          }
        ]
      },
      {
        "field_name": "labels",
        "required": false,
        "predefined": false,
        "display_name": "Labels",
        "field_type": 2,
        "schema_type": "array",
        "schema_system": "labels",
        "schema_items": "string",
        "component_type": "AUTO_COMPLETE_MANY"
      }
    ],
    "selected_fields": [
      {
        "field_name": "summary",
        "required": true,
        "predefined": false,
        "display_name": "Summary",
        "field_type": 1,
        "schema_type": "string",
        "schema_system": "summary",
        "component_type": "INPUT_TEXT"
      },
      {
        "field_name": "reporter",
        "required": true,
        "predefined": false,
        "display_name": "Reporter",
        "field_type": 1,
        "schema_type": "user",
        "schema_system": "reporter",
        "component_type": "AUTO_COMPLETE_SINGLE"
      }
    ]
  },
  "issue_type": [
    {
      "label": "Story",
      "selected": true,
      "value": "10001"
    },
    {
      "label": "Task",
      "selected": false,
      "value": "10002"
    },
    {
      "label": "Bug",
      "selected": false,
      "value": "10003"
    },
    {
      "label": "Epik",
      "selected": false,
      "value": "10004"
    }
  ],
  "project": [
    {
      "label": "BernaPO",
      "value": "BER",
      "selected": false
    },
    {
      "label": "Kartal",
      "value": "KAR",
      "selected": true
    },
    {
      "label": "SenaEroğlu",
      "value": "SEN",
      "selected": false
    }
  ]
}'
```
