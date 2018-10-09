# /USERS/CURRENT
## ***GET***

**Summary:** Handles a GET for user info

### HTTP Request
`***GET*** /users/current`

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 401 | Unauthorized |
| 500 | Server error |

# /PROPERTIES/CURRENT
## ***GET***

**Summary:** Handles a GET for the current user's properties

### HTTP Request
`***GET*** /properties/current`

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 401 | Unauthorized |
| 500 | Server error |

## ***POST***

**Summary:** Set the current user's properties

**Description:**

### HTTP Request
`***POST*** /properties/current`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| payload | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 400 | Invalid parameters |
| 401 | Unauthorized |
| 500 | Server error |
