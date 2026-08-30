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

Permanently deletes a file attachment and its stored content from disk. If the file is referenced by entity attribute values (file or image data type), those references will become stale. Returns 204 on success.

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
    // string | File attachment UUID to delete
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
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
| **id** | `string` | File attachment UUID to delete | [Defaults to `undefined`] |

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

Returns the raw binary file content for a given file attachment ID. The response Content-Type header matches the original uploaded file MIME type. The file must belong to the authenticated user\&#39;s project.

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
    // string | Unique UUID identifier of the file attachment to download
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
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
| **id** | `string` | Unique UUID identifier of the file attachment to download | [Defaults to `undefined`] |

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

Returns metadata for a file attachment (original filename, MIME type, file size in bytes, upload timestamp, context) without streaming the binary content. Use this to inspect file properties before deciding whether to download.

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
    // string | Unique UUID identifier of the file attachment
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
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
| **id** | `string` | Unique UUID identifier of the file attachment | [Defaults to `undefined`] |

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

Generates and returns a resized thumbnail for image-type file attachments (JPEG, PNG, WebP, GIF). Optional &#x60;width&#x60; and &#x60;height&#x60; query parameters control output dimensions (range 50–1000px, default 200×200). Returns 400 if the file is not an image type. The thumbnail is returned as JPEG binary.

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
    // string | Unique UUID identifier of the image file attachment
    id: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // number | Target thumbnail width in pixels (range 50 to 1000, default 200) (optional)
    width: 200,
    // number | Target thumbnail height in pixels (range 50 to 1000, default 200) (optional)
    height: 200,
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
| **id** | `string` | Unique UUID identifier of the image file attachment | [Defaults to `undefined`] |
| **width** | `number` | Target thumbnail width in pixels (range 50 to 1000, default 200) | [Optional] [Defaults to `200`] |
| **height** | `number` | Target thumbnail height in pixels (range 50 to 1000, default 200) | [Optional] [Defaults to `200`] |

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

> FileAttachmentResponse uploadFileAttachment(file, id, context, ttlHours)

Upload a file attachment

Uploads a file as a multipart/form-data request. Supported MIME types include images (JPEG, PNG, WebP, GIF, SVG), documents (PDF), spreadsheets (CSV, XLSX), and structured data (JSON, YAML). An optional pre-generated UUIDv7 &#x60;id&#x60; can be supplied; otherwise the server generates one. The &#x60;context&#x60; field controls storage lifecycle: \&quot;entity\&quot; files are permanent, \&quot;chat\&quot; files are temporary with configurable &#x60;ttl_hours&#x60; (default 48h). Returns the file metadata including the assigned ID for use in entity attribute values.

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
    // string (optional)
    context: context_example,
    // number (optional)
    ttlHours: 56,
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
| **context** | `entity`, `chat` |  | [Optional] [Defaults to `&#39;entity&#39;`] [Enum: entity, chat] |
| **ttlHours** | `number` |  | [Optional] [Defaults to `undefined`] |

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

