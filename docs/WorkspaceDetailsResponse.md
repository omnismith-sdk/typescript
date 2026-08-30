
# WorkspaceDetailsResponse

Workspace details including configuration and fully hydrated view panes

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`description` | string
`layout` | string
`is_default` | boolean
`sort_order` | number
`views` | [Array&lt;WorkspaceViewResponse&gt;](WorkspaceViewResponse.md)
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { WorkspaceDetailsResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  "name": Operations Hub,
  "description": Daily fleet monitoring workspace,
  "layout": split-v,
  "is_default": false,
  "sort_order": 0,
  "views": null,
  "created_at": 2026-08-26T12:00Z,
  "updated_at": 2026-08-26T12:30Z,
} satisfies WorkspaceDetailsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as WorkspaceDetailsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


