# SchemaApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**getProjectSchema**](SchemaApi.md#getprojectschema) | **GET** /discovery/project-schema | Get complete project schema |



## getProjectSchema

> ProjectSchemaResponse getProjectSchema()

Get complete project schema

Returns all attributes, templates, list items, and reference configs in a single response

### Example

```ts
import {
  Configuration,
  SchemaApi,
} from '@omnismith-sdk/typescript';
import type { GetProjectSchemaRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new SchemaApi(config);

  try {
    const data = await api.getProjectSchema();
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

[**ProjectSchemaResponse**](ProjectSchemaResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Project schema |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

