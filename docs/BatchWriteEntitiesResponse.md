
# BatchWriteEntitiesResponse

Summary counters plus the outcome of every operation, in the order submitted.

## Properties

Name | Type
------------ | -------------
`atomic` | boolean
`total` | number
`created` | number
`updated` | number
`replaced` | number
`deleted` | number
`failed` | number
`results` | [Array&lt;BatchOperationResult&gt;](BatchOperationResult.md)

## Example

```typescript
import type { BatchWriteEntitiesResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "atomic": false,
  "total": 26,
  "created": 3,
  "updated": 22,
  "replaced": 1,
  "deleted": 1,
  "failed": 0,
  "results": null,
} satisfies BatchWriteEntitiesResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BatchWriteEntitiesResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


