# /COLLECTORS/{UUID}/CONFIG
## ***POST***

**Summary:** Changes the log level to the caller's desired level

**Description:**

### HTTP Request
`***POST*** /collectors/{uuid}/config`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| uuid | path | The hostname and optionally the instance name of the collector if sepecified, separated by colons, e.g localhost::default | Yes | string |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successfully changed log level |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |
