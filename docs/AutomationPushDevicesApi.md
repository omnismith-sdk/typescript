# AutomationPushDevicesApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listPushDevices**](AutomationPushDevicesApi.md#listpushdevices) | **GET** /automation/push-devices | List the current user\&#39;s registered push devices |
| [**registerPushDevice**](AutomationPushDevicesApi.md#registerpushdeviceoperation) | **POST** /automation/push-devices | Register a push notification device token |
| [**unregisterPushDevice**](AutomationPushDevicesApi.md#unregisterpushdeviceoperation) | **DELETE** /automation/push-devices | Unregister a push notification device token |



## listPushDevices

> ListPushDevices200Response listPushDevices()

List the current user\&#39;s registered push devices

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
| **200** | List of push devices |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## registerPushDevice

> CreateAttributeItem201Response registerPushDevice(registerPushDeviceRequest)

Register a push notification device token

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

[**CreateAttributeItem201Response**](CreateAttributeItem201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Device registered |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## unregisterPushDevice

> unregisterPushDevice(unregisterPushDeviceRequest)

Unregister a push notification device token

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
| **204** | Device unregistered |  -  |
| **401** | Unauthorized |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

