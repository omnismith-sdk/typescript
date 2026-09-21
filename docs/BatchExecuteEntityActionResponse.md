
# BatchExecuteEntityActionResponse

Summary counters plus the outcome for every record, in the order submitted.

## Properties

Name | Type
------------ | -------------
`atomic` | boolean
`total` | number
`executed` | number
`precondition_failed` | number
`rule_violated` | number
`failed` | number
`results` | [Array&lt;EntityActionOutcome&gt;](EntityActionOutcome.md)

## Example

```typescript
import type { BatchExecuteEntityActionResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "atomic": false,
  "total": 40,
  "executed": 37,
  "precondition_failed": 2,
  "rule_violated": 1,
  "failed": 0,
  "results": null,
} satisfies BatchExecuteEntityActionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BatchExecuteEntityActionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


