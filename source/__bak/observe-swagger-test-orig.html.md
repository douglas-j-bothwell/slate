---

title: Katana API

language_tabs:
   - shell

toc_footers:
   - <a href='#'>Sign Up for a Developer Key</a>
   - <a href='https://github.com/lavkumarv'>Documentation Powered by lav</a>

includes:
   - errors

search: true

---

# Introduction

This is a rest version of the Katana api

**Version:** 1.0.0

# Authentication

|apiKey|*API Key*|
|---|---|

# /DATUMS
## ***POST***

**Summary:** Add datum (addDatum)

**Description:**

### HTTP Request
`***POST*** /datums`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| payload | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |

## ***GET***

**Summary:** Get the datums (getDataSeries)

**Description:** Searches the database for data based on input filters

### HTTP Request
`***GET*** /datums`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| fully_qualified_moob | query | The full name of the moob to query against, namespace:mar:moob | Yes | string |
| metric | query | The metric to search against | Yes | string |
| source | query | Search for data gathered from this source, e.g localhost | Yes | string |
| granularity | query | The datum granularity to search, raw, second, minute, hour, etc | Yes | string |
| key | query | Key used to identify data, for instance /dev for a metric diskStats | No | string |
| start_time | query | Search for data occuring on or after start_time, defaults to an hour ago | No | number |
| end_time | query | Search for data occuring before end_time, defaults to now | No | number |
| limit | query | Limit of number of datums to return | No | integer |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |

# /DATUMS/METRICS
## ***GET***

**Summary:** Get a list of running metrics, optionally searching with regex against input fields

### HTTP Request
`***GET*** /datums/metrics`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| fully_qualified_moob | query | The fully qualified moob to query against | No | string |
| metric | query | The metric to query against | No | string |
| source | query | The source to query against | No | string |
| key | query | The key to query against | No | string |
| tags | query | The tags to query against | No | string |
| limit | query | The max number of items to return | No | number |
| sory_by | query | How to sort the results (alphabetically or by number of datums) | No | string |
| direction | query | Sort ascending or descending | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Bad input |
| 401 | Unauthorized |

## ***POST***

**Summary:** Restarts the input metric

### HTTP Request
`***POST*** /datums/metrics`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| payload | body | Restart payload | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Bad input |
| 401 | Unauthorized |

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

# /EVENTS/MUTE
## ***GET***

**Summary:** Get's any muted period filtered on input

**Description:**

### HTTP Request
`***GET*** /events/mute`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| start | query | The starting time of the muted period | Yes | number |
| end | query | The ending time of the muted period | Yes | number |
| reason | query | The reason for this supressed period e.g maintenance | No | string |
| moobs | query | A list of fully qualified moobs effected by this mute | No | array |
| metrics | query | A list of fully qualified metrics effected by this mute | No | array |
| keys | query | A list of fully qualified keys effected by this mute | No | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |

## ***POST***

**Summary:** Marks a period as muted (maintenance)

**Description:**

### HTTP Request
`***POST*** /events/mute`

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

# /EVENTS/SUMMARY
## ***GET***

**Summary:** Get the event summaries

**Description:**

### HTTP Request
`***GET*** /events/summary`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| start | query | The start time of the event | Yes | number |
| end | query | The end time of the event | Yes | number |
| order | query | An ordering in ascending or descending order (e.g. ASC or DESC) | No | string |
| orderBy | query | What field to order the data by | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |

# /DATUMS/GRANULARITIES
## ***GET***

**Summary:** Get the granularities (getGranularities)

**Description:**

### HTTP Request
`***GET*** /datums/granularities`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| source | query | The source to query against | Yes | string |
| fully_qualified_moob | query | The moob to query against | Yes | string |
| metric | query | The metric to query against | Yes | string |
| key | query | The key to query against | No | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid input |
| 401 | Unauthorized |

# /MARS
## ***GET***

**Summary:**

**Description:** Finds the available mars present in the directory.

### HTTP Request
`***GET*** /mars`

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |

# /LICENSE/SERVER
## ***GET***

**Summary:**

**Description:** Returns the server-side license report in json format

### HTTP Request
`***GET*** /license/server`

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 500 | File IO error |

