# /SESSIONS/SAML/RESPONSE
## ***POST***

### HTTP Request
`***POST*** /sessions/saml/response`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 302 | Redirect to login page upon successful auth |
| 401 | Not authenticated by SSO |
| 500 | Internal server error |
