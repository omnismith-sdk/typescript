# TemplatesApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createTemplate**](TemplatesApi.md#createtemplateoperation) | **POST** /templates | Create a new template |
| [**deleteTemplate**](TemplatesApi.md#deletetemplate) | **DELETE** /templates/{id} | Delete a template |
| [**getTemplate**](TemplatesApi.md#gettemplate) | **GET** /templates/{id} | Get a template |
| [**listTemplateEntityCounts**](TemplatesApi.md#listtemplateentitycounts) | **GET** /templates/entity-counts | List entity counts per template |
| [**listTemplates**](TemplatesApi.md#listtemplates) | **GET** /templates | List templates |
| [**updateTemplate**](TemplatesApi.md#updatetemplateoperation) | **PUT** /templates/{id} | Update a template |



## createTemplate

> CreateAttributeItem201Response createTemplate(createTemplateRequest)

Create a new template

### Example

```ts
import {
  Configuration,
  TemplatesApi,
} from '@omnismith-sdk/typescript';
import type { CreateTemplateOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TemplatesApi(config);

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

[**CreateAttributeItem201Response**](CreateAttributeItem201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Template created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteTemplate

> deleteTemplate(id)

Delete a template

### Example

```ts
import {
  Configuration,
  TemplatesApi,
} from '@omnismith-sdk/typescript';
import type { DeleteTemplateRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TemplatesApi(config);

  const body = {
    // string | Template ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` | Template ID | [Defaults to `undefined`] |

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
| **204** | Template deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getTemplate

> TemplateResponse getTemplate(id)

Get a template

### Example

```ts
import {
  Configuration,
  TemplatesApi,
} from '@omnismith-sdk/typescript';
import type { GetTemplateRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TemplatesApi(config);

  const body = {
    // string | Template ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` | Template ID | [Defaults to `undefined`] |

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


## listTemplateEntityCounts

> ListTemplateEntityCounts200Response listTemplateEntityCounts()

List entity counts per template

### Example

```ts
import {
  Configuration,
  TemplatesApi,
} from '@omnismith-sdk/typescript';
import type { ListTemplateEntityCountsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TemplatesApi(config);

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
| **200** | Counts per template |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTemplates

> ListTemplates200Response listTemplates()

List templates

### Example

```ts
import {
  Configuration,
  TemplatesApi,
} from '@omnismith-sdk/typescript';
import type { ListTemplatesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TemplatesApi(config);

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
| **200** | List of templates |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateTemplate

> updateTemplate(id, updateTemplateRequest)

Update a template

### Example

```ts
import {
  Configuration,
  TemplatesApi,
} from '@omnismith-sdk/typescript';
import type { UpdateTemplateOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TemplatesApi(config);

  const body = {
    // string | Template ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` | Template ID | [Defaults to `undefined`] |
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
| **204** | Template updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

