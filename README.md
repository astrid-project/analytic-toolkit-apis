<!-- Generator: Widdershins v4.0.1 -->

<h1 id="analytic-toolkit-rest-api">Analytic Toolkit REST API v2.0.0</h1>

> Scroll down for example requests and responses.

Base URLs:

* <a href="http://localhost:8080/v1">http://localhost:8080/v1</a>

 License: Apache License 2.0

<h1 id="analytic-toolkit-rest-api-nodes">nodes</h1>

create/read/update/delete operations on nodes

## get all nodes

<a id="opIdget all nodes"></a>

`GET /nodes`

*Return list of all nodes currently managed*

> Example responses

> 200 Response

```json
[
  {
    "node-id": "Genoa-Erzelli",
    "area": "Genoa",
    "type": "NTP",
    "use-case": [
      "NTP1",
      "NTP2"
    ]
  }
]
```

<h3 id="get-all-nodes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeConfigList](#schemanodeconfiglist)|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## manage new node

<a id="opIdmanage new node"></a>

`POST /nodes`

*Manage a new node identified by a new {id}*

> Body parameter

```json
{
  "node-id": "Genoa-Erzelli",
  "area": "Genoa",
  "type": "NTP",
  "use-case": [
    "NTP1",
    "NTP2"
  ]
}
```

<h3 id="manage-new-node-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[NodeConfig](#schemanodeconfig)|true|none|

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
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

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
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get node by id

<a id="opIdget node by id"></a>

`GET /nodes/{id}`

*Detailed information for a specific node {id}*

<h3 id="get-node-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The name of the node to retrieve|

> Example responses

> 200 Response

```json
{
  "node-id": "Genoa-Erzelli",
  "area": "Genoa",
  "type": "NTP",
  "use-case": [
    "NTP1",
    "NTP2"
  ]
}
```

<h3 id="get-node-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[NodeConfig](#schemanodeconfig)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## update node by name

<a id="opIdupdate node by name"></a>

`POST /nodes/{id}`

*Update information for a given node {id}*

> Body parameter

```json
{
  "node-id": "Genoa-Erzelli",
  "area": "Genoa",
  "type": "NTP",
  "use-case": [
    "NTP1",
    "NTP2"
  ]
}
```

