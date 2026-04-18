# FeedbackApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**sendFeedback**](FeedbackApi.md#sendfeedbackoperation) | **POST** /feedback | Submit user feedback |



## sendFeedback

> sendFeedback(sendFeedbackRequest)

Submit user feedback

Sends a feedback email to the Omnismith support team on behalf of the authenticated user.

### Example

```ts
import {
  Configuration,
  FeedbackApi,
} from '@omnismith/sdk-typescript';
import type { SendFeedbackOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FeedbackApi(config);

  const body = {
    // SendFeedbackRequest
    sendFeedbackRequest: ...,
  } satisfies SendFeedbackOperationRequest;

  try {
    const data = await api.sendFeedback(body);
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
| **sendFeedbackRequest** | [SendFeedbackRequest](SendFeedbackRequest.md) |  | |

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
| **204** | Feedback submitted successfully |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Failed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

