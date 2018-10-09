# /EVENTS/HEAT
## ***GET***

**Summary:** Calculate the anomaly heat based on input filters

**Description:**

### HTTP Request
`***GET*** /events/heat`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| start | query | The starting search time | No | number |
| end | query | The ending search time | No | number |
| points | query | A list of (moobel, source) maps to filter against | No | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 401 | Unauthorized |
