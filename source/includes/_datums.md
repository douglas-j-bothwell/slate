# /DATUMS
## ***POST***

**Summary:** Add datum (addDatum)

**Description:**

### HTTP Request
`***POST*** /datums`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| payload | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |

## ***GET***

**Summary:** Get the datums (getDataSeries)

**Description:** Searches the database for data based on input filters

### HTTP Request
`***GET*** /datums`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| fully_qualified_moob | query | The full name of the moob to query against, namespace:mar:moob | Yes | string |
| metric | query | The metric to search against | Yes | string |
| source | query | Search for data gathered from this source, e.g localhost | Yes | string |
| granularity | query | The datum granularity to search, raw, second, minute, hour, etc | Yes | string |
| key | query | Key used to identify data, for instance /dev for a metric diskStats | No | string |
| start_time | query | Search for data occuring on or after start_time, defaults to an hour ago | No | number |
| end_time | query | Search for data occuring before end_time, defaults to now | No | number |
| limit | query | Limit of number of datums to return | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |
