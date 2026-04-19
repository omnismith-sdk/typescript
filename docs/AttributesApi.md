# AttributesApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createAttribute**](AttributesApi.md#createattributeoperation) | **POST** /attributes | Create a new attribute |
| [**createAttributeItem**](AttributesApi.md#createattributeitem) | **POST** /attributes/{id}/items | Add a list item to an attribute |
| [**deleteAttribute**](AttributesApi.md#deleteattribute) | **DELETE** /attributes/{id} | Delete an attribute |
| [**deleteAttributeItem**](AttributesApi.md#deleteattributeitem) | **DELETE** /attributes/{id}/items/{itemId} | Remove a list item from an attribute |
| [**deleteAttributeReferenceConfig**](AttributesApi.md#deleteattributereferenceconfig) | **DELETE** /attributes/{id}/reference | Delete reference configuration for an attribute |
| [**getAttribute**](AttributesApi.md#getattribute) | **GET** /attributes/{id} | Get an attribute |
| [**getAttributeReferenceConfig**](AttributesApi.md#getattributereferenceconfig) | **GET** /attributes/{id}/reference | Get reference configuration for an attribute |
| [**getProjectSchema**](AttributesApi.md#getprojectschema) | **GET** /discovery/project-schema | Get complete project schema |
| [**listAttributeItems**](AttributesApi.md#listattributeitems) | **GET** /attributes/{id}/items | List items of an attribute |
| [**listAttributes**](AttributesApi.md#listattributes) | **GET** /attributes | List attributes |
| [**setAttributeItems**](AttributesApi.md#setattributeitems) | **PUT** /attributes/{id}/items | Set list items for an attribute (replaces all existing items) |
| [**setAttributeReferenceConfig**](AttributesApi.md#setattributereferenceconfig) | **PUT** /attributes/{id}/reference | Set or update reference configuration for an attribute |
| [**updateAttribute**](AttributesApi.md#updateattributeoperation) | **PUT** /attributes/{id} | Update an attribute |
| [**updateAttributeItem**](AttributesApi.md#updateattributeitem) | **PUT** /attributes/{id}/items/{itemId} | Update a list item of an attribute |



## createAttribute

> CreateAttributeItem201Response createAttribute(createAttributeRequest)

Create a new attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { CreateAttributeOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // CreateAttributeRequest
    createAttributeRequest: ...,
  } satisfies CreateAttributeOperationRequest;

  try {
    const data = await api.createAttribute(body);
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
| **createAttributeRequest** | [CreateAttributeRequest](CreateAttributeRequest.md) |  | |

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
| **201** | Attribute created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **402** | Tier quota exceeded |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createAttributeItem

> CreateAttributeItem201Response createAttributeItem(id, addListItemRequest)

Add a list item to an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { CreateAttributeItemRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string | Attribute ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // AddListItemRequest
    addListItemRequest: ...,
  } satisfies CreateAttributeItemRequest;

  try {
    const data = await api.createAttributeItem(body);
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
| **id** | `string` | Attribute ID | [Defaults to `undefined`] |
| **addListItemRequest** | [AddListItemRequest](AddListItemRequest.md) |  | |

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
| **201** | Item created |  -  |
| **404** | Attribute not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAttribute

> deleteAttribute(id)

Delete an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { DeleteAttributeRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteAttributeRequest;

  try {
    const data = await api.deleteAttribute(body);
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
| **204** | Attribute deleted |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAttributeItem

> deleteAttributeItem(id, itemId)

Remove a list item from an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { DeleteAttributeItemRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string | Attribute ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string | List Item ID
    itemId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteAttributeItemRequest;

  try {
    const data = await api.deleteAttributeItem(body);
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
| **id** | `string` | Attribute ID | [Defaults to `undefined`] |
| **itemId** | `string` | List Item ID | [Defaults to `undefined`] |

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
| **204** | Item removed |  -  |
| **404** | Item or Attribute not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteAttributeReferenceConfig

> deleteAttributeReferenceConfig(id)

Delete reference configuration for an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { DeleteAttributeReferenceConfigRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string | Attribute ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteAttributeReferenceConfigRequest;

  try {
    const data = await api.deleteAttributeReferenceConfig(body);
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
| **id** | `string` | Attribute ID | [Defaults to `undefined`] |

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
| **204** | Reference config deleted |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAttribute

> AttributeResponse getAttribute(id)

Get an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { GetAttributeRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetAttributeRequest;

  try {
    const data = await api.getAttribute(body);
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

[**AttributeResponse**](AttributeResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Attribute details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getAttributeReferenceConfig

> ReferenceConfigResponse getAttributeReferenceConfig(id)

Get reference configuration for an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { GetAttributeReferenceConfigRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string | Attribute ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetAttributeReferenceConfigRequest;

  try {
    const data = await api.getAttributeReferenceConfig(body);
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
| **id** | `string` | Attribute ID | [Defaults to `undefined`] |

### Return type

[**ReferenceConfigResponse**](ReferenceConfigResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Reference config |  -  |
| **404** | Reference config not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getProjectSchema

> ProjectSchemaResponse getProjectSchema()

Get complete project schema

Returns all attributes, templates, list items, and reference configs in a single response

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { GetProjectSchemaRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

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


## listAttributeItems

> ListAttributeItems200Response listAttributeItems(id)

List items of an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { ListAttributeItemsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string | Attribute ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies ListAttributeItemsRequest;

  try {
    const data = await api.listAttributeItems(body);
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
| **id** | `string` | Attribute ID | [Defaults to `undefined`] |

### Return type

[**ListAttributeItems200Response**](ListAttributeItems200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of items |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAttributes

> ListAttributes200Response listAttributes()

List attributes

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { ListAttributesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  try {
    const data = await api.listAttributes();
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

[**ListAttributes200Response**](ListAttributes200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of attributes |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## setAttributeItems

> setAttributeItems(id, setListItemsRequest)

Set list items for an attribute (replaces all existing items)

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { SetAttributeItemsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string | Attribute ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // SetListItemsRequest
    setListItemsRequest: ...,
  } satisfies SetAttributeItemsRequest;

  try {
    const data = await api.setAttributeItems(body);
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
| **id** | `string` | Attribute ID | [Defaults to `undefined`] |
| **setListItemsRequest** | [SetListItemsRequest](SetListItemsRequest.md) |  | |

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
| **204** | Items updated |  -  |
| **400** | Attribute is not a List type |  -  |
| **404** | Attribute not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## setAttributeReferenceConfig

> setAttributeReferenceConfig(id, setReferenceConfigRequest)

Set or update reference configuration for an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { SetAttributeReferenceConfigRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string | Attribute ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // SetReferenceConfigRequest
    setReferenceConfigRequest: ...,
  } satisfies SetAttributeReferenceConfigRequest;

  try {
    const data = await api.setAttributeReferenceConfig(body);
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
| **id** | `string` | Attribute ID | [Defaults to `undefined`] |
| **setReferenceConfigRequest** | [SetReferenceConfigRequest](SetReferenceConfigRequest.md) |  | |

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
| **204** | Reference config updated |  -  |
| **400** | Attribute is not a Reference type |  -  |
| **404** | Attribute not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateAttribute

> updateAttribute(id, updateAttributeRequest)

Update an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { UpdateAttributeOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // UpdateAttributeRequest
    updateAttributeRequest: ...,
  } satisfies UpdateAttributeOperationRequest;

  try {
    const data = await api.updateAttribute(body);
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
| **updateAttributeRequest** | [UpdateAttributeRequest](UpdateAttributeRequest.md) |  | |

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
| **204** | Attribute updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateAttributeItem

> updateAttributeItem(id, itemId, updateListItemRequest)

Update a list item of an attribute

### Example

```ts
import {
  Configuration,
  AttributesApi,
} from '@omnismith-sdk/typescript';
import type { UpdateAttributeItemRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AttributesApi(config);

  const body = {
    // string | Attribute ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string | List Item ID
    itemId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // UpdateListItemRequest
    updateListItemRequest: ...,
  } satisfies UpdateAttributeItemRequest;

  try {
    const data = await api.updateAttributeItem(body);
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
| **id** | `string` | Attribute ID | [Defaults to `undefined`] |
| **itemId** | `string` | List Item ID | [Defaults to `undefined`] |
| **updateListItemRequest** | [UpdateListItemRequest](UpdateListItemRequest.md) |  | |

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
| **204** | Item updated |  -  |
| **404** | Item or Attribute not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