# /LICENSE/UI
## ***GET***

**Summary:**

**Description:** Returns the ui license report in json format

### HTTP Request
`***GET*** /license/ui`

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 500 | File IO error |

# /STATUS
## ***GET***

**Summary:**

**Description:** Returns the health status of the webserver

### HTTP Request
`***GET*** /status`

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |

# /MARS/MOOBS
## ***GET***

**Summary:** Get the available moobs (findAllMoobs, getMoobs)

**Description:**

### HTTP Request
`***GET*** /mars/moobs`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body |  | No |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successful response |
| 400 | Invalid input |
| 401 | Unauthorized |

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

# /TEMP/MODELS
## ***POST***

**Summary:** Marks a period as muted (maintenance)

**Description:**

### HTTP Request
`***POST*** /temp/models`

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

# /EVENTS/HEAT
## ***GET***

**Summary:** Calculate the anomaly heat based on input filters

**Description:**

### HTTP Request
`***GET*** /events/heat`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| start | query | The starting search time | No | number |
| end | query | The ending search time | No | number |
| points | query | A list of (moobel, source) maps to filter against | No | array |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 401 | Unauthorized |

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

# /COLLECTORS/{UUID}/MOOBS
## ***POST***

**Summary:** Update MOOB status (updateMoob)

**Description:**

### HTTP Request
`***POST*** /collectors/{uuid}/moobs`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| uuid | path | The hostname and optionally the instance name of the collector if sepecified, separated by colons, e.g localhost::default | Yes | string |
| payload | body | List of fully qualified moobs to alter status of | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |

# /COLLECTORS
## ***GET***

**Summary:**

**Description:** If a query param is provided, it searches for a collector with the specified name. If not, it provides info on each collector.

### HTTP Request
`***GET*** /collectors`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| query | query | The search query | No | string |
| show_overview | query | Flag indicating that user wants collector overiew | No | boolean |
| show_details | query | Flag indicating that user wants collector details | No | boolean |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |

# /COLLECTORS/{UUID}/METRICS
## ***GET***

**Summary:** Load metric config

**Description:**

### HTTP Request
`***GET*** /collectors/{uuid}/metrics`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| uuid | path | The hostname and optionally the instance name of the collector if sepecified, separated by colons, e.g localhost::default | Yes | string |
| fully_qualified_moob | query | The (moob : metric : source : key) to read | Yes | string |
| metric | query | The metric we're interested in | Yes | string |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |

## ***POST***

**Summary:** Updated metric config, or restart a metric in the config.

**Description:**

### HTTP Request
`***POST*** /collectors/{uuid}/metrics`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| uuid | path | UUID of the collector | Yes | string |
| payload | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successfully restarted |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |

# /COLLECTORS/{UUID}/CONFIG
## ***POST***

**Summary:** Changes the log level to the caller's desired level

**Description:**

### HTTP Request
`***POST*** /collectors/{uuid}/config`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| uuid | path | The hostname and optionally the instance name of the collector if sepecified, separated by colons, e.g localhost::default | Yes | string |
| body | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Successfully changed log level |
| 400 | Invalid parameters |
| 405 | Validation exception |
| 500 | Server error during status update |

# /FEEDBACK
## ***POST***

**Summary:** Add feedback (feedback)

**Description:**

### HTTP Request
`***POST*** /feedback`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| body | body | Feedback to be added | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 405 | Validation exception |

# /SLACK
## ***POST***

**Summary:** Suppress the slackbot for a period of time

### HTTP Request
`***POST*** /slack`

**Parameters**

| Name | Located in | Description | Required | Type |
| ---- | ---------- | ----------- | -------- | ---- |
| payload | body |  | Yes |  |

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |
| 400 | Invalid parameters |
| 401 | Unauthenticated |
| 405 | Validation exception |

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

# /SESSIONS/SAML/DETAILS
## ***GET***

**Description:** Checks if SAML SSO is enabled for this instance

### HTTP Request
`***GET*** /sessions/saml/details`

**Responses**

| Code | Description |
| ---- | ----------- |
| 200 | Success |

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

<!-- Converted with the swagger-to-slate https://github.com/lavkumarv/swagger-to-slate -->
