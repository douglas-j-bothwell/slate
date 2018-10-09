# /DATUMS/METRICS
## ***GET***

**Summary:** Get a list of running metrics, optionally searching with regex against input fields

### HTTP Request
`***GET*** /datums/metrics`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| fully_qualified_moob | query | The fully qualified moob to query against | No | string |
| metric | query | The metric to query against | No | string |
| source | query | The source to query against | No | string |
| key | query | The key to query against | No | string |
| tags | query | The tags to query against | No | string |
| limit | query | The max number of items to return | No | number |
| sory_by | query | How to sort the results (alphabetically or by number of datums) | No | string |
| direction | query | Sort ascending or descending | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Bad input |
| 401 | Unauthorized |

## ***POST***

**Summary:** Restarts the input metric

### HTTP Request
`***POST*** /datums/metrics`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| payload | body | Restart payload | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Bad input |
| 401 | Unauthorized |
