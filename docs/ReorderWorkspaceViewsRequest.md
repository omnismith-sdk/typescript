
# ReorderWorkspaceViewsRequest

Payload containing the reordered list of workspace view IDs

## Properties

Name | Type
------------ | -------------
`view_ids` | Array&lt;string&gt;

## Example

```typescript
import type { ReorderWorkspaceViewsRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "view_ids": ["0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c","0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6d"],
} satisfies ReorderWorkspaceViewsRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ReorderWorkspaceViewsRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


