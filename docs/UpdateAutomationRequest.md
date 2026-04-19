
# UpdateAutomationRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`description` | string
`trigger` | [UpdateAutomationRequestTrigger](UpdateAutomationRequestTrigger.md)
`conditions` | [Array&lt;AutomationResponseConditionsInner&gt;](AutomationResponseConditionsInner.md)
`actions` | [Array&lt;AutomationResponseActionsInner&gt;](AutomationResponseActionsInner.md)
`cooldownSeconds` | number

## Example

```typescript
import type { UpdateAutomationRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Updated automation name,
  "description": Updated description,
  "trigger": null,
  "conditions": null,
  "actions": null,
  "cooldownSeconds": 120,
} satisfies UpdateAutomationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateAutomationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


