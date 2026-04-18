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

### Example

```ts
import {
  Configuration,
  UserApi,
} from '@omnismith/sdk-typescript';
import type { ConfirmUserEmailRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const api = new UserApi();

  const body = {
    // string | The email confirmation token
    token: token_example,
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
| **token** | `string` | The email confirmation token | [Defaults to `undefined`] |

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

> CreateAttributeItem201Response registerUser(registerUserRequest)

Register a new user

### Example

```ts
import {
  Configuration,
  UserApi,
} from '@omnismith/sdk-typescript';
import type { RegisterUserOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
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

[**CreateAttributeItem201Response**](CreateAttributeItem201Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | User registered successfully |  -  |
| **400** | Invalid input |  -  |
| **422** | Validation Failed |  -  |
| **409** | User already exists |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## resendConfirmationEmail

> ResendConfirmationEmail200Response resendConfirmationEmail(resendConfirmationEmailRequest)

Resend the email confirmation link

### Example

```ts
import {
  Configuration,
  UserApi,
} from '@omnismith/sdk-typescript';
import type { ResendConfirmationEmailOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
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
| **429** | Confirmation email already sent recently |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

