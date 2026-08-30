# AutomationNotificationChannelsApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createNotificationChannel**](AutomationNotificationChannelsApi.md#createnotificationchanneloperation) | **POST** /automation/notification-channels | Create a notification channel |
| [**deleteNotificationChannel**](AutomationNotificationChannelsApi.md#deletenotificationchannel) | **DELETE** /automation/notification-channels/{id} | Delete a notification channel |
| [**getNotificationChannel**](AutomationNotificationChannelsApi.md#getnotificationchannel) | **GET** /automation/notification-channels/{id} | Get a notification channel by ID |
| [**listNotificationChannels**](AutomationNotificationChannelsApi.md#listnotificationchannels) | **GET** /automation/notification-channels | List notification channels |
| [**testNotificationChannel**](AutomationNotificationChannelsApi.md#testnotificationchanneloperation) | **POST** /automation/notification-channels/{id}/test | Send a test notification message |
| [**updateNotificationChannel**](AutomationNotificationChannelsApi.md#updatenotificationchanneloperation) | **PUT** /automation/notification-channels/{id} | Update a notification channel |



## createNotificationChannel

> CreateNotificationChannel201Response createNotificationChannel(createNotificationChannelRequest)

Create a notification channel

Registers a new external notification channel for the current project. Channels can be of type &#x60;telegram&#x60; (configured with a Telegram bot token), &#x60;webhook&#x60; (configured with endpoint URL, custom HTTP headers, and authentication methods such as bearer token or basic auth), or &#x60;push&#x60; (FCM mobile push notifications). Configured channels can then be linked as target actions in automation rules.

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith-sdk/typescript';
import type { CreateNotificationChannelOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
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

[**CreateNotificationChannel201Response**](CreateNotificationChannel201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Notification channel successfully created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteNotificationChannel

> deleteNotificationChannel(id)

Delete a notification channel

Permanently removes a notification channel from the project by UUID. Automations referencing this channel must be updated to prevent dispatch delivery failures.

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith-sdk/typescript';
import type { DeleteNotificationChannelRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  const body = {
    // string | Unique notification channel UUID to delete
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60002,
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
| **id** | `string` | Unique notification channel UUID to delete | [Defaults to `undefined`] |

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
| **204** | Notification channel successfully deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Notification channel not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getNotificationChannel

> NotificationChannelResponse getNotificationChannel(id)

Get a notification channel by ID

Retrieves configuration details and status of a specific notification channel by its UUID, including channel type, name, creation timestamp, and credential settings for authorized project administrators.

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith-sdk/typescript';
import type { GetNotificationChannelRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  const body = {
    // string | Unique notification channel UUID
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60002,
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
| **id** | `string` | Unique notification channel UUID | [Defaults to `undefined`] |

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
| **200** | Notification channel details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Notification channel not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listNotificationChannels

> ListNotificationChannels200Response listNotificationChannels()

List notification channels

Retrieves all notification delivery channels configured within the current project. Channels are reusable destination targets for automation alerts, supporting Telegram bots, external HTTP webhooks, and mobile push notifications. Sensitive credentials are sanitized in list outputs.

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith-sdk/typescript';
import type { ListNotificationChannelsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
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
| **200** | List of configured notification channels |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## testNotificationChannel

> TestNotificationChannel200Response testNotificationChannel(id, testNotificationChannelRequest)

Send a test notification message

Dispatches an immediate test notification message to verify channel credentials, network reachability, and recipient configuration. Accepts channel-specific parameters such as Telegram &#x60;chat_id&#x60; or push notification &#x60;title&#x60; and &#x60;message&#x60;.

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith-sdk/typescript';
import type { TestNotificationChannelOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  const body = {
    // string | Unique notification channel UUID to test
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60002,
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
| **id** | `string` | Unique notification channel UUID to test | [Defaults to `undefined`] |
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
| **200** | Test message delivered successfully |  -  |
| **401** | Unauthorized |  -  |
| **404** | Notification channel not found |  -  |
| **422** | Test message delivery failed |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateNotificationChannel

> updateNotificationChannel(id, updateNotificationChannelRequest)

Update a notification channel

Updates an existing notification channel configuration by UUID. Allows updating the channel display name or updating integration credentials (such as new bot tokens, webhook endpoints, or authentication credentials).

### Example

```ts
import {
  Configuration,
  AutomationNotificationChannelsApi,
} from '@omnismith-sdk/typescript';
import type { UpdateNotificationChannelOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationNotificationChannelsApi(config);

  const body = {
    // string | Unique notification channel UUID to update
    id: 01912ecb-4654-7890-a1b2-c3d4e5f60002,
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
| **id** | `string` | Unique notification channel UUID to update | [Defaults to `undefined`] |
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
| **204** | Notification channel successfully updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Notification channel not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

