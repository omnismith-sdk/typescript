# AutomationNotificationChannelsApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createNotificationChannel**](AutomationNotificationChannelsApi.md#createnotificationchanneloperation) | **POST** /automation/notification-channels | Create a new notification channel |
| [**deleteNotificationChannel**](AutomationNotificationChannelsApi.md#deletenotificationchannel) | **DELETE** /automation/notification-channels/{id} | Delete a notification channel |
| [**getNotificationChannel**](AutomationNotificationChannelsApi.md#getnotificationchannel) | **GET** /automation/notification-channels/{id} | Get a notification channel |
| [**listNotificationChannels**](AutomationNotificationChannelsApi.md#listnotificationchannels) | **GET** /automation/notification-channels | List all notification channels |
| [**testNotificationChannel**](AutomationNotificationChannelsApi.md#testnotificationchanneloperation) | **POST** /automation/notification-channels/{id}/test | Send a test message via the notification channel |
| [**updateNotificationChannel**](AutomationNotificationChannelsApi.md#updatenotificationchanneloperation) | **PUT** /automation/notification-channels/{id} | Update a notification channel |



## createNotificationChannel

> CreateAttributeItem201Response createNotificationChannel(createNotificationChannelRequest)

Create a new notification channel

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith/sdk-typescript';
import type { CreateNotificationChannelOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  const body = {
    // CreateNotificationChannelRequest
    createNotificationChannelRequest: ...,
  } satisfies CreateNotificationChannelOperationRequest;

  try {
    const data = await api.createNotificationChannel(body);
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
| **createNotificationChannelRequest** | [CreateNotificationChannelRequest](CreateNotificationChannelRequest.md) |  | |

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
| **201** | Channel created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteNotificationChannel

> deleteNotificationChannel(id)

Delete a notification channel

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith/sdk-typescript';
import type { DeleteNotificationChannelRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  const body = {
    // string | Channel UUID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteNotificationChannelRequest;

  try {
    const data = await api.deleteNotificationChannel(body);
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
| **id** | `string` | Channel UUID | [Defaults to `undefined`] |

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
| **204** | Channel deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getNotificationChannel

> NotificationChannelResponse getNotificationChannel(id)

Get a notification channel

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith/sdk-typescript';
import type { GetNotificationChannelRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  const body = {
    // string | Channel UUID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetNotificationChannelRequest;

  try {
    const data = await api.getNotificationChannel(body);
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
| **id** | `string` | Channel UUID | [Defaults to `undefined`] |

### Return type

[**NotificationChannelResponse**](NotificationChannelResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Channel details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listNotificationChannels

> ListNotificationChannels200Response listNotificationChannels()

List all notification channels

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith/sdk-typescript';
import type { ListNotificationChannelsRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  try {
    const data = await api.listNotificationChannels();
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

[**ListNotificationChannels200Response**](ListNotificationChannels200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of channels |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## testNotificationChannel

> TestNotificationChannel200Response testNotificationChannel(id, testNotificationChannelRequest)

Send a test message via the notification channel

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith/sdk-typescript';
import type { TestNotificationChannelOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  const body = {
    // string | Channel UUID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // TestNotificationChannelRequest
    testNotificationChannelRequest: ...,
  } satisfies TestNotificationChannelOperationRequest;

  try {
    const data = await api.testNotificationChannel(body);
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
| **id** | `string` | Channel UUID | [Defaults to `undefined`] |
| **testNotificationChannelRequest** | [TestNotificationChannelRequest](TestNotificationChannelRequest.md) |  | |

### Return type

[**TestNotificationChannel200Response**](TestNotificationChannel200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Test message sent successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Test failed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateNotificationChannel

> updateNotificationChannel(id, updateNotificationChannelRequest)

Update a notification channel

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith/sdk-typescript';
import type { UpdateNotificationChannelOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  const body = {
    // string | Channel UUID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // UpdateNotificationChannelRequest
    updateNotificationChannelRequest: ...,
  } satisfies UpdateNotificationChannelOperationRequest;

  try {
    const data = await api.updateNotificationChannel(body);
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
| **id** | `string` | Channel UUID | [Defaults to `undefined`] |
| **updateNotificationChannelRequest** | [UpdateNotificationChannelRequest](UpdateNotificationChannelRequest.md) |  | |

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
| **204** | Channel updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

