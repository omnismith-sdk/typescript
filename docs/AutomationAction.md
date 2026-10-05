
# AutomationAction

One action an automation runs when its trigger fires and its conditions pass. Actions run in order; each succeeds or fails on its own, and the outcome is recorded per action on the execution.

## Properties

Name | Type
------------ | -------------
`type` | string
`config` | object

## Example

```typescript
import type { AutomationAction } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "type": update_entity,
  "config": {"target":{"kind":"trigger_entity"},"values":{"escalation_note":"No reply to {values.title} yet","escalated_at":"{timestamp}"}},
} satisfies AutomationAction

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AutomationAction
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


