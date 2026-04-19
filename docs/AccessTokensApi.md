# AccessTokensApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createAccessToken**](AccessTokensApi.md#createaccesstokenoperation) | **POST** /access-tokens | Create an API access token |
| [**deleteAccessToken**](AccessTokensApi.md#deleteaccesstoken) | **DELETE** /access-tokens/{id} | Delete an API access token |
| [**listAccessTokens**](AccessTokensApi.md#listaccesstokens) | **GET** /access-tokens | List API access tokens |



## createAccessToken

> CreateAccessToken201Response createAccessToken(createAccessTokenRequest)

Create an API access token

Creates a new API access token for the current user and project. The raw API key is returned once in the response and cannot be retrieved again.

### Example

```ts
import {
  Configuration,
  AccessTokensApi,
} from '@omnismith-sdk/typescript';
import type { CreateAccessTokenOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccessTokensApi(config);

  const body = {
    // CreateAccessTokenRequest
    createAccessTokenRequest: ...,
  } satisfies CreateAccessTokenOperationRequest;

  try {
    const data = await api.createAccessToken(body);
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
| **createAccessTokenRequest** | [CreateAccessTokenRequest](CreateAccessTokenRequest.md) |  | |

### Return type

[**CreateAccessToken201Response**](CreateAccessToken201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Access token created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAccessToken

> deleteAccessToken(id)

Delete an API access token

### Example

```ts
import {
  Configuration,
  AccessTokensApi,
} from '@omnismith-sdk/typescript';
import type { DeleteAccessTokenRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccessTokensApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteAccessTokenRequest;

  try {
    const data = await api.deleteAccessToken(body);
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


## listAccessTokens

> ListAccessTokens200Response listAccessTokens()

List API access tokens

Returns all access tokens for the current user and project.

### Example

```ts
import {
  Configuration,
  AccessTokensApi,
} from '@omnismith-sdk/typescript';
import type { ListAccessTokensRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AccessTokensApi(config);

  try {
    const data = await api.listAccessTokens();
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

[**ListAccessTokens200Response**](ListAccessTokens200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Access tokens |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

