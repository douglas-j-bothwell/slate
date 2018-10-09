# /DATUMS/GRANULARITIES
## ***GET***

**Summary:** Get the granularities (getGranularities)

**Description:**

### HTTP Request
`***GET*** /datums/granularities`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| source | query | The source to query against | Yes | string |
| fully_qualified_moob | query | The moob to query against | Yes | string |
| metric | query | The metric to query against | Yes | string |
| key | query | The key to query against | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |
