
# AutomationTimerResponse


## Properties

Name | Type
------------ | -------------
`id` | string
`automation_id` | string
`automation_name` | string
`entity_id` | string
`kind` | string
`due_at` | Date

## Example

```typescript
import type { AutomationTimerResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 5f0c1a2b-3c4d-5e6f-8a9b-0c1d2e3f4a5b,
  "automation_id": 01912ecb-4654-7890-a1b2-c3d4e5f60001,
  "automation_name": Renewal reminder,
  "entity_id": 01912ecb-4654-7890-a1b2-c3d4e5f60099,
  "kind": date_reached,
  "due_at": 2026-11-01T09:00Z,
} satisfies AutomationTimerResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AutomationTimerResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


