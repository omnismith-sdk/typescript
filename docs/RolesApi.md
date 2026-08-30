# RolesApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**createRole**](RolesApi.md#createroleoperation) | **POST** /roles | Create a new role |
| [**deleteRole**](RolesApi.md#deleterole) | **DELETE** /roles/{id} | Delete a role |
| [**getRole**](RolesApi.md#getrole) | **GET** /roles/{id} | Get a role |
| [**getRolePermissions**](RolesApi.md#getrolepermissions) | **GET** /roles/{id}/permissions | Get role permissions |
| [**getRoleResources**](RolesApi.md#getroleresources) | **GET** /roles/{id}/resources | Get role resource restrictions |
| [**getRoleScopes**](RolesApi.md#getrolescopes) | **GET** /roles/{id}/scopes | Get role entity-access scopes |
| [**listAvailablePermissions**](RolesApi.md#listavailablepermissions) | **GET** /roles/permissions/available | List available permissions for role assignment |
| [**listRoles**](RolesApi.md#listroles) | **GET** /roles | List roles |
| [**setRolePermissions**](RolesApi.md#setrolepermissionsoperation) | **PUT** /roles/{id}/permissions | Set role permissions |
| [**setRoleResources**](RolesApi.md#setroleresourcesoperation) | **PUT** /roles/{id}/resources | Set role resource restrictions |
| [**setRoleScopes**](RolesApi.md#setrolescopesoperation) | **PUT** /roles/{id}/scopes | Set role entity-access scopes |
| [**updateRole**](RolesApi.md#updateroleoperation) | **PUT** /roles/{id} | Update a role |



## createRole

> CreateProject201Response createRole(createRoleRequest)

Create a new role

Creates a new custom role within the project. Role permissions, resource restrictions, and entity scopes can be configured subsequently.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { CreateRoleOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // CreateRoleRequest
    createRoleRequest: ...,
  } satisfies CreateRoleOperationRequest;

  try {
    const data = await api.createRole(body);
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
| **createRoleRequest** | [CreateRoleRequest](CreateRoleRequest.md) |  | |

### Return type

[**CreateProject201Response**](CreateProject201Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Role created |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteRole

> deleteRole(id)

Delete a role

Permanently deletes a custom role. System owner roles cannot be deleted. Any users assigned to this role must be reassigned.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { DeleteRoleRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // string | Unique UUID of the role to delete
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
  } satisfies DeleteRoleRequest;

  try {
    const data = await api.deleteRole(body);
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
| **id** | `string` | Unique UUID of the role to delete | [Defaults to `undefined`] |

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
| **204** | Role deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getRole

> RoleResponse getRole(id)

Get a role

Retrieves role metadata (name, is_owner status, creation timestamp) by role UUID.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { GetRoleRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // string | Unique UUID of the role
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
  } satisfies GetRoleRequest;

  try {
    const data = await api.getRole(body);
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
| **id** | `string` | Unique UUID of the role | [Defaults to `undefined`] |

### Return type

[**RoleResponse**](RoleResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Role details |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getRolePermissions

> GetRolePermissions200Response getRolePermissions(id)

Get role permissions

Returns the array of permission keys (e.g. \&quot;template.view\&quot;, \&quot;entity.create\&quot;, \&quot;attribute.manage\&quot;) explicitly granted to the specified role.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { GetRolePermissionsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // string | Unique UUID of the role
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
  } satisfies GetRolePermissionsRequest;

  try {
    const data = await api.getRolePermissions(body);
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
| **id** | `string` | Unique UUID of the role | [Defaults to `undefined`] |

### Return type

[**GetRolePermissions200Response**](GetRolePermissions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Role permissions |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getRoleResources

> GetRoleResources200Response getRoleResources(id)

Get role resource restrictions

Retrieves granular resource-level access restrictions configured for the role, specifying access levels (deny, view, edit, full) for particular templates or attributes.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { GetRoleResourcesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // string | Unique UUID of the role
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
  } satisfies GetRoleResourcesRequest;

  try {
    const data = await api.getRoleResources(body);
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
| **id** | `string` | Unique UUID of the role | [Defaults to `undefined`] |

### Return type

[**GetRoleResources200Response**](GetRoleResources200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Role resource restrictions |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getRoleScopes

> GetRoleScopes200Response getRoleScopes(id)

Get role entity-access scopes

Retrieves row-level entity access scopes for the role, which restrict what entity records matching specific attribute conditions the role can access within given templates.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { GetRoleScopesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // string | Unique UUID of the role
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
  } satisfies GetRoleScopesRequest;

  try {
    const data = await api.getRoleScopes(body);
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
| **id** | `string` | Unique UUID of the role | [Defaults to `undefined`] |

### Return type

[**GetRoleScopes200Response**](GetRoleScopes200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Role entity-access scopes |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listAvailablePermissions

> ListAvailablePermissions200Response listAvailablePermissions()

List available permissions for role assignment

Returns all user-assignable permissions grouped by module. Excludes internal-only permissions.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { ListAvailablePermissionsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  try {
    const data = await api.listAvailablePermissions();
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

[**ListAvailablePermissions200Response**](ListAvailablePermissions200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Available permissions grouped by module |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listRoles

> ListRoles200Response listRoles()

List roles

Lists all custom and predefined roles defined within the current project, including the project owner role.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { ListRolesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  try {
    const data = await api.listRoles();
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

[**ListRoles200Response**](ListRoles200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of roles |  -  |
| **401** | Unauthorized |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## setRolePermissions

> setRolePermissions(id, setRolePermissionsRequest)

Set role permissions

Replaces the entire set of permission keys assigned to the role with the provided list. Use GET /roles/permissions/available to inspect valid keys.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { SetRolePermissionsOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // string | Unique UUID of the role
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
    // SetRolePermissionsRequest
    setRolePermissionsRequest: ...,
  } satisfies SetRolePermissionsOperationRequest;

  try {
    const data = await api.setRolePermissions(body);
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
| **id** | `string` | Unique UUID of the role | [Defaults to `undefined`] |
| **setRolePermissionsRequest** | [SetRolePermissionsRequest](SetRolePermissionsRequest.md) |  | |

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
| **204** | Permissions updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## setRoleResources

> setRoleResources(id, setRoleResourcesRequest)

Set role resource restrictions

Replaces all resource-level access restrictions for the role. Each item defines a resource type (\&quot;template\&quot; or \&quot;attribute\&quot;), target resource UUID, and granted access level (\&quot;deny\&quot;, \&quot;view\&quot;, \&quot;edit\&quot;, \&quot;full\&quot;).

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { SetRoleResourcesOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // string | Unique UUID of the role
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
    // SetRoleResourcesRequest
    setRoleResourcesRequest: ...,
  } satisfies SetRoleResourcesOperationRequest;

  try {
    const data = await api.setRoleResources(body);
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
| **id** | `string` | Unique UUID of the role | [Defaults to `undefined`] |
| **setRoleResourcesRequest** | [SetRoleResourcesRequest](SetRoleResourcesRequest.md) |  | |

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
| **204** | Resource restrictions updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## setRoleScopes

> setRoleScopes(id, setRoleScopesRequest)

Set role entity-access scopes

Replaces row-level entity access scopes for the role. Conditions filter entity visibility based on field/attribute comparisons (operators: eq, neq, gt, lt, like, not-like, empty, not-empty).

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { SetRoleScopesOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // string | Unique UUID of the role
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
    // SetRoleScopesRequest
    setRoleScopesRequest: ...,
  } satisfies SetRoleScopesOperationRequest;

  try {
    const data = await api.setRoleScopes(body);
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
| **id** | `string` | Unique UUID of the role | [Defaults to `undefined`] |
| **setRoleScopesRequest** | [SetRoleScopesRequest](SetRoleScopesRequest.md) |  | |

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
| **204** | Entity-access scopes updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateRole

> updateRole(id, updateRoleRequest)

Update a role

Updates the display name of an existing custom role. System owner roles cannot be modified.

### Example

```ts
import {
  Configuration,
  RolesApi,
} from '@omnismith-sdk/typescript';
import type { UpdateRoleOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new RolesApi(config);

  const body = {
    // string | Unique UUID of the role
    id: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
    // UpdateRoleRequest
    updateRoleRequest: ...,
  } satisfies UpdateRoleOperationRequest;

  try {
    const data = await api.updateRole(body);
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
| **id** | `string` | Unique UUID of the role | [Defaults to `undefined`] |
| **updateRoleRequest** | [UpdateRoleRequest](UpdateRoleRequest.md) |  | |

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
| **204** | Role updated |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

