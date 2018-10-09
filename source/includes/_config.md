# /CONFIG
## ***GET***

**Summary:** Get config from ZooKeeper

### HTTP Request
`***GET*** /config`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| key | query | The key (path) to fetch from ZooKeeper | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters or the input path does not exist in ZooKeeper |
| 401 | Unauthorized |
| 500 | Server error |

## ***POST***

**Summary:** Set config in ZooKeeper

### HTTP Request
`***POST*** /config`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| payload | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 401 | Unauthorized |
| 500 | Server error |

# /SESSIONS
## ***POST***

**Summary:** Handles a POST for a web login request

### HTTP Request
`***POST*** /sessions`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successful login request |
| 400 | Invalid parameters |
| 401 | Unauthenticated |
| 405 | Validation exception |
