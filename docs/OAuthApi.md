# OAuthApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**approveOAuthAuthorization**](OAuthApi.md#approveoauthauthorizationoperation) | **POST** /oauth/authorize/approve | Approve OAuth Authorization Consent |
| [**exchangeOAuthToken**](OAuthApi.md#exchangeoauthtoken) | **POST** /oauth/token | Exchange OAuth 2.0 Token |
| [**getJwks**](OAuthApi.md#getjwks) | **GET** /.well-known/jwks.json | Get JSON Web Key Set |
| [**getOAuthAuthorizeInfo**](OAuthApi.md#getoauthauthorizeinfo) | **GET** /oauth/authorize/info | Get OAuth Authorization Consent Screen Info |
| [**getOAuthServerMetadata**](OAuthApi.md#getoauthservermetadata) | **GET** /.well-known/oauth-authorization-server | Get OAuth Authorization Server Metadata |
| [**registerOAuthClient**](OAuthApi.md#registeroauthclientoperation) | **POST** /oauth/register | Register Dynamic OAuth Client |
| [**revokeOAuthToken**](OAuthApi.md#revokeoauthtokenoperation) | **POST** /oauth/revoke | Revoke OAuth Token |



## approveOAuthAuthorization

> ApproveOAuthAuthorization200Response approveOAuthAuthorization(approveOAuthAuthorizationRequest)

Approve OAuth Authorization Consent

Approves client access to a specific Omnismith project and generates an authorization code.

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@omnismith-sdk/typescript';
import type { ApproveOAuthAuthorizationOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OAuthApi(config);

  const body = {
    // ApproveOAuthAuthorizationRequest
    approveOAuthAuthorizationRequest: ...,
  } satisfies ApproveOAuthAuthorizationOperationRequest;

  try {
    const data = await api.approveOAuthAuthorization(body);
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
| **approveOAuthAuthorizationRequest** | [ApproveOAuthAuthorizationRequest](ApproveOAuthAuthorizationRequest.md) |  | |

### Return type

[**ApproveOAuthAuthorization200Response**](ApproveOAuthAuthorization200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Authorization approved and code generated |  -  |
| **400** | Invalid approval parameters |  -  |
| **401** | User not authenticated |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## exchangeOAuthToken

> ExchangeOAuthToken200Response exchangeOAuthToken(oAuthTokenRequest)

Exchange OAuth 2.0 Token

Exchanges an authorization code or refresh token for a standard RS256 JWT access token (RFC 6749 / RFC 7636).

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@omnismith-sdk/typescript';
import type { ExchangeOAuthTokenRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new OAuthApi();

  const body = {
    // OAuthTokenRequest
    oAuthTokenRequest: ...,
  } satisfies ExchangeOAuthTokenRequest;

  try {
    const data = await api.exchangeOAuthToken(body);
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
| **oAuthTokenRequest** | [OAuthTokenRequest](OAuthTokenRequest.md) |  | |

### Return type

[**ExchangeOAuthToken200Response**](ExchangeOAuthToken200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Token issued successfully |  -  |
| **400** | Invalid grant or request parameters |  -  |
| **401** | Invalid client credentials |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getJwks

> GetJwks200Response getJwks()

Get JSON Web Key Set

Returns the JSON Web Key Set (RFC 7517) containing the active public cryptographic keys used to verify RS256 JWT access tokens issued by the platform.

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@omnismith-sdk/typescript';
import type { GetJwksRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new OAuthApi();

  try {
    const data = await api.getJwks();
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

[**GetJwks200Response**](GetJwks200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | JSON Web Key Set |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getOAuthAuthorizeInfo

> GetOAuthAuthorizeInfo200Response getOAuthAuthorizeInfo(clientId, redirectUri, responseType, scope, codeChallenge, codeChallengeMethod, state)

Get OAuth Authorization Consent Screen Info

Retrieves client metadata, requested scopes, verified user identity, and accessible projects to render the OAuth consent interface.

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@omnismith-sdk/typescript';
import type { GetOAuthAuthorizeInfoRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new OAuthApi(config);

  const body = {
    // string | Registered OAuth client identifier
    clientId: omni_client_0195a8f2c3e471238000000000000001,
    // string | Target redirection URI matching registered client URIs
    redirectUri: https://claude.ai/api/mcp/oauth_callback,
    // string | OAuth response type (must be \"code\")
    responseType: code,
    // string | Space-delimited requested scopes (optional)
    scope: omnismith:all,
    // string | PKCE code challenge string (RFC 7636) (optional)
    codeChallenge: E9Melhoa2OwvFrGMTJguCH5SZXgk6uKUaz312M20O48,
    // 'S256' | 'plain' | PKCE code challenge transformation method (optional)
    codeChallengeMethod: S256,
    // string | Opaque client state parameter for CSRF mitigation (optional)
    state: state_xyz123,
  } satisfies GetOAuthAuthorizeInfoRequest;

  try {
    const data = await api.getOAuthAuthorizeInfo(body);
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
| **clientId** | `string` | Registered OAuth client identifier | [Defaults to `undefined`] |
| **redirectUri** | `string` | Target redirection URI matching registered client URIs | [Defaults to `undefined`] |
| **responseType** | `string` | OAuth response type (must be \&quot;code\&quot;) | [Defaults to `&#39;code&#39;`] |
| **scope** | `string` | Space-delimited requested scopes | [Optional] [Defaults to `undefined`] |
| **codeChallenge** | `string` | PKCE code challenge string (RFC 7636) | [Optional] [Defaults to `undefined`] |
| **codeChallengeMethod** | `S256`, `plain` | PKCE code challenge transformation method | [Optional] [Defaults to `&#39;S256&#39;`] [Enum: S256, plain] |
| **state** | `string` | Opaque client state parameter for CSRF mitigation | [Optional] [Defaults to `undefined`] |

### Return type

[**GetOAuthAuthorizeInfo200Response**](GetOAuthAuthorizeInfo200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Authorization consent info and accessible projects |  -  |
| **400** | Invalid authorization request parameters |  -  |
| **401** | User not authenticated |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getOAuthServerMetadata

> GetOAuthServerMetadata200Response getOAuthServerMetadata()

Get OAuth Authorization Server Metadata

Returns OAuth 2.0 Authorization Server Metadata (RFC 8414) defining the endpoints, supported grant types, and PKCE challenge methods for automated client configuration.

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@omnismith-sdk/typescript';
import type { GetOAuthServerMetadataRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new OAuthApi();

  try {
    const data = await api.getOAuthServerMetadata();
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

[**GetOAuthServerMetadata200Response**](GetOAuthServerMetadata200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OAuth 2.0 Authorization Server Metadata |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## registerOAuthClient

> RegisterOAuthClient201Response registerOAuthClient(registerOAuthClientRequest)

Register Dynamic OAuth Client

Dynamically registers a new OAuth client per RFC 7591 (Dynamic Client Registration). Generates unique client credentials and registers authorized callback redirection URIs.

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@omnismith-sdk/typescript';
import type { RegisterOAuthClientOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new OAuthApi();

  const body = {
    // RegisterOAuthClientRequest
    registerOAuthClientRequest: ...,
  } satisfies RegisterOAuthClientOperationRequest;

  try {
    const data = await api.registerOAuthClient(body);
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
| **registerOAuthClientRequest** | [RegisterOAuthClientRequest](RegisterOAuthClientRequest.md) |  | |

### Return type

[**RegisterOAuthClient201Response**](RegisterOAuthClient201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Client registered successfully |  -  |
| **400** | Invalid client registration parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeOAuthToken

> RevokeOAuthToken200Response revokeOAuthToken(revokeOAuthTokenRequest)

Revoke OAuth Token

Revokes an issued OAuth access token or refresh token per RFC 7009 (Token Revocation). Returns success even if the token was already revoked or expired.

### Example

```ts
import {
  Configuration,
  OAuthApi,
} from '@omnismith-sdk/typescript';
import type { RevokeOAuthTokenOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new OAuthApi();

  const body = {
    // RevokeOAuthTokenRequest
    revokeOAuthTokenRequest: ...,
  } satisfies RevokeOAuthTokenOperationRequest;

  try {
    const data = await api.revokeOAuthToken(body);
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
| **revokeOAuthTokenRequest** | [RevokeOAuthTokenRequest](RevokeOAuthTokenRequest.md) |  | |

### Return type

[**RevokeOAuthToken200Response**](RevokeOAuthToken200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Token revoked successfully (or was already invalid) |  -  |
| **400** | Invalid revocation parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

