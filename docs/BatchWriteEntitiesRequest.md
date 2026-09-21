
# BatchWriteEntitiesRequest

An ordered, mixed list of entity writes applied in one call.

## Properties

Name | Type
------------ | -------------
`operations` | [Array&lt;BatchOperationInput&gt;](BatchOperationInput.md)
`atomic` | boolean

## Example

```typescript
import type { BatchWriteEntitiesRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "operations": null,
  "atomic": false,
} satisfies BatchWriteEntitiesRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BatchWriteEntitiesRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


