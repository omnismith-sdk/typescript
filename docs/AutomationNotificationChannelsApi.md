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

> CreateNotificationChannel201Response createNotificationChannel(createNotificationChannelRequest, xOmnismithProjectId)

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteNotificationChannel

> deleteNotificationChannel(id, xOmnismithProjectId)

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **204** | Notification channel successfully deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Notification channel not found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getNotificationChannel

> NotificationChannelResponse getNotificationChannel(id, xOmnismithProjectId)

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listNotificationChannels

> ListNotificationChannels200Response listNotificationChannels(xOmnismithProjectId)

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

  const body = {
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies ListNotificationChannelsRequest;

  try {
    const data = await api.listNotificationChannels(body);
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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## testNotificationChannel

> TestNotificationChannel200Response testNotificationChannel(id, testNotificationChannelRequest, xOmnismithProjectId)

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateNotificationChannel

> updateNotificationChannel(id, updateNotificationChannelRequest, xOmnismithProjectId)

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
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
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
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

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
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

