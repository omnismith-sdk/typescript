
# CreateAutomationRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`description` | string
`trigger` | [CreateAutomationRequestTrigger](CreateAutomationRequestTrigger.md)
`conditions` | [Array&lt;CreateAutomationRequestConditionsInner&gt;](CreateAutomationRequestConditionsInner.md)
`actions` | [Array&lt;CreateAutomationRequestActionsInner&gt;](CreateAutomationRequestActionsInner.md)
`cooldownSeconds` | number

## Example

```typescript
import type { CreateAutomationRequest } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Notify on status change,
  "description": Sends alert when status changes,
  "trigger": null,
  "conditions": null,
  "actions": null,
  "cooldownSeconds": 60,
} satisfies CreateAutomationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateAutomationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


