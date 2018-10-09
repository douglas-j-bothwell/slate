# /COLLECTORS/TAR
## ***GET***

**Summary:** Returns a bash command to download the collector (collectorDownload)

**Description:** Returns a bash command to download the collector

### HTTP Request
`***GET*** /collectors/tar`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| platform | query | The platform the collector is running on e.g. mac/linux/windows | Yes | string |
| instance | query | The instance name of the downloaded collector | Yes | string |
| moobs | query | The list of moobs we want the collector to run e.g. ['aws', 'url'] | Yes | list |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Returned with a bash command to download the collector |
| 400 | Invalid parameters |
| 405 | Validation exception |
