
# UpdateWorkspaceRequest

Payload for updating workspace properties and layout

## Properties

Name | Type
------------ | -------------
`name` | string
`description` | string
`layout` | string
`is_default` | boolean
`sort_order` | number

## Example

```typescript
import type { UpdateWorkspaceRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Operations Hub,
  "description": Updated fleet operations workspace,
  "layout": quad,
  "is_default": true,
  "sort_order": 1,
} satisfies UpdateWorkspaceRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateWorkspaceRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


