# AuditLogApi

All URIs are relative to *https://api.omnismith.io/v1*

| Method | HTTP request | Description |
|------------- | ------------- | -------------|
| [**listAuditLogs**](AuditLogApi.md#listauditlogs) | **GET** /audit-logs | List project audit logs |



## listAuditLogs

> ListAuditLogs200Response listAuditLogs(page, limit, sortBy, sortDirection, search, eventType, resourceType, resourceId, authorEmail, start, end)

List project audit logs

Returns an immutable, time-ordered audit trail of user and system events for the current project context.  ### Security &amp; Authorization Restricted to authenticated users holding the Project Owner role.  ### Comprehensive Filtering &amp; Search - &#x60;event_type&#x60;: Filter by single or comma-separated event types (e.g. &#x60;entity.created&#x60;, &#x60;entity.updated&#x60;, &#x60;entity.deleted&#x60;, &#x60;template.created&#x60;). - &#x60;resource_type&#x60;: Filter by domain target (e.g. &#x60;entity&#x60;, &#x60;template&#x60;, &#x60;attribute&#x60;, &#x60;project&#x60;). - &#x60;resource_id&#x60;: Filter by exact resource UUID. - &#x60;author_email&#x60;: Filter by the actor email address. - &#x60;start&#x60; and &#x60;end&#x60;: Date-time window bounding event occurrence (ISO 8601 or &#x60;YYYY-MM-DD HH:MM:SS&#x60;). - &#x60;search&#x60;: Text search across event types, resource types, resource IDs, author emails, and value summaries.  ### Pagination &amp; Sorting Supports 1-indexed pagination (&#x60;page&#x60;, &#x60;limit&#x60; up to 100) and sorting by &#x60;occurred_at&#x60;, &#x60;event_type&#x60;, &#x60;resource_type&#x60;, &#x60;resource_id&#x60;, or &#x60;author_email&#x60; (&#x60;asc&#x60;/&#x60;desc&#x60;).

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

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)

