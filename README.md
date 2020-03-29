<h1 id="analytic-toolkit-rest-api">Analytic Toolkit REST API v1.0.0</h1>

> Scroll down for example requests and responses.

Base URLs:

* <a href="http://localhost:8080/v1">http://localhost:8080/v1</a>

 License: Apache License 2.0

<h1 id="analytic-toolkit-rest-api-estimator">estimator</h1>

## get status

<a id="opIdget status"></a>

`GET /estimator/status/summary`

*Return the current status computed from all estimators*

> Example responses

> 200 Response

```json
{
  "timeslot": 0,
  "status": "BaU"
}
```

<h3 id="get-status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorSummary](#schemaestimatorsummary)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get all status details

<a id="opIdget all status details"></a>

`GET /estimator/status/details`

*Detailed status of all estimators*

<h3 id="get-all-status-details-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the estimator to retrieve|

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "name": "string",
    "tag": "string"
  }
]
```

<h3 id="get-all-status-details-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetailList](#schemaestimatordetaillist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get status details by id

<a id="opIdget status details by id"></a>

`GET /estimator/status/details/{Id}`

*Detailed state for a specific estimator*

<h3 id="get-status-details-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the estimator to retrieve|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}
```

<h3 id="get-status-details-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetail](#schemaestimatordetail)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get estimator paramaters

<a id="opIdget estimator paramaters"></a>

`GET /estimator/params`

*Get the ARIMA parameters used by the estimators*

> Example responses

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}
```

<h3 id="get-estimator-paramaters-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetail](#schemaestimatordetail)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## update estimator parameters

<a id="opIdupdate estimator parameters"></a>

`PUT /estimator/params`

*Update the ARIMA parameters used by the estimators*

> Body parameter

```json
{
  "P": 0,
  "D": 0,
  "Q": 0
}
```

<h3 id="update-estimator-parameters-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ArimaParameters](#schemaarimaparameters)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}
```

<h3 id="update-estimator-parameters-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetail](#schemaestimatordetail)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get estimator threads

<a id="opIdget estimator threads"></a>

`GET /estimator/threads`

*Get the number of threads used by ARIMA estimators*

> Example responses

> 200 Response

```json
0
```

<h3 id="get-estimator-threads-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|integer|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## update estimator threads

<a id="opIdupdate estimator threads"></a>

`PUT /estimator/threads`

*Update the number of threads used by ARIMA estimators*

> Body parameter

```json
0
```

<h3 id="update-estimator-threads-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|integer(int32)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}
```

<h3 id="update-estimator-threads-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorDetail](#schemaestimatordetail)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-nodes">nodes</h1>

## get all nodes

<a id="opIdget all nodes"></a>

`GET /nodes`

*Return list of nodes currently managed*

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="get-all-nodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## manage new node

<a id="opIdmanage new node"></a>

`POST /nodes`

*Manage a new node*

> Body parameter

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="manage-new-node-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Node](#schemanode)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="manage-new-node-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get node by id

<a id="opIdget node by id"></a>

`GET /nodes/{Id}`

*Detailed information for a specific node*

<h3 id="get-node-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node to retrieve|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="get-node-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## update node by id

<a id="opIdupdate node by id"></a>

`PUT /nodes/{Id}`

*Update information for a specific node {Id}*

> Body parameter

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="update-node-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node to update|
|body|body|[Node](#schemanode)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="update-node-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## delete node by id

<a id="opIddelete node by id"></a>

`DELETE /nodes/{Id}`

*Remove node {id} from the managed nodes*

<h3 id="delete-node-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node to delete|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="delete-node-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## ignore a node

<a id="opIdignore a node"></a>

`POST /nodes/{Id}/ignore`

*If set to true, keep node {id} tracked but do not consider for the estimation.*

> Body parameter

```json
true
```

<h3 id="ignore-a-node-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node|
|body|body|boolean|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="ignore-a-node-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-use-cases">use-cases</h1>

## get all use-cases

<a id="opIdget all use-cases"></a>

`GET /use-cases`

*Return list of use-cases currently managed*

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="get-all-use-cases-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## manage a new use-case

<a id="opIdmanage a new use-case"></a>

`POST /use-cases`

*Manage a new use-case*

> Body parameter

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="manage-a-new-use-case-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Node](#schemanode)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]
```

<h3 id="manage-a-new-use-case-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeList](#schemanodelist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get use-case by id

<a id="opIdget use-case by id"></a>

`GET /use-cases/{Id}`

*Detailed information for a specific use-case*

<h3 id="get-use-case-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the use-case to retrieve|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="get-use-case-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## update use-case

<a id="opIdupdate use-case"></a>

`PUT /use-cases/{Id}`

*Update information for a specific use-case {Id}*