<h3 id="update-node-by-name-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The id of the node to update|
|body|body|[NodeConfig](#schemanodeconfig)|true|none|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="update-node-by-name-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## delete node by id

<a id="opIddelete node by id"></a>

`DELETE /nodes/{id}`

*Remove node by its {id} from the managed nodes*

<h3 id="delete-node-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The name of the node to delete|

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
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-use-cases">use-cases</h1>

create/read/update/delete operations on use-cases

## get all use-cases

<a id="opIdget all use-cases"></a>

`GET /use-cases`

*Return list of use-cases currently managed*

> Example responses

> 200 Response

```json
[
  {
    "uc-id": "NTP",
    "forecast-parameters": [
      {
        "id": "NTP_volume",
        "threshold": 474
      }
    ],
    "detection-parameters": [
      {
        "id": "NTP_monlist",
        "area-detection-percentage": {
          "value": 11
        },
        "type-detection-percentage": {
          "value": 11
        },
        "area-correlation-percentage": {
          "value": 11
        },
        "type-correlation-percentage": {
          "value": 11
        },
        "threshold": 474,
        "histeresys": 3
      }
    ]
  }
]
```

<h3 id="get-all-use-cases-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCaseList](#schemausecaselist)|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## manage a new use-case

<a id="opIdmanage a new use-case"></a>

`POST /use-cases`

*Manage a new use-case identified by a new {id}*

> Body parameter

```json
{
  "uc-id": "NTP",
  "forecast-parameters": [
    {
      "id": "NTP_volume",
      "threshold": 474
    }
  ],
  "detection-parameters": [
    {
      "id": "NTP_monlist",
      "area-detection-percentage": {
        "value": 11
      },
      "type-detection-percentage": {
        "value": 11
      },
      "area-correlation-percentage": {
        "value": 11
      },
      "type-correlation-percentage": {
        "value": 11
      },
      "threshold": 474,
      "histeresys": 3
    }
  ]
}
```

<h3 id="manage-a-new-use-case-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UseCase](#schemausecase)|true|none|

> Example responses

> 200 Response

```json
{
  "uc-id": "NTP",
  "forecast-parameters": [
    {
      "id": "NTP_volume",
      "threshold": 474
    }
  ],
  "detection-parameters": [
    {
      "id": "NTP_monlist",
      "area-detection-percentage": {
        "value": 11
      },
      "type-detection-percentage": {
        "value": 11
      },
      "area-correlation-percentage": {
        "value": 11
      },
      "type-correlation-percentage": {
        "value": 11
      },
      "threshold": 474,
      "histeresys": 3
    }
  ]
}
```

<h3 id="manage-a-new-use-case-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

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
  "uc-id": "NTP",
  "forecast-parameters": [
    {
      "id": "NTP_volume",
      "threshold": 474
    }
  ],
  "detection-parameters": [
    {
      "id": "NTP_monlist",
      "area-detection-percentage": {
        "value": 11
      },
      "type-detection-percentage": {
        "value": 11
      },
      "area-correlation-percentage": {
        "value": 11
      },
      "type-correlation-percentage": {
        "value": 11
      },
      "threshold": 474,
      "histeresys": 3
    }
  ]
}
```

<h3 id="delete-all-use-cases-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get use-case by name

<a id="opIdget use-case by name"></a>

`GET /use-cases/{id}`

*Detailed information for a specific use-case by {id}*

<h3 id="get-use-case-by-name-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The id of the use-case to retrieve|

> Example responses

> 200 Response

```json
{
  "uc-id": "NTP",
  "forecast-parameters": [
    {
      "id": "NTP_volume",
      "threshold": 474
    }
  ],
  "detection-parameters": [
    {
      "id": "NTP_monlist",
      "area-detection-percentage": {
        "value": 11
      },
      "type-detection-percentage": {
        "value": 11
      },
      "area-correlation-percentage": {
        "value": 11
      },
      "type-correlation-percentage": {
        "value": 11
      },
      "threshold": 474,
      "histeresys": 3
    }
  ]
}
```

<h3 id="get-use-case-by-name-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## update use-case

<a id="opIdupdate use-case"></a>

`POST /use-cases/{id}`

*Update information for a specific use-case by {id}*

> Body parameter

```json
{
  "uc-id": "NTP",
  "forecast-parameters": [
    {
      "id": "NTP_volume",
      "threshold": 474
    }
  ],
  "detection-parameters": [
    {
      "id": "NTP_monlist",
      "area-detection-percentage": {
        "value": 11
      },
      "type-detection-percentage": {
        "value": 11
      },
      "area-correlation-percentage": {
        "value": 11
      },
      "type-correlation-percentage": {
        "value": 11
      },
      "threshold": 474,
      "histeresys": 3
    }
  ]
}
```

<h3 id="update-use-case-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The id of the use-case to update|
|body|body|[UseCase](#schemausecase)|true|none|

> Example responses

> 200 Response

```json
{
  "uc-id": "NTP",
  "forecast-parameters": [
    {
      "id": "NTP_volume",
      "threshold": 474
    }
  ],
  "detection-parameters": [
    {
      "id": "NTP_monlist",
      "area-detection-percentage": {
        "value": 11
      },
      "type-detection-percentage": {
        "value": 11
      },
      "area-correlation-percentage": {
        "value": 11
      },
      "type-correlation-percentage": {
        "value": 11
      },
      "threshold": 474,
      "histeresys": 3
    }
  ]
}
```

<h3 id="update-use-case-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## delete use case

<a id="opIddelete use case"></a>

`DELETE /use-cases/{id}`

*Remove use-case by {id} from the managed use-cases*

<h3 id="delete-use-case-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The id of the use-case to delete|

> Example responses

> 200 Response

```json
{
  "uc-id": "NTP",
  "forecast-parameters": [
    {
      "id": "NTP_volume",
      "threshold": 474
    }
  ],
  "detection-parameters": [
    {
      "id": "NTP_monlist",
      "area-detection-percentage": {
        "value": 11
      },
      "type-detection-percentage": {
        "value": 11
      },
      "area-correlation-percentage": {
        "value": 11
      },
      "type-correlation-percentage": {
        "value": 11
      },
      "threshold": 474,
      "histeresys": 3
    }
  ]
}
```

<h3 id="delete-use-case-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[UseCase](#schemausecase)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-status">status</h1>

estimator status including correlations

## get status

<a id="opIdget status"></a>

`GET /status`

*get the estimator status, including correlations*

> Example responses

> 200 Response

```json
{
  "time": 1600034400,
  "network-status": "BAU",
  "correlation-type-status": [
    {
      "use-case": "MITM",
      "correlations": [
        {
          "node-type": "PE-Routers",
          "value": "BAU"
        }
      ]
    }
  ],
  "correlation-area-status": [
    {
      "use-case": "MITM",
      "correlations": [
        {
          "area": "Turin",
          "value": "BAU"
        }
      ]
    }
  ]
}
```

<h3 id="get-status-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[FullStatus](#schemafullstatus)|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-estimator">estimator</h1>

low-level operations on the estimators settings defined for a given use-case, node and probe

## get hysteresis

<a id="opIdget hysteresis"></a>

`GET /estimator/hysteresis`

*Get the hysteresis between WARN and STATUS*

<h3 id="get-hysteresis-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|use-case|query|string|true|use-case identifier|
|node|query|string|true|node identifier|
|probe|query|string|true|probe identifier|

> Example responses

> 200 Response

```json
{
  "histeresys": 3
}
```

<h3 id="get-hysteresis-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[EstimatorHysteresisState](#schemaestimatorhysteresisstate)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## set hysteresis

<a id="opIdset hysteresis"></a>

`POST /estimator/hysteresis`

*Set the hysteresis between WARN and STATUS*

> Body parameter

```json
{
  "histeresys": 3,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}
```

<h3 id="set-hysteresis-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[EstimatorHysteresisConfig](#schemaestimatorhysteresisconfig)|true|The use-case and node.|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="set-hysteresis-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get estimator parameters

<a id="opIdget estimator parameters"></a>

`GET /estimator/params`

*Get the ARIMA parameters*

<h3 id="get-estimator-parameters-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|use-case|query|string|true|use-case identifier|
|node|query|string|true|node identifier|
|probe|query|string|true|probe identifier|

> Example responses

> 200 Response

```json
{
  "P": 5,
  "D": 1,
  "Q": 0
}
```

<h3 id="get-estimator-parameters-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[ArimaParametersState](#schemaarimaparametersstate)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## update estimator parameters

<a id="opIdupdate estimator parameters"></a>

`POST /estimator/params`

*Update the ARIMA parameters*

> Body parameter

```json
{
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C",
  "P": 5,
  "D": 1,
  "Q": 0
}
```

<h3 id="update-estimator-parameters-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ArimaParametersConfig](#schemaarimaparametersconfig)|true|none|

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
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get forecast threshold

<a id="opIdget forecast threshold"></a>

`GET /estimator/forecast-threshold`

*Get the forecast threshold*

<h3 id="get-forecast-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|use-case|query|string|true|use-case identifier|
|node|query|string|true|node identifier|
|probe|query|string|true|probe identifier|

> Example responses

> 200 Response

```json
{
  "threshold": 474
}
```

<h3 id="get-forecast-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[ThresholdValueState](#schemathresholdvaluestate)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## set forecast threshold

<a id="opIdset forecast threshold"></a>

`POST /estimator/forecast-threshold`

*Set the forecast threshold*

> Body parameter

```json
{
  "threshold": 474,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}
```

<h3 id="set-forecast-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ThresholdValueConfig](#schemathresholdvalueconfig)|true|none|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="set-forecast-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get detection threshold

<a id="opIdget detection threshold"></a>

`GET /estimator/detection-threshold`

*Get the detection threshold*

<h3 id="get-detection-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|use-case|query|string|true|use-case identifier|
|node|query|string|true|node identifier|
|probe|query|string|true|probe identifier|

> Example responses

> 200 Response

```json
{
  "threshold": 474
}
```

<h3 id="get-detection-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[ThresholdValueState](#schemathresholdvaluestate)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Set detection threshold

<a id="opIdSet detection threshold"></a>

`POST /estimator/detection-threshold`

*Set the detection threshold*

> Body parameter

```json
{
  "threshold": 474,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}
```

<h3 id="set-detection-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ThresholdValueConfig](#schemathresholdvalueconfig)|true|none|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="set-detection-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get relative per-area detection threshold

<a id="opIdget relative per-area detection threshold"></a>

`GET /estimator/area-detection-percentage`

*Get the relative per-area detection threshold*

<h3 id="get-relative-per-area-detection-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|use-case|query|string|true|use-case identifier|
|node|query|string|true|node identifier|
|probe|query|string|true|probe identifier|

> Example responses

> 200 Response

```json
{
  "value": 11
}
```

<h3 id="get-relative-per-area-detection-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[PercentageState](#schemapercentagestate)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## set relative per-area detection threshold

<a id="opIdset relative per-area detection threshold"></a>

`POST /estimator/area-detection-percentage`

*Set the relative per-area detection threshold*

> Body parameter

```json
{
  "value": 11,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}
```

<h3 id="set-relative-per-area-detection-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PercentageConfig](#schemapercentageconfig)|true|none|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="set-relative-per-area-detection-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get relative per-type detection threshold

<a id="opIdget relative per-type detection threshold"></a>

`GET /estimator/type-detection-percentage`

*Get the relative per-type detection threshold*

<h3 id="get-relative-per-type-detection-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|use-case|query|string|true|use-case identifier|
|node|query|string|true|node identifier|
|probe|query|string|true|probe identifier|

> Example responses

> 200 Response

```json
{
  "value": 11
}
```

<h3 id="get-relative-per-type-detection-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[PercentageState](#schemapercentagestate)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## set relative per-type detection threshold

<a id="opIdset relative per-type detection threshold"></a>

`POST /estimator/type-detection-percentage`

*Set the relative per-type detection threshold*

> Body parameter

```json
{
  "value": 11,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}
```

<h3 id="set-relative-per-type-detection-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PercentageConfig](#schemapercentageconfig)|true|none|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="set-relative-per-type-detection-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get relative per-area correlation threshold

<a id="opIdget relative per-area correlation threshold"></a>

`GET /estimator/area-correlation-percentage`

*Get the relative per-area correlation threshold*

<h3 id="get-relative-per-area-correlation-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|use-case|query|string|true|use-case identifier|
|node|query|string|true|node identifier|
|probe|query|string|true|probe identifier|

> Example responses

> 200 Response

```json
{
  "value": 11
}
```

<h3 id="get-relative-per-area-correlation-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[PercentageState](#schemapercentagestate)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## set relative per-area correlation threshold

<a id="opIdset relative per-area correlation threshold"></a>

`POST /estimator/area-correlation-percentage`

*Set the relative per-area correlation threshold*

> Body parameter

```json
{
  "value": 11,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}
```

<h3 id="set-relative-per-area-correlation-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PercentageConfig](#schemapercentageconfig)|true|none|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="set-relative-per-area-correlation-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get relative per-type correlation threshold

<a id="opIdget relative per-type correlation threshold"></a>

`GET /estimator/type-correlation-percentage`

*Get the relative per-type correlation threshold*

<h3 id="get-relative-per-type-correlation-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|use-case|query|string|true|use-case identifier|
|node|query|string|true|node identifier|
|probe|query|string|true|probe identifier|

> Example responses

> 200 Response

```json
{
  "value": 11
}
```

<h3 id="get-relative-per-type-correlation-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[PercentageState](#schemapercentagestate)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Set relative per-area correlation threshold

<a id="opIdSet relative per-area correlation threshold"></a>

`POST /estimator/type-correlation-percentage`

*Set the relative per-area correlation threshold*

> Body parameter

```json
{
  "value": 11,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}
