
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
  "id": 01912ecb-4654-7890-a1b2-c3d4e5f60010,
  "automation_id": 01912ecb-4654-7890-a1b2-c3d4e5f60001,
  "entity_id": 01912ecb-4654-7890-a1b2-c3d4e5f60099,
  "triggered_at": 2026-08-26T12:00Z,
  "completed_at": 2026-08-26T12:00:01Z,
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


