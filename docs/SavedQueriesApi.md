# SavedQueriesApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createSavedQuery**](SavedQueriesApi.md#createsavedqueryoperation) | **POST** /saved-queries | Create a saved query |
| [**deleteSavedQuery**](SavedQueriesApi.md#deletesavedquery) | **DELETE** /saved-queries/{id} | Delete a saved query |
| [**executeSavedQuery**](SavedQueriesApi.md#executesavedquery) | **POST** /saved-queries/{id}/execute | Execute a saved query (count matches) |
| [**getSavedQuery**](SavedQueriesApi.md#getsavedquery) | **GET** /saved-queries/{id} | Get a saved query |
| [**listSavedQueries**](SavedQueriesApi.md#listsavedqueries) | **GET** /saved-queries | List saved queries |



## createSavedQuery

> CreateAttributeItem201Response createSavedQuery(createSavedQueryRequest)

Create a saved query

### Example

```ts
import {
  Configuration,
  SavedQueriesApi,
} from '@omnismith/sdk-typescript';
import type { CreateSavedQueryOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SavedQueriesApi(config);

  const body = {
    // CreateSavedQueryRequest
    createSavedQueryRequest: ...,
  } satisfies CreateSavedQueryOperationRequest;

  try {
    const data = await api.createSavedQuery(body);
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
| **createSavedQueryRequest** | [CreateSavedQueryRequest](CreateSavedQueryRequest.md) |  | |

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
| **201** | Saved query created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteSavedQuery

> deleteSavedQuery(id)

Delete a saved query

### Example

```ts
import {
  Configuration,
  SavedQueriesApi,
} from '@omnismith/sdk-typescript';
import type { DeleteSavedQueryRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SavedQueriesApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteSavedQueryRequest;

  try {
    const data = await api.deleteSavedQuery(body);
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
| **204** | Deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## executeSavedQuery

> ExecuteSavedQuery200Response executeSavedQuery(id)

Execute a saved query (count matches)

### Example

```ts
import {
  Configuration,
  SavedQueriesApi,
} from '@omnismith/sdk-typescript';
import type { ExecuteSavedQueryRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SavedQueriesApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies ExecuteSavedQueryRequest;

  try {
    const data = await api.executeSavedQuery(body);
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

[**ExecuteSavedQuery200Response**](ExecuteSavedQuery200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Count results |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getSavedQuery

> any getSavedQuery(id)

Get a saved query

### Example

```ts
import {
  Configuration,
  SavedQueriesApi,
} from '@omnismith/sdk-typescript';
import type { GetSavedQueryRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SavedQueriesApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetSavedQueryRequest;

  try {
    const data = await api.getSavedQuery(body);
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

**any**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Saved query |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSavedQueries

> ListSavedQueries200Response listSavedQueries()

List saved queries

### Example

```ts
import {
  Configuration,
  SavedQueriesApi,
} from '@omnismith/sdk-typescript';
import type { ListSavedQueriesRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SavedQueriesApi(config);

  try {
    const data = await api.listSavedQueries();
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

[**ListSavedQueries200Response**](ListSavedQueries200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Saved queries |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

