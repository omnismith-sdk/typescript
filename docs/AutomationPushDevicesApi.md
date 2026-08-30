# AutomationPushDevicesApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listPushDevices**](AutomationPushDevicesApi.md#listpushdevices) | **GET** /automation/push-devices | List registered push devices |
| [**registerPushDevice**](AutomationPushDevicesApi.md#registerpushdeviceoperation) | **POST** /automation/push-devices | Register a mobile push notification device |
| [**unregisterPushDevice**](AutomationPushDevicesApi.md#unregisterpushdeviceoperation) | **DELETE** /automation/push-devices | Unregister a mobile push notification device |



## listPushDevices

> ListPushDevices200Response listPushDevices()

List registered push devices

Retrieves all Firebase Cloud Messaging (FCM) mobile push devices registered under the authenticated user account for receiving automated push alerts. Device registration tokens are masked in the output for security.

### Example

```ts
import {
  Configuration,
  AutomationPushDevicesApi,
} from '@omnismith-sdk/typescript';
import type { ListPushDevicesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationPushDevicesApi(config);

  try {
    const data = await api.listPushDevices();
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

[**ListPushDevices200Response**](ListPushDevices200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of registered push notification devices |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## registerPushDevice

> RegisterPushDevice201Response registerPushDevice(registerPushDeviceRequest)

Register a mobile push notification device

Registers an FCM device token under the authenticated user account to receive real-time push notifications from automation action triggers. If the token is already registered, its device name and activity timestamp are updated.

### Example

```ts
import {
  Configuration,
  AutomationPushDevicesApi,
} from '@omnismith-sdk/typescript';
import type { RegisterPushDeviceOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationPushDevicesApi(config);

  const body = {
    // RegisterPushDeviceRequest
    registerPushDeviceRequest: ...,
  } satisfies RegisterPushDeviceOperationRequest;

  try {
    const data = await api.registerPushDevice(body);
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
| **registerPushDeviceRequest** | [RegisterPushDeviceRequest](RegisterPushDeviceRequest.md) |  | |

### Return type

[**RegisterPushDevice201Response**](RegisterPushDevice201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Push device successfully registered |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## unregisterPushDevice

> unregisterPushDevice(unregisterPushDeviceRequest)

Unregister a mobile push notification device

Removes an FCM push notification device token from the authenticated user profile, stopping all future automation push notifications directed to that device.

### Example

```ts
import {
  Configuration,
  AutomationPushDevicesApi,
} from '@omnismith-sdk/typescript';
import type { UnregisterPushDeviceOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AutomationPushDevicesApi(config);

  const body = {
    // UnregisterPushDeviceRequest
    unregisterPushDeviceRequest: ...,
  } satisfies UnregisterPushDeviceOperationRequest;

  try {
    const data = await api.unregisterPushDevice(body);
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
| **unregisterPushDeviceRequest** | [UnregisterPushDeviceRequest](UnregisterPushDeviceRequest.md) |  | |

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
| **204** | Push device successfully unregistered |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

