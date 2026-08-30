# EntityApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createEntity**](EntityApi.md#createentityoperation) | **POST** /entities | Create a new dynamic entity |
| [**deleteEntity**](EntityApi.md#deleteentity) | **DELETE** /entities/{id} | Soft-delete an entity record |
| [**exportEntities**](EntityApi.md#exportentitiesoperation) | **POST** /entities/export/{template_id} | Export entities to structured CSV file |
| [**getEntity**](EntityApi.md#getentity) | **GET** /entities/{id} | Get an entity record by ID |
| [**getEntityChart**](EntityApi.md#getentitychart) | **GET** /entities/{id}/chart | Get entity chart time-series data |
| [**getEntityHistory**](EntityApi.md#getentityhistory) | **GET** /entities/{id}/history | Get entity dimension change history |
| [**importEntities**](EntityApi.md#importentities) | **POST** /entities/import/{template_id} | Import entities from structured CSV file |
| [**ingestEntityMetrics**](EntityApi.md#ingestentitymetrics) | **POST** /entities/{id}/metrics | Ingest high-frequency metric observations for an entity |
| [**searchEntities**](EntityApi.md#searchentitiesoperation) | **POST** /entities/search/{template_id} | Search entities with filtering, sorting, and pagination |
| [**semanticSearchEntities**](EntityApi.md#semanticsearchentitiesoperation) | **POST** /entities/semantic-search | Perform semantic vector similarity search on entities |
| [**updateEntity**](EntityApi.md#updateentityoperation) | **PATCH** /entities/{id} | Update entity attribute values |



## createEntity

> CreateEntity201Response createEntity(createEntityRequest)

Create a new dynamic entity

Creates a new dynamic entity record conforming to a template schema.  ### Template Association Specify the target schema via either &#x60;template_id&#x60; (UUID) or &#x60;template_slug&#x60; (human-readable slug).  ### Dynamic Attribute Values (&#x60;attribute_values&#x60;) Each attribute entry supports identifier resolution and accepts either: - &#x60;attribute_id&#x60;: Canonical attribute UUID - &#x60;attribute_slug&#x60;: Attribute slug identifier (e.g. &#x60;price&#x60;, &#x60;sku&#x60;, &#x60;status&#x60;)  ### Value Formatting Rules - **Dimension - Text / Markdown**: UTF-8 string value (e.g., &#x60;\&quot;Wireless Headphones\&quot;&#x60;) - **Dimension - Number**: Numeric string representation (e.g., &#x60;\&quot;129.99\&quot;&#x60;, &#x60;\&quot;42\&quot;&#x60;) - **Dimension - Boolean**: Strict boolean representation: &#x60;\&quot;true\&quot;&#x60;, &#x60;\&quot;false\&quot;&#x60;, &#x60;\&quot;1\&quot;&#x60;, or &#x60;\&quot;0\&quot;&#x60; - **Dimension - Date &amp; Datetime**: Formatted as &#x60;YYYY-MM-DD&#x60; (date) or &#x60;YYYY-MM-DD HH:MM:SS&#x60; / ISO 8601 &#x60;YYYY-MM-DDTHH:MM:SSZ&#x60; (datetime) - **Dimension - File &amp; Image**: UUID string of a pre-uploaded workspace file asset - **List Attribute**: Must provide the exact UUID string of a valid defined &#x60;ListItem&#x60; option - **Reference Attribute**: Must provide the exact UUID string of an existing referenced &#x60;Entity&#x60;  ### Metric Telemetry Persistence Any metric attributes included in &#x60;attribute_values&#x60; are published directly to the metric ingestion pipeline and recorded in time-series telemetry storage.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { CreateEntityOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // CreateEntityRequest
    createEntityRequest: ...,
  } satisfies CreateEntityOperationRequest;

  try {
    const data = await api.createEntity(body);
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
| **createEntityRequest** | [CreateEntityRequest](CreateEntityRequest.md) |  | |

### Return type

[**CreateEntity201Response**](CreateEntity201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Entity created successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteEntity

> deleteEntity(id)

Soft-delete an entity record

Marks an entity record as soft-deleted by setting its &#x60;deleted_at&#x60; timestamp.  Soft-deleted entities are immediately excluded from standard entity searches, BI row queries, and direct retrieval endpoints. Associated historical change logs and time-series telemetry remain preserved for audit compliance.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { DeleteEntityRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Unique entity identifier (UUID) to soft-delete
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
  } satisfies DeleteEntityRequest;

  try {
    const data = await api.deleteEntity(body);
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
| **id** | `string` | Unique entity identifier (UUID) to soft-delete | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Entity soft-deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## exportEntities

> Blob exportEntities(templateId, exportEntitiesRequest, sortField, sortDirection)

Export entities to structured CSV file

Exports entity records of a template schema matching filter criteria as a streaming CSV download.  ### Re-importable CSV Schema Format The generated CSV conforms to the Omnismith two-row metadata specification, making it directly compatible with &#x60;POST /entities/import/{template_id}&#x60;: - **Row 1**: Display column names and attribute aliases. - **Row 2**: Metadata row prefixed with &#x60;#&#x60; containing attribute UUIDs and column IDs (e.g. &#x60;#id&#x60;, &#x60;#018b2f1b-8c1a...&#x60;). - **Row 3+**: Entity data records.  ### Filter &amp; Search Model Accepts the same filtering payload as &#x60;SearchEntities&#x60;: structured &#x60;filters&#x60; (supporting &#x60;eq&#x60;, &#x60;neq&#x60;, &#x60;gt&#x60;, &#x60;lt&#x60;, &#x60;like&#x60;, &#x60;not-like&#x60;, &#x60;empty&#x60;, &#x60;not-empty&#x60;) and &#x60;global_search&#x60; text queries.  ### Sorting Sort results via &#x60;sort_field&#x60; (attribute UUID, slug, or standard timestamp) and &#x60;sort_direction&#x60; (&#x60;asc&#x60;/&#x60;desc&#x60;).

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { ExportEntitiesOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Unique identifier (UUID) of the template schema to export
    templateId: 018b2f1b-8c1a-75b3-8000-7f0000010001,
    // ExportEntitiesRequest
    exportEntitiesRequest: ...,
    // string | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by (optional)
    sortField: created_at,
    // 'asc' | 'desc' | Sort direction: \"asc\" (ascending) or \"desc\" (descending) (optional)
    sortDirection: asc,
  } satisfies ExportEntitiesOperationRequest;

  try {
    const data = await api.exportEntities(body);
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
| **templateId** | `string` | Unique identifier (UUID) of the template schema to export | [Defaults to `undefined`] |
| **exportEntitiesRequest** | [ExportEntitiesRequest](ExportEntitiesRequest.md) |  | |
| **sortField** | `string` | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by | [Optional] [Defaults to `undefined`] |
| **sortDirection** | `asc`, `desc` | Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [Optional] [Defaults to `&#39;asc&#39;`] [Enum: asc, desc] |

### Return type

**Blob**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `text/csv`, `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | CSV file download stream |  * Content-Disposition - Attachment header with dynamic filename <br>  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntity

> EntityResponse getEntity(id, attributeKey)

Get an entity record by ID

Retrieves the full hydrated record for a dynamic entity by its unique identifier (UUID).  ### Attribute Key Formatting (&#x60;attribute_key&#x60;) The &#x60;attribute_key&#x60; query parameter controls the dictionary keys in &#x60;attribute_values&#x60;: - &#x60;\&quot;id\&quot;&#x60; (default): Keys are canonical attribute UUIDs (e.g. &#x60;018b2f1b-8c1a...&#x60;). - &#x60;\&quot;slug\&quot;&#x60;: Keys are human-readable attribute slugs (e.g. &#x60;price&#x60;, &#x60;sku&#x60;, &#x60;category&#x60;), which is recommended for API consumers and AI agent workflows.  ### Hydrated Attribute Values The returned &#x60;attribute_values&#x60; object includes both raw serialized values and resolved display labels (&#x60;custom_value&#x60;) for references and list options.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { GetEntityRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Unique entity identifier (UUID)
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // 'id' | 'slug' | Format for attribute_values dictionary keys: \"id\" for attribute UUIDs or \"slug\" for human-readable attribute slugs (optional)
    attributeKey: slug,
  } satisfies GetEntityRequest;

  try {
    const data = await api.getEntity(body);
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
| **id** | `string` | Unique entity identifier (UUID) | [Defaults to `undefined`] |
| **attributeKey** | `id`, `slug` | Format for attribute_values dictionary keys: \&quot;id\&quot; for attribute UUIDs or \&quot;slug\&quot; for human-readable attribute slugs | [Optional] [Defaults to `&#39;id&#39;`] [Enum: id, slug] |

### Return type

[**EntityResponse**](EntityResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Hydrated entity details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntityChart

> GetEntityChart200Response getEntityChart(id, attributeIds, start, end, aggregateFunc, bucketWidth)

Get entity chart time-series data

Retrieves aggregated, time-bucketed metric time-series data for an entity.  ### Metric Attribute Filtering (&#x60;attribute_ids&#x60;) Pass one or more comma-separated metric attribute UUIDs to aggregate across the query window.  ### Aggregation Functions (&#x60;aggregate_func&#x60;) Supported aggregation operations within each bucket: - &#x60;avg&#x60; (default): Arithmetic mean of values - &#x60;sum&#x60;: Sum total of values - &#x60;min&#x60; / &#x60;max&#x60;: Minimum / Maximum observed value - &#x60;count&#x60;: Number of recorded observations - &#x60;first&#x60; / &#x60;last&#x60;: Earliest / Latest observation within the time bucket  ### Time Intervals &amp; Bucket Widths (&#x60;bucket_width&#x60;) Values follow standard time interval notation: &#x60;1 second&#x60;, &#x60;5 seconds&#x60;, &#x60;10 seconds&#x60;, &#x60;1 minute&#x60; (1m), &#x60;5 minutes&#x60; (5m), &#x60;10 minutes&#x60;, &#x60;15 minutes&#x60;, &#x60;30 minutes&#x60;, &#x60;1 hour&#x60; (1h), &#x60;6 hours&#x60;, &#x60;12 hours&#x60;, &#x60;1 day&#x60; (1d), &#x60;1 week&#x60;, &#x60;1 month&#x60;.  ### Query Window (&#x60;start&#x60; &amp; &#x60;end&#x60;) Query range is defined by &#x60;start&#x60; and &#x60;end&#x60; timestamps supplied as integer Unix epoch seconds.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { GetEntityChartRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Unique entity identifier (UUID)
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // string | Comma-separated metric attribute UUIDs to aggregate
    attributeIds: 018b2f1b-8c1a-75b3-8000-7f0000010010,018b2f1b-8c1a-75b3-8000-7f0000010011,
    // number | Start timestamp as Unix epoch in seconds
    start: 1774396800,
    // number | End timestamp as Unix epoch in seconds
    end: 1774483200,
    // 'sum' | 'avg' | 'min' | 'max' | 'count' | 'first' | 'last' | Aggregation function applied within each bucket (optional)
    aggregateFunc: avg,
    // '1 second' | '5 seconds' | '10 seconds' | '1 minute' | '5 minutes' | '10 minutes' | '15 minutes' | '30 minutes' | '1 hour' | '6 hours' | '12 hours' | '1 day' | '1 week' | '1 month' | Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day) (optional)
    bucketWidth: 1 hour,
  } satisfies GetEntityChartRequest;

  try {
    const data = await api.getEntityChart(body);
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
| **id** | `string` | Unique entity identifier (UUID) | [Defaults to `undefined`] |
| **attributeIds** | `string` | Comma-separated metric attribute UUIDs to aggregate | [Defaults to `undefined`] |
| **start** | `number` | Start timestamp as Unix epoch in seconds | [Defaults to `undefined`] |
| **end** | `number` | End timestamp as Unix epoch in seconds | [Defaults to `undefined`] |
| **aggregateFunc** | `sum`, `avg`, `min`, `max`, `count`, `first`, `last` | Aggregation function applied within each bucket | [Optional] [Defaults to `&#39;avg&#39;`] [Enum: sum, avg, min, max, count, first, last] |
| **bucketWidth** | `1 second`, `5 seconds`, `10 seconds`, `1 minute`, `5 minutes`, `10 minutes`, `15 minutes`, `30 minutes`, `1 hour`, `6 hours`, `12 hours`, `1 day`, `1 week`, `1 month` | Time bucket width interval (e.g. 1 minute, 5 minutes, 1 hour, 1 day) | [Optional] [Defaults to `&#39;1 hour&#39;`] [Enum: 1 second, 5 seconds, 10 seconds, 1 minute, 5 minutes, 10 minutes, 15 minutes, 30 minutes, 1 hour, 6 hours, 12 hours, 1 day, 1 week, 1 month] |

### Return type

[**GetEntityChart200Response**](GetEntityChart200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Chart time-series data grouped by attribute |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntityHistory

> GetEntityHistory200Response getEntityHistory(id, page, limit, sortBy, sortDirection, search, attributeIds, start, end, authorEmail)

Get entity dimension change history

Retrieves the immutable change audit log for an entity\&#39;s dimension attribute mutations.  ### Dedicated Dimension Audit Log Records all historical mutations to dimension, list, and reference attribute values. High-volume metric telemetry observations bypass this log and are stored in dedicated time-series storage, keeping the audit log clean and performant.  ### Filtering &amp; Search - &#x60;attribute_ids&#x60;: Filter by one or more comma-separated attribute UUIDs. - &#x60;search&#x60;: Text search matching historical serialized values. - &#x60;start&#x60; and &#x60;end&#x60;: Filter history records within a timestamp window (ISO 8601 or &#x60;YYYY-MM-DD HH:MM:SS&#x60;). - &#x60;author_email&#x60;: Filter by the actor who performed the mutation.  ### Pagination &amp; Sorting Supports 1-indexed pagination (&#x60;page&#x60;, &#x60;limit&#x60; up to 100) and sorting by &#x60;created_at&#x60;, &#x60;attribute_id&#x60;, or &#x60;value&#x60; (&#x60;asc&#x60;/&#x60;desc&#x60;).

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { GetEntityHistoryRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Unique entity identifier (UUID)
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // number | 1-based page number for pagination (optional)
    page: 1,
    // number | Number of history records per page (1-100) (optional)
    limit: 20,
    // 'created_at' | 'attribute_id' | 'value' | Field to sort change logs by (optional)
    sortBy: created_at,
    // 'asc' | 'desc' | Sort direction: \"asc\" (ascending) or \"desc\" (descending) (optional)
    sortDirection: desc,
    // string | Free-text search filter matching against old and new attribute values (optional)
    search: Electronics,
    // string | Comma-separated attribute UUIDs to filter change history (optional)
    attributeIds: 018b2f1b-8c1a-75b3-8000-7f0000010002,018b2f1b-8c1a-75b3-8000-7f0000010003,
    // Date | Filter change records occurring on or after this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format) (optional)
    start: 2026-08-01T00:00:00Z,
    // Date | Filter change records occurring on or before this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format) (optional)
    end: 2026-08-26T23:59:59Z,
    // string | Filter change records by author or actor email (optional)
    authorEmail: demo@omnismith.io,
  } satisfies GetEntityHistoryRequest;

  try {
    const data = await api.getEntityHistory(body);
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
| **id** | `string` | Unique entity identifier (UUID) | [Defaults to `undefined`] |
| **page** | `number` | 1-based page number for pagination | [Optional] [Defaults to `1`] |
| **limit** | `number` | Number of history records per page (1-100) | [Optional] [Defaults to `20`] |
| **sortBy** | `created_at`, `attribute_id`, `value` | Field to sort change logs by | [Optional] [Defaults to `&#39;created_at&#39;`] [Enum: created_at, attribute_id, value] |
| **sortDirection** | `asc`, `desc` | Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **search** | `string` | Free-text search filter matching against old and new attribute values | [Optional] [Defaults to `undefined`] |
| **attributeIds** | `string` | Comma-separated attribute UUIDs to filter change history | [Optional] [Defaults to `undefined`] |
| **start** | `Date` | Filter change records occurring on or after this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format) | [Optional] [Defaults to `undefined`] |
| **end** | `Date` | Filter change records occurring on or before this timestamp (ISO 8601 or YYYY-MM-DD HH:MM:SS format) | [Optional] [Defaults to `undefined`] |
| **authorEmail** | `string` | Filter change records by author or actor email | [Optional] [Defaults to `undefined`] |

### Return type

[**GetEntityHistory200Response**](GetEntityHistory200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated entity dimension change history |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## importEntities

> ImportEntities200Response importEntities(templateId, file)

Import entities from structured CSV file

Bulk imports entity records into a template schema from a structured CSV file.  ### Upsert Semantics - **Update existing**: If a data row includes an &#x60;id&#x60; matching an existing entity UUID, that entity is updated. - **Create new**: If the &#x60;id&#x60; column is empty, omitted, or contains a new UUID, a new entity record is created.  ### Required 2-Row CSV Header Format The CSV file must follow the Omnismith two-row header format (identical to the output of &#x60;POST /entities/export/{template_id}&#x60;): - **Row 1 (Display Header)**: Human-readable attribute names or aliases (e.g. &#x60;ID&#x60;, &#x60;SKU&#x60;, &#x60;Price&#x60;, &#x60;Category&#x60;). - **Row 2 (Metadata Marker)**: Canonical attribute identifiers prefixed by &#x60;#&#x60; (e.g. &#x60;#id&#x60;, &#x60;#018b2f1b-8c1a...&#x60;, &#x60;#018b2f1b-8c1b...&#x60;). - **Row 3+ (Data Rows)**: Serialized entity values conforming to the template\&#39;s attribute data types.  ### Attribute Value Validation - List attributes require valid &#x60;ListItem&#x60; option UUIDs. - Reference attributes require existing target &#x60;Entity&#x60; UUIDs. - Number/Date/Boolean fields must match required format syntax.  ### Execution Summary Returns an execution report detailing counts of created, updated, skipped, and failed rows, along with granular row/column error messages.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { ImportEntitiesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Unique identifier (UUID) of the template schema to import entities into
    templateId: 018b2f1b-8c1a-75b3-8000-7f0000010001,
    // Blob | CSV file exported from the export endpoint or matching its format
    file: BINARY_DATA_HERE,
  } satisfies ImportEntitiesRequest;

  try {
    const data = await api.importEntities(body);
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
| **templateId** | `string` | Unique identifier (UUID) of the template schema to import entities into | [Defaults to `undefined`] |
| **file** | `Blob` | CSV file exported from the export endpoint or matching its format | [Defaults to `undefined`] |

### Return type

[**ImportEntities200Response**](ImportEntities200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Import completed |  -  |
| **400** | Bad Request |  -  |
| **422** | Validation Error |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## ingestEntityMetrics

> ingestEntityMetrics(id, ingestMetricsRequest)

Ingest high-frequency metric observations for an entity

Ingests time-series metric observations for an entity record.  ### Batch Telemetry Ingestion Accepts a batch array of metric observations (&#x60;metric_values&#x60;). Each observation targets a metric attribute by &#x60;attribute_id&#x60; (UUID) or &#x60;attribute_slug&#x60; and specifies a numeric &#x60;value&#x60;.  ### High-Throughput Streaming Architecture Metric ingestion calls stream directly into the high-throughput telemetry ingestion pipeline. Asynchronous background consumers persist data points into tenant-scoped time-series storage configured with automated retention and continuous aggregation rollups.  ### Strict Metric Attribute Constraint Only attributes defined with &#x60;attribute_type: Metric&#x60; are accepted by this endpoint. Mutations to dimension, list, or reference attributes must use &#x60;PATCH /entities/{id}&#x60; instead.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { IngestEntityMetricsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Unique entity identifier (UUID)
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // IngestMetricsRequest
    ingestMetricsRequest: ...,
  } satisfies IngestEntityMetricsRequest;

  try {
    const data = await api.ingestEntityMetrics(body);
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
| **id** | `string` | Unique entity identifier (UUID) | [Defaults to `undefined`] |
| **ingestMetricsRequest** | [IngestMetricsRequest](IngestMetricsRequest.md) |  | |

### Return type

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **202** | Metrics accepted for ingestion and time-series persistence |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchEntities

> SearchEntities200Response searchEntities(templateId, searchEntitiesRequest, limit, offset, sortField, sortDirection, attributeKey)

Search entities with filtering, sorting, and pagination

Executes structured queries, full-text searches, and sorting across dynamic entities of a specified template schema.  ### Template Targeting (&#x60;template_id&#x60;) Accepts either a canonical template UUID (e.g. &#x60;018b2f1b-8c1a...&#x60;) or a human-readable template slug (e.g. &#x60;product_catalog&#x60;).  ### Structured Filters (&#x60;filters&#x60;) Filter conditions are specified in the request body as an array of filter objects: &#x60;&#x60;&#x60;json [   {\&quot;field\&quot;: \&quot;status\&quot;, \&quot;operator\&quot;: \&quot;eq\&quot;, \&quot;value\&quot;: \&quot;018b2f1b-8c1a-75b3-8000-7f0000010020\&quot;},   {\&quot;field\&quot;: \&quot;price\&quot;, \&quot;operator\&quot;: \&quot;gt\&quot;, \&quot;value\&quot;: \&quot;100\&quot;},   {\&quot;field\&quot;: \&quot;name\&quot;, \&quot;operator\&quot;: \&quot;like\&quot;, \&quot;value\&quot;: \&quot;Pro\&quot;} ] &#x60;&#x60;&#x60; - **&#x60;field&#x60;**: Target attribute UUID, attribute slug, or standard field (&#x60;id&#x60;, &#x60;created_at&#x60;, &#x60;updated_at&#x60;). - **&#x60;operator&#x60;**: Comparison operator: &#x60;eq&#x60; (equals), &#x60;neq&#x60; (not equals), &#x60;gt&#x60; (greater than), &#x60;lt&#x60; (less than), &#x60;like&#x60; (substring / trigram match), &#x60;not-like&#x60; (does not match), &#x60;empty&#x60; (is null or empty), &#x60;not-empty&#x60; (has value). - **&#x60;value&#x60;**: Target comparison value serialized as string.  ### Global Search (&#x60;global_search&#x60;) Performs accelerated full-text and GIN trigram matching across all string dimension attributes defined on the template.  ### Sorting &amp; Pagination - **&#x60;sort_field&#x60;**: Attribute UUID, attribute slug, or standard entity fields (&#x60;id&#x60;, &#x60;created_at&#x60;, &#x60;updated_at&#x60;, &#x60;deleted_at&#x60;). - **&#x60;sort_direction&#x60;**: &#x60;asc&#x60; or &#x60;desc&#x60; (default: &#x60;asc&#x60; when &#x60;sort_field&#x60; is set, otherwise default sort is &#x60;created_at&#x60; DESC). - **&#x60;limit&#x60;** and **&#x60;offset&#x60;**: Bounded pagination (max 100 per page).  ### Attribute Key Formatting (&#x60;attribute_key&#x60;) Passing &#x60;attribute_key&#x3D;\&quot;slug\&quot;&#x60; formats the returned &#x60;attribute_values&#x60; dictionary keys using human-readable attribute slugs instead of raw UUIDs.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { SearchEntitiesOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Template UUID or human-readable template slug
    templateId: product_catalog,
    // SearchEntitiesRequest
    searchEntitiesRequest: ...,
    // number | Maximum number of entity records to return (1-100) (optional)
    limit: 50,
    // number | Zero-based pagination offset (optional)
    offset: 0,
    // string | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by (optional)
    sortField: created_at,
    // 'asc' | 'desc' | Sort direction: \"asc\" (ascending) or \"desc\" (descending) (optional)
    sortDirection: desc,
    // 'id' | 'slug' | Format for attribute_values dictionary keys: \"id\" for attribute UUIDs or \"slug\" for human-readable attribute slugs (optional)
    attributeKey: slug,
  } satisfies SearchEntitiesOperationRequest;

  try {
    const data = await api.searchEntities(body);
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
| **templateId** | `string` | Template UUID or human-readable template slug | [Defaults to `undefined`] |
| **searchEntitiesRequest** | [SearchEntitiesRequest](SearchEntitiesRequest.md) |  | |
| **limit** | `number` | Maximum number of entity records to return (1-100) | [Optional] [Defaults to `50`] |
| **offset** | `number` | Zero-based pagination offset | [Optional] [Defaults to `0`] |
| **sortField** | `string` | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by | [Optional] [Defaults to `undefined`] |
| **sortDirection** | `asc`, `desc` | Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [Optional] [Defaults to `&#39;asc&#39;`] [Enum: asc, desc] |
| **attributeKey** | `id`, `slug` | Format for attribute_values dictionary keys: \&quot;id\&quot; for attribute UUIDs or \&quot;slug\&quot; for human-readable attribute slugs | [Optional] [Defaults to `&#39;id&#39;`] [Enum: id, slug] |

### Return type

[**SearchEntities200Response**](SearchEntities200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Search results matching criteria |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## semanticSearchEntities

> Array&lt;SemanticSearchResultItem&gt; semanticSearchEntities(semanticSearchEntitiesRequest)

Perform semantic vector similarity search on entities

Executes an approximate nearest neighbors (ANN) vector similarity search across entity dimension embeddings.  ### 768-Dimensional Embedding Vectors Requires a 768-dimensional float embedding array (&#x60;query_vector&#x60;) representing the query text or multimodal vector (e.g. generated by Google &#x60;text-embedding-004&#x60; or similar models).  ### Scoping &amp; Filtering (&#x60;template_id&#x60;) Pass an optional &#x60;template_id&#x60; (UUID) or template slug to constrain the semantic search to records belonging to a specific template schema.  ### Cosine Similarity Threshold &amp; Ranking (&#x60;threshold&#x60;) - &#x60;threshold&#x60;: Minimum cosine similarity score threshold (range &#x60;0.0&#x60; to &#x60;1.0&#x60;, default &#x60;0.5&#x60;). Observations below this similarity cutoff are discarded. - Matches are returned strictly ranked in descending order of &#x60;similarity_score&#x60;.  ### Attribute Key Formatting (&#x60;attribute_key&#x60;) Set &#x60;attribute_key&#x3D;\&quot;slug\&quot;&#x60; to format the nested entity &#x60;attribute_values&#x60; dictionary keys as human-readable slugs instead of raw attribute UUIDs.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { SemanticSearchEntitiesOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // SemanticSearchEntitiesRequest
    semanticSearchEntitiesRequest: ...,
  } satisfies SemanticSearchEntitiesOperationRequest;

  try {
    const data = await api.semanticSearchEntities(body);
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
| **semanticSearchEntitiesRequest** | [SemanticSearchEntitiesRequest](SemanticSearchEntitiesRequest.md) |  | |

### Return type

[**Array&lt;SemanticSearchResultItem&gt;**](SemanticSearchResultItem.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Matching entities ranked by semantic similarity score |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateEntity

> updateEntity(id, updateEntityRequest)

Update entity attribute values

Updates specific dynamic attribute values for an existing entity record.  ### Dynamic Attribute Values (&#x60;attribute_values&#x60;) Submit one or more attribute value updates. Each entry supports identifier resolution via: - &#x60;attribute_id&#x60;: Canonical attribute UUID - &#x60;attribute_slug&#x60;: Attribute slug identifier (e.g. &#x60;price&#x60;, &#x60;sku&#x60;, &#x60;status&#x60;)  ### Value Formatting Rules - **Dimension - Text / Markdown**: UTF-8 string value - **Dimension - Number**: Numeric string representation (e.g. &#x60;\&quot;149.99\&quot;&#x60;) - **Dimension - Boolean**: Boolean representation: &#x60;\&quot;true\&quot;&#x60;, &#x60;\&quot;false\&quot;&#x60;, &#x60;\&quot;1\&quot;&#x60;, or &#x60;\&quot;0\&quot;&#x60; - **Dimension - Date &amp; Datetime**: Formatted as &#x60;YYYY-MM-DD&#x60; or &#x60;YYYY-MM-DD HH:MM:SS&#x60; / ISO 8601 &#x60;YYYY-MM-DDTHH:MM:SSZ&#x60; - **Dimension - File &amp; Image**: UUID string of a pre-uploaded workspace file asset - **List Attribute**: Must provide the exact UUID string of a valid defined &#x60;ListItem&#x60; option - **Reference Attribute**: Must provide the exact UUID string of an existing referenced &#x60;Entity&#x60;  ### Audit Trail &amp; Metrics - Dimension updates are recorded in the append-only entity dimension change history log. - Metric attribute values submitted here are dispatched to the metric streaming pipeline for time-series aggregation.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { UpdateEntityOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Unique entity identifier (UUID)
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // UpdateEntityRequest
    updateEntityRequest: ...,
  } satisfies UpdateEntityOperationRequest;

  try {
    const data = await api.updateEntity(body);
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
| **id** | `string` | Unique entity identifier (UUID) | [Defaults to `undefined`] |
| **updateEntityRequest** | [UpdateEntityRequest](UpdateEntityRequest.md) |  | |

### Return type

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Entity attributes updated successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

