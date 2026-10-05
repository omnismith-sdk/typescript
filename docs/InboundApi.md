# InboundApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**addInboundEndpointSecret**](InboundApi.md#addinboundendpointsecretoperation) | **POST** /templates/{templateId}/inbound-endpoints/{id}/secrets | Add a secret to an inbound endpoint (start a rotation) |
| [**createTemplateInboundEndpoint**](InboundApi.md#createtemplateinboundendpoint) | **POST** /templates/{templateId}/inbound-endpoints | Create an inbound endpoint on a template |
| [**deleteInboundEndpointSecret**](InboundApi.md#deleteinboundendpointsecret) | **DELETE** /templates/{templateId}/inbound-endpoints/{id}/secrets/{secretId} | Remove a secret from an inbound endpoint (finish a rotation) |
| [**deleteTemplateInboundEndpoint**](InboundApi.md#deletetemplateinboundendpoint) | **DELETE** /templates/{templateId}/inbound-endpoints/{id} | Delete an inbound endpoint |
| [**getInboundDelivery**](InboundApi.md#getinbounddelivery) | **GET** /templates/{templateId}/inbound-endpoints/{id}/deliveries/{deliveryId} | Get one delivery an inbound endpoint received |
| [**getTemplateInboundEndpoint**](InboundApi.md#gettemplateinboundendpoint) | **GET** /templates/{templateId}/inbound-endpoints/{id} | Get an inbound endpoint |
| [**listInboundDeliveries**](InboundApi.md#listinbounddeliveries) | **GET** /templates/{templateId}/inbound-endpoints/{id}/deliveries | List the deliveries an inbound endpoint received |
| [**listTemplateInboundEndpoints**](InboundApi.md#listtemplateinboundendpoints) | **GET** /templates/{templateId}/inbound-endpoints | List the inbound endpoints of a template |
| [**previewInboundMapping**](InboundApi.md#previewinboundmappingoperation) | **POST** /templates/{templateId}/inbound-endpoints/{id}/preview | Preview what an inbound mapping does with a sample payload |
| [**receiveInboundDelivery**](InboundApi.md#receiveinbounddelivery) | **POST** /inbound/{projectId}/{endpointId} | Receive a delivery from an outside system |
| [**replayInboundDelivery**](InboundApi.md#replayinbounddelivery) | **POST** /templates/{templateId}/inbound-endpoints/{id}/deliveries/{deliveryId}/replay | Replay a stored inbound delivery through the current mapping |
| [**updateTemplateInboundEndpoint**](InboundApi.md#updatetemplateinboundendpoint) | **PATCH** /templates/{templateId}/inbound-endpoints/{id} | Update an inbound endpoint |



## addInboundEndpointSecret

> InboundSecretRevealed addInboundEndpointSecret(templateId, id, xOmnismithProjectId, addInboundEndpointSecretRequest)

Add a secret to an inbound endpoint (start a rotation)

Adds a second secret. Deliveries signed with either secret are accepted until the old one is removed with &#x60;deleteInboundEndpointSecret&#x60;. An endpoint holds at most two secrets. The body may be empty to have the secret generated.  The response carries the secret once and never again: give it to whoever configures the sender and do not store it anywhere else. Like updating the endpoint, this requires your own permission to create and edit records of the template.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { AddInboundEndpointSecretOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | Inbound endpoint UUID
    id: 01a0f0e2-7c1a-7000-8000-000000000001,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
    // AddInboundEndpointSecretRequest (optional)
    addInboundEndpointSecretRequest: ...,
  } satisfies AddInboundEndpointSecretOperationRequest;

  try {
    const data = await api.addInboundEndpointSecret(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **id** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
| **addInboundEndpointSecretRequest** | [AddInboundEndpointSecretRequest](AddInboundEndpointSecretRequest.md) |  | [Optional] |

### Return type

[**InboundSecretRevealed**](InboundSecretRevealed.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The new secret, shown once |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## createTemplateInboundEndpoint

> InboundEndpointCreatedResponse createTemplateInboundEndpoint(templateId, createInboundEndpointRequest, xOmnismithProjectId)

Create an inbound endpoint on a template

Creates a public URL through which an outside system (Stripe, GitHub, a form tool, a device) writes records into the template without an Omnismith credential. Pick the sender\&#39;s &#x60;signature&#x60; preset and describe the &#x60;mapping&#x60; from the payload to the template\&#39;s attributes.  The response carries the receive URL to configure in the sender and, once only, the secret the sender signs with. Hand both to the user, once, for pasting into the sender. Do not repeat the secret later and never store it in a record: it is never returned again, and a lost secret is replaced with &#x60;addInboundEndpointSecret&#x60; (the &#x60;add_inbound_endpoint_secret&#x60; tool).  To verify the feed: check the mapping on a sample event from the sender\&#39;s documentation with &#x60;previewInboundMapping&#x60; (the &#x60;preview_inbound_mapping&#x60; tool), ask the user to send a test event, then read &#x60;listInboundDeliveries&#x60; (the &#x60;list_inbound_deliveries&#x60; tool).  An endpoint lets its sender create and edit the template\&#39;s records, so creating one also requires your own permission to create and edit records of the template.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { CreateTemplateInboundEndpointRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // CreateInboundEndpointRequest
    createInboundEndpointRequest: ...,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies CreateTemplateInboundEndpointRequest;

  try {
    const data = await api.createTemplateInboundEndpoint(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **createInboundEndpointRequest** | [CreateInboundEndpointRequest](CreateInboundEndpointRequest.md) |  | |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**InboundEndpointCreatedResponse**](InboundEndpointCreatedResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Endpoint created, with its secret |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteInboundEndpointSecret

> deleteInboundEndpointSecret(templateId, id, secretId, xOmnismithProjectId)

Remove a secret from an inbound endpoint (finish a rotation)

Deliveries signed with this secret are rejected from now on. An endpoint keeps at least one secret, so the last one cannot be removed (422).

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { DeleteInboundEndpointSecretRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | Inbound endpoint UUID
    id: 01a0f0e2-7c1a-7000-8000-000000000001,
    // string | Secret UUID, from the endpoint\'s `secrets`
    secretId: 01a0f0e2-7c1a-7000-8000-0000000000c1,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies DeleteInboundEndpointSecretRequest;

  try {
    const data = await api.deleteInboundEndpointSecret(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **id** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
| **secretId** | `string` | Secret UUID, from the endpoint\&#39;s &#x60;secrets&#x60; | [Defaults to `undefined`] |
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
| **204** | Secret removed |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## deleteTemplateInboundEndpoint

> deleteTemplateInboundEndpoint(templateId, id, xOmnismithProjectId)

Delete an inbound endpoint

Deletes the endpoint. Its URL answers 404 from then on, so the sender\&#39;s deliveries stop being accepted. Records it wrote are not affected.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { DeleteTemplateInboundEndpointRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | Inbound endpoint UUID
    id: 01a0f0e2-7c1a-7000-8000-000000000001,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies DeleteTemplateInboundEndpointRequest;

  try {
    const data = await api.deleteTemplateInboundEndpoint(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **id** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
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
| **204** | Endpoint deleted |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getInboundDelivery

> InboundDeliveryDetail getInboundDelivery(templateId, id, deliveryId, xOmnismithProjectId)

Get one delivery an inbound endpoint received

One row of the delivery log with the stored body (at most 256 KB), the allow-listed headers, and &#x60;error&#x60;: for a rejected or partial delivery, the per-record &#x60;items&#x60; and field &#x60;errors&#x60; it was answered with. &#x60;deliveryId&#x60; is the &#x60;log_id&#x60; the sender was answered with. The stored body can serve as the sample for &#x60;previewInboundMapping&#x60; (&#x60;delivery_id&#x60;).

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { GetInboundDeliveryRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | Inbound endpoint UUID
    id: 01a0f0e2-7c1a-7000-8000-000000000001,
    // string | Delivery log row UUID
    deliveryId: 01a0f0e2-7c1a-7000-8000-0000000000d1,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies GetInboundDeliveryRequest;

  try {
    const data = await api.getInboundDelivery(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **id** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
| **deliveryId** | `string` | Delivery log row UUID | [Defaults to `undefined`] |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**InboundDeliveryDetail**](InboundDeliveryDetail.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The delivery |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## getTemplateInboundEndpoint

> InboundEndpointResponse getTemplateInboundEndpoint(templateId, id, xOmnismithProjectId)

Get an inbound endpoint

Returns the endpoint with its receive URL. Secret values are never returned; each secret shows only a hint.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { GetTemplateInboundEndpointRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | Inbound endpoint UUID
    id: 01a0f0e2-7c1a-7000-8000-000000000001,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies GetTemplateInboundEndpointRequest;

  try {
    const data = await api.getTemplateInboundEndpoint(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **id** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**InboundEndpointResponse**](InboundEndpointResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The endpoint |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listInboundDeliveries

> ListInboundDeliveries200Response listInboundDeliveries(templateId, id, xOmnismithProjectId, outcome, from, to, limit, offset)

List the deliveries an inbound endpoint received

The endpoint\&#39;s delivery log, newest first: every delivery that passed signature verification, and at most one signature failure per 10 seconds. Rows are kept for 7 days. Bodies are left out; read one delivery for its body and headers.  This is how a feed is verified after a test event. On &#x60;rejected&#x60; or &#x60;partial&#x60;, read the delivery with &#x60;getInboundDelivery&#x60; (the &#x60;get_inbound_delivery&#x60; tool) for its per-record errors, fix the mapping with &#x60;updateTemplateInboundEndpoint&#x60; (the &#x60;update_template_inbound_endpoint&#x60; tool), then recover it with &#x60;replayInboundDelivery&#x60; (the &#x60;replay_inbound_delivery&#x60; tool). A &#x60;401&#x60; row (&#x60;reason&#x60; &#x60;mismatch&#x60; or &#x60;missing_signature&#x60;) usually means the sender is configured with the wrong secret or header.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { ListInboundDeliveriesRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | Inbound endpoint UUID
    id: 01a0f0e2-7c1a-7000-8000-000000000001,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
    // Array<'processed' | 'partial' | 'skipped' | 'rejected' | 'failed'> | Only deliveries with one of these outcomes; comma-separated (optional)
    outcome: ["rejected","failed"],
    // Date | Only deliveries received at or after this RFC 3339 time (optional)
    from: 2026-10-01T00:00:00Z,
    // Date | Only deliveries received at or before this RFC 3339 time (optional)
    to: 2026-10-01T23:59:59Z,
    // number | Page size (optional)
    limit: 56,
    // number | Number of deliveries to skip (optional)
    offset: 56,
  } satisfies ListInboundDeliveriesRequest;

  try {
    const data = await api.listInboundDeliveries(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **id** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |
| **outcome** | `processed`, `partial`, `skipped`, `rejected`, `failed` | Only deliveries with one of these outcomes; comma-separated | [Optional] [Enum: processed, partial, skipped, rejected, failed] |
| **from** | `Date` | Only deliveries received at or after this RFC 3339 time | [Optional] [Defaults to `undefined`] |
| **to** | `Date` | Only deliveries received at or before this RFC 3339 time | [Optional] [Defaults to `undefined`] |
| **limit** | `number` | Page size | [Optional] [Defaults to `20`] |
| **offset** | `number` | Number of deliveries to skip | [Optional] [Defaults to `0`] |

### Return type

[**ListInboundDeliveries200Response**](ListInboundDeliveries200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | A page of the delivery log |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## listTemplateInboundEndpoints

> ListTemplateInboundEndpoints200Response listTemplateInboundEndpoints(templateId, xOmnismithProjectId)

List the inbound endpoints of a template

Returns every inbound endpoint that writes records into the template, in creation order, each with its receive URL, signature, mapping and secret hints. Secret values are never returned. The schema overview (&#x60;get_schema_overview&#x60;) already lists each template\&#39;s endpoints in brief.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { ListTemplateInboundEndpointsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies ListTemplateInboundEndpointsRequest;

  try {
    const data = await api.listTemplateInboundEndpoints(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**ListTemplateInboundEndpoints200Response**](ListTemplateInboundEndpoints200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Inbound endpoints of the template |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## previewInboundMapping

> PreviewInboundMapping200Response previewInboundMapping(templateId, id, previewInboundMappingRequest, xOmnismithProjectId)

Preview what an inbound mapping does with a sample payload

A dry run: maps a sample payload with the endpoint\&#39;s mapping, or with an unsaved &#x60;mapping&#x60; to try, and reports what each record would become. Nothing is written.  Use it before saving a mapping and before asking the sender for a test event: pass the sample event from the sender\&#39;s documentation as &#x60;body&#x60;, or a delivery from the endpoint\&#39;s log as &#x60;delivery_id&#x60;.  The answer says whether the &#x60;match&#x60; conditions hold, and per record: the external key, whether it would &#x60;create&#x60; or &#x60;update&#x60; a record (and which), the attribute values after list and reference resolution, in the write API\&#39;s shape, and the error a real delivery would meet: mapping errors, type errors and rule violations, keyed as on receive (&#x60;items[i].attributes.&lt;slug&gt;&#x60;). A mapping that does not fit the template, or an &#x60;items&#x60; path that names no list, is answered with 422.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { PreviewInboundMappingOperationRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | Inbound endpoint UUID
    id: 01a0f0e2-7c1a-7000-8000-000000000001,
    // PreviewInboundMappingRequest
    previewInboundMappingRequest: ...,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies PreviewInboundMappingOperationRequest;

  try {
    const data = await api.previewInboundMapping(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **id** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
| **previewInboundMappingRequest** | [PreviewInboundMappingRequest](PreviewInboundMappingRequest.md) |  | |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**PreviewInboundMapping200Response**](PreviewInboundMapping200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | What the mapping would do |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project selected, or the stored delivery cannot serve as a sample (no stored body, or a truncated one) |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## receiveInboundDelivery

> ReceiveInboundDelivery200Response receiveInboundDelivery(projectId, endpointId, requestBody)

Receive a delivery from an outside system

The receive URL of an inbound endpoint, called by the sending system rather than by API clients. It takes no Omnismith credential: every delivery must carry a valid signature for the endpoint.  - &#x60;200&#x60; — &#x60;processed&#x60;: every record was written. &#x60;partial&#x60;: some records failed; &#x60;errors&#x60; and &#x60;items&#x60; say which, and a replay recovers them. &#x60;skipped&#x60;: nothing was processed, with &#x60;reason&#x60; &#x60;match&#x60; (the mapping\&#39;s conditions did not hold), &#x60;no_items&#x60; (the items list was empty) or &#x60;duplicate&#x60; (the delivery id was already processed). - &#x60;400&#x60; — the body is not a JSON object or array. - &#x60;401&#x60; — the signature is missing or does not verify; &#x60;reason&#x60; says why. - &#x60;404&#x60; — no enabled endpoint at this URL. - &#x60;422&#x60; — no record could be written; &#x60;errors&#x60; are keyed &#x60;items[i].attributes.&lt;slug&gt;&#x60;, as the entity write API keys them. - &#x60;409&#x60;, &#x60;429&#x60;, &#x60;5xx&#x60; — the delivery could not be written right now (a key conflict, a quota or rate limit); retry later. - &#x60;413&#x60; — the body is over 1 MB.  Every answer after signature verification carries &#x60;log_id&#x60;, the delivery\&#39;s row in the endpoint\&#39;s delivery log.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { ReceiveInboundDeliveryRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const api = new InboundApi();

  const body = {
    // string | Project UUID
    projectId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // string | Inbound endpoint UUID
    endpointId: 38400000-8cf0-11bd-b23e-10b96e4ef00d,
    // { [key: string]: any; } | The sender\'s JSON payload, unchanged. At most 1 MB.
    requestBody: Object,
  } satisfies ReceiveInboundDeliveryRequest;

  try {
    const data = await api.receiveInboundDelivery(body);
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
| **projectId** | `string` | Project UUID | [Defaults to `undefined`] |
| **endpointId** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
| **requestBody** | `{ [key: string]: any; }` | The sender\&#39;s JSON payload, unchanged. At most 1 MB. | |

### Return type

[**ReceiveInboundDelivery200Response**](ReceiveInboundDelivery200Response.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Delivery accepted |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **404** | Not Found |  -  |
| **409** | External key conflict |  -  |
| **413** | Body over 1 MB |  -  |
| **422** | Validation Error |  -  |
| **429** | Quota or rate limit reached; retry later |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## replayInboundDelivery

> InboundDeliverySummary replayInboundDelivery(templateId, id, deliveryId, xOmnismithProjectId)

Replay a stored inbound delivery through the current mapping

Recovers a delivery after the mapping or the template was fixed: re-runs the endpoint\&#39;s current mapping on the stored body and writes the records, attributed to the endpoint as on receive. The signature is not verified again (only verified deliveries are stored) and the duplicate check is skipped.  Only &#x60;rejected&#x60;, &#x60;failed&#x60; and &#x60;partial&#x60; deliveries are replayed; for a &#x60;partial&#x60; one, only the records that failed. A processed or skipped delivery, one that failed signature verification (nothing of it was stored), and one whose stored body was truncated are refused with 409.  The replay is a new row in the delivery log, returned here, with &#x60;replay_of&#x60; naming the replayed delivery and &#x60;replayed_by&#x60; the user who asked. Its &#x60;outcome&#x60; says whether the records were written now.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { ReplayInboundDeliveryRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | Inbound endpoint UUID
    id: 01a0f0e2-7c1a-7000-8000-000000000001,
    // string | The delivery log row to replay
    deliveryId: 01a0f0e2-7c1a-7000-8000-0000000000d1,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies ReplayInboundDeliveryRequest;

  try {
    const data = await api.replayInboundDelivery(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **id** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
| **deliveryId** | `string` | The delivery log row to replay | [Defaults to `undefined`] |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**InboundDeliverySummary**](InboundDeliverySummary.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The replay\&#39;s own delivery log row |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project selected, or the delivery is not replayable |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


## updateTemplateInboundEndpoint

> InboundEndpointResponse updateTemplateInboundEndpoint(templateId, id, updateInboundEndpointRequest, xOmnismithProjectId)

Update an inbound endpoint

Partial update: send only the fields to change. &#x60;delivery_id_source: null&#x60; removes the delivery id source. Set &#x60;enabled: false&#x60; to stop accepting deliveries without deleting the endpoint. Secrets are changed with the secrets endpoints, never here.  Try a mapping change first with &#x60;previewInboundMapping&#x60; (the &#x60;preview_inbound_mapping&#x60; tool), which takes an unsaved &#x60;mapping&#x60;. After saving, recover the deliveries the old mapping rejected with &#x60;replayInboundDelivery&#x60; (the &#x60;replay_inbound_delivery&#x60; tool).  Like create, this requires your own permission to create and edit records of the template.

### Example

```ts
import {
  Configuration,
  InboundApi,
} from '@omnismith-sdk/typescript';
import type { UpdateTemplateInboundEndpointRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new InboundApi(config);

  const body = {
    // string | UUID or slug of the template
    templateId: customer,
    // string | Inbound endpoint UUID
    id: 01a0f0e2-7c1a-7000-8000-000000000001,
    // UpdateInboundEndpointRequest
    updateInboundEndpointRequest: ...,
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
  } satisfies UpdateTemplateInboundEndpointRequest;

  try {
    const data = await api.updateTemplateInboundEndpoint(body);
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
| **templateId** | `string` | UUID or slug of the template | [Defaults to `undefined`] |
| **id** | `string` | Inbound endpoint UUID | [Defaults to `undefined`] |
| **updateInboundEndpointRequest** | [UpdateInboundEndpointRequest](UpdateInboundEndpointRequest.md) |  | |
| **xOmnismithProjectId** | `string` | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\&#39;s &#x60;projects&#x60; claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code &#x60;stale_project_grant&#x60;; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 &#x60;no_project_selected&#x60;. Two clients holding the same credential may send different values at the same time. | [Optional] [Defaults to `undefined`] |

### Return type

[**InboundEndpointResponse**](InboundEndpointResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated endpoint |  -  |
| **400** | Bad Request |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **404** | Not Found |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |
| **422** | Validation Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

