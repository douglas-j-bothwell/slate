# /EVENTS/MUTE
## ***GET***

**Summary:** Get's any muted period filtered on input

**Description:**

### HTTP Request
`***GET*** /events/mute`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| start | query | The starting time of the muted period | Yes | number |
| end | query | The ending time of the muted period | Yes | number |
| reason | query | The reason for this supressed period e.g maintenance | No | string |
| moobs | query | A list of fully qualified moobs effected by this mute | No | array |
| metrics | query | A list of fully qualified metrics effected by this mute | No | array |
| keys | query | A list of fully qualified keys effected by this mute | No | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |

## ***POST***

**Summary:** Marks a period as muted (maintenance)

**Description:**

### HTTP Request
`***POST*** /events/mute`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |
