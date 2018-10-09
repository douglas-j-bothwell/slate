# /COLLECTORS
## ***GET***

**Summary:**

**Description:** If a query param is provided, it searches for a collector with the specified name. If not, it provides info on each collector.

### HTTP Request
`***GET*** /collectors`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| query | query | The search query | No | string |
| show_overview | query | Flag indicating that user wants collector overiew | No | boolean |
| show_details | query | Flag indicating that user wants collector details | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |
