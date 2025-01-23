# Get Band Width Types

Retrieves all available bandwidth types along with their associated read and write limits.

***

### Endpoint Information

* **URL**: `https://testinium.io/Testinium.RestApi/api/enums/bandWidthTypes`
* **Method**: `GET`
* **Authentication**: Required (`Bearer Token`)

***

### Path Parameters

| Parameter | Type     | Description                                                            |
| --------- | -------- | ---------------------------------------------------------------------- |
| `user`    | `Object` | The user making the request. Must have the authority `BANDWIDTH_VIEW`. |

***

### Response

{\`\[ { "band\_width\_name": "Wifi", "read\_band\_width\_limit": 307200000, "write\_band\_width\_limit": 307200000, "code": "WIFI" }, { "band\_width\_name": "Internet(Unlimited)", "read\_band\_width\_limit": 307200000, "write\_band\_width\_limit": 307200000, "code": "INTERNET\_UNLIMITED" }, { "band\_width\_name": "3G-Good", "read\_band\_width\_limit": 870400, "write\_band\_width\_limit": 870400, "code": "THREE\_G\_GOOD" }, { "band\_width\_name": "3G-Normal", "read\_band\_width\_limit": 798720, "write\_band\_width\_limit": 798720, "code": "THREE\_G\_NORMAL" }, { "band\_width\_name": "3G-Poor", "read\_band\_width\_limit": 798720, "write\_band\_width\_limit": 798720, "code": "THREE\_G\_POOR" }, { "band\_width\_name": "LTE", "read\_band\_width\_limit": 307200000, "write\_band\_width\_limit": 307200000, "code": "LTE" }, { "band\_width\_name": "Cable", "read\_band\_width\_limit": 6291456, "write\_band\_width\_limit": 6291456, "code": "CABLE" }, { "band\_width\_name": "DSL", "read\_band\_width\_limit": 2097152, "write\_band\_width\_limit": 2097152, "code": "DSL" }, { "band\_width\_name": "Edge-Good", "read\_band\_width\_limit": 256000, "write\_band\_width\_limit": 256000, "code": "EDGE\_GOOD" }, { "band\_width\_name": "Edge-Normal", "read\_band\_width\_limit": 245760, "write\_band\_width\_limit": 245760, "code": "EDGE\_NORMAL" }, { "band\_width\_name": "Edge-Poor", "read\_band\_width\_limit": 245760, "write\_band\_width\_limit": 245760, "code": "EDGE\_POOR" } ]\`}

***

### Response Fields

<table data-full-width="false"><thead><tr><th>Field</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td><code>band_width_name</code></td><td><code>String</code></td><td>The name of the bandwidth type (e.g., <code>Wifi</code>, <code>LTE</code>).</td></tr><tr><td><code>read_band_width_limit</code></td><td><code>Long</code></td><td>The read bandwidth limit (in bits per second).</td></tr><tr><td><code>write_band_width_limit</code></td><td><code>Long</code></td><td>The write bandwidth limit (in bits per second).</td></tr><tr><td><code>code</code></td><td><code>String</code></td><td>The code representing the bandwidth type (e.g., <code>WIFI</code>, <code>LTE</code>).</td></tr></tbody></table>

***

### Error Codes

| HTTP Status | Code             | Message                                                               |
| ----------- | ---------------- | --------------------------------------------------------------------- |
| 400         | `BAD_REQUEST`    | Invalid request parameters.                                           |
| 401         | `UNAUTHORIZED`   | The user is not authorized to access this resource.                   |
| 403         | `FORBIDDEN`      | The user does not have sufficient permissions to access the resource. |
| 500         | `INTERNAL_ERROR` | An internal server error occurred while processing the request.       |

#### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/enums/bandWidthTypes" \
--header 'Authorization: Bearer <your_access_token>'
```
