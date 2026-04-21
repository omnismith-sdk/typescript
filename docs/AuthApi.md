# AuthApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getMyPermissions**](AuthApi.md#getmypermissions) | **GET** /auth/me/permissions | Get current user\&#39;s role permissions |
| [**googleLogin**](AuthApi.md#googleloginoperation) | **POST** /auth/google-login | Login or register via Google Sign-In |
| [**listSessions**](AuthApi.md#listsessions) | **GET** /auth/sessions | List recent login sessions |
| [**login**](AuthApi.md#loginoperation) | **POST** /auth/login | Login user |
| [**refreshToken**](AuthApi.md#refreshtokenoperation) | **POST** /auth/refresh | Refresh access token |
| [**revokeSession**](AuthApi.md#revokesession) | **DELETE** /auth/sessions/{id} | Revoke a login session |
| [**switchProject**](AuthApi.md#switchprojectoperation) | **POST** /auth/switch-project | Switch active project context |



## getMyPermissions

> GetMyPermissions200Response getMyPermissions()

Get current user\&#39;s role permissions

Returns the permissions for the authenticated user\&#39;s current role. Returns [\&quot;*\&quot;] for project owners (full access) or an empty array if no role is assigned.

### Example

```ts
import {
  Configuration,
  AuthApi,
} from '@omnismith-sdk/typescript';
import type { GetMyPermissionsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AuthApi(config);

  try {
    const data = await api.getMyPermissions();
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

[**GetMyPermissions200Response**](GetMyPermissions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of permission strings |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## googleLogin

> GoogleLogin200Response googleLogin(googleLoginRequest)

Login or register via Google Sign-In

Authenticates a user using a Google ID token. If the user does not exist, a new account is automatically created.

### Example

```ts
import {
  Configuration,
  AuthApi,
} from '@omnismith-sdk/typescript';
import type { GoogleLoginOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new AuthApi();

  const body = {
    // GoogleLoginRequest
    googleLoginRequest: ...,
  } satisfies GoogleLoginOperationRequest;

  try {
    const data = await api.googleLogin(body);
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
| **googleLoginRequest** | [GoogleLoginRequest](GoogleLoginRequest.md) |  | |

### Return type

[**GoogleLogin200Response**](GoogleLogin200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Login successful |  -  |
| **422** | Validation Error |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSessions

> ListSessions200Response listSessions()

List recent login sessions

### Example

```ts
import {
  Configuration,
  AuthApi,
} from '@omnismith-sdk/typescript';
import type { ListSessionsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AuthApi(config);

  try {
    const data = await api.listSessions();
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

[**ListSessions200Response**](ListSessions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of sessions |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## login

> GoogleLogin200Response login(loginRequest)

Login user

### Example

```ts
import {
  Configuration,
  AuthApi,
} from '@omnismith-sdk/typescript';
import type { LoginOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new AuthApi();

  const body = {
    // LoginRequest
    loginRequest: ...,
  } satisfies LoginOperationRequest;

  try {
    const data = await api.login(body);
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
| **loginRequest** | [LoginRequest](LoginRequest.md) |  | |

### Return type

[**GoogleLogin200Response**](GoogleLogin200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Login successful |  -  |
| **422** | Validation Error |  -  |
| **401** | Unauthorized |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## refreshToken

> RefreshToken200Response refreshToken(refreshTokenRequest)

Refresh access token

Exchange a valid refresh token for a new access token and refresh token. The old refresh token is invalidated (rotation).

### Example

```ts
import {
  Configuration,
  AuthApi,
} from '@omnismith-sdk/typescript';
import type { RefreshTokenOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new AuthApi();

  const body = {
    // RefreshTokenRequest
    refreshTokenRequest: ...,
  } satisfies RefreshTokenOperationRequest;

  try {
    const data = await api.refreshToken(body);
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
| **refreshTokenRequest** | [RefreshTokenRequest](RefreshTokenRequest.md) |  | |

### Return type

[**RefreshToken200Response**](RefreshToken200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Token refresh successful |  -  |
| **401** | Invalid, expired, or revoked refresh token |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeSession

> revokeSession(id)

Revoke a login session

### Example

```ts
import {
  Configuration,
  AuthApi,
} from '@omnismith-sdk/typescript';
import type { RevokeSessionRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AuthApi(config);

  const body = {
    // string | Session ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies RevokeSessionRequest;

  try {
    const data = await api.revokeSession(body);
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
| **id** | `string` | Session ID | [Defaults to `undefined`] |

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
| **204** | Session revoked |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Session not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## switchProject

> GoogleLogin200Response switchProject(switchProjectRequest)

Switch active project context

### Example

```ts
import {
  Configuration,
  AuthApi,
} from '@omnismith-sdk/typescript';
import type { SwitchProjectOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AuthApi(config);

  const body = {
    // SwitchProjectRequest
    switchProjectRequest: ...,
  } satisfies SwitchProjectOperationRequest;

  try {
    const data = await api.switchProject(body);
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
| **switchProjectRequest** | [SwitchProjectRequest](SwitchProjectRequest.md) |  | |

### Return type

[**GoogleLogin200Response**](GoogleLogin200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Project switched successfully |  -  |
| **422** | Validation Error |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

