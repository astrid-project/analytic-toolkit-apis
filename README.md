<!-- Generator: Widdershins v4.0.0 -->

<h1 id="analytic-toolkit-rest-api">Analytic Toolkit REST API v1.0.0</h1>

> Scroll down for example requests and responses.

Base URLs:

* <a href="http://localhost:8080/v1">http://localhost:8080/v1</a>

 License: Apache License 2.0

<h1 id="analytic-toolkit-rest-api-estimator">estimator</h1>

## get estimator parameters

<a id="opIdget estimator parameters"></a>

`GET /estimator/params`

*Get the ARIMA parameters used by the estimators*

> Example responses

> 200 Response

```json
{
  "P": 5,
  "D": 1,
  "Q": 0
}
```

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="get-estimator-parameters-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[ArimaParameters](#schemaarimaparameters)|
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

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="update-estimator-parameters-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
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
{
  "threads": 8
}
```

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
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
{
  "threads": 12
}
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
    "timeslot": 0,
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": [
      {
        "id": "string",
        "status": "BaU"
      }
    ]
  }
]
```

<h3 id="get-all-nodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeStatusList](#schemanodestatuslist)|
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
  "use-case": [
    "string"
  ]
}
```

<h3 id="manage-new-node-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[NodeConfig](#schemanodeconfig)|true|Optional description in *Markdown*|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="manage-new-node-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## delete all use ndoes

<a id="opIddelete all use ndoes"></a>

`DELETE /nodes`

*Remove all nodes from the list of managed nodes*

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="delete-all-use-ndoes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## filter nodes by status

<a id="opIdfilter nodes by status"></a>

`GET /nodes/status`

*Get list of nodes having the given status*

<h3 id="filter-nodes-by-status-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|status|query|[Status](#schemastatus)|true|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|status|BaU|
|status|Warn|
|status|Alarm|
|status|Undefined|

> Example responses

> 200 Response

```json
[
  {
    "node-id": "string",
    "timeslot": 0,
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": [
      {
        "id": "string",
        "status": "BaU"
      }
    ]
  }
]
```

<h3 id="filter-nodes-by-status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeStatusList](#schemanodestatuslist)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get summarized status

<a id="opIdget summarized status"></a>

`GET /nodes/summarizedstatus`

*Return the worst status across all nodes and use-cases*

> Example responses

> 200 Response

```json
{
  "timeslot": 0,
  "status": "BaU"
}
```

<h3 id="get-summarized-status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodesSummarizedStatus](#schemanodessummarizedstatus)|

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
  "timeslot": 0,
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": [
    {
      "id": "string",
      "status": "BaU"
    }
  ]
}
```

