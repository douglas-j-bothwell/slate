# /MODELS
## ***GET***

**Summary:** Get a model (loadModel) or model summary (availableModels) if no parameters supplied

**Description:**

### HTTP Request
`***GET*** /models`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| model_keys | query | The metric key (moob, metric, source, key) | No | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |

## ***POST***

**Summary:** Saves a model to the database

**Description:**

### HTTP Request
`***POST*** /models`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |
