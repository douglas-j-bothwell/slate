# /COLLECTORS/{UUID}/MOOBS
## ***POST***

**Summary:** Update MOOB status (updateMoob)

**Description:**

### HTTP Request
`***POST*** /collectors/{uuid}/moobs`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| uuid | path | The hostname and optionally the instance name of the collector if sepecified, separated by colons, e.g localhost::default | Yes | string |
| payload | body | List of fully qualified moobs to alter status of | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |
