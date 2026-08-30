# BIApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getBiSchema**](BIApi.md#getbischema) | **GET** /bi/schema | Get BI schema catalog |
| [**listBiTemplateRows**](BIApi.md#listbitemplaterows) | **POST** /bi/templates/{template_id}/rows | List flattened template rows for BI integration |
| [**listBiTemplateTimeSeries**](BIApi.md#listbitemplatetimeseries) | **POST** /bi/templates/{template_id}/time-series | List aggregated time-series rows for BI integration |



## getBiSchema

> BiSchemaResponse getBiSchema()

Get BI schema catalog

Returns a normalized metadata catalog of all template schemas and dynamic attribute definitions in the current workspace context.  ### BI Tooling Compatibility Designed for BI connectors (PowerBI, Tableau, Looker Studio, Metabase) and ETL ingestion pipelines. Translates dynamic template schemas into relational column definitions, data types (&#x60;string&#x60;, &#x60;number&#x60;, &#x60;boolean&#x60;, &#x60;datetime&#x60;, &#x60;date&#x60;), reference join keys, and allowed list options.

### Example

```ts
import {
  Configuration,
  BIApi,
} from '@omnismith-sdk/typescript';
import type { GetBiSchemaRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BIApi(config);

  try {
    const data = await api.getBiSchema();
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**BiSchemaResponse**](BiSchemaResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Normalized BI schema catalog |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listBiTemplateRows

> BiTemplateRowsResponse listBiTemplateRows(templateId, biListTemplateRowsRequest, limit, offset, sortField, sortDirection)

List flattened template rows for BI integration

Returns a flattened, relational row-based live dataset for a template, optimized for BI dashboards, spreadsheets, and reporting tools.  ### Tabular Data Model Transforms dynamic entity records into flat rows where columns correspond to the attribute definitions retrieved from &#x60;GET /bi/schema&#x60;.  ### Filter &amp; Search Model Supports structured &#x60;filters&#x60; (operators: &#x60;eq&#x60;, &#x60;neq&#x60;, &#x60;gt&#x60;, &#x60;lt&#x60;, &#x60;like&#x60;, &#x60;not-like&#x60;, &#x60;empty&#x60;, &#x60;not-empty&#x60;) and &#x60;global_search&#x60; text queries.  ### Sorting &amp; Pagination - &#x60;sort_field&#x60;: Attribute UUID, slug, or standard column (&#x60;id&#x60;, &#x60;created_at&#x60;, &#x60;updated_at&#x60;, &#x60;deleted_at&#x60;). - &#x60;sort_direction&#x60;: &#x60;asc&#x60; or &#x60;desc&#x60;. - &#x60;limit&#x60; (max 100) and &#x60;offset&#x60; pagination.

### Example

```ts
import {
  Configuration,
  BIApi,
} from '@omnismith-sdk/typescript';
import type { ListBiTemplateRowsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BIApi(config);

  const body = {
    // string | Unique identifier (UUID) of the template schema to query
    templateId: 018b2f1b-8c1a-75b3-8000-7f0000010001,
    // BiListTemplateRowsRequest
    biListTemplateRowsRequest: ...,
    // number | Maximum number of rows to return per page (1-100) (optional)
    limit: 50,
    // number | Zero-based pagination offset (optional)
    offset: 0,
    // string | Attribute UUID, slug, or standard field (id, created_at, updated_at, deleted_at) to sort by (optional)
    sortField: created_at,
    // 'asc' | 'desc' | Sort direction: \"asc\" (ascending) or \"desc\" (descending) (optional)
    sortDirection: desc,
  } satisfies ListBiTemplateRowsRequest;

  try {
    const data = await api.listBiTemplateRows(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **templateId** | `string` | Unique identifier (UUID) of the template schema to query | [Defaults to `undefined`] |
| **biListTemplateRowsRequest** | [BiListTemplateRowsRequest](BiListTemplateRowsRequest.md) |  | |
| **limit** | `number` | Maximum number of rows to return per page (1-100) | [Optional] [Defaults to `50`] |
| **offset** | `number` | Zero-based pagination offset | [Optional] [Defaults to `0`] |
| **sortField** | `string` | Attribute UUID, slug, or standard field (id, created_at, updated_at, deleted_at) to sort by | [Optional] [Defaults to `undefined`] |
| **sortDirection** | `asc`, `desc` | Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [Optional] [Defaults to `&#39;asc&#39;`] [Enum: asc, desc] |

### Return type

[**BiTemplateRowsResponse**](BiTemplateRowsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flat dataset rows with column definitions |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listBiTemplateTimeSeries

> BiTimeSeriesResponse listBiTemplateTimeSeries(templateId, attributeIds, start, end, biListTemplateRowsRequest, aggregateFunc, bucketWidth)

List aggregated time-series rows for BI integration

Returns aggregated, time-bucketed metric data points across entities of a template schema for BI and analytical visualization tools.  ### Combined Dimension Filtering &amp; Metric Aggregation Combines entity dimension filtering (scoped via the &#x60;filters&#x60; and &#x60;global_search&#x60; body payload) with time-series rollup across the specified &#x60;attribute_ids&#x60;.  ### Aggregation Functions (&#x60;aggregate_func&#x60;) - &#x60;avg&#x60; (default), &#x60;sum&#x60;, &#x60;min&#x60;, &#x60;max&#x60;, &#x60;count&#x60;, &#x60;first&#x60;, &#x60;last&#x60;.  ### Bucket Intervals (&#x60;bucket_width&#x60;) Values follow standard time interval notation: &#x60;1 second&#x60;, &#x60;5 seconds&#x60;, &#x60;10 seconds&#x60;, &#x60;1 minute&#x60; (1m), &#x60;5 minutes&#x60; (5m), &#x60;10 minutes&#x60;, &#x60;15 minutes&#x60;, &#x60;30 minutes&#x60;, &#x60;1 hour&#x60; (1h), &#x60;6 hours&#x60;, &#x60;12 hours&#x60;, &#x60;1 day&#x60; (1d), &#x60;1 week&#x60;, &#x60;1 month&#x60;.  ### Query Window (&#x60;start&#x60; &amp; &#x60;end&#x60;) Specified as integer Unix epoch seconds bounding the telemetry observations.

### Example

```ts
import {
  Configuration,
  BIApi,
} from '@omnismith-sdk/typescript';
import type { ListBiTemplateTimeSeriesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BIApi(config);

  const body = {
    // string | Unique identifier (UUID) of the template schema
    templateId: 018b2f1b-8c1a-75b3-8000-7f0000010001,
    // string | Comma-separated metric attribute UUIDs to aggregate
    attributeIds: 018b2f1b-8c1a-75b3-8000-7f0000010010,018b2f1b-8c1a-75b3-8000-7f0000010011,
    // number | Start timestamp as Unix epoch in seconds
    start: 1774396800,
    // number | End timestamp as Unix epoch in seconds
    end: 1774483200,
    // BiListTemplateRowsRequest
    biListTemplateRowsRequest: ...,
    // 'sum' | 'avg' | 'min' | 'max' | 'count' | 'first' | 'last' | Aggregation function applied within each time bucket (optional)
    aggregateFunc: avg,
    // '1 second' | '5 seconds' | '10 seconds' | '1 minute' | '5 minutes' | '10 minutes' | '15 minutes' | '30 minutes' | '1 hour' | '6 hours' | '12 hours' | '1 day' | '1 week' | '1 month' | Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day) (optional)
    bucketWidth: 1 hour,
  } satisfies ListBiTemplateTimeSeriesRequest;

  try {
    const data = await api.listBiTemplateTimeSeries(body);
    console.log(data);
  } catch (error) {
    console.error(error);
  }
}

// Run the test
example().catch(console.error);
```

### Parameters


| Name | Type | Description  | Notes |
|------------- | ------------- | ------------- | -------------|
| **templateId** | `string` | Unique identifier (UUID) of the template schema | [Defaults to `undefined`] |
| **attributeIds** | `string` | Comma-separated metric attribute UUIDs to aggregate | [Defaults to `undefined`] |
| **start** | `number` | Start timestamp as Unix epoch in seconds | [Defaults to `undefined`] |
| **end** | `number` | End timestamp as Unix epoch in seconds | [Defaults to `undefined`] |
| **biListTemplateRowsRequest** | [BiListTemplateRowsRequest](BiListTemplateRowsRequest.md) |  | |
| **aggregateFunc** | `sum`, `avg`, `min`, `max`, `count`, `first`, `last` | Aggregation function applied within each time bucket | [Optional] [Defaults to `&#39;avg&#39;`] [Enum: sum, avg, min, max, count, first, last] |
| **bucketWidth** | `1 second`, `5 seconds`, `10 seconds`, `1 minute`, `5 minutes`, `10 minutes`, `15 minutes`, `30 minutes`, `1 hour`, `6 hours`, `12 hours`, `1 day`, `1 week`, `1 month` | Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day) | [Optional] [Defaults to `&#39;1 hour&#39;`] [Enum: 1 second, 5 seconds, 10 seconds, 1 minute, 5 minutes, 10 minutes, 15 minutes, 30 minutes, 1 hour, 6 hours, 12 hours, 1 day, 1 week, 1 month] |

### Return type

[**BiTimeSeriesResponse**](BiTimeSeriesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Flat time-series dataset |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

