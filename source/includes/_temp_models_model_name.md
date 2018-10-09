# /TEMP/MODELS/{MODEL_NAME}
## ***GET***

**Summary:** Sends back a model marked as completed or incomplete

**Description:**

### HTTP Request
`***GET*** /temp/models/{model_name}`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| model_name | path | The name of the model to retrieve. Provided in the url | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 401 | Unauthorized |
