
# DuplicateWorkspaceRequest

Payload for duplicating an existing workspace

## Properties

Name | Type
------------ | -------------
`new_name` | string

## Example

```typescript
import type { DuplicateWorkspaceRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "new_name": Operations Hub (Copy),
} satisfies DuplicateWorkspaceRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as DuplicateWorkspaceRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


