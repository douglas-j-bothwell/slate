# /MARS/ASSETS
## ***GET***

**Summary:** Load a MAR asset (loadAsset)

**Description:** Returns a MAR asset

### HTTP Request
`***GET*** /mars/assets`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| namespace | query | Namespace | No | string |
| mar | query | MAR | No | string |
| asset | query | asset | No | string |
| type | query | type | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | successful operation |
| 400 | Invalid ID supplied |

## ***POST***

**Summary:** Handles a POST that marks that something in a mar has changed.

### HTTP Request
`***POST*** /mars/assets`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| payload | body |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | The operation was successful |
| 400 | Invalid parameters |
| 401 | Unauthenticated |
| 405 | Validation exception |
