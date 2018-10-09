# /SESSIONS/SAML/REQUEST
## ***GET***

**Description:** Prepares a SAML AuthnRequest

### HTTP Request
`***GET*** /sessions/saml/request`

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Cannot find redirect url in idp_metadata.xml |
| 500 | Server error either building the AuthnRequest or reading files |
