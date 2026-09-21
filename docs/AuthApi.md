# AuthApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getMyPermissions**](AuthApi.md#getmypermissions) | **GET** /auth/me/permissions | Discover authenticated caller permissions and capabilities |
| [**googleLogin**](AuthApi.md#googleloginoperation) | **POST** /auth/google-login | Authenticate or register with Google Sign-In |
| [**googleLoginRedirect**](AuthApi.md#googleloginredirect) | **POST** /auth/google-login-redirect | Google OAuth callback redirect handler |
| [**listSessions**](AuthApi.md#listsessions) | **GET** /auth/sessions | List active and historical user sessions |
| [**login**](AuthApi.md#loginoperation) | **POST** /auth/login | Authenticate user with email and password |
| [**refreshToken**](AuthApi.md#refreshtokenoperation) | **POST** /auth/refresh | Rotate refresh token and issue new access token |
| [**revokeSession**](AuthApi.md#revokesession) | **DELETE** /auth/sessions/{id} | Revoke an active login session |



## getMyPermissions

> GetMyPermissions200Response getMyPermissions(xOmnismithProjectId)

Discover authenticated caller permissions and capabilities

Returns the complete list of permission keys granted to the authenticated user or agent under their active project role. Call this endpoint before planning or executing multi-step schema modifications, role administration, or entity mutations to verify current operational capabilities. Returns &#x60;[\&quot;*\&quot;]&#x60; for project owners who possess root administrative privileges, or an array of granular permission keys (e.g. &#x60;entity.view&#x60;, &#x60;entity.create&#x60;, &#x60;template.create&#x60;, &#x60;billing.view_usage&#x60;) for assigned roles. Returns an empty array if no role is currently assigned.

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

  const body = {
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies GetMyPermissionsRequest;

  try {
    const data = await api.getMyPermissions(body);
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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

Authenticate or register with Google Sign-In

Authenticates a user using a Google Identity Services (GIS) ID token. Verifies the cryptographic token signature against Google public keys. If no account exists for the verified email address, a new user account is automatically provisioned and verified. Returns a JWT access token and refresh token for the active session.

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
| **200** | Authentication successful with issued JWT access and refresh tokens |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## googleLoginRedirect

> googleLoginRedirect(credential, gCsrfToken)

Google OAuth callback redirect handler

Handles Google Identity Services form-urlencoded POST redirection (&#x60;credential&#x60; and &#x60;g_csrf_token&#x60;). Authenticates or provisions the user account, initiates an active session, and redirects the browser (HTTP 302) to the frontend application callback URL with JWT access and refresh tokens embedded in the URL fragment.

### Example

```ts
import {
  Configuration,
  AuthApi,
} from '@omnismith-sdk/typescript';
import type { GoogleLoginRedirectRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new AuthApi();

  const body = {
    // string | Google ID token credential issued by Google Identity Services
    credential: credential_example,
    // string | CSRF token provided by Google Identity Services (optional)
    gCsrfToken: gCsrfToken_example,
  } satisfies GoogleLoginRedirectRequest;

  try {
    const data = await api.googleLoginRedirect(body);
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
| **credential** | `string` | Google ID token credential issued by Google Identity Services | [Defaults to `undefined`] |
| **gCsrfToken** | `string` | CSRF token provided by Google Identity Services | [Optional] [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/x-www-form-urlencoded`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **302** | Redirects to the frontend application callback route (/auth/google-callback#...) with authentication tokens in the URL fragment |  -  |
| **400** | Bad Request |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listSessions

> ListSessions200Response listSessions()

List active and historical user sessions

Retrieves all login sessions recorded for the authenticated user across devices and browsers. Each session record includes client metadata (IP address, User-Agent), issuance timestamp, expiration date, current status (&#x60;active&#x60;, &#x60;expired&#x60;, &#x60;revoked&#x60;), and revocation details if applicable.

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
| **200** | List of login session records |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## login

> GoogleLogin200Response login(loginRequest)

Authenticate user with email and password

Authenticates an existing user account using email and password. Upon successful validation, generates an active login session and returns a short-lived JWT access token and a refresh token for rotating credentials.

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
| **200** | Authentication successful with issued JWT access and refresh tokens |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## refreshToken

> RefreshToken200Response refreshToken(refreshTokenRequest)

Rotate refresh token and issue new access token

Exchanges a valid refresh token for a newly issued JWT access token and a rotated refresh token. Implements strict single-use refresh token rotation: the supplied refresh token is permanently invalidated upon successful exchange. If an expired, already-rotated, or revoked token is presented, the request is rejected. The refresh token alone authenticates the call; no &#x60;Authorization&#x60; header is required, and one sent alongside is ignored.

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
| **200** | Token refresh successful with rotated credentials |  -  |
| **401** | Invalid, expired, or revoked refresh token |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## revokeSession

> revokeSession(id)

Revoke an active login session

Immediately revokes a specific user login session by its unique session ID. All refresh tokens issued within this session are invalidated, preventing further token refreshes. If the revoked session corresponds to the current client connection, subsequent refresh attempts will fail.

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
    // string | Unique UUID identifier of the session to revoke
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
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
| **id** | `string` | Unique UUID identifier of the session to revoke | [Defaults to `undefined`] |

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
| **204** | Session revoked successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

