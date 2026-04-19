
# AutomationExecutionResponseActionResultsInner


## Properties

Name | Type
------------ | -------------
`action_index` | number
`success` | boolean
`error_message` | string
`executed_at` | Date

## Example

```typescript
import type { AutomationExecutionResponseActionResultsInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "action_index": 0,
  "success": true,
  "error_message": null,
  "executed_at": null,
} satisfies AutomationExecutionResponseActionResultsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AutomationExecutionResponseActionResultsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


