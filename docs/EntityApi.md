# EntityApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**aggregateEntities**](EntityApi.md#aggregateentitiesoperation) | **POST** /entities/aggregate/{template_id} | Count, sum, average, min or max entities, optionally grouped by attributes |
| [**batchExecuteEntityAction**](EntityApi.md#batchexecuteentityactionoperation) | **POST** /entities/batch/actions/{slug} | Execute an action on a selection of entities |
| [**batchWriteEntities**](EntityApi.md#batchwriteentitiesoperation) | **POST** /entities/batch | Apply a batch of mixed entity creates, updates, replaces, and deletes |
| [**createEntity**](EntityApi.md#createentityoperation) | **POST** /entities/template/{template} | Create a new dynamic entity |
| [**deleteEntity**](EntityApi.md#deleteentity) | **DELETE** /entities/{id} | Soft-delete an entity record |
| [**executeEntityAction**](EntityApi.md#executeentityactionoperation) | **POST** /entities/{id}/actions/{slug} | Execute an action on an entity |
| [**exportEntities**](EntityApi.md#exportentitiesoperation) | **POST** /entities/export/{template_id} | Export entities to structured CSV file |
| [**getEntity**](EntityApi.md#getentity) | **GET** /entities/{id} | Get an entity record by ID |
| [**getEntityChart**](EntityApi.md#getentitychart) | **GET** /entities/{id}/chart | Get entity chart time-series data |
| [**getEntityHistory**](EntityApi.md#getentityhistory) | **GET** /entities/{id}/history | Get entity dimension change history |
| [**importEntities**](EntityApi.md#importentities) | **POST** /entities/import/{template_id} | Import entities from structured CSV file |
| [**ingestEntityMetrics**](EntityApi.md#ingestentitymetrics) | **POST** /entities/{id}/metrics | Ingest high-frequency metric observations for an entity |
| [**listEntityActions**](EntityApi.md#listentityactions) | **GET** /entities/{id}/actions | List the actions available on an entity |
| [**replaceEntity**](EntityApi.md#replaceentityoperation) | **PUT** /entities/{id} | Replace all non-metric attributes of an entity |
| [**searchEntities**](EntityApi.md#searchentitiesoperation) | **POST** /entities/search/{template_id} | Search entities with filtering, sorting, and pagination |
| [**semanticSearchEntities**](EntityApi.md#semanticsearchentitiesoperation) | **POST** /entities/semantic-search | Perform semantic vector similarity search on entities |
| [**updateEntity**](EntityApi.md#updateentityoperation) | **PATCH** /entities/{id} | Update entity attribute values |



## aggregateEntities

> AggregateEntities200Response aggregateEntities(templateId, aggregateEntitiesRequest, xOmnismithProjectId)

Count, sum, average, min or max entities, optionally grouped by attributes

Answers \&quot;how many\&quot;, \&quot;how much\&quot; and \&quot;broken down by\&quot; questions in one call, computed by the database. Use it instead of paginating &#x60;search_entities&#x60; and tallying rows: a count or a per-status breakdown of a 10,000-record template is one small response. See &#x60;filter_groups&#x60;, &#x60;group_by&#x60; and &#x60;aggregations&#x60; for the request shape.  Each response group\&#39;s &#x60;key&#x60; mirrors &#x60;group_by&#x60; in order (&#x60;value&#x60; is the stored value, &#x60;custom_value&#x60; is the list item label or the referenced record\&#39;s display value; &#x60;null&#x60; groups the records that have no value for that attribute), and &#x60;aggregates&#x60; mirrors &#x60;aggregations&#x60; in order. Numbers come back as floats, dates as RFC 3339 strings, and &#x60;null&#x60; when no record in the group has a value. Metric attributes are rejected with a 400: they are time series, reduced over a time window with &#x60;get_entity_chart&#x60; instead — this endpoint reduces the current dimension values of records.  Groups are ordered by the first aggregation descending (nulls last), then by key. &#x60;limit&#x60; (1-100, default 50) caps the groups returned; &#x60;truncated: true&#x60; means more groups exist — narrow with &#x60;filter_groups&#x60; or group by fewer fields.  Read-only. Applies the caller\&#39;s template access and row scopes exactly as search does; restricted attributes are not valid fields.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { AggregateEntitiesOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Template UUID or human-readable template slug
    templateId: tenant_user,
    // AggregateEntitiesRequest
    aggregateEntitiesRequest: ...,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies AggregateEntitiesOperationRequest;

  try {
    const data = await api.aggregateEntities(body);
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
| **aggregateEntitiesRequest** | [AggregateEntitiesRequest](AggregateEntitiesRequest.md) |  | |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**AggregateEntities200Response**](AggregateEntities200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Groups with their aggregates, ordered by the first aggregation descending |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## batchExecuteEntityAction

> BatchExecuteEntityActionResponse batchExecuteEntityAction(slug, batchExecuteEntityActionRequest, xOmnismithProjectId)

Execute an action on a selection of entities

Runs one named action on many records in a single call — \&quot;confirm these forty\&quot;. Each record goes through exactly what &#x60;POST /entities/{id}/actions/{slug}&#x60; (&#x60;execute_entity_action&#x60;) does: precondition, field matching, presets, type validation and the template\&#39;s rules, with history attributed to the action. &#x60;values&#x60; are the same for every record.  The action is resolved per record on its template, so the selection may span templates that each define the slug; a record whose template does not is reported as &#x60;failed&#x60; with a 404 body.  At most 100 records per call; page a larger selection.  Outcomes: By default (&#x60;atomic: false&#x60;) every record is attempted and the response is &#x60;200&#x60; with one outcome per record — &#x60;executed&#x60; with a receipt, or &#x60;precondition_failed&#x60; / &#x60;rule_violated&#x60; / &#x60;failed&#x60; with the error body the single-record endpoint would have returned. Read the counters, then &#x60;results&#x60; for the records that did not run.  With &#x60;atomic: true&#x60; the batch runs in one transaction and the first record that does not execute rolls all of it back. That case answers with that record\&#39;s own error status and body plus &#x60;failed_entity_id&#x60;, not with a results list.  Quotas: The dimension-update quota is checked for the whole selection before any record is written.  Errors: - &#x60;400&#x60; — the body is not the documented shape, or lists an entity twice. - &#x60;402&#x60; — the selection would cross the tier\&#39;s update quota. - &#x60;422&#x60; — a submitted value does not fit the action (only when nothing could run).

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { BatchExecuteEntityActionOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // string | Action slug, as listed by `GET /templates/{templateId}/actions` or `GET /entities/{id}/actions`
    slug: confirm_attendance,
    // BatchExecuteEntityActionRequest
    batchExecuteEntityActionRequest: ...,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies BatchExecuteEntityActionOperationRequest;

  try {
    const data = await api.batchExecuteEntityAction(body);
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
| **slug** | `string` | Action slug, as listed by &#x60;GET /templates/{templateId}/actions&#x60; or &#x60;GET /entities/{id}/actions&#x60; | [Defaults to `undefined`] |
| **batchExecuteEntityActionRequest** | [BatchExecuteEntityActionRequest](BatchExecuteEntityActionRequest.md) |  | |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**BatchExecuteEntityActionResponse**](BatchExecuteEntityActionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Batch applied. One outcome per record in &#x60;results&#x60;; the counters say how many ran. |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | An atomic batch stopped at a record whose precondition does not hold (&#x60;type: error/action-unavailable&#x60;, with &#x60;failed_entity_id&#x60;), or no project is selected |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## batchWriteEntities

> BatchWriteEntitiesResponse batchWriteEntities(batchWriteEntitiesRequest, xOmnismithProjectId)

Apply a batch of mixed entity creates, updates, replaces, and deletes

Applies an ordered, heterogeneous list of entity writes in a single call: update these twenty, create three, replace two, delete one.  This is distinct from CSV import, which moves a homogeneous set of new rows. Use this endpoint when the set of edits is already computed and addresses known records.  Operations: Every entry names an &#x60;op&#x60; and carries exactly the fields for it — nothing more, nothing less: - &#x60;create&#x60;  — &#x60;{ \&quot;op\&quot;: \&quot;create\&quot;, \&quot;template\&quot;: \&quot;&lt;slug|uuid&gt;\&quot;, \&quot;id\&quot;?: \&quot;&lt;uuidv7&gt;\&quot;, \&quot;attributes\&quot;: { ... } }&#x60; (&#x60;attributes&#x60; may be &#x60;{}&#x60;) - &#x60;update&#x60;  — &#x60;{ \&quot;op\&quot;: \&quot;update\&quot;, \&quot;id\&quot;: \&quot;&lt;uuid&gt;\&quot;, \&quot;attributes\&quot;: { ... } }&#x60; (non-empty; partial, like PATCH) - &#x60;replace&#x60; — &#x60;{ \&quot;op\&quot;: \&quot;replace\&quot;, \&quot;id\&quot;: \&quot;&lt;uuid&gt;\&quot;, \&quot;attributes\&quot;: { ... } }&#x60; (like PUT: attributes absent from the map are cleared; &#x60;{}&#x60; clears all; metrics rejected) - &#x60;delete&#x60;  — &#x60;{ \&quot;op\&quot;: \&quot;delete\&quot;, \&quot;id\&quot;: \&quot;&lt;uuid&gt;\&quot; }&#x60; (soft delete)  &#x60;id&#x60; always means the entity id; &#x60;template&#x60; always means the template slug or UUID. See &#x60;BatchOperationInput&#x60;\&#39;s &#x60;attributes&#x60; property for the accepted value shapes.  At most 100 operations per call. Larger sets must be split.  Failure handling: By default (&#x60;atomic: false&#x60;) every operation is attempted, successes stand, and each failure is reported against its index with the same error body the single-entity endpoint would have returned. The response is &#x60;200&#x60; regardless of how many entries failed; read &#x60;failed&#x60; and the per-item &#x60;status&#x60;.  With &#x60;atomic: true&#x60; the whole batch runs in one transaction and the first failure rolls all of it back. That case answers with the failing operation\&#39;s own error status and body plus &#x60;failed_index&#x60;, not with a results list. Atomic batches reject metric attribute values, because metric telemetry is published outside the transaction and cannot be rolled back.  Quotas: Tier quotas are evaluated for the whole batch before any of it is applied, so a batch that would cross the limit is refused as a unit rather than applied halfway.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { BatchWriteEntitiesOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new EntityApi(config);

  const body = {
    // BatchWriteEntitiesRequest
    batchWriteEntitiesRequest: ...,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies BatchWriteEntitiesOperationRequest;

  try {
    const data = await api.batchWriteEntities(body);
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
| **batchWriteEntitiesRequest** | [BatchWriteEntitiesRequest](BatchWriteEntitiesRequest.md) |  | |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**BatchWriteEntitiesResponse**](BatchWriteEntitiesResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Batch applied. Per-item outcomes are in &#x60;results&#x60;; check &#x60;failed&#x60; for partial failure. |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createEntity

> CreateEntity201Response createEntity(template, xOmnismithProjectId, createEntityRequest)

Create a new dynamic entity

Creates one entity of the template named in the path — &#x60;{template}&#x60; is the template\&#39;s slug or UUID — and returns its id. Pass &#x60;id&#x60; to choose the entity\&#39;s UUIDv7 yourself (cross-system keys); otherwise one is generated. An &#x60;id&#x60; that already exists — even a soft-deleted entity\&#39;s — is rejected with &#x60;409&#x60; rather than overwritten: if a retry might be hitting this because an earlier call\&#39;s response was lost, &#x60;GET /entities/{id}&#x60; first to check whether it already carries what you meant to write, rather than retrying blindly.  See the &#x60;attributes&#x60; property for the accepted value shapes.  &#x60;attributes&#x60; is required; send &#x60;{}&#x60; to create an entity with no values yet. Metric attributes in the map are appended to the entity\&#39;s time series; everything else becomes the entity\&#39;s initial state and is recorded in its history.  Errors: - &#x60;400&#x60; — the body is not the documented shape (missing &#x60;attributes&#x60;, a list instead of an object, unknown fields, wrong types). - &#x60;422&#x60; — the shape is right but the content is not: unknown attribute, attribute not on the template, duplicate attribute, bad &#x60;updated_at&#x60;, a value that fails its attribute type, or an operation on an attribute that is not a number. &#x60;errors&#x60; names the exact field, e.g. &#x60;attributes.status&#x60;. - &#x60;404&#x60; — no template with that slug or UUID in this project. - &#x60;409&#x60; — the given &#x60;id&#x60; already exists.

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
    // string | Template UUID or human-readable slug
    template: article,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
    // CreateEntityRequest (optional)
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
| **template** | `string` | Template UUID or human-readable slug | [Defaults to `undefined`] |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
| **createEntityRequest** | [CreateEntityRequest](CreateEntityRequest.md) |  | [Optional] |

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
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **409** | The given &#x60;id&#x60; already exists (&#x60;type: error/conflict&#x60;), or no project is selected |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteEntity

> deleteEntity(id, xOmnismithProjectId)

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## executeEntityAction

> ExecuteEntityActionResponse executeEntityAction(id, slug, xOmnismithProjectId, executeEntityActionRequest)

Execute an action on an entity

Runs one named action on one record as a single atomic write. Prefer this over a plain update (&#x60;PATCH /entities/{id}&#x60;, the &#x60;update_entity&#x60; tool) whenever &#x60;GET /entities/{id}/actions&#x60; (&#x60;list_entity_actions&#x60;) lists an action for what you intend: the action\&#39;s presets are applied for you and its required fields are enforced.  What happens: 1. The action\&#39;s precondition is checked against the record\&#39;s current values — &#x60;409&#x60; if it does not hold, with the reason. 2. &#x60;values&#x60; are matched to the action\&#39;s &#x60;fields&#x60;; an attribute the action does not ask for, or an empty required field, is &#x60;422&#x60; keyed by &#x60;attributes.&lt;slug&gt;&#x60;. 3. Presets are merged on top of &#x60;values&#x60; (presets win) and the result is written exactly like an entity update: attribute types are validated and the template\&#39;s rules are enforced (&#x60;422&#x60; on a violation, in the same &#x60;attributes.&lt;slug&gt;&#x60; shape).  The response is a receipt naming what was written — for a number field sent as &#x60;{ \&quot;op\&quot;: \&quot;increment\&quot;, \&quot;value\&quot;: n }&#x60; that is the operation itself; the resolved number lands in the record and its history. History rows produced by the write carry the action\&#39;s slug.  Errors: - &#x60;400&#x60; — the body is not the documented shape. - &#x60;403&#x60; — the caller may not edit this record. - &#x60;404&#x60; — no such entity, or the template has no enabled action with this slug. - &#x60;409&#x60; — the precondition does not hold; &#x60;detail&#x60; says which attribute and why. - &#x60;422&#x60; — a required field is empty, a value fails its attribute type, or a rule refuses the write.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { ExecuteEntityActionOperationRequest } from '@omnismith-sdk/typescript';

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
    // string | Action slug, as listed by `GET /entities/{id}/actions`
    slug: confirm_attendance,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
    // ExecuteEntityActionRequest (optional)
    executeEntityActionRequest: ...,
  } satisfies ExecuteEntityActionOperationRequest;

  try {
    const data = await api.executeEntityAction(body);
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
| **slug** | `string` | Action slug, as listed by &#x60;GET /entities/{id}/actions&#x60; | [Defaults to `undefined`] |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
| **executeEntityActionRequest** | [ExecuteEntityActionRequest](ExecuteEntityActionRequest.md) |  | [Optional] |

### Return type

[**ExecuteEntityActionResponse**](ExecuteEntityActionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The action ran; the receipt lists what was written |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | The precondition does not hold for this record (&#x60;type: error/action-unavailable&#x60;), or no project is selected |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## exportEntities

> Blob exportEntities(templateId, exportEntitiesRequest, xOmnismithProjectId, sortField, sortDirection)

Export entities to structured CSV file

Exports entity records of a template schema matching filter criteria as a streaming CSV download.  ### Re-importable CSV Schema Format The generated CSV conforms to the Omnismith two-row metadata specification, making it directly compatible with &#x60;POST /entities/import/{template_id}&#x60;: - **Row 1**: Display column names and attribute aliases. - **Row 2**: Metadata row prefixed with &#x60;#&#x60; containing attribute UUIDs and column IDs (e.g. &#x60;#id&#x60;, &#x60;#018b2f1b-8c1a...&#x60;). - **Row 3+**: Entity data records.  Accepts the same &#x60;filter_groups&#x60; and &#x60;global_search&#x60; payload as &#x60;searchEntities&#x60;.  ### Filters (&#x60;filter_groups&#x60;) A list of groups; clauses inside a group are AND-ed, groups are OR-ed. &#x60;[[a, b]]&#x60; is &#x60;a AND b&#x60;; &#x60;[[a], [b, c]]&#x60; is &#x60;a OR (b AND c)&#x60;; &#x60;[]&#x60; applies no filter. &#x60;&#x60;&#x60;json [   [     {\&quot;field\&quot;: \&quot;status\&quot;, \&quot;operator\&quot;: \&quot;in\&quot;, \&quot;value\&quot;: [\&quot;018b…0020\&quot;, \&quot;018b…0021\&quot;]},     {\&quot;field\&quot;: \&quot;created_at\&quot;, \&quot;operator\&quot;: \&quot;between\&quot;, \&quot;value\&quot;: [\&quot;2026-01-01\&quot;, \&quot;2026-03-31\&quot;]},     {\&quot;field\&quot;: \&quot;customer.tier\&quot;, \&quot;operator\&quot;: \&quot;eq\&quot;, \&quot;value\&quot;: \&quot;018b…0042\&quot;}   ],   [{\&quot;field\&quot;: \&quot;priority\&quot;, \&quot;operator\&quot;: \&quot;eq\&quot;, \&quot;value\&quot;: \&quot;018b…0007\&quot;}] ] &#x60;&#x60;&#x60; - **&#x60;field&#x60;**: attribute slug or UUID, a standard field (&#x60;id&#x60;, &#x60;created_at&#x60;, &#x60;updated_at&#x60;), or a one-hop path &#x60;&lt;reference&gt;.&lt;attribute&gt;&#x60; that filters on an attribute of the referenced record (e.g. &#x60;customer.tier&#x60;). One hop only. - **&#x60;operator&#x60;** and **&#x60;value&#x60;**: &#x60;eq&#x60;, &#x60;neq&#x60;, &#x60;gt&#x60;, &#x60;lt&#x60;, &#x60;like&#x60; (case-insensitive substring), &#x60;not-like&#x60; take a string; &#x60;in&#x60;, &#x60;not-in&#x60; take a non-empty list of strings; &#x60;between&#x60; takes &#x60;[lower, upper]&#x60; (inclusive; number, date, datetime attributes and &#x60;created_at&#x60; / &#x60;updated_at&#x60;); &#x60;empty&#x60;, &#x60;not-empty&#x60; take no value. - List and reference attributes compare the stored id (from &#x60;list_item_ids&#x60; / &#x60;reference_entity_ids&#x60; or the schema), never the label. - Unknown fields, operators that do not fit the field, malformed values and paths that do not traverse a reference are refused with 400 naming the valid fields; a path into a template the caller may not view is 403.  ### Sorting Sort results via &#x60;sort_field&#x60; (attribute UUID, slug, or standard timestamp) and &#x60;sort_direction&#x60; (&#x60;asc&#x60;/&#x60;desc&#x60;).

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntity

> EntityResponse getEntity(id, xOmnismithProjectId, verbose, fields)

Get an entity record by ID

Retrieves the full hydrated record for a dynamic entity by its unique identifier (UUID). See &#x60;verbose&#x60; and &#x60;fields&#x60; for response shape and projection options.

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
    // boolean | When true, attribute_values is an array of EntityAttributeValue items with attribute id, slug, raw value, resolved custom_value and reference_entity_id. When false (default), attribute_values is a compact object mapping attribute slug to display value, with the ids behind list, reference and file labels in list_item_ids, reference_entity_ids and file_ids. (optional)
    verbose: false,
    // Array<string> | Attribute slugs or UUIDs to project, e.g. [\"title\", \"status\"]. Standard fields (id, template_id, template_slug, created_at, updated_at) are always included and do not need to be listed. When specified, only the requested attributes are fetched and returned in attribute_values, avoiding database hydration for unneeded attributes and significantly reducing response payload size. If omitted, all attributes defined on the template are returned. (optional)
    fields: ["title","status"],
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
| **verbose** | `boolean` | When true, attribute_values is an array of EntityAttributeValue items with attribute id, slug, raw value, resolved custom_value and reference_entity_id. When false (default), attribute_values is a compact object mapping attribute slug to display value, with the ids behind list, reference and file labels in list_item_ids, reference_entity_ids and file_ids. | [Optional] [Defaults to `false`] |
| **fields** | `Array<string>` | Attribute slugs or UUIDs to project, e.g. [\&quot;title\&quot;, \&quot;status\&quot;]. Standard fields (id, template_id, template_slug, created_at, updated_at) are always included and do not need to be listed. When specified, only the requested attributes are fetched and returned in attribute_values, avoiding database hydration for unneeded attributes and significantly reducing response payload size. If omitted, all attributes defined on the template are returned. | [Optional] |

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
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntityChart

> GetEntityChart200Response getEntityChart(id, attributeIds, start, end, xOmnismithProjectId, aggregateFunc, bucketWidth)

Get entity chart time-series data

Retrieves aggregated, time-bucketed metric time-series data for an entity. Returns one &#x60;series&#x60; entry per requested &#x60;attribute_id&#x60;, each a chronological list of &#x60;{time, value}&#x60; points aggregated at the given &#x60;bucket_width&#x60;.

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntityHistory

> GetEntityHistory200Response getEntityHistory(id, xOmnismithProjectId, page, limit, sortBy, sortDirection, search, attributeIds, start, end, authorEmail)

Get entity dimension change history

Retrieves the immutable change audit log for an entity\&#39;s dimension attribute mutations. Records mutations to dimension, list, and reference attribute values; metric telemetry is excluded and lives in time-series storage instead (see &#x60;get_entity_chart&#x60;). Returns paginated &#x60;items&#x60; (each an attribute change from &#x60;old_value&#x60; to &#x60;value&#x60;, with &#x60;author_email&#x60; and &#x60;action_slug&#x60; when the write came from an action) plus &#x60;total&#x60; matching records.

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## importEntities

> ImportEntities200Response importEntities(templateId, file, xOmnismithProjectId)

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## ingestEntityMetrics

> ingestEntityMetrics(id, ingestMetricsRequest, xOmnismithProjectId)

Ingest high-frequency metric observations for an entity

Ingests time-series metric observations for an entity record.  Batch Telemetry Ingestion: Accepts a batch array of metric observations (&#x60;metric_values&#x60;). Each observation targets a metric attribute by &#x60;attribute_id&#x60; (UUID) or &#x60;attribute_slug&#x60; and specifies a numeric &#x60;value&#x60;.  Ingestion is asynchronous: a call is accepted immediately (&#x60;202&#x60;) and each observation is persisted shortly after, so it may not be visible in &#x60;get_entity_chart&#x60; the instant this call returns.  Strict Metric Attribute Constraint: Only attributes defined with &#x60;attribute_type: Metric&#x60; are accepted by this endpoint. Mutations to dimension, list, or reference attributes must use &#x60;PATCH /entities/{id}&#x60; instead.

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listEntityActions

> ListEntityActions200Response listEntityActions(id, xOmnismithProjectId)

List the actions available on an entity

The enabled actions of the entity\&#39;s template, each evaluated against the record\&#39;s current values.  Call this before changing a record: when an action exists for what you intend (a status transition, a hand-off), run it with &#x60;POST /entities/{id}/actions/{slug}&#x60; (the &#x60;execute_entity_action&#x60; tool) instead of a plain update (&#x60;update_entity&#x60;), so its presets and required fields apply.  Each entry says whether the action is &#x60;available&#x60; now and, if not, &#x60;unavailable_reason&#x60; names the attribute, the expectation and the current value. &#x60;fields&#x60; are the values to submit (keyed by &#x60;slug&#x60; in the execute body), with the list choices and reference target resolved; &#x60;presets&#x60; are what the action will set on its own.  Disabled actions are not listed. Read-only: nothing is written.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { ListEntityActionsRequest } from '@omnismith-sdk/typescript';

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies ListEntityActionsRequest;

  try {
    const data = await api.listEntityActions(body);
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**ListEntityActions200Response**](ListEntityActions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Actions of the entity\&#39;s template with per-record availability, in display order |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## replaceEntity

> replaceEntity(id, replaceEntityRequest, xOmnismithProjectId)

Replace all non-metric attributes of an entity

Full replacement: after this call the entity\&#39;s dimension attributes are exactly the map you sent. Every non-metric attribute of the template that is **absent from the map is cleared**. Use PATCH unless you really mean \&quot;make the record look exactly like this\&quot;.  ### &#x60;attributes&#x60; An object keyed by attribute **slug or UUID** — mix them freely. Each value is a plain scalar, a backfill object &#x60;{ \&quot;value\&quot;: ..., \&quot;updated_at\&quot;: \&quot;&lt;RFC 3339&gt;\&quot; }&#x60;, or an operation object &#x60;{ \&quot;op\&quot;: \&quot;increment\&quot;, \&quot;value\&quot;: &lt;number&gt; }&#x60;:  &#x60;&#x60;&#x60;json {   \&quot;hostname\&quot;: \&quot;edge-fra-01\&quot;,   \&quot;cpu_cores\&quot;: 8,   \&quot;is_active\&quot;: true,   \&quot;notes\&quot;: null,   \&quot;01a094f1-24be-7154-a5bd-3b5c33c930fb\&quot;: \&quot;01a094f1-4c1d-7498-b73b-48ae46da900b\&quot;,   \&quot;operational_status\&quot;: { \&quot;value\&quot;: \&quot;Active\&quot;, \&quot;updated_at\&quot;: \&quot;2026-09-12T12:23:52Z\&quot; },   \&quot;restart_count\&quot;: { \&quot;op\&quot;: \&quot;increment\&quot;, \&quot;value\&quot;: 1 } } &#x60;&#x60;&#x60;  &#x60;null&#x60; clears an attribute. &#x60;{ \&quot;op\&quot;: \&quot;increment\&quot;, \&quot;value\&quot;: n }&#x60; adds &#x60;n&#x60; to the stored number without you reading it first (number attributes and metrics only; concurrent increments never lose an update). Every attribute must belong to the entity\&#39;s template and may appear only once (the same attribute as slug *and* UUID is rejected). Full value rules are on the &#x60;EntityAttributesInput&#x60; schema.  &#x60;attributes&#x60; is required; an explicit &#x60;{}&#x60; clears every non-metric attribute. Metric attributes are append-only telemetry and cannot be replaced — including one in the map is a &#x60;422&#x60;; send it via PATCH or &#x60;/entities/{id}/metrics&#x60;.  Errors: - &#x60;400&#x60; — the body is not the documented shape (missing &#x60;attributes&#x60;, a list instead of an object, unknown fields, wrong types). - &#x60;422&#x60; — the shape is right but the content is not: unknown attribute, attribute not on the template, duplicate attribute, bad &#x60;updated_at&#x60;, a value that fails its attribute type, or an operation on an attribute that is not a number. &#x60;errors&#x60; names the exact field, e.g. &#x60;attributes.status&#x60;. - &#x60;404&#x60; — no entity with that id.

### Example

```ts
import {
  Configuration,
  EntityApi,
} from '@omnismith-sdk/typescript';
import type { ReplaceEntityOperationRequest } from '@omnismith-sdk/typescript';

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
    // ReplaceEntityRequest
    replaceEntityRequest: ...,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies ReplaceEntityOperationRequest;

  try {
    const data = await api.replaceEntity(body);
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
| **replaceEntityRequest** | [ReplaceEntityRequest](ReplaceEntityRequest.md) |  | |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **204** | Entity attributes replaced successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchEntities

> SearchEntities200Response searchEntities(templateId, searchEntitiesRequest, xOmnismithProjectId, limit, offset, sortField, sortDirection)

Search entities with filtering, sorting, and pagination

Executes structured queries, full-text search, and sorting across dynamic entities of a template (&#x60;template_id&#x60; accepts a UUID or a human-readable slug). See &#x60;filter_groups&#x60;, &#x60;global_search&#x60;, &#x60;verbose&#x60;, &#x60;fields&#x60;, &#x60;sort_field&#x60; and &#x60;sort_direction&#x60; for the query and response-shape options. Use &#x60;aggregate_entities&#x60; instead of paginating through results when you only need counts, sums, or other per-group reduces.

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
    // number | Maximum number of entity records to return (1-100) (optional)
    limit: 50,
    // number | Zero-based pagination offset (optional)
    offset: 0,
    // string | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by (optional)
    sortField: created_at,
    // 'asc' | 'desc' | Sort direction: \"asc\" (ascending) or \"desc\" (descending) (optional)
    sortDirection: desc,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
| **limit** | `number` | Maximum number of entity records to return (1-100) | [Optional] [Defaults to `50`] |
| **offset** | `number` | Zero-based pagination offset | [Optional] [Defaults to `0`] |
| **sortField** | `string` | Attribute UUID, attribute slug, or standard field (id, created_at, updated_at, deleted_at) to sort by | [Optional] [Defaults to `undefined`] |
| **sortDirection** | `asc`, `desc` | Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [Optional] [Defaults to `&#39;asc&#39;`] [Enum: asc, desc] |

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
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## semanticSearchEntities

> Array&lt;SemanticSearchResultItem&gt; semanticSearchEntities(semanticSearchEntitiesRequest, xOmnismithProjectId)

Perform semantic vector similarity search on entities

Executes an approximate nearest neighbors (ANN) vector similarity search across entity dimension embeddings.  ### 768-Dimensional Embedding Vectors Requires a 768-dimensional float embedding array (&#x60;query_vector&#x60;) representing the query text or multimodal vector (e.g. generated by Google &#x60;text-embedding-004&#x60; or similar models).  ### Scoping &amp; Filtering (&#x60;template_id&#x60;) Pass an optional &#x60;template_id&#x60; (UUID) or template slug to constrain the semantic search to records belonging to a specific template schema.  ### Cosine Similarity Threshold &amp; Ranking (&#x60;threshold&#x60;) - &#x60;threshold&#x60;: Minimum cosine similarity score threshold (range &#x60;0.0&#x60; to &#x60;1.0&#x60;, default &#x60;0.5&#x60;). Observations below this similarity cutoff are discarded. - Matches are returned strictly ranked in descending order of &#x60;similarity_score&#x60;.  ### Attribute Values Shape (&#x60;verbose&#x60;) By default each nested entity\&#39;s &#x60;attribute_values&#x60; is a compact object mapping attribute slug to display value, with the ids behind list, reference and file labels in &#x60;list_item_ids&#x60;, &#x60;reference_entity_ids&#x60; and &#x60;file_ids&#x60;. Set &#x60;\&quot;verbose\&quot;: true&#x60; to receive an array of &#x60;EntityAttributeValue&#x60; items with attribute &#x60;id&#x60;, &#x60;slug&#x60;, raw &#x60;value&#x60;, resolved &#x60;custom_value&#x60; and &#x60;reference_entity_id&#x60; instead.

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateEntity

> updateEntity(id, updateEntityRequest, xOmnismithProjectId)

Update entity attribute values

Partial update: writes the attributes in the map and leaves every other attribute untouched. This is the default way to change an entity. See the &#x60;attributes&#x60; property for the accepted value shapes.  &#x60;attributes&#x60; is required and must not be empty. Dimension changes are appended to the entity\&#39;s history (unchanged values cost nothing); metric attributes are appended to the entity\&#39;s time series.  Errors: - &#x60;400&#x60; — the body is not the documented shape (missing &#x60;attributes&#x60;, a list instead of an object, unknown fields, wrong types). - &#x60;422&#x60; — the shape is right but the content is not: unknown attribute, attribute not on the template, duplicate attribute, bad &#x60;updated_at&#x60;, a value that fails its attribute type, or an operation on an attribute that is not a number. &#x60;errors&#x60; names the exact field, e.g. &#x60;attributes.status&#x60;. - &#x60;404&#x60; — no entity with that id.

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

