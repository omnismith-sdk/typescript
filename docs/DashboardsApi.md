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

> CreateAttributeItem201Response createDashboard(createDashboardRequest)

Create a new dashboard

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith/sdk-typescript';
import type { CreateDashboardOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardsApi(config);

  const body = {
    // CreateDashboardRequest
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
| **createDashboardRequest** | [CreateDashboardRequest](CreateDashboardRequest.md) |  | |

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
| **201** | Dashboard created |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteDashboard

> deleteDashboard(id)

Delete a dashboard

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith/sdk-typescript';
import type { DeleteDashboardRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardsApi(config);

  const body = {
    // string | Dashboard ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` | Dashboard ID | [Defaults to `undefined`] |

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
| **204** | Dashboard deleted |  -  |
| **404** | Dashboard not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getDashboard

> DashboardResponse getDashboard(id)

Get a dashboard by ID

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith/sdk-typescript';
import type { GetDashboardRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardsApi(config);

  const body = {
    // string | Dashboard ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` | Dashboard ID | [Defaults to `undefined`] |

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
| **404** | Dashboard not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listDashboards

> ListDashboards200Response listDashboards()

List all dashboards

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith/sdk-typescript';
import type { ListDashboardsRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
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

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateDashboard

> updateDashboard(id, updateDashboardRequest)

Update a dashboard

### Example

```ts
import {
  Configuration,
  DashboardsApi,
} from '@omnismith/sdk-typescript';
import type { UpdateDashboardOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new DashboardsApi(config);

  const body = {
    // string | Dashboard ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // UpdateDashboardRequest
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
| **id** | `string` | Dashboard ID | [Defaults to `undefined`] |
| **updateDashboardRequest** | [UpdateDashboardRequest](UpdateDashboardRequest.md) |  | |

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
| **200** | Dashboard updated |  -  |
| **404** | Dashboard not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

