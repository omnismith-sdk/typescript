# WorkspacesApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createWorkspace**](WorkspacesApi.md#createworkspaceoperation) | **POST** /workspaces | Create a new workspace |
| [**createWorkspaceView**](WorkspacesApi.md#createworkspaceviewoperation) | **POST** /workspaces/{id}/views | Add a new view / pane to a workspace |
| [**deleteWorkspace**](WorkspacesApi.md#deleteworkspace) | **DELETE** /workspaces/{id} | Delete a workspace and its views |
| [**deleteWorkspaceView**](WorkspacesApi.md#deleteworkspaceview) | **DELETE** /workspaces/{id}/views/{viewId} | Delete a view / pane from a workspace |
| [**duplicateWorkspace**](WorkspacesApi.md#duplicateworkspaceoperation) | **POST** /workspaces/{id}/duplicate | Duplicate an existing workspace and its views |
| [**getWorkspace**](WorkspacesApi.md#getworkspace) | **GET** /workspaces/{id} | Get workspace details and its views |
| [**getWorkspaceView**](WorkspacesApi.md#getworkspaceview) | **GET** /workspaces/{id}/views/{viewId} | Get details of a workspace view / pane |
| [**listTemplateViews**](WorkspacesApi.md#listtemplateviews) | **GET** /workspaces/template/{templateId} | List saved views for a specific template across workspaces |
| [**listWorkspaces**](WorkspacesApi.md#listworkspaces) | **GET** /workspaces | List all workspaces for current project |
| [**reorderWorkspaceViews**](WorkspacesApi.md#reorderworkspaceviewsoperation) | **PUT** /workspaces/{id}/reorder-views | Reorder views inside a workspace |
| [**setDefaultWorkspace**](WorkspacesApi.md#setdefaultworkspace) | **POST** /workspaces/{id}/default | Set workspace as the default workspace |
| [**updateWorkspace**](WorkspacesApi.md#updateworkspaceoperation) | **PUT** /workspaces/{id} | Update workspace metadata and layout |
| [**updateWorkspaceView**](WorkspacesApi.md#updateworkspaceviewoperation) | **PUT** /workspaces/{id}/views/{viewId} | Update workspace view / pane filters, sort, display mode, or columns |



## createWorkspace

> CreateDashboard201Response createWorkspace(createWorkspaceRequest)

Create a new workspace

Creates a new workspace in the current project context with a specified multi-pane layout (single, split-v, split-h, quad), optional default workspace status, and initial template view bindings to automatically generate panes.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { CreateWorkspaceOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

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
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { CreateWorkspaceViewOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

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


## deleteWorkspace

> deleteWorkspace(id)

Delete a workspace and its views

Permanently removes a workspace and all nested view pane configurations from the project.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { DeleteWorkspaceRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

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
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { DeleteWorkspaceViewRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

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


## duplicateWorkspace

> DuplicateWorkspace201Response duplicateWorkspace(id, duplicateWorkspaceRequest)

Duplicate an existing workspace and its views

Creates a deep copy of an existing workspace, cloning all nested view panes, filter rules, display configurations, and layout settings into a new workspace with an optional customized name.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { DuplicateWorkspaceOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string | Source workspace unique identifier (UUID) to clone
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // DuplicateWorkspaceRequest | Optional configuration for the duplicated workspace (optional)
    duplicateWorkspaceRequest: ...,
  } satisfies DuplicateWorkspaceOperationRequest;

  try {
    const data = await api.duplicateWorkspace(body);
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
| **id** | `string` | Source workspace unique identifier (UUID) to clone | [Defaults to `undefined`] |
| **duplicateWorkspaceRequest** | [DuplicateWorkspaceRequest](DuplicateWorkspaceRequest.md) | Optional configuration for the duplicated workspace | [Optional] |

### Return type

[**DuplicateWorkspace201Response**](DuplicateWorkspace201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Workspace duplicated successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getWorkspace

> WorkspaceDetailsResponse getWorkspace(id)

Get workspace details and its views

Retrieves detailed information for a specific workspace, including its multi-pane layout configuration and all hydrated view panes with their associated template schemas, filter rules, search criteria, column selections, and ordering.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { GetWorkspaceRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

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
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { GetWorkspaceViewRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

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


## listTemplateViews

> ListTemplateViews200Response listTemplateViews(templateId)

List saved views for a specific template across workspaces

Searches and returns all saved workspace view panes configured across any workspace that are bound to a specific entity schema template, facilitating cross-workspace view reuse and discovery.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { ListTemplateViewsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string | Schema template unique identifier (UUID)
    templateId: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  } satisfies ListTemplateViewsRequest;

  try {
    const data = await api.listTemplateViews(body);
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
| **templateId** | `string` | Schema template unique identifier (UUID) | [Defaults to `undefined`] |

### Return type

[**ListTemplateViews200Response**](ListTemplateViews200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of saved views for template |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listWorkspaces

> ListWorkspaces200Response listWorkspaces()

List all workspaces for current project

Retrieves all workspaces configured within the authenticated project context, including multi-pane layout structures (single, split-v, split-h, quad), view pane counts, sort ordering, and default workspace indicators for workbench navigation.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { ListWorkspacesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

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


## reorderWorkspaceViews

> reorderWorkspaceViews(id, reorderWorkspaceViewsRequest)

Reorder views inside a workspace

Updates the visual sequence and tab ordering of view panes inside a workspace by supplying an ordered list of view IDs matching the desired layout arrangement.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { ReorderWorkspaceViewsOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string | Workspace unique identifier (UUID)
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
    // ReorderWorkspaceViewsRequest | Payload containing ordered view IDs
    reorderWorkspaceViewsRequest: ...,
  } satisfies ReorderWorkspaceViewsOperationRequest;

  try {
    const data = await api.reorderWorkspaceViews(body);
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
| **reorderWorkspaceViewsRequest** | [ReorderWorkspaceViewsRequest](ReorderWorkspaceViewsRequest.md) | Payload containing ordered view IDs | |

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
| **204** | Workspace views reordered successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## setDefaultWorkspace

> setDefaultWorkspace(id)

Set workspace as the default workspace

Designates the specified workspace as the primary/default landing view for the project, automatically demoting any existing default workspace.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { SetDefaultWorkspaceRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

  const body = {
    // string | Workspace unique identifier (UUID) to designate as default
    id: 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  } satisfies SetDefaultWorkspaceRequest;

  try {
    const data = await api.setDefaultWorkspace(body);
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
| **id** | `string` | Workspace unique identifier (UUID) to designate as default | [Defaults to `undefined`] |

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
| **204** | Workspace designated as default successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateWorkspace

> updateWorkspace(id, updateWorkspaceRequest)

Update workspace metadata and layout

Updates workspace attributes including display name, description, multi-pane layout arrangement (single, split-v, split-h, quad), sort order sequence, and default workspace status.

### Example

```ts
import {
  Configuration,
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { UpdateWorkspaceOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

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
  WorkspacesApi,
} from '@omnismith-sdk/typescript';
import type { UpdateWorkspaceViewOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new WorkspacesApi(config);

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

