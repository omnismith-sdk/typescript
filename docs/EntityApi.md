# EntityApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createEntity**](EntityApi.md#createentityoperation) | **POST** /entities | Create a new entity |
| [**deleteEntity**](EntityApi.md#deleteentity) | **DELETE** /entities/{id} | Delete an entity |
| [**exportEntities**](EntityApi.md#exportentitiesoperation) | **POST** /entities/export/{template_id} | Export entities to CSV |
| [**getEntity**](EntityApi.md#getentity) | **GET** /entities/{id} | Get an entity |
| [**getEntityChart**](EntityApi.md#getentitychart) | **GET** /entities/{id}/chart | Get entity chart time-series data |
| [**getEntityHistory**](EntityApi.md#getentityhistory) | **GET** /entities/{id}/history | Get entity history |
| [**importEntities**](EntityApi.md#importentities) | **POST** /entities/import/{template_id} | Import entities from CSV |
| [**searchEntities**](EntityApi.md#searchentitiesoperation) | **POST** /entities/search/{template_id} | Search entities |
| [**updateEntity**](EntityApi.md#updateentityoperation) | **PUT** /entities/{id} | Update an entity |



## createEntity

> CreateAttributeItem201Response createEntity(createEntityRequest)

Create a new entity

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

[**CreateAttributeItem201Response**](CreateAttributeItem201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Entity created |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteEntity

> deleteEntity(id)

Delete an entity

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
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` |  | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: Not defined


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **204** | Entity deleted |  -  |
| **404** | Entity not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## exportEntities

> Blob exportEntities(templateId, exportEntitiesRequest, sortField, sortDirection)

Export entities to CSV

Export entities matching the given filters to a CSV file. Uses the same filters as the search endpoint.

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
    // string | Template ID
    templateId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // ExportEntitiesRequest
    exportEntitiesRequest: ...,
    // string | Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at (optional)
    sortField: sortField_example,
    // 'asc' | 'desc' | Sort direction (only used when sort_field is provided) (optional)
    sortDirection: sortDirection_example,
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
| **templateId** | `string` | Template ID | [Defaults to `undefined`] |
| **exportEntitiesRequest** | [ExportEntitiesRequest](ExportEntitiesRequest.md) |  | |
| **sortField** | `string` | Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at | [Optional] [Defaults to `undefined`] |
| **sortDirection** | `asc`, `desc` | Sort direction (only used when sort_field is provided) | [Optional] [Defaults to `&#39;asc&#39;`] [Enum: asc, desc] |

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
| **200** | CSV file download |  * Content-Disposition - Attachment filename <br>  |
| **422** | Validation Error |  -  |
| **401** | Unauthorized |  -  |
| **403** | Access denied |  -  |
| **404** | Template not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntity

> EntityResponse getEntity(id)

Get an entity

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
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` |  | [Defaults to `undefined`] |

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
| **200** | Entity details |  -  |
| **404** | Entity not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntityChart

> GetEntityChart200Response getEntityChart(id, attributeIds, start, end, aggregateFunc, bucketWidth)

Get entity chart time-series data

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { GetEntityChartRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new EntityApi();

  const body = {
    // string | Entity ID
    id: id_example,
    // string | Comma-separated attribute IDs
    attributeIds: attributeIds_example,
    // number | Start timestamp (Unix seconds)
    start: 56,
    // number | End timestamp (Unix seconds)
    end: 56,
    // 'sum' | 'avg' | 'min' | 'max' | 'count' | 'first' | 'last' | Aggregate function (optional)
    aggregateFunc: aggregateFunc_example,
    // '1 second' | '5 seconds' | '10 seconds' | '1 minute' | '5 minutes' | '10 minutes' | '15 minutes' | '30 minutes' | '1 hour' | '6 hours' | '12 hours' | '1 day' | '1 week' | '1 month' | Time bucket width (PostgreSQL interval) (optional)
    bucketWidth: bucketWidth_example,
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
| **id** | `string` | Entity ID | [Defaults to `undefined`] |
| **attributeIds** | `string` | Comma-separated attribute IDs | [Defaults to `undefined`] |
| **start** | `number` | Start timestamp (Unix seconds) | [Defaults to `undefined`] |
| **end** | `number` | End timestamp (Unix seconds) | [Defaults to `undefined`] |
| **aggregateFunc** | `sum`, `avg`, `min`, `max`, `count`, `first`, `last` | Aggregate function | [Optional] [Defaults to `&#39;avg&#39;`] [Enum: sum, avg, min, max, count, first, last] |
| **bucketWidth** | `1 second`, `5 seconds`, `10 seconds`, `1 minute`, `5 minutes`, `10 minutes`, `15 minutes`, `30 minutes`, `1 hour`, `6 hours`, `12 hours`, `1 day`, `1 week`, `1 month` | Time bucket width (PostgreSQL interval) | [Optional] [Defaults to `&#39;1 hour&#39;`] [Enum: 1 second, 5 seconds, 10 seconds, 1 minute, 5 minutes, 10 minutes, 15 minutes, 30 minutes, 1 hour, 6 hours, 12 hours, 1 day, 1 week, 1 month] |

### Return type

[**GetEntityChart200Response**](GetEntityChart200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Chart time-series data grouped by attribute |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntityHistory

> GetEntityHistory200Response getEntityHistory(id, page, limit, sortBy, sortDirection, search, attributeIds, start, end, authorEmail)

Get entity history

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { GetEntityHistoryRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new EntityApi();

  const body = {
    // string | Entity ID
    id: id_example,
    // number (optional)
    page: 56,
    // number (optional)
    limit: 56,
    // 'created_at' | 'attribute_id' | 'value' (optional)
    sortBy: sortBy_example,
    // 'asc' | 'desc' (optional)
    sortDirection: sortDirection_example,
    // string (optional)
    search: search_example,
    // string (optional)
    attributeIds: attributeIds_example,
    // Date | Filter logs created after this timestamp (optional)
    start: 2013-10-20T19:20:30+01:00,
    // Date | Filter logs created before this timestamp (optional)
    end: 2013-10-20T19:20:30+01:00,
    // string | Filter logs by author email (optional)
    authorEmail: authorEmail_example,
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
| **id** | `string` | Entity ID | [Defaults to `undefined`] |
| **page** | `number` |  | [Optional] [Defaults to `1`] |
| **limit** | `number` |  | [Optional] [Defaults to `20`] |
| **sortBy** | `created_at`, `attribute_id`, `value` |  | [Optional] [Defaults to `&#39;created_at&#39;`] [Enum: created_at, attribute_id, value] |
| **sortDirection** | `asc`, `desc` |  | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **search** | `string` |  | [Optional] [Defaults to `undefined`] |
| **attributeIds** | `string` |  | [Optional] [Defaults to `undefined`] |
| **start** | `Date` | Filter logs created after this timestamp | [Optional] [Defaults to `undefined`] |
| **end** | `Date` | Filter logs created before this timestamp | [Optional] [Defaults to `undefined`] |
| **authorEmail** | `string` | Filter logs by author email | [Optional] [Defaults to `undefined`] |

### Return type

[**GetEntityHistory200Response**](GetEntityHistory200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Entity history |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## importEntities

> ImportEntities200Response importEntities(templateId, file)

Import entities from CSV

Import entities from a CSV file. Supports upsert: creates new entities or updates existing ones based on the ID column. The CSV must include a metadata row (row 2) with attribute IDs prefixed by #.

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
    // string | Template ID
    templateId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **templateId** | `string` | Template ID | [Defaults to `undefined`] |
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
| **400** | Bad request (invalid CSV format) |  -  |
| **422** | Validation Error |  -  |
| **401** | Unauthorized |  -  |
| **403** | Access denied |  -  |
| **404** | Template not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchEntities

> SearchEntities200Response searchEntities(templateId, searchEntitiesRequest, limit, offset, sortField, sortDirection)

Search entities

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
    // string | Template ID
    templateId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // SearchEntitiesRequest
    searchEntitiesRequest: ...,
    // number | Number of results (optional)
    limit: 56,
    // number | Pagination offset (optional)
    offset: 56,
    // string | Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at (optional)
    sortField: sortField_example,
    // 'asc' | 'desc' | Sort direction (only used when sort_field is provided) (optional)
    sortDirection: sortDirection_example,
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
| **templateId** | `string` | Template ID | [Defaults to `undefined`] |
| **searchEntitiesRequest** | [SearchEntitiesRequest](SearchEntitiesRequest.md) |  | |
| **limit** | `number` | Number of results | [Optional] [Defaults to `50`] |
| **offset** | `number` | Pagination offset | [Optional] [Defaults to `0`] |
| **sortField** | `string` | Attribute ID to sort by (UUID) OR one of: id, created_at, updated_at, deleted_at | [Optional] [Defaults to `undefined`] |
| **sortDirection** | `asc`, `desc` | Sort direction (only used when sort_field is provided) | [Optional] [Defaults to `&#39;asc&#39;`] [Enum: asc, desc] |

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
| **200** | Search results |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateEntity

> updateEntity(id, updateEntityRequest)

Update an entity

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
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` |  | [Defaults to `undefined`] |
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
| **204** | Entity updated |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |
| **404** | Entity not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

