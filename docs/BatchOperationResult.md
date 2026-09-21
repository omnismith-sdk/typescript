
# BatchOperationResult

The outcome of a single operation. On failure, `error` carries the same body the equivalent single-entity endpoint would have returned.

## Properties

Name | Type
------------ | -------------
`index` | number
`op` | string
`id` | string
`status` | string
`error` | [ErrorResponse](ErrorResponse.md)

## Example

```typescript
import type { BatchOperationResult } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "index": 0,
  "op": update,
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "status": ok,
  "error": null,
} satisfies BatchOperationResult

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BatchOperationResult
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


