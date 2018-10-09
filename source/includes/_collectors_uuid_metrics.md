# /COLLECTORS/{UUID}/METRICS
## ***GET***

**Summary:** Load metric config

**Description:**

### HTTP Request
`***GET*** /collectors/{uuid}/metrics`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| uuid | path | The hostname and optionally the instance name of the collector if sepecified, separated by colons, e.g localhost::default | Yes | string |
| fully_qualified_moob | query | The (moob : metric : source : key) to read | Yes | string |
| metric | query | The metric we're interested in | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |

## ***POST***

**Summary:** Updated metric config, or restart a metric in the config.

**Description:**

### HTTP Request
`***POST*** /collectors/{uuid}/metrics`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| uuid | path | UUID of the collector | Yes | string |
| payload | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successfully restarted |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |
