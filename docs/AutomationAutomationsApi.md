# AutomationAutomationsApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createAutomation**](AutomationAutomationsApi.md#createautomationoperation) | **POST** /automation/automations | Create an automation rule |
| [**deleteAutomation**](AutomationAutomationsApi.md#deleteautomation) | **DELETE** /automation/automations/{id} | Delete an automation |
| [**getAutomation**](AutomationAutomationsApi.md#getautomation) | **GET** /automation/automations/{id} | Get an automation by ID |
| [**listAutomationExecutions**](AutomationAutomationsApi.md#listautomationexecutions) | **GET** /automation/automations/{id}/executions | List automation execution logs |
| [**listAutomations**](AutomationAutomationsApi.md#listautomations) | **GET** /automation/automations | List project automations |
| [**toggleAutomation**](AutomationAutomationsApi.md#toggleautomationoperation) | **PATCH** /automation/automations/{id}/toggle | Toggle automation enabled status |
| [**updateAutomation**](AutomationAutomationsApi.md#updateautomationoperation) | **PUT** /automation/automations/{id} | Update an automation |



## createAutomation

> CreateAutomation201Response createAutomation(createAutomationRequest)

Create an automation rule

Creates a new event-driven automation rule within the current project. Configures event trigger criteria (such as &#x60;on_entity_created&#x60;, &#x60;on_entity_updated&#x60;, or &#x60;on_attribute_changed&#x60;), multi-condition filters evaluating attribute values (using operators &#x60;eq&#x60;, &#x60;neq&#x60;, &#x60;gt&#x60;, &#x60;gte&#x60;, &#x60;lt&#x60;, &#x60;lte&#x60;, &#x60;contains&#x60;, &#x60;not_contains&#x60;, &#x60;is_empty&#x60;, &#x60;is_not_empty&#x60; across current value or delta modes), automated action targets (&#x60;telegram&#x60;, &#x60;webhook&#x60;, &#x60;push&#x60;), and an optional cooldown window in seconds to throttle repeated firings for the same entity.

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith-sdk/typescript';
import type { CreateAutomationOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
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


## deleteAutomation

> deleteAutomation(id)

Delete an automation

Permanently deletes an automation rule by UUID, unbinding event listeners and stopping all future evaluations and action dispatches for that rule.

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith-sdk/typescript';
import type { DeleteAutomationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

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


## getAutomation

> AutomationResponse getAutomation(id)

Get an automation by ID

Retrieves the complete configuration of a specific automation rule by its UUID, including trigger event types, template/attribute references, condition comparison expressions, action payloads, execution cooldown interval, and the timestamp of its last execution.

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith-sdk/typescript';
import type { GetAutomationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

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


## listAutomationExecutions

> ListAutomationExecutions200Response listAutomationExecutions(id, limit, offset, status)

List automation execution logs

Retrieves paginated execution logs and audit history for a specific automation rule. Each execution log records the triggering entity ID, trigger timestamp, execution completion time, final status (&#x60;pending&#x60;, &#x60;success&#x60;, &#x60;partial_failure&#x60;, &#x60;failed&#x60;), detailed action dispatch outcomes with error messages, and top-level execution errors.

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith-sdk/typescript';
import type { ListAutomationExecutionsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

  const body = {
    // string | Automation UUID to fetch execution history for
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60001,
    // number | Maximum number of execution log entries to return per page (optional)
    limit: 20,
    // number | Number of execution log records to skip for pagination (optional)
    offset: 0,
    // 'pending' | 'success' | 'partial_failure' | 'failed' | Filter execution logs by execution outcome status (optional)
    status: success,
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
| **id** | `string` | Automation UUID to fetch execution history for | [Defaults to `undefined`] |
| **limit** | `number` | Maximum number of execution log entries to return per page | [Optional] [Defaults to `20`] |
| **offset** | `number` | Number of execution log records to skip for pagination | [Optional] [Defaults to `0`] |
| **status** | `pending`, `success`, `partial_failure`, `failed` | Filter execution logs by execution outcome status | [Optional] [Defaults to `undefined`] [Enum: pending, success, partial_failure, failed] |

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
| **200** | Paginated list of execution logs |  -  |
| **401** | Unauthorized |  -  |
| **404** | Automation not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAutomations

> Array&lt;AutomationResponse&gt; listAutomations(templateId, isEnabled)

List project automations

Retrieves all automation rules configured within the current project context. Automations define event-driven workflows triggered by entity lifecycle events (such as entity creation, attribute updates, or metric threshold changes), evaluated against multi-attribute conditions, and dispatched to configured action channels (Telegram, webhooks, mobile push). Results can be filtered by entity template or active status.

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith-sdk/typescript';
import type { ListAutomationsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

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


## toggleAutomation

> AutomationResponse toggleAutomation(id, toggleAutomationRequest)

Toggle automation enabled status

Enables or pauses an automation rule without altering its trigger definitions, condition criteria, or action configurations. Paused automations are ignored during event processing.

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith-sdk/typescript';
import type { ToggleAutomationOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

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


## updateAutomation

> updateAutomation(id, updateAutomationRequest)

Update an automation

Updates an existing automation rule by UUID. Supports modifying rule name, description, trigger event definitions, condition filter criteria, action dispatches, and cooldown throttle settings.

### Example

```ts
import {
  Configuration,
  AutomationAutomationsApi,
} from '@omnismith-sdk/typescript';
import type { UpdateAutomationOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationAutomationsApi(config);

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

