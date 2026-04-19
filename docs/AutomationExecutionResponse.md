
# AutomationExecutionResponse


## Properties

Name | Type
------------ | -------------
`id` | string
`automation_id` | string
`entity_id` | string
`triggered_at` | Date
`completed_at` | Date
`status` | string
`action_results` | [Array&lt;AutomationExecutionResponseActionResultsInner&gt;](AutomationExecutionResponseActionResultsInner.md)
`error_message` | string

## Example

```typescript
import type { AutomationExecutionResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "automation_id": null,
  "entity_id": null,
  "triggered_at": null,
  "completed_at": null,
  "status": success,
  "action_results": null,
  "error_message": null,
} satisfies AutomationExecutionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AutomationExecutionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