```

<h3 id="set-relative-per-area-correlation-threshold-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PercentageConfig](#schemapercentageconfig)|true|none|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="set-relative-per-area-correlation-threshold-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="analytic-toolkit-rest-api-history">history</h1>

low-level operations on the estimators forecast history

## get history by use-case, node and probe

<a id="opIdget history by use-case, node and probe"></a>

`GET /history/`

*Return estimator forecast history for the given use-case, node and probe*

<h3 id="get-history-by-use-case,-node-and-probe-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|use-case|query|string|true|use-case identifier|
|node|query|string|true|node identifier|
|probe|query|string|true|probe identifier|

> Example responses

> 200 Response

```json
[
  {
    "time": 1600034400,
    "value": "BAU"
  }
]
```

<h3 id="get-history-by-use-case,-node-and-probe-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<h3 id="get-history-by-use-case,-node-and-probe-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[HistoryPoint](#schemahistorypoint)]|false|none|none|
|» time|[Timestamp](#schematimestamp)(int32)|false|none|seconds since epoch|
|» value|[Status](#schemastatus)|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|value|BAU|
|value|WARN|
|value|ALARM|
|value|UNDEFINED|

<aside class="success">
This operation does not require authentication
</aside>

## realign one estimator history

<a id="opIdrealign one estimator history"></a>

`POST /history/realign/`

*Realign the forecast history for the given use-case, node and probe*

> Body parameter

```json
{
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}
```

<h3 id="realign-one-estimator-history-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UNP-identifier](#schemaunp-identifier)|true|none|

> Example responses

> default Response

```json
{
  "code": "500",
  "message": "Internal application error"
}
```

<h3 id="realign-one-estimator-history-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|
|default|Default|Unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_NodeConfigList">NodeConfigList</h2>
<!-- backwards compatibility -->
<a id="schemanodeconfiglist"></a>
<a id="schema_NodeConfigList"></a>
<a id="tocSnodeconfiglist"></a>
<a id="tocsnodeconfiglist"></a>

```json
[
  {
    "node-id": "Genoa-Erzelli",
    "area": "Genoa",
    "type": "NTP",
    "use-case": [
      "NTP1",
      "NTP2"
    ]
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[NodeConfig](#schemanodeconfig)]|false|none|none|

<h2 id="tocS_NodeConfig">NodeConfig</h2>
<!-- backwards compatibility -->
<a id="schemanodeconfig"></a>
<a id="schema_NodeConfig"></a>
<a id="tocSnodeconfig"></a>
<a id="tocsnodeconfig"></a>

```json
{
  "node-id": "Genoa-Erzelli",
  "area": "Genoa",
  "type": "NTP",
  "use-case": [
    "NTP1",
    "NTP2"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|node-id|string|true|none|none|
|area|string|false|none|none|
|type|string|false|none|none|
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
    "uc-id": "NTP",
    "forecast-parameters": [
      {
        "id": "NTP_volume",
        "threshold": 474
      }
    ],
    "detection-parameters": [
      {
        "id": "NTP_monlist",
        "area-detection-percentage": {
          "value": 11
        },
        "type-detection-percentage": {
          "value": 11
        },
        "area-correlation-percentage": {
          "value": 11
        },
        "type-correlation-percentage": {
          "value": 11
        },
        "threshold": 474,
        "histeresys": 3
      }
    ]
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
  "uc-id": "NTP",
  "forecast-parameters": [
    {
      "id": "NTP_volume",
      "threshold": 474
    }
  ],
  "detection-parameters": [
    {
      "id": "NTP_monlist",
      "area-detection-percentage": {
        "value": 11
      },
      "type-detection-percentage": {
        "value": 11
      },
      "area-correlation-percentage": {
        "value": 11
      },
      "type-correlation-percentage": {
        "value": 11
      },
      "threshold": 474,
      "histeresys": 3
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|uc-id|string|true|none|none|
|forecast-parameters|[[ForecastParameter](#schemaforecastparameter)]|false|none|[A parameter used for forecast and its threshold]|
|detection-parameters|[[DetectionParameter](#schemadetectionparameter)]|false|none|[A parameter used for detection and its threshold, the hysteresis and its set of relative thresholds for correlation. The "area-detection-percentage" is a percentage of the detection threshold and is used to compute a, typically lower, per-area detection threshold. For every area A, ATk looks for its nodes where the resulting per-area detection threshold is exceeded.  If the percentage of these nodes in an area A exceeds the "area-correlation-percentage", then ATK decides status "WARN" for the area A, otherwise status "BAU". Similarly, the "type-detection-percentage" is a percentage of the detection threshold and is used to compute a, typically lower, per-type detection threshold. For every node type T, ATk looks for nodes where the resulting per-type detection threshold is exceeded.  If the percentage of these nodes for a type T exceeds the "type-correlation-percentage", then ATK decides status "WARN" for the type T, otherwise status "BAU".<br>]|

<h2 id="tocS_ForecastParameter">ForecastParameter</h2>
<!-- backwards compatibility -->
<a id="schemaforecastparameter"></a>
<a id="schema_ForecastParameter"></a>
<a id="tocSforecastparameter"></a>
<a id="tocsforecastparameter"></a>

```json
{
  "id": "NTP_volume",
  "threshold": 474
}

```

A parameter used for forecast and its threshold

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|string|false|none|Unique identifier of each parameter|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ThresholdValueState](#schemathresholdvaluestate)|false|none|none|

<h2 id="tocS_ThresholdValueState">ThresholdValueState</h2>
<!-- backwards compatibility -->
<a id="schemathresholdvaluestate"></a>
<a id="schema_ThresholdValueState"></a>
<a id="tocSthresholdvaluestate"></a>
<a id="tocsthresholdvaluestate"></a>

```json
{
  "threshold": 474
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|threshold|number|false|none|Absolute value of a threshold|

<h2 id="tocS_ThresholdValueConfig">ThresholdValueConfig</h2>
<!-- backwards compatibility -->
<a id="schemathresholdvalueconfig"></a>
<a id="schema_ThresholdValueConfig"></a>
<a id="tocSthresholdvalueconfig"></a>
<a id="tocsthresholdvalueconfig"></a>

```json
{
  "threshold": 474,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ThresholdValueState](#schemathresholdvaluestate)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[UNP-identifier](#schemaunp-identifier)|false|none|reusable model containing just use-case (U), node (N) and probe (P) identifier|

<h2 id="tocS_DetectionParameter">DetectionParameter</h2>
<!-- backwards compatibility -->
<a id="schemadetectionparameter"></a>
<a id="schema_DetectionParameter"></a>
<a id="tocSdetectionparameter"></a>
<a id="tocsdetectionparameter"></a>

```json
{
  "id": "NTP_monlist",
  "area-detection-percentage": {
    "value": 11
  },
  "type-detection-percentage": {
    "value": 11
  },
  "area-correlation-percentage": {
    "value": 11
  },
  "type-correlation-percentage": {
    "value": 11
  },
  "threshold": 474,
  "histeresys": 3
}

```

A parameter used for detection and its threshold, the hysteresis and its set of relative thresholds for correlation. The "area-detection-percentage" is a percentage of the detection threshold and is used to compute a, typically lower, per-area detection threshold. For every area A, ATk looks for its nodes where the resulting per-area detection threshold is exceeded.  If the percentage of these nodes in an area A exceeds the "area-correlation-percentage", then ATK decides status "WARN" for the area A, otherwise status "BAU". Similarly, the "type-detection-percentage" is a percentage of the detection threshold and is used to compute a, typically lower, per-type detection threshold. For every node type T, ATk looks for nodes where the resulting per-type detection threshold is exceeded.  If the percentage of these nodes for a type T exceeds the "type-correlation-percentage", then ATK decides status "WARN" for the type T, otherwise status "BAU".

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|object|false|none|none|
|» id|string|false|none|Unique identifier of each parameter|
|» area-detection-percentage|[PercentageState](#schemapercentagestate)|false|none|none|
|» type-detection-percentage|[PercentageState](#schemapercentagestate)|false|none|none|
|» area-correlation-percentage|[PercentageState](#schemapercentagestate)|false|none|none|
|» type-correlation-percentage|[PercentageState](#schemapercentagestate)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ThresholdValueState](#schemathresholdvaluestate)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[EstimatorHysteresisState](#schemaestimatorhysteresisstate)|false|none|The estimator waits for this number of time intervals before passing from WARN to ALARM state|

<h2 id="tocS_ArimaParametersState">ArimaParametersState</h2>
<!-- backwards compatibility -->
<a id="schemaarimaparametersstate"></a>
<a id="schema_ArimaParametersState"></a>
<a id="tocSarimaparametersstate"></a>
<a id="tocsarimaparametersstate"></a>

```json
{
  "P": 5,
  "D": 1,
  "Q": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|P|integer(int64)|false|none|none|
|D|integer(int64)|false|none|none|
|Q|integer(int64)|false|none|none|

<h2 id="tocS_ArimaParametersConfig">ArimaParametersConfig</h2>
<!-- backwards compatibility -->
<a id="schemaarimaparametersconfig"></a>
<a id="schema_ArimaParametersConfig"></a>
<a id="tocSarimaparametersconfig"></a>
<a id="tocsarimaparametersconfig"></a>

```json
{
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C",
  "P": 5,
  "D": 1,
  "Q": 0
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[UNP-identifier](#schemaunp-identifier)|false|none|reusable model containing just use-case (U), node (N) and probe (P) identifier|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[ArimaParametersState](#schemaarimaparametersstate)|false|none|none|

<h2 id="tocS_UNP-identifier">UNP-identifier</h2>
<!-- backwards compatibility -->
<a id="schemaunp-identifier"></a>
<a id="schema_UNP-identifier"></a>
<a id="tocSunp-identifier"></a>
<a id="tocsunp-identifier"></a>

```json
{
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}

```

reusable model containing just use-case (U), node (N) and probe (P) identifier

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|use-case|string|false|none|use-case identifier|
|node|string|false|none|node identifier|
|probe|string|false|none|probe identifier|

<h2 id="tocS_EstimatorHysteresisState">EstimatorHysteresisState</h2>
<!-- backwards compatibility -->
<a id="schemaestimatorhysteresisstate"></a>
<a id="schema_EstimatorHysteresisState"></a>
<a id="tocSestimatorhysteresisstate"></a>
<a id="tocsestimatorhysteresisstate"></a>

```json
{
  "histeresys": 3
}

```

The estimator waits for this number of time intervals before passing from WARN to ALARM state

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|histeresys|integer(int32)|false|none|none|

<h2 id="tocS_EstimatorHysteresisConfig">EstimatorHysteresisConfig</h2>
<!-- backwards compatibility -->
<a id="schemaestimatorhysteresisconfig"></a>
<a id="schema_EstimatorHysteresisConfig"></a>
<a id="tocSestimatorhysteresisconfig"></a>
<a id="tocsestimatorhysteresisconfig"></a>

```json
{
  "histeresys": 3,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}

```

This is EstimatorHysteresisState decorated with use-case, node and probe information.

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[EstimatorHysteresisState](#schemaestimatorhysteresisstate)|false|none|The estimator waits for this number of time intervals before passing from WARN to ALARM state|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[UNP-identifier](#schemaunp-identifier)|false|none|reusable model containing just use-case (U), node (N) and probe (P) identifier|

<h2 id="tocS_Status">Status</h2>
<!-- backwards compatibility -->
<a id="schemastatus"></a>
<a id="schema_Status"></a>
<a id="tocSstatus"></a>
<a id="tocsstatus"></a>

```json
"BAU"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|BAU|
|*anonymous*|WARN|
|*anonymous*|ALARM|
|*anonymous*|UNDEFINED|

<h2 id="tocS_FullStatus">FullStatus</h2>
<!-- backwards compatibility -->
<a id="schemafullstatus"></a>
<a id="schema_FullStatus"></a>
<a id="tocSfullstatus"></a>
<a id="tocsfullstatus"></a>

```json
{
  "time": 1600034400,
  "network-status": "BAU",
  "correlation-type-status": [
    {
      "use-case": "MITM",
      "correlations": [
        {
          "node-type": "PE-Routers",
          "value": "BAU"
        }
      ]
    }
  ],
  "correlation-area-status": [
    {
      "use-case": "MITM",
      "correlations": [
        {
          "area": "Turin",
          "value": "BAU"
        }
      ]
    }
  ]
}

```

return the status computed across all node types and areas, for each use-case.

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|time|[Timestamp](#schematimestamp)|false|none|seconds since epoch|
|network-status|[Status](#schemastatus)|false|none|none|
|correlation-type-status|[[CorrelationStatusByType](#schemacorrelationstatusbytype)]|false|none|[correlationstatus computed across all node types]|
|correlation-area-status|[[CorrelationStatusByArea](#schemacorrelationstatusbyarea)]|false|none|[correlationstatus computed across all areas]|

<h2 id="tocS_CorrelationStatusByType">CorrelationStatusByType</h2>
<!-- backwards compatibility -->
<a id="schemacorrelationstatusbytype"></a>
<a id="schema_CorrelationStatusByType"></a>
<a id="tocScorrelationstatusbytype"></a>
<a id="tocscorrelationstatusbytype"></a>

```json
{
  "use-case": "MITM",
  "correlations": [
    {
      "node-type": "PE-Routers",
      "value": "BAU"
    }
  ]
}

```

correlationstatus computed across all node types

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|use-case|string|false|none|use-case identifier|
|correlations|[[CorrelationStatusByTypeElement](#schemacorrelationstatusbytypeelement)]|false|none|none|

<h2 id="tocS_CorrelationStatusByArea">CorrelationStatusByArea</h2>
<!-- backwards compatibility -->
<a id="schemacorrelationstatusbyarea"></a>
<a id="schema_CorrelationStatusByArea"></a>
<a id="tocScorrelationstatusbyarea"></a>
<a id="tocscorrelationstatusbyarea"></a>

```json
{
  "use-case": "MITM",
  "correlations": [
    {
      "area": "Turin",
      "value": "BAU"
    }
  ]
}

```

correlationstatus computed across all areas

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|use-case|string|false|none|use-case identifier|
|correlations|[[CorrelationStatusByAreaElement](#schemacorrelationstatusbyareaelement)]|false|none|none|

<h2 id="tocS_CorrelationStatusByTypeElement">CorrelationStatusByTypeElement</h2>
<!-- backwards compatibility -->
<a id="schemacorrelationstatusbytypeelement"></a>
<a id="schema_CorrelationStatusByTypeElement"></a>
<a id="tocScorrelationstatusbytypeelement"></a>
<a id="tocscorrelationstatusbytypeelement"></a>

```json
{
  "node-type": "PE-Routers",
  "value": "BAU"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|node-type|string|false|none|none|
|value|[Status](#schemastatus)|false|none|none|

<h2 id="tocS_CorrelationStatusByAreaElement">CorrelationStatusByAreaElement</h2>
<!-- backwards compatibility -->
<a id="schemacorrelationstatusbyareaelement"></a>
<a id="schema_CorrelationStatusByAreaElement"></a>
<a id="tocScorrelationstatusbyareaelement"></a>
<a id="tocscorrelationstatusbyareaelement"></a>

```json
{
  "area": "Turin",
  "value": "BAU"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|area|string|false|none|none|
|value|[Status](#schemastatus)|false|none|none|

<h2 id="tocS_PercentageState">PercentageState</h2>
<!-- backwards compatibility -->
<a id="schemapercentagestate"></a>
<a id="schema_PercentageState"></a>
<a id="tocSpercentagestate"></a>
<a id="tocspercentagestate"></a>

```json
{
  "value": 11
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|value|integer(int32)|false|none|none|

<h2 id="tocS_PercentageConfig">PercentageConfig</h2>
<!-- backwards compatibility -->
<a id="schemapercentageconfig"></a>
<a id="schema_PercentageConfig"></a>
<a id="tocSpercentageconfig"></a>
<a id="tocspercentageconfig"></a>

```json
{
  "value": 11,
  "use-case": "NTP",
  "node": "Milan-3",
  "probe": "probe-C"
}

```

### Properties

allOf

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[PercentageState](#schemapercentagestate)|false|none|none|

and

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[UNP-identifier](#schemaunp-identifier)|false|none|reusable model containing just use-case (U), node (N) and probe (P) identifier|

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

<h2 id="tocS_HistoryPoint">HistoryPoint</h2>
<!-- backwards compatibility -->
<a id="schemahistorypoint"></a>
<a id="schema_HistoryPoint"></a>
<a id="tocShistorypoint"></a>
<a id="tocshistorypoint"></a>

```json
{
  "time": 1600034400,
  "value": "BAU"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|time|[Timestamp](#schematimestamp)|false|none|seconds since epoch|
|value|[Status](#schemastatus)|false|none|none|

<h2 id="tocS_Timestamp">Timestamp</h2>
<!-- backwards compatibility -->
<a id="schematimestamp"></a>
<a id="schema_Timestamp"></a>
<a id="tocStimestamp"></a>
<a id="tocstimestamp"></a>

```json
1600034400

```

seconds since epoch

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|integer(int32)|false|none|seconds since epoch|