<h3 id="get-node-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeStatus](#schemanodestatus)|
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
  "use-case": [
    "string"
  ]
}
```

<h3 id="update-node-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the node to update|
|body|body|[NodeConfig](#schemanodeconfig)|true|Optional description in *Markdown*|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="update-node-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
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

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="delete-node-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
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

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="ignore-a-node-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
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

<h3 id="get-all-use-cases-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCaseList](#schemausecaselist)|
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

<h3 id="manage-a-new-use-case-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UseCase](#schemausecase)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

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

<h3 id="manage-a-new-use-case-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## delete all use cases

<a id="opIddelete all use cases"></a>

`DELETE /use-cases`

*Remove all use-cases from the managed use-cases*

> Example responses

> 200 Response

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

<h3 id="delete-all-use-cases-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
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

<h3 id="get-use-case-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
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

<h3 id="update-use-case-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the use-case to update|
|body|body|[UseCase](#schemausecase)|true|Optional description in *Markdown*|

> Example responses

> 200 Response

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

<h3 id="update-use-case-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## delete use case

<a id="opIddelete use case"></a>

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

<h3 id="delete-use-case-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-history">history</h1>

## get history

<a id="opIdget history"></a>

`GET /history`

*Return history for all use-case currently managed*

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

*Return history for the given use-case Id*

<h3 id="get-history-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The id of the use-case to retrieve|

> Example responses

> 200 Response

```json
"string"
```

<h3 id="get-history-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|string|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## realign history for all use-cases

<a id="opIdrealign history for all use-cases"></a>

`POST /history/realign`

*Reread history from input data, adapt and store them in local history for all use-cases*

> Example responses

> 200 Response

```json
"string"
```

<h3 id="realign-history-for-all-use-cases-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|string|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## realign history for use-case id

<a id="opIdrealign history for use-case id"></a>

`POST /history/realign/{Id}`

*Reread history from input data, adapt and store them in local history for a given use-case Id*

<h3 id="realign-history-for-use-case-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|Id|path|string|true|The Id of the use-case to realign history|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="realign-history-for-use-case-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
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

<h2 id="tocS_EstimatorDetail">EstimatorDetail</h2>
<!-- backwards compatibility -->
<a id="schemaestimatordetail"></a>
<a id="schema_EstimatorDetail"></a>
<a id="tocSestimatordetail"></a>
<a id="tocsestimatordetail"></a>

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

<h2 id="tocS_NodeStatusList">NodeStatusList</h2>
<!-- backwards compatibility -->
<a id="schemanodestatuslist"></a>
<a id="schema_NodeStatusList"></a>
<a id="tocSnodestatuslist"></a>
<a id="tocsnodestatuslist"></a>

```json
[
  {
    "node-id": "string",
    "timeslot": 0,
    "tags": [
      "string"
    ],
    "tracked": true,
    "use-case": [
      {
        "id": "string",
        "status": "BaU"
      }
    ]
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[NodeStatus](#schemanodestatus)]|false|none|none|

<h2 id="tocS_NodeStatus">NodeStatus</h2>
<!-- backwards compatibility -->
<a id="schemanodestatus"></a>
<a id="schema_NodeStatus"></a>
<a id="tocSnodestatus"></a>
<a id="tocsnodestatus"></a>

```json
{
  "node-id": "string",
  "timeslot": 0,
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": [
    {
      "id": "string",
      "status": "BaU"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|node-id|string|true|none|none|
|timeslot|integer(int32)|false|none|none|
|tags|[string]|false|none|none|
|tracked|boolean|false|none|none|
|use-case|[object]|false|none|none|
|» id|string|false|none|none|
|» status|[Status](#schemastatus)|false|none|none|

<h2 id="tocS_NodeConfig">NodeConfig</h2>
<!-- backwards compatibility -->
<a id="schemanodeconfig"></a>
<a id="schema_NodeConfig"></a>
<a id="tocSnodeconfig"></a>
<a id="tocsnodeconfig"></a>

```json
{
  "node-id": "string",
  "tags": [
    "string"
  ],
  "tracked": true,
  "use-case": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|node-id|string|true|none|none|
|tags|[string]|false|none|none|
|tracked|boolean|false|none|none|
|use-case|[string]|false|none|none|

<h2 id="tocS_UseCaseList">UseCaseList</h2>
<!-- backwards compatibility -->
<a id="schemausecaselist"></a>
<a id="schema_UseCaseList"></a>
<a id="tocSusecaselist"></a>
<a id="tocsusecaselist"></a>

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

<h2 id="tocS_UseCase">UseCase</h2>
<!-- backwards compatibility -->
<a id="schemausecase"></a>
<a id="schema_UseCase"></a>
<a id="tocSusecase"></a>
<a id="tocsusecase"></a>

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

<h2 id="tocS_NodesSummarizedStatus">NodesSummarizedStatus</h2>
<!-- backwards compatibility -->
<a id="schemanodessummarizedstatus"></a>
<a id="schema_NodesSummarizedStatus"></a>
<a id="tocSnodessummarizedstatus"></a>
<a id="tocsnodessummarizedstatus"></a>

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
|status|[Status](#schemastatus)|false|none|none|

<h2 id="tocS_ArimaParameters">ArimaParameters</h2>
<!-- backwards compatibility -->
<a id="schemaarimaparameters"></a>
<a id="schema_ArimaParameters"></a>
<a id="tocSarimaparameters"></a>
<a id="tocsarimaparameters"></a>

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

<h2 id="tocS_Status">Status</h2>
<!-- backwards compatibility -->
<a id="schemastatus"></a>
<a id="schema_Status"></a>
<a id="tocSstatus"></a>
<a id="tocsstatus"></a>

```json
"BaU"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|BaU|
|*anonymous*|Warn|
|*anonymous*|Alarm|
|*anonymous*|Undefined|

<h2 id="tocS_Error">Error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "code": "500",
  "message": "Internal application error"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int32)|true|none|none|
|message|string|true|none|none|

