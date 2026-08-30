# AccessTokensApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createAccessToken**](AccessTokensApi.md#createaccesstokenoperation) | **POST** /access-tokens | Create a programmatic API access token |
| [**deleteAccessToken**](AccessTokensApi.md#deleteaccesstoken) | **DELETE** /access-tokens/{id} | Delete an API access token |
| [**listAccessTokens**](AccessTokensApi.md#listaccesstokens) | **GET** /access-tokens | List API access tokens |



## createAccessToken

> CreateAccessToken201Response createAccessToken(createAccessTokenRequest)

Create a programmatic API access token

Generates a new programmatic API access token prefixed with &#x60;omni_&#x60; (e.g. &#x60;omni_live_secret_key_...&#x60;) for the authenticated user within the active project context. The token inherits the user\&#39;s current role permissions and scopes for authenticating automated API clients and scripts. The raw secret key is returned exactly once in the response and cannot be recovered later.

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
| **201** | Access token generated successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAccessToken

> deleteAccessToken(id)

Delete an API access token

Permanently revokes and removes a programmatic API access token by its unique identifier. Any future API request using the revoked secret key will immediately fail authentication with a 401 Unauthorized status.

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
    // string | Unique UUIDv7 identifier of the access token to delete
    id: 0192a543-7f28-72b1-9b7e-97c997321034,
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
| **id** | `string` | Unique UUIDv7 identifier of the access token to delete | [Defaults to `undefined`] |

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
| **204** | Access token deleted successfully |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAccessTokens

> ListAccessTokens200Response listAccessTokens()

List API access tokens

Retrieves all active and expired programmatic API access tokens created by the authenticated user for the active project context. Returns token metadata including unique ID, user-assigned label, creation date, expiration timestamp, and last used timestamp. Note: raw secret API keys are only displayed once upon generation and are never returned in list responses.

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
| **200** | List of access token metadata records |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