> Body parameter

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="update-use-case-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the use-case to update|
|body|body|[Node](#schemanode)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="update-use-case-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## delete use-case

<a id="opIddelete use-case"></a>

`DELETE /use-cases/{Id}`

*Remove use-case {id} from the managed use-cases*

<h3 id="delete-use-case-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the use-case to delete|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="delete-use-case-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-history">history</h1>

## get history

<a id="opIdget history"></a>

`GET /history`

*Return history of all nodes currently managed*

> Example responses

> 200 Response

```json
"string"
```

<h3 id="get-history-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|string|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get history by id

<a id="opIdget history by id"></a>

`GET /history/{Id}`

*Return history for the given node Id*

<h3 id="get-history-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node to retrieve|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="get-history-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## realign history for all nodes

<a id="opIdrealign history for all nodes"></a>

`POST /history/realign`

*Reread history from input data, adapt and store them in local history for all nodes*

> Example responses

> 200 Response

```json
"string"
```

<h3 id="realign-history-for-all-nodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|string|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## realing history for node id

<a id="opIdrealing history for node id"></a>

`GET /history/realign/{Id}`

*Reread history from input data, adapt and store them in local history for a given node Id*

<h3 id="realing-history-for-node-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The Id of the node to realign history|

> Example responses

> 200 Response

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}
```

<h3 id="realing-history-for-node-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Node](#schemanode)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get minimum timeslots

<a id="opIdget minimum timeslots"></a>

`GET /history/ts-min`

*Return minimum number of timeslots to populate local history*

> Example responses

> 200 Response

```json
0
```

<h3 id="get-minimum-timeslots-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|integer|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get maximum timeslots

<a id="opIdget maximum timeslots"></a>

`GET /history/ts-max`

*Return maximum number of timeslots to populate local history*

> Example responses

> 200 Response

```json
0
```

<h3 id="get-maximum-timeslots-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|integer|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get autorefresh

<a id="opIdget autorefresh"></a>

`GET /history/autorefresh`

*Return the time interval between consecutive data captures*

> Example responses

> 200 Response

```json
0
```

<h3 id="get-autorefresh-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|integer|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-version">version</h1>

## get version

<a id="opIdget version"></a>

`GET /version`

*Return the ATk software version*

> Example responses

> 200 Response

```json
"string"
```

<h3 id="get-version-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|string|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSestimatordetail">EstimatorDetail</h2>

<a id="schemaestimatordetail"></a>

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|true|none|none|
|name|string|false|none|none|
|tag|string|false|none|none|

<h2 id="tocSestimatordetaillist">EstimatorDetailList</h2>

<a id="schemaestimatordetaillist"></a>

```json
[
  {
    "id": 0,
    "name": "string",
    "tag": "string"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[EstimatorDetail](#schemaestimatordetail)]|false|none|none|

<h2 id="tocSnodelist">NodeList</h2>

<a id="schemanodelist"></a>

```json
[
  {
    "node-id": "string",
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": "string"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Node](#schemanode)]|false|none|none|

<h2 id="tocSnode">Node</h2>

<a id="schemanode"></a>

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|node-id|string|true|none|none|
|tags|[string]|false|none|none|
|tracked|boolean|false|none|none|
|use-case|string|false|none|none|

<h2 id="tocSusecaselist">UseCaseList</h2>

<a id="schemausecaselist"></a>

```json
[
  {
    "uc-id": "string",
    "tags": [
      "string"
    ],
    "adaptation": "string",
    "bau": {
      "samples": 0,
      "threshold": 0,
      "threshold-type": "string"
    },
    "warning": {
      "samples": 0,
      "hysteresis": "string"
    }
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[UseCase](#schemausecase)]|false|none|none|

<h2 id="tocSusecase">UseCase</h2>

<a id="schemausecase"></a>

```json
{
  "uc-id": "string",
  "tags": [
    "string"
  ],
  "adaptation": "string",
  "bau": {
    "samples": 0,
    "threshold": 0,
    "threshold-type": "string"
  },
  "warning": {
    "samples": 0,
    "hysteresis": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uc-id|string|true|none|none|
|tags|[string]|false|none|none|
|adaptation|string|false|none|none|
|bau|object|false|none|none|
|» samples|integer(int32)|false|none|none|
|» threshold|integer(int32)|false|none|none|
|» threshold-type|string|false|none|none|
|warning|object|false|none|none|
|» samples|integer(int32)|false|none|none|
|» hysteresis|string|false|none|none|

<h2 id="tocSestimatorsummary">EstimatorSummary</h2>

<a id="schemaestimatorsummary"></a>

```json
{
  "timeslot": 0,
  "status": "BaU"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|timeslot|integer(int64)|false|none|none|
|status|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|status|BaU|
|status|Warn|
|status|Alarm|
|status|Undefined|

<h2 id="tocSarimaparameters">ArimaParameters</h2>

<a id="schemaarimaparameters"></a>

```json
{
  "P": 0,
  "D": 0,
  "Q": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|P|integer(int64)|false|none|none|
|D|integer(int64)|false|none|none|
|Q|integer(int64)|false|none|none|

<h2 id="tocSerror">Error</h2>

<a id="schemaerror"></a>

```json
{
  "code": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int32)|true|none|none|
|message|string|true|none|none|

