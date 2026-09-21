# MarketplaceApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteMarketplaceBlueprint**](MarketplaceApi.md#deletemarketplaceblueprint) | **DELETE** /marketplace/blueprints/{id} | Delete a marketplace blueprint |
| [**getMarketplaceBlueprint**](MarketplaceApi.md#getmarketplaceblueprint) | **GET** /marketplace/blueprints/{id} | Get marketplace blueprint details |
| [**installMarketplaceBlueprint**](MarketplaceApi.md#installmarketplaceblueprintoperation) | **POST** /marketplace/blueprints/{id}/install | Install a marketplace blueprint into a project |
| [**listMarketplaceKeywords**](MarketplaceApi.md#listmarketplacekeywords) | **GET** /marketplace/keywords | List marketplace keywords |
| [**publishMarketplaceBlueprint**](MarketplaceApi.md#publishmarketplaceblueprintoperation) | **POST** /marketplace/blueprints | Publish or update a marketplace blueprint |
| [**searchMarketplaceBlueprints**](MarketplaceApi.md#searchmarketplaceblueprints) | **GET** /marketplace/blueprints | Search marketplace blueprints |



## deleteMarketplaceBlueprint

> deleteMarketplaceBlueprint(id)

Delete a marketplace blueprint

Permanently removes a published blueprint from the marketplace catalog. Only the author who published the blueprint or a system administrator has permission to delete it.

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith-sdk/typescript';
import type { DeleteMarketplaceBlueprintRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketplaceApi(config);

  const body = {
    // string | Unique blueprint UUID to delete
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60003,
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
| **id** | `string` | Unique blueprint UUID to delete | [Defaults to `undefined`] |

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
| **204** | Blueprint successfully deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden - Not the owner of the blueprint |  -  |
| **404** | Blueprint not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getMarketplaceBlueprint

> GetMarketplaceBlueprint200Response getMarketplaceBlueprint(id)

Get marketplace blueprint details

Retrieves complete information for a specific marketplace blueprint by its UUID. Returns full blueprint metadata, publisher details, popularity metrics, and packaged blueprint schema definition containing template schemas, attribute configurations, the rules and actions of those templates, and optional demo entities.

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith-sdk/typescript';
import type { GetMarketplaceBlueprintRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new MarketplaceApi();

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


## installMarketplaceBlueprint

> installMarketplaceBlueprint(id, xOmnismithProjectId, installMarketplaceBlueprintRequest)

Install a marketplace blueprint into a project

Installs a marketplace blueprint into the project the request acts on. Provisions all packaged templates, attributes, relationships, rules and actions defined in the blueprint schema, and optionally populates sample demo entities. Automatically increments the installation count for the blueprint.

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith-sdk/typescript';
import type { InstallMarketplaceBlueprintOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketplaceApi(config);

  const body = {
    // string | Unique UUID of the blueprint to install
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60003,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
    // InstallMarketplaceBlueprintRequest (optional)
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
| **installMarketplaceBlueprintRequest** | [InstallMarketplaceBlueprintRequest](InstallMarketplaceBlueprintRequest.md) |  | [Optional] |

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
| **403** | Forbidden - insufficient permissions, or the selected project is not one the credential may act in |  -  |
| **404** | Blueprint not found |  -  |
| **422** | Validation Error |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listMarketplaceKeywords

> ListMarketplaceKeywords200Response listMarketplaceKeywords()

List marketplace keywords

Retrieves all distinct categorization keywords and tags associated with published blueprints along with their total occurrence count, ordered by popularity descending. Useful for populating discovery tags, filters, and keyword clouds.

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith-sdk/typescript';
import type { ListMarketplaceKeywordsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
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

> GetMarketplaceBlueprint200Response publishMarketplaceBlueprint(publishMarketplaceBlueprintRequest, xOmnismithProjectId)

Publish or update a marketplace blueprint

Publishes a new blueprint to the public marketplace or updates an existing blueprint owned by the authenticated user. Snapshots selected templates, their attributes and list items, and their enabled rules and actions into an exportable blueprint package with title, description, and searchable keywords.

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith-sdk/typescript';
import type { PublishMarketplaceBlueprintOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new MarketplaceApi(config);

  const body = {
    // PublishMarketplaceBlueprintRequest
    publishMarketplaceBlueprintRequest: ...,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **201** | Blueprint successfully published |  -  |
| **200** | Blueprint successfully updated |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden - Not the owner of the blueprint |  -  |
| **422** | Validation Error |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## searchMarketplaceBlueprints

> SearchMarketplaceBlueprints200Response searchMarketplaceBlueprints(search, keywords, limit, offset, sortBy, sortDirection, featured)

Search marketplace blueprints

Searches and lists public blueprints available in the marketplace catalog. Blueprints package reusable template schemas, attribute definitions, and sample data that users can install directly into their projects. Supports full-text search across titles and descriptions, keyword tag filtering, filtering by featured status, and sorting by creation date, install counts, or title.

### Example

```ts
import {
  Configuration,
  MarketplaceApi,
} from '@omnismith-sdk/typescript';
import type { SearchMarketplaceBlueprintsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new MarketplaceApi();

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

