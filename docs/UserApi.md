# UserApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**confirmUserEmail**](UserApi.md#confirmuseremail) | **GET** /users/confirm-email | Confirm a user\&#39;s email address using a confirmation token |
| [**registerUser**](UserApi.md#registeruseroperation) | **POST** /users/register | Register a new user |
| [**resendConfirmationEmail**](UserApi.md#resendconfirmationemailoperation) | **POST** /users/resend-confirmation | Resend the email confirmation link |



## confirmUserEmail

> ConfirmUserEmail200Response confirmUserEmail(token)

Confirm a user\&#39;s email address using a confirmation token

Validates an email confirmation token sent to a newly registered user\&#39;s email address and activates the account upon success. If the token is valid, returns a success confirmation message.

### Example

```ts
import {
  Configuration,
  UserApi,
} from '@omnismith-sdk/typescript';
import type { ConfirmUserEmailRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new UserApi();

  const body = {
    // string | The email confirmation token received via email
    token: cf_token_abc123xyz,
  } satisfies ConfirmUserEmailRequest;

  try {
    const data = await api.confirmUserEmail(body);
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
| **token** | `string` | The email confirmation token received via email | [Defaults to `undefined`] |

### Return type

[**ConfirmUserEmail200Response**](ConfirmUserEmail200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Email confirmed successfully |  -  |
| **400** | Invalid confirmation token |  -  |
| **410** | Confirmation token expired |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## registerUser

> CreateProject201Response registerUser(registerUserRequest)

Register a new user

Registers a new user account with email and password. For unauthenticated / public signups, a Cloudflare Turnstile &#x60;captchaToken&#x60; is required to prevent bot abuse. Sends a confirmation link to the provided email address upon creation.

### Example

```ts
import {
  Configuration,
  UserApi,
} from '@omnismith-sdk/typescript';
import type { RegisterUserOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new UserApi();

  const body = {
    // RegisterUserRequest
    registerUserRequest: ...,
  } satisfies RegisterUserOperationRequest;

  try {
    const data = await api.registerUser(body);
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
| **registerUserRequest** | [RegisterUserRequest](RegisterUserRequest.md) |  | |

### Return type

[**CreateProject201Response**](CreateProject201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | User registered successfully |  -  |
| **400** | Bad Request |  -  |
| **422** | Validation Error |  -  |
| **409** | Conflict |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## resendConfirmationEmail

> ResendConfirmationEmail200Response resendConfirmationEmail(resendConfirmationEmailRequest)

Resend the email confirmation link

Resends the account verification email with an activation link for unconfirmed accounts. Rate-limited to prevent abuse. Silently succeeds if the email is not registered for security.

### Example

```ts
import {
  Configuration,
  UserApi,
} from '@omnismith-sdk/typescript';
import type { ResendConfirmationEmailOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new UserApi();

  const body = {
    // ResendConfirmationEmailRequest
    resendConfirmationEmailRequest: ...,
  } satisfies ResendConfirmationEmailOperationRequest;

  try {
    const data = await api.resendConfirmationEmail(body);
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
| **resendConfirmationEmailRequest** | [ResendConfirmationEmailRequest](ResendConfirmationEmailRequest.md) |  | |

### Return type

[**ResendConfirmationEmail200Response**](ResendConfirmationEmail200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Confirmation email sent (or silently ignored if user not found) |  -  |
| **422** | Validation Error |  -  |
| **429** | Too Many Requests |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

