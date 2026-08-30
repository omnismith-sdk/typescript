# MCPApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createAttribute**](MCPApi.md#createattributeoperation) | **POST** /attributes | Create a new attribute |
| [**createAttributeItem**](MCPApi.md#createattributeitem) | **POST** /attributes/{id}/items | Add a list item to an attribute |
| [**createAutomation**](MCPApi.md#createautomationoperation) | **POST** /automation/automations | Create an automation rule |
| [**createDashboard**](MCPApi.md#createdashboardoperation) | **POST** /dashboards | Create a new dashboard |
| [**createDashboardBlock**](MCPApi.md#createdashboardblockoperation) | **POST** /dashboards/{dashboardId}/blocks | Create a new block in a dashboard |
| [**createEntity**](MCPApi.md#createentityoperation) | **POST** /entities | Create a new dynamic entity |
| [**createNotificationChannel**](MCPApi.md#createnotificationchanneloperation) | **POST** /automation/notification-channels | Create a notification channel |
| [**createTemplate**](MCPApi.md#createtemplateoperation) | **POST** /templates | Create a new template |
| [**createWorkspace**](MCPApi.md#createworkspaceoperation) | **POST** /workspaces | Create a new workspace |
| [**createWorkspaceView**](MCPApi.md#createworkspaceviewoperation) | **POST** /workspaces/{id}/views | Add a new view / pane to a workspace |
| [**deleteAttribute**](MCPApi.md#deleteattribute) | **DELETE** /attributes/{id} | Delete an attribute |
| [**deleteAttributeReferenceConfig**](MCPApi.md#deleteattributereferenceconfig) | **DELETE** /attributes/{id}/reference | Delete reference configuration for an attribute |
| [**deleteAutomation**](MCPApi.md#deleteautomation) | **DELETE** /automation/automations/{id} | Delete an automation |
| [**deleteDashboard**](MCPApi.md#deletedashboard) | **DELETE** /dashboards/{id} | Delete a dashboard |
| [**deleteDashboardBlock**](MCPApi.md#deletedashboardblock) | **DELETE** /dashboards/{dashboardId}/blocks/{blockId} | Delete a dashboard block |
| [**deleteEntity**](MCPApi.md#deleteentity) | **DELETE** /entities/{id} | Soft-delete an entity record |
| [**deleteNotificationChannel**](MCPApi.md#deletenotificationchannel) | **DELETE** /automation/notification-channels/{id} | Delete a notification channel |
| [**deleteTemplate**](MCPApi.md#deletetemplate) | **DELETE** /templates/{id} | Delete a template |
| [**deleteWorkspace**](MCPApi.md#deleteworkspace) | **DELETE** /workspaces/{id} | Delete a workspace and its views |
| [**deleteWorkspaceView**](MCPApi.md#deleteworkspaceview) | **DELETE** /workspaces/{id}/views/{viewId} | Delete a view / pane from a workspace |
| [**getAttribute**](MCPApi.md#getattribute) | **GET** /attributes/{id} | Get an attribute by ID |
| [**getAttributeReferenceConfig**](MCPApi.md#getattributereferenceconfig) | **GET** /attributes/{id}/reference | Get reference configuration for an attribute |
| [**getAutomation**](MCPApi.md#getautomation) | **GET** /automation/automations/{id} | Get an automation by ID |
| [**getDashboard**](MCPApi.md#getdashboard) | **GET** /dashboards/{id} | Get a dashboard by ID |
| [**getDashboardBlock**](MCPApi.md#getdashboardblock) | **GET** /dashboards/{dashboardId}/blocks/{blockId} | Get a dashboard block by ID |
| [**getEntity**](MCPApi.md#getentity) | **GET** /entities/{id} | Get an entity record by ID |
| [**getEntityChart**](MCPApi.md#getentitychart) | **GET** /entities/{id}/chart | Get entity chart time-series data |
| [**getEntityHistory**](MCPApi.md#getentityhistory) | **GET** /entities/{id}/history | Get entity dimension change history |
| [**getMarketplaceBlueprint**](MCPApi.md#getmarketplaceblueprint) | **GET** /marketplace/blueprints/{id} | Get marketplace blueprint details |
| [**getNotificationChannel**](MCPApi.md#getnotificationchannel) | **GET** /automation/notification-channels/{id} | Get a notification channel by ID |
| [**getProjectSchema**](MCPApi.md#getprojectschema) | **GET** /discovery/project-schema | Get complete project schema graph |
| [**getTemplate**](MCPApi.md#gettemplate) | **GET** /templates/{id} | Get a template by ID or slug |
| [**getUsageInsights**](MCPApi.md#getusageinsights) | **GET** /billing/usage/insights | Get current tier usage insights |
| [**getWorkspace**](MCPApi.md#getworkspace) | **GET** /workspaces/{id} | Get workspace details and its views |
| [**getWorkspaceView**](MCPApi.md#getworkspaceview) | **GET** /workspaces/{id}/views/{viewId} | Get details of a workspace view / pane |
| [**ingestEntityMetrics**](MCPApi.md#ingestentitymetrics) | **POST** /entities/{id}/metrics | Ingest high-frequency metric observations for an entity |
| [**installMarketplaceBlueprint**](MCPApi.md#installmarketplaceblueprintoperation) | **POST** /marketplace/blueprints/{id}/install | Install a marketplace blueprint into a project |
| [**listAttributeItems**](MCPApi.md#listattributeitems) | **GET** /attributes/{id}/items | List items of an attribute |
| [**listAttributes**](MCPApi.md#listattributes) | **GET** /attributes | List all attributes |
| [**listAuditLogs**](MCPApi.md#listauditlogs) | **GET** /audit-logs | List project audit logs |
| [**listAutomations**](MCPApi.md#listautomations) | **GET** /automation/automations | List project automations |
| [**listDashboardBlocks**](MCPApi.md#listdashboardblocks) | **GET** /dashboards/{dashboardId}/blocks | List all blocks in a dashboard |
| [**listDashboards**](MCPApi.md#listdashboards) | **GET** /dashboards | List all dashboards |
| [**listNotificationChannels**](MCPApi.md#listnotificationchannels) | **GET** /automation/notification-channels | List notification channels |
| [**listTemplateEntityCounts**](MCPApi.md#listtemplateentitycounts) | **GET** /templates/entity-counts | List entity counts per template |
| [**listTemplates**](MCPApi.md#listtemplates) | **GET** /templates | List all templates |
| [**listWorkspaces**](MCPApi.md#listworkspaces) | **GET** /workspaces | List all workspaces for current project |
| [**patchAttribute**](MCPApi.md#patchattributeoperation) | **PATCH** /attributes/{id} | Patch an attribute (granular partial update) |
| [**patchTemplate**](MCPApi.md#patchtemplateoperation) | **PATCH** /templates/{id} | Patch a template (granular partial update) |
| [**resolveDashboardBlock**](MCPApi.md#resolvedashboardblock) | **GET** /dashboards/{dashboardId}/blocks/{blockId}/resolve | Resolve a dashboard block to its computed data |
| [**searchEntities**](MCPApi.md#searchentitiesoperation) | **POST** /entities/search/{template_id} | Search entities with filtering, sorting, and pagination |
| [**searchMarketplaceBlueprints**](MCPApi.md#searchmarketplaceblueprints) | **GET** /marketplace/blueprints | Search marketplace blueprints |
| [**setAttributeItems**](MCPApi.md#setattributeitems) | **PUT** /attributes/{id}/items | Set list items for an attribute (replaces all existing items) |
| [**setAttributeReferenceConfig**](MCPApi.md#setattributereferenceconfig) | **PUT** /attributes/{id}/reference | Set or update reference configuration for an attribute |
| [**testNotificationChannel**](MCPApi.md#testnotificationchanneloperation) | **POST** /automation/notification-channels/{id}/test | Send a test notification message |
| [**toggleAutomation**](MCPApi.md#toggleautomationoperation) | **PATCH** /automation/automations/{id}/toggle | Toggle automation enabled status |
| [**updateAttribute**](MCPApi.md#updateattributeoperation) | **PUT** /attributes/{id} | Update an attribute (full replacement) |
| [**updateAutomation**](MCPApi.md#updateautomationoperation) | **PUT** /automation/automations/{id} | Update an automation |
| [**updateDashboard**](MCPApi.md#updatedashboardoperation) | **PUT** /dashboards/{id} | Update a dashboard |
| [**updateDashboardBlock**](MCPApi.md#updatedashboardblockoperation) | **PUT** /dashboards/{dashboardId}/blocks/{blockId} | Update a dashboard block |
| [**updateEntity**](MCPApi.md#updateentityoperation) | **PATCH** /entities/{id} | Update entity attribute values |
| [**updateNotificationChannel**](MCPApi.md#updatenotificationchanneloperation) | **PUT** /automation/notification-channels/{id} | Update a notification channel |
| [**updateTemplate**](MCPApi.md#updatetemplateoperation) | **PUT** /templates/{id} | Update a template (full replacement) |
| [**updateWorkspace**](MCPApi.md#updateworkspaceoperation) | **PUT** /workspaces/{id} | Update workspace metadata and layout |
| [**updateWorkspaceView**](MCPApi.md#updateworkspaceviewoperation) | **PUT** /workspaces/{id}/views/{viewId} | Update workspace view / pane filters, sort, display mode, or columns |



## createAttribute

> CreateAttribute201Response createAttribute(createAttributeRequest)

Create a new attribute

Defines a new attribute in the project schema. Attributes can be of kind Dimension (0), Metric (1), List (2), or Reference (3). Specify the storage data type (String: 0, Number: 1, Boolean: 2, Datetime: 3, Date: 4, File: 5, Image: 6, Markdown: 7), name, optional project-unique slug (auto-generated from name if omitted), optional template associations, and an optional reference_config if kind is Reference (3). Subject to project tier quota constraints.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateAttributeOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // CreateAttributeRequest
    createAttributeRequest: ...,
  } satisfies CreateAttributeOperationRequest;

  try {
    const data = await api.createAttribute(body);
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
| **createAttributeRequest** | [CreateAttributeRequest](CreateAttributeRequest.md) |  | |

### Return type

[**CreateAttribute201Response**](CreateAttribute201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Attribute successfully created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **409** | Conflict |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createAttributeItem

> CreateAttributeItem201Response createAttributeItem(id, addListItemRequest)

Add a list item to an attribute

Appends a single selectable choice option item to a List-type (attribute_type &#x3D; 2) attribute. Returns the generated or assigned UUID of the newly created list item.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateAttributeItemRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the List-type attribute
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // AddListItemRequest
    addListItemRequest: ...,
  } satisfies CreateAttributeItemRequest;

  try {
    const data = await api.createAttributeItem(body);
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
| **id** | `string` | UUID of the List-type attribute | [Defaults to `undefined`] |
| **addListItemRequest** | [AddListItemRequest](AddListItemRequest.md) |  | |

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
| **201** | List item created successfully |  -  |
| **400** | Bad Request - Attribute is not a List type |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createAutomation

> CreateAutomation201Response createAutomation(createAutomationRequest)

Create an automation rule

Creates a new event-driven automation rule within the current project. Configures event trigger criteria (such as &#x60;on_entity_created&#x60;, &#x60;on_entity_updated&#x60;, or &#x60;on_attribute_changed&#x60;), multi-condition filters evaluating attribute values (using operators &#x60;eq&#x60;, &#x60;neq&#x60;, &#x60;gt&#x60;, &#x60;gte&#x60;, &#x60;lt&#x60;, &#x60;lte&#x60;, &#x60;contains&#x60;, &#x60;not_contains&#x60;, &#x60;is_empty&#x60;, &#x60;is_not_empty&#x60; across current value or delta modes), automated action targets (&#x60;telegram&#x60;, &#x60;webhook&#x60;, &#x60;push&#x60;), and an optional cooldown window in seconds to throttle repeated firings for the same entity.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateAutomationOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // CreateAutomationRequest
    createAutomationRequest: ...,
  } satisfies CreateAutomationOperationRequest;

  try {
    const data = await api.createAutomation(body);
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
| **createAutomationRequest** | [CreateAutomationRequest](CreateAutomationRequest.md) |  | |

### Return type

[**CreateAutomation201Response**](CreateAutomation201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Automation successfully created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createDashboard

> CreateDashboard201Response createDashboard(createDashboardRequest)

Create a new dashboard

Creates a new analytics and telemetry dashboard canvas for organizing metric KPIs, charts, gauges, and entity tables within a customizable grid layout.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateDashboardOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // CreateDashboardRequest | Dashboard creation payload
    createDashboardRequest: ...,
  } satisfies CreateDashboardOperationRequest;

  try {
    const data = await api.createDashboard(body);
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
| **createDashboardRequest** | [CreateDashboardRequest](CreateDashboardRequest.md) | Dashboard creation payload | |

### Return type

[**CreateDashboard201Response**](CreateDashboard201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Dashboard created successfully |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createDashboardBlock

> CreateDashboardBlock201Response createDashboardBlock(dashboardId, createDashboardBlockRequest)

Create a new block in a dashboard

Creates a new visualization block widget on a dashboard canvas. Supports four block types: stat (single KPI counter of matching entities), chart (time-series telemetry multi-line/bar graph aggregating metric data), gauge (metric threshold gauge with min/max bounds and percentage progress), and list (filtered and sorted entity table). Grid placement is defined via x, y, cols, rows layout parameters.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateDashboardBlockOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Target dashboard unique identifier (UUID)
    dashboardId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // CreateDashboardBlockRequest | Dashboard block creation payload
    createDashboardBlockRequest: ...,
  } satisfies CreateDashboardBlockOperationRequest;

  try {
    const data = await api.createDashboardBlock(body);
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
| **dashboardId** | `string` | Target dashboard unique identifier (UUID) | [Defaults to `undefined`] |
| **createDashboardBlockRequest** | [CreateDashboardBlockRequest](CreateDashboardBlockRequest.md) | Dashboard block creation payload | |

### Return type

[**CreateDashboardBlock201Response**](CreateDashboardBlock201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Dashboard block created successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createEntity

> CreateEntity201Response createEntity(createEntityRequest)

Create a new dynamic entity

Creates a new dynamic entity record conforming to a template schema.  ### Template Association Specify the target schema via either &#x60;template_id&#x60; (UUID) or &#x60;template_slug&#x60; (human-readable slug).  ### Dynamic Attribute Values (&#x60;attribute_values&#x60;) Each attribute entry supports identifier resolution and accepts either: - &#x60;attribute_id&#x60;: Canonical attribute UUID - &#x60;attribute_slug&#x60;: Attribute slug identifier (e.g. &#x60;price&#x60;, &#x60;sku&#x60;, &#x60;status&#x60;)  ### Value Formatting Rules - **Dimension - Text / Markdown**: UTF-8 string value (e.g., &#x60;\&quot;Wireless Headphones\&quot;&#x60;) - **Dimension - Number**: Numeric string representation (e.g., &#x60;\&quot;129.99\&quot;&#x60;, &#x60;\&quot;42\&quot;&#x60;) - **Dimension - Boolean**: Strict boolean representation: &#x60;\&quot;true\&quot;&#x60;, &#x60;\&quot;false\&quot;&#x60;, &#x60;\&quot;1\&quot;&#x60;, or &#x60;\&quot;0\&quot;&#x60; - **Dimension - Date &amp; Datetime**: Formatted as &#x60;YYYY-MM-DD&#x60; (date) or &#x60;YYYY-MM-DD HH:MM:SS&#x60; / ISO 8601 &#x60;YYYY-MM-DDTHH:MM:SSZ&#x60; (datetime) - **Dimension - File &amp; Image**: UUID string of a pre-uploaded workspace file asset - **List Attribute**: Must provide the exact UUID string of a valid defined &#x60;ListItem&#x60; option - **Reference Attribute**: Must provide the exact UUID string of an existing referenced &#x60;Entity&#x60;  ### Metric Telemetry Persistence Any metric attributes included in &#x60;attribute_values&#x60; are published directly to the metric ingestion pipeline and recorded in time-series telemetry storage.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateEntityOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

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


## createNotificationChannel

> CreateNotificationChannel201Response createNotificationChannel(createNotificationChannelRequest)

Create a notification channel

Registers a new external notification channel for the current project. Channels can be of type &#x60;telegram&#x60; (configured with a Telegram bot token), &#x60;webhook&#x60; (configured with endpoint URL, custom HTTP headers, and authentication methods such as bearer token or basic auth), or &#x60;push&#x60; (FCM mobile push notifications). Configured channels can then be linked as target actions in automation rules.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateNotificationChannelOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // CreateNotificationChannelRequest
    createNotificationChannelRequest: ...,
  } satisfies CreateNotificationChannelOperationRequest;

  try {
    const data = await api.createNotificationChannel(body);
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
| **createNotificationChannelRequest** | [CreateNotificationChannelRequest](CreateNotificationChannelRequest.md) |  | |

### Return type

[**CreateNotificationChannel201Response**](CreateNotificationChannel201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Notification channel successfully created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createTemplate

> CreateTemplate201Response createTemplate(createTemplateRequest)

Create a new template

Creates a new dynamic schema template (content type) in the project. Accepts template name, optional description, category, unique slug, attribute bindings, and UI layout groups. Attribute bindings can be defined using structured &#x60;attributes&#x60; (with optional &#x60;default_value&#x60; validated against attribute kind/data type) or flat &#x60;attribute_ids&#x60; / &#x60;attribute_slugs&#x60;. Visual layout groups organize attributes into 1- or 2-column sections with optional icons. Creating templates is subject to tier quota limits.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateTemplateOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // CreateTemplateRequest
    createTemplateRequest: ...,
  } satisfies CreateTemplateOperationRequest;

  try {
    const data = await api.createTemplate(body);
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
| **createTemplateRequest** | [CreateTemplateRequest](CreateTemplateRequest.md) |  | |

### Return type

[**CreateTemplate201Response**](CreateTemplate201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Template successfully created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **409** | Conflict |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createWorkspace

> CreateDashboard201Response createWorkspace(createWorkspaceRequest)

Create a new workspace

Creates a new workspace in the current project context with a specified multi-pane layout (single, split-v, split-h, quad), optional default workspace status, and initial template view bindings to automatically generate panes.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateWorkspaceOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // CreateWorkspaceRequest | Workspace creation payload
    createWorkspaceRequest: ...,
  } satisfies CreateWorkspaceOperationRequest;

  try {
    const data = await api.createWorkspace(body);
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
| **createWorkspaceRequest** | [CreateWorkspaceRequest](CreateWorkspaceRequest.md) | Workspace creation payload | |

### Return type

[**CreateDashboard201Response**](CreateDashboard201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Workspace created successfully |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createWorkspaceView

> CreateDashboardBlock201Response createWorkspaceView(id, createWorkspaceViewRequest)

Add a new view / pane to a workspace

Creates and mounts a new view pane within an existing workspace bound to a specific entity schema template, configuring presentation mode (table, grid), visible columns, filter criteria, search queries (keyword or semantic), sorting preferences, and pane order.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { CreateWorkspaceViewOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Target workspace unique identifier (UUID)
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // CreateWorkspaceViewRequest | Workspace view creation payload
    createWorkspaceViewRequest: ...,
  } satisfies CreateWorkspaceViewOperationRequest;

  try {
    const data = await api.createWorkspaceView(body);
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
| **id** | `string` | Target workspace unique identifier (UUID) | [Defaults to `undefined`] |
| **createWorkspaceViewRequest** | [CreateWorkspaceViewRequest](CreateWorkspaceViewRequest.md) | Workspace view creation payload | |

### Return type

[**CreateDashboardBlock201Response**](CreateDashboardBlock201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Workspace view created successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAttribute

> deleteAttribute(id)

Delete an attribute

Soft-deletes an attribute from the project schema. Soft-deleted attributes are removed from active template projections and future queries, while existing historical dimension and telemetry records remain preserved for audit integrity.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteAttributeRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the attribute to delete
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
  } satisfies DeleteAttributeRequest;

  try {
    const data = await api.deleteAttribute(body);
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
| **id** | `string` | UUID of the attribute to delete | [Defaults to `undefined`] |

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
| **204** | Attribute deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAttributeReferenceConfig

> deleteAttributeReferenceConfig(id)

Delete reference configuration for an attribute

Removes the foreign entity reference configuration mapping from a Reference-type (attribute_type &#x3D; 3) attribute.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteAttributeReferenceConfigRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the Reference attribute
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
  } satisfies DeleteAttributeReferenceConfigRequest;

  try {
    const data = await api.deleteAttributeReferenceConfig(body);
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
| **id** | `string` | UUID of the Reference attribute | [Defaults to `undefined`] |

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
| **204** | Reference configuration deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAutomation

> deleteAutomation(id)

Delete an automation

Permanently deletes an automation rule by UUID, unbinding event listeners and stopping all future evaluations and action dispatches for that rule.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteAutomationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Unique automation UUID to delete
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60001,
  } satisfies DeleteAutomationRequest;

  try {
    const data = await api.deleteAutomation(body);
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
| **id** | `string` | Unique automation UUID to delete | [Defaults to `undefined`] |

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
| **204** | Automation successfully deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Automation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteDashboard

> deleteDashboard(id)

Delete a dashboard

Permanently removes a dashboard and all attached visualization blocks, metric widgets, and configurations.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteDashboardRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Dashboard unique identifier (UUID) to delete
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  } satisfies DeleteDashboardRequest;

  try {
    const data = await api.deleteDashboard(body);
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
| **id** | `string` | Dashboard unique identifier (UUID) to delete | [Defaults to `undefined`] |

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
| **204** | Dashboard deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteDashboardBlock

> deleteDashboardBlock(dashboardId, blockId)

Delete a dashboard block

Permanently removes a visualization block widget from the specified dashboard canvas.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteDashboardBlockRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Parent dashboard unique identifier (UUID)
    dashboardId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // string | Dashboard block unique identifier (UUID) to delete
    blockId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  } satisfies DeleteDashboardBlockRequest;

  try {
    const data = await api.deleteDashboardBlock(body);
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
| **dashboardId** | `string` | Parent dashboard unique identifier (UUID) | [Defaults to `undefined`] |
| **blockId** | `string` | Dashboard block unique identifier (UUID) to delete | [Defaults to `undefined`] |

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
| **204** | Dashboard block deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteEntity

> deleteEntity(id)

Soft-delete an entity record

Marks an entity record as soft-deleted by setting its &#x60;deleted_at&#x60; timestamp.  Soft-deleted entities are immediately excluded from standard entity searches, BI row queries, and direct retrieval endpoints. Associated historical change logs and time-series telemetry remain preserved for audit compliance.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteEntityRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

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


## deleteNotificationChannel

> deleteNotificationChannel(id)

Delete a notification channel

Permanently removes a notification channel from the project by UUID. Automations referencing this channel must be updated to prevent dispatch delivery failures.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteNotificationChannelRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Unique notification channel UUID to delete
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60002,
  } satisfies DeleteNotificationChannelRequest;

  try {
    const data = await api.deleteNotificationChannel(body);
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
| **id** | `string` | Unique notification channel UUID to delete | [Defaults to `undefined`] |

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
| **204** | Notification channel successfully deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Notification channel not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteTemplate

> deleteTemplate(id)

Delete a template

Soft-deletes a template definition by UUID or slug. Soft-deleted templates are hidden from normal listings, and entity creation under deleted templates is prevented.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteTemplateRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID or unique slug of the template to delete
    id: 018b2f1b-8c1a-75b3-8000-7f0000010010,
  } satisfies DeleteTemplateRequest;

  try {
    const data = await api.deleteTemplate(body);
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
| **id** | `string` | UUID or unique slug of the template to delete | [Defaults to `undefined`] |

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
| **204** | Template deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteWorkspace

> deleteWorkspace(id)

Delete a workspace and its views

Permanently removes a workspace and all nested view pane configurations from the project.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteWorkspaceRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Workspace unique identifier (UUID) to delete
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  } satisfies DeleteWorkspaceRequest;

  try {
    const data = await api.deleteWorkspace(body);
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
| **id** | `string` | Workspace unique identifier (UUID) to delete | [Defaults to `undefined`] |

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
| **204** | Workspace deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteWorkspaceView

> deleteWorkspaceView(id, viewId)

Delete a view / pane from a workspace

Permanently removes a view pane from a workspace.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { DeleteWorkspaceViewRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Workspace unique identifier (UUID)
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // string | Workspace view unique identifier (UUID) to delete
    viewId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  } satisfies DeleteWorkspaceViewRequest;

  try {
    const data = await api.deleteWorkspaceView(body);
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
| **id** | `string` | Workspace unique identifier (UUID) | [Defaults to `undefined`] |
| **viewId** | `string` | Workspace view unique identifier (UUID) to delete | [Defaults to `undefined`] |

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
| **204** | Workspace view deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAttribute

> AttributeResponse getAttribute(id)

Get an attribute by ID

Retrieves complete attribute metadata by its UUID, including kind (Dimension: 0, Metric: 1, List: 2, Reference: 3), storage data type, assigned template IDs, creation timestamps, and reference configuration if applicable.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetAttributeRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the attribute to fetch
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
  } satisfies GetAttributeRequest;

  try {
    const data = await api.getAttribute(body);
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
| **id** | `string` | UUID of the attribute to fetch | [Defaults to `undefined`] |

### Return type

[**AttributeResponse**](AttributeResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Attribute details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAttributeReferenceConfig

> ReferenceConfigResponse getAttributeReferenceConfig(id)

Get reference configuration for an attribute

Retrieves the relational reference target configuration for a Reference-type (attribute_type &#x3D; 3) attribute. Returns the target template UUID and target display attribute UUID used for entity reference pointer resolution.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetAttributeReferenceConfigRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the Reference attribute
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
  } satisfies GetAttributeReferenceConfigRequest;

  try {
    const data = await api.getAttributeReferenceConfig(body);
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
| **id** | `string` | UUID of the Reference attribute | [Defaults to `undefined`] |

### Return type

[**ReferenceConfigResponse**](ReferenceConfigResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reference configuration details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found - Reference configuration not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAutomation

> AutomationResponse getAutomation(id)

Get an automation by ID

Retrieves the complete configuration of a specific automation rule by its UUID, including trigger event types, template/attribute references, condition comparison expressions, action payloads, execution cooldown interval, and the timestamp of its last execution.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetAutomationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Unique automation UUID
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60001,
  } satisfies GetAutomationRequest;

  try {
    const data = await api.getAutomation(body);
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
| **id** | `string` | Unique automation UUID | [Defaults to `undefined`] |

### Return type

[**AutomationResponse**](AutomationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Automation details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Automation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getDashboard

> DashboardResponse getDashboard(id)

Get a dashboard by ID

Retrieves metadata and top-level configuration for a specific dashboard by its unique identifier.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetDashboardRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Dashboard unique identifier (UUID)
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  } satisfies GetDashboardRequest;

  try {
    const data = await api.getDashboard(body);
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
| **id** | `string` | Dashboard unique identifier (UUID) | [Defaults to `undefined`] |

### Return type

[**DashboardResponse**](DashboardResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Dashboard details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getDashboardBlock

> DashboardBlockResponse getDashboardBlock(dashboardId, blockId)

Get a dashboard block by ID

Retrieves the configuration details, grid coordinates, and data query definitions for an individual visualization block.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetDashboardBlockRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Parent dashboard unique identifier (UUID)
    dashboardId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // string | Dashboard block unique identifier (UUID)
    blockId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  } satisfies GetDashboardBlockRequest;

  try {
    const data = await api.getDashboardBlock(body);
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
| **dashboardId** | `string` | Parent dashboard unique identifier (UUID) | [Defaults to `undefined`] |
| **blockId** | `string` | Dashboard block unique identifier (UUID) | [Defaults to `undefined`] |

### Return type

[**DashboardBlockResponse**](DashboardBlockResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Dashboard block details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getEntity

> EntityResponse getEntity(id, attributeKey)

Get an entity record by ID

Retrieves the full hydrated record for a dynamic entity by its unique identifier (UUID).  ### Attribute Key Formatting (&#x60;attribute_key&#x60;) The &#x60;attribute_key&#x60; query parameter controls the dictionary keys in &#x60;attribute_values&#x60;: - &#x60;\&quot;id\&quot;&#x60; (default): Keys are canonical attribute UUIDs (e.g. &#x60;018b2f1b-8c1a...&#x60;). - &#x60;\&quot;slug\&quot;&#x60;: Keys are human-readable attribute slugs (e.g. &#x60;price&#x60;, &#x60;sku&#x60;, &#x60;category&#x60;), which is recommended for API consumers and AI agent workflows.  ### Hydrated Attribute Values The returned &#x60;attribute_values&#x60; object includes both raw serialized values and resolved display labels (&#x60;custom_value&#x60;) for references and list options.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetEntityRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

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
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetEntityChartRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

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
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetEntityHistoryRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

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


## getMarketplaceBlueprint

> GetMarketplaceBlueprint200Response getMarketplaceBlueprint(id)

Get marketplace blueprint details

Retrieves complete information for a specific marketplace blueprint by its UUID. Returns full blueprint metadata, publisher details, popularity metrics, and packaged blueprint schema definition containing template schemas, attribute configurations, and optional demo entities.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetMarketplaceBlueprintRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new MCPApi();

  const body = {
    // string | Unique marketplace blueprint UUID
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60003,
  } satisfies GetMarketplaceBlueprintRequest;

  try {
    const data = await api.getMarketplaceBlueprint(body);
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
| **id** | `string` | Unique marketplace blueprint UUID | [Defaults to `undefined`] |

### Return type

[**GetMarketplaceBlueprint200Response**](GetMarketplaceBlueprint200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Marketplace blueprint details |  -  |
| **404** | Blueprint not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getNotificationChannel

> NotificationChannelResponse getNotificationChannel(id)

Get a notification channel by ID

Retrieves configuration details and status of a specific notification channel by its UUID, including channel type, name, creation timestamp, and credential settings for authorized project administrators.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetNotificationChannelRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Unique notification channel UUID
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60002,
  } satisfies GetNotificationChannelRequest;

  try {
    const data = await api.getNotificationChannel(body);
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
| **id** | `string` | Unique notification channel UUID | [Defaults to `undefined`] |

### Return type

[**NotificationChannelResponse**](NotificationChannelResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Notification channel details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Notification channel not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getProjectSchema

> ProjectSchemaResponse getProjectSchema()

Get complete project schema graph

Retrieves the complete consolidated schema graph for the active project in a single payload. Includes all active attributes, templates (with attribute bindings and UI layout groups), list choice items, and foreign entity reference configurations. Ideal for AI agents, client initialization, metadata caching, and schema introspection.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetProjectSchemaRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  try {
    const data = await api.getProjectSchema();
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

[**ProjectSchemaResponse**](ProjectSchemaResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Consolidated project schema definition |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getTemplate

> TemplateResponse getTemplate(id)

Get a template by ID or slug

Retrieves complete template schema details by UUID or unique slug, including ordered attribute bindings, default values per attribute, and visual UI layout groups. Automatically filters out any restricted attributes the caller is not permitted to view.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetTemplateRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID or unique slug of the template to retrieve
    id: 018b2f1b-8c1a-75b3-8000-7f0000010010,
  } satisfies GetTemplateRequest;

  try {
    const data = await api.getTemplate(body);
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
| **id** | `string` | UUID or unique slug of the template to retrieve | [Defaults to `undefined`] |

### Return type

[**TemplateResponse**](TemplateResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Template details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getUsageInsights

> UsageInsightsResponse getUsageInsights()

Get current tier usage insights

Returns current resource consumption vs. tier limits for the authenticated user. Includes usage counts (attributes, templates, entities, dashboards, automations, channels, monthly metric ingestions, monthly dimension updates, disk usage, AI credits), corresponding tier limits, and percentage utilization for each resource category. Use this to check quota availability before performing operations.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetUsageInsightsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  try {
    const data = await api.getUsageInsights();
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

[**UsageInsightsResponse**](UsageInsightsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Tier usage insights with limits and percentages |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getWorkspace

> WorkspaceDetailsResponse getWorkspace(id)

Get workspace details and its views

Retrieves detailed information for a specific workspace, including its multi-pane layout configuration and all hydrated view panes with their associated template schemas, filter rules, search criteria, column selections, and ordering.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetWorkspaceRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Workspace unique identifier (UUID)
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  } satisfies GetWorkspaceRequest;

  try {
    const data = await api.getWorkspace(body);
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
| **id** | `string` | Workspace unique identifier (UUID) | [Defaults to `undefined`] |

### Return type

[**WorkspaceDetailsResponse**](WorkspaceDetailsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Workspace details with hydrated views |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getWorkspaceView

> WorkspaceViewResponse getWorkspaceView(id, viewId)

Get details of a workspace view / pane

Retrieves complete configuration details for a single workspace view pane, including its schema template binding, active filter rules, search parameters, column visibility, sort order, and layout positioning.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { GetWorkspaceViewRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Workspace unique identifier (UUID)
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // string | Workspace view unique identifier (UUID)
    viewId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  } satisfies GetWorkspaceViewRequest;

  try {
    const data = await api.getWorkspaceView(body);
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
| **id** | `string` | Workspace unique identifier (UUID) | [Defaults to `undefined`] |
| **viewId** | `string` | Workspace view unique identifier (UUID) | [Defaults to `undefined`] |

### Return type

[**WorkspaceViewResponse**](WorkspaceViewResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Workspace view details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## ingestEntityMetrics

> ingestEntityMetrics(id, ingestMetricsRequest)

Ingest high-frequency metric observations for an entity

Ingests time-series metric observations for an entity record.  ### Batch Telemetry Ingestion Accepts a batch array of metric observations (&#x60;metric_values&#x60;). Each observation targets a metric attribute by &#x60;attribute_id&#x60; (UUID) or &#x60;attribute_slug&#x60; and specifies a numeric &#x60;value&#x60;.  ### High-Throughput Streaming Architecture Metric ingestion calls stream directly into the high-throughput telemetry ingestion pipeline. Asynchronous background consumers persist data points into tenant-scoped time-series storage configured with automated retention and continuous aggregation rollups.  ### Strict Metric Attribute Constraint Only attributes defined with &#x60;attribute_type: Metric&#x60; are accepted by this endpoint. Mutations to dimension, list, or reference attributes must use &#x60;PATCH /entities/{id}&#x60; instead.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { IngestEntityMetricsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

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


## installMarketplaceBlueprint

> installMarketplaceBlueprint(id, installMarketplaceBlueprintRequest)

Install a marketplace blueprint into a project

Installs a marketplace blueprint into the specified project context. Provisions all packaged templates, attributes, and relationships defined in the blueprint schema, and optionally populates sample demo entities. Automatically increments the installation count for the blueprint.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { InstallMarketplaceBlueprintOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Unique UUID of the blueprint to install
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60003,
    // InstallMarketplaceBlueprintRequest
    installMarketplaceBlueprintRequest: ...,
  } satisfies InstallMarketplaceBlueprintOperationRequest;

  try {
    const data = await api.installMarketplaceBlueprint(body);
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
| **id** | `string` | Unique UUID of the blueprint to install | [Defaults to `undefined`] |
| **installMarketplaceBlueprintRequest** | [InstallMarketplaceBlueprintRequest](InstallMarketplaceBlueprintRequest.md) |  | |

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
| **204** | Blueprint successfully installed into the target project |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden - Insufficient project permissions |  -  |
| **404** | Blueprint not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAttributeItems

> ListAttributeItems200Response listAttributeItems(id)

List items of an attribute

Retrieves all selectable choice option items for a List-type (attribute_type &#x3D; 2) attribute in ascending sort order. Each item contains its UUID, parent attribute ID, string value, and sort rank.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListAttributeItemsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the List-type attribute
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
  } satisfies ListAttributeItemsRequest;

  try {
    const data = await api.listAttributeItems(body);
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
| **id** | `string` | UUID of the List-type attribute | [Defaults to `undefined`] |

### Return type

[**ListAttributeItems200Response**](ListAttributeItems200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of option items for the attribute |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAttributes

> ListAttributes200Response listAttributes()

List all attributes

Retrieves all schema attributes defined in the active project. Attributes represent the core schema building blocks across 4 kinds: Dimension (0), Metric (1), List (2), and Reference (3). Each attribute defines its storage data type (String: 0, Number: 1, Boolean: 2, Datetime: 3, Date: 4, File: 5, Image: 6, Markdown: 7), unique slug, optional description, associated templates, and reference configurations.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListAttributesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  try {
    const data = await api.listAttributes();
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

[**ListAttributes200Response**](ListAttributes200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of all project attributes |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAuditLogs

> ListAuditLogs200Response listAuditLogs(page, limit, sortBy, sortDirection, search, eventType, resourceType, resourceId, authorEmail, start, end)

List project audit logs

Returns an immutable, time-ordered audit trail of user and system events for the current project context.  ### Security &amp; Authorization Restricted to authenticated users holding the Project Owner role.  ### Comprehensive Filtering &amp; Search - &#x60;event_type&#x60;: Filter by single or comma-separated event types (e.g. &#x60;entity.created&#x60;, &#x60;entity.updated&#x60;, &#x60;entity.deleted&#x60;, &#x60;template.created&#x60;). - &#x60;resource_type&#x60;: Filter by domain target (e.g. &#x60;entity&#x60;, &#x60;template&#x60;, &#x60;attribute&#x60;, &#x60;project&#x60;). - &#x60;resource_id&#x60;: Filter by exact resource UUID. - &#x60;author_email&#x60;: Filter by the actor email address. - &#x60;start&#x60; and &#x60;end&#x60;: Date-time window bounding event occurrence (ISO 8601 or &#x60;YYYY-MM-DD HH:MM:SS&#x60;). - &#x60;search&#x60;: Text search across event types, resource types, resource IDs, author emails, and value summaries.  ### Pagination &amp; Sorting Supports 1-indexed pagination (&#x60;page&#x60;, &#x60;limit&#x60; up to 100) and sorting by &#x60;occurred_at&#x60;, &#x60;event_type&#x60;, &#x60;resource_type&#x60;, &#x60;resource_id&#x60;, or &#x60;author_email&#x60; (&#x60;asc&#x60;/&#x60;desc&#x60;).

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListAuditLogsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // number | 1-based page number for pagination (optional)
    page: 1,
    // number | Number of audit log records per page (1-100) (optional)
    limit: 20,
    // 'occurred_at' | 'event_type' | 'resource_type' | 'resource_id' | 'author_email' | Field to sort audit log entries by (optional)
    sortBy: occurred_at,
    // 'asc' | 'desc' | Sort direction: \"asc\" (ascending) or \"desc\" (descending) (optional)
    sortDirection: desc,
    // string | Text search filter across event_type, resource_type, resource_id, author_email, and value (optional)
    search: entity.created,
    // string | Filter by single or comma-separated event types (e.g. \"entity.created,entity.updated\") (optional)
    eventType: entity.created,
    // string | Filter by single or comma-separated resource types (e.g. \"entity,template,attribute\") (optional)
    resourceType: entity,
    // string | Filter by exact resource unique identifier (UUID) (optional)
    resourceId: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // string | Filter by actor or author email address (optional)
    authorEmail: demo@omnismith.io,
    // Date | Filter audit records occurring on or after this timestamp (ISO 8601 format) (optional)
    start: 2026-08-01T00:00:00Z,
    // Date | Filter audit records occurring on or before this timestamp (ISO 8601 format) (optional)
    end: 2026-08-26T23:59:59Z,
  } satisfies ListAuditLogsRequest;

  try {
    const data = await api.listAuditLogs(body);
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
| **page** | `number` | 1-based page number for pagination | [Optional] [Defaults to `1`] |
| **limit** | `number` | Number of audit log records per page (1-100) | [Optional] [Defaults to `20`] |
| **sortBy** | `occurred_at`, `event_type`, `resource_type`, `resource_id`, `author_email` | Field to sort audit log entries by | [Optional] [Defaults to `&#39;occurred_at&#39;`] [Enum: occurred_at, event_type, resource_type, resource_id, author_email] |
| **sortDirection** | `asc`, `desc` | Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **search** | `string` | Text search filter across event_type, resource_type, resource_id, author_email, and value | [Optional] [Defaults to `undefined`] |
| **eventType** | `string` | Filter by single or comma-separated event types (e.g. \&quot;entity.created,entity.updated\&quot;) | [Optional] [Defaults to `undefined`] |
| **resourceType** | `string` | Filter by single or comma-separated resource types (e.g. \&quot;entity,template,attribute\&quot;) | [Optional] [Defaults to `undefined`] |
| **resourceId** | `string` | Filter by exact resource unique identifier (UUID) | [Optional] [Defaults to `undefined`] |
| **authorEmail** | `string` | Filter by actor or author email address | [Optional] [Defaults to `undefined`] |
| **start** | `Date` | Filter audit records occurring on or after this timestamp (ISO 8601 format) | [Optional] [Defaults to `undefined`] |
| **end** | `Date` | Filter audit records occurring on or before this timestamp (ISO 8601 format) | [Optional] [Defaults to `undefined`] |

### Return type

[**ListAuditLogs200Response**](ListAuditLogs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated list of audit log records |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAutomations

> Array&lt;AutomationResponse&gt; listAutomations(templateId, isEnabled)

List project automations

Retrieves all automation rules configured within the current project context. Automations define event-driven workflows triggered by entity lifecycle events (such as entity creation, attribute updates, or metric threshold changes), evaluated against multi-attribute conditions, and dispatched to configured action channels (Telegram, webhooks, mobile push). Results can be filtered by entity template or active status.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListAutomationsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Filter automations scoped to a specific entity template UUID (optional)
    templateId: 01912ecb-4654-7890-a1b2-c3d4e5f60088,
    // boolean | Filter automations by active enabled status (true for active rules, false for paused rules) (optional)
    isEnabled: true,
  } satisfies ListAutomationsRequest;

  try {
    const data = await api.listAutomations(body);
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
| **templateId** | `string` | Filter automations scoped to a specific entity template UUID | [Optional] [Defaults to `undefined`] |
| **isEnabled** | `boolean` | Filter automations by active enabled status (true for active rules, false for paused rules) | [Optional] [Defaults to `undefined`] |

### Return type

[**Array&lt;AutomationResponse&gt;**](AutomationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of automation rules |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDashboardBlocks

> ListDashboardBlocks200Response listDashboardBlocks(dashboardId)

List all blocks in a dashboard

Retrieves all visualization blocks mounted on a dashboard canvas, including widget types (stat KPI card, time-series chart, gauge meter, entity list), grid position coordinates (x, y, cols, rows), template filters, and aggregation configs.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListDashboardBlocksRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Parent dashboard unique identifier (UUID)
    dashboardId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  } satisfies ListDashboardBlocksRequest;

  try {
    const data = await api.listDashboardBlocks(body);
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
| **dashboardId** | `string` | Parent dashboard unique identifier (UUID) | [Defaults to `undefined`] |

### Return type

[**ListDashboardBlocks200Response**](ListDashboardBlocks200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of dashboard blocks |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDashboards

> ListDashboards200Response listDashboards()

List all dashboards

Retrieves all analytics dashboards configured within the authenticated project context, including dashboard metadata, layout settings, and visualization configurations.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListDashboardsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  try {
    const data = await api.listDashboards();
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

[**ListDashboards200Response**](ListDashboards200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of dashboards |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listNotificationChannels

> ListNotificationChannels200Response listNotificationChannels()

List notification channels

Retrieves all notification delivery channels configured within the current project. Channels are reusable destination targets for automation alerts, supporting Telegram bots, external HTTP webhooks, and mobile push notifications. Sensitive credentials are sanitized in list outputs.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListNotificationChannelsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  try {
    const data = await api.listNotificationChannels();
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

[**ListNotificationChannels200Response**](ListNotificationChannels200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of configured notification channels |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTemplateEntityCounts

> ListTemplateEntityCounts200Response listTemplateEntityCounts()

List entity counts per template

Returns total entity record counts grouped by template UUID for all accessible templates in the current project context. Efficiently calculates counts and honors role-based resource access restrictions.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListTemplateEntityCountsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  try {
    const data = await api.listTemplateEntityCounts();
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

[**ListTemplateEntityCounts200Response**](ListTemplateEntityCounts200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Entity counts per template |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTemplates

> ListTemplates200Response listTemplates()

List all templates

Retrieves all dynamic schema templates defined within the active project context. Templates represent content types grouping reusable attributes, establishing per-template default values, and organizing fields into visual layout groups for the UI workbench and entity forms.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListTemplatesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  try {
    const data = await api.listTemplates();
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

[**ListTemplates200Response**](ListTemplates200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of all project templates |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listWorkspaces

> ListWorkspaces200Response listWorkspaces()

List all workspaces for current project

Retrieves all workspaces configured within the authenticated project context, including multi-pane layout structures (single, split-v, split-h, quad), view pane counts, sort ordering, and default workspace indicators for workbench navigation.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ListWorkspacesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  try {
    const data = await api.listWorkspaces();
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

[**ListWorkspaces200Response**](ListWorkspaces200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of workspaces |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## patchAttribute

> patchAttribute(id, patchAttributeRequest)

Patch an attribute (granular partial update)

Applies partial modifications to an existing attribute without overwriting omitted fields. Allows independently changing name, description, slug, template associations, reference configuration, or transitioning data type. Lossless data type transition rules apply when updating data_type (Dimension only: Number(1)-&gt;String(0), Boolean(2)-&gt;String(0), Date(4)&lt;-&gt;Datetime(3), Date(4)/Datetime(3)-&gt;String(0), String(0)&lt;-&gt;Markdown(7)). Template associations merge and preserve restricted templates.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { PatchAttributeOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the attribute to patch
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // PatchAttributeRequest
    patchAttributeRequest: ...,
  } satisfies PatchAttributeOperationRequest;

  try {
    const data = await api.patchAttribute(body);
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
| **id** | `string` | UUID of the attribute to patch | [Defaults to `undefined`] |
| **patchAttributeRequest** | [PatchAttributeRequest](PatchAttributeRequest.md) |  | |

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
| **204** | Attribute patched successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **409** | Conflict |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## patchTemplate

> patchTemplate(id, patchTemplateRequest)

Patch a template (granular partial update)

Applies partial modifications to an existing template by UUID or slug without overwriting omitted fields. Allows modifying name, description, category, slug, attribute associations (with validated default values), or visual layout groups independently. Safely merges and preserves any restricted attributes.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { PatchTemplateOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID or unique slug of the template to patch
    id: 018b2f1b-8c1a-75b3-8000-7f0000010010,
    // PatchTemplateRequest
    patchTemplateRequest: ...,
  } satisfies PatchTemplateOperationRequest;

  try {
    const data = await api.patchTemplate(body);
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
| **id** | `string` | UUID or unique slug of the template to patch | [Defaults to `undefined`] |
| **patchTemplateRequest** | [PatchTemplateRequest](PatchTemplateRequest.md) |  | |

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
| **204** | Template patched successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **409** | Conflict |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## resolveDashboardBlock

> ResolvedBlockResponse resolveDashboardBlock(dashboardId, blockId)

Resolve a dashboard block to its computed data

Executes the underlying data query for a dashboard block and returns computed real-time aggregated metrics and time-series telemetry. Returns a typed payload matching the block type: stat (matching entity count), gauge (current metric value, min/max bounds, progress percentage), chart (time-series data point series bucketed by time intervals with aggregation functions), or list (hydrated entity items with dynamic attributes).

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ResolveDashboardBlockRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Parent dashboard unique identifier (UUID)
    dashboardId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // string | Dashboard block unique identifier (UUID) to resolve and compute
    blockId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  } satisfies ResolveDashboardBlockRequest;

  try {
    const data = await api.resolveDashboardBlock(body);
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
| **dashboardId** | `string` | Parent dashboard unique identifier (UUID) | [Defaults to `undefined`] |
| **blockId** | `string` | Dashboard block unique identifier (UUID) to resolve and compute | [Defaults to `undefined`] |

### Return type

[**ResolvedBlockResponse**](ResolvedBlockResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Resolved block computed data payload |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchEntities

> SearchEntities200Response searchEntities(templateId, searchEntitiesRequest, limit, offset, sortField, sortDirection, attributeKey)

Search entities with filtering, sorting, and pagination

Executes structured queries, full-text searches, and sorting across dynamic entities of a specified template schema.  ### Template Targeting (&#x60;template_id&#x60;) Accepts either a canonical template UUID (e.g. &#x60;018b2f1b-8c1a...&#x60;) or a human-readable template slug (e.g. &#x60;product_catalog&#x60;).  ### Structured Filters (&#x60;filters&#x60;) Filter conditions are specified in the request body as an array of filter objects: &#x60;&#x60;&#x60;json [   {\&quot;field\&quot;: \&quot;status\&quot;, \&quot;operator\&quot;: \&quot;eq\&quot;, \&quot;value\&quot;: \&quot;018b2f1b-8c1a-75b3-8000-7f0000010020\&quot;},   {\&quot;field\&quot;: \&quot;price\&quot;, \&quot;operator\&quot;: \&quot;gt\&quot;, \&quot;value\&quot;: \&quot;100\&quot;},   {\&quot;field\&quot;: \&quot;name\&quot;, \&quot;operator\&quot;: \&quot;like\&quot;, \&quot;value\&quot;: \&quot;Pro\&quot;} ] &#x60;&#x60;&#x60; - **&#x60;field&#x60;**: Target attribute UUID, attribute slug, or standard field (&#x60;id&#x60;, &#x60;created_at&#x60;, &#x60;updated_at&#x60;). - **&#x60;operator&#x60;**: Comparison operator: &#x60;eq&#x60; (equals), &#x60;neq&#x60; (not equals), &#x60;gt&#x60; (greater than), &#x60;lt&#x60; (less than), &#x60;like&#x60; (substring / trigram match), &#x60;not-like&#x60; (does not match), &#x60;empty&#x60; (is null or empty), &#x60;not-empty&#x60; (has value). - **&#x60;value&#x60;**: Target comparison value serialized as string.  ### Global Search (&#x60;global_search&#x60;) Performs accelerated full-text and GIN trigram matching across all string dimension attributes defined on the template.  ### Sorting &amp; Pagination - **&#x60;sort_field&#x60;**: Attribute UUID, attribute slug, or standard entity fields (&#x60;id&#x60;, &#x60;created_at&#x60;, &#x60;updated_at&#x60;, &#x60;deleted_at&#x60;). - **&#x60;sort_direction&#x60;**: &#x60;asc&#x60; or &#x60;desc&#x60; (default: &#x60;asc&#x60; when &#x60;sort_field&#x60; is set, otherwise default sort is &#x60;created_at&#x60; DESC). - **&#x60;limit&#x60;** and **&#x60;offset&#x60;**: Bounded pagination (max 100 per page).  ### Attribute Key Formatting (&#x60;attribute_key&#x60;) Passing &#x60;attribute_key&#x3D;\&quot;slug\&quot;&#x60; formats the returned &#x60;attribute_values&#x60; dictionary keys using human-readable attribute slugs instead of raw UUIDs.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { SearchEntitiesOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

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


## searchMarketplaceBlueprints

> SearchMarketplaceBlueprints200Response searchMarketplaceBlueprints(search, keywords, limit, offset, sortBy, sortDirection, featured)

Search marketplace blueprints

Searches and lists public blueprints available in the marketplace catalog. Blueprints package reusable template schemas, attribute definitions, and sample data that users can install directly into their projects. Supports full-text search across titles and descriptions, keyword tag filtering, filtering by featured status, and sorting by creation date, install counts, or title.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { SearchMarketplaceBlueprintsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new MCPApi();

  const body = {
    // string | Free-text search filter across blueprint title and description (optional)
    search: crm pipeline,
    // string | Comma-separated keywords or tags to filter blueprints (optional)
    keywords: crm,sales,leads,
    // number | Number of blueprint records to return per page (max 100) (optional)
    limit: 20,
    // number | Number of blueprint records to skip for pagination (optional)
    offset: 0,
    // 'created_at' | 'installs' | 'title' | Field to sort blueprint results by (optional)
    sortBy: installs,
    // 'asc' | 'desc' | Sort direction order (ascending or descending) (optional)
    sortDirection: desc,
    // boolean | Filter to return only curated and featured marketplace blueprints (optional)
    featured: true,
  } satisfies SearchMarketplaceBlueprintsRequest;

  try {
    const data = await api.searchMarketplaceBlueprints(body);
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
| **search** | `string` | Free-text search filter across blueprint title and description | [Optional] [Defaults to `undefined`] |
| **keywords** | `string` | Comma-separated keywords or tags to filter blueprints | [Optional] [Defaults to `undefined`] |
| **limit** | `number` | Number of blueprint records to return per page (max 100) | [Optional] [Defaults to `20`] |
| **offset** | `number` | Number of blueprint records to skip for pagination | [Optional] [Defaults to `0`] |
| **sortBy** | `created_at`, `installs`, `title` | Field to sort blueprint results by | [Optional] [Defaults to `&#39;created_at&#39;`] [Enum: created_at, installs, title] |
| **sortDirection** | `asc`, `desc` | Sort direction order (ascending or descending) | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **featured** | `boolean` | Filter to return only curated and featured marketplace blueprints | [Optional] [Defaults to `undefined`] |

### Return type

[**SearchMarketplaceBlueprints200Response**](SearchMarketplaceBlueprints200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated list of marketplace blueprints |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## setAttributeItems

> setAttributeItems(id, setListItemsRequest)

Set list items for an attribute (replaces all existing items)

Atomically replaces all selectable option items for a List-type (attribute_type &#x3D; 2) attribute. Existing list items for this attribute are removed and replaced with the provided array of items (with values, sort orders, and optional custom UUIDs). Returns HTTP 400 if the target attribute is not of List kind.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { SetAttributeItemsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the List-type attribute
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // SetListItemsRequest
    setListItemsRequest: ...,
  } satisfies SetAttributeItemsRequest;

  try {
    const data = await api.setAttributeItems(body);
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
| **id** | `string` | UUID of the List-type attribute | [Defaults to `undefined`] |
| **setListItemsRequest** | [SetListItemsRequest](SetListItemsRequest.md) |  | |

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
| **204** | List items replaced successfully |  -  |
| **400** | Bad Request - Attribute is not a List type |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## setAttributeReferenceConfig

> setAttributeReferenceConfig(id, setReferenceConfigRequest)

Set or update reference configuration for an attribute

Sets or updates the target template and display attribute for a Reference-type (attribute_type &#x3D; 3) attribute. Enables relational linking and foreign entity display label resolution. Returns HTTP 400 if the target attribute is not of Reference kind.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { SetAttributeReferenceConfigRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the Reference attribute
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // SetReferenceConfigRequest
    setReferenceConfigRequest: ...,
  } satisfies SetAttributeReferenceConfigRequest;

  try {
    const data = await api.setAttributeReferenceConfig(body);
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
| **id** | `string` | UUID of the Reference attribute | [Defaults to `undefined`] |
| **setReferenceConfigRequest** | [SetReferenceConfigRequest](SetReferenceConfigRequest.md) |  | |

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
| **204** | Reference configuration updated successfully |  -  |
| **400** | Bad Request - Attribute is not a Reference type |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## testNotificationChannel

> TestNotificationChannel200Response testNotificationChannel(id, testNotificationChannelRequest)

Send a test notification message

Dispatches an immediate test notification message to verify channel credentials, network reachability, and recipient configuration. Accepts channel-specific parameters such as Telegram &#x60;chat_id&#x60; or push notification &#x60;title&#x60; and &#x60;message&#x60;.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { TestNotificationChannelOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Unique notification channel UUID to test
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60002,
    // TestNotificationChannelRequest
    testNotificationChannelRequest: ...,
  } satisfies TestNotificationChannelOperationRequest;

  try {
    const data = await api.testNotificationChannel(body);
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
| **id** | `string` | Unique notification channel UUID to test | [Defaults to `undefined`] |
| **testNotificationChannelRequest** | [TestNotificationChannelRequest](TestNotificationChannelRequest.md) |  | |

### Return type

[**TestNotificationChannel200Response**](TestNotificationChannel200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Test message delivered successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Notification channel not found |  -  |
| **422** | Test message delivery failed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## toggleAutomation

> AutomationResponse toggleAutomation(id, toggleAutomationRequest)

Toggle automation enabled status

Enables or pauses an automation rule without altering its trigger definitions, condition criteria, or action configurations. Paused automations are ignored during event processing.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { ToggleAutomationOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Unique automation UUID to toggle
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60001,
    // ToggleAutomationRequest
    toggleAutomationRequest: ...,
  } satisfies ToggleAutomationOperationRequest;

  try {
    const data = await api.toggleAutomation(body);
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
| **id** | `string` | Unique automation UUID to toggle | [Defaults to `undefined`] |
| **toggleAutomationRequest** | [ToggleAutomationRequest](ToggleAutomationRequest.md) |  | |

### Return type

[**AutomationResponse**](AutomationResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Automation status successfully toggled |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateAttribute

> updateAttribute(id, updateAttributeRequest)

Update an attribute (full replacement)

Performs a full update of an existing attribute definition. Supports updating name, description, slug, template associations, reference configuration, and lossless data type transitions. Data type transitions are permitted only for Dimension (0) attributes and must follow lossless compatibility: Number(1) -&gt; String(0), Boolean(2) -&gt; String(0), Date(4) &lt;-&gt; Datetime(3), Date(4)/Datetime(3) -&gt; String(0), and String(0) &lt;-&gt; Markdown(7). Non-lossless transitions or transitions on non-dimension attributes will return HTTP 422. Template associations preserve restricted templates the caller cannot see.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { UpdateAttributeOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID of the attribute to update
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // UpdateAttributeRequest
    updateAttributeRequest: ...,
  } satisfies UpdateAttributeOperationRequest;

  try {
    const data = await api.updateAttribute(body);
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
| **id** | `string` | UUID of the attribute to update | [Defaults to `undefined`] |
| **updateAttributeRequest** | [UpdateAttributeRequest](UpdateAttributeRequest.md) |  | |

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
| **204** | Attribute updated successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **409** | Conflict |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateAutomation

> updateAutomation(id, updateAutomationRequest)

Update an automation

Updates an existing automation rule by UUID. Supports modifying rule name, description, trigger event definitions, condition filter criteria, action dispatches, and cooldown throttle settings.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { UpdateAutomationOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Unique automation UUID to update
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60001,
    // UpdateAutomationRequest
    updateAutomationRequest: ...,
  } satisfies UpdateAutomationOperationRequest;

  try {
    const data = await api.updateAutomation(body);
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
| **id** | `string` | Unique automation UUID to update | [Defaults to `undefined`] |
| **updateAutomationRequest** | [UpdateAutomationRequest](UpdateAutomationRequest.md) |  | |

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
| **204** | Automation successfully updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Automation not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateDashboard

> updateDashboard(id, updateDashboardRequest)

Update a dashboard

Updates dashboard metadata including its display name, description, and canvas layout settings.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { UpdateDashboardOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Dashboard unique identifier (UUID) to update
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // UpdateDashboardRequest | Dashboard update payload
    updateDashboardRequest: ...,
  } satisfies UpdateDashboardOperationRequest;

  try {
    const data = await api.updateDashboard(body);
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
| **id** | `string` | Dashboard unique identifier (UUID) to update | [Defaults to `undefined`] |
| **updateDashboardRequest** | [UpdateDashboardRequest](UpdateDashboardRequest.md) | Dashboard update payload | |

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
| **204** | Dashboard updated successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateDashboardBlock

> updateDashboardBlock(dashboardId, blockId, updateDashboardBlockRequest)

Update a dashboard block

Updates the display title, grid placement (x, y, cols, rows), metric queries, time-series aggregation buckets, gauge bounds, or filtering rules of an existing visualization block.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { UpdateDashboardBlockOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Parent dashboard unique identifier (UUID)
    dashboardId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // string | Dashboard block unique identifier (UUID) to update
    blockId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
    // UpdateDashboardBlockRequest | Dashboard block update payload
    updateDashboardBlockRequest: ...,
  } satisfies UpdateDashboardBlockOperationRequest;

  try {
    const data = await api.updateDashboardBlock(body);
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
| **dashboardId** | `string` | Parent dashboard unique identifier (UUID) | [Defaults to `undefined`] |
| **blockId** | `string` | Dashboard block unique identifier (UUID) to update | [Defaults to `undefined`] |
| **updateDashboardBlockRequest** | [UpdateDashboardBlockRequest](UpdateDashboardBlockRequest.md) | Dashboard block update payload | |

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
| **204** | Dashboard block updated successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateEntity

> updateEntity(id, updateEntityRequest)

Update entity attribute values

Updates specific dynamic attribute values for an existing entity record.  ### Dynamic Attribute Values (&#x60;attribute_values&#x60;) Submit one or more attribute value updates. Each entry supports identifier resolution via: - &#x60;attribute_id&#x60;: Canonical attribute UUID - &#x60;attribute_slug&#x60;: Attribute slug identifier (e.g. &#x60;price&#x60;, &#x60;sku&#x60;, &#x60;status&#x60;)  ### Value Formatting Rules - **Dimension - Text / Markdown**: UTF-8 string value - **Dimension - Number**: Numeric string representation (e.g. &#x60;\&quot;149.99\&quot;&#x60;) - **Dimension - Boolean**: Boolean representation: &#x60;\&quot;true\&quot;&#x60;, &#x60;\&quot;false\&quot;&#x60;, &#x60;\&quot;1\&quot;&#x60;, or &#x60;\&quot;0\&quot;&#x60; - **Dimension - Date &amp; Datetime**: Formatted as &#x60;YYYY-MM-DD&#x60; or &#x60;YYYY-MM-DD HH:MM:SS&#x60; / ISO 8601 &#x60;YYYY-MM-DDTHH:MM:SSZ&#x60; - **Dimension - File &amp; Image**: UUID string of a pre-uploaded workspace file asset - **List Attribute**: Must provide the exact UUID string of a valid defined &#x60;ListItem&#x60; option - **Reference Attribute**: Must provide the exact UUID string of an existing referenced &#x60;Entity&#x60;  ### Audit Trail &amp; Metrics - Dimension updates are recorded in the append-only entity dimension change history log. - Metric attribute values submitted here are dispatched to the metric streaming pipeline for time-series aggregation.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { UpdateEntityOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

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


## updateNotificationChannel

> updateNotificationChannel(id, updateNotificationChannelRequest)

Update a notification channel

Updates an existing notification channel configuration by UUID. Allows updating the channel display name or updating integration credentials (such as new bot tokens, webhook endpoints, or authentication credentials).

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { UpdateNotificationChannelOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Unique notification channel UUID to update
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60002,
    // UpdateNotificationChannelRequest
    updateNotificationChannelRequest: ...,
  } satisfies UpdateNotificationChannelOperationRequest;

  try {
    const data = await api.updateNotificationChannel(body);
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
| **id** | `string` | Unique notification channel UUID to update | [Defaults to `undefined`] |
| **updateNotificationChannelRequest** | [UpdateNotificationChannelRequest](UpdateNotificationChannelRequest.md) |  | |

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
| **204** | Notification channel successfully updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Notification channel not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateTemplate

> updateTemplate(id, updateTemplateRequest)

Update a template (full replacement)

Performs a full update of an existing template definition by UUID or slug. Replaces name, description, category, slug, attribute associations (with validated per-attribute default values), and UI layout groups. If the caller lacks permissions to certain restricted attributes, those restricted attributes are automatically preserved in the template.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { UpdateTemplateOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | UUID or unique slug of the template to update
    id: 018b2f1b-8c1a-75b3-8000-7f0000010010,
    // UpdateTemplateRequest
    updateTemplateRequest: ...,
  } satisfies UpdateTemplateOperationRequest;

  try {
    const data = await api.updateTemplate(body);
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
| **id** | `string` | UUID or unique slug of the template to update | [Defaults to `undefined`] |
| **updateTemplateRequest** | [UpdateTemplateRequest](UpdateTemplateRequest.md) |  | |

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
| **204** | Template updated successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **409** | Conflict |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateWorkspace

> updateWorkspace(id, updateWorkspaceRequest)

Update workspace metadata and layout

Updates workspace attributes including display name, description, multi-pane layout arrangement (single, split-v, split-h, quad), sort order sequence, and default workspace status.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { UpdateWorkspaceOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Workspace unique identifier (UUID) to update
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // UpdateWorkspaceRequest | Workspace update payload
    updateWorkspaceRequest: ...,
  } satisfies UpdateWorkspaceOperationRequest;

  try {
    const data = await api.updateWorkspace(body);
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
| **id** | `string` | Workspace unique identifier (UUID) to update | [Defaults to `undefined`] |
| **updateWorkspaceRequest** | [UpdateWorkspaceRequest](UpdateWorkspaceRequest.md) | Workspace update payload | |

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
| **204** | Workspace updated successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateWorkspaceView

> updateWorkspaceView(id, viewId, updateWorkspaceViewRequest)

Update workspace view / pane filters, sort, display mode, or columns

Updates the configuration of a specific workspace view pane, modifying its title, filtering rules, search query and mode, sorting preferences, presentation display mode (table or grid), column visibility lists, or pane display sequence.

### Example

```ts
import {
  Configuration,
  MCPApi,
} from '@omnismith-sdk/typescript';
import type { UpdateWorkspaceViewOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MCPApi(config);

  const body = {
    // string | Workspace unique identifier (UUID)
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // string | Workspace view unique identifier (UUID) to update
    viewId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
    // UpdateWorkspaceViewRequest | Workspace view update payload
    updateWorkspaceViewRequest: ...,
  } satisfies UpdateWorkspaceViewOperationRequest;

  try {
    const data = await api.updateWorkspaceView(body);
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
| **id** | `string` | Workspace unique identifier (UUID) | [Defaults to `undefined`] |
| **viewId** | `string` | Workspace view unique identifier (UUID) to update | [Defaults to `undefined`] |
| **updateWorkspaceViewRequest** | [UpdateWorkspaceViewRequest](UpdateWorkspaceViewRequest.md) | Workspace view update payload | |

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
| **204** | Workspace view updated successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

