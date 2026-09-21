# AuditLogApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listAuditLogs**](AuditLogApi.md#listauditlogs) | **GET** /audit-logs | List project audit logs |



## listAuditLogs

> ListAuditLogs200Response listAuditLogs(xOmnismithProjectId, page, limit, sortBy, sortDirection, search, eventType, resourceType, resourceId, authorEmail, start, end)

List project audit logs

Returns an immutable, time-ordered audit trail of user and system events for the current project context. Restricted to authenticated users holding the Project Owner role. Returns paginated &#x60;items&#x60;, each an event (&#x60;event_type&#x60;, &#x60;resource_type&#x60;/&#x60;resource_id&#x60;, &#x60;author_email&#x60;, a &#x60;value&#x60; summary, &#x60;occurred_at&#x60;) plus &#x60;total&#x60; matching records.

### Example

```ts
import {
  Configuration,
  AuditLogApi,
} from '@omnismith-sdk/typescript';
import type { ListAuditLogsRequest } from '@omnismith-sdk/typescript';

async function example() {
  console.log("🚀 Testing @omnismith-sdk/typescript SDK...");
  const config = new Configuration({ 
    // Configure HTTP bearer authorization: bearerAuth
    accessToken: "YOUR BEARER TOKEN",
  });
  const api = new AuditLogApi(config);

  const body = {
    // string | The project this call acts on. A credential proves identity and grants a set of projects; it never selects one, so every tenant-scoped call names its target here. The value must be one of the projects in the credential\'s `projects` claim and must still be reachable — a project the caller is not a member of, or one that has been deleted, is rejected with 403 rather than silently ignored. A project the caller *is* a member of but which the credential predates is also rejected with 403, carrying the code `stale_project_grant`; that one is answered by refreshing the credential once and retrying, and is the only 403 here worth retrying. Omitting the header is not an error: the caller is simply acting with no project selected, and a tenant-scoped operation then answers 409 `no_project_selected`. Two clients holding the same credential may send different values at the same time. (optional)
    xOmnismithProjectId: 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7d,
    // number | 1-based page number for pagination (optional)
    page: 1,
    // number | Number of audit log records per page (1-100) (optional)
    limit: 20,
    // 'occurred_at' | 'event_type' | 'resource_type' | 'resource_id' | 'author_email' | Field to sort audit log entries by (optional)
    sortBy: occurred_at,
    // 'asc' | 'desc' | Sort direction: \"asc\" (ascending) or \"desc\" (descending) (optional)
    sortDirection: desc,
    // string | Text search filter across event_type, resource_type, resource_id, author_email, and value (optional)
    search: entity.created,
    // string | Filter by single or comma-separated event types (e.g. \"entity.created,entity.updated\") (optional)
    eventType: entity.created,
    // string | Filter by single or comma-separated resource types (e.g. \"entity,template,attribute\") (optional)
    resourceType: entity,
    // string | Filter by exact resource unique identifier (UUID) (optional)
    resourceId: 018b2f1b-8c1a-75b3-8000-7f0000010000,
    // string | Filter by actor or author email address (optional)
    authorEmail: demo@omnismith.io,
    // Date | Filter audit records occurring on or after this timestamp (ISO 8601 format) (optional)
    start: 2026-08-01T00:00:00Z,
    // Date | Filter audit records occurring on or before this timestamp (ISO 8601 format) (optional)
    end: 2026-08-26T23:59:59Z,
  } satisfies ListAuditLogsRequest;

  try {
    const data = await api.listAuditLogs(body);
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
| **page** | `number` | 1-based page number for pagination | [Optional] [Defaults to `1`] |
| **limit** | `number` | Number of audit log records per page (1-100) | [Optional] [Defaults to `20`] |
| **sortBy** | `occurred_at`, `event_type`, `resource_type`, `resource_id`, `author_email` | Field to sort audit log entries by | [Optional] [Defaults to `&#39;occurred_at&#39;`] [Enum: occurred_at, event_type, resource_type, resource_id, author_email] |
| **sortDirection** | `asc`, `desc` | Sort direction: \&quot;asc\&quot; (ascending) or \&quot;desc\&quot; (descending) | [Optional] [Defaults to `&#39;desc&#39;`] [Enum: asc, desc] |
| **search** | `string` | Text search filter across event_type, resource_type, resource_id, author_email, and value | [Optional] [Defaults to `undefined`] |
| **eventType** | `string` | Filter by single or comma-separated event types (e.g. \&quot;entity.created,entity.updated\&quot;) | [Optional] [Defaults to `undefined`] |
| **resourceType** | `string` | Filter by single or comma-separated resource types (e.g. \&quot;entity,template,attribute\&quot;) | [Optional] [Defaults to `undefined`] |
| **resourceId** | `string` | Filter by exact resource unique identifier (UUID) | [Optional] [Defaults to `undefined`] |
| **authorEmail** | `string` | Filter by actor or author email address | [Optional] [Defaults to `undefined`] |
| **start** | `Date` | Filter audit records occurring on or after this timestamp (ISO 8601 format) | [Optional] [Defaults to `undefined`] |
| **end** | `Date` | Filter audit records occurring on or before this timestamp (ISO 8601 format) | [Optional] [Defaults to `undefined`] |

### Return type

[**ListAuditLogs200Response**](ListAuditLogs200Response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated list of audit log records |  -  |
| **401** | Unauthorized |  -  |
| **403** | Forbidden |  -  |
| **409** | No project is selected. The caller is authenticated but the request is tenant-scoped, so a project must be selected before it can be answered. The response body carries &#x60;\&quot;code\&quot;: \&quot;no_project_selected\&quot;&#x60;, which clients branch on to offer a project picker rather than an access-denied message. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

