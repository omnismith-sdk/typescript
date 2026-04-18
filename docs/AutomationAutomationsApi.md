# AutomationAutomationsApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createAutomation**](AutomationAutomationsApi.md#createautomationoperation) | **POST** /automation/automations | Create a new automation |
| [**deleteAutomation**](AutomationAutomationsApi.md#deleteautomation) | **DELETE** /automation/automations/{id} | Delete an automation |
| [**getAutomation**](AutomationAutomationsApi.md#getautomation) | **GET** /automation/automations/{id} | Get an automation by ID |
| [**listAutomationExecutions**](AutomationAutomationsApi.md#listautomationexecutions) | **GET** /automation/automations/{id}/executions | List automation executions |
| [**listAutomations**](AutomationAutomationsApi.md#listautomations) | **GET** /automation/automations | List automations |
| [**toggleAutomation**](AutomationAutomationsApi.md#toggleautomationoperation) | **PATCH** /automation/automations/{id}/toggle | Toggle automation enabled status |
| [**updateAutomation**](AutomationAutomationsApi.md#updateautomationoperation) | **PUT** /automation/automations/{id} | Update an automation |



## createAutomation

> CreateAttributeItem201Response createAutomation(createAutomationRequest)

Create a new automation

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith/sdk-typescript';
import type { CreateAutomationOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

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

[**CreateAttributeItem201Response**](CreateAttributeItem201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Automation created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAutomation

> deleteAutomation(id)

Delete an automation

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith/sdk-typescript';
import type { DeleteAutomationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **204** | Automation deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Automation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAutomation

> AutomationResponse getAutomation(id)

Get an automation by ID

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith/sdk-typescript';
import type { GetAutomationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` |  | [Defaults to `undefined`] |

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


## listAutomationExecutions

> ListAutomationExecutions200Response listAutomationExecutions(id, limit, offset, status)

List automation executions

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith/sdk-typescript';
import type { ListAutomationExecutionsRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

  const body = {
    // string | Automation ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // number | Number of results (optional)
    limit: 56,
    // number | Pagination offset (optional)
    offset: 56,
    // 'pending' | 'success' | 'partial_failure' | 'failed' | Filter by status (optional)
    status: status_example,
  } satisfies ListAutomationExecutionsRequest;

  try {
    const data = await api.listAutomationExecutions(body);
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
| **id** | `string` | Automation ID | [Defaults to `undefined`] |
| **limit** | `number` | Number of results | [Optional] [Defaults to `20`] |
| **offset** | `number` | Pagination offset | [Optional] [Defaults to `0`] |
| **status** | `pending`, `success`, `partial_failure`, `failed` | Filter by status | [Optional] [Defaults to `undefined`] [Enum: pending, success, partial_failure, failed] |

### Return type

[**ListAutomationExecutions200Response**](ListAutomationExecutions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of executions |  -  |
| **401** | Unauthorized |  -  |
| **404** | Automation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAutomations

> Array&lt;AutomationResponse&gt; listAutomations(templateId, isEnabled)

List automations

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith/sdk-typescript';
import type { ListAutomationsRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

  const body = {
    // string | Filter by template ID (optional)
    templateId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // boolean | Filter by enabled status (optional)
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
| **templateId** | `string` | Filter by template ID | [Optional] [Defaults to `undefined`] |
| **isEnabled** | `boolean` | Filter by enabled status | [Optional] [Defaults to `undefined`] |

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
| **200** | List of automations |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## toggleAutomation

> AutomationResponse toggleAutomation(id, toggleAutomationRequest)

Toggle automation enabled status

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith/sdk-typescript';
import type { ToggleAutomationOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` |  | [Defaults to `undefined`] |
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
| **200** | Automation toggled |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Automation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateAutomation

> updateAutomation(id, updateAutomationRequest)

Update an automation

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith/sdk-typescript';
import type { UpdateAutomationOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` |  | [Defaults to `undefined`] |
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
| **204** | Automation updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Automation not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

