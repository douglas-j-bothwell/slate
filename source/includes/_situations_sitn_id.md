# /SITUATIONS/{SITN_ID}
## ***GET***

**Summary:** Get AIOps situation events (getSituationEvents)

**Description:** Get AIOps situation events

### HTTP Request
`***GET*** /situations/{sitn_id}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| sitn_id | path | The situation id | Yes | string |
| start | query | start | No | string |
| limit | query | asset | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid or no ID supplied |
