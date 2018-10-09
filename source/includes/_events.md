# /EVENTS
## ***POST***

**Summary:** Send event (sendToMooms)

**Description:**

### HTTP Request
`***POST*** /events`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| payload | body | Event to be sent | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |

## ***GET***

**Summary:** Get the event overview (getAnomalyOverview)

**Description:**

### HTTP Request
`***GET*** /events`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| start | query | Starting time for search | No | number |
| end | query | Ending time for search | No | number |
| sources | query | List of sources to filter on | No | string |
| moobs | query | List of moobs to filter on | No | string |
| types | query | List of sources to filter on | No | string |
| severities | query | List of severities to filter on | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |
