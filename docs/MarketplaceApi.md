# MarketplaceApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteMarketplaceBlueprint**](MarketplaceApi.md#deletemarketplaceblueprint) | **DELETE** /marketplace/blueprints/{id} | Delete a marketplace blueprint |
| [**getMarketplaceBlueprint**](MarketplaceApi.md#getmarketplaceblueprint) | **GET** /marketplace/blueprints/{id} | Get marketplace blueprint details |
| [**installMarketplaceBlueprint**](MarketplaceApi.md#installmarketplaceblueprintoperation) | **POST** /marketplace/blueprints/{id}/install | Install a marketplace blueprint into a project |
| [**listMarketplaceKeywords**](MarketplaceApi.md#listmarketplacekeywords) | **GET** /marketplace/keywords | List all marketplace keywords with blueprint counts |
| [**publishMarketplaceBlueprint**](MarketplaceApi.md#publishmarketplaceblueprintoperation) | **POST** /marketplace/blueprints | Publish or update a marketplace blueprint |
| [**searchMarketplaceBlueprints**](MarketplaceApi.md#searchmarketplaceblueprints) | **GET** /marketplace/blueprints | Search marketplace blueprints |



## deleteMarketplaceBlueprint

> deleteMarketplaceBlueprint(id)

Delete a marketplace blueprint

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith/sdk-typescript';
import type { DeleteMarketplaceBlueprintRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketplaceApi(config);

  const body = {
    // string | Blueprint ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteMarketplaceBlueprintRequest;

  try {
    const data = await api.deleteMarketplaceBlueprint(body);
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
| **id** | `string` | Blueprint ID | [Defaults to `undefined`] |

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
| **204** | Blueprint deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMarketplaceBlueprint

> GetMarketplaceBlueprint200Response getMarketplaceBlueprint(id)

Get marketplace blueprint details

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith/sdk-typescript';
import type { GetMarketplaceBlueprintRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const api = new MarketplaceApi();

  const body = {
    // string | Blueprint ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` | Blueprint ID | [Defaults to `undefined`] |

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
| **200** | Blueprint detail |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## installMarketplaceBlueprint

> installMarketplaceBlueprint(id, installMarketplaceBlueprintRequest)

Install a marketplace blueprint into a project

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith/sdk-typescript';
import type { InstallMarketplaceBlueprintOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketplaceApi(config);

  const body = {
    // string | Blueprint ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
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
| **id** | `string` | Blueprint ID | [Defaults to `undefined`] |
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
| **204** | Blueprint installed successfully |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Blueprint not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listMarketplaceKeywords

> ListMarketplaceKeywords200Response listMarketplaceKeywords()

List all marketplace keywords with blueprint counts

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith/sdk-typescript';
import type { ListMarketplaceKeywordsRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const api = new MarketplaceApi();

  try {
    const data = await api.listMarketplaceKeywords();
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

[**ListMarketplaceKeywords200Response**](ListMarketplaceKeywords200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Distinct keywords sorted by popularity |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## publishMarketplaceBlueprint

> GetMarketplaceBlueprint200Response publishMarketplaceBlueprint(publishMarketplaceBlueprintRequest)

Publish or update a marketplace blueprint

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith/sdk-typescript';
import type { PublishMarketplaceBlueprintOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketplaceApi(config);

  const body = {
    // PublishMarketplaceBlueprintRequest
    publishMarketplaceBlueprintRequest: ...,
  } satisfies PublishMarketplaceBlueprintOperationRequest;

  try {
    const data = await api.publishMarketplaceBlueprint(body);
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
| **publishMarketplaceBlueprintRequest** | [PublishMarketplaceBlueprintRequest](PublishMarketplaceBlueprintRequest.md) |  | |

### Return type

[**GetMarketplaceBlueprint200Response**](GetMarketplaceBlueprint200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Blueprint created |  -  |
| **200** | Blueprint updated |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchMarketplaceBlueprints

> SearchMarketplaceBlueprints200Response searchMarketplaceBlueprints(search, keywords, limit, offset, sortBy, sortDirection, featured)

Search marketplace blueprints

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith/sdk-typescript';
import type { SearchMarketplaceBlueprintsRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const api = new MarketplaceApi();

  const body = {
    // string | Free-text search on title and description (optional)
    search: search_example,
    // string | Comma-separated keywords to filter by (optional)
    keywords: keywords_example,
    // number | Number of results per page (optional)
    limit: 56,
    // number | Pagination offset (optional)
    offset: 56,
    // 'created_at' | 'installs' | 'title' | Sort field (optional)
    sortBy: sortBy_example,
    // 'asc' | 'desc' | Sort direction (optional)
    sortDirection: sortDirection_example,
    // boolean | Filter by featured status (optional)
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
| **search** | `string` | Free-text search on title and description | [Optional] [Defaults to `undefined`] |
| **keywords** | `string` | Comma-separated keywords to filter by | [Optional] [Defaults to `undefined`] |
| **limit** | `number` | Number of results per page | [Optional] [Defaults to `20`] |
| **offset** | `number` | Pagination offset | [Optional] [Defaults to `0`] |
| **sortBy** | `created_at`, `installs`, `title` | Sort field | [Optional] [Defaults to `&#39;created_at&#39;`] [Enum: created_at, installs, title] |
| **sortDirection** | `asc`, `desc` | Sort direction | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **featured** | `boolean` | Filter by featured status | [Optional] [Defaults to `undefined`] |

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
| **200** | Marketplace blueprints list |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

