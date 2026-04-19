# FileAttachmentApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**deleteFileAttachment**](FileAttachmentApi.md#deletefileattachment) | **DELETE** /file-attachments/{id} | Delete a file attachment |
| [**downloadFileAttachment**](FileAttachmentApi.md#downloadfileattachment) | **GET** /file-attachments/{id} | Download a file attachment |
| [**getFileAttachmentMetadata**](FileAttachmentApi.md#getfileattachmentmetadata) | **GET** /file-attachments/{id}/metadata | Get file metadata without downloading content |
| [**getFileAttachmentThumbnail**](FileAttachmentApi.md#getfileattachmentthumbnail) | **GET** /file-attachments/{id}/thumbnail | Get image thumbnail |
| [**uploadFileAttachment**](FileAttachmentApi.md#uploadfileattachment) | **POST** /file-attachments | Upload a file attachment |



## deleteFileAttachment

> deleteFileAttachment(id)

Delete a file attachment

### Example

```ts
import {
  Configuration,
  FileAttachmentApi,
} from '@omnismith-sdk/typescript';
import type { DeleteFileAttachmentRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FileAttachmentApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteFileAttachmentRequest;

  try {
    const data = await api.deleteFileAttachment(body);
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
| **id** | `string` |  | [Defaults to `undefined`] |

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
| **204** | File deleted |  -  |
| **404** | File not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## downloadFileAttachment

> downloadFileAttachment(id)

Download a file attachment

### Example

```ts
import {
  Configuration,
  FileAttachmentApi,
} from '@omnismith-sdk/typescript';
import type { DownloadFileAttachmentRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FileAttachmentApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DownloadFileAttachmentRequest;

  try {
    const data = await api.downloadFileAttachment(body);
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
| **id** | `string` |  | [Defaults to `undefined`] |

### Return type

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | File content |  -  |
| **404** | File not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getFileAttachmentMetadata

> FileAttachmentResponse getFileAttachmentMetadata(id)

Get file metadata without downloading content

### Example

```ts
import {
  Configuration,
  FileAttachmentApi,
} from '@omnismith-sdk/typescript';
import type { GetFileAttachmentMetadataRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FileAttachmentApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetFileAttachmentMetadataRequest;

  try {
    const data = await api.getFileAttachmentMetadata(body);
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
| **id** | `string` |  | [Defaults to `undefined`] |

### Return type

[**FileAttachmentResponse**](FileAttachmentResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | File metadata |  -  |
| **404** | File not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getFileAttachmentThumbnail

> getFileAttachmentThumbnail(id, width, height)

Get image thumbnail

### Example

```ts
import {
  Configuration,
  FileAttachmentApi,
} from '@omnismith-sdk/typescript';
import type { GetFileAttachmentThumbnailRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FileAttachmentApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // number (optional)
    width: 56,
    // number (optional)
    height: 56,
  } satisfies GetFileAttachmentThumbnailRequest;

  try {
    const data = await api.getFileAttachmentThumbnail(body);
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
| **id** | `string` |  | [Defaults to `undefined`] |
| **width** | `number` |  | [Optional] [Defaults to `200`] |
| **height** | `number` |  | [Optional] [Defaults to `200`] |

### Return type

`void` (Empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `image/jpeg`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Thumbnail image |  -  |
| **400** | Not an image or invalid dimensions |  -  |
| **404** | File not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## uploadFileAttachment

> FileAttachmentResponse uploadFileAttachment(file, id)

Upload a file attachment

### Example

```ts
import {
  Configuration,
  FileAttachmentApi,
} from '@omnismith-sdk/typescript';
import type { UploadFileAttachmentRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new FileAttachmentApi(config);

  const body = {
    // Blob
    file: BINARY_DATA_HERE,
    // string (optional)
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies UploadFileAttachmentRequest;

  try {
    const data = await api.uploadFileAttachment(body);
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
| **file** | `Blob` |  | [Defaults to `undefined`] |
| **id** | `string` |  | [Optional] [Defaults to `undefined`] |

### Return type

[**FileAttachmentResponse**](FileAttachmentResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | File uploaded |  -  |
| **400** | Bad request |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

