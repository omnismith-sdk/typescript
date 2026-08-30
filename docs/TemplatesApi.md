# TemplatesApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createTemplate**](TemplatesApi.md#createtemplateoperation) | **POST** /templates | Create a new template |
| [**deleteTemplate**](TemplatesApi.md#deletetemplate) | **DELETE** /templates/{id} | Delete a template |
| [**getTemplate**](TemplatesApi.md#gettemplate) | **GET** /templates/{id} | Get a template by ID or slug |
| [**listTemplateEntityCounts**](TemplatesApi.md#listtemplateentitycounts) | **GET** /templates/entity-counts | List entity counts per template |
| [**listTemplates**](TemplatesApi.md#listtemplates) | **GET** /templates | List all templates |
| [**patchTemplate**](TemplatesApi.md#patchtemplateoperation) | **PATCH** /templates/{id} | Patch a template (granular partial update) |
| [**updateTemplate**](TemplatesApi.md#updatetemplateoperation) | **PUT** /templates/{id} | Update a template (full replacement) |



## createTemplate

> CreateTemplate201Response createTemplate(createTemplateRequest)

Create a new template

Creates a new dynamic schema template (content type) in the project. Accepts template name, optional description, category, unique slug, attribute bindings, and UI layout groups. Attribute bindings can be defined using structured &#x60;attributes&#x60; (with optional &#x60;default_value&#x60; validated against attribute kind/data type) or flat &#x60;attribute_ids&#x60; / &#x60;attribute_slugs&#x60;. Visual layout groups organize attributes into 1- or 2-column sections with optional icons. Creating templates is subject to tier quota limits.

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


## deleteTemplate

> deleteTemplate(id)

Delete a template

Soft-deletes a template definition by UUID or slug. Soft-deleted templates are hidden from normal listings, and entity creation under deleted templates is prevented.

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


## getTemplate

> TemplateResponse getTemplate(id)

Get a template by ID or slug

Retrieves complete template schema details by UUID or unique slug, including ordered attribute bindings, default values per attribute, and visual UI layout groups. Automatically filters out any restricted attributes the caller is not permitted to view.

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


## listTemplateEntityCounts

> ListTemplateEntityCounts200Response listTemplateEntityCounts()

List entity counts per template

Returns total entity record counts grouped by template UUID for all accessible templates in the current project context. Efficiently calculates counts and honors role-based resource access restrictions.

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
| **200** | List of all project templates |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## patchTemplate

> patchTemplate(id, patchTemplateRequest)

Patch a template (granular partial update)

Applies partial modifications to an existing template by UUID or slug without overwriting omitted fields. Allows modifying name, description, category, slug, attribute associations (with validated default values), or visual layout groups independently. Safely merges and preserves any restricted attributes.

### Example

```ts
import {
  Configuration,
  TemplatesApi,
} from '@omnismith-sdk/typescript';
import type { PatchTemplateOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new TemplatesApi(config);

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


## updateTemplate

> updateTemplate(id, updateTemplateRequest)

Update a template (full replacement)

Performs a full update of an existing template definition by UUID or slug. Replaces name, description, category, slug, attribute associations (with validated per-attribute default values), and UI layout groups. If the caller lacks permissions to certain restricted attributes, those restricted attributes are automatically preserved in the template.

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

