# DashboardsApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createDashboard**](DashboardsApi.md#createdashboardoperation) | **POST** /dashboards | Create a new dashboard |
| [**deleteDashboard**](DashboardsApi.md#deletedashboard) | **DELETE** /dashboards/{id} | Delete a dashboard |
| [**getDashboard**](DashboardsApi.md#getdashboard) | **GET** /dashboards/{id} | Get a dashboard by ID |
| [**listDashboards**](DashboardsApi.md#listdashboards) | **GET** /dashboards | List all dashboards |
| [**updateDashboard**](DashboardsApi.md#updatedashboardoperation) | **PUT** /dashboards/{id} | Update a dashboard |



## createDashboard

> CreateDashboard201Response createDashboard(createDashboardRequest)

Create a new dashboard

Creates a new analytics and telemetry dashboard canvas for organizing metric KPIs, charts, gauges, and entity tables within a customizable grid layout.

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith-sdk/typescript';
import type { CreateDashboardOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardsApi(config);

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


## deleteDashboard

> deleteDashboard(id)

Delete a dashboard

Permanently removes a dashboard and all attached visualization blocks, metric widgets, and configurations.

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith-sdk/typescript';
import type { DeleteDashboardRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardsApi(config);

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


## getDashboard

> DashboardResponse getDashboard(id)

Get a dashboard by ID

Retrieves metadata and top-level configuration for a specific dashboard by its unique identifier.

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith-sdk/typescript';
import type { GetDashboardRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardsApi(config);

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


## listDashboards

> ListDashboards200Response listDashboards()

List all dashboards

Retrieves all analytics dashboards configured within the authenticated project context, including dashboard metadata, layout settings, and visualization configurations.

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith-sdk/typescript';
import type { ListDashboardsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardsApi(config);

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


## updateDashboard

> updateDashboard(id, updateDashboardRequest)

Update a dashboard

Updates dashboard metadata including its display name, description, and canvas layout settings.

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith-sdk/typescript';
import type { UpdateDashboardOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardsApi(config);

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

