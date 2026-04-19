# DashboardBlocksApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createDashboardBlock**](DashboardBlocksApi.md#createdashboardblockoperation) | **POST** /dashboards/{dashboardId}/blocks | Create a new block in a dashboard |
| [**deleteDashboardBlock**](DashboardBlocksApi.md#deletedashboardblock) | **DELETE** /dashboards/{dashboardId}/blocks/{blockId} | Delete a dashboard block |
| [**getDashboardBlock**](DashboardBlocksApi.md#getdashboardblock) | **GET** /dashboards/{dashboardId}/blocks/{blockId} | Get a dashboard block by ID |
| [**listDashboardBlocks**](DashboardBlocksApi.md#listdashboardblocks) | **GET** /dashboards/{dashboardId}/blocks | List all blocks in a dashboard |
| [**resolveDashboardBlock**](DashboardBlocksApi.md#resolvedashboardblock) | **GET** /dashboards/{dashboardId}/blocks/{blockId}/resolve | Resolve a dashboard block to its computed data |
| [**updateDashboardBlock**](DashboardBlocksApi.md#updatedashboardblockoperation) | **PUT** /dashboards/{dashboardId}/blocks/{blockId} | Update a dashboard block |



## createDashboardBlock

> CreateAttributeItem201Response createDashboardBlock(dashboardId, createDashboardBlockRequest)

Create a new block in a dashboard

### Example

```ts
import {
  Configuration,
  DashboardBlocksApi,
} from '@omnismith-sdk/typescript';
import type { CreateDashboardBlockOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardBlocksApi(config);

  const body = {
    // string | Dashboard ID
    dashboardId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // CreateDashboardBlockRequest
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
| **dashboardId** | `string` | Dashboard ID | [Defaults to `undefined`] |
| **createDashboardBlockRequest** | [CreateDashboardBlockRequest](CreateDashboardBlockRequest.md) |  | |

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
| **201** | Block created |  -  |
| **404** | Dashboard not found |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteDashboardBlock

> deleteDashboardBlock(dashboardId, blockId)

Delete a dashboard block

### Example

```ts
import {
  Configuration,
  DashboardBlocksApi,
} from '@omnismith-sdk/typescript';
import type { DeleteDashboardBlockRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardBlocksApi(config);

  const body = {
    // string | Dashboard ID
    dashboardId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string | Block ID
    blockId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **dashboardId** | `string` | Dashboard ID | [Defaults to `undefined`] |
| **blockId** | `string` | Block ID | [Defaults to `undefined`] |

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
| **204** | Block deleted |  -  |
| **404** | Block not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getDashboardBlock

> DashboardBlockResponse getDashboardBlock(dashboardId, blockId)

Get a dashboard block by ID

### Example

```ts
import {
  Configuration,
  DashboardBlocksApi,
} from '@omnismith-sdk/typescript';
import type { GetDashboardBlockRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardBlocksApi(config);

  const body = {
    // string | Dashboard ID
    dashboardId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string | Block ID
    blockId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **dashboardId** | `string` | Dashboard ID | [Defaults to `undefined`] |
| **blockId** | `string` | Block ID | [Defaults to `undefined`] |

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
| **200** | Block details |  -  |
| **404** | Block not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDashboardBlocks

> ListDashboardBlocks200Response listDashboardBlocks(dashboardId)

List all blocks in a dashboard

### Example

```ts
import {
  Configuration,
  DashboardBlocksApi,
} from '@omnismith-sdk/typescript';
import type { ListDashboardBlocksRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardBlocksApi(config);

  const body = {
    // string | Dashboard ID
    dashboardId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **dashboardId** | `string` | Dashboard ID | [Defaults to `undefined`] |

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
| **200** | List of blocks |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## resolveDashboardBlock

> ResolvedBlockResponse resolveDashboardBlock(dashboardId, blockId)

Resolve a dashboard block to its computed data

Executes the block configuration and returns computed values based on block type (stat count, gauge value, chart series, or list items)

### Example

```ts
import {
  Configuration,
  DashboardBlocksApi,
} from '@omnismith-sdk/typescript';
import type { ResolveDashboardBlockRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardBlocksApi(config);

  const body = {
    // string | Dashboard ID
    dashboardId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string | Block ID
    blockId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **dashboardId** | `string` | Dashboard ID | [Defaults to `undefined`] |
| **blockId** | `string` | Block ID | [Defaults to `undefined`] |

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
| **200** | Resolved block data |  -  |
| **404** | Block not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateDashboardBlock

> updateDashboardBlock(dashboardId, blockId, updateDashboardBlockRequest)

Update a dashboard block

### Example

```ts
import {
  Configuration,
  DashboardBlocksApi,
} from '@omnismith-sdk/typescript';
import type { UpdateDashboardBlockOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardBlocksApi(config);

  const body = {
    // string | Dashboard ID
    dashboardId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string | Block ID
    blockId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // UpdateDashboardBlockRequest
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
| **dashboardId** | `string` | Dashboard ID | [Defaults to `undefined`] |
| **blockId** | `string` | Block ID | [Defaults to `undefined`] |
| **updateDashboardBlockRequest** | [UpdateDashboardBlockRequest](UpdateDashboardBlockRequest.md) |  | |

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
| **200** | Block updated |  -  |
| **404** | Block not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

