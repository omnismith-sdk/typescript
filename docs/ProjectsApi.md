# ProjectsApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**assignUserToProject**](ProjectsApi.md#assignusertoprojectoperation) | **POST** /projects/{id}/users | Assign user to project |
| [**createProject**](ProjectsApi.md#createprojectoperation) | **POST** /projects | Create a new project |
| [**deleteProject**](ProjectsApi.md#deleteproject) | **DELETE** /projects/{id} | Delete a project |
| [**dismissProjectTour**](ProjectsApi.md#dismissprojecttour) | **POST** /projects/{id}/dismiss-tour | Dismiss the interactive tour for a project |
| [**getProject**](ProjectsApi.md#getproject) | **GET** /projects/{id} | Get a project by ID |
| [**inviteUserToProject**](ProjectsApi.md#inviteusertoprojectoperation) | **POST** /projects/{id}/users/invite | Invite user to project by email |
| [**listProjectUsers**](ProjectsApi.md#listprojectusers) | **GET** /projects/{id}/users | List users in project |
| [**listProjects**](ProjectsApi.md#listprojects) | **GET** /projects | List all projects |
| [**removeUserFromProject**](ProjectsApi.md#removeuserfromproject) | **DELETE** /projects/{id}/users/{userId} | Remove user from project |
| [**updateProject**](ProjectsApi.md#updateprojectoperation) | **PUT** /projects/{id} | Update a project |



## assignUserToProject

> assignUserToProject(id, assignUserToProjectRequest)

Assign user to project

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { AssignUserToProjectOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // AssignUserToProjectRequest
    assignUserToProjectRequest: ...,
  } satisfies AssignUserToProjectOperationRequest;

  try {
    const data = await api.assignUserToProject(body);
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
| **assignUserToProjectRequest** | [AssignUserToProjectRequest](AssignUserToProjectRequest.md) |  | |

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
| **200** | User assigned |  -  |
| **404** | Project not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createProject

> CreateAttributeItem201Response createProject(createProjectRequest)

Create a new project

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { CreateProjectOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // CreateProjectRequest
    createProjectRequest: ...,
  } satisfies CreateProjectOperationRequest;

  try {
    const data = await api.createProject(body);
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
| **createProjectRequest** | [CreateProjectRequest](CreateProjectRequest.md) |  | |

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
| **201** | Project created |  -  |
| **422** | Validation Error |  -  |
| **500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteProject

> deleteProject(id)

Delete a project

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { DeleteProjectRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DeleteProjectRequest;

  try {
    const data = await api.deleteProject(body);
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
| **204** | Project deleted |  -  |
| **404** | Project not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## dismissProjectTour

> dismissProjectTour(id)

Dismiss the interactive tour for a project

Marks the interactive tour as dismissed for the given project, so it will not auto-trigger again.

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { DismissProjectTourRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies DismissProjectTourRequest;

  try {
    const data = await api.dismissProjectTour(body);
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
| **204** | Tour dismissed |  -  |
| **404** | Project not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getProject

> ProjectResponse getProject(id)

Get a project by ID

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { GetProjectRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies GetProjectRequest;

  try {
    const data = await api.getProject(body);
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

[**ProjectResponse**](ProjectResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Project details |  -  |
| **404** | Project not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## inviteUserToProject

> inviteUserToProject(id, inviteUserToProjectRequest)

Invite user to project by email

Invites a user to join a project using their email address. If the user exists, they are immediately assigned to the project with the specified role. If the user does not exist, a pending invitation will be created (future functionality).

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { InviteUserToProjectOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string | Project ID
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // InviteUserToProjectRequest
    inviteUserToProjectRequest: ...,
  } satisfies InviteUserToProjectOperationRequest;

  try {
    const data = await api.inviteUserToProject(body);
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
| **id** | `string` | Project ID | [Defaults to `undefined`] |
| **inviteUserToProjectRequest** | [InviteUserToProjectRequest](InviteUserToProjectRequest.md) |  | |

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
| **200** | User invited/assigned successfully |  -  |
| **404** | Project not found or user with email not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listProjectUsers

> ListProjectUsers200Response listProjectUsers(id)

List users in project

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { ListProjectUsersRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies ListProjectUsersRequest;

  try {
    const data = await api.listProjectUsers(body);
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

[**ListProjectUsers200Response**](ListProjectUsers200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of users in project |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listProjects

> ListProjects200Response listProjects()

List all projects

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { ListProjectsRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  try {
    const data = await api.listProjects();
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

[**ListProjects200Response**](ListProjects200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | List of projects |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## removeUserFromProject

> removeUserFromProject(id, userId)

Remove user from project

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { RemoveUserFromProjectRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string
    userId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
  } satisfies RemoveUserFromProjectRequest;

  try {
    const data = await api.removeUserFromProject(body);
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
| **userId** | `string` |  | [Defaults to `undefined`] |

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
| **204** | User removed |  -  |
| **404** | User not assigned to project |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateProject

> updateProject(id, updateProjectRequest)

Update a project

### Example

```ts
import {
  Configuration,
  ProjectsApi,
} from '@omnismith/sdk-typescript';
import type { UpdateProjectOperationRequest } from '@omnismith/sdk-typescript';

async function example() {
  console.log("🚀 Testing @omnismith/sdk-typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new ProjectsApi(config);

  const body = {
    // string
    id: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // UpdateProjectRequest
    updateProjectRequest: ...,
  } satisfies UpdateProjectOperationRequest;

  try {
    const data = await api.updateProject(body);
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
| **updateProjectRequest** | [UpdateProjectRequest](UpdateProjectRequest.md) |  | |

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
| **200** | Project updated |  -  |
| **404** | Project not found |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

