# BillingApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createCheckout**](BillingApi.md#createcheckoutoperation) | **POST** /billing/checkout | Create a checkout session for subscription |
| [**getAllTiers**](BillingApi.md#getalltiers) | **GET** /billing/tiers | List all available tiers |
| [**getPortalUrl**](BillingApi.md#getportalurl) | **GET** /billing/portal | Get customer portal URL |
| [**getUsageInsights**](BillingApi.md#getusageinsights) | **GET** /billing/usage/insights | Get current tier usage insights |
| [**getUserTier**](BillingApi.md#getusertier) | **GET** /billing/tier | Get current user tier |
| [**logAiUsage**](BillingApi.md#logaiusageoperation) | **POST** /billing/log-usage | Log AI usage credits |



## createCheckout

> CheckoutResponse createCheckout(createCheckoutRequest)

Create a checkout session for subscription

Creates a LemonSqueezy checkout session to subscribe to a paid tier. Returns a URL to redirect the user to complete payment.

### Example

```ts
import {
  Configuration,
  BillingApi,
} from '@omnismith/sdk-typescript';
import type { CreateCheckoutOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BillingApi(config);

  const body = {
    // CreateCheckoutRequest
    createCheckoutRequest: ...,
  } satisfies CreateCheckoutOperationRequest;

  try {
    const data = await api.createCheckout(body);
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
| **createCheckoutRequest** | [CreateCheckoutRequest](CreateCheckoutRequest.md) |  | |

### Return type

[**CheckoutResponse**](CheckoutResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Checkout session created successfully |  -  |
| **400** | Invalid tier level (e.g., Free tier) |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAllTiers

> GetAllTiers200Response getAllTiers()

List all available tiers

### Example

```ts
import {
  Configuration,
  BillingApi,
} from '@omnismith/sdk-typescript';
import type { GetAllTiersRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const api = new BillingApi();

  try {
    const data = await api.getAllTiers();
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

[**GetAllTiers200Response**](GetAllTiers200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of all tiers |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getPortalUrl

> PortalUrlResponse getPortalUrl()

Get customer portal URL

Returns a LemonSqueezy customer portal URL where users can manage their subscription (cancel, update payment method, view invoices).

### Example

```ts
import {
  Configuration,
  BillingApi,
} from '@omnismith/sdk-typescript';
import type { GetPortalUrlRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BillingApi(config);

  try {
    const data = await api.getPortalUrl();
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

[**PortalUrlResponse**](PortalUrlResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Portal URL retrieved successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | No active subscription found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getUsageInsights

> UsageInsightsResponse getUsageInsights()

Get current tier usage insights

### Example

```ts
import {
  Configuration,
  BillingApi,
} from '@omnismith/sdk-typescript';
import type { GetUsageInsightsRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BillingApi(config);

  try {
    const data = await api.getUsageInsights();
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

[**UsageInsightsResponse**](UsageInsightsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Tier usage insights with limits and percentages |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getUserTier

> TierResponse getUserTier()

Get current user tier

### Example

```ts
import {
  Configuration,
  BillingApi,
} from '@omnismith/sdk-typescript';
import type { GetUserTierRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BillingApi(config);

  try {
    const data = await api.getUserTier();
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

[**TierResponse**](TierResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | User tier details |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## logAiUsage

> LogAiUsage200Response logAiUsage(logAiUsageRequest)

Log AI usage credits

### Example

```ts
import {
  Configuration,
  BillingApi,
} from '@omnismith/sdk-typescript';
import type { LogAiUsageOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new BillingApi(config);

  const body = {
    // LogAiUsageRequest
    logAiUsageRequest: ...,
  } satisfies LogAiUsageOperationRequest;

  try {
    const data = await api.logAiUsage(body);
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
| **logAiUsageRequest** | [LogAiUsageRequest](LogAiUsageRequest.md) |  | |

### Return type

[**LogAiUsage200Response**](LogAiUsage200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Usage logged successfully |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

