
# WorkspaceViewResponse

Workspace view / pane configuration including template binding, filters, search settings, and presentation modes

## Properties

Name | Type
------------ | -------------
`id` | string
`workspace_id` | string
`template_id` | string
`name` | string
`filters` | Array&lt;object&gt;
`search_string` | string
`search_mode` | string
`sort` | [WorkspaceViewResponseSort](WorkspaceViewResponseSort.md)
`display_mode` | string
`displayed_columns` | Array&lt;string&gt;
`pane_order` | number
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { WorkspaceViewResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  "workspace_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  "template_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6a,
  "name": Active Gateways,
  "filters": [{"field":"status","operator":"eq","value":"active","is_active":true}],
  "search_string": gateway,
  "search_mode": keyword,
  "sort": null,
  "display_mode": table,
  "displayed_columns": ["name","status","ip_address","created_at"],
  "pane_order": 0,
  "created_at": 2026-08-26T12:00Z,
  "updated_at": 2026-08-26T12:30Z,
} satisfies WorkspaceViewResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WorkspaceViewResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


