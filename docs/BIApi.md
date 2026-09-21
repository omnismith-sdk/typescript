# BIApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getBiSchema**](BIApi.md#getbischema) | **GET** /bi/schema | Get BI schema catalog |
| [**listBiTemplateRows**](BIApi.md#listbitemplaterows) | **POST** /bi/templates/{template_id}/rows | List flattened template rows for BI integration |
| [**listBiTemplateTimeSeries**](BIApi.md#listbitemplatetimeseries) | **POST** /bi/templates/{template_id}/time-series | List aggregated time-series rows for BI integration |



## getBiSchema

> BiSchemaResponse getBiSchema(xOmnismithProjectId)

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

  const body = {
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies GetBiSchemaRequest;

  try {
    const data = await api.getBiSchema(body);
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listBiTemplateRows

> BiTemplateRowsResponse listBiTemplateRows(templateId, biListTemplateRowsRequest, xOmnismithProjectId, limit, offset, sortField, sortDirection)

List flattened template rows for BI integration

Returns a flattened, relational row-based live dataset for a template, optimized for BI dashboards, spreadsheets, and reporting tools.  ### Tabular Data Model Transforms dynamic entity records into flat rows where columns correspond to the attribute definitions retrieved from &#x60;GET /bi/schema&#x60;.  ### Filter &amp; Search Model Accepts the same &#x60;filter_groups&#x60; and &#x60;global_search&#x60; payload as &#x60;searchEntities&#x60;.  ### Filters (&#x60;filter_groups&#x60;) A list of groups; clauses inside a group are AND-ed, groups are OR-ed. &#x60;[[a, b]]&#x60; is &#x60;a AND b&#x60;; &#x60;[[a], [b, c]]&#x60; is &#x60;a OR (b AND c)&#x60;; &#x60;[]&#x60; applies no filter. &#x60;&#x60;&#x60;json [   [     {\&quot;field\&quot;: \&quot;status\&quot;, \&quot;operator\&quot;: \&quot;in\&quot;, \&quot;value\&quot;: [\&quot;018b…0020\&quot;, \&quot;018b…0021\&quot;]},     {\&quot;field\&quot;: \&quot;created_at\&quot;, \&quot;operator\&quot;: \&quot;between\&quot;, \&quot;value\&quot;: [\&quot;2026-01-01\&quot;, \&quot;2026-03-31\&quot;]},     {\&quot;field\&quot;: \&quot;customer.tier\&quot;, \&quot;operator\&quot;: \&quot;eq\&quot;, \&quot;value\&quot;: \&quot;018b…0042\&quot;}   ],   [{\&quot;field\&quot;: \&quot;priority\&quot;, \&quot;operator\&quot;: \&quot;eq\&quot;, \&quot;value\&quot;: \&quot;018b…0007\&quot;}] ] &#x60;&#x60;&#x60; - **&#x60;field&#x60;**: attribute slug or UUID, a standard field (&#x60;id&#x60;, &#x60;created_at&#x60;, &#x60;updated_at&#x60;), or a one-hop path &#x60;&lt;reference&gt;.&lt;attribute&gt;&#x60; that filters on an attribute of the referenced record (e.g. &#x60;customer.tier&#x60;). One hop only. - **&#x60;operator&#x60;** and **&#x60;value&#x60;**: &#x60;eq&#x60;, &#x60;neq&#x60;, &#x60;gt&#x60;, &#x60;lt&#x60;, &#x60;like&#x60; (case-insensitive substring), &#x60;not-like&#x60; take a string; &#x60;in&#x60;, &#x60;not-in&#x60; take a non-empty list of strings; &#x60;between&#x60; takes &#x60;[lower, upper]&#x60; (inclusive; number, date, datetime attributes and &#x60;created_at&#x60; / &#x60;updated_at&#x60;); &#x60;empty&#x60;, &#x60;not-empty&#x60; take no value. - List and reference attributes compare the stored id (from &#x60;list_item_ids&#x60; / &#x60;reference_entity_ids&#x60; or the schema), never the label. - Unknown fields, operators that do not fit the field, malformed values and paths that do not traverse a reference are refused with 400 naming the valid fields; a path into a template the caller may not view is 403.  ### Sorting &amp; Pagination - &#x60;sort_field&#x60;: Attribute UUID, slug, or standard column (&#x60;id&#x60;, &#x60;created_at&#x60;, &#x60;updated_at&#x60;, &#x60;deleted_at&#x60;). - &#x60;sort_direction&#x60;: &#x60;asc&#x60; or &#x60;desc&#x60;. - &#x60;limit&#x60; (max 100) and &#x60;offset&#x60; pagination.  ### Column Projection (&#x60;fields&#x60;) Supply an optional &#x60;fields&#x60; array in the request body to project specific columns (e.g. &#x60;{\&quot;fields\&quot;: [\&quot;price\&quot;, \&quot;sku\&quot;]}&#x60;). Non-projected dynamic attribute columns are excluded from both the schema &#x60;columns&#x60; and row data, eliminating unnecessary attribute hydration and reducing tabular payload size.

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listBiTemplateTimeSeries

> BiTimeSeriesResponse listBiTemplateTimeSeries(templateId, attributeIds, start, end, biListTemplateRowsRequest, xOmnismithProjectId, aggregateFunc, bucketWidth)

List aggregated time-series rows for BI integration

Returns aggregated, time-bucketed metric data points across entities of a template schema for BI and analytical visualization tools.  ### Combined Dimension Filtering &amp; Metric Aggregation Combines entity dimension filtering (scoped via the &#x60;filter_groups&#x60; and &#x60;global_search&#x60; body payload, same grammar as &#x60;searchEntities&#x60;) with time-series rollup across the specified &#x60;attribute_ids&#x60;.  ### Aggregation Functions (&#x60;aggregate_func&#x60;) - &#x60;avg&#x60; (default), &#x60;sum&#x60;, &#x60;min&#x60;, &#x60;max&#x60;, &#x60;count&#x60;, &#x60;first&#x60;, &#x60;last&#x60;.  ### Bucket Intervals (&#x60;bucket_width&#x60;) Values follow standard time interval notation: &#x60;1 second&#x60;, &#x60;5 seconds&#x60;, &#x60;10 seconds&#x60;, &#x60;1 minute&#x60; (1m), &#x60;5 minutes&#x60; (5m), &#x60;10 minutes&#x60;, &#x60;15 minutes&#x60;, &#x60;30 minutes&#x60;, &#x60;1 hour&#x60; (1h), &#x60;6 hours&#x60;, &#x60;12 hours&#x60;, &#x60;1 day&#x60; (1d), &#x60;1 week&#x60;, &#x60;1 month&#x60;.  ### Query Window (&#x60;start&#x60; &amp; &#x60;end&#x60;) Specified as integer Unix epoch seconds bounding the telemetry observations.

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

