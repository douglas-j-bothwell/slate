# /EVENTS/SUMMARY
## ***GET***

**Summary:** Get the event summaries

**Description:**

### HTTP Request
`***GET*** /events/summary`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| start | query | The start time of the event | Yes | number |
| end | query | The end time of the event | Yes | number |
| order | query | An ordering in ascending or descending order (e.g. ASC or DESC) | No | string |
| orderBy | query | What field to order the data by | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |
