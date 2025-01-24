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

```json
[
    {
        "band_width_name": "Wifi",
        "read_band_width_limit": 307200000,
        "write_band_width_limit": 307200000,
        "code": "WIFI"
    },
    {
        "band_width_name": "Internet(Unlimited)",
        "read_band_width_limit": 307200000,
        "write_band_width_limit": 307200000,
        "code": "INTERNET_UNLIMITED"
    },
    {
        "band_width_name": "3G-Good",
        "read_band_width_limit": 870400,
        "write_band_width_limit": 870400,
        "code": "THREE_G_GOOD"
    },
    {
        "band_width_name": "3G-Normal",
        "read_band_width_limit": 798720,
        "write_band_width_limit": 798720,
        "code": "THREE_G_NORMAL"
    },
    {
        "band_width_name": "3G-Poor",
        "read_band_width_limit": 798720,
        "write_band_width_limit": 798720,
        "code": "THREE_G_POOR"
    },
    {
        "band_width_name": "LTE",
        "read_band_width_limit": 307200000,
        "write_band_width_limit": 307200000,
        "code": "LTE"
    },
    {
        "band_width_name": "Cable",
        "read_band_width_limit": 6291456,
        "write_band_width_limit": 6291456,
        "code": "CABLE"
    },
    {
        "band_width_name": "DSL",
        "read_band_width_limit": 2097152,
        "write_band_width_limit": 2097152,
        "code": "DSL"
    },
    {
        "band_width_name": "Edge-Good",
        "read_band_width_limit": 256000,
        "write_band_width_limit": 256000,
        "code": "EDGE_GOOD"
    },
    {
        "band_width_name": "Edge-Normal",
        "read_band_width_limit": 245760,
        "write_band_width_limit": 245760,
        "code": "EDGE_NORMAL"
    },
    {
        "band_width_name": "Edge-Poor",
        "read_band_width_limit": 245760,
        "write_band_width_limit": 245760,
        "code": "EDGE_POOR"
    }
]
```

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

### Example Request

```bash
curl --location --request GET "https://testinium.io/Testinium.RestApi/api/enums/bandWidthTypes" \
--header 'Authorization: Bearer <your_access_token>'
```
